Creating tests
==============

This part of the documentation will explain the required fields and the tests that are possible.

Each test file needs to have **exactly two keys at its root**; the '**test_info**' and the '**tests**' key.

The 'test_info' key contains a dictionary of information about this test and information needed to run this test.
The 'tests' key is a dictionary that contains the actual tests.

Ok! Let's get started:

1. Open a new file.
2. Add the JSON dictionaries stated in the example.
3. Think of a name for your test. **For what malware sample is this test?** Use that as a name for the test.
4. Save your new file in the **tests directory** of Cuckoo-unittest **with a .json extension**.

Example: the filename is Cryptolocker-test.json
 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
		}
	}

.. toctree::

    testinfokeys/index
    addingtests/index
	