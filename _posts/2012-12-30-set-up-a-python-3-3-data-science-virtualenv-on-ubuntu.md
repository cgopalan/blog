---
layout: post
title: "Set up a Python 3.3 data science virtualenv on Ubuntu 12.10"
date: 2012-12-30
---

**1. Install Python 3.3.**

Since Ubuntu's default python distribution is 3.2, the best way would be
to download the source for 3.3 and then use configure, make, make test
and sudo make install. This will replace the default python installation
with 3.3 so that when you type python3 in the prompt, it will bring the
python 3.3 interpreter. To use the previous version, you will have to
type the version specifically - for eg python3.2.

**2. Use pyvenv in Python 3.3 to set up the virtual environment.**

Create the virtualenv. Then activate the virtual env and test that
typing 'python' brings up python 3.3.

```
/home/py-datasci-env$ pyvenv py-datasci-env(py-datasci-env)/home/py-datasci-env$
```

**3. Install pip.**

Since the virtual env installation in Python 3.3 does not install pip,
install pip using distribute and then easy_install pip.

```
(py-datasci-env)/home/py-datasci-env$ python distribute_setup.py
```

System Message: WARNING/2 (/Users/cgopalan/my_blog/content/2012-12-30-set-up-a-python-3-3-data-science-virtualenv-on-ubuntu.rst, line 85)

Literal block ends without a blank line; unexpected unindent.
(py-datasci-env)/home/py-datasci-env$ easy_install pip

**4. Install IPython notebook.**

Use pip to install ipython and then tornado, pyzmq which are needed for
the notebook functionality.

**5. Install Numpy version 1.7.**

Unfortunately pypi at the time of this writing only provides Numpy 1.6
which is not compatible with Python 3.3. So use pip to install the Numpy
version 1.7 in git.

```
(py-datasci-env)/home/py-datasci-env$ pip install git+http://github.com/numpy/numpy/
```

**6. Install nose (optional).**

If you want to run Numpy tests, you need to install nose.

**7. Install matplotlib.**

Matplotlib is now compatible with Python 3, so use pip to install it.

**8. Install Scipy.**

To get the scientific packages, install Scipy using pip.

You should be good to go!