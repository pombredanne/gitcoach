===============================
gitcoach
===============================

.. image:: https://badge.fury.io/py/gitcoach.png
    :target: http://badge.fury.io/py/gitcoach
    
.. image:: https://travis-ci.org/tarmstrong/gitcoach.png?branch=master
        :target: https://travis-ci.org/tarmstrong/gitcoach

.. image:: https://pypip.in/d/gitcoach/badge.png
        :target: https://crate.io/packages/gitcoach?version=latest


Gitlearn and gitcoach are a pair of tools for helping me, and hopefully 
other people, better understand large projects living in Git by trying
to identify codependent pieces of code.  

* Free software: BSD license
* Documentation: http://gitcoach.rtfd.org.

Installation
------------

The easiest way to install gitcoach is through pip::

    $ pip install gitcoach

Usage
-----

To generate the prediction data, run `gitlearn`. This might take a long time, especially
when using large values for `--max-commit-values` ::

    usage: gitlearn [-h] [--max-commit-files MAX_COMMIT_FILES]

    Generate coaching data for gitcoach.

    optional arguments:
      -h, --help            show this help message and exit
      --max-commit-files MAX_COMMIT_FILES, -n MAX_COMMIT_FILES
                            Commits touching more than N files are thrown away

The `gitcoach` utility::

    usage: gitcoach [-h] [--file FILE] [--commit COMMIT] [--threshold THRESHOLD]

    Find co-dependent files based on git history. Two files are co-dependent if
    they have been modified in the same commits often enough.

    optional arguments:
    -h, --help            show this help message and exit
    --file FILE, -f FILE  Find suggestions for a specific file
    --commit COMMIT, -c COMMIT
                            Find suggestions for files modified in a specific
                            commit.
    --threshold THRESHOLD, -t THRESHOLD
                            Threshold for co-incidence ratio (default=0.8).


Example output of `gitcoach`::

    Here are some files you might want to look at:

    travis.yml	suggested by	README.rst (0.500000)
    tox.ini	suggested by	README.rst (0.500000)
    setup.py	suggested by	README.rst (0.500000)
    requirements.txt	suggested by	README.rst (0.500000)
