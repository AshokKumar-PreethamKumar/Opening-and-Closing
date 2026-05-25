# OPENING--AND-CLOSING

## Aim
To implement Opening and Closing operations using Python and OpenCV.

---

## Software Required
- Anaconda – Python 3.7
- OpenCV
- NumPy
- Matplotlib

---

## Algorithm

### Step 1
Import the required libraries such as OpenCV, NumPy, and Matplotlib.

### Step 2
Create a text image using the `cv2.putText()` function.

### Step 3
Create a structuring element for morphological operations.

### Step 4
Apply the Opening operation on the noisy image.

### Step 5
Apply the Closing operation on the noisy image and display the results.

---

# Program

## Import the Necessary Packages
```python
import cv2
import numpy as np
from matplotlib import pyplot as plt
```

## Create the Text using cv2.putText
```python
# Replace 'ABCDE' with your name (only the first 5 characters)

def load_img():

    blank_img = np.zeros((600,600))

    font = cv2.FONT_HERSHEY_SIMPLEX

    cv2.putText(blank_img,
                text='PREET',
                org=(50,300),
                fontFace=font,
                fontScale=5,
                color=(255,255,255),
                thickness=25,
                lineType=cv2.LINE_AA)

    return blank_img
```

## Display the Image
```python
def display_img(img):

    fig = plt.figure(figsize=(12,10))

    ax = fig.add_subplot(111)

    ax.imshow(img, cmap='gray')

    plt.show()
```

## Create the Structuring Element
```python
kernel = np.ones((5,5), dtype=np.uint8)

kernel
```

## Display the Input Image
```python
img = load_img()

display_img(img)
```

## Use the Opening Operation
```python
# Create white noise

white_noise = np.random.randint(low=0, high=2, size=(600,600))

white_noise = white_noise * 255

noise_img = white_noise + img

display_img(noise_img)

# Apply Opening

opening = cv2.morphologyEx(noise_img, cv2.MORPH_OPEN, kernel)

display_img(opening)
```

## Use the Closing Operation
```python
# Create black noise

img = load_img()

black_noise = np.random.randint(low=0, high=2, size=(600,600))

black_noise = black_noise * -255

black_noise_img = img + black_noise

black_noise_img[black_noise_img == -255] = 0

display_img(black_noise_img)

# Apply Closing

closing = cv2.morphologyEx(black_noise_img,
                           cv2.MORPH_CLOSE,
                           kernel)

display_img(closing)
```

---

# Output

## Display the Input Image
<img width="829" height="796" alt="image" src="https://github.com/user-attachments/assets/119d2e29-1608-405b-bc02-2176419a2367" />

## Display the Result of Opening
<img width="846" height="800" alt="image" src="https://github.com/user-attachments/assets/2b725d02-430f-49dd-a974-b976910ac8e8" />

<img width="832" height="803" alt="image" src="https://github.com/user-attachments/assets/0f8ec014-3e32-427b-b032-2ba4033bc1e3" />

## Display the Result of Closing

<img width="830" height="784" alt="image" src="https://github.com/user-attachments/assets/ad395a4c-a9ea-4585-b82f-c8137e74c9a3" />

<img width="826" height="802" alt="image" src="https://github.com/user-attachments/assets/6a8254ce-04ff-4b9c-aea2-fffb27f6e81b" />

---

# Result
Thus, the Opening and Closing operations were successfully performed on the image using Python and OpenCV.

---
