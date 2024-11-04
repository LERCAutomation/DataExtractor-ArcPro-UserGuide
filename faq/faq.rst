.. index::
	single: FAQ
	see: Frequently asked questions; FAQ

**************************
Frequently Asked Questions
**************************

This is a list of Frequently Asked Questions about the Data Extractor tool. Feel free to suggest new entries!

General questions
=================

**How do I get a copy of the tool?**

	The source code as well as the installer setups can be downloaded from GitHub (`MapInfo <https://github.com/LERCAutomation/DataExtractor-MapInfo/releases>`_ or `ArcMap <https://github.com/LERCAutomation/DataExtractor-ArcObjects/releases>`_ or `ArcGIS Pro <https://github.com/LERCAutomation/DataExtractor-ArcPro/releases>`_). Please ensure that you use the correct configuration file, examples copy of which are also included with the releases.

**Can several people use the tool at the same time?**

	Any number of users can use the tool simultaneously if they have a copy of the tool loaded in their own copy of GIS. The tool uses the data layers that are loaded in GIS in a read-only fashion, so there is no limit to the number of users of the tool. The stored procedures that are run store their temporary results in tables that carry the login name of the user, so as long as each user has a unique login ID no conflicts should arise. However, where results are written to a central (network) location, and the extraction is run for the same partner, conflicts may occur.

**Does the tool work with QGIS?**

	Currently only ArcMap Desktop, ArcGIS Pro and MapInfo implementations of the tool exist. However, if funding was available the tool could be adapted to also support QGIS.

Operating the tool
==================

**One of the data tables I want to use isn't showing in the form. How do I get it to show up?**

	This issue can arise in several ways:

	- The layer isn't loaded in your GIS active map. In this case, a :ref:`message will pop up <figlaunchwarning>` before the form is displayed informing you the layer isn't loaded. Add the layer to GIS and reload the profile the tool and the problem should be resolved.
	- The layer isn't listed in the XML configuration document. Please refer to the :doc:`Setting up the tool <../setup/setup>` section and add it as a map layer.
	- The layer is in the GIS active map, and it is listed in the configuration document, but the :ref:`LayerName <LayerName>` is spelled incorrectly. Note that the name must follow the exact format of the name of the layer in the active map.

**The partner I want to extract data for is not shown in the form. How do I get the name to show up?**

	This issue can arise in two ways:

	- The partner boundary polygon and attributes do not exist in the partner boundary GIS layer. Add it to the layer and reload the profile.
	- The partner's status in not **Active**. Change the value of the partner's status in the :ref:`ActiveColumn <activecolumn>` to ``Y`` and then reload the profile.

**The tool is not extracting the expected data for the partner**

	This issue will arise if the names of files in the :ref:`SQLFiles` column and/or :ref:`MapFiles>` column are not correct. Check that the names match the node names in the XML configuration file. Alternatively, check the :ref:`FormatColumn <FormatColumn>` and the :ref:`ExportColumn <ExportColumn>` to ensure the correct format of data is requested.


Tool issues
===========

**How do I report a new bug or propose a change in the tool?**

	Please report any issues or propose any new changes to `Andy Foy <mailto:andy@andyfoyconsulting.co.uk>`_. 