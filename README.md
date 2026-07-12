# 743Inpro
# In-Pro Check-In Tool

A single-file, browser-based attendance check-in system for managing battalion in-processing. Built to replace paper nominal rolls on in-pro day — search a name, tap once, and the parade state updates live.

**No installation, no server, no database.** Everything runs inside the browser on your phone or laptop. Personnel data is loaded locally on each device and is never uploaded anywhere.

## How it works

1. **Open the tool** — visit the site link on any phone or laptop browser.
2. **Load the nominal roll** — drop in the battalion NR (`.xlsx` or `.csv`). The battalion template is auto-detected: all company sheets are read, section headers are skipped, and anyone marked *Disrupting/Deferring* is automatically excluded from expected strength.
3. **Pick your company** — each commander selects only the company their device is covering.
4. **Check people in** — type a few letters of a name, tap **Check in**. Timestamp recorded. Undo available. Walk-ins not on the roll can be added on the spot.
5. **Track live** — the top strip shows Present / Outstanding / Expected / Excused at all times. The **Outstanding** tab gives a printable chase list, and the **Dashboard** breaks numbers down by company.
6. **Consolidate** — each commander taps **Save session (.json)** and sends the file to the manpower desk. The master device loads the full NR, then uses **Merge company sessions** to combine all files into one battalion picture and exports the final parade state to Excel.

## Features

- Instant name search across 700+ personnel (NRIC last-4 search too, if the roll has an NRIC column)
- Automatic handling of Disrupting/Deferring lists via the NR's formula columns
- Duplicate-name safe — same-name personnel are kept separate, even within one company
- Company picker so each device only carries its own sub-unit
- Session save/resume — survives closed tabs and restarted phones
- Multi-session merge for consolidating results from several devices
- Excel/CSV export with attendance, timestamps, and walk-in flags
- Printable outstanding list for chasing stragglers
- Paste-data fallback for phones where the file picker is blocked

## Data privacy

- This repository contains **no personnel data** — only the empty tool.
- Nominal rolls are loaded into the browser's memory on the user's own device and are **never transmitted** to any server.
- Session files (`.json`) and exports contain personnel data — handle and share them through approved channels only, and delete them when no longer needed.
- Data lives in memory only: closing the tab discards it. Save your session regularly.

## Tips for in-pro day

- Open the tool link **before** entering camp and keep the tab open — the page needs a data connection to load, but all check-in work after that is local.
- If tapping "Choose file" does nothing, you are probably inside WhatsApp/Telegram's built-in viewer. Use its ⋯ menu → **Open in browser**, then retry. Worst case, use the paste fallback on the Setup screen.
- Open and **save the NR in Excel** before distributing it, so the Disrupting/Deferring formula values are up to date.
- Save the session every 15–20 minutes as a safety net.

## Updating the tool

Replace `index.html` with the new version (**Add file → Upload files → Commit changes**). The site link stays the same; changes go live within a couple of minutes.
