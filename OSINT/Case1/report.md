#  OSINT Investigation Report – Missing Person Case (TryHackMe)

## Overview

A friend reportedly went on holiday in 2025 and shared a series of photos before losing contact. The objective of this investigation was to analyze the provided evidence and reconstruct the subject’s movements to assist in a potential police report.

---

## Tools & Techniques Used

* Reverse image search (Google Images, Yandex)
* EXIF Metadata Analysis (ExifTool)
* Open Source Intelligence (OSINT)
* Geolocation via Google Maps
* Social Media enumeration
* Pivoting Techniques
* SpiderFoot 

---

## Investigation Process

### 1. Identifying the Circuit

BY using reverse image search on the first provided image (MotoGP.jpg) I was able to match the visual data with publicly available images. This led to identifying the location as:

> **Pertamina Mandalika International Street Circuit**

---

### 2.Date
Based on the scenario indicating the year 2025, I correlated the circuit with known events using open-source searches. This confirmed the event took place on:

> **03–05/10/2025**

---

### 3. Restaurant Identification

The second image (food.jpg) was analyzed using reverse image search on both Google Images and Yandex. Cross-referencing results led to identifying the restaurant as:

> **Cantina Mexicana**

---

### 4. Timestamp Extraction

To determine when the photo was taken, I analyzed the image metadata using **ExifTool**. The original timestamp revealed:

> **19:55:30**

---

### 5. Locating the Afterparty Bar

Based on the message referencing a MotoGP afterparty, I searched for related events in the area during that timeframe. Two potential events were identified.

By cross-referencing:

* Event details
* Venue information
* Satellite imagery (Google Maps)

I confirmed the correct location and extracted the full address:

> **Jl. Raya Kuta, Kuta, Kec. Pujut, Kabupaten Lombok Tengah, Nusa Tenggara Bar**

---

### 6. Identifying the DJ

From the event lineup and local DJ appearances during the afterparty, I identified the relevant individual as:

> **Bong Leleh**

This was determined by narrowing down DJs performing at the specific venue and matching the “local DJ” clue from the scenario.

---

### 7. Pivoting to social Media (Cave discovery)

Using the DJ’s stage name, I performed OSINT enumeration via **SpiderFoot**, which revealed linked social media accounts.

A TikTok account associated with the DJ contained videos showcasing guided tours to a cave. From this content, I identified:

> **Gua Sumur**

---

### 8. Extracting Contact Information

Further searches on Google combining the DJ’s(Bong Leleh) name with the name of the specific cave(Gua Sumur),led to a profile with his username where he offers guided tours in this cave.This included a contact number:

> **085333137345**

---

## Key OSINT Techniques Applied

* Reverse image correlation
* Metadata extraction
* Event-based pivoting
* Identity linking across platforms
* Social media intelligence gathering
* Location verification via satellite imagery

---

## Timeline of Events

| Time / Date             | Event Description                                                                |
| ----------------------- | -------------------------------------------------------------------------------- |
| 03–05/10/2025           | Subject attends MotoGP event at Pertamina Mandalika International Street Circuit |
| 03–05/10/2025           |   >>     dines at Cantina Mexicana                                               |
| 19:55:30                | Photo captured at restaurant (based on EXIF metadata)                            |
| Same night              | Attends MotoGP afterparty at bar located in Kuta Lombok                          |
| Same night              | Meets local DJ “Bong Leleh”                                                      |
| Following day           | Plans visit to cave (as we see in last message)                                  |
| Unknown time            | Dj linked to tourist visits at Gua Sumur                                         |
| Unknown time            | Contact number associated with DJ’s tour activity identified (085333137345)      |

---

---

## Conclusion

Through structured OSINT methodology and systematic pivoting, it was possible to reconstruct the subject’s movements and identify keylocations, and activities leading up to their disappearance.


## Notes

This report is part of hands-on practice from TryHackMe, focusing on:

* OSINT investigations
* Real-world analytical thinking
* Tool-based intelligence gathering

---
