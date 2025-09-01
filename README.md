<p align="center">
<img src="/misc/readme/Spotify_logo.png" title="Spotify Logo" width="150" />
</p>

<h2 align="center">
PODinsights – Spotify Transcripts <br /> A product by Hovershelf
</h2>

<p align="center">
<img src="/misc/readme/4.png" title="Demo Screenshot" width="1000" />
</p>

---

## ✨ Key features 
- **Transcripts:** Speech recognition to convert speech into text with timestamps.
- **Search:** Search within the transcript and jump to any part of the conversation.
- **Chapters:** Auto-generated chapters based on identified topics.
- **Subtitles:** Accessibility for people with hearing difficulties.  

---

## 📖 About the project
PODinsights was inspired by two earlier community-driven projects:  

- **Spotify Topics:** Built during Spotify’s 2020 hackathon – a [tool](https://github.com/johan-akerman/SpotifyTopics) that allows fast-forwarding to timestamps where topics are discussed.  
- **Spotify Subtitles:** In 2022, a [feature request](https://community.spotify.com/t5/Live-Ideas/Podcasts-Subtitles-for-Podcasts/idi-p/5200537) for podcast subtitles received 4500+ upvotes on Spotify’s community forum, which further motivated experimentation in this space.  

In 2023, during the rise of ChatGPT, I combined these inspirations into one project and enhanced it using OpenAI APIs to create transcripts, subtitles, and auto-generated chapters for podcasts.  

👉 Spotify has since released their own version of podcast transcripts and chapters – [read here](https://pr-newsroom-wp.appspot.com/2023-09-28/international-podcast-day-transcripts-chapters-show-pages-global/).  


---

## ⚙️ Technologies used

| Technology | Use case |
| :--- | :--- |
| React | Frontend framework |
| Tailwind | CSS styling library |
| Python | Backend transcription logic |
| Flask | Connects Python backend with React frontend |
| Spotify API | Podcast episode metadata |
| Google Speech Recognition API | Speech-to-text transcription |
| OpenAI GPT-3.5 API | Segment transcript into topic-based chapters |

The frontend requests podcast data via the Spotify API. The backend downloads the episode audio (as mp3) to process timestamps for each sentence, using silence detection (< 14 dB for > 500 ms). Sentences are chunked into smaller files, transcribed via Google’s API, then segmented into chapters using OpenAI’s GPT API.  

---

## 🚫 Limitations
Spotify’s API **only provides 30-second previews**, not full podcast episodes.  
Therefore, this is a **proof of concept** only.  

---

## 🚀 Getting started

### Step 1: Sign up for API keys
- [Spotify Developer](https://developer.spotify.com/)  
- [OpenAI](https://platform.openai.com/)  

### Step 2: Add API keys to `.env`
Create a `.env` file in the root directory:  

```bash
REACT_APP_SPOTIFY_CLIENT_ID=YOUR_SPOTIFY_CLIENT_ID
REACT_APP_OPEN_AI_KEY=YOUR_OPEN_AI_KEY
