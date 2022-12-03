In VCS, you might get an error message which includes this line:

`ERROR*************: BAD quad or saux: non-net, non-event on lhs of declarative quad!!!!!!!`

There are probably a bunch more lines, but this jumps out at you as you read the errors.  After all, it has lots of asterisks and exclamation points.

**You are reading the error messages, aren't you?**  Of course you are!  It would be silly to not read the output in a quest to discover a reason for why your code isn't compiling.

This particular error message appears whenever you have a primitive gate with more than four inputs.  For some reason, VCS refuses to implement the portion of the SystemVerilog standard that requires primitive gates to be able to have 64 (or is it 256) inputs.  Instead, VCS is limited to four inputs.

What to do about it?  Why break that gate into two (or more) separate gates.  An AND gate with up to 7 inputs can be implemented as two AND gates with four or fewer inputs.  Ditto for OR gates.