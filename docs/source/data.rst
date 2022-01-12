emr_analysis.data
=================

.. _Loader:

data.Loader
-----------

*class* data.Loader()

Loads data from a text or zip file, that match the supported EMR content type patterns, for both filename & data header:

+--------------+-------------------------------------------------------+----------------------------------------------------------------------------+
|              |                                                   Patterns                                                                         |
| Content type +-------------------------------------------------------+----------------------------------------------------------------------------+
|              | Filename                                              | Header                                                                     |
+--------------+-------------------------------------------------------+----------------------------------------------------------------------------+
| admissions   | ``^[Aa]dmissions[Cc]ore.+\.[Tt][Xx][Tt]``             | ``^[Pp]atient[Ii][Dd].+[Aa]dmission[Ss]tart[Dd]ate.*``                     |
+--------------+-------------------------------------------------------+----------------------------------------------------------------------------+
| diagnosis    | ``^[Aa]dmissions[Dd]iagnoses[Cc]ore.+\.[Tt][Xx][Tt]`` | ``^[Pp]atient[Ii][Dd].+[Dd]iagnosis[Cc]ode.*``                             |
+--------------+-------------------------------------------------------+----------------------------------------------------------------------------+
| labs         | ``^[Ll]abs[Cc]ore.+\.[Tt][Xx][Tt]``                   | ``^[Pp]atient[Ii][Dd].+[Ll]ab[Nn]ame.*``                                   |
+--------------+-------------------------------------------------------+----------------------------------------------------------------------------+
| patients     | ``^[Pp]atient[Cc]ore.+\.[Tt][Xx][Tt]``                | ``^[Pp]atient[Ii][Dd].+[Pp]atient(?:[Dd]ate[Oo]f[Bb]irth|[Dd][Oo][Bb]).*`` |
+--------------+-------------------------------------------------------+----------------------------------------------------------------------------+

Attributes
""""""""""

    *str* EXAMPLE_ZIP_PATH:
        Absolute path of the example zip file "100-Patients.zip".
    *str* EMR_FILE_ENC:
        File encoding of the text files in the example zip file.
    *str* LOAD_TYPES:
        Valid values for the "load_type" argument in the "__call__()" method.
    *str* EMR_FILE_TYPES:
        Valid file MIME types for the EMR data.
    *dict[str, dict[str, re.Pattern]]* EMR_PATTERNS:
        Dictionary with the content type as keys and filename/header patterns as values.

Methods
"""""""

.. ___call__:

__call__()
^^^^^^^^^^^^^^^^^

Entry point for the Loader object.

    **Parameters:**
        *str* load_type:
            Controls the type of input file loading. Can only be one of ``'example'``, ``'text'`` or ``'zip'``.
        *str* input_file_path:
            Absolute path of the zip or text file to load. File type must match with 'load_type' argument value. Arguments 'append' and 'dialog' are ignored when this is set. Defaults to ``''``.
        *bool* append:
            Flag to control the return value. Only applicable when argument 'load_type' is 'text'. Defaults to ``False``.
        *bool* dialog:
            Flag to control whether to use a Tkinter dialog box to load the file. Defaults to ``False``.

    **Returns:**
        *dict[str, pandas.DataFrame]* OR *list[tuple[str, pandas.DataFrame]]]*:
            Returns either: (1) a list containing a single tuple of content type and DataFrame, or (2) a dictionary with content type as keys and DataFrame as values.

Examples:
"""""""

**Initialisation:**

>>> import emr_analysis as emr
>>> loader = emr.data.Loader()

1. **Loading the example zip file:**

>>> dfs = loader('example')

2. **Loading a custom zip file:**

>>> custom_zip = '/path/to/custom_zipfile.zip'
>>> dfs = loader('zip', input_file_path = custom_zip)

OR

>>> dfs = loader('zip', dialog = True)

which will create a Tkinter file dialog box for the user to load the zip file.

OR

>>> dfs = loader('zip', dialog = False)

which will prompt the user to enter the path to the zip file.

3. **Loading a custom text file:**

**Note:** Both filename and data header must match any one of the supported patterns given above.

>>> custom_text = '/path/to/AdmissionsCore_xyz.txt'
>>> dfs = loader('text', input_file_path = custom_text, append = False)

which returns a dictionary of content type and data.

OR

>>> custom_text = '/path/to/AdmissionsCore_xyz.txt'
>>> dfs = {}
>>> dfs.update(loader('text', input_file_path = custom_text, append = True))

which returns a list with a single tuple of content type and data.

OR

>>> dfs = loader('text', append = False, dialog = True)

which will create a Tkinter file dialog box for the user to load the text file, then return a dictionary of content type and data.

OR

>>> dfs = loader('text', append = False, dialog = False)

which will prompt the user to enter the path to the text file, then return a dictionary of content type and data.

OR

>>> dfs = {}
>>> dfs.update(loader('text', append = True, dialog = True))

which will create a Tkinter file dialog box for the user to load the text file, then return a list with a single tuple of content type and data.

OR

>>> dfs = {}
>>> dfs.update(loader('text', append = True, dialog = False))

which will prompt the user to enter the path to the text file, then return a list with a single tuple of content type and data.
