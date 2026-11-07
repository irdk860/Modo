# Modo

A free web app for learning music at your own pace: piano, guitar, bass, woodwind (flute, clarinet, sax), brass (trumpet, trombone) and percussion.

**Beta 0.1.** Built to test whether each feature in the Modo plan works in a browser.

## What's in the beta
- Lessons for six instruments, in any order (basics and technique)
- Note trainer with instrument-specific controls: keyboard, fretboard with tab, note buttons with staff and fingering, drum pads
- Rhythm trainer that measures timing in milliseconds, with latency calibration
- Song practice with tempo control and section looping
- Live tuner and recording analysis (pitch detection)
- Personalised feedback and recommendations
- Beta report showing which features are proven, plus a tester questionnaire

## How it runs
- **Website:** a single `index.html`, served by GitHub Pages. No build step.
- **Accounts and data:** Supabase (project `modo`, London region). Practice history, lessons and settings sync per user; row-level security keeps each user's data private. Questionnaire responses go to the `tester_feedback` table.
- Without signing in, progress is saved in the visitor's browser.

## Reading tester feedback
Supabase dashboard → Table Editor → `tester_feedback`, or run `select * from tester_feedback_summary;` in the SQL editor.
