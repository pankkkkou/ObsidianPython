## Checks that: a == b

Вот пример кода для теста двух функций на соответствие друг другу данных которые идут на выход :
Файл test_main
```python
import unittest
import main


class TestStringMethods(unittest.TestCase):
	'''Test for main.py'''
	def test_one_word(self):
		text = 'Hello'
		result = main.upper(text)
		self.assertEqual(result, text.upper())

	  def test_multiple_words(self):
		text = 'hello world!'
		result = main.multiple_words(text)
		self.assertEqual(result, 'Hello World!')

if __name__ == '__main__':
	unittest.main()
```

Файл main
```python
def upper(my_string):
	return my_string.upper()


def multiple_words(my_srting):
	return my_srting.title()
```

---
Фигурирует:
