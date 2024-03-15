```python
import cv2

img = cv2.imread('Image/image.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

  
if __name__ == '__main__':
	cv2.imshow('Result', img)
	cv2.waitKey(0)
```

## Кратко о HSV
---
### HSV (Hue, Saturation, and Value) Color Model

The hue component in HSV is specified by an angle from 0° to 360°, where Red is 0°, Yellow is 60°, Green is 120°, Cyan is 180°, Blue is 240°, and Magenta is 300°**

[Wikipedia about HSV](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjDpr7CqeqEAxVlQvEDHZ7ACjMQmhN6BAhgEAI&url=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FHSL_and_HSV&usg=AOvVaw1ZPPY_-vZ9sHQYhSswXtuD&opi=89978449)

---
# Фигурирует:
*  Основная тема [[OpenCV-python]]