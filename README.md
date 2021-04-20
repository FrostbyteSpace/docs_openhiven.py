# ![OpenHiven.py](https://images.nxybi.me/da4e88d64f12.png) <br> OpenHiven.py [(View Docs)](https://Luna-Klatzer.github.io/docs_openhiven.py/latest/)
## The OpenSource Python API Wrapper for Hiven!

[![Package Version](https://img.shields.io/badge/package%20version-v0.1.3.2-purple?logo=python)](https://github.com/Luna-Klatzer/openhiven.py)
[![Python Version](https://img.shields.io/badge/python->=3.7-blue?logo=python)](https://python.org)
![Build](https://img.shields.io/github/workflow/status/Luna-Klatzer/openhiven.py/CodeQL?logo=github)
[![Latest Commit](https://img.shields.io/github/last-commit/Luna-Klatzer/openhiven.py?logo=github&color=violet)](https://github.com/Luna-Klatzer/openhiven.py/commits/mainy)
![Lines of Code](https://img.shields.io/tokei/lines/github/Luna-Klatzer/openhiven.py)
[![License](https://img.shields.io/github/license/Luna-Klatzer/openhiven.py)](https://github.com/Luna-Klatzer/openhiven.py/blob/main/LICENSE)
[![Documentation Status](https://readthedocs.org/projects/openhivenpy/badge/?version=latest)](https://readthedocs.org/projects/openhivenpy/)

## Dependencies

[![aiohttp](https://img.shields.io/github/pipenv/locked/dependency-version/Luna-Klatzer/openhiven.py/aiohttp/main)](https://docs.aiohttp.org/en/stable/)
[![asyncio](https://img.shields.io/github/pipenv/locked/dependency-version/Luna-Klatzer/openhiven.py/asyncio/main)](https://docs.python.org/3/library/asyncio.html)
[![typing](https://img.shields.io/github/pipenv/locked/dependency-version/Luna-Klatzer/openhiven.py/typing/main)](https://docs.python.org/3/library/typing.html)

## Installation
### Install (PyPi Release)

```bash
python3 -m pip install -U openhivenpy
```

### PyPi Specific Version

```bash
python3 -m pip install -U openhivenpy==version
```

### Install (Github Build)
```bash
python3 -m pip install -U https://github.com/Luna-Klatzer/openhiven.py/archive/main.zip
```

## Documentation
For full documentation visit the documentation our readthedocs-page
[here](https://openhivenpy.readthedocs.io/en/latest/) or go to the github pages build 
[here [Recommended]](https://Luna-Klatzer.github.io/docs_openhiven.py/latest/)


### Usage Example (v0.1.3.2)

**A simple UserClient Bot for quick usage:**

```python

import openhivenpy as hiven

client = hiven.UserClient("Insert token")

@client.event()
async def on_ready():
    print("Bot is ready")

client.run()

```

**A simple CommandListener for reacting to commands:**

```python 

import openhivenpy as hiven

client = hiven.UserClient("Insert token")

@client.event()
async def on_ready():
    print("Bot is ready")

@client.event()
async def on_message_create(msg):
    if msg.content.startswith("-"):
        if msg.content == "-ping":
            return await msg.room.send("pong")

client.run()
 
```

**Inherited HivenClient Example:**

```python 

import openhivenpy as hiven

class Bot(hiven.UserClient):
    def __init__(self, token, *args, **kwargs):
        self._token = token
        super().__init__(token, *args, **kwargs)

    # Not directly needed but protects the token from being changed while runtime!
    @property
    def token(self):
        return self._token

    async def on_ready(self):
        print("Bot is ready!")

if __name__ == '__main__':
    client = Bot(token="")
    client.run()

```

## Contributors
<a href="https://github.com/Luna-Klatzer/openhiven.py/graphs/contributors"><image src="https://contributors-img.web.app/image?repo=Luna-Klatzer/openhiven.py"></a>

