Read me TXT

http://stackoverflow.com/questions/5456011/how-to-compile-lex-yacc-files-on-windows/5545924#5545924

As for today (2018-10-19) you will need the lastest versions of:

* flex-2.5.4a-1.exe (http://gnuwin32.sourceforge.net/packages/flex.htm)
* flex version 2.6.4 (linux opensuse)
* bison-2.4.1-setup.exe (http://gnuwin32.sourceforge.net/packages/bison.htm)
* bison version 3.0.4 (linux opensuse)

    After that, do a full install in a directory of your preference (default to C:\Program Files (x86)\GnuWin32). 
I suggest C:\GnuWin32 , because here bison had some problems with spaces in directory names.

    Also, consider installing Dev-CPP in the default directory (C:\Dev-Cpp)
(http://www.bloodshed.net/dev/devcpp.html)

    After that, set the PATH variable to include the bin directories of gcc (in C:\Dev-Cpp\bin) and flex\bison (in C:\GnuWin32\bin). 
To do that, copy this: ;C:\Dev-Cpp\bin;C:\GnuWin32\bin and append it to the end of the PATH variable, defined in the place show by this figure:
    step-by-step to set PATH variable under Win-7.
    If the figure is not in good resolution, you can see a step-by-step here. 
(http://geekswithblogs.net/renso/archive/2009/10/21/how-to-set-the-windows-path-in-windows-7.aspx)

    Open a prompt, cd to the directory where your ".l" and ".y" are, and compile them with:
        flex hello.l
        bison -dy hello.y
        gcc lex.yy.c y.tab.c -o hello.exe

Commands to create lexical analyzer, parser and executable.

You will be able to run the program. I made the sources for a simple test (the infamous Hello World).


