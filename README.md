PyTach
================
Python library for communicating with GlobalCache iTach IR/RF device

Features
================
* Command line interface
* REST interface
* Web interface

Usage
================
### Control device
	pytach.py nexa (1-4) (on | off)
	pytach.py multibrackets (up | stop | down)
	pytach.py yamaha (cd | dtv | stereo | vol_up | vol_down)

### Start web server
	pytach.py --web

Installation
================
Debian
----------------

	cd /opt
	sudo su - 
	git clone https://github.com/gotling/PyTach.git
	cd PyTach
	pip install -r requirements.txt

Standalone development server
----------------
Make PyTach available at http://address:8082
	ln -s /opt/PyTach/scripts/pytach-init.sh /etc/init.d/pytach
	chmod +x /etc/init.d/pytach
	/etc/init.d/pytach start

nginx + uWSGI (recommended)
----------------
Make PyTach available at http://address/pytach

	apt-get install uwsgi uwsgi-plugin-python python-bottle nginx
	ln -s /opt/PyTach/scripts/pytach-uwsgi.ini /etc/uwsgi/apps-enabled/
	service uwsig restart
	Add content of scripts/nginx-config to /etc/nginx/sites-available/default
	service nginx restart

Acknowledgements
================
Bottle
----------------
Copyright © 2012 Marcel Hellkamp.

http://bottlepy.org/

License: MIT License

docopt
----------------
Copyright © 2012 Vladimir Keleshev

http://docopt.org/

License: MIT License

microajax
----------------
Copyright © 2008 Stefan Lange-Hegermann

https://code.google.com/p/microajax/

License: BSD License

Pure
----------------
Copyright © 2014 Yahoo! Inc

http://purecss.io/

License: BSD License
