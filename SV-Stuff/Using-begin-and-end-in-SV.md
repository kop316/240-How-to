You may sometimes see in SystemVerilog the use of the `begin` and `end`
keywords. You may wonder when you should use one. This page should hopefully
answer that question.

The short answer is: anywhere you would use `{` or `}` in a programming language
like C.

The most common SV constructs you'll use in this class that can use `begin` and
`end` are below. If you see a construct you're not yet familiar with, don't
worry. You'll come across them later in the semester.
* `initial` blocks
* `for` loops
* conditionals (`if`, `else if`, `else`)
* `always_comb`
* inside the cases in your `case` statements
* `always_ff`

Another thing to note is that you technically don't have to *always* use
`begin`/`end` on one condition: *the line of code that you would have put in the
`begin`/`end` block is only one line long*. What I mean by this is if you have
multiple lines of code, then they should be enclosed between a `begin` and
`end`. Otherwise the construct will only treat the first line as part of the
block.

This may be kind of annoying to remember, so my advice is this: **always use
`begin` and `end`, even for one-liners**. Yes it's not 100% necessary, and may
`end` up making your code longer, but the potential bugs you avoid by doing
this is almost certainly worth it.

This "one-liner" rule is more clear in an example. Let's consider a `for` loop
(which you may use in testbenches **only**. I don't want to see these in actual
hardware!).

```systemverilog
logic [4:0] i;
initial begin
    for (i = 5'd0; i < 5'd16; i++)
        #10 a[3:0] = i[3:0];
end
```

This is perfectly fine. There is only one statement (where I set `a` to be the
value of `i` in that loop iteration) within that `for` loop, so I don't need a
`begin` and `end`. Note that I have the `#10` to advance the simulator time
because if I don't do that, then I won't be able to see my outputs change
between loop iterations.

As an aside, you may be wondering why `i` is 5-bits, when I only iterate up to
15 (which only needs 4 bits). This is because my loop guard has to compare i to
16, a number that cannot be represented in 4 bits. If I set `i` to be only
4-bits and keep the same loop guard, *then I will infinitely loop!*

Let's now consider another example
```systemverilog
logic [4:0] i;
initial begin
    for (i = 5'd0; i < 5'd16; i++)
        #10 a[3:0] = i[3:0];
        if (out != expected_out)
            $display("oops!");
end
```
Now this is where we run into a problem. What I *want* to happen is 1) set `a`
to be the value of `i` in that iteration, then *in the same iteration* 2) check
to see if `out` is the same as my expected value.  What *actually* happens is it
won't treat that `if` statement as part of my loop, so it'll run the loop to
completion first then do the check on the last value of the loop.

What we *really* want is
```systemverilog
logic [4:0] i;
initial begin
    for (i = 5'd0; i < 5'd16; i++) begin
        #10 a[3:0] = i[3:0];
        if (out != expected_out)
            $display("oops!");
    end
end
```

Which has the behavior I'm looking for.
