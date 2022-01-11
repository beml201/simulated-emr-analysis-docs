emr_analysis.summ
=================

.. _SummaryInformation:

SummaryPlot
-----------
Provides a matplotlib.plt bar chart plot of the number of admissions in each year. By default ``start_date=None`` and ``to_date=None`` which sets the start and end dates of the plot to be the minimum and maximum dates in the dataset.

.. _admission_time_diff_summary:

admission_time_diff_summary
---------------------------
Constructs a multiple matplotlib.Figure.figure containg a single histogram plot of the frequencies of time spent in admission.

.. _lab_summary:

lab_summary
-----------
Constructs a pandas dataframe containing summary statistics for each lab test's values including; count, mean, standard devation, minimum value, 25% percentile, 50% percentile, 75% percentile, maximum value.

.. _lab_plot:

lab_plot
--------
Constructs multiple matplotlib.Figure.figure's containing histograms for the labvalues of each labtype, seperated by the general area of the lab type (e.g. cbc, urinary, metabolic...), that are contained in a dictionary.


.. _personal_plot:

personal_plot
-------------
Constructs a matplotlib.Figure.figure containing bar charts that display the counts for patient gender, race, marital status and language.
