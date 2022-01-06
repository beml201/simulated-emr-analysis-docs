Quickstart
==========

.. _installation:

Installation
------------

simluated-emr-analysis can be installed through pip or conda:

.. code-block:: console

   (.venv) $ pip install simulated-emr-analysis

or

.. code-block:: console

   (.venv) $ conda install simulated-emr-analysis

.. _example_data:

Example Data
------------

The best way to start testing the package is using the example data provided, 
you can use ``emr_analysis.data.load_example()`` function:

================================
emr_analysis.data.load_example()
================================

returns a ``dict`` of the electronic medical record data that can be used for analysis

For example:

>>> import emr_analysis
>>> dfs = emr_analysis.data.load_example()

