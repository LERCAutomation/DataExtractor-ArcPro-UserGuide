*******
Preface
*******

The most up to date version of this documentation can be found in **HTML** and **PDF** form on `ReadTheDocs <https://readthedocs.org/projects/dataextractor-arcpro-userguide/>`_.

.. index::
	single: Recommended user knowledge

Recommended User Knowledge
==========================

Users
-----

This user guide assumes that users of the ArcGIS Pro version of theDataExtractor tool have:

* General IT experience including the use of Microsoft Windows.
* Experience in the use of the GIS application ArcGIS Pro supported by this version of the tool.
* An understanding of the datasets that are used by the DataExtractor tool.


Administrators
--------------
It is recommended that a person within each organisation is designated as the tool and database administrator. This person should:

* Have an understanding and experience of IT systems management.
* Understand relational database structures.
* Be an expert user of SQL Server.
* Have certified training or equivalent experience in advanced features of the relevant GIS software.
* Become familiar with how the DataExtractor tool has been configured within the organisation.
* Have a good understanding of XML.

.. raw:: latex

   \newpage

.. index::
	single: Reading guide

Reading Guide
=============

This Preface explains a little about the DataExtractor tool, the community of people who develop and use it, and the licensing conditions for using and distributing it. It also explains how to read this user guide.

:doc:`../introduction/introduction` \ explains why the DataExtractor tool is needed, what it does and where it comes from.

:doc:`Anatomy of data extraction <../anatomy/anatomy>` \ is a brief outline of the key stages of data extraction, and how the DataExtractor tool addresses these.

:doc:`Setting up the tool <../setup/setup>` \ describes how to install and set up the DataExtractor tool.

:doc:`Running the tool <../execute/execute>` \ describes how to run the DataExtractor tool.

:doc:`FAQs <../faq/faq>` \ has a list of commonly asked questions and their answers.

:doc:`../appendix/appendix` \ contains an example of an XML configuration file for ArcGIS Pro and contains a copy of the GNU Free Documentation License v1.3 covering this guide.


.. index::
	single: Licensing

Licensing
=========

The code for the DataExtractor tool is 'open source' and is released under the `GNU General Public License (GPL) v3 <http://www.gnu.org/licenses/gpl.html>`_. Users are free to install it on as many computers as they like, and to redistribute it according to the GPLv3 license.

This guide is released under the `GNU Free Documentation License (FDL) v1.3 <http://www.gnu.org/licenses/fdl.html>`_. Permission is granted to copy, distribute and/or modify this document under the terms of the license.

Please remember, however, that the tool cost a lot of money to develop and still requires further development and ongoing support. Hence any contributions towards costs would be gratefully received. Enquiries can be made via email to `Andy Foy <mailto:andy@andyfoyconsulting.co.uk>`_.


.. index::
	single: Useful links

Useful links
============

Related community links:

* Administrators (`Releases <https://github.com/LERCAutomation/DataExtractor-ArcPro/releases/>`_) - Release notes and installers for ArcGIS Pro.
* Developers (`Source code <https://github.com/LERCAutomation/DataExtractor-ArcPro>`_) - Source code for the ArcGIS Pro version of the Data Extractor Tool.
* Issues (`Issues <https://github.com/LERCAutomation/DataExtractor-ArcPro/issues>`_) - Details of known issues and existing change requests.


.. raw:: latex

	\newpage

.. index::
	single: Acknowledgements

Acknowledgements
================

The DataExtractor tool was developed with funding from:

* Greenspace Information for Greater London CIC
* Thames Valley Environmental Records Centre
* Sussex Biodiversity Records Centre
* Surrey Biodiversity Information Centre

The DataExtractor user guide was developed with additional funding from:
* Dorset Environmental Records Centre
* Isle of Wight Local Records Centre

Many thanks are due to all the LERCs and their staff who have, and continue to, fund and contribute towards the DataExtractor tool.


.. raw:: latex

	\newpage

.. index::
	single: Conventions used in this user guide

Conventions used in this user guide
===================================

The following typographical conventions are used in this manual:

:kbd:`Ctrl-A`
	Indicates a key, or combination of keys, to press.

**Commit**
	Indicates a label, button or anything that appears in user interfaces.

**Tools... --> About**
	Indicates a menu choice, or a combination of menu choices, tab selections or GUI buttons.

:file:`D:\\DataTools\\DataExtractor\\Config`
	Indicates a filename or directory name.

.. tip::
	Tips can help save time or provide shortcuts.

.. seealso::
	References and/or links to other sections of this guide.

.. note::
	Notes explain things in more detail or highlight important points.

.. caution::
	Warnings where users should pay attention.

