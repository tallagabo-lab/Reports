# OSINT Investigation Report – Missing Person Case (from TryHackMe)

## Overview

This investigation was conducted as part of an OSINT scenario involving a missing individual. The only available evidence consisted of a small set of images and a final message referencing travel activity in 2025.
The goal was to reconstruct the subject’s movements and identify any relevant locations, events, or individuals that could assist in locating them.

---

## Summary

Starting from just two images and a short message, it was possible to trace the subject’s journey to Indonesia, identify a major event they attended, and uncover their interactions leading up to their disappearance.

Through a combination of image analysis, metadata extraction, and social media investigation, the subject was linked to:
- A MotogP event at a specific racing circuit
- A restaurant visit
- An after-party location
- A local DJ who later became a key person of interest

The investigation ultimately revealed a likely next destination and a contact number tied to that individual.

---

## Methodology

The approach followed a typical OSINT workflow:

- Reverse image search to identify locations
- Metadata analysis for timestamps
- Correlation with public event data
- Targeted search queries for contextual clues
- Social media pivoting 

**The process was iterative — each finding led to the next step.**

---

## Investigation Walkthrough

### 1. Identifying the Location

The investigation began with reverse image search on the provided photos using Google Images.

One of the images matched a well-known motorsport location:
- **Pertamina Mandalika International Street Circuit**

This was confirmed by comparing visual elements and verifying the location via maps.

---

### 2. Determining the Event Date

Knowing the location and that the trip occurred in 2025, the next step was to correlate events hosted at the circuit.
By reviewing public event schedules, the relevant event was identified:
- **03–05/10/2025**

---

### 3. Restaurant Identification

A second image showed a dining location. Using reverse image search again, the place was identified as:
- **Cantina Mexicana**

This aligned with the subject’s mention of Mexican food.

---

### 4. Extracting Metadata

The image files were analyzed using EXIF tools to extract embedded metadata.
This revealed:
- **Timestamp: 19:55:30**

This helped establish a more precise timeline of activity.

---

### 5. Locating the after-party

The subject’s final message referenced a MotoGP after-party.

Using targeted searches combining:
- Event name
- Location
- Keywords like “after party”

The following location was identified:
- **Jl. Raya Kuta, Kuta, Kec. Pujut, Kabupaten Lombok Tengah, Nusa Tenggara Barat**

---

### 6. Identifying the DJ

From the same message, the subject mentioned meeting a local DJ.

By correlating event-related information and local searches, the DJ was identified as:
- **Bong Leleh**,who is the only local Dj

---

### 7. Social Media Investigation

At this stage, the investigation pivoted to social media analysis.

Using a combination of manual searches and automated OSINT tooling, specifically :contentReference[oaicite:1]{index=1}, multiple accounts associated with the identified DJ were discovered across different platforms.

SpiderFoot helped aggregate and correlate usernames, revealing the DJ’s presence on platforms such as TikTok.

Further analysis of the TikTok content showed:
- Videos containing hashtags referencing a cave
- Content indicating guided visits and local tours

By correlating this information, the following location was identified:

**Finding:**
- Cave: **Gua Sumur**

---

### 8. Discovering Contact Information

Further investigation in Facebook revealed a profile connected to the same individual.

This profile promoted cave tours and included contact details.

**Finding:**
- Phone Number: **085333137345**

---

## Timeline Reconstruction

| Timeframe | Activity |
|----------|--------|
| Early October 2025 | Subject travels to Indonesia |
| 03–05 Oct 2025 | Attends MotoGP event |
| Same period | Visits cantina Mexicana |
| Evening | Photo taken at 19:55:30 |
| Later that night | Attends after-party |
| Same night | Meets DJ -Bong Leleh |
| Following day | Plans visit to Gua sumur |

---

## Conclusion

What started as a minimal dataset was enough to build a clear picture of the subject’s last known movements.

By combining image analysis, open-source data, and social media intelligence, it was possible to:
- Identify locations visited
- Link the subject to a specific individual
- Discover a likely next destination
- Obtain contact information tied to that individual

This type of investigation highlights how publicly available data can be leveraged to support real-world cases, especially when time and information are limited.

---

## Tools & Techniques Used

- Google Images (-Reverse image search)
- EXIF Metadata analysis
- Search Engine intelligence
- Social Media Intelligence 
- :contentReference[oaicite:3]{index=3}

---

## Skills Demonstrated

- OSINT investigation workflow
- Image geolocation
- Metadata analysis
- Social media pivoting
- Analytical thinking & correlation

  ##Screenshots
![O_1](O_1.png)
![O_2](O_2.png)

  
