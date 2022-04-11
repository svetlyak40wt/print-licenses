# Print licenses used by the given project and its dependencies

Install with Quicklisp:

    (ql:quickload "print-licenses")

Note that in order to do this the project must be `quickload`ed, so you might
want to do this in a separate Lisp image if you don't want to clutter your
current one.


If the project does not specify its license in its ASDF system definition it
will be listed as 'Unspecified'.  You should manually figure out what license
it uses (and maybe send a pull request).

Example:

~~~lisp
  (print-licenses 'fast-io)
  =>
  alexandria           | Public Domain / 0-clause MIT
  babel                | MIT
  cffi                 | MIT
  cffi-grovel          | MIT
  cffi-toolchain       | MIT
  fast-io              | NewBSD
  static-vectors       | MIT
  trivial-features     | MIT
  trivial-gray-streams | MIT
  uiop                 | Unspecified
~~~

Or you might want to group systems by their license:

~~~lisp
  (print-licenses :fast-io
                  :group-by-license t)
  =>
  MIT
    babel, cffi, cffi-grovel, cffi-toolchain, fast-io, static-vectors, trivial-features, trivial-gray-streams

  Public Domain / 0-clause MIT
    alexandria

  Unspecified
    asdf, uiop
~~~

## Credit

Code entirely taken from
[**@sjl**'s utilities](https://github.com/sjl/cl-losh/blob/master/losh.lisp),
the original snippet to build the license tree coming from a
**@dk_jackdaniel**'s [snippet](http://paste.lisp.org/display/327154).

MIT.
