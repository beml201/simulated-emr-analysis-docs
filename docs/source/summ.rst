emr_analysis.summary
====================

.. _SummaryInformation:

summary.SummaryInformation
--------------------------
*class* summary.SummaryInformation(dfs=None)

Parameters
""""""""""
    *__init__(dfs: dict)*
        *dict* dfs:
            A dictionary created by the ``data.Loader()`` that contains all the relevant pandas dataframes for analysis.

Methods
"""""""

.. _admissions_plot:

admissions_plot()
^^^^^^^^^^^^^^^^^

   **Parameters**
     *str* from_date:
         *Defaults to* ``None``
         The date from which the plot will start from.
         If ``None`` the plot will start from the minimum date in the dataset.
     *str* to_date:
         *Defaults to* ``None``
         The date from which the plot will end at.
         If ``None`` the plot will end at the maximum date in the dataset.

   **Returns**
       *(fig, ax)*
           Returns a tuple that containts the matplotlib.figure.Figure and matplotlib.axes.Axes for the plot.

Example:

>>> import emr_analysis as emr
>>> summ_info = emr.summary.SummaryInformation(dfs)
>>> plot = summ_info.admissions_plot()
>>> plot[0].show()

Provides a time series graph of the number admitted patients in each year.


.. _admission_time_plot:

admission_time_plot()
^^^^^^^^^^^^^^^^^^^^^

   **Returns**
       *(fig, ax)*
           Returns a tuple that containts the matplotlib.figure.Figure and matplotlib.axes.Axes for the plot.

Example:

>>> import emr_analysis as emr
>>> summ_info = emr.summary.SummaryInformation(dfs)
>>> plot = summ_info.admission_time_plot()
>>> plot[0].show()

Provides a a histogram plot of the frequency of times spent in admission.


.. _lab_summary:

lab_summary()
^^^^^^^^^^^^^

   **Parameters**
     *str* from_date:
         *Defaults to* ``None``
         The date from which the plot will start from.
         If ``None`` the plot will start from the minimum date in the dataset.
     *str* to_date:
         *Defaults to* ``None``
         The date from which the plot will end at.
         If ``None`` the plot will end at the maximum date in the dataset.

   **Returns**
       *DataFrame*
           Returns a pandas.DataFrame

Example:

>>> import emr_analysis as emr
>>> summ_info = emr.summary.SummaryInformation(dfs)
>>> lab_stats = summ_info.lab_summary()
>>> lab_stats

Provides a table of summary statistics of lab values for each lab type including; count, mean, standard deviation, minimum value, quartiles, and maximum value.


.. _lab_plot:

lab_plot()
^^^^^^^^^^

   **Returns**
       *{str:(fig, ax),...}*
           Returns a dictionary that contains the matplotlib.figure.Figure and matplotlib.axes.Axes.

Example:

>>> import emr_analysis as emr
>>> summ_info = emr.summary.SummaryInformation(dfs)
>>> plots = summ_info.lab_plot()
>>> plots.keys()
>>> plots['CBC'][0].show()

Provides multiple figures containing histogram plots of lab values for every lab type, seperated into subcatagories.


.. _personal_plot:

personal_plot()
^^^^^^^^^^^^^^^

   **Returns**
       *(fig, ax)*
           Returns a tuple that containts the matplotlib.figure.Figure and matplotlib.axes.Axes for the plot.

Example:

>>> import emr_analysis as emr
>>> summ_info = emr.summary.SummaryInformation(dfs)
>>> plot = summ_info._personal_plot()
>>> plot[0].show()

Provides a figure containing bar chart plots for the count of patient gender, race, marital status and language.
