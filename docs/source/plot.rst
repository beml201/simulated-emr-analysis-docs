emr_analysis.plot
=================

.. _IndSummary:

IndSummary *class*
------------------
Provides a summary of a specific patient as both text and a graph
set ``browser=True`` to open the interactive graphs of the patients lab values in a plotly server

**Parameters**
    *Init()*
        *dict* dfs:
            A dictionary created by the ``data.Loader()`` that contains all the relevant pandas dataframes for analysis
    *Call()*
        *str* patient_id:
            The ID of the patient whose data and summary should be returned
        *bool* browser:
            Defaults to ``False``
            If ``True`` will open a new window in the default browser of the user
            Will also return the resulting dictionary (see ***Returns***)
            If ``False`` will just return the resulting dictionary (see ***Returns***)
        *int* port:
            Defaults to 8050
            Changes the port for the Dash server to open in. Only works when ``browser=True``
            Does not check if port is already opening

**Returns**
    *dict*
        Returns a dictionary that contains the patients characteristics and some plots about their previous lab data

Example:

>>> import emr_analysis as emr
>>> individuals = emr.plot.IndSummary(dfs)
>>> patient1 = individuals('1A8791E3-A61C-455A-8DEE-763EB90C9B2C')
>>> print(patient1['info']
>>> patient1['plots']['CBC'].show()

.. _QuickSearch:

QuickSearch *class*
-------------------

***QuickSearch*** is a utility to quickly search through the EMR dataframes passed into it.
It will open a new browser window in which you can quickly adjust parameters to search through the dataframes.
Parameters include: *sex, year of birth, race, marital status, language, number of asmissions and known primary diagnosis codes*


**Parameters**
    *Init()*
        *dict* dfs:
            A dictionary created by the ``data.Loader()`` that contains all the relevant pandas dataframes for analysis
    *Call()*
        *int* port:
            Defaults to 8050
            Changes the port for the Dash server to open in.
            Does not check if port is already opening

**Returns**
    *None*

Example:

>>> import emr_analysis as emr
>>> search = emr.plot.QuickSearch(dfs)
>>> search()