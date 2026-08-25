# SensorMind - Standard Operating Procedure (SOP)

## 1. Overview

### 1.1 Purpose
SensorMind is a browser-based sensor intelligence application that uses your device's built-in sensors (accelerometer, gyroscope, GPS, etc.) to detect your activity, count steps, and create automated responses based on your behavior.

### 1.2 Key Features
- **Activity Detection**: Automatically detects Walking, Running, Stationary, Driving, Cycling, and Public Transport
- **Step Counting**: Counts your steps with visual progress tracking
- **Automation Engine**: Create rules that trigger actions based on detected activities
- **Sound Effects**: Audio feedback for walking, running, and fall detection
- **Gesture Recording**: Record custom gestures to trigger actions
- **Privacy Controls**: Do Not Record mode, data clearing, and export options
- **No Cloud Upload**: All data stays on your device

### 1.3 System Requirements
| Requirement | Details |
|-------------|---------|
| **Browser** | Chrome 60+, Safari 14+, Firefox 60+ |
| **Device** | Smartphone with accelerometer recommended |
| **Permissions** | Device motion, location (optional), battery access |
| **Internet** | Not required (runs entirely on-device) |

---

## 2. Quick Start Guide

### 2.1 First-Time Setup (30 seconds)

1. **Open** SensorMind in your browser
2. **Read** the permission information
3. **Click** "Enable Sensors"
4. **Grant** motion permission when prompted
5. **Start using** - the app will detect your activity

### 2.2 Navigation Overview

| Tab | Icon | Purpose |
|-----|------|---------|
| Context | 🧭 | Home - current activity, status, timeline |
| Activity | 📊 | Activity breakdown, step count, statistics |
| Rules | ⚡ | Create and manage automation rules |
| Insights | 💡 | Ask questions, patterns, suggestions |
| Sensors | 📡 | Sensor status, gestures, simulation |
| Settings | ⚙️ | Privacy, goals, places, system settings |

---

## 3. Core Features - How To Use

### 3.1 Activity Detection (Automatic)

**What it does:** Detects your current activity without any input.

**How to read the display:**
- **Context Card** (top of Home): Shows emoji + activity name
- **Confidence**: Percentage of certainty (e.g., "92% confidence")
- **Metrics**: Speed, steps, shake intensity

**Click "Why was this detected?"** to see the reasoning.

### 3.2 Step Counting

**Automatic** - counts steps when walking or running.

**View your steps:**
- **Home tab**: Shows steps + progress bar toward goal
- **Activity tab**: Shows total steps in statistics

**Set a step goal:**
1. Go to **Settings** tab
2. Find **"Goals"** section
3. Enter your daily step goal (default: 10,000)
4. Press Enter to save

### 3.3 Creating Automations (Rules)

**Purpose:** Automatically trigger actions when specific activities are detected.

**Step-by-step:**
1. Go to **Rules** tab (⚡ icon)
2. Fill in the form:
   - **Name**: "Morning Walk Alert" (descriptive)
   - **When**: Select trigger activity
   - **If**: Optional conditions (battery, time, confidence)
   - **Then**: Choose action (notification, mode, etc.)
   - **Cooldown**: Minimum time between triggers (30s+)
3. Click **"Create Automation"**
4. **Toggle ON/OFF** using the switch
5. **Test** with the "Test" button

**Export/Import:** Use buttons at the top of Rules tab to backup your rules.

### 3.4 Sound Effects

**What sounds play:**
- 🚶 **Walking**: Soft footstep sounds
- 🏃 **Running**: Faster, higher-pitched footsteps
- ⚠️ **Fall**: Crash/thud sound effect

**Controls:**
- 🔊/🔇 **Quick toggle** at the top of the app
- **Settings toggle** in Privacy & Data Control section

> Note: Sounds require Web Audio API support. Works on most modern browsers.

### 3.5 Recording Gestures

**Purpose:** Create custom gesture-triggered actions.

**How to record:**
1. Go to **Sensors** tab (📡 icon)
2. Find **"My Gestures"** section
3. Enter a **Gesture Name** (e.g., "Triple Shake")
4. Select **Duration** (2, 5, or 10 seconds)
5. Select **Action** (Show alert, Record event, Switch mode)
6. Click **"Start Recording"**
7. Perform your gesture within the time limit
8. Click **"Save Gesture"** when prompted

### 3.6 Ask SensorMind (AI-Like Query)

**Purpose:** Get answers about your current state and data.

**How to ask:**
1. Go to **Insights** tab (💡 icon)
2. Type your question
3. Click **"Ask"** or press Enter

**Example questions:**
- "What am I doing now?"
- "How active was I today?"
- "Which sensors are active?"
- "What automations ran today?"
- "How long was I walking?"
- "Sound effects status?"

### 3.7 Privacy Controls

**Key privacy features:**
- **Do Not Record**: Pauses all data logging
- **Clear History**: Wipes all session data
- **Battery Saver**: Auto-throttles when battery < 20%
- **Data Export**: Download all data as JSON
- **Reset SensorMind**: Delete EVERYTHING (requires confirmation)

---

## 4. Troubleshooting

### 4.1 Common Issues

| Issue | Solution |
|-------|----------|
| **"Enable Sensors" does nothing** | Refresh page and try again. Check browser console (F12). |
| **Activity shows "Unknown"** | Ensure sensors are enabled. Move the device. |
| **Steps not counting** | Walk more vigorously. Need peaks >1.2g with variance >0.04. |
| **No sound effects** | Check sound toggle is ON. Device not muted. |
| **GPS speed shows 0** | GPS takes time. Walk outside for better signal. |
| **Automations not triggering** | Check rule enabled. Verify cooldown. Check conditions. |
| **Simulation running on phone** | Check "Simulation Controls" in Sensors tab. Set to "Auto-detect". |

