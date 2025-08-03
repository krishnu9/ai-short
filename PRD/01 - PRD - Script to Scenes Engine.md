---
id: FCM-001
title: "Feature: Script to Scenes Engine"
status: To Do
epic: 
owner: "@krishnu"
created: 2025-07-30
tags:
  - feature
  - mvp
  - core-engine
---

# PRD: Script to Scenes Engine

|            |                           |           |
| ---------- | ------------------------- | --------- |
| **Status** | **Epic**                  | **Owner** |
| 🧊 To Do   | [[Core Video Generation]] | @krishnu  |

## 1. Summary

This document outlines the requirements for the **Script to Scenes Engine**, the core component of the Faceless Content Machine. This feature is responsible for the automated conversion of a user's text script into a sequence of distinct visual scenes. It functions by programmatically parsing the script, extracting relevant keywords from key phrases or keywords, and using those keywords to query and retrieve a suitable stock video or image from integrated, rights-free libraries (e.g., Pexels, Unsplash).

## 2. Problem & User Stories

### Problem Statement

Content creators, particularly those managing "faceless" accounts, spend a significant amount of time manually searching for, downloading, and editing stock media to match their scripts. This process is tedious, time-consuming, and a major bottleneck in content production. This feature aims to eliminate that friction entirely.

### User Stories

> As a faceless content creator, I want to simply paste my script and have the system automatically find relevant background visuals, so that I can save hours of manually searching for stock media.

> As a content creator, I want the system to create a new visual for each key phrase or keyword, so that my final video has a dynamic pace that keeps viewers engaged.

### Stories in this Epic

| ID      | Title                             | Status   | Owner    | Link                                     |
| ------- | --------------------------------- | -------- | -------- | ---------------------------------------- |
| FCM-002 | Automatic Script-to-Scene Parsing | 🧊 To Do | @krishnu | [[02 - FCM-002 - US - Script Parsing]]        |
| FCM-003 | AI-Powered Keyword Extraction     | 🧊 To Do | @krishnu | [[FCM-003 - US - Keyword Extraction]]    |
| FCM-004 | Global Visual Refresh ("Re-Roll") | 🧊 To Do | @krishnu | [[FCM-004 - US - Global Visual Refresh]] |

## 3. Acceptance Criteria

These are the testable conditions that must be met for this feature to be considered complete and ready for release.

- [ ] **Scene Parsing:** GIVEN a user pastes a script with content, WHEN they initiate the video creation process, THEN the system must parse the text and treat each identified key phrase or keyword as a separate scene.
    
- [ ] **Keyword Extraction:** GIVEN a key phrase or keyword, WHEN the system processes it, THEN it must automatically extract the most relevant keywords for searching.
    
- [ ] **API Integration & Fetching:** GIVEN keywords are extracted, WHEN the system queries the integrated stock media API (e.g., Pexels), THEN it must successfully fetch the single top video or image result.
    
- [ ] **Visuals Re-Roll:** GIVEN a user is viewing the video preview, WHEN they are unsatisfied with the generated visuals, THEN a "Try new visuals" button must be available that re-runs the stock media search to fetch a new set of clips for the same script.
    

## 4. Scope

### In Scope

- Automatic parsing of the input script based on key phrases or keywords.
    
- Automatic keyword extraction from each key phrase or keyword.
    
- API integration with Pexels and/or Unsplash.
    
- Automatically selecting only the **top** search result per scene to ensure simplicity.
    
- A single "re-roll" option that regenerates **all** visuals for the script at once.
    

### Out of Scope (for MVP)

- **User-Uploaded Media:** Users cannot upload their own videos or images.
    
- **Manual Keyword Editing:** Users cannot view or change the keywords extracted by the AI.
    
- **Scene-Level Choice:** Users will not be presented with multiple visual options for a single scene.
    
- **Media Library / Timeline Editor:** There will be no interface for managing media or arranging scenes on a timeline.
    

## 5. Dependencies & Technical Notes

- **Core Dependency:** This feature is a foundational dependency for the entire video generation workflow. No other part of the video creation process can begin until the script has been converted into a sequence of scenes with associated media.
    
- **API Keys:** Requires secure storage and management of API keys for Pexels and/or Unsplash.
    
- **Performance:** The keyword extraction and API query process must be optimized to ensure the video preview is generated in a timely manner.