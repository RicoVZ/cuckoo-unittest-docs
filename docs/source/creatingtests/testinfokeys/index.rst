test_info keys
==============

At this time, there are six keys that you can use in test_info, **of which five are required**.

The possible and needed keys are:

- test_name (Required)
- sample_filename (Required)
- sample_sha1 (Required)
- sample_sha256 (Required)
- sample_url (Required)
- cuckoo_options (Recommended)

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
So this is the name of the file that is submitted to Cuckoo for analysis.
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
			"sample_sha1":"77ba9cd915c8e359d9733edcfe9c61e5aca92afb"
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
This key is important, it is a key that is used to store a URL of a sample. The Cuckoo webpanel gives
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

cuckoo_options
--------------
This key can contain any options that Cuckoo might have and is like using the command line "--options" parameter. The options 
will be send to Cuckoo specifically for the samply belonging to this test.
Seperate each option by a comma.

**It is recommended to use the "json.calls=0" option.**
This option tells Cuckoo not to store all function calls in a report. This saves a lot of
time and a lot of disk space. Using this key does not affect the tests in any way.

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
			"cuckoo_options":"json.calls=0,free=yes"
		},
		"tests": {
		}
	}