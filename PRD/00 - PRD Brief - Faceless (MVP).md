# The Faceless Content Machine (MVP)

### **Value Proposition: From Idea to Viral in Minutes**

FCM is the all-in-one creation suite that empowers anyone to produce engaging short-form videos without needing complex editing skills or expensive equipment. We turn your ideas, text, or even just a topic into engaging, trend-aware content for TikTok, Reels, and Shorts.

## Epics

- [[01 - PRD - Script to Scenes Engine]]


## Feature 1: Script to Scenes Engine

- **Feature Name:** Script to Scenes Engine
    
- **Summary:** This is the core engine of the application. It automatically converts key phrases or keywords from a user's script into a distinct visual scene by extracting keywords and fetching a relevant, rights-free stock video or image from an integrated library like Pexels or Unsplash.
    
- **User Stories:**
    
    - "As a faceless content creator, I want to simply paste my script and have the system automatically find relevant background visuals, so that I can save hours of manually searching for stock media."
        
    - "As a content creator, I want the system to create a new visual for each key phrase or keyword, so that my final video has a dynamic pace that keeps viewers engaged."
        
- **Acceptance Criteria:**
    
    - GIVEN a user pastes a script with content, WHEN they initiate the video creation process, THEN the system must parse the text and treat each identified key phrase or keyword as a separate scene.
        
    - GIVEN a key phrase or keyword, WHEN the system processes it, THEN it must automatically extract the most relevant keywords.
        
    - GIVEN keywords are extracted, WHEN the system queries the integrated stock media API (e.g., Pexels), THEN it must successfully fetch the top video/image result.
        
    - GIVEN a user is viewing the video preview, WHEN they are unsatisfied with the generated visuals, THEN a "Try new visuals" button must be available that re-runs the stock media search to fetch a new set of clips for the same script.
        
- **Scope (In and Out):**
    
    - **In Scope:** Automatic keyword extraction; API integration with Pexels and/or Unsplash; Automatically selecting only the top search result per scene; A "re-roll" option for all visuals at once.
        
    - **Out of Scope:** User-uploaded media; Manual keyword editing; Allowing users to choose from multiple visual options for a single scene; A media library or timeline editor.
        
- **Dependencies:** This feature is a core dependency for the entire video generation process.
    

## Feature 2: High-Quality AI Voiceover

- **Feature Name:** High-Quality AI Voiceover
    
- **Summary:** This feature generates a clear, human-like voiceover for the user's script using an integrated Text-to-Speech (TTS) API. It provides a small, curated selection of voices and, critically, generates the word-level timestamps required for the dynamic captions feature.
    
- **User Stories:**
    
    - "As a content creator, I want to choose from a small selection of high-quality AI voices, so that I can select a tone that perfectly matches the message of my video."
        
    - "As a content creator, I want the voiceover to be generated automatically from my script, so I don't have to record or edit audio myself."
        
- **Acceptance Criteria:**
    
    - GIVEN a user is in the "Choose Style" step, WHEN they view the voice options, THEN a dropdown menu with 3-5 curated, distinct voices must be presented (e.g., 2 male, 2 female, 1 narrative).
        
    - GIVEN a user selects a voice, WHEN the video is generated, THEN the final audio must use the selected voice.
        
    - The system must successfully integrate with a high-quality TTS API (e.g., ElevenLabs, OpenAI TTS).
        
    - The data returned from the TTS API must include precise word-level timestamps for use by the captioning engine.
        
- **Scope (In and Out):**
    
    - **In Scope:** Integration with a single TTS provider; Offering 3-5 pre-selected, high-quality voices.
        
    - **Out of Scope:** AI voice cloning; Allowing users to upload their own audio files; Controls for adjusting the speed, pitch, or emotion of the AI voice.
        

## Feature 3: Dynamic "Live" Captions

- **Feature Name:** Dynamic "Live" Captions
    
- **Summary:** This is the killer feature. It creates highly engaging, animated captions that are synchronized word-for-word with the AI voiceover. It offers several pre-designed, trendy styles and can automatically add relevant emojis to the text to increase visual appeal.
    
