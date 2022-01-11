Quickstart
==========

.. _installation:

Installation
------------

simluated-emr-analysis can curently be installed through test-pypi:

.. code-block:: console

   (.venv) $ pip install --extra-index-url https://test.pypi.org/simple/ emr-analysis

.. _example_data:

Example Data
------------

The best way to start testing the package is using the example data provided, 
you can use ``emr_analysis.data.Loader()`` to load the example files:

>>> import emr_analysis as emr
>>> loader = emr.data.Loader()
>>> dfs = loader('example')

