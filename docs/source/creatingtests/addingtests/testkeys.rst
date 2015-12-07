tests
=====

This section explains what each test key does and how to use it.

Some tests have special features like; using wilcards (? and \*) and using regular expressions.

**'\*'** is a wildcard for any length of characters.

**'?'** is a wildcard for a single character

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

check_expected_api_calls
------------------------
This test checks if the expected api calls were used. You can specify multiple api calls 
and for each call how many times you expect it to be called.

*Data type: Dictionary with string key and integer value*

- Wilcards: No
- Regular expressions: No

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_expected_api_calls": {
				"LdrLoadDll": 7,
				"ReadProcessMemory": 21,
				"NtCreateMutant": 2,
				"LdrUnloadDll": 7
			}
		}
	}

check_expected_regkeys_opened
-----------------------------
This test checks if the specified registry keys were opened. You can specify multiple registry keys. 

*Data type: List with strings*

- Wilcards: Yes
- Regular expressions: No

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_expected_regkeys_opened": [
				"HKEY_CURRENT_USER\\Software\\*",
				"HKEY_LOCAL_MACHINE\\SOFTWARE\\dd20ce73d7\\30e5b11d",
				"*\\SomeKey",
				"HKEY_LOCAL_MACHINE\\SOFTWARE\\Number?"
			]
		}
	}

check_expected_regkeys_read
---------------------------
This test checks if the specified registry keys were read. You can specify multiple registry keys. 

*Data type: List with strings*

- Wilcards: Yes
- Regular expressions: No

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_expected_regkeys_read": [
				"HKEY_CURRENT_USER\\Software\\*",
				"HKEY_LOCAL_MACHINE\\SOFTWARE\\dd20ce73d7\\30e5b11d",
				"*\\SomeKey",
				"HKEY_LOCAL_MACHINE\\SOFTWARE\\Number?"
			]
		}
	}

check_expected_regkeys_written
------------------------------
This test checks if the specified registry keys were written. You can specify multiple registry keys. 

*Data type: List with strings*

- Wilcards: Yes
- Regular expressions: No

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_expected_regkeys_written": [
				"HKEY_CURRENT_USER\\Software\\*",
				"HKEY_LOCAL_MACHINE\\SOFTWARE\\dd20ce73d7\\30e5b11d",
				"*\\SomeKey",
				"HKEY_LOCAL_MACHINE\\SOFTWARE\\Number?"
			]
		}
	}

check_expected_regkeys_deleted
------------------------------
This test checks if the specified registry keys were deleted. You can specify multiple registry keys. 

*Data type: List with strings*

- Wilcards: Yes
- Regular expressions: No

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_expected_regkeys_deleted": [
				"HKEY_CURRENT_USER\\Software\\*",
				"HKEY_LOCAL_MACHINE\\SOFTWARE\\dd20ce73d7\\30e5b11d",
				"*\\SomeKey",
				"HKEY_LOCAL_MACHINE\\SOFTWARE\\Number?"
			]
		}
	}

check_expected_mutexes_created
------------------------------
This test checks if the specified mutex or the specified pattern is found in the created mutexes.

*Data type: Dictionary with string key and string value*

- Wilcards: No
- Regular expressions: Yes

In this test, the key is the name or pattern of the mutex you expect to find.
The value is a setting, this setting can be the value "regex_on" or "regex_off". When using "regex_on", the
key will be read as a regular expression. If "regex_off" is used, it will be read as a normal string.

You can use the regular expressions in cases where a random mutex name is generated. But you
might know that it always has a length of 16 characters.

For a guide on regular expressions, look here: `python regular expressions <https://developers.google.com/edu/python/regular-expressions>`_

You can use `pythex.org <http://pythex.org/>`_ to test your regular expression. Make sure it only matches the values you expect.


Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			  "check_expected_mutexes_created": {
				  "^[A-Z0-9]{16}$": "regex_on",
				  "SuperAwesomeMutexName": "regex_off"
			  }
		}
	}

check_expected_ips_connected
----------------------------
This test checks if the specified IP addresses were connected to. 

*Data type: List with strings*

- Wilcards: No
- Regular expressions: No

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_expected_ips_connected": [
				"8.8.8.8",
				"144.55.48.7"
			]
		}
	}

check_expected_hosts_connected
------------------------------
This test checks if the specified hostnames were connected to.

*Data type: List with strings*

- Wilcards: No
- Regular expressions: No

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_expected_hosts_connected": [
				"malicious.something.com",
				"virus.ru"
			]
		}
	}

check_expected_processes
------------------------
This test checks if the processes and amount of them were started.

*Data type: Dictionary with string key and integer value*

- Wilcards: No
- Regular expressions: No

The key is the name of the process you expect to be started.
The value is the amount of times you expect the process to be started.

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			  "check_expected_processes": {
				  "regsvr32.exe": 2,
				  "virus.exe": 1
			  }
		}
	}

check_expected_dll_loaded
-------------------------
This test checks if the specified DLLs were loaded

*Data type: List with strings*

- Wilcards: Yes
- Regular expressions: No

The value of this test should contain a path to a DLL. If you don't know the path, use the * wildcard.

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_expected_dll_loaded": [
				"*SomeDLL.dll",
				"C:\\WINDOWS\\system32\\wininet.dll"
			]
		}
	}

check_expected_monitor_log_lines
--------------------------------
This test checks the output of the debug log that was generated by Cuckoo and
can be used to say that a certain log line should exist or not, how many times etc.
It is possible to use comparison operators to specify the amount you expect.

*Data type: Dictionary with String:dictionary(String:integer) values*

- Wilcards: Yes
- Regular expressions: No

The value of this test should contain some or part of a debug log line.

Possible comparison operators:

- ==
- >
- <
- >=
- <=

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			  "check_expected_monitor_log_lines": {
					"*INFO:Test passed:*": {">=": 4},
					"*CRITICAL:Test didn't pass:*": {"==": 0},
					"*Starting analyzer*": {"<": 4},
					"*lib.common.registry*": {">=": 5}
			  }
		}
	}