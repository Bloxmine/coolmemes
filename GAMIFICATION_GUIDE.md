# 🎮 Gamification & Capture Features Guide

## 📊 Scoring System

### How Points Work
- **Base Points**: 10 points per pose
- **Combo Multiplier**: Stay on the same pose to build combo (up to 10x)
- **Score Calculation**: Base Points × Combo Multiplier

### Score Panel (Bottom Left)
- **Score**: Total points earned this session
- **Combo**: Current combo multiplier
- **Poses**: Total number of poses hit

### Example
1. Hit "T-Pose" → 10 points (1x combo)
2. Hit "T-Pose" again → 20 points (2x combo)
3. Hit "T-Pose" again → 30 points (3x combo)
4. Switch to "Dab" → 10 points (1x combo, reset)

---

## 🏆 Leaderboard

### Features
- Automatically saves your top 10 sessions
- Shows: Score, Poses Hit, Max Combo, Unique Poses
- Persistent storage (survives page refresh)

### How to Access
Click **🏆 Leaderboard** button to view high scores

### Leaderboard Entry
Your session is saved when you:
- Open the leaderboard
- Have a score > 0

---

## 🎖️ Achievements

### Available Achievements

| Achievement | Description | Unlock Condition |
|------------|-------------|------------------|
| 🏅 **First Steps** | Hit your first pose | Complete 1 pose |
| 🎯 **Pose Master** | Hit 50 poses | Complete 50 poses |
| 👑 **Combo King** | Reach 5x combo | Achieve 5x multiplier |
| 🌈 **Variety Show** | Hit 5 different poses | Use 5 unique poses |
| ⚡ **Speedster** | Complete timer under 30s | Timer challenge < 30 seconds |
| 📸 **Photographer** | Take 10 screenshots | Capture 10 photos |
| 💯 **Century Club** | Score 100 points | Reach 100 points |
| ⏰ **Marathon Runner** | Play for 10 minutes | 10 minutes playtime |

### Achievement Popup
When you unlock an achievement:
- Large animated popup appears
- Shows achievement name and description
- Auto-dismisses after 3 seconds

---

## 🎯 Challenges

### Daily Challenges
1. **🎯 Daily Challenge**: Hit 20 different poses
2. **⚡ Speed Challenge**: Reach 10x combo
3. **💯 Century Challenge**: Score 500 points

### Challenge Progress
- View current progress for each challenge
- Progress is tracked per session

---

## ⏱️ Timer Mode

### How It Works
1. Click **⏱️ Timer Mode** to start
2. Hit **10 different poses** as fast as possible
3. Timer runs until challenge complete
4. Receive your final time

### Rules
- Only unique poses count
- Repeating the same pose doesn't decrease counter
- Complete under 30 seconds to unlock **Speedster** achievement

### UI Elements
- **Timer Display**: Shows elapsed time (MM:SS)
- **Poses Remaining**: Countdown of unique poses needed
- **Stop Timer**: Cancel challenge anytime

---

## 📸 Screenshot System

### Auto-Capture
- **Automatic**: Every confirmed pose is captured
- Photos saved to gallery automatically
- Stored in browser localStorage

### Manual Capture
- Click **📷 Screenshot** button
- Captures current canvas view
- Downloads image immediately
- Also saves to gallery

### Screenshot Format
- PNG format
- Full canvas size
- Includes: video, skeleton, keypoints, overlays

---

## 🎥 Video Recording

### How to Record
1. Click **🎥 Record** to start
2. Button turns red: **⏹️ Stop**
3. Click again to stop and download

### Recording Details
- **Format**: WebM (VP9 codec)
- **FPS**: 30 frames per second
- **Quality**: High quality capture
- **Auto-download**: Video downloads when stopped

### What's Captured
- Live webcam feed
- Pose skeleton overlay
- Keypoint markers
- Meme overlays
- Score panel

---

## 🖼️ Photo Gallery

### Features
- View all captured poses
- Click photo to open fullscreen
- Shows pose name and timestamp
- Grid layout for easy browsing

### Gallery Actions
- **💾 Download All**: Downloads all photos as separate files
- **🗑️ Clear All**: Deletes entire gallery (requires confirmation)

### Storage
- Stored in browser localStorage
- ~5-10MB storage limit
- Oldest photos auto-deleted when full

---

## 📤 Social Sharing (Future Feature)

While not fully implemented, you can:
1. Open photo in new tab (click in gallery)
2. Right-click → Save or Share
3. Use browser's native share options

---

## 🎮 Tips & Tricks

### Maximize Your Score
1. **Build Combos**: Repeat same pose for multiplier
2. **Balance Strategy**: Switch poses to hit different targets
3. **Use Timer Mode**: Practice speed for high scores

### Achievement Hunting
- **Photographer**: Enable auto-screenshot (already on!)
- **Speedster**: Memorize 10 quick poses
- **Marathon**: Leave app running in background
- **Variety Show**: Explore all available poses

### Gallery Management
- Download photos regularly (storage is limited)
- Clear gallery if experiencing performance issues
- Screenshots work even without gallery access

---

## 🛠️ Technical Details

### Data Storage
- **localStorage**: Achievements, leaderboard, gallery
- **Session Data**: Score, combos, current game state
- **Persistence**: Data survives page refresh (except session)

### Performance
- Canvas recording: ~30 FPS
- Screenshot capture: Instant
- Gallery rendering: Optimized for 50+ photos

### Browser Compatibility
- **Modern Browsers**: Chrome, Firefox, Edge, Safari
- **Required Features**: localStorage, Canvas API, MediaRecorder
- **Recommended**: Chrome for best recording quality

---

## 🚀 Controls Summary

| Button | Function |
|--------|----------|
| 🏆 Leaderboard | View high scores |
| 🎖️ Achievements | View locked/unlocked achievements |
| 📸 Gallery | Browse captured photos |
| 🎯 Challenges | View daily challenges & timer mode |
| ⏱️ Timer Mode | Start speed challenge |
| 📷 Screenshot | Manual capture & download |
| 🎥 Record | Start/stop video recording |

---

## 📝 Notes

- **Auto-Screenshot**: Happens on every pose confirmation
- **Storage Limits**: Browser localStorage ~5-10MB
- **Privacy**: All data stored locally (no server uploads)
- **Reset Data**: Clear browser localStorage to reset everything

Enjoy your gamified pose detection experience! 🎉
