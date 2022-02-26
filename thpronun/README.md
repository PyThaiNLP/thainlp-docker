# thpronun

This is dockerfile of thpronun.

thpronun is a program for analyzing pronunciation of Thai words.

GitHub: [https://github.com/tlwg/thpronun](https://github.com/tlwg/thpronun)

Blog (Thai): https://thep.blogspot.com/2018/08/thpronun.html

thpronun license: GNU General Public License v3.0

## How to build

> docker build -t thpronun:v0.2 .

or using docker image by PyThaiNLP

> docker pull ghcr.io/pythainlp/thainlp-docker/thpronun:thpronun-v0.2.0

## Using

> docker run --rm -it thpronun:v0.2  bash -c "thpronun mode word"

or using docker image by PyThaiNLP

> docker run --rm -it ghcr.io/pythainlp/thainlp-docker/thpronun:thpronun-v0.2.0 bash -c "thpronun mode word"

**list mode**
- `-t` - Thai pronunciation
- `-r` - romanization
- `-p` - phonetic
- `-s` - soundex
- `-w` - raw code


**Example**

```sh
$ docker run --rm -it thpronun:v0.2  bash -c "thpronun -t ทดสอบ"
ทดสอบ:
ทะ-ดะ-สอบ
ทะ-ดะ-สะ-อบ
ทะ-ดะ-สอบ
ทะ-ดะ-สะ-อบ
ทะ-ดด-อบ
ทด-สะ-อบ
ทด-สอบ
ทด-สะ-อบ
ทะ-ดด-อบ

$ docker run --rm -it thpronun:v0.2  bash -c "thpronun -s ทดสอบ"
ทดสอบ:
Ta_-da_-scp
Ta_-da_-sa_-?op
Ta_-da_-scp
Ta_-da_-sa_-?op
Ta_-dot-?op
Tot-sa_-?op
Tot-scp
Tot-sa_-?op
Ta_-dot-?op

```