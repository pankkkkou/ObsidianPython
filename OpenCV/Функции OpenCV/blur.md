Функция которая позволяет нам замазать какое либо изображение или видео.

```python
img = cv2.imread('images/image.jpg')
img = cv2.GaussianBlur(img, (9, 9), 0)
```

Первым мы пишем какое изображение мы хотим изменить, в данном случае мы указали переменную `img` в которой хранится наше изображение.

Вторым мы указываем кортеж в котором два числа оба должны быть нечетными, чем больше число тем больше размывается фотография. 

Третьим мы указываем значение `sigma_x`

---
# Фигурирует:
*  Основная тема [[OpenCV-python]]

