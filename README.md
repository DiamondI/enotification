# enotification

## Introduction

`enotification` is a small package based on [zmail](https://github.com/zhangyunhao116/zmail), used to email you when your function is finished.

## Installation

`pip install enotification`

## Requirements

Since `enotification` is based on zmail, you should meet the requirements of zmail:

>Before using it, please ensure:
>
>- Using python3
>- Open SMTP/POP3 functions in your mail (For **@163.com** and **@gmail.com** you need to set your app private password)
>
>Then, all you need to do is just import zmail.

Note, since this package uses **f-string**, thus it requires Python>=3.6.

## QuickStart

`enotification` is designed as a decorator class

```python
from enotification import ENotification
import time

@ENotification(send_from="your email", password="your email password")
def test_func():
    print("test!")
    time.sleep(10)
    
if __name__ == "__main__":
    test_func()
    # your email would receive an email like this:
    # subject: This is a notification from enotification!
    # content: 
    # Your function test_func is finished!
    # Start time: 2021-04-23 11:13:54
    # End time: 2021-04-23 11:14:04
    # Time cost: 0:00:10!

```

## TODO

- [x] Ask user to input her email account or password if it is empty (using [getpass](https://docs.python.org/3/library/getpass.html) module). Usage: `@ENotification()`. **Note:** the `()` is must.
- [ ] 

## Q & A

If the notification email is not sent correctly, please read zmail's [Q&A](https://github.com/zhangyunhao116/zmail#qa) part to see more specific configurations.

