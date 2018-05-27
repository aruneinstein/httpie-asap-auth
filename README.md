httpie-asap-auth
================

[![PyPi Package](https://img.shields.io/pypi/v/httpie-asap-auth.svg)](https://pypi.python.org/pypi/httpie-asap-auth) [![Build Status](https://travis-ci.org/jasonfriedland/httpie-asap-auth.svg?branch=master)](https://travis-ci.org/jasonfriedland/httpie-asap-auth) [![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/ambv/black)

[ASAP](https://s2sauth.bitbucket.io/) Auth plugin for [HTTPie](https://httpie.org/).


Installation
------------

    $ pip install httpie-asap-auth


You should now see `asap` under `--auth-type` in the `$ http --help` output.


Usage
-----

    $ http --auth-type=asap --auth=path/to/asap.config http://example.com/


Example ASAP Config
-------------------

Store your ASAP config in a file following this format:

```
{
    "issuer": "webapp/admin",
    "kid": "webapp/admin/dev.pem",
    "audience": [
        "webapp"
    ],
    "sub": "administration",
    "privateKey": "-----BEGIN RSA PRIVATE KEY-----\n ... \n-----END RSA PRIVATE KEY-----"
}
```
NB. the subject (`sub` field) is optional.
