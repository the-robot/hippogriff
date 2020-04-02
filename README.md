<h1 align="center">Yaat</h1>  
<p align="center"><i>yet another ASGI toolkit</i> </p>

## Yaat

Yaat is a lightweight asynchronous web framework/toolkit. Learn more about <a href="https://asgi.readthedocs.io/en/latest/" target="_blank">ASGI</a>.  

**Features**  

- Provide decorator routes & class based views.
- Template support with [Jinja2](https://jinja.palletsprojects.com/).
- Cookie support.
- WebSocket support.
- Background tasks runner.
- Test client using [httpx](https://www.python-httpx.org/).
- Static file serving.

## Requirements

Python 3.6+

## Setup

```bash
pip3 install yaat
```

> or just clone this and use directly to get the latest development version.

You'll also want to install an ASGI server, such as uvicorn.

```bash
pip3 install uvicorn
```

## Example

**example.py**
```python
from yaat import Yaat
from yaat.responses import TextResponse

app = Yaat()

@app.route("/")
async def index(req):
    response = TextResponse(content="Hello World")
    return response
```

Then run using uvicorn:

```bash
uvicorn example:app
```

> See <a href="https://github.com/the-robot/yaat/wiki">Wiki</a> for documentation and complete examples

## FYI

1. Is this just another web framework?
    - I started this to learn how a framework like <a href="https://palletsprojects.com/p/flask/" target="_blank">Flask</a> actually works and I am also interested in ASGI, so I decided to build this in ASGI instead of WSGI. However, after I used <a href="https://palletsprojects.com/p/flask/" target="_blank">Flask</a> and <a href="https://www.djangoproject.com" target="_blank">Django</a> for a long time, I found things that I love and hate from each. So when I started working on this, I made it to include good features that both of those have (I.e. `individual small applications` feature from Django).
