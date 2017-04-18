Fibre Script Reference
======================

This document will show you how to get up and running with Read the Docs.
You will have your docs imported on Read the Docs in 5 minutes,
displayed beautifully for the world.

Game API
--------

You have two options for formatting your documentation:

* RST
* Markdown

.. _in-rst:

In reStructuredText
~~~~~~~~~~~~~~~~~~~

There is that will help you get started if you prefer.

Is a tool that makes it easy to create beautiful documentation.
Assuming you have Python_ already::

    $ pip install sphinx sphinx-autobuild

Maybe some c code?::

    function main()
    {
    	test();
    }

.. note:: Some note.

Edit your files and rebuild until you like what you see, then commit your changes and push to your public repository.
Once you have Sphinx documentation in a public repository, you can start using Read the Docs.

.. _in-markdown:

In Markdown
~~~~~~~~~~~

You can use Markdown and reStructuredText in the same Sphinx project.
We support this natively on Read the Docs, and you can do it locally