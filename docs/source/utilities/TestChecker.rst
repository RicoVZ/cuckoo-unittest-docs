TestChecker
===========

**This tool checks if a test file**:

- Consists of valid JSON
- Contains the mandatory test_info keys
- Contains existing test keys
- Has the correct test data type for tests. (*Dictionary, String, List etc..*)

It reports all errors it can find. If the error is a JSON error, run the checker
again after fixing it.

This tool can be given a test file or a directory containing test files.

**Usage**::

    $ ./utils/TestChecker.py test_file/tests_dir

**Checking a single test file**::

    $ ./utils/TestChecker.py tests/sometest.json

This will check the specified test file for errors and report them.
	
**Check all test files in a directory**::

    $ ./utils/TestChecker.py tests

This will check all test files in the specified directory for errors and report them.