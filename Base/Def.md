Функция в питоне представляет из себя маленькую программируемую команду которую мы можем вызывать бесконечно раз и вызывать ее из другого файла методом [[Import]] 

Вот пример функции которая будет исполнять сложение двух даных ей числе 

Первой строкой мы дадим имя функции и скажем что она может применять.

```python
def sum_of_two_numbers(a, b):
```

Второй строкой мы уже объясним ей что делать с этими данными:
1. Создаем переменную 'result' 
2. Положить в переменную сумму a и b

```python
def sum_of_two_numbers(a, b):
	result = a + b
```

Третьей строкой мы объясним ей что нужно делать с результатом, а именно просот вернуть значение.

```python
def sum_of_two_numbers(a, b):
	result = a + b
	return result
```