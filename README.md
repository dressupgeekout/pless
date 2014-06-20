# pless, the screen-oriented pager

Christian Koch -- cfkoch@sdf.lonestar.org

----

**pless** is a lot like less(1), except that pages NEVER overlap. If reading
the output of less(1) is like reading a long scroll, then **pless** reads
like a book.

Also, unlike less(1), **pless** has FAR fewer options. And this program is
written in Ruby (but it really shouldn't).


## Usage

**pless [-l lines_per_page] [file]**

By default, pless pages "at" every (N-1) lines, where N is the height of the
terminal. (The last line displays some status info.) You can force pless to
page at some arbitrary interval with the **-l** option.

You can navigate a document with the following keys. They're like less(1):

  - **h**, **p** -- previous page
  - **l**, **n** -- next page
  - **g** -- first page
  - **G** -- last page
  - **q** -- quit


NOTE. There's a TODO: If a file is not provided, then pless should read
from the standard input. Right now I can't figure out how reconcile
Curses' getch() function and reading the initial data from stdin. The best
workaround for now is to use a named pipe:

    $ mkfifo work
    $ /do/something/to a_file > work &
    $ pless work


## License (2-clause BSD-style)

Copyright (c) 2013, 2014 Christian Koch.
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

  - Redistributions of source code must retain the above copyright notice,
    this list of conditions and the following disclaimer.

  - Redistributions in binary form must reproduce the above copyright
    notice, this list of conditions and the following disclaimer in the
    documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.
