As you may realize, we have a strict "No lines of code longer than 80
characters" rule in our style guideline. As you may also realize, sometimes we
need to print out really long lines that span more than 80 characters.

Thankfully There are multiple ways you can break up a long string into multiple
lines:
1. Use line breaks, and make sure each line break in the middle of your string
   ends with a single backslash (\\). Note that if you do this, then if you
   indent the following lines you'll have some pretty wonky looking spacing. The
   indent spaces become part of your string.  Try it out if you're wondering what 
   I mean by that :)
2. Use multiple strings, concatenated together (my personal preference). To do
   this, use brackets `{}`, with strings separated by commas. For example:
```systemverilog
$display({"some potentially long string that if we ",
    "were to write this all in one line it would ",
    "probably violate some style guideline :("});
```
Will print out:
```
some potentially long string that if we were to write this all in one line it would probably violate some style guideline :(
```
