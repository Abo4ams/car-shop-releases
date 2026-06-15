# Car Shop Cairo — Releases

This repo hosts auto-update files for the Car Shop Cairo desktop app.

---

## How to publish an update

### Step 1 — Run the release script

Open PowerShell in the app project folder and run:

```powershell
.\scripts\release.ps1 -Version "0.2.0" -Notes "What you fixed" -GitHubUser "Abo4ams"
```

Change `0.2.0` and the notes each time. The script will:
- Bump the version in `tauri.conf.json`
- Build and sign the installer
- Generate `latest.json`
- Open the GitHub release page in your browser automatically

### Step 2 — Publish on GitHub

The browser will open a release page. Do this:

1. The tag and title will already be filled as `v0.2.0` — leave them
2. Write a short description if you want (optional)
3. Drag and drop **both files** from the project root folder:
   - `car-shop-0.2.0-setup.exe`
   - `latest.json`
4. Click **Publish release**

### Step 3 — Done

The app on the shop PC checks for updates every time it launches.
When it finds a new version it shows a blue notification at the bottom corner.
The owner clicks **Install & Restart** and the update installs automatically.

---

## Version history

| Version | Date | Notes |
|---------|------|-------|
| 0.1.0   | 2026-06-15 | Initial release |

*(Add a row here each time you publish)*

---

## Important files

| File | Location | Purpose |
|------|----------|---------|
| Private key | `C:\Users\moham\.tauri\car-shop.key` | Signs every update — keep it safe |
| Release script | `scripts\release.ps1` in app project | Run this to build a release |
| App project | `D:\Mohamed Files\Projects\car-shop-app` | Source code |
