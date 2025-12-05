# Face Looker

Simple demo showing a face that follows your cursor.

## How to Run

Open `demo.html` in your browser.

## How to Generate Images

### Option 1: Web Interface (Easiest)

1. Go to [https://replicate.com/kylan02/face-looker](https://replicate.com/kylan02/face-looker)
2. Upload your 512×512 face image
3. Download the generated ZIP file
4. Extract the `faces/` folder from the ZIP
5. Use the images in the demo (see "How to Add Your Own Images" below)

### Option 2: API (Python)

1. Install the Replicate Python client:
   ```bash
   pip install replicate
   ```
2. Get your API token from [replicate.com/account/api-tokens](https://replicate.com/account/api-tokens)
3. Set the token:
   ```bash
   # Windows PowerShell
   $env:REPLICATE_API_TOKEN="your_token_here"
   
   # Linux/Mac
   export REPLICATE_API_TOKEN=your_token_here
   ```
4. Run Python script:
   ```python
   import replicate
   
   output = replicate.run(
       "kylan02/face-looker:latest",
       input={"image": open("your_face.jpg", "rb")}
   )
   print(output)  # Download URL for the ZIP file
   ```

### Option 3: API (cURL)

```bash
curl -X POST https://api.replicate.com/v1/models/kylan02/face-looker/predictions \
  -H "Authorization: Token $REPLICATE_API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"input": {"image": "https://your-image-url.com/face.jpg"}}'
```

## How to Add Your Own Images

1. Extract your generated images to a folder (e.g., `my_faces/`)
2. Open `demo.html` and change line 95:
   ```javascript
   const BASE_PATH = 'my_faces/';
   ```
3. Refresh the page

## Image Requirements

- Images must be named: `gaze_px{value}_py{value}_256.webp`
- Example: `gaze_px0p0_py0p0_256.webp`, `gaze_px3p0_py-3p0_256.webp`
- Grid: -15 to 15, step 3 (121 images total)

## Current Image Sets

- `face_looker/face_looker/faces/` - First set
- `face_looker/face_looker/faces 2/` - Second set

Change `BASE_PATH` in `demo.html` to switch between them.

