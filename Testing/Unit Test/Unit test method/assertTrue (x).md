## Checks that: bool(x) is True 

main.py
```python
def can_fly(name):
	if name == 'Batman':
		return True
	else:
		return False
```

test_main.py
```python
def test_can_fly_batman(self):
	 """can_fly() have to return 'Batman have to be able to fly' if name == 'Batman' """
	"""Test comment: Batman have to able to fly"""
	test_name = 'Batman'
	self.assertTrue(main.can_fly(test_name), f'{test_name} have to be able to fly')
```


---
Фигурирует: