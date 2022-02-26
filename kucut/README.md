# KUCut

This is dockerfile of KUCut.

KU wordcut is thai word segmentor.

GitHub: https://github.com/Thanabhat/KUCut

KUCut License: GPL-2.0 License

## How to build

> docker build -t kucut:v1.4.3b2 .

## Using

> docker run --rm -it --entrypoint bash kucut:v1.4.3b2

or when docker is running.

> docker exec -it kucut:v1.4.3b2 bash

using

```sh
# python
Python 2.6.6 (r266:84292, Aug 18 2016, 15:13:37) 
[GCC 4.4.7 20120313 (Red Hat 4.4.7-17)] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> from kucut import SimpleKucutWrapper as KUCut
kucut/AIMA/utils.py:7: DeprecationWarning: the sets module is deprecated
  from sets import *
>>> myKUCut = KUCut()

>>> result = myKUCut.tokenize([u"ทดสอบทดสอบ"])
>>> result 
[[[u'\u0e17\u0e14\u0e2a\u0e2d\u0e1a', u'\u0e17\u0e14\u0e2a\u0e2d\u0e1a']]]
>>> print result[0]
[[u'\u0e17\u0e14\u0e2a\u0e2d\u0e1a', u'\u0e17\u0e14\u0e2a\u0e2d\u0e1a']]
>>> print result[0][0]
[u'\u0e17\u0e14\u0e2a\u0e2d\u0e1a', u'\u0e17\u0e14\u0e2a\u0e2d\u0e1a']
>>> print result[0][0][0]
ทดสอบ
>>> print result[0][0][1]
ทดสอบ
```