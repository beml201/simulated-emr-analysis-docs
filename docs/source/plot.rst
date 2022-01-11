emr_analysis.plot
=================

.. _IndSummary:

IndSummary
----------

***Parameters***
~~~~~~~~~~~~~~~~
**Init**

    dict *dfs*:
        A dictionary created by the ```data.Loader()``` that contains all the relevant pandas dataframes for analysis

**Call**

    str *patient_id*:
        The ID of the patient whose data and summary should be returned

    bool *browser*:
        *Defaults to "False"*
        If ``True`` will open a new window in the default browser of the user
        Will also return the resulting dictionary (see *Returns*)
        If ``False``will just return the resulting dictionary (see *Returns*)

    int *port*:
        * Defaults to "8050"*
        Changes the port for the Dash server to open in. Only works when ``browser=True```
        Does not check if port is already opening


***Returns***
~~~~~~~~~~~~~
    *dict*
        Returns a dictionary that containts the patients characteristics and some plots about their previous lab data

Example:

.. code-block:: console

>>> import emr_analysis as em
>>> individuals = emr.plot.IndSummary(dfs)
>>> patient1 = individuals('1A8791E3-A61C-455A-8DEE-763EB90C9B2C')
>>> print(patient1['info']
>>> patient1['plots']['CBC'].show()

Provides a summary of a specific patient as both text and a graph
set ``browser=True`` to open the interactive graphs of the patients lab values in a plotly server

.. _QuickSearch:

QuickSearch
-----------

A quick filter system that can help users find specific patients using known characteristics