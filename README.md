# Scroll your outputs without clutter

The motivation for this tool is very simple. In many cases tools produce
too much of diagnostic output which I do not care about. While producing
those floods of messages, some actually important lines (errors, warnings)
might be printed as well, but they quickly disappear from the view and
often from the terminal buffer if output has way too many lines.

You can pipe output of such tools into skroll and get only 5 lines
scrolling happily for you on the terminal.  If you would like to retain
some lines (e.g. errors, warnings) you can do so by using -m or -M flags
of the tool (run it with -h to see all options).

A very simple example use of the tool (with delay while printing each line):

    cat skroll | ./skroll -m 'ok *$' -M a -n 10 -s 0.01 -c -l -i

so you could see lines of the script scrolling while those which do not have
'a' in them, and those which end with 'ok' being printed permanently.

Disclaimer:

 most likely due to current use of printf inside and scroll ring being
 just a string, it wouldn't work correctly if output contains escaped
 sequences such as \n etc
