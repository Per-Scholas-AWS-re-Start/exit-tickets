




State machines are defined using JSON text that represents a structure containing the following fields.

Comment (Optional)
A human-readable description of the state machine.

StartAt (Required)
A string that must exactly match (is case sensitive) the name of one of the state objects.

TimeoutSeconds (Optional)
The maximum number of seconds an execution of the state machine can run. If it runs longer than the specified time, the execution fails with a States.Timeout Error Name.

Version (Optional)
The version of the Amazon States Language used in the state machine (default is "1.0").

States (Required)
An object containing a comma-delimited set of states.


