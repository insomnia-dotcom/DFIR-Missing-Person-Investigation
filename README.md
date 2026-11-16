# Digital Forensics: Missing Person Investigation

## Case DF-2026-001 — Elena

### Project Overview

I created this project to gain hands-on experience with digital forensic investigations and better understand how digital evidence can help reconstruct events in a missing person case.

The investigation focuses on a simulated missing person named Elena. Using a synthetic disk image, I examined files, recovered deleted evidence, analyzed browser activity, and reconstructed a timeline of events leading up to her planned meeting with an unidentified individual.

This project is a training exercise. All evidence and individuals involved in the case are fictional.

### Tools Used

- Autopsy 4.23.1 — Filesystem examination, metadata analysis, deleted file recovery, file carving, and timeline reconstruction.
- FTK Imager — Forensic imaging tool setup.
- DB Browser for SQLite — Manual examination of browser history.
- Windows PowerShell — SHA-256 hash verification and browser timestamp conversion.

### Investigation Objectives

- Preserve the original evidence and verify the integrity of the working copy.
- Examine files and identify information relevant to Elena's disappearance.
- Recover deleted data and examine unallocated space.
- Analyze browser history, messages, and image metadata.
- Reconstruct a timeline of relevant events.
- Document findings and identify potential investigative leads.

### Investigation Process

#### 1. Evidence Preservation

I organized the case into separate folders for original evidence, working copies, exports, screenshots, notes, and reports.

Before examining the disk image, I calculated SHA-256 hashes to verify evidence integrity and used a working copy for analysis.

#### 2. Filesystem Examination

I imported the working disk image into Autopsy and examined the available files.

The evidence included:

- NOTES.TXT
- MESSAGES.TXT
- HISTORY.DB
- RECEIPT.TXT
- STATION.JPG
- A deleted text file identified as _RAFT.TXT

These files provided information about Elena's planned meeting, travel arrangements, and concerns about missing records.

#### 3. Deleted File Recovery

One of the most interesting parts of the investigation was recovering a deleted text file containing a message intended for Sofia.

The message mentioned a blue folder, missing records, and Elena's concerns about an individual identified as R.

I also recovered a matching file through file carving. Both exported files were 158 bytes in size.

Using PowerShell, I calculated their SHA-256 hashes and confirmed that they matched. This demonstrated that the deleted file and the carved file contained identical data.

#### 4. Browser History Analysis

I examined HISTORY.DB using DB Browser for SQLite and identified four relevant browser history entries.

The database contained searches related to the old station café, Route 12, the station's north entrance, and the weather.

I converted the browser timestamps into Central Standard Time using PowerShell and compared them with the messages and filesystem timestamps.

#### 5. Timeline Reconstruction

I used Autopsy's timeline feature and the contents of the recovered evidence to reconstruct the following events.

| Date and Time (CST) | Event |
|---|---|
| Nov 6, 2026 — 21:12 | Notes file creation/modification timestamp |
| Nov 7 — 16:42 | Sofia asks Elena about dinner |
| Nov 7 — 16:50 | Browser history records a search for the old station café |
| Nov 7 — 17:02 | Route 12 schedule accessed |
| Nov 7 — 17:08 | R changes the meeting location to the north entrance |
| Nov 7 — 17:11 | Elena states that she will take the bus |
| Nov 7 — 17:14 | Browser history records a search for the station's north entrance |
| Nov 7 — 17:19 | Sofia asks Elena to text when she gets home |
| Nov 7 — 17:26 | Deleted draft creation/modification timestamp |
| Nov 7 — 17:34 | Simulated Route 12 transit receipt |
| Nov 7 — 17:41 | Station image creation/modification timestamp |
| Nov 7 — 18:30 | Planned meeting time |

### Key Findings

The evidence suggests that Elena was preparing to meet an individual identified as R at the old station.

The messages indicate that the meeting location changed shortly before the planned meeting. Browser activity and the simulated transit receipt are consistent with preparations to travel using Route 12.

The recovered deleted draft provided additional investigative leads involving a blue folder and missing records. It also indicated that Elena had concerns about the explanation R provided for the meeting.

### Conclusion

Based on the evidence I examined, I was able to reconstruct several events leading up to Elena's planned meeting and identify information that could support further investigation.

However, the available evidence does not establish whether Elena arrived at the station, attended the meeting, or encountered criminal activity.

Further investigation would focus on identifying R, locating the blue folder, examining the missing records, and obtaining relevant surveillance footage.

### Limitations

- The evidence is synthetic and was created for training purposes.
- Browser history does not independently establish who performed each search.
- Filesystem timestamps do not necessarily establish when a real-world event occurred.
- The station image does not independently establish Elena's physical location.
- The identity of R and the time of the draft's deletion remain unknown.

### Skills Demonstrated

- Digital evidence handling
- SHA-256 integrity verification
- Filesystem analysis
- Deleted file recovery
- File carving
- SQLite database examination
- Browser timestamp conversion
- EXIF metadata analysis
- Forensic timeline reconstruction
- Investigative documentation and reporting

### What I Learned

This project helped me understand how different pieces of digital evidence can be connected to build a timeline.

Recovering the deleted draft and verifying it against the carved file was particularly valuable because it showed me the importance of validating recovered evidence rather than relying on a single tool or result.

I also learned how important it is to separate confirmed findings from assumptions when writing a forensic report.

This investigation is part of my ongoing development in digital forensics and cybersecurity.

---

**Examiner:** insomnia-dotcom

**Case ID:** DF-2026-001

**Status:** Investigation completed

**Project Type:** Digital Forensics Training Lab