### 4.2 Browser Notes

| Browser | Notes |
|---------|-------|
| **Chrome (Android)** | Full support. Allow motion permissions. |
| **Safari (iOS)** | Motion requires user gesture (tap). |
| **Firefox** | Good support. May ask permissions separately. |
| **Desktop Browsers** | Simulation mode only (no real sensors). |

### 4.3 Permissions Guide

| Permission | Why Needed | If Denied |
|------------|------------|-----------|
| **Device Motion** | Accelerometer for activity detection | Simulation mode only |
| **Geolocation** | GPS speed for vehicle detection | Speed = 0, no place context |
| **Battery** | Low battery detection | Battery level unavailable |

---

## 5. Data Storage & Privacy

### 5.1 What Data is Stored

| Data Type | Storage | Persistence |
|-----------|---------|-------------|
| Activities | IndexedDB or Memory | Persists across sessions |
| Timeline Events | IndexedDB or Memory | Persists across sessions |
| Automations | IndexedDB or Memory | Persists across sessions |
| Gestures | IndexedDB or Memory | Persists across sessions |
| Places | IndexedDB or Memory | Persists across sessions |
| Step Count | Memory only | Resets on reload |

### 5.2 Storage Engine

- **IndexedDB**: Full persistence (when available)
- **Memory Fallback**: Session-only (when IndexedDB unavailable)
- Check storage status in Developer Mode

### 5.3 Data Privacy Guarantee

✅ **All data stays on your device**  
✅ **No data is sent to any server**  
✅ **Your location is never uploaded**  
✅ **You control all data deletion**  
✅ **No cloud backup** (by design)

---

## 6. Advanced Features

### 6.1 Developer Mode

**Purpose:** View raw sensor data for debugging.

1. Go to **Settings** → **"Developer / Debug Mode"**
2. Toggle **"Show raw pipeline output"**
3. View real-time sensor readings, features, and classification

**Shows:**
- Raw accelerometer, gyroscope, GPS values
- Feature extraction results (variance, cadence)
- Fusion scores for each activity
- Confidence and quality metrics
- Processing time for each stage

### 6.2 Simulation Mode

**Purpose:** Test SensorMind when real sensors are unavailable.

**Controls in Sensors tab:**
- **Auto-detect**: Automatic sensor/simulation selection
- **Force Simulation**: Always use simulation
- **Force Activity**: Simulate specific activities
- **Simulate Fall Impact**: Tests fall detection
- **Simulate Shake**: Tests shake detection

---

## 7. Quick Reference

### 7.1 Key Actions & Locations

| Action | Location |
|--------|----------|
| Enable Sensors | Gate screen (first page) |
| Toggle Sound | Top of app or Settings |
| Quick Mode Switch | Mode buttons below header |
| View Activity Breakdown | Activity tab |
| Create Automation | Rules tab |
| Ask a Question | Insights tab |
| Check Sensors | Sensors tab |
| Manage Privacy | Settings tab |

### 7.2 Keyboard Shortcuts (Desktop)

| Shortcut | Action |
|----------|--------|
| `Ctrl+Shift+I` | Open Developer Tools |
| `Esc` | Close modals |
| `Enter` | Submit forms |

---

## 8. Safety & Disclaimer

### 8.1 Health Disclaimer
⚠️ **SensorMind is NOT a medical device**  
- Activity and step tracking are estimates, not medical measurements  
- Fall detection is experimental and NOT a substitute for emergency systems  
- Do not rely on SensorMind for medical decisions

### 8.2 Battery Usage
- Sensor processing may consume battery  
- Use Battery Saver mode to reduce power consumption  
- Close the app when not in use

### 8.3 Privacy Assurance
- All data stays on your device  
- No data is ever transmitted  
- Full control over deletion

---

## 9. Getting Help

### 9.1 Self-Diagnosis
1. Check **Developer Mode** for detailed diagnostics
2. View the **Why Panel** for activity reasoning
3. Export data for external analysis
4. Refresh the page to reset state

### 9.2 Error Messages

| Message | Meaning | Resolution |
|---------|---------|------------|
| "Simulation mode" | No real sensors detected | Normal on desktop |
| "Storage: Memory (session only)" | IndexedDB unavailable | Data resets on reload |
| "No automations have run yet" | No rules triggered | Move to trigger activity |
| "Insufficient data" | Not enough sensor data | Move the device |

### 9.3 Report Issues
- Open an issue on GitHub
- Include: Browser, Device, Steps to reproduce
- Attach exported debug data (Settings → Export)

---

## 10. Glossary

| Term | Definition |
|------|------------|
| **Accelerometer** | Sensor measuring acceleration (movement) |
| **Gyroscope** | Sensor measuring orientation/rotation |
| **GPS** | Global Positioning System for location/speed |
| **Variance** | Measure of how much acceleration varies (indicates activity) |
| **Confidence** | How certain the system is about its classification |
| **Cooldown** | Minimum time between automation triggers |
| **IndexedDB** | Browser database for persistent storage |
| **Session** | One usage period (until page refresh) |
| **DNR** | Do Not Record - privacy mode |

---

## 11. Version History

| Version | Date | Changes |
|---------|------|---------|
| 2.1 | Current | Sound effects, step goals, transition chart |
| 2.0 | Previous | Complete rewrite with automation engine |
| 1.0 | Original | Basic activity detection |

---

**Last Updated:** August 2026

*This SOP is maintained alongside the SensorMind application. For the latest version, refer to the application itself or the deployment repository.*

---

**🎯 Quick Start:**
1. Open the app
2. Click "Enable Sensors"
3. Allow permissions
4. Start moving!
