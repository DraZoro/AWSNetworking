AWS Networking Notes
====================

This is a collection of notes for AWS Networking. Most topics are from AWS 
Certified Advanced Networking - Speciality (ANS-01). 

.. contents::

About
-----

The documentation project using `Sphinx Documentation <https://www.sphinx-doc.org/>`_ 
project.

Building Sphinx documentation 
-----------------------------

* The following instructions were tested on Ubuntu 22.04::

    $ lsb_release -a
    Distributor ID: Ubuntu
    Description:    Ubuntu 22.04.4 LTS
    Release:        22.04
    Codename:       jammy

* This is only required for the new project. Just adding here for reference::
  
    docker run -it --rm -v ./Doc:/docs sphinxdoc/sphinx:7.3.7 sphinx-quickstart

  

docker run -it --rm -v Doc:/docs sphinxdoc/sphinx sphinx-quickstart