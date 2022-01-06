emr_analysis.data
=================

load_example
------------
Function loads the example data provided by emrbots.org in a dictionary format

The loaded datasets are accessible using the keys wich can be found using ``emr_analysis.data.load_example().keys()``.
The keys are:

+-------------------------------------------+
|``"AdmissionsDiagnosesCorePopulatedTable"``|
+-------------------------------------------+
|``"AdmissionsCorePopulatedTable"``         |
+-------------------------------------------+
|``"LabsCorePopulatedTable"``               |
+-------------------------------------------+
|``"PatientCorePopulatedTable"``            |
+-------------------------------------------+

User data will be able to be formatted into the same form as this for use with the package at a later date

load
----
Temporary function