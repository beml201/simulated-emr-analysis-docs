Quickstart
==========

.. _installation:

Installation
------------

simluated-emr-analysis can curently be installed through test-pypi:

.. code-block:: console

   (.venv) $ pip install --extra-index-url https://test.pypi.org/simple/ emr-analysis

.. _example_data:

Usage
-----

The best way to start testing the package is using the example data provided, 
you can use ``emr_analysis.data.Loader()`` to load the example files:

>>> import emr_analysis as emr
>>> loader = emr.data.Loader()
>>> dfs = loader('example')

Once that's done, you should be able to get out summary information from your dataset:

>>> summary = emr.summary.SummaryInformation(dfs)
>>> plot = summ_info.admissions_plot()
>>> plot[0].show()

If you want individual summary information, that can be done using:

>>> individuals = emr.plot.IndSummary(dfs)
>>> patient1 = individuals('1A8791E3-A61C-455A-8DEE-763EB90C9B2C', browser=True)

If you need help finding a patient ID, use *QuickSearch* in the :doc:`plot` module to help you.