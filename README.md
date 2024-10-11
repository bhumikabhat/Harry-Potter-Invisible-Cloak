---

# Invisibility Cloak using OpenCV

This project implements a real-time invisibility cloak effect using Python and OpenCV. By detecting a specific cloak color (blue by default), it captures the background and replaces the area covered by the cloak with that background, giving the illusion that the person is invisible.

## Features
- Real-time invisibility effect.
- Adjustable cloak color (set to blue by default).
- Captures background dynamically and applies it during video feed.

## How It Works
1. **Background Capture:** The camera captures multiple frames and creates a static background when the user moves out of the frame.
2. **Color Detection:** The code identifies a specific color (blue by default) in the live video using HSV color space.
3. **Mask Creation:** A mask is created to detect the area where the cloak is worn.
4. **Cloak Effect:** The cloak area is replaced with the captured background, making the wearer appear "invisible."

## Requirements
Make sure you have the following installed:

- Python 3.x
- OpenCV
- NumPy

Install the required packages using:

```bash
pip install opencv-python numpy
```

## Usage

1. **Clone this repository:**

   ```bash
   git clone https://github.com/your-username/invisibility-cloak-opencv.git
   cd invisibility-cloak-opencv
   ```

2. **Run the script:**

   ```bash
   python invisibility_cloak.py
   ```

3. **Move out of the frame** for a few seconds to allow the camera to capture the background. Then, wear a blue cloak or any cloth that matches the specified HSV range.

4. **Press 'q'** to quit the program.

### Customization
To change the color of the cloak, modify the `lower_blue` and `upper_blue` HSV ranges in the code. For example:

```python
lower_blue = np.array([90, 50, 50])
upper_blue = np.array([130, 255, 255])
```

Replace these with the desired color's HSV range.

### Explanation of Key Functions
- **`create_background(cap, num_frames)`**: Captures multiple frames to create a static background using the median of the frames.
- **`create_mask(frame, lower_color, upper_color)`**: Detects the cloak color in the frame by creating a mask based on the specified HSV range.
- **`apply_cloak_effect(frame, mask, background)`**: Combines the mask and background to apply the invisibility effect.

### Controls
- **'q'**: Quit the program.

## Troubleshooting
- **Background not captured properly?** Ensure you move completely out of the frame during the initial background capture phase.
- **Cloak color not detected?** Adjust the HSV values of `lower_blue` and `upper_blue` to better match the color of your cloak under current lighting conditions.


---

This README provides detailed usage instructions, customization options, and a basic understanding of the project's key functions.
