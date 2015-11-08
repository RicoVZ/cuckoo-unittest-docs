Adding tests
============

This section explains how to use the various types of tests that are available.
You can add as many tests to one test file as you want.

The type of data type differs per test. The data type that you should use for the test is documented at each test. 

The available tests are:

- check_md5 - *Type: String*
- check_sha1 - *Type: String*
- check_sha256 - *Type: String*
- check_sha512 - *Type: String*
- check_expected_api_calls - *Type: Dictionary: String:Integer*
- check_expected_regkeys_opened - *Type: List: String*
- check_expected_regkeys_read - *Type: List: String*
- check_expected_regkeys_written - *Type: List: String*
- check_expected_regkeys_deleted - *Type: List: String*
- check_expected_files_opened - *Type: List: String*
- check_expected_files_read - *Type: List: String*
- check_expected_files_written - *Type: List: String*
- check_expected_files_deleted - *Type: List: String*
- check_expected_mutexes_created - *Type: Dictionary: String:String*
- check_expected_ips_connected - *Type: List: String*
- check_expected_hosts_connected - *Type: List: String*
- check_expected_processes - *Type: Dictionary: String:Integer*
- check_expected_dll_loaded - *Type: List: String*

Each test key in the 'tests' key should be seperated by a comma. Like so:
 .. code-block:: javascript
    :linenos:
 
	{
		"test_info": {
		},
		"tests": {
			"check_md5":"",
			"check_sha256":"",
			"check_expected_api_calls": {
			},
			"check_expected_ips_connected": [
			]
		}
	}

Documentation on each type of test is coming soon..