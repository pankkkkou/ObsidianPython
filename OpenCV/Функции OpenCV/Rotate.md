```python
import cv2

def rotate(img_param, angle):
	height, width = img_param.shape[:2]
	point = (width // 2, height // 2)
	mat = cv2.getRotationMatrix2D(point, angle, 1)
	return cv2.warpAffine(img_param, mat, (width, height))
```

Фигурирует: [[OpenCV-python]]