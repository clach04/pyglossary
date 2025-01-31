Configuration Parameters
------------------------
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| Name                         | Command Flags         | Type  | Default       | Comment                                                 |
+==============================+=======================+=======+===============+=========================================================+
| ``log_time``                 | | ``--log-time``      | bool  | ``false``     | Show date and time in logs                              |
|                              | | ``--no-log-time``   |       |               |                                                         |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``cleanup``                  | | ``--cleanup``       | bool  | ``true``      | Cleanup cache or temporary files after conversion       |
|                              | | ``--no-cleanup``    |       |               |                                                         |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``auto_sqlite``              |                       | bool  | ``true``      | Auto-enable ``--sqlite`` to limit RAM usage when direct |
|                              |                       |       |               | mode is not possible. Can override with ``--no-sqlite`` |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``lower``                    | | ``--lower``         | bool  | ``false``     | Lowercase words before writing                          |
|                              | | ``--no-lower``      |       |               |                                                         |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``utf8_check``               | | ``--utf8-check``    | bool  | ``false``     | Ensure entries contain valid UTF-8 strings              |
|                              | | ``--no-utf8-check`` |       |               |                                                         |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``enable_alts``              | | ``--alts``          | bool  | ``true``      | Enable alternates                                       |
|                              | | ``--no-alts``       |       |               |                                                         |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``skip_resources``           | ``--skip-resources``  | bool  | ``false``     | Skip resources (images, audio, etc)                     |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``rtl``                      | ``--rtl``             | bool  | ``false``     | Mark all definitions as Right-To-Left                   |
|                              |                       |       |               | (definitions must be HTML)                              |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``remove_html``              | ``--remove-html``     | str   | ``""``        | Remove given html tags (comma-separated)                |
|                              |                       |       |               | from definitions                                        |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``remove_html_all``          | ``--remove-html-all`` | bool  | ``false``     | Remove all html tags from definitions                   |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``normalize_html``           | ``--normalize-html``  | bool  | ``false``     | Lowercase and normalize html tags in definitions        |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``save_info_json``           | ``--info``            | bool  | ``false``     | Save glossary info as json file with .info extension    |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``color.enable.cmd.unix``    | ``--no-color``        | bool  | ``true``      | Enable colors in Linux/Unix command line                |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``color.enable.cmd.windows`` | ``--no-color``        | bool  | ``false``     | Enable colors in Windows command line                   |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``color.cmd.critical``       |                       | int   | ``196``       | | Color code for critical errors in command line        |
|                              |                       |       | |image0|      | | See `term_colors.md <./term_colors.md/>`_             |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``color.cmd.error``          |                       | int   | ``1``         | | Color code for errors in command line                 |
|                              |                       |       | |image1|      | | See `term_colors.md <./term_colors.md/>`_             |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``color.cmd.warning``        |                       | int   | ``208``       | | Color code for warnings in command line               |
|                              |                       |       | |image2|      | | See `term_colors.md <./term_colors.md/>`_             |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``ui_autoSetFormat``         |                       | bool  | ``true``      |                                                         |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``reverse_matchWord``        |                       | bool  | ``true``      |                                                         |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``reverse_showRel``          |                       | str   | ``"Percent"`` |                                                         |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``reverse_saveStep``         |                       | int   | ``1000``      |                                                         |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``reverse_minRel``           |                       | float | ``0.3``       |                                                         |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``reverse_maxNum``           |                       | int   | ``-1``        |                                                         |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+
| ``reverse_includeDefs``      |                       | bool  | ``false``     |                                                         |
+------------------------------+-----------------------+-------+---------------+---------------------------------------------------------+

Configuration Files
-------------------

The default configuration values are stored in `config.json <./../config.json/>`_
file in source/installation directory.

The user configuration file - if exists - will override default configuration
values. The location of this file depends on the operating system:

- Linux or BSD: ``~/.pyglossary/config.json``
- Mac: ``~/Library/Preferences/PyGlossary/config.json``
- Windows: ``C:\Users\USERNAME\AppData\Roaming\PyGlossary\config.json``

Using as library
----------------

When you use PyGlossary as a library, neither of ``config.json`` files are
loaded. So if you want to change the config, you should set ``glos.config``
property (which you can do only once for each instance of ``Glossary``).
For example:

.. code:: python

    glos = Glossary()
    glos.config = {
        "lower": True,
    }


.. |image0| image:: https://via.placeholder.com/20/ff0000/000000?text=+
.. |image1| image:: https://via.placeholder.com/20/aa0000/000000?text=+
.. |image2| image:: https://via.placeholder.com/20/ff8700/000000?text=+