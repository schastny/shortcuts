##Vim
###How to Exit

Key  | Meaning
-----  | ----
:q[uit]  | Quit Vim. This fails when changes have been made.
:q[uit]!  | Quit without writing.
:cq[uit]  | Quit always, without writing.
:wq  | Write the current file and exit.
:wq!  | Write the current file and exit always.
:wq {file}  | Write to {file}. Exit if not editing the last
:wq! {file}  | Write to {file} and exit always.
:[range]wq[!] [file]  | Same as above, but only write the lines in [range].
ZZ  | Write current file, if modified, and exit.
ZQ  | Quit current file and exit (same as ":q!").
