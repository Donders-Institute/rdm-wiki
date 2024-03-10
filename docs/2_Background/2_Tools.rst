Data Transfer Tools
******

At the :bdg-danger:`DCCN`, we support four data transfer tools which, together, 

.. _Cyberduck: http://cyberduck.io
.. _Repocli: https://github.com/Donders-Institute/dr-tools/tree/main/cmd/repocli
.. _Stager: https://stager.dccn.nl
.. _Uploader: https://uploader.dccn.nl

.. table::
   :widths: auto

   +-------------------+-----------------+-----------------+--------------------------+--------------------------------+
   |                   | `Cyberduck`_    | `Repocli`_      |  `Stager`_               | `Uploader`_                    |
   +===================+=================+=================+==========================+================================+
   | *User Interface*  | Graphical       | Comamnd-Line    |  Web                     | Web                            |
   +-------------------+-----------------+-----------------+--------------------------+--------------------------------+
   | *Transfer Routes* | | local ⟷ RDR  | | Local ⟷ RDR  |  Project Storage ⟷ RDR  | Local → Project Storage        |
   |                   | local ⟷ HPC    | | HPC ⟷ RDR    |                          | Local → RDR                    |
   +-------------------+-----------------+-----------------+--------------------------+--------------------------------+
   | | *Access*        |                 |                 | | DCCN Trigon network    | | DCCN Trigon network          |
   | | *Restriction*   |                 |                 | | or eduVPN              | | or eduVPN                    |
   +-------------------+-----------------+-----------------+--------------------------+--------------------------------+
   | *OS Support*      | | Windows       | | Windows       | | Windows                | | Windows                      |
   |                   | | MacOSX        | | MacOSX        | | MacOSX                 | | MacOSX                       |
   |                   |                 | | Linux         | | Linux                  | | Linux                        |
   +-------------------+-----------------+-----------------+--------------------------+--------------------------------+
   | *Key Feature*     | Ease-of-use     | Scriptable      | Efficient                | Automatic Data Organization    |
   +-------------------+-----------------+-----------------+--------------------------+--------------------------------+
