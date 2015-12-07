GetSample
=========

This tool downloads the in "sample_url" specified sample for the
specified test and stores it in the specified directory and **writes the 
filename to the sample_filename key in test_info**.

This tool can be given a test file or a directory containing test files.

**Usage**::

    $ ./utils/GetSample.py sample_dir test_file/test_dir

**Downloading a single sample**::

    $ ./utils/GetSample.py samples tests/sometest.json

This will download the sample for sometest.json to the samples directory.

**Downloading samples for all tests in a directory**::

    $ ./utils/GetSample.py samples tests

This will download samples for all the tests in the tests directory and store
them in the samples directory.
    