- **User Stories:**
    
    - "As a content creator, I want my captions to animate on screen word-by-word as they are spoken, so I can maximize viewer retention on platforms like TikTok and Reels."
        
    - "As a content creator, I want to choose from a few popular, proven caption styles with a single click, so I don't have to waste time designing them myself."
        
    - "As a content creator, I want relevant emojis to appear automatically in my captions, so I can add visual flair and emotional context without manual effort."
        
- **Acceptance Criteria:**
    
    - GIVEN a voiceover with word-level timestamps has been generated, WHEN the video is rendered, THEN each word in the caption must appear on screen precisely as it is spoken in the audio.
        
    - The UI must present 3-4 clickable, visual presets for caption styles.
        
    - One of the presets must be a "Hormozi" style, which includes a bold white font where key words are highlighted in green or yellow and have a subtle pop animation.
        
    - The system must detect a pre-defined set of keywords (e.g., "money," "idea," "success") and automatically place a corresponding emoji (e.g., 💰, 💡, ✅) next to them in the caption text.
        
- **Scope (In and Out):**
    
    - **In Scope:** Word-by-word animation; 3-4 hard-coded style presets; Automatic emoji placement for a limited, pre-defined dictionary of words.
        
    - **Out of Scope:** A full caption editor (font, color, size, position); Custom highlight colors; Custom animation styles; Uploading external subtitle files (e.g., .srt).
        
- **Dependencies:** This feature is critically dependent on **Feature 2: High-Quality AI Voiceover** to provide the necessary word-level timestamps.
    

## Feature 4: Background Music Selection

- **Feature Name:** Background Music
    
- **Summary:** Allows the user to select a single royalty-free music track from a small, curated library. The selected track will be automatically mixed into the final video at an appropriate, low volume to complement the voiceover.
    
- **User Stories:**
    
    - "As a content creator, I want to easily add background music to my video, so that it feels more professional and emotionally resonant."
        
- **Acceptance Criteria:**
    
    - GIVEN a user is on the style selection screen, WHEN they interact with the music selection element, THEN a dropdown list of 10-15 tracks must be available.
        
    - The music tracks in the list should be categorized by mood (e.g., "Uplifting," "Epic," "Calm").
        
    - GIVEN a user selects a track, WHEN the final video is generated, THEN the selected music must be mixed into the final audio track at a volume that is clearly audible but does not overpower the voiceover.
        
- **Scope (In and Out):**
    
    - **In Scope:** A pre-approved, built-in library of 10-15 royalty-free tracks; Selection via a simple dropdown menu.
        
    - **Out of Scope:** Allowing users to upload their own music; Searching the music library; Controls for adjusting music volume.
        

## Feature 5: One-Click Video Generation & Export

- **Feature Name:** One-Click Video Generation & Export
    
- **Summary:** This feature encompasses the final user workflow step: a simple, two-stage process where the user initiates the video creation with a single "Generate" button, sees a preview, and can then download the final, fully rendered MP4 file.
    
- **User Stories:**
    
    - "As a content creator, I want to click one button to generate my entire video, so the process is as fast and simple as possible."
        
    - "As a content creator, I want to see a preview of my video before downloading, so I can confirm I'm happy with the result or decide to try new visuals."
        
    - "As a content creator, I want to download my final video as a high-resolution MP4 in the correct aspect ratio, so it's ready to be uploaded immediately to social media."
        
- **Acceptance Criteria:**
    
    - GIVEN the user has made all their style selections, WHEN they click the "Create My Video" button, THEN the backend must begin processing all components (visuals, voice, captions, music) into a single video file.
        
    - After processing is complete, a preview of the final video must be displayed to the user within the web interface.
        
    - A "Download" button must be present on the preview screen.
        
    - WHEN the user clicks "Download", THEN they must receive the final video as an .mp4 file.
        
    - The final exported video file must be rendered in a 9:16 aspect ratio.
        
- **Scope (In and Out):**
    
    - **In Scope:** Generation of a 9:16 MP4 file; An in-app preview screen; A download button for the final file.
        
    - **Out of Scope:** Exporting in different aspect ratios or file formats; A progress bar or estimated time for rendering; Direct sharing or integration with any social media platform.

