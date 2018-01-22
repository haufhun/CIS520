Files changed: 
	modified:   ../tests/threads/Make.tests
		- Added "alarm-mega" to "tests/treads_TESTS".

	modified:   ../tests/threads/Rubric.alarm
		- Added "4	alarm-mega" to "Functionality and robustness of alarm clock".

	new file:   ../tests/threads/alarm-mega.ck
		- Created perl script alarm-mega.

	modified:   ../tests/threads/alarm-wait.c
		- Added test function "test_alarm_mega" which calls the "test_sleep" function, 
			creating 5 cores and 70 alarms for each core.

	modified:   ../tests/threads/tests.c
		- Added alarm-mega test function "test_alarm_mega" to be associated with 
			"alarm-mega" in the tests array.

	modified:   ../tests/threads/tests.h
		- Add reference to test function test_alarm_mega.


To find the files needed to be changed, I used the "grep -r alarm-multiple *" to find alarm-multiple references. I then added a reference to "alarm-mega" in each of those files, seen above. 

Next, after making the change in alarm.c, I found that a test_alarm_mega function was needed to make the call. I then did a search for "test_alarm_multiple" to find the references to this function, and found that it was in the alarm-wait.c file. I create the "test_alarm_mega" function there. 

After making these changes, I recompiled the src/threads build, and then tested. 
