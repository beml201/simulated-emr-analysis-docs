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

.. code-block:: console

>>> import emr_analysis as emr
>>> loader = emr.data.Loader()
>>> dfs = loader('example')

================================
emr_analysis.data.load_example()
================================

returns a ``dict`` of the electronic medical record data that can be used for analysis

For example:

>>> import emr_analysis
>>> dfs = emr_analysis.data.load_example()

