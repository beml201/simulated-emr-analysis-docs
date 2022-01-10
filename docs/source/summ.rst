emr_analysis.summ
=================

.. _SummaryInformation:

SummaryPlot
-----------
Provides a matplotlib.plt bar chart plot of the number of admissions in each year. By default ``start_date=None`` and ``to_date=None`` which sets the start and end dates of the plot to be the minimum and maximum dates in the dataset.

.. _admission_time_diff_summary:

admission_time_diff_summary
---------------------------

Provides a matplotlib.plt histogram plot of the frequency of admission times in the dataset.

.. _lab_summary:

lab_summary
-----------
Provides a table containing summary statistics for each lab test's values including; count, mean, standard devation, minimum value, 25% percentile, 50% percentile, 75% percentile, maximum value.

.. _lab_plot:

lab_plot
--------
Provides a dictionary containing matplotlib.plt histogram plots for each lab type (e.g. cbc, urinary, metabolic...).


.. _personal_plot:

personal_plot
-------------
Provides a set of matplotlib.plt bar chart plots for patient's gender, race, marital status and language.
