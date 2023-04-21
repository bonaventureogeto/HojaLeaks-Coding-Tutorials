---
title: "A Dive into Network Programming in Python 101"
seoTitle: "A Dive into Network Programming in Python 101"
datePublished: Mon Feb 27 2023 16:26:06 GMT+0000 (Coordinated Universal Time)
cuid: clen17u45000209jkgyct1rqy
slug: a-dive-into-network-programming-in-python-101
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1677514990493/d9e83c9a-1ab0-4810-869f-1666f61718cf.jpeg
tags: programming-blogs, python, data-science, python3, python-beginner

---

## HTTP (Hypertext Transfer Protocol):

HTTP is a protocol used for sending and receiving data over the internet. In Python, you can use the `requests` module to send HTTP requests and receive HTTP responses. Here's an example of sending an HTTP GET request using the `requests` module:

```python
import requests

response = requests.get('https://www.example.com')
print(response.status_code) 
print(response.content)
```

In this example, `requests.get` sends an HTTP GET request to the specified URL and returns an HTTP response object. The `content` attribute of the response object contains the response body as bytes.

## HTTP Application Protocol:

HTTP is an application protocol used for transmitting data between applications. In Python, you can use the `http.server` module to create a simple HTTP server. Here's an example of creating an HTTP server that serves a single file:

```python
from http.server import HTTPServer, SimpleHTTPRequestHandler

class MyHandler(SimpleHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.end_headers()
        with open('index.html', 'rb') as f:
            self.wfile.write(f.read())

httpd = HTTPServer(('localhost', 8000), MyHandler)
httpd.serve_forever()
```

In this example, `MyHandler` is a subclass of `SimpleHTTPRequestHandler` that overrides the `do_GET` method to serve a single file (`index.html`). The `HTTPServer` class is used to create an HTTP server that listens on port 8000.

## HTTP Request:

An HTTP request is a message sent by a client to a server. In Python, you can use the `requests` module to send HTTP requests. Here's an example of sending an HTTP POST request with data using the `requests` module:

```python
import requests

data = {'name': 'John', 'age': 30}
response = requests.post('https://www.example.com', data=data)
print(response.content)
```

In this example, [`requests.post`](http://requests.post) sends an HTTP POST request to the specified URL with the data in the `data` dictionary. The `content` attribute of the response object contains the response body as bytes.

## Unicode and UTF-8:

Unicode is a character encoding standard that represents each character in a unique code point. UTF-8 is a variable-width encoding that can represent all Unicode characters using one to four bytes. In Python, you can use the `encode` and `decode` methods to convert between Unicode strings and bytes using the UTF-8 encoding. Here's an example of encoding a Unicode string as bytes using the UTF-8 encoding:

```python
text = 'Hello, world!'
bytes = text.encode('utf-8')
print(bytes)
```

In this example, `text.encode('utf-8')` encodes the Unicode string `text` as bytes using the UTF-8 encoding.

## HTTP URL Library:

Python's built-in `urllib` module provides a convenient way to access web pages and other resources over the internet. Here's an example of using the `urllib.request` module to retrieve the contents of a web page:

```python
import urllib.request

url = 'https://www.example.com'
response = urllib.request.urlopen(url)
data = response.read()
text = data.decode('utf-8')
print(text)
```

In this example, `urllib.request.urlopen` sends an HTTP GET request to the specified URL and returns an HTTP response object. The `read` method of the response object reads the contents of the response into a bytes object, which is then decoded using the UTF-8 encoding to convert it to a string.

## URL Parsing:

You can use the `urllib.parse` module to parse URLs into their component parts. Here's an example of parsing a URL into its component parts:

```python
from urllib.parse import urlparse

url = 'https://www.example.com/path/to/resource?param=value'
parsed = urlparse(url)
print(parsed.scheme)   # 'https'
print(parsed.netloc)   # 'www.example.com'
print(parsed.path)     # '/path/to/resource'
print(parsed.query)    # 'param=value'
```

In this example, `urlparse` parses the URL `url` into its component parts (scheme, netloc, path, and query), which are then printed.

## URL Encoding:

You can use the `urllib.parse` module to encode special characters in URLs. Here's an example of encoding a URL with special characters:

```python
from urllib.parse import quote

url = 'https://www.example.com/search?q=Python tutorial'
encoded = quote(url)
print(encoded)   # 'https%3A//www.example.com/search%3Fq%3DPython%20tutorial'
```

In this example, `quote` encodes the special characters in the URL `url` (colon, slash, and space) using percent-encoding.

## URL Decoding:

You can use the `urllib.parse` module to decode percent-encoded characters in URLs. Here's an example of decoding a URL with percent-encoded characters:

```python
from urllib.parse import unquote

url = 'https%3A//www.example.com/search%3Fq%3DPython%20tutorial'
decoded = unquote(url)
print(decoded)   # 'https://www.example.com/search?q=Python tutorial'
```

In this example, `unquote` decodes the percent-encoded characters in the URL `url` using UTF-8 decoding.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy Coding!