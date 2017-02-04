.. _quickstart:

Quickstart
==========

Make sure you have everything installed. See :ref:`installation` instructions to verify you have installed all required tools first.

Python Flask App
----------------
Getting the Flask app set up locally.

- From within the repo, run ``vagrant ssh``
- Once in the VM go to flask app directory ``cd pentameter/``
- Install latest requirements with ``pip install --upgrade -r dev-requirements.txt``
- Initialize the database with ``python init.py``
- Run the app with ``python run.py``
- Should see app at `55.55.55.10 <http://55.55.55.10/>`_

React Front End
---------------

- SSH into VM ``vagrant ssh``
- Once with VM to go front end app directory ``cd pentameter/app``
- Make sure npm dependencies are installed ``npm install``
- Build the app with ``npm run build``
- Start/run app with ``npm start``

