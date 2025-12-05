# Face Looker - Presentation Speech

## Introduction & Quick Demo

Good [morning/afternoon/evening], everyone! Today I'm excited to present **Face Looker** - an interactive gaze tracking demonstration that creates an engaging visual experience.

*[Show the demo - move cursor around]*

As you can see, the face on the screen follows your cursor movements in real-time, creating an illusion of eye contact and engagement. This is achieved through a clever combination of pre-rendered images and JavaScript-based gaze tracking.

---

## Technical Explanation

### How It Works

Face Looker uses a **grid-based gaze tracking system** that works in three main steps:

1. **Image Generation**: A face image is processed through an AI model to generate 121 different gaze directions, creating a grid of images where the eyes look in different directions.

2. **Coordinate Mapping**: When you move your cursor, the system calculates the relative position of your cursor to the face container. This position is normalized to coordinates between -1 and 1.

3. **Image Selection**: The normalized coordinates are quantized to match the pre-generated image grid (ranging from -15 to 15 in steps of 3), and the corresponding face image with the matching gaze direction is displayed.

### Technical Details

- **Grid Configuration**: 11×11 grid (121 images total)
- **Gaze Range**: -15 to +15 degrees in both X and Y axes
- **Step Size**: 3 degrees between each image
- **Image Format**: WebP format for optimal performance
- **Naming Convention**: `gaze_px{value}_py{value}_256.webp`

The system uses JavaScript to:
- Track mouse/touch movements
- Calculate normalized coordinates
- Quantize to the nearest grid point
- Dynamically swap images for smooth gaze following

---

## Installation Guide

### Option 1: Web Interface (Easiest)

This is the simplest way to get started with Face Looker. Follow these steps:

#### Step 1: Generate Your Face Images

1. Navigate to the Replicate web interface: [https://replicate.com/kylan02/face-looker](https://replicate.com/kylan02/face-looker)

2. **Prepare your image**: You'll need a 512×512 pixel face image. Make sure the face is clearly visible and centered.

3. **Upload your image**: Click the upload button and select your prepared face image.

4. **Generate**: The AI model will process your image and generate 121 different gaze direction images.

5. **Download**: Once processing is complete, download the generated ZIP file.

#### Step 2: Extract and Organize Files

1. **Extract the ZIP file** to a location of your choice.

2. **Locate the `faces/` folder** inside the extracted contents. This folder contains all 121 gaze direction images.

3. **Place the folder** in your project directory. For example:
   ```
   your-project/
   ├── demo.html
   └── my_faces/          ← Your extracted faces folder
       ├── gaze_px0p0_py0p0_256.webp
       ├── gaze_px3p0_py0p0_256.webp
       └── ... (121 images total)
   ```

#### Step 3: Configure the Demo

1. **Open `demo.html`** in a text editor.

2. **Find line 181** (or search for `BASE_PATH`).

3. **Update the path** to point to your extracted faces folder:
   ```javascript
   const BASE_PATH = 'my_faces/';  // Change this to your folder name
   ```

4. **Save the file**.

#### Step 4: Run the Demo

1. **Open `demo.html`** in your web browser (simply double-click the file or use "Open with" your preferred browser).

2. **Move your cursor** around the screen and watch the face follow your movements!

3. **That's it!** No server setup, no complex installation - just open and enjoy.

---

## Final Result

The final implementation features:

- **Beautiful UI**: Modern design with a dotted black and white background theme
- **3D Card Effect**: Interactive text section that responds to mouse movements with a 3D tilt effect
- **Responsive Layout**: Two-section design with the face on the right and information on the left, separated by a clean divider line
- **Smooth Performance**: Optimized image swapping for seamless gaze tracking
- **Cross-Platform**: Works on desktop and mobile devices with touch support

The demo creates an engaging, interactive experience that demonstrates the power of AI-generated gaze tracking in a simple, accessible web interface.

---

## Use Cases

Face Looker has numerous practical and creative applications:

### 1. **Interactive Websites & Portfolios**
   - Create engaging "about me" sections where your face follows visitors
   - Add personality to personal websites and portfolios
   - Enhance user engagement on landing pages

### 2. **Educational Demonstrations**
   - Teach concepts of coordinate mapping and normalization
   - Demonstrate image pre-rendering techniques
   - Showcase AI model capabilities in an accessible way

### 3. **Marketing & Advertising**
   - Create attention-grabbing banner ads
   - Interactive product showcases
   - Engaging social media content

### 4. **Entertainment & Gaming**
   - Interactive character displays
   - Game UI elements
   - Virtual avatars with realistic gaze

### 5. **Accessibility Tools**
   - Eye-tracking demonstrations
   - Assistive technology prototypes
   - Research in human-computer interaction

### 6. **Art & Creative Projects**
   - Digital art installations
   - Interactive exhibits
   - Creative web experiences

### 7. **Customer Service**
   - Virtual assistants with engaging presence
   - Chatbot interfaces with visual feedback
   - Interactive help systems

---

## Conclusion

Face Looker demonstrates how modern AI and web technologies can create engaging, interactive experiences with minimal setup. The combination of pre-rendered images and real-time JavaScript creates a smooth, responsive gaze tracking system that's both impressive and accessible.

Thank you for your attention! I'm happy to answer any questions or provide a live demonstration.

---

## Q&A Preparation

**Common Questions:**

- **Q: Can I use my own face?**  
  A: Yes! Simply follow the installation guide using Option 1 (Web Interface) to generate images from your own photo.

- **Q: Does it work on mobile?**  
  A: Yes, the demo includes touch support for mobile devices.

- **Q: How many images do I need?**  
  A: The system requires 121 images (11×11 grid) for full functionality, which is automatically generated by the Replicate model.

- **Q: Can I customize the appearance?**  
  A: Yes, you can modify the CSS in `demo.html` to change colors, sizes, and layout to match your needs.

