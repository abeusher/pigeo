================
``pigeo`` readme
================

Introduction
------------

``pigeo`` is a document or Twitter user geolocation tool. Given a piece of text or a Twitter user, it can predict their locations based on pre-trained models.

The design principles are as follows:

1. Lightweight and fast
2. Comes with text-based classification and network-based regression pre-trained models.
3. It is possible to train new text-based classification models.
4. It can be used in shell mode, web mode powered by Python Flask and as a library.
5. It supports informal text.
6. It's performance is evaluated over a standard Twitter geolocation dataset.

Quick Start
-----------

``pigeo``'s installation is straightforward:


1. download the zip file from github or run: ``git clone http://github.com/afshinrahimi/pigeo.git``

2. ``cd pigeo`` then ``chmod +x download_models.sh`` and then run ``./download_models.sh``.

This downloads the pre-trained models and extracts them in models. alternatively you can do it manually.

3. Requirements:

	3.1 ``sudo pip install flask-restful`` or use ``pip install --user flask-restful`` if you are not a sudoer.
	
	3.2 ``sudo pip install scikit-learn`` 

4. ``pigeo`` is ready to use. Go to usage section.


Directory Structure
-------------------

The directory structure after installation and downloading the models should be:

```
.
├── download_models.sh
├── models
│   ├── lpworld
│   │   └── userhash_coordinate.pkl.gz
│   └── lrworld
│       ├── clf.pkl.gz
│       ├── coordinate_address.pkl.gz
│       ├── label_coordinate.pkl.gz
│       └── vectorizer.pkl.gz
├── params.py
├── pigeo.py
├── README.md
├── static
│   └── styles
│       ├── bootstrap-3.3.6-dist
│       │   ├── css
│       │   │   ├── bootstrap.css
│       │   │   ├── bootstrap.css.map
│       │   │   ├── bootstrap.min.css
│       │   │   ├── bootstrap.min.css.map
│       │   │   ├── bootstrap-theme.css
│       │   │   ├── bootstrap-theme.css.map
│       │   │   ├── bootstrap-theme.min.css
│       │   │   └── bootstrap-theme.min.css.map
│       │   ├── fonts
│       │   │   ├── glyphicons-halflings-regular.eot
│       │   │   ├── glyphicons-halflings-regular.svg
│       │   │   ├── glyphicons-halflings-regular.ttf
│       │   │   ├── glyphicons-halflings-regular.woff
│       │   │   └── glyphicons-halflings-regular.woff2
│       │   └── js
│       │       ├── bootstrap.js
│       │       ├── bootstrap.min.js
│       │       └── npm.js
│       └── main.css
├── templates
│   ├── index.html
│   └── index-simple.html
└── twitterapi.py
```

Usage
-----


```
usage: pigeo.py [-h] [--model MODEL] [--dump_dir DUMP_DIR] [--host HOST]
                [--port PORT] [--mode MODE]

optional arguments:
  -h, --help            show this help message and exit
  --model MODEL, -d MODEL
                        text-based classification model directory to be used.
                        default(./models/lrworld)
  --dump_dir DUMP_DIR, -o DUMP_DIR
                        directory to which a newly trained model is saved.
                        default(./models/test_model)
  --host HOST           host name/IP address where Flask web server in web
                        mode will be running on. Set to 0.0.0.0 to make it
                        externally available. default (127.0.0.1)
  --port PORT, -p PORT  port number where Flask web server will bind to in web
                        mode. default (5000).
  --mode MODE, -m MODE  mode (web, shell) in which pigeo will be used. default
                        (shell).
```


