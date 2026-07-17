MIA — AI VOICE CALL  (Gemini + ElevenLabs edition)
==================================================

A one-button voice call with Mia, an AI with her own personality,
shown as an animated robot face with live expressions and lip sync.

Brain: Google Gemini Flash (free tier — fast, smart)
Voice: ElevenLabs Flash v2.5 (free tier — very natural, ~75ms latency)


SETUP (5 minutes, one time)
---------------------------
You need two free API keys. No credit card for either.

1. GEMINI KEY
   - Go to  https://aistudio.google.com/apikey
   - Sign in with a Google account, click "Create API key", copy it.

2. ELEVENLABS KEY
   - Go to  https://elevenlabs.io  and create a free account.
   - Click your profile (bottom left) -> "API Keys" -> create one, copy it.
   - Free tier gives 10,000 credits per month (roughly 10-20 min of
     Mia talking).

3. Open index.html in Chrome or Edge (double-click it, or open your
   Vercel URL). A setup screen appears — paste both keys and save.
   Keys are stored only in YOUR browser (localStorage). You can change
   them any time with the gear icon (top right).


HOW TO USE
----------
1. Tap the green call button.
2. Allow microphone access when asked.
3. Talk. Mia answers out loud. Tap the red button to hang up.
No typing anywhere — it's voice only.


REQUIREMENTS
------------
- Chrome or Edge (desktop or Android). Firefox and desktop Safari
  don't support the speech recognition this app uses.
- Microphone + headphones recommended (so Mia doesn't hear herself).
- Internet connection.


IMPORTANT IF YOU DEPLOY PUBLICLY (e.g. Vercel)
----------------------------------------------
Keys are entered by each visitor in their own browser, so YOUR keys
are never inside the file — safe to deploy as-is. Do NOT hardcode
your keys into the HTML on a public site: anyone could read and
abuse them.


TROUBLESHOOTING
---------------
- "Gemini key rejected": key is wrong, or you pasted it with spaces.
- "ElevenLabs key rejected": same — recreate the key and re-paste.
- Voice suddenly sounds robotic: your monthly ElevenLabs credits ran
  out; the app fell back to your device's built-in voice. Resets
  monthly, or upgrade at elevenlabs.io.
- Slow or failing answers: Gemini free tier allows ~10 requests per
  minute; very fast back-and-forth can hit that limit. The app
  automatically retries with another Flash model.
- Nothing happens when I talk: check mic permission (padlock icon
  next to the address bar).
- She keeps hearing herself: use headphones.


CHANGING THE VOICE (optional)
-----------------------------
The app automatically picks a voice from YOUR ElevenLabs account
(free accounts can't use shared library voices via the API, so it
uses the default voices that come with your account). To force a
specific voice, open the browser console (F12) on the app page:
  localStorage.setItem('mia_el_voice', 'PASTE_VOICE_ID_HERE')
then reload. Voice IDs are in the ElevenLabs "My Voices" page.
If that voice isn't allowed on your plan, the app detects it and
switches to one that is.

SWEDISH MODE / SVENSKA
----------------------
Open the gear icon (top right) and set Language / Språk to Svenska.
Mia then speaks and understands Swedish, and the app text follows.

ABOUT THE MIC CHIME ON ANDROID
------------------------------
The short beep during calls is Android's own speech-recognition
sound — web pages cannot silence it. The app now keeps the mic
session open for your whole turn, so it chimes at most once per
turn instead of repeatedly. To remove it completely, mute system/
touch sounds in your phone's Android sound settings.

CAMERA EYES (optional)
----------------------
During a call, a camera button appears next to the call button.
Tap it and allow camera access: a small preview shows what Mia can
see, and every question you ask now includes a live snapshot — so
you can ask "what am I holding?" or "what do you see?". The small
arrow on the preview flips between back and front camera. Tap the
camera button again to turn her eyes off; they also turn off
automatically when the call ends. Nothing is recorded — one photo
is sent to Gemini per question, only while the camera is on.

ATTACHMENTS & GENERATED FILES
-----------------------------
During a call, a paperclip button appears to the right of the call
button.

ATTACH: Tap it and pick an image, PDF or text file (.txt, .md,
.csv, .json, .html — max 10 MB). A small card shows the attachment;
now just ask Mia about it out loud ("what does this document say?",
"summarize this", "what's in this picture?"). The attachment stays
active for the whole call, or until you tap the ✕ on its card.

GENERATE: Ask Mia to create something — "write me a packing list
as a file", "make me a picture of a red cabin by a lake". Documents
appear as a card with the filename and a green ⬇ download button.
Images appear with a small thumbnail and the same ⬇ button. After
you download, the card disappears and the paperclip returns.

Notes: image generation uses Gemini's image model (small free
daily quota) and automatically falls back to pollinations.ai
(free) if that quota runs out. Generated documents are .txt, .md,
.html or .csv — Word/PDF export isn't possible from a single HTML
file without heavy libraries.

TEXT CHAT
---------
Tap the 💬 button (top left, only visible when not in a call) to
open a text chat with Mia. It has its own attach button (images,
PDF, text files) and the same file/image generation — generated
things appear right in the chat with a thumbnail/filename and ⬇
download button. Tap 💬 again to close.

MEMORY & CONVERSATION LOG
-------------------------
Mia now remembers your previous conversations — both voice calls
and text chats share one memory, stored only in your browser. The
gear menu shows the full conversation log, including everything
Mia has generated, with working download links (files/images are
kept in your browser's storage). "Clear log & memory" wipes it all.
Note: memory is per browser/device, and clearing the browser's
site data also clears Mia's memory.
