
# Django TDD

- 2019/01


1. 抓 `geckodriver` - Selenium for Firefox

* https://github.com/mozilla/geckodriver/releases

2. 設 環境變數


# Terms

> Functional Test == Acceptance Test == End-to-End Test == Black Box Test

# Concept

> User Story : (以 user 的觀點), 描述 app 如何運作, 此用來組織 FT.

寫 FTs(Functional Tests), 要先有一套 User Story, 寫好註解(與非Programmers討論)

```sh
git commit -a
# 自動增加 tracked files, 但不會增加 brand new files 
```

## Example

```py
from selenium import webdriver
import unittest

class NewVisitorTest(unittest.TestCase):
    def setUp(self):
        self.browser = webdriver.Firefox()
        self.browser.implicitly_wait(3)     # 不見得到處都有用! (別太依賴它!)

    def tearDown(self):
        self.browser.quit()

    def test_can_start_a_list_and_retrieve_it_later(self):
        self.browser.get('http://localhost:8000')
        self.assertIn('To-Do', self.browser.title)
        self.fail('Finish the test!')
```


