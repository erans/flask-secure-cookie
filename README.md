# flask-secure-cookie - Use Tornado cookies in Flask

Use Tornado styled secure cookies in Flask.
This module can also help you interoperate between a Flask project and a Tornado project using the same cookies.

The code support both old style v1 Tornado cookies as well as v2.
Default cookie encoding uses v2 while decoding uses v1 as a minimum.

## Installation
* `pip install flask-secure-cookie`

## Usage

```python
from flask_secure_cookie import SecureCookie

app = Flask(__name__)
# Cookie secret value will be read from app.config.
# If it does not exist, an exception will be thrown.
#
# You can also set the cookie secret in the SecureCookie initializer:
# secure_cookie = SecureCookie(app, cookie_secret="MySecret")
#
secure_cookie = SecureCookie(app)

redirect_to_protected = redirect("/protected")
response = app.make_response(redirect_to_protected)

secure_cookie.set("mycookie", "Hello World", response)
cookie_value = secure_cookie.get("mycookie")
```

For furhter comments, thoughts, ideas, etc feel free to send pull requests or contact me at:
* [@erans](https://twitter.com/erans) (http://eran.sandler.co.il)
