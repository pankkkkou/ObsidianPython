## Colar Model Lab 

```python
import cv2

img = cv2.imread('Image/image.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

  
if __name__ == '__main__':
	cv2.imshow('Result', img)
	cv2.waitKey(0)
```

Очень похоже на [[COLOR_BGR2HSV]]

[Wikipedia](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwi2m-zvq-qEAxVKcPEDHVBtB2UQFnoECBQQAQ&url=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FCIELAB_color_space&usg=AOvVaw3rEXKbE1f1W-KGTdrdbpDs&opi=89978449) 

---
Фигурирует: [[OpenCV-python]]