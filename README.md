# Meme Magic Mirror 🎭

A pose-recognition powered magic mirror that displays memes based on your body poses! Built with p5.js and ML5.js.

## Files & Folders

- **index.html** - Main magic mirror application
- **pose-editor.html** - Visual pose editor to create custom poses
- **poses.json** - Pose definitions file (auto-loads on startup)
- **sounds/** - Place vine-boom.mp3 here for sound effects
- **poses/** - Place pose images here (e.g., dab.jpg, t_pose.jpg)

## Setup

1. Place `vine-boom.mp3` in the `sounds/` folder
2. Add pose images to the `poses/` folder (format: `[pose_id].jpg`)
3. Open `index.html` in your browser

## How to Use

### 1. Running the Magic Mirror

1. Open `index.html` in your web browser
2. Allow camera access when prompted
3. **Hold a pose for 1.5 seconds** to register it
4. Watch for the progress bar to fill up
5. Hear the vine boom and see your meme image!

**Features:**
- **Pose holding** - Must hold poses for 1.5 seconds to prevent rapid changes
- **Sound effects** - Plays vine-boom.mp3 when pose is detected
- **Full-screen images** - Displays the corresponding .jpg from poses/ folder
- **Progress bar** - Shows how long you need to hold the pose

**Controls:**
- **Load Poses** - Import a custom poses.json file
- **Pose Editor** - Open the pose editor in a new tab

### 2. Creating Custom Poses

1. Open `pose-editor.html` in your browser
2. **Use the toolbar to select your tool:**
   - **✋ Move Tool**: Click and drag individual dots to position them
   - **⬛ Select Tool**: Draw a rectangle to select multiple points at once
3. **Work with multiple points:**
   - Use **Select All** to select all keypoints
   - **Shift+Click** to add individual points to your selection
   - **Drag selected points** together to move entire body parts
   - Press **Delete** to reset selected points to default positions
   - Press **Escape** to deselect all points
4. Fill in the pose details:
   - **Pose ID**: Unique identifier (e.g., `peace_sign`)
   - **Meme Name**: Display name (e.g., `✌️ PEACE OUT ✌️`)
   - **Meme Text**: Subtitle text (e.g., `Stay Cool!`)
   - **Emoji**: Single emoji to display
   - **Image Path**: Path to image file (e.g., `poses/dab.gif` - supports .jpg and .gif)
   - **Detection Conditions**: JavaScript expression to detect the pose

5. Click **Save Pose** to add it to your collection
6. Click **Download JSON** to export all poses
7. Use **Load JSON File** to import previously saved poses

### Keyboard Shortcuts

- **Ctrl/Cmd + A** - Select all points
- **Shift + Click** - Add point to selection
- **Escape** - Deselect all points
- **Delete** - Reset selected points to default positions

### 3. Detection Conditions

Write JavaScript expressions using these keypoint variables:
- `nose`, `leftEye`, `rightEye`, `leftEar`, `rightEar`
- `leftShoulder`, `rightShoulder`
- `leftElbow`, `rightElbow`
- `leftWrist`, `rightWrist`
- `leftHip`, `rightHip`
- `leftKnee`, `rightKnee`
- `leftAnkle`, `rightAnkle`

Each keypoint has `.x` and `.y` properties.

**Example conditions:**

```javascript
// Arms up
leftWrist.y < leftShoulder.y - 50 && rightWrist.y < rightShoulder.y - 50

// T-Pose
leftWrist.y > leftShoulder.y - 50 && leftWrist.y < leftShoulder.y + 50 && rightWrist.y > rightShoulder.y - 50 && rightWrist.y < rightShoulder.y + 50 && leftWrist.x < leftShoulder.x - 100 && rightWrist.x > rightShoulder.x + 100

// Hands on hips
Math.sqrt((leftWrist.x - leftHip.x) ** 2 + (leftWrist.y - leftHip.y) ** 2) < 100 && Math.sqrt((rightWrist.x - rightHip.x) ** 2 + (rightWrist.y - rightHip.y) ** 2) < 100
```

### 4. Default Poses

The app comes with these default poses:
- 🎉 **Arms Up** - Celebration
- 💪 **T-Pose** - Dominance
- 👋 **Dab** - Epic dab
- 💁 **Hands on Hips** - Sassy mode

## JSON Format

```json
{
  "memes": {
    "pose_id": {
      "name": "🎉 MEME NAME 🎉",
      "text": "Meme text here",
      "emoji": "🎊",
      "image": "poses/pose_id.gif"
    }
  },
  "poseDetection": {
    "pose_id": {
      "conditions": "JavaScript condition here",
      "keypoints": {
        "nose": { "x": 300, "y": 150, "color": "#ff6b6b" },
        ...
      }
    }
  }
}
```

## Media Files

### Sound Effects (sounds/ folder)
- **vine-boom.mp3** - Required. Plays when a pose is successfully detected
- Download from: Search for "vine boom sound effect" online

### Pose Images (poses/ folder)
- Format: .jpg or .gif (GIFs are supported!)
- Image paths are defined in poses.json under each meme's "image" property
- Images display full-screen for 3 seconds when pose is detected
- Recommended: 1920x1080 or similar high resolution
- Use meme images, reaction GIFs, or custom artwork

Example poses.json entry:
```json
"dab": {
  "name": "👋 DAB ON 'EM 👋",
  "text": "Epic Dab Detected",
  "emoji": "🔥",
  "image": "poses/dab.gif"
}
```

Example file structure:
```
coolmemes/
├── sounds/
│   └── vine-boom.mp3
├── poses/
│   ├── dab.jpg
│   ├── t_pose.jpg
│   ├── arms_up.jpg
│   └── hands_on_hips.jpg
```

## Tips

- **Hold poses steady** - The 1.5 second hold requirement prevents accidental triggers
- **Selection tool** makes it easy to move entire body parts (like both arms) at once
- **Hold Shift** while using move tool to add points to your selection
- **Good lighting** helps with pose detection
- **Stand back** from the camera so your full body is visible
- **Hold poses** for a second to be detected
- Test your custom conditions in the browser console first
- Use && for "and" conditions, || for "or" conditions

## Troubleshooting

- **Camera not working?** Check browser permissions
- **Poses not detecting?** Try adjusting the condition thresholds (±50 values)
- **Custom poses not loading?** Check JSON syntax in the console
- **Skeleton not showing?** Make sure you're visible in frame

Have fun creating custom poses! 🎭✨
