# Digital Forensics – Missing Person Investigation

## Project Overview

This project is a simulated missing person investigation that I completed as part of my hands-on digital forensics training.

The goal was to examine a forensic disk image associated with a fictional missing person named Elena, recover relevant digital evidence, and reconstruct a timeline of activity leading up to her planned meeting on November 7, 2026.

I wanted to practice the investigative process from beginning to end, including evidence preservation, forensic examination, deleted file recovery, timeline analysis, and report writing.

## Case Information

| Field | Details |
|---|---|
| Case ID | DF-2026-001 |
| Case Type | Simulated Missing Person Investigation |
| Subject | Elena |
| Evidence ID | E001 |
| Evidence Type | Forensic Disk Image |
| Examiner | insomnia-dotcom |
| Examination Date | November 15, 2026 |

## Tools Used

- **Autopsy 4.23.1** – Filesystem examination, deleted file recovery, file carving, metadata analysis, timeline reconstruction, and reporting.
- **DB Browser for SQLite** – Examination of browser history records.
- **Windows PowerShell** – SHA-256 hash verification, file comparison, and timestamp conversion.
- **FTK Imager** – Forensic workstation preparation.
- **ExifTool** – Metadata examination.

## Investigation Process

### 1. Evidence Preservation and Verification

Before examining the evidence, I calculated the SHA-256 hash of the original forensic image and compared it with the supplied reference hash.

I then created a working copy and independently verified its hash against the original evidence. Both verification checks returned True.

The original evidence was stored separately to preserve its integrity throughout the investigation.

### 2. Filesystem Examination

I imported the working copy into Autopsy and examined the filesystem for potentially relevant evidence.

The examination identified several files of interest:

- NOTES.TXT
- MESSAGES.TXT
- HISTORY.DB
- RECEIPT.TXT
- STATION.JPG
- _RAFT.TXT (deleted file)

These files provided information about Elena's planned meeting, communications, possible travel arrangements, and concerns about missing records.

### 3. Browser History Analysis

I examined HISTORY.DB using DB Browser for SQLite and reviewed the recorded browsing activity.

I also used PowerShell to convert browser timestamps into Central Standard Time so that the browsing activity could be compared with other evidence.

The browser history included activity related to transportation and the station's north entrance.

### 4. Deleted File Recovery and File Carving

One of the most important findings was a deleted text file identified as _RAFT.TXT.

The recovered message indicated that Elena was concerned about an upcoming meeting and instructed Sofia to check a blue folder in her desk if she did not call that night.

A matching text file, f0000000.txt, was also recovered through file carving.

Both recovered files were exported and independently hashed using SHA-256.

**Results:**

- Deleted file size: 158 bytes
- Carved file size: 158 bytes
- SHA-256 comparison: Match

The matching hashes confirmed that both exported files contained identical data.

### 5. Metadata Examination

I examined the available metadata associated with STATION.JPG and reviewed its filesystem timestamps.

The image depicted the station's north entrance. However, the available metadata did not independently establish when the photograph was taken or Elena's physical location.

### 6. Timeline Reconstruction

I used Autopsy's timeline feature and converted browser history timestamps to reconstruct relevant activity.

| Date | Time (CST) | Event |
|---|---|---|
| Nov. 6, 2026 | 21:12 | NOTES.TXT creation and modification timestamps |
| Nov. 7, 2026 | 17:08 | Message changing the meeting location |
| Nov. 7, 2026 | 17:14 | Browser search related to the station's north entrance |
| Nov. 7, 2026 | 17:18 | HISTORY.DB creation and modification timestamps |
| Nov. 7, 2026 | 17:22 | MESSAGES.TXT creation and modification timestamps |
| Nov. 7, 2026 | 17:26 | Deleted draft creation and modification timestamps |
| Nov. 7, 2026 | 17:35 | RECEIPT.TXT creation and modification timestamps |
| Nov. 7, 2026 | 17:41 | STATION.JPG creation and modification timestamps |
| Nov. 7, 2026 | 18:30 | Scheduled meeting with R |

Filesystem timestamps represent recorded file activity and do not necessarily establish when the underlying real-world events occurred.

## Key Findings

- Elena planned to meet an individual identified as R at the old station.
- The meeting location was changed from the café entrance to the north entrance.
- Browser history and other recovered evidence were consistent with preparations to travel using Route 12.
- A deleted draft revealed Elena's concerns about the meeting and referenced missing records and a blue folder.
- The deleted draft and carved file were verified as identical using SHA-256.
- The available evidence did not establish whether Elena arrived at the station or attended the meeting.

## Investigation Documentation

The repository includes documentation of the examination process and supporting findings.

- [Investigation Screenshots](screenshots/)
- [Forensic Reports](reports/)
- [Investigation Documentation](documentation/)

These folders contain screenshots, investigation notes, evidence verification records, and forensic reports.

## Skills Demonstrated

- Digital evidence preservation
- SHA-256 integrity verification
- Filesystem analysis
- Deleted file recovery
- File carving
- SQLite database examination
- Browser history analysis
- Metadata examination
- Timestamp conversion
- Forensic timeline reconstruction
- Investigative documentation
- Forensic report writing

## Conclusion

This investigation gave me practical experience working through a digital forensics case from evidence verification to final reporting.

One of the most valuable parts of the project was recovering a deleted file through two different methods and using SHA-256 hashes to verify that the recovered contents were identical.

The project also reinforced the importance of separating verified findings from assumptions. While the evidence supported the interpretation that Elena was preparing to attend a meeting, it was not sufficient to determine what happened to her afterward.

## Disclaimer

This project is a fictional digital forensics training exercise. All individuals, events, and evidence are synthetic and intended for educational purposes only.
