# tmi.js - docs

Our project's documentation is very important and is essential when developing an application using our framework. Our documentation is made with Jekyll & Liquid and is hosted on GitHub. Your contribution to this documentation is always appreciated.

This repository does not accept issues, only Pull Requests. If you have any issue with the documentation, feel free to contact Schmoopiie@tmijs.org or any member of our organization.

### Tips & Tricks

- You can hide a version in the ``hidden_versions`` field of ``_config.yml``
- You can change the latest version in the ``latest_version`` field of ``_config.yml``
- You must provide a date in the filename with Jekyll
- You must specify the version as a category in the header of each document

### Hosting the documentation locally

- Download and install Ruby
- Download and install Jekyll
- Git clone this repository
- Modify ``_config.yml`` and change the ``url`` to ``http://127.0.0.1:4000``
- Run ```jekyll serve --watch```
