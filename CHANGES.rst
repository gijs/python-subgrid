Changelog of python-subgrid
===================================================


0.3 (unreleased)
----------------

- Added ``update_testcases.sh`` script for checking out the testcases that are
  needed for our functional tests.

- Started documentation on Fortran variables that you can call
  directly. All variables are documented (as undocumented variables
  raise a ``NotDocumentedError`` exception).

- Added a status page to the documentation with the svn and github
  locations and so on.

- Updated the build instructions, including hint to use the
  now-available ubuntu packages.

- Fixed library search order: specific wins over generic
  (=``/usr/lib``).

- Moved to github. Github pull requests are quite essential now for
  proper development. https://github.com/nens/python-subgrid . Mail
  Reinout for access if needed.

- Added roadmap document (in the sphinx docs in ``doc/``) that
  describes the main structure and future roadmap of this library.


0.2 (2013-09-23)
----------------

- Made a branch off an older stable version to create a 0.2 release.
  This is the "svn revision 714" version that was/is used on the server.

- The fortran library can be loaded through a "with" context manager now. The
  previous version loaded it upon importing the ``wrapper.py`` file, handling
  everything on the main module level.

  The current approach is cleaner and takes care of startup/shutdown code and
  model initialization/cleanup automatically. The latter depends on the
  fortran cleanup code to function well, which at the moment is not the case
  yet.

- The context manager behaviour is now also available with simple
  ``start()``/``stop()`` methods so that it can be used on the webserver where
  there's no single block-within-a-``with``-statement.

- Big documentation update. Sphinx documentation added (currently
  automatically rendered to http://jenkins.3di.lizard.net/doc/). Docstrings
  everywhere.


0.1 (2013-06-04)
----------------

- Refactored the wrapper to make the code cleaner and more testable.

- If the models aren't available, the functional model tests are skipped. This
  makes for quicker tests if you want to test just the internal unittests.

- Modified library loading routine to automatically look in a couple of
  standard locations, amongst them ``/opt/3di/``.

- Added code from the previous ``python_wrapper`` directory.

- Initial project structure created with nensskel 1.33.dev0.
