tests
=====

This section explains what each test key does and how to use it.

Some tests have special features like; using wilcards (? and \*) and using regular expressions. 
At each test it is stated what features the tests supports.

As stated before, each test needs a specific type of test data format. The formats that 
are currently used by the tests are: Strings, lists, and dictionaries.

Each test on this page states what type of data it needs.

check_md5
---------
This test checks if the given md5 hash matches the md5 hash calculated by Cuckoo.

*Data type: String*

Support information:

- Wilcards: No
- Regular expressions: No

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_md5":"e48e13207341b6bffb7fb1622282247b"
		}
	}

check_sha1
----------
This test checks if the given sha1 hash matches the sha1 hash calculated by Cuckoo.

*Data type: String*

Support information:

- Wilcards: No
- Regular expressions: No

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_sha1":"77ba9cd915c8e359d9733edcfe9c61e5aca92afb"
		}
	}

check_sha256
------------
This test checks if the given sha256 hash matches the sha256 hash calculated by Cuckoo.

*Data type: String*

Support information:

- Wilcards: No
- Regular expressions: No

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_sha256":"5db1fee4b5703808c48078a76768b155b421b210c0761cd6a5d223f4d99f1eaa"
		}
	}

check_sha512
------------
This test checks if the given sha512 hash matches the sha512 hash calculated by Cuckoo.

*Data type: String*

Support information:

- Wilcards: No
- Regular expressions: No

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_sha512":"6f0ac65fe01188660aad900bfe16c566ebf0e56c0a7d4a15bd831049108de80bd3a2fbf1a8b91662433a40458ec208a207cab073f190bd65b889e95e4fca8e09"
		}
	}