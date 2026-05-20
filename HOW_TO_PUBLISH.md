# 📚 StudyFlow — How to Publish Your App Worldwide
### A plain-English guide for beginners

---

## What This Does

Once you follow these steps, **every time you release a new version**, GitHub will automatically:
- Build the Android APK (for all phones)
- Build the Windows installer (.exe)
- Build the macOS disk image (.dmg)
- Publish them all on a public download page — **anyone worldwide can download**

It's all free. It takes about 30 minutes to set up once.

---

## STEP 1 — Create a Free GitHub Account

1. Go to **https://github.com**
2. Click **Sign up**
3. Enter your email, create a password, choose a username
4. Verify your email

---

## STEP 2 — Install GitHub Desktop (Easier Than Command Line)

1. Go to **https://desktop.github.com**
2. Download and install it
3. Sign in with your GitHub account

---

## STEP 3 — Create a New Repository on GitHub

1. Go to **https://github.com/new**
2. Repository name: `studyflow`
3. Set to **Public** (required for free builds)
4. Click **Create repository**

---

## STEP 4 — Upload Your Project

### Using GitHub Desktop:
1. Open GitHub Desktop
2. Click **File → Add local repository**
3. Browse to your `studyflow` project folder
4. Click **Add repository**
5. If it says "not a git repo", click **Create and add**
6. Click **Publish repository** → uncheck "Keep this code private" → **Publish**

### Manually check the files are there:
After publishing, go to `https://github.com/YOUR_USERNAME/studyflow`
You should see your `lib/`, `android/`, `macos/`, `windows/` folders listed.

---

## STEP 5 — Add the Build Pipeline Files

Copy the two files from this folder into your project:

```
Your studyflow folder/
  ├── .github/
  │   └── workflows/
  │       └── release.yml        ← Copy this file here
  ├── android/
  │   └── app/
  │       └── build.gradle.kts   ← Replace existing with android_build.gradle.kts
  └── ... (rest of your files)
```

**How to copy:**
1. In your studyflow folder, create a new folder called `.github`
2. Inside `.github`, create a folder called `workflows`
3. Copy `release.yml` into `.github/workflows/`
4. Copy the contents of `android_build.gradle.kts` into `android/app/build.gradle.kts` (replace existing)

Then in GitHub Desktop:
- You'll see the new files listed under "Changes"
- Write a commit message: "Add CI/CD release pipeline"
- Click **Commit to main**
- Click **Push origin**

---

## STEP 6 — Publish Your First Release

This is what triggers the build. Every release = a new set of downloadable files.

1. Go to your GitHub repository page
2. On the right side, click **Releases**
3. Click **Draft a new release**
4. Click **Choose a tag** → type `v1.0.0` → click **Create new tag: v1.0.0**
5. Title: `StudyFlow v1.0.0 — Initial Release`
6. Click **Publish release**

---

## STEP 7 — Wait for the Build (~15-25 minutes)

1. Click the **Actions** tab on your repo
2. You'll see a workflow called "🚀 StudyFlow — Build & Release" running
3. Wait for all 3 jobs to go green ✅
   - 🤖 Android APK
   - 🪟 Windows Installer
   - 🍎 macOS App

If any job has a ❌ red cross, click it to see the error log — common fix below.

---

## STEP 8 — Share Your App Worldwide 🌍

Once all jobs are green:

1. Go to your repo → **Releases**
2. You'll see `v1.0.0` with all download files listed
3. **Share this link:** `https://github.com/YOUR_USERNAME/studyflow/releases`

Anyone can:
- Download the APK on Android
- Download the .exe on Windows
- Download the .dmg on Mac

---

## Releasing Updates

Whenever you make changes to your app:
1. Make your code changes
2. In GitHub Desktop → Commit → Push
3. Go to GitHub → Releases → **Draft a new release**
4. Tag it `v1.0.1` (or whatever version)
5. Publish → builds happen automatically

---

## Common Problems & Fixes

### ❌ "flutter: command not found" error in Actions
The workflow installs Flutter automatically. If this happens, check the `flutter-version` in `release.yml` matches your local version. Run `flutter --version` locally to check.

### ❌ Android build fails with "SDK not found"
This is handled automatically by the GitHub runner. No action needed on your end.

### ❌ macOS build fails
The macOS runner sometimes needs Xcode updates. Usually resolves itself or just re-run the job.

### ❌ Windows installer step fails
The Inno Setup installer creation is optional. Even if it fails, the raw Windows build folder is still uploaded as an artifact. You can zip that and share it.

---

## Your Public Download Link

```
https://github.com/YOUR_USERNAME/studyflow/releases/latest
```

Replace `YOUR_USERNAME` with your actual GitHub username.

---

## Want to Go Further? (Optional)

| Goal | How |
|------|-----|
| Custom domain for download page | GitHub Pages |
| Publish to Google Play Store | $25 one-time fee at play.google.com/console |
| Publish to Microsoft Store | Free at partner.microsoft.com |
| Auto-build on every code push | Change `on: tags` to `on: push` in release.yml |
| Add a nice website | Ask me to create one! |

---

*Generated for StudyFlow v1.0.0 — Clean Architecture Flutter App*
