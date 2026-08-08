# PO-28 Robot — Android App Setup Guide

---

## ⚠️ Fixing your npm error

You got this because you ran `npm install` from the wrong folder:

```
npm error enoent Could not read package.json: ...open 'C:\Users\User\package.json'
```

**Fix:** You must `cd` into the project folder first:

```cmd
cd Desktop\po-robot
npm install
```

---

## Step 1 — Install prerequisites

### Node.js (v18+)
https://nodejs.org — choose LTS. After install verify:
```cmd
node -v
npm -v
```

### Java JDK 17
https://adoptium.net — Eclipse Temurin 17 LTS. Installer sets JAVA_HOME automatically.
```cmd
java -version
```

### Android Studio
https://developer.android.com/studio

After install → **More Actions → SDK Manager**:
- SDK Platforms: check **Android 14.0 (API 34)**
- SDK Tools: check **Build-Tools 34.x**, **Emulator**, **Platform-Tools**

### Set ANDROID_HOME (Windows)
Search "Environment Variables" → System Variables → New:
- Name: `ANDROID_HOME`
- Value: `C:\Users\YOUR_NAME\AppData\Local\Android\Sdk`

Edit `Path`, add:
- `%ANDROID_HOME%\tools`
- `%ANDROID_HOME%\platform-tools`

Restart Command Prompt. Verify: `adb --version`

---

## Step 2 — Install npm dependencies

```cmd
cd Desktop\po-robot
npm install
```

## Step 3 — Add Android

```cmd
npx cap add android
npx cap sync android
```

## Step 4 — Open in Android Studio

```cmd
npx cap open android
```

Wait for Gradle sync, then press ▶ Run.

---

## Keyboard shortcuts (browser testing)

| Keys      | Action           |
|-----------|------------------|
| Q W E R   | Pads 1–4         |
| A S D F   | Pads 5–8         |
| Z X C V   | Pads 9–12        |
| 1 2 3 4   | Pads 13–16       |
| Space     | Play/Stop        |
| Enter     | Write mode       |

---

## Troubleshooting

- **npm ENOENT** → `cd` into the po-robot folder first
- **Gradle fails** → File → Invalidate Caches → Restart  
- **No sound on first tap** → Normal — tap any pad to unlock Web Audio
- **Emulator slow** → Install "Hypervisor Driver" in SDK Tools