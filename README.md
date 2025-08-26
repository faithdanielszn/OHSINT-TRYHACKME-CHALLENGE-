# OHSINT-TRYHACKME-CHALLENGE-
A detailed walkthrough of the TryHackMe OSINT Lab Challenge, showcasing various OSINT tools and techniques for gathering publicly available information on a target. Includes commands and screenshots.
# My Understanding of OSINT

Open-Source Intelligence (OSINT) is the process of collecting publicly available data from sources like social media, websites, and documents to assess security risks. In cybersecurity, OSINT is crucial for uncovering vulnerabilities, tracking threats, and performing reconnaissance without engaging in illegal activities.

## Why I Chose OSINT

As an entry-level professional, OSINT was a natural fit because it’s practical, beginner-friendly, and has real-world applications. It allows me to build foundational cybersecurity skills using freely available resources—perfect for someone starting out in the field.

## Why the TryHackMe OhSINT Lab?

The OhSINT room on TryHackMe is an excellent starting point because:
- It’s designed for beginners, with a gradual increase in difficulty.
- It offers hands-on experience with real-world scenarios, like extracting metadata from an image.
- It helps develop practical OSINT skills using accessible tools, perfect for entry-level learners.
### This is a link to the room
[TryHackMe OhSINT Room](https://tryhackme.com/room/ohsint)

## Taking on the Challenge

### Understanding the Challenge

Before diving into the challenge, I clicked the bright blue button at the top of Task 1 labeled ‘Download Task Files’, to obtain the task file, which I downloaded and saved to my system.

![task file](ohsint.jpg)


### OSINT Investigation: Revealing Hidden Insights

Initially, the image appears unremarkable, offering no apparent hints or concealed messages. However, in OSINT, we dive deeper! The true insights often lie beneath the surface, waiting to be uncovered. My first step? Examine the metadata to reveal the concealed details that can guide me to the next lead!

#### Understanding Metadata

Metadata is the unseen data embedded within files, offering context and additional information. It can include creation dates, software used, device details, and even geographical data. This hidden information can be invaluable for OSINT investigators.

#### Tools for Metadata Extraction

We use various tools to extract metadata, each with its unique capabilities:

- **ExifTool:** A robust command-line utility for reading and writing metadata in multiple file formats, especially useful for images and videos.
  - Example: `exiftool image.jpg`
- **PhotoDNA:** A forensic tool for analyzing images and videos to extract detailed metadata, including any modifications.
  - Example: Upload the file to the PhotoDNA website for analysis.
- **Metadata2Go:** An online tool for uploading files and viewing their metadata without installing software.
  - Example: Visit [Metadata2Go](https://metadata2go.com/) and upload your file.
- **Geosetter:** A tool for geotagging images, also useful for viewing and editing existing geotags.
  - Example: Open the image in Geosetter to view or edit geotag information.

#### Analyzing Extracted Metadata

After extracting metadata, we analyze it for useful information. Key metadata to look for includes:

- **Creation Date and Time:** Helps establish a timeline and correlate the image with other events.
- **Camera Model and Serial Number:** Can identify the device used, potentially leading to the photographer.
- **GPS Coordinates:** If geotagged, these can pinpoint the photo's location, providing context.
- **Software Used:** Insights into the creator's tools and potential digital footprint.
- **Author and Copyright Information:** May directly identify the creator.

#### Approach I Took

I ran the obtained image on ExifTool, which extracted metadata, and I analyzed the information and gathered two key pieces of information:

- **GPS Coordinates:** 54 deg 17' 41.27" N, 2 deg 15' 1.33" W
- **Copyright Information:** OWoodflint.
 
![exiftool output](1snap.png)

A quick Google search on the copyright information was my next step to uncover more clues.

I quickly searched the copyright name, which I presumed to be the author of the image, online precisely on google.com to see if it was linked to any websites. I discovered it was associated with three platforms: GitHub, X (formerly Twitter), and a WordPress blog.

#### Task 1: Discovering the User’s Avatar

To complete the first task, which was discovering what the user's avatar was, I visited the user's X (formerly Twitter) profile and found that their profile picture was a cat.

#### Task 2: Locating the User’s Location

To uncover the user’s location, the second task, I thoroughly examined their GitHub profile. In the README file, I found a clear indication that the user is based in London. This information, directly provided in the README, answers the second question and gives us a geographical context for the user, which can be crucial for further OSINT investigations. Knowing the user's location can help in understanding their digital footprint, potential interests, and online activities, especially when combined with other gathered data.

#### Task 3: Gathering Information on the SSID

While checking his X (formerly Twitter) account, I found a posted BSSID: B4:5D:50:AA:86:41. A BSSID is a unique identifier for a wireless access point, like a digital fingerprint for networks. To uncover the SSID, we use WiGLE.net — a global database that maps Wi-Fi networks by collecting BSSIDs, SSIDs, and approximate locations. Access requires a registered account, and new accounts are limited to five detailed queries per day.

Steps:
1. Log in to WiGLE.net.
2. Enter the BSSID into the search field and apply the filter.
3. Zoom out to see the world map, then navigate to London.
4. A red ring marks the access point’s location.
5. Zoom in gradually until street level is visible — the SSID UnileverWiFi appears, revealing the answer.

#### Task 4: Finding User’s Email Address

During the investigation, I examined the target’s GitHub profile and explored the available repositories. Inside one of the repositories, I reviewed the README file and identified a personal email address listed there: OWoodflint@gmail.com. This finding highlights how sensitive information can often be unintentionally exposed through publicly accessible code repositories. GitHub is a common place for OSINT analysts to discover email addresses, usernames, or other identifiers because developers sometimes embed them in documentation, commit messages, or project files.

#### Task 5: Answering the 5th Task

The email address information was found on GitHub.

#### Task 6: Holiday Destination

To answer the sixth question, I investigated the target’s WordPress blog. In one of the posts, he mentioned being on holiday in New York, which directly reveals his current travel destination. This demonstrates how personal blogs can unintentionally leak location data or travel plans, making them valuable sources in OSINT investigations.

#### Task 7: Uncover Password

I began by checking the target’s X (formerly Twitter) account and GitHub profile, but found no relevant clues. As a next step, I inspected the source code of the WordPress site. After carefully reviewing the code several times, I noticed an unusual string hidden in plain sight. At first, it was easy to overlook, but on closer inspection, it became clear that this string was the password: `pennYDr0pper.!`.

## Mission Complete

And that’s a wrap on the OhSINT challenge! It was a fun little treasure hunt across the internet—digging through tweets, GitHub repos, WordPress code, and even Wi-Fi databases. Every clue felt like peeling back another layer, and it definitely sharpened my reconnaissance muscles. I’m excited to keep pushing further, tackling tougher challenges, and leveling up my OSINT toolkit. This was just one stop on the journey, and there are plenty more puzzles out there waiting to be cracked. On to the next hunt—because every breadcrumb leads to a bigger skillset. 🚀🔎
