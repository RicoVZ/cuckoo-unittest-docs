Cuckoo unit test writing
========================
This piece of documentation will teach you how to write a unit test for Cuckoo-unittest.

After reading the pages in the documentation you will be able to:

- Create a test file
- What to put into each test
- Automatically verify that your test file is free of errors

The unit test files are used to tell Cuckoo-unittest what to look for in the Cuckoo log.
A unit test file is written in `JSON <https://en.wikipedia.org/wiki/JSON>`_. Each test file consists of two sections; a section that contains information about the test, and a section that contains the actual tests.


Contents:

.. toctree::
 
    creatingtests/index