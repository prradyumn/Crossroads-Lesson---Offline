# Crossroads · Learn with Swiftee

Grade 8 geometry game: linear pairs and vertically opposite angles. **English and Hindi (हिंदी)** in one game.
A static website: no build step, no server code, no internet needed once loaded.

## Pages

| URL | File | What it is |
|---|---|---|
| `/` | `index.html` | Start screen: choose **Lesson** or **Practice**, and the language |
| `/lesson` | `lesson.html` | The 32-screen lesson with Swiftee (voice, sound effects, animations) |
| `/practice` | `practice.html` | The four practice rounds |

Add `?lang=hi` or `?lang=en` to any page to open it in that language. The English | हिंदी switch
(top right of every screen) changes the language; the choice is remembered and shared by all pages,
and the learner stays on the same lesson screen (in practice, the current junction starts again).

## Folder structure

```
index.html              start screen
lesson.html             lesson (English + Hindi)
practice.html           practice rounds (English + Hindi)
assets/                 start-screen artwork, fonts, site icon (file names carry a content hash)
audio/
  en/                   Swiftee's English voice (113 clips)
  hi/                   Swiftee's Hindi voice (259 clips: every lesson and practice line)
  voice-manifest.js             English lesson: on-screen line -> clip
  voice-manifest-hi.js          Hindi lesson:   on-screen line -> clip
  practice-voice-manifest-hi.js Hindi practice: on-screen line -> clip
licences/               font licences (Nunito, Baloo 2, Noto Sans Devanagari: SIL OFL)
vercel.json             clean URLs, caching for audio and assets
.vercelignore           keeps the review files below off the website

translation/            NOT deployed: English <-> Hindi review sheets (every voice line, every screen text)
_original-english/      NOT deployed: the original English-only files, unchanged
```

## Deploy to Vercel

Framework preset **Other**, no build command, output directory = the project root (the defaults).

- **Vercel CLI:** in this folder run `npx vercel` (preview) or `npx vercel --prod`.
- **Git:** push this folder to a GitHub repository and import it at vercel.com/new.
- **Drag and drop:** upload the folder at vercel.com/new.

## Run offline

Double-click `index.html` (Chrome or Edge works best). Keep the whole folder together: the pages need
`audio/` and `assets/` next to them. Best on a tablet held sideways; tap Swiftee to hear the last message again.
