# FocusSense: Context-Aware Parental Control & Habit Building Platform

FocusSense is a dual-tier parental safety system consisting of:
1. **Android Application (`/app`)**: Jetpack Compose mobile client featuring real-time Accessibility scraping, Gemini 3.5 Flash & on-device MobileBERT threat evaluation, scheduled app blocking, and live location safety.
2. **Central Cloud/Backend Server (`/server`)**: Python FastAPI backend with PostgreSQL (Supabase) integration and safety endpoints.

---

## 📌 Opening in Android Studio

When opening or syncing this project in **Android Studio**:

### 1. Why do files look different or "missing" in the left sidebar?
By default, Android Studio selects the **"Android" Project View** (top-left dropdown above the project file tree).
- The "Android" view **only displays Gradle Android modules (`:app`)**.
- Backend directories (`/server`), environment configurations (`.env`), SQL schemas (`schema.sql`), and documentation are **hidden** in this view.
- **To see all project files**: Click the dropdown at the very top of the Project window (where it says **"Android"**) and switch it to **"Project"** or **"Project Files"**. You will immediately see the complete root directory including `server/`, `.env`, and all architecture files.

### 2. Exploring the App on an Android Emulator or Physical Device
- The app includes **1-Click Instant Demo Launchers** on the first screen:
  - Tap **"Parent Dashboard"** to instantly open the full admin console with pre-seeded logs, charts, curfew schedules, and live location map.
  - Or sign in using the demo account: **`parent@demo.com`** / Password: **`demo`** (a one-tap auto-fill button is provided).
- **Gemini 3.5 Flash AI**: The app directly evaluates threats using your configured Gemini API key on-device and in cloud mode across 7 safety categories. You can test live text prompts in the **Gemini Cloud AI Sentinel & Threat Lab** (Tab 3 or via the shortcut banner on Tab 0).

---

## 🚀 Running the Python Backend Server (Optional)
The Android app is fully functional autonomously with its local Room database and direct Gemini API evaluation. If you also want to run the FastAPI backend locally:

```bash
cd server
pip install -r requirements.txt
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

*Note for Android Emulators: Use `http://10.0.2.2:8000` as the Server URL in the app to connect to a server running on your computer.*
