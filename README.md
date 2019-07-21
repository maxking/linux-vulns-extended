This repo captures the new vulnerabilities that I have studied, after I wrote
my MS thesis (which is [freely available][1])


Memory Corruption
=====================

Concurrently Use-After-Free
-------------------------------

This kind of vulnerability is caused by use-after-free(UAF) in code that
executes concurrently, mostly drivers. This [research paper from USENIX
2019][2] explores how these bugs can be detected with what they call "summary
based lockset analysis" (an advanced static analysis).

The basic summary is that they collect all possible functions that acquire a
lock and pair them with other functions which can execute concurrently with
that function, from the same and from a different driver using static
analysis. Then they finally compare the functions in those pairs for
use-after-free bugs. Read the paper for more details.




[1]: https://github.com/maxking/linux-vulnerabilities-10-years
[2]: https://www.usenix.org/system/files/atc19-bai.pdf
