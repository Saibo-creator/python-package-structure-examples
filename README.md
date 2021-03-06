# python-package-structure-examples

This repo is just a collection of several popular python packages from small(e.g. Tweepy) to complicated ones(ee.g. Numpy). The aim is to show the structure of such packages.

## To locate a package(source code) on the PC
```python
import numpy as np
print(np) 
# something like <module 'numpy' from '/opt/anaconda3/lib/python3.7/site-packages/numpy/__init__.py'>
```

## Original packages:
[PyPDF2](https://github.com/mstamy2/PyPDF2)

[tweepy](https://github.com/tweepy/tweepy)
...

## Take-away
- import inside the package:
```python
from .logging_setup import logger
from .AbstractImageAgeLabeler import AbstractImageAgeLabeler
```
- tests and example run scripts placed outside of source code directory


- inside \_\_init__.py
```
__version__ = '3.9.0'
__author__ = 'Joshua Roesslein'
__license__ = 'MIT'

from tweepy.api import API
from tweepy.auth import AppAuthHandler, OAuthHandler
from tweepy.cache import Cache, FileCache, MemoryCache
from tweepy.cursor import Cursor
from tweepy.error import RateLimitError, TweepError
from tweepy.models import DirectMessage, Friendship, ModelFactory, SavedSearch, SearchResults, Status, User
from tweepy.streaming import Stream, StreamListener
```


> Don't run a module inside the package as a script. Only run scripts from outside the package.
> Mixing scripts inside packages is tricky and should be avoided if at all possible. Use a wrapper script that imports the package and runs your 'scripty' function instead.


## License
All packages retain their original license. Please refer to the original package license for more information.
