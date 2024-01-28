Возьмем примерную программу которая будет открывать показывать размеры нашей картинки и потом открывать ее на это время и закрывать через энное время или с помощью кнопки Q

```python
import cv2

img = cv2.imread('images/OpenCv.jpg')

print(img.shape)

new_img = cv2.resize(img, (img.shape[1] // 2, 500))

print(new_img.shape)

cv2.imshow('Result', new_img)

cv2.waitKey(int(input('How many seconds you want to see picture or video: ')))

```

