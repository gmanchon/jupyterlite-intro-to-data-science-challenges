# JupyterLite Demo

[![lite-badge](https://jupyterlite.rtfd.io/en/latest/_static/badge.svg)](https://jupyterlite.github.io/demo)

JupyterLite deployed as a static site to GitHub Pages, for demo purposes.

## ✨ Try it in your browser ✨

➡️ **https://jupyterlite.github.io/demo**

![github-pages](https://user-images.githubusercontent.com/591645/120649478-18258400-c47d-11eb-80e5-185e52ff2702.gif)

## Requirements

JupyterLite is being tested against modern web browsers:

- Firefox 90+
- Chromium 89+

## Deploy your JupyterLite website on GitHub Pages

Check out the guide on the JupyterLite documentation: https://jupyterlite.readthedocs.io/en/latest/quickstart/deploy.html

## Further Information and Updates

For more info, keep an eye on the JupyterLite documentation:

- How-to Guides: https://jupyterlite.readthedocs.io/en/latest/howto/index.html
- Reference: https://jupyterlite.readthedocs.io/en/latest/reference/index.html

This template provides the Pyodide kernel (`jupyterlite-pyodide-kernel`), the JavaScript kernel (`jupyterlite-javascript-kernel`), and the p5 kernel (`jupyterlite-p5-kernel`), along with other
optional utilities and extensions to make the JupyterLite experience more enjoyable. See the
[`requirements.txt` file](requirements.txt) for a list of all the dependencies provided.

For a template based on the Xeus kernel, see the [`jupyterlite/xeus-python-demo` repository](https://github.com/jupyterlite/xeus-python-demo)

setup environment for the [Introduction to Data Science](https://github.com/lewagon/intro-to-data-science-challenges) challenges

the challenges are served through [mybinder](https://www.notion.so/lewagon/B2U-Intro-to-Data-Science-f88a9af1afff44109bfd3)

entry point: https://mybinder.org/v2/gh/lewagon/intro-to-data-science-challenges/master

# update package version

update the contents of `requirements_raw.txt`, then process `requirements.txt` from a new env:

``` bash
pyenv install 3.10.13
pyenv virtualenv-delete binder
pyenv virtualenv 3.10.13 binder
pyenv local binder
pip install -U pip
export REQ_URL=https://raw.githubusercontent.com/lewagon/intro-to-data-science-env/master/requirements_raw.txt
export PACKAGES=$(curl -s ${REQ_URL} | tr "\\n" " ")
pip install $(echo ${PACKAGES})
pip freeze | grep $(echo ${$(echo ${PACKAGES})/#/-e }) > requirements.txt
```

# info

`build.log` contains the mybinder image build and container start logs
