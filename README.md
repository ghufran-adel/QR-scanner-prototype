# QR Attendance – prototype

A free, single-file web app: membership QR cards, iPhone camera scanning, Bluetooth-scanner support,
duplicate prevention, live counter, weekly/monthly reports and Excel export.
No server, no subscription, no account. Data is stored on the device that runs it.

Files: `index.html` (the whole app, libraries included) and `icon.png` (home-screen icon).

## 1. Try it on your Windows PC (2 minutes)
1. Unzip the folder and double-click `index.html` (open it in Chrome or Edge).
2. Members → **Add 20 demo members**.
3. Settings → **Generate demo history** (creates 8 past weekly events for the reports).
4. Cards → **All active** → **Print / Save as PDF** → choose "Save as PDF", A4, scale 100%, "Background graphics" ON.
5. Scan → **Start camera** and hold a printed card (or the PDF on your phone screen) up to the webcam.

## 2. Put it on your iPhone (free hosting, HTTPS is required for the camera)
Option A – GitHub Pages (recommended):
1. Create a free GitHub account → New repository (e.g. `attendance`), Public.
2. "Add file → Upload files" → drag `index.html` and `icon.png` → Commit.
3. Settings → Pages → Source: "Deploy from a branch", Branch `main` / root → Save.
4. After ~1 minute open `https://<your-username>.github.io/attendance/` in **Safari** on the iPhone.

Option B – Netlify Drop: go to app.netlify.com/drop, drag the folder in, open the URL it gives you.

Then on the iPhone: Share → **Add to Home Screen**. Always open it from the home-screen icon
(the data is kept with the home-screen app, and Safari won't clear it).

> The data on your PC and on your iPhone are separate. To move data, use
> Settings → Download backup on one device and Restore from backup on the other.
> Recommended flow: set up members on the iPhone, or import an Excel list there.

## 3. Bluetooth scanner (optional, about $30–60)
- Any 2D QR scanner with **Bluetooth HID (keyboard) mode** works. No app is needed.
- Set it to HID mode, US keyboard layout, with an **Enter (CR) suffix** (usually the default).
- Pair it in iPhone Settings → Bluetooth. Open the app's Scan tab and scan; each card is checked in instantly.
- While a scanner is paired, iOS hides the on-screen keyboard. Disconnect the scanner to type normally.

## 4. Running a weekly event
- Open the Scan tab. The **first scan of the day automatically starts today's event**.
- Green = checked in, amber = already checked in (duplicate), red = unknown or inactive card.
- Forgotten card: type the name in "Manual check-in".
- Wrong scan: tap **Undo** in "Recent scans".
- After the event: Reports → **Export to Excel**, and Settings → **Download backup**.

## 5. Importing a real member list
Excel or CSV with headers: `Name` (required), `Phone`, `Group`, `Notes`, `Member no`, `Code`.
If `Code` is present (e.g. from a previous export) the existing cards keep working.
"Export members" produces a file in exactly this format, which is useful for migration.

## Excel export contents
By Event · Weekly · Monthly · Member Summary · Matrix (members × events) · Attendance Log · Members
