### Table of Contents
1. [When is the last time I can submit an assignment?](#q1)
1. [How many times can I hand in an assignment?](#q2)
1. [Why am I getting an error regarding "Reportlab"?](#q3)
1. [Why is it failing to hand in my files?](#q4)
1. [It says my handin directory wasn't found.](#q5)
1. [Can I hand in my files without compiling?](#q6)

<a name="q1"></a>
#### When is the last time I can submit an assignment?
Read the homework handout for the deadline. Attempts to run `handin240` for
overdue assignments will *not* work, as we do not accept late work.

Please *please* **please** leave ample time before the deadline to submit. We
are not responsible for your inability to plan accordingly.

<a name="q2"></a>
#### How many times can I hand in an assignment?
You may submit as many times as you want, up until the deadline. We will always
take the last submission for grading. Unfortunately there is no functionality to
choose a submission for assessment, so take care when submitting that nothing
breaks.

<a name="q3"></a>
#### Why am I getting an error regarding "Reportlab"?
You probably didn't install the dependencies as specified in the [initialization
portion](Overview#initialization) of the overview. Just run
```bash
init_handin240
```
and you should be good to go.

<a name="q4"></a>
#### Why is it failing to hand in my files?
**Stop.** Before you make a Piazza post, please *read the terminal output*. 4/5
times the problem is solved by reading what the program tells you. If it isn't
clear after doing this, *then* go ahead and ask away.

<a name="q5"></a>
#### It says my handin directory wasn't found.
It's likely that one of two things is happening:
1. We haven't opened the handin yet on the servers. There may be a delay in
   setting up the assignment, or maybe we forgot to open it.
   **Post a Piazza question so we can get on that**.
2. Your name isn't in the class roster. This could be because you're on the
   waitlist, or there's some other administrative mistake. **Post a private
   question on Piazza, or email the course staff.** We'll sort it out on our
   end.

<a name="q6"></a>
#### Can I hand in my files without compiling?
Short answer: Yes. Run the handin script with the `-s` flag to skip the compile
check step.

Long answer: Yes, *but do so at your own risk*. Unless you are 100% sure the
code compiles it is *highly* inadvisable to do this, as code that doesn't
compile **will get a zero**. There are no exceptions.
