## Checks that: bool(x) is False

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
def test_can_fly_eny_one_else(self):
	"""Test comment: Only Batman have to able to fly"""
	test_names_list = ['Bob', 'Jack', 'Tema']
	self.assertFalse(main.can_fly(test_names_list[0]), 'Only, Batman have to be able to fly')
	self.assertFalse(main.can_fly(test_names_list[1]), 'Only, Batman have to be able to fly')
	self.assertFalse(main.can_fly(test_names_list[2]), 'Only, Batman have to be able to fly')
```

---
Фигурирует:


