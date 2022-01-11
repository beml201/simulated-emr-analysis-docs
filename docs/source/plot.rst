emr_analysis.plot
=================

.. _IndSummary:

plot.IndSummary
---------------
*class* plot.IndSummary(dfs = None)

***IndSummary*** provides a summary of a specific patient. It returns a dictionary of a pandas dataframe of characteristics, 
with key= ``'info'`` , and a dictionary of plots, with key= ``'plots'`` .
To view the plots, ``.show()`` should be used to open them in a new browser page.
See the example for how to use.
Set ``browser=True`` to open the summary of the patient in a local webpage.
Plots output is done in plotly and can be interacted with, including tooltips and zooming.

**Parameters**
    *__init__(dfs: dict)*
        *dict* dfs:
            A dictionary created by the ``data.Loader()`` that contains all the relevant pandas dataframes for analysis.
    *__call__(patient_id: str, browser:bool, port:int)*
        *str* patient_id:
            The ID of the patient whose data and summary should be returned
        *bool* browser:
            Defaults to ``False``.
            If ``True`` will open a new window in the default browser of the user.
            Will also return the resulting dictionary (see ***Returns***).
            If ``False`` will just return the resulting dictionary (see ***Returns***).
        *int* port:
            Defaults to 8050.
            Changes the port for the Dash server to open in. Only works when ``browser=True``.
            Does not check if port is already open.

**Returns**
    *dict*
        A dictionary that contains the patients characteristics in ``['info']`` 
        and some plots about their previous lab data in ``['plots']``.
        *plots* is a dictionary of the different lab values of the data.
        There are three main lab values measured: *CBC, METABOLIC or URINALYSIS*.
        See the example for how to use.

Example:

>>> import emr_analysis as emr
>>> # Load the dataframes into IndSummary
>>> individuals = emr.plot.IndSummary(dfs)
>>> # Request a specific individual
>>> patient1 = individuals('1A8791E3-A61C-455A-8DEE-763EB90C9B2C')
>>> # Print the pandas dataframe
>>> print(patient1['info']
>>> # Show the plot (.show() will open the plot in a new browser window)
>>> patient1['plots']['CBC'].show()

.. _QuickSearch:

plot.QuickSearch
----------------
*class* plot.QuickSearch(dfs = None)

***QuickSearch*** is a utility to quickly search through the EMR dataframes passed into it.
This is especially useful when trying to get a better understanding of the data or when trying to look up a specific patients ID as the EMR data usually does not contain names.
It will open a new browser window in which you can quickly adjust parameters to search through the dataframes.
Parameters include: *sex, year of birth, race, marital status, language, number of admissions and known primary diagnosis codes*.
QuickSearch does not currently have functionality 

**Parameters**
    *__init__(dfs: dict)*
        *dict* dfs:
            A dictionary created by the ``data.Loader()`` that contains all the relevant pandas dataframes for analysis.
    *__call__(port: int)*
        *int* port:
            Defaults to 8050
            Changes the port for the Dash server to open in.
            Does not check if port is already open.

**Returns**
    *None*

Example:

>>> import emr_analysis as emr
>>> search = emr.plot.QuickSearch(dfs)
>>> search()