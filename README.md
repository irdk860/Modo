# Modo

A free web app for learning music at your own pace: piano, guitar, bass, woodwind (flute, clarinet, sax), brass (trumpet, trombone) and percussion.

**Beta 0.1.** Built to test whether each feature in the Modo plan works in a browser.

## What's in the beta
- Lessons for six instruments, in any order (basics and technique)
- Note trainer with instrument-specific controls: keyboard, fretboard with tab, note buttons with staff and fingering, drum pads
- Chord trainer for piano and guitar: chord diagrams, microphone chord recognition, chord-change drills, major/minor ear training
- Drum-hit recognition (kick, snare, hi-hat, tom, cymbal) for recordings and a live microphone, plus a real-drum mode in the rhythm trainer
- Camera posture and hand-shape check (MediaPipe pose and hand landmarks, runs on the device; nothing is uploaded)
- Streaks, weekly goal, badges and a weekly challenge
- Groups: friends groups with a weekly board, and classes where teachers set practice and see each student's progress
- Rhythm trainer that measures timing in milliseconds, with latency calibration
- Song practice with tempo control and section looping: 8 copyright-free melodies, 2 bass lines and 7 drum grooves
- Room sound (dry, room, hall) and improved brass and wind tone
- Live tuner and recording analysis (pitch detection)
- Personalised feedback and recommendations
- Market research survey (15 questions: audience, needs, existing apps, features, desirability, pricing, improvements) with live results
- Beta report showing which features are proven, plus a tester questionnaire

## How it runs
- **Website:** a single `index.html`, served by GitHub Pages. No build step.
- **Accounts and data:** Supabase (project `modo`, London region). Practice history, lessons and settings sync per user; groups, classes and assignments live in `groups`, `group_members`, `assignments` and `profiles`; row-level security keeps each user's data private. Questionnaire responses go to the `tester_feedback` table.
- Without signing in, progress is saved in the visitor's browser.

## Reading tester feedback
Supabase dashboard → Table Editor → `tester_feedback`, or run `select * from tester_feedback_summary;` in the SQL editor.

## Reading survey results
- In the app: Survey tab → See results so far (counts only; written comments are never shown publicly). Copy as CSV for charts.
- Full answers, including comments: Supabase → Table Editor → `market_survey`.
- Free Supabase projects pause after about a week with no visitors; restore from the dashboard if the app says the server can't be reached.

## Privacy notes
- Group members see each other only by a chosen nickname, never an email.
- In a class, students see only themselves and their teacher; the teacher sees each student's practice summary.
- The camera check runs entirely in the browser; video is never recorded or uploaded.
