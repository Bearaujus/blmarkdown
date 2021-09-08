# BLMARKDOWN
Bear Au Jus Learning Markdown (blmarkdown) is a tool used to help you documenting your learning history in rich and flavored markdown.
> + Github Directory [https://github.com/bearaujus/blmarkdown](https://github.com/bearaujus/blmarkdown)
> + PyPI [https://pypi.org/project/blmarkdown/](https://pypi.org/project/blmarkdown/)

# Latest Changelog
Release Date : 09/08/2021 `v2.1`
> + Bug Fixes

# Installation
Get latest version of blmarkdown
```
pip install blmarkdown
```

# How To Use
There is **2 main class** is needed to import from **blmarkdown**
```.py
from blmarkdown import Learning, LearningData
```

Let's create our new **learning** variable
```.py
learning_subject = 'Python Fundamental'
author = 'Haryo Bagas Assyafah'

learning = Learning(learning_subject, author)
```

Now let's **add some data** to our **learning** variable
```.py
data = LearningData('Operator')
data.add('Addition')
data.add('Subtraction')
data.add('Multiplication')
data.add('Division')

learning.add(data)
```
```.py
data = LearningData('Control Structure', 'https://github.com/yourLink2')
data.add('Loop', ['For', 'While', 'Do While', 'For Each'])
data.add('Branching', ['If', 'Else If', 'Else'])

learning.add(data)
```

Let's **grab the markdown** from **learning** variable
```.py
learning.markdown()
```
> Output
```
# Learning : Python Fundamental

### Learning 01 - Operator

+ Addition
+ Subtraction
+ Multiplication
+ Division

---
### Learning 02 - Control Structure
> Shortcut : [Link](https://github.com/yourLink2)

+ Loop
    - For
    - While
    - Do While
    - For Each
+ Branching
    - If
    - Else If
    - Else

---
**Haryo Bagas Assyafah** @2021 | Generated by [blmarkdown](https://github.com/bearaujus/blmarkdown) v2.1
```

**Congratulations**, you just learned how to generate markdown using **blmarkdown** !

But, those are just **some of our features** we had. You can look at **List Function** we had, or some **example** we just documented here. **Happy Reading** ! :D

# Examples
> - Simple [Link](https://github.com/bearaujus/blmarkdown/blob/main/v2.1/examples/example_simple.ipynb)

> - Advanced [Link](https://github.com/bearaujus/blmarkdown/blob/main/v2.1/examples/example_advanced.ipynb)

# List Function
## A. Class Learning

- A.1. Constructor
```.py
def __init__(self, learning_subject_title, credit_name, footer_data=dict()):
        self.learning_subject_title = learning_subject_title
        self.credit_name = credit_name
        self.footer_data = footer_data
        self.data = list()
```
> Return Type : `None`
---

- A.2. Add LearningData
```.py
# parameter 'child' is instance of LearningData Class
def add(self, child):
        if not isinstance(child, Ld):
            raise Exception(
                "'child' must an instance of class 'LearningData'. Example : github.com/bearaujus/blmarkdown")
        else:
            self.data.append(child)
```
> Return Type : `None`
---

- A.3. Preview Generated Markdown
```.py
# this function will open a new tab in your default browser for viewing the generated markdown
    def preview(self, keep_file_on_complete=False, file_name=''):
        Utill.compile_viewer(self.__generate(), keep_file_on_complete, file_name)
```
> Return Type : `None`
---

- A.4. Save Generated Markdown
```.py
def save_markdown(self, file_name=''):
        return Utill.save_markdown(self.__generate(), file_name)
```
> Return Type : `String`
---

- A.5. Get Markdown as Raw String
```.py
def get_markdown(self):
        return self.__generate()
```
> Return Type : `String`
---

- A.6. Print Generated Markdown
```.py
def markdown(self):
        print(self.__generate())
```
> Return Type : `None`
---

- A.7. Get Added Learning Data by Index
```.py
def get_child(self, index):
        return self.data[index]
```
> Return Type : `LearningData`
---

- A.8. Get All Index Data Inside Learning
```.py
def index(self):
        if not self.data:
            return {}
        else:
            return {idx: learning_data.title for idx, learning_data in enumerate(self.data)}
```
> Return Type : `Dict`
---

## B. Class LearningData

- B.1. Constructor
```.py
def __init__(self, title, link=''):
        self.title = title
        self.link = link
        self.learning_data = dict()
```
> Return Type : `None`
---

- B.2. Add Subject
```.py
def add(self, subject, subject_data=list()):
        if not isinstance(subject, str):
            raise Exception(
                "'subject' must an instance of class 'string'. Example : Loop")
        elif not isinstance(subject_data, list):
            raise Exception(
                "'subject_data' must an instance of class 'list'. Example : ['For', 'While', 'For Each']")
        else:
            self.learning_data[subject] = subject_data
```
> Return Type : `None`
---

- B.3. Preview Generated Markdown
```.py
def preview(self, keep_file_on_complete=False, file_name=''):
        Utill.compile_viewer(self.__generate(),
                             keep_file_on_complete, file_name)
```
> Return Type : `None`
---

- B.4. Save Generated Markdown
```.py
def save_markdown(self, file_name=''):
        return Utill.save_markdown(self.__generate(), file_name)
```
> Return Type : `String`
---

- B.5. Get Markdown as Raw String
```.py
def get_markdown(self):
        return self.__generate()
```
> Return Type : `String`
---

- B.6. Print Generated Markdown
```.py
def markdown(self):
        print(self.__generate())
```
> Return Type : `None`

# Donation
Want bought us some coffee ? :D
> - Bitcoin (BTC)
```
1CCngoXD8sgbLVatc74fg1z54vbRKxTJn8
```

> - Ethereum (ETH)
```
0xec5b67e7ccffa41673e74a64d9f64ea72efc91bc
```

# Credit
+ Main Github Page : [https://github.com/bearaujus/](https://github.com/bearaujus/)
+ Linkedin : [https://www.linkedin.com/in/bearaujus/](https://www.linkedin.com/in/bearaujus/)

**Bear Au Jus - ジュースとくま** @2021
