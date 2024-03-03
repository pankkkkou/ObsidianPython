## Checks that: a != b

main.py
```python
def greet(name, isEnemy):
	if isEnemy == False:
		return f'Hello {name}, how are you?'
	elif isEnemy == True:
		return f'Hello {name}, I will kill you bastard!'
```

test_main.py
```python
def test_greet(self):
	"""greet() have to return 'How are you? if isEnemy' == False"""
	test_name = 'Jack'
	test_isEnemy = False
	self.assertEqual(main.greet(test_name, test_isEnemy), f'Hello {test_name}, how are you?')
	self.assertNotEqual(main.greet(test_name, test_isEnemy), f'Hello {test_name}, I will kill you bastard!')
```

Фигурирует:
[[Def]]
[[String (str)]]
[[Import]]
[[Boolean (bool)]]
