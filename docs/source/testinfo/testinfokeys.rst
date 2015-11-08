test_info keys
==============

At this time, there are five keys that you need to use in test_info, **of which all are required**.

The possible and needed keys are:

- test_name (Required)
- sample_filename (Required)
- sample_sha1 (Required)
- sample_sha256 (Required)
- sample_url (Required)

All of these keys should have a string as a value.

A simple description of each key is provided below

test_name
---------
This key should contain the name of the test.

*Value type: String*

**Best practise** is to **keep this equal to the file name of the test**.

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
			"test_name":"SomeTestName"
		},
		"tests": {
		}
	}

sample_filename
---------------
This key is very important. It tells Cuckoo-unittest what the name of the malware sample in the sample directory is.
So this is the name of the file it submits to Cuckoo for analysis.
It should contain a string name of the file. 

--> **Do not upload the malware sample!** <--

*Value type: String*

**Best practise** is using **the sha256 hash of the malware sample as a filename for it**.

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
			"test_name":"SomeTestName",
			"sample_filename":"5db1fee4b5703808c48078a76768b155b421b210c0761cd6a5d223f4d99f1eaa"
		},
		"tests": {
		}
	}

sample_sha1
-----------
This key should have the sha1 hash of the malware sample.

*Value type: String*

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
			"test_name":"SomeTestName",
			"sample_filename":"5db1fee4b5703808c48078a76768b155b421b210c0761cd6a5d223f4d99f1eaa",
			"sample_sha1":"5db1fee4b5703808c48078a76768b155b421b210c0761cd6a5d223f4d99f1eaa"
		},
		"tests": {
		}
	}

sample_sha256
-------------
This key should have the sha256 hash of the malware sample.

*Value type: String*

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
			"test_name":"SomeTestName",
			"sample_filename":"5db1fee4b5703808c48078a76768b155b421b210c0761cd6a5d223f4d99f1eaa",
			"sample_sha1":"77ba9cd915c8e359d9733edcfe9c61e5aca92afb",
			"sample_sha256":"5db1fee4b5703808c48078a76768b155b421b210c0761cd6a5d223f4d99f1eaa"
		},
		"tests": {
		}
	}

sample_url
----------
This is a key that is used to put in a URL of a sample. Cuckoo gives
the option to download the malware sample. You can use the link for that download in the sample_url.

This key can be used to automatically download the needed samples for tests that have this key.

**Only add sample URLs from trusted sources!**

*Value type: String*

Example:

 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
			"test_name":"SomeTestName",
			"sample_filename":"5db1fee4b5703808c48078a76768b155b421b210c0761cd6a5d223f4d99f1eaa",
			"sample_sha1":"77ba9cd915c8e359d9733edcfe9c61e5aca92afb",
			"sample_sha256":"5db1fee4b5703808c48078a76768b155b421b210c0761cd6a5d223f4d99f1eaa",
			"sample_url":"http://yourtrustedcuckooserver.nl/file/sample/560febba1a35004e8d1064b5"
		},
		"tests": {
		}
	}
