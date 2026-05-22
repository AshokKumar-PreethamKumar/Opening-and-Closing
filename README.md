# OPENING--AND--CLOSING

## Aim
To perform Morphological Opening and Closing operations using Python and OpenCV.

---

## Software Required
- Anaconda – Python 3.7  
- OpenCV  

---

## Algorithm

### Step 1
Import the required libraries.

### Step 2
Create a blank image and add text using `cv2.putText()`.

### Step 3
Create the structuring element (kernel).

### Step 4
Apply the Morphological Opening operation.

### Step 5
Apply the Morphological Closing operation.

---

# Program

## Import the Necessary Packages

```python
import cv2
import numpy as np
```

---

## Create a Blank Image

```python
image = np.zeros((300, 500), dtype="uint8")
```

---

## Create the Text using cv2.putText

```python
cv2.putText(image,
            'OPENCV',
            (50, 180),
            cv2.FONT_HERSHEY_SIMPLEX,
            3,
            (255),
            8)
```

---

## Create the Structuring Element

```python
kernel = cv2.getStructuringElement(
            cv2.MORPH_RECT,
            (15, 15))
```

---

## Use Opening Operation

```python
opening = cv2.morphologyEx(
            image,
            cv2.MORPH_OPEN,
            kernel)
```

---

## Use Closing Operation

```python
closing = cv2.morphologyEx(
            image,
            cv2.MORPH_CLOSE,
            kernel)
```

---

## Display the Input Image

```python
cv2.imshow("Input Image", image)
```

---

## Display the Result of Opening

```python
cv2.imshow("Opening", opening)
```

---

## Display the Result of Closing

```python
cv2.imshow("Closing", closing)
```

---

## Wait and Destroy Windows

```python
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

# Output

## Display the Input Image

<img width="817" height="698" alt="image" src="https://github.com/user-attachments/assets/1dd93781-84b3-4f88-87a0-b0a86d9a246a" />


---

## Display the Result of Opening

<img width="795" height="697" alt="image" src="https://github.com/user-attachments/assets/cf4c7489-0493-47fc-bb4c-4143d43b3766" />


---

## Display the Result of Closing

<img width="752" height="696" alt="image" src="https://github.com/user-attachments/assets/7127c10b-c2ac-49c9-8864-1654066aab47" />

---

# Result
Thus, the Morphological Opening and Closing operations were successfully implemented using Python and OpenCV.

## Developed By
### Name : ASHOK KUMAR PREETHAM KUMAR
### Reg No: 212224040032
