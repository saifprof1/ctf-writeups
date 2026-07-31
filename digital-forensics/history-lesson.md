# History Lesson

## Table of contents

- [Overview](#overview)
- [Challenge Description](#challenge-description)
- [Investigation Process](#investigation-process)
- [Solution](#solution)
- [Lessons Learned](#lessons-learned)
- [Tools Used](#tools-used)

---
## Overview

**Category:** Digital Forensics

This challenge focuses on investigating a recovered Linux home directory to uncover a hidden secret. Instead of storing sensitive information directly, the user relied on encoding and compression while unintentionally leaving behind valuable forensic artifacts. The objective was to analyze those artifacts, reconstruct the user's actions, and recover the hidden flag.

## Challenge Description
The challenge provided a recovered home directory from a DevOps operator's Linux system. It contained several useful files and directories, such as the shell history, Python history, cache files, SSH configuration, and project-related files.

Although the secret was not stored directly in plain text, the user's daily activities left behind enough forensic evidence. By carefully examining these artifacts, it was possible to trace the user's actions and eventually recover the hidden flag.
