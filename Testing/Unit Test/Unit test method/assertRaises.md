Проверяет вызывается ли при исполнение функции то что мы хотим. 

main.py
```python
def greet(name, isEnemy):
	if not isinstance(isEnemy, bool):
		raise ValueError('isEnemy must be boolean type')
	if isEnemy == False:
		return f'Hello {name}, how are you?'
	elif isEnemy == True:
		return f'Hello {name}, I will kill you bastard!'
```

test_main.py


```python
def test_greet_boolean(self):
	with self.assertRaises(ValueError):
		main.greet('Ivan', 'Bla-bla')
```


Фигурирует:
[[Def]]
[[String (str)]]
[[Import]]
[[Boolean (bool)]]
