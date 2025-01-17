********
Appendix
********

.. index::
    single: Appendix
    single: Appendix; Change Log
    single: Change Log

.. _change_log:

Change Log
==========

**1.0.5**
(18th Jan 2025)

    * :guilabel:`Fixed` - Don't delete extract outputs incorrectly

**1.0.4**
(14th Jan 2025)

    * :guilabel:`Changed` - Remove XML variable 'ClearSubsetStoredProcedure'
    * :guilabel:`Changed` - Checkboxes styles now match ArcGIS Pro style
    * :guilabel:`Changed` - Standardise shared functions
    * :guilabel:`Fixed` - Apply default options for exclusion clause, use centroids and upload to server
    * :guilabel:`Fixed` - Correctly check output polygon record count

**1.0.3**
(6th Jan 2025)

    * :guilabel:`Fixed` - Ensure XML profiles are not repeated
    * :guilabel:`Fixed` - Replace hyphens in userid to avoid SQL error

**1.0.2**
(12th Dec 2024)

    * :guilabel:`Changed` - Standardise shared functions
    * :guilabel:`Fixed` - Ensure list of SQL tables is loaded
    * :guilabel:`Fixed` - Don't clear/reload form when attribute table is opened/closed

**1.0.1**
(29th Oct 2024)

    * :guilabel:`Improved` - Improve load performance
    * :guilabel:`Improved` - Increase progress reporting frequency
    * :guilabel:`Fixed` - Disable double-click on scroll bars in lists
    * :guilabel:`Fixed` - Handle empty output and export formats
    * :guilabel:`Fixed` - Ensure <Ctrl>A selects hidden items in lists

**1.0.0**
(28th Oct 2024)

    * Initial version


.. raw:: latex

   \newpage

.. index::
    single: Appendix; XML files
    single: XML files
    single: XML files; Example Tool XML file

.. _example_xml:

Example tool XML file
=====================

Below is an example of an XML profile that might be used to set up the Data Selector tool in ArcGIS Pro.
Note, many of the settings have been included for illustration only and it is up to each user or LERC to
ensure the system is configured to their requirements.

::

    <?xml version="1.0" encoding="utf-8"?>

    <!--
    WARNING: This file should be changed carefully and a backup should be
    taken before any changes so that they can be backed out.  Changed lines
    can also be commented out as below.
    -->

    <!--
    This config file contains all the variables used by the DataSearches
    ArcGIS Add-in tool.

    The 'configuration' node is the 'root' node and signifies the start of the
    contents of the configuration file.

    The 'InitialConfig' node contains the nodes relating to the initial setup of the tool.

    Note a detailed XML profile file must also be set up in order for the tool to run.

    -->

    <configuration>
    <InitialConfig>
        <!-- Are we allowing the user to choose their own configuration file? Yes/No -->
        <ChooseXML>
            <value>Yes</value>
        </ChooseXML>

        <!-- What is the default XML file called? If blank, the system looks for DefaultProfile.xml -->
        <DefaultProfile>
            <value></value>
        </DefaultProfile>
        
        <!-- The URL of the online user guide -->
        <HelpURL>
            <value>https://dataextractor-userguide.readthedocs.io/en/latest/</value>
        </HelpURL>
    </InitialConfig>
    </configuration>


.. raw:: latex

   \newpage

.. index::
    single: XML files; Example user XML profile

Example user XML profile
========================
                                                                                                     
Below is an example of an XML profile that might be used to set up the Data Extractor tool in ArcGIS Pro.
Note, many of the settings have been included for illustration only and it is up to each user or LERC to ensure the system is configured to their requirements.

::

    <?xml version="1.0" encoding="utf-8"?>

    <!--
    WARNING: This file should be changed carefully and a backup should be
    taken before any changes so that they can be backed out.  Changed lines
    can also be commented out as below.
    -->

    <!--
    This config file contains all the variables used by the DataExtractor
    ArcGIS Pro add-in.

    The 'configuration' node is the 'root' node and signifies the start of the
    contents of the configuration file.

    The 'DataExtractor' node contains all of the entries relating to the
    ArcGIS  Pro add-in variables.

    Each entry relates to a file, folder, table name, column name or SQL statement
    used by the ArcGIS Pro add-in to select and export GIS data for partners.
    -->

    <configuration>
    <DataExtractor>

      <!-- The existing file location where log files will be saved with output messages. -->
      <LogFilePath>
        <value>D:\Data Tools\Extractor\Logfiles</value>
      </LogFilePath>

      <!-- The location of the SDE file that specifies which SQL Server database to connect to. -->
      <SDEFile>
        <value>D:\Data Tools\DataExtractor\Config\NBNExtract.sde</value>
      </SDEFile>

      <!-- The stored procedure to execute spatial selection in SQL Server. -->
      <SpatialStoredProcedure>
        <value>AFSelectSppRecords</value>
      </SpatialStoredProcedure>

      <!-- The stored procedure to execute non-spatial subset selection in SQL Server. -->
      <SubsetStoredProcedure>
        <value>AFSelectSppSubset2</value>
      </SubsetStoredProcedure>

      <!-- The stored procedure to clear selection in SQL Server. -->
      <ClearSpatialStoredProcedure>
        <value>HLClearSpatialSubset</value>
      </ClearSpatialStoredProcedure>

      <!-- The stored procedure to clear selection in SQL Server. -->
      <ClearSubsetStoredProcedure>
        <value>HLClearSppSubset</value>
      </ClearSubsetStoredProcedure>

      <!-- The existing file location under which all partner sub-folders will be created -->
      <DefaultPath>
        <value>D:\Data Tools\Extractor\Extracts</value>
      </DefaultPath>

      <!-- The output sub-folder in which each partner's file will be created. -->
      <PartnerFolder>
        <value>%partner%_DataExchange_%qq%_%ffff%</value>
      </PartnerFolder>

      <!-- The output filegeodatabase into which GDB files will be saved. -->
      <GDBName>
        <value>GiGL_DataExchange_%qq%_%ffff%</value>
      </GDBName>

      <!-- The output sub-folder into which ArcGIS files will be saved. -->
      <ArcGISFolder>
        <value>ArcGIS</value>
      </ArcGISFolder>

      <!-- The output sub-folder into which CSV files will be saved. -->
      <CSVFolder>
        <value>CSV</value>
      </CSVFolder>

      <!-- The output sub-folder into which TXT files will be saved. -->
      <TXTFolder>
        <value></value>
      </TXTFolder>

      <!-- The schema used in the SQL Server database. -->
      <DatabaseSchema>
        <value>dbo</value>
      </DatabaseSchema>

      <!-- the Include wildcard for table names to list all the species tables in SQL Server that can be selected
           by the user to extract from. -->
      <IncludeWildcard>
        <value>Spp_PointPoly_*Names|Spp_Poly_*Names</value>
      </IncludeWildcard>

      <!-- the Exclude wildcard for table names that should NOT be used for species tables in SQL Server that can be selected
           by the user to extract from. -->
      <ExcludeWildcard>
        <value>Spp_*_*_*</value>
      </ExcludeWildcard>

      <!-- Whether the map processing should be paused during processing? -->
      <PauseMap>
        <value>Yes</value>
      </PauseMap>

      <!-- The name of the partner GIS layer in SQL Server used to select the records. -->
      <PartnerTable>
        <value>PartnerPolygons</value>
      </PartnerTable>

      <!-- The name of the column in the partner GIS layer containing the partner name passed to SQL
           Server by the tool to use as the partner's boundary for selecting the records. -->
      <PartnerColumn>
        <value>PartnerName</value>
      </PartnerColumn>

      <!-- The name of the column in the partner GIS layer containing the abbreviated name passed to
           SQL Server by the tool to use as the sub-folder name for the destination of extracted
           records. -->
      <ShortColumn>
        <value>ShortName</value>
      </ShortColumn>

      <!-- The name of the column in the partner GIS layer containing any notes text relating
           to the partner. -->
      <NotesColumn>
        <value>Notes</value>
      </NotesColumn>

      <!-- The name of the column in the partner GIS layer containing the Y/N flag to indicate
           if the partner is currently active.  Only active partners will available for proccessing. -->
      <ActiveColumn>
        <value>Active</value>
      </ActiveColumn>

      <!-- The name of the column in the partner GIS layer containing the GIS format required for
           the output records (SHP or GDB). -->
      <FormatColumn>
        <value>GISformat</value>
      </FormatColumn>

      <!-- The name of the column in the partner GIS layer indicating whether an export should also
           be created as a CSV or TXT file. Leave blank for no export. -->
      <ExportColumn>
        <value>ExportFormat</value>
      </ExportColumn>

      <!-- The name of the column in the partner GIS layer indicating which SQL table should be
           used for that partner. -->
      <SQLTableColumn>
        <value>SQLTable</value>
      </SQLTableColumn>

      <!-- The name of the column in the partner GIS layer indicating which SQL files should be
           created for each partner. -->
      <SQLFilesColumn>
        <value>SQLFiles</value>
      </SQLFilesColumn>

      <!-- The name of the column in the partner GIS layer indicating which Map files should be
            created for each partner -->
      <MapFilesColumn>
        <value>MapFiles</value>
      </MapFilesColumn>

      <!-- The name of the column in the partner GIS layer indicating which survey tags, if any
           should be included in the export. -->
      <TagsColumn>
        <value>PartnerTags</value>
      </TagsColumn>

      <!-- The name of the column in the partner GIS layer containing the spatial geometry. -->
      <SpatialColumn>
        <value>Shape</value>
      </SpatialColumn>

      <!-- The where clause to determine which partners to display. -->
      <PartnerClause>
        <value>Active = "Y"</value>
      </PartnerClause>

      <!-- The options for the selection types. -->
      <SelectTypeOptions>
        <value>Spatial Only;Survey Tags Only;Spatial and Survey Tags</value>
      </SelectTypeOptions>

      <!-- The default selection type (1 = spatial, 2 = tags, 3 = both). -->
      <DefaultSelectType>
        <value>3</value>
      </DefaultSelectType>

      <!-- The SQL criteria for excluding any unwanted records. -->
      <ExclusionClause>
        <value>SurveyName &lt;&gt; 'Bird Survey - Test' AND SurveyName &lt;&gt; 'North Park Nature Reserve'</value>
      </ExclusionClause>

      <!-- The default value for including the exclusion clause. Leave blank to hide option in dialog. -->
      <DefaultApplyExclusionClause>
        <value>Yes</value>
      </DefaultApplyExclusionClause>

      <!-- By default, should centroids be used for selecting records? Leave blank to hide option in dialog. -->
      <DefaultUseCentroids>
        <value>No</value>
      </DefaultUseCentroids>

      <!-- The default value for uploading the partner table to the server. Leave blank to hide option in dialog. -->
      <DefaultUploadToServer>
        <value>Yes</value>
      </DefaultUploadToServer>

      <!-- By default, should an existing log file be cleared? -->
      <DefaultClearLogFile>
        <value>Yes</value>
      </DefaultClearLogFile>

      <!-- By default, should the log file be opened after running. -->
      <DefaultOpenLogFile>
        <value>Yes</value>
      </DefaultOpenLogFile>

      <!-- The table columns and SQL where clauses used to select all the required columns for
        the extract tables -->
      <SQLTables>
        <AllSppPoint>
            <OutputName>
                <Value>Species_All_%partner%</Value>
            </OutputName>
            <Columns>
                <Value>TaxonName, CommonName, TaxonClass, TaxonGroup, TaxonOrder, SP_GEOMETRY</Value>
            </Columns>
            <WhereClause>
                <Value>RECORDYEAR &gt;= 1985 AND (NEG_RECORD &lt;&gt; 'Y' OR NEG_RECORD IS NULL) AND GRPRECISION &lt;= 100 AND GRIDREF IS NOT NULL AND DATE_START IS NOT NULL AND RECORDER IS NOT NULL AND LATIN_NAME &lt;&gt; 'Homo sapiens' AND VERIFICATION &lt;&gt; 'Considered incorrect'</Value>
            </WhereClause>
            <OrderColumns>
                <Value></Value>
            </OrderColumns>
            <MacroName>
                <Value></Value>
            </MacroName>
            <MacroParms>
                <Value></Value>
            </MacroParms>
        </AllSppPoint>
        <DesignatedSpp>
            <OutputName>
                <Value>Species_Designated_%partner%</Value>
            </OutputName>
            <Columns>
                <Value>TaxonName, CommonName, TaxonClass, TaxonGroup, TaxonOrder, SurveyName</Value>
            </Columns>
            <WhereClause>
                <Value>(NEG_RECORD &lt;&gt; 'Y' OR NEG_RECORD IS NULL) AND GRPRECISION &lt;= 100 AND (STATUS_PLANNING IS NOT NULL OR STATUS_OTHER IS NOT NULL) AND GRIDREF IS NOT NULL AND DATE_START IS NOT NULL AND RECORDER IS NOT NULL AND LATIN_NAME &lt;&gt; 'Homo sapiens' AND VERIFICATION &lt;&gt; 'Considered incorrect'</Value>
            </WhereClause>
            <OrderColumns>
                <Value>TAXONOMIC_GROUP, SPP_NAME</Value>
            </OrderColumns>
            <MacroName>
                <Value></Value>
            </MacroName>
            <MacroParms>
                <Value></Value>
            </MacroParms>
        </DesignatedSpp>
      </SQLTables>

      <!-- The names and local names of the map tables and the required columns for the map tables -->
      <MapLayers>
        <Polys_-_SACs>
            <LayerName>
                <value>Special Area of Conservation</value>
            </LayerName>
            <OutputName>
                <value>%shortref%_SACs</value>
            </OutputName>
            <Columns>
                <value>SAC_NAME, SAC_CODE</value> <!-- Use commas to separate. NOTE case sensitive! -->
            </Columns>
            <OrderColumns> <!-- Overrides GroupColumns -->
                <value></value>
            </OrderColumns>
            <WhereClause>
                <value></value><!-- example: Name = 'myName' OR area_ha > 5 -->
            </WhereClause>
            <LoadWarning>
                <value>Yes</value>
            </LoadWarning>
            <MacroName>
                <Value></Value>
            </MacroName>
            <MacroParms>
                <Value></Value>
            </MacroParms>
        </Polys_-_SACs>
        <Polys_-_SPAs>
            <LayerName>
                <value>Special Protection Area</value>
            </LayerName>
            <OutputName>
                <value>SPAs</value>
            </OutputName>
            <Columns>
                <value>SPA_NAME</value> <!-- Use commas to separate. NOTE case sensitive! -->
            </Columns>
            <OrderColumns> <!-- Overrides GroupColumns -->
                <value></value>
            </OrderColumns>
            <WhereClause>
                <value></value><!-- example: Name = 'myName' OR area_ha > 5 -->
            </WhereClause>
            <LoadWarning>
                <value>Yes</value>
            </LoadWarning>
            <MacroName>
                <Value></Value>
            </MacroName>
            <MacroParms>
                <Value></Value>
            </MacroParms>
        </Polys_-_SPAs>
        <Polys_-_Ramsars>
            <LayerName>
                <value>Ramsar</value>
            </LayerName>
            <OutputName>
                <value>Ramsars</value>
            </OutputName>
            <Columns>
                <value>NAME</value> <!-- Use commas to separate. NOTE case sensitive! -->
            </Columns>
            <OrderColumns> <!-- Overrides GroupColumns -->
                <value></value>
            </OrderColumns>
            <WhereClause>
                <value></value><!-- example: Name = 'myName' OR area_ha > 5 -->
            </WhereClause>
            <LoadWarning>
                <value>Yes</value>
            </LoadWarning>
            <MacroName>
                <Value></Value>
            </MacroName>
            <MacroParms>
                <Value></Value>
            </MacroParms>
        </Polys_-_Ramsars>
      </MapLayers>

    </DataExtractor>
    </configuration>


.. raw:: latex

	\newpage

.. index::
    single: Appendix; Licence
    single: License

.. _licence:

GNU Free Documentation License
==============================

Permission is granted to copy, distribute and/or modify this document under 
the terms of the GNU Free Documentation License, Version 1.3 or any later
version published by the Free Software Foundation; with no Invariant Sections,
no Front-Cover Texts and no Back-Cover Texts.  A copy of the license is
included in the Appendix section.

.. raw:: latex

    The full GNU Free Documentation License can be viewed at `www.gnu.org/licenses/fdl-1.3.en.html <https://www.gnu.org/licenses/fdl-1.3.en.html>`_

.. only:: html

::

                    GNU Free Documentation License
                     Version 1.3, 3 November 2008
    
    
     Copyright (C) 2000, 2001, 2002, 2007, 2008 Free Software Foundation, Inc.
         <http://fsf.org/>
     Everyone is permitted to copy and distribute verbatim copies
     of this license document, but changing it is not allowed.
    
    0. PREAMBLE
    
    The purpose of this License is to make a manual, textbook, or other
    functional and useful document "free" in the sense of freedom: to
    assure everyone the effective freedom to copy and redistribute it,
    with or without modifying it, either commercially or noncommercially.
    Secondarily, this License preserves for the author and publisher a way
    to get credit for their work, while not being considered responsible
    for modifications made by others.
    
    This License is a kind of "copyleft", which means that derivative
    works of the document must themselves be free in the same sense.  It
    complements the GNU General Public License, which is a copyleft
    license designed for free software.
    
    We have designed this License in order to use it for manuals for free
    software, because free software needs free documentation: a free
    program should come with manuals providing the same freedoms that the
    software does.  But this License is not limited to software manuals;
    it can be used for any textual work, regardless of subject matter or
    whether it is published as a printed book.  We recommend this License
    principally for works whose purpose is instruction or reference.
    
    
    1. APPLICABILITY AND DEFINITIONS
    
    This License applies to any manual or other work, in any medium, that
    contains a notice placed by the copyright holder saying it can be
    distributed under the terms of this License.  Such a notice grants a
    world-wide, royalty-free license, unlimited in duration, to use that
    work under the conditions stated herein.  The "Document", below,
    refers to any such manual or work.  Any member of the public is a
    licensee, and is addressed as "you".  You accept the license if you
    copy, modify or distribute the work in a way requiring permission
    under copyright law.
    
    A "Modified Version" of the Document means any work containing the
    Document or a portion of it, either copied verbatim, or with
    modifications and/or translated into another language.
    
    A "Secondary Section" is a named appendix or a front-matter section of
    the Document that deals exclusively with the relationship of the
    publishers or authors of the Document to the Document's overall
    subject (or to related matters) and contains nothing that could fall
    directly within that overall subject.  (Thus, if the Document is in
    part a textbook of mathematics, a Secondary Section may not explain
    any mathematics.)  The relationship could be a matter of historical
    connection with the subject or with related matters, or of legal,
    commercial, philosophical, ethical or political position regarding
    them.
    
    The "Invariant Sections" are certain Secondary Sections whose titles
    are designated, as being those of Invariant Sections, in the notice
    that says that the Document is released under this License.  If a
    section does not fit the above definition of Secondary then it is not
    allowed to be designated as Invariant.  The Document may contain zero
    Invariant Sections.  If the Document does not identify any Invariant
    Sections then there are none.
    
    The "Cover Texts" are certain short passages of text that are listed,
    as Front-Cover Texts or Back-Cover Texts, in the notice that says that
    the Document is released under this License.  A Front-Cover Text may
    be at most 5 words, and a Back-Cover Text may be at most 25 words.
    
    A "Transparent" copy of the Document means a machine-readable copy,
    represented in a format whose specification is available to the
    general public, that is suitable for revising the document
    straightforwardly with generic text editors or (for images composed of
    pixels) generic paint programs or (for drawings) some widely available
    drawing editor, and that is suitable for input to text formatters or
    for automatic translation to a variety of formats suitable for input
    to text formatters.  A copy made in an otherwise Transparent file
    format whose markup, or absence of markup, has been arranged to thwart
    or discourage subsequent modification by readers is not Transparent.
    An image format is not Transparent if used for any substantial amount
    of text.  A copy that is not "Transparent" is called "Opaque".
    
    Examples of suitable formats for Transparent copies include plain
    ASCII without markup, Texinfo input format, LaTeX input format, SGML
    or XML using a publicly available DTD, and standard-conforming simple
    HTML, PostScript or PDF designed for human modification.  Examples of
    transparent image formats include PNG, XCF and JPG.  Opaque formats
    include proprietary formats that can be read and edited only by
    proprietary word processors, SGML or XML for which the DTD and/or
    processing tools are not generally available, and the
    machine-generated HTML, PostScript or PDF produced by some word
    processors for output purposes only.
    
    The "Title Page" means, for a printed book, the title page itself,
    plus such following pages as are needed to hold, legibly, the material
    this License requires to appear in the title page.  For works in
    formats which do not have any title page as such, "Title Page" means
    the text near the most prominent appearance of the work's title,
    preceding the beginning of the body of the text.
    
    The "publisher" means any person or entity that distributes copies of
    the Document to the public.
    
    A section "Entitled XYZ" means a named subunit of the Document whose
    title either is precisely XYZ or contains XYZ in parentheses following
    text that translates XYZ in another language.  (Here XYZ stands for a
    specific section name mentioned below, such as "Acknowledgements",
    "Dedications", "Endorsements", or "History".)  To "Preserve the Title"
    of such a section when you modify the Document means that it remains a
    section "Entitled XYZ" according to this definition.
    
    The Document may include Warranty Disclaimers next to the notice which
    states that this License applies to the Document.  These Warranty
    Disclaimers are considered to be included by reference in this
    License, but only as regards disclaiming warranties: any other
    implication that these Warranty Disclaimers may have is void and has
    no effect on the meaning of this License.
    
    2. VERBATIM COPYING
    
    You may copy and distribute the Document in any medium, either
    commercially or noncommercially, provided that this License, the
    copyright notices, and the license notice saying this License applies
    to the Document are reproduced in all copies, and that you add no
    other conditions whatsoever to those of this License.  You may not use
    technical measures to obstruct or control the reading or further
    copying of the copies you make or distribute.  However, you may accept
    compensation in exchange for copies.  If you distribute a large enough
    number of copies you must also follow the conditions in section 3.
    
    You may also lend copies, under the same conditions stated above, and
    you may publicly display copies.
    
    
    3. COPYING IN QUANTITY
    
    If you publish printed copies (or copies in media that commonly have
    printed covers) of the Document, numbering more than 100, and the
    Document's license notice requires Cover Texts, you must enclose the
    copies in covers that carry, clearly and legibly, all these Cover
    Texts: Front-Cover Texts on the front cover, and Back-Cover Texts on
    the back cover.  Both covers must also clearly and legibly identify
    you as the publisher of these copies.  The front cover must present
    the full title with all words of the title equally prominent and
    visible.  You may add other material on the covers in addition.
    Copying with changes limited to the covers, as long as they preserve
    the title of the Document and satisfy these conditions, can be treated
    as verbatim copying in other respects.
    
    If the required texts for either cover are too voluminous to fit
    legibly, you should put the first ones listed (as many as fit
    reasonably) on the actual cover, and continue the rest onto adjacent
    pages.
    
    If you publish or distribute Opaque copies of the Document numbering
    more than 100, you must either include a machine-readable Transparent
    copy along with each Opaque copy, or state in or with each Opaque copy
    a computer-network location from which the general network-using
    public has access to download using public-standard network protocols
    a complete Transparent copy of the Document, free of added material.
    If you use the latter option, you must take reasonably prudent steps,
    when you begin distribution of Opaque copies in quantity, to ensure
    that this Transparent copy will remain thus accessible at the stated
    location until at least one year after the last time you distribute an
    Opaque copy (directly or through your agents or retailers) of that
    edition to the public.
    
    It is requested, but not required, that you contact the authors of the
    Document well before redistributing any large number of copies, to
    give them a chance to provide you with an updated version of the
    Document.
    
    
    4. MODIFICATIONS
    
    You may copy and distribute a Modified Version of the Document under
    the conditions of sections 2 and 3 above, provided that you release
    the Modified Version under precisely this License, with the Modified
    Version filling the role of the Document, thus licensing distribution
    and modification of the Modified Version to whoever possesses a copy
    of it.  In addition, you must do these things in the Modified Version:
    
    A. Use in the Title Page (and on the covers, if any) a title distinct
       from that of the Document, and from those of previous versions
       (which should, if there were any, be listed in the History section
       of the Document).  You may use the same title as a previous version
       if the original publisher of that version gives permission.
    B. List on the Title Page, as authors, one or more persons or entities
       responsible for authorship of the modifications in the Modified
       Version, together with at least five of the principal authors of the
       Document (all of its principal authors, if it has fewer than five),
       unless they release you from this requirement.
    C. State on the Title page the name of the publisher of the
       Modified Version, as the publisher.
    D. Preserve all the copyright notices of the Document.
    E. Add an appropriate copyright notice for your modifications
       adjacent to the other copyright notices.
    F. Include, immediately after the copyright notices, a license notice
       giving the public permission to use the Modified Version under the
       terms of this License, in the form shown in the Addendum below.
    G. Preserve in that license notice the full lists of Invariant Sections
       and required Cover Texts given in the Document's license notice.
    H. Include an unaltered copy of this License.
    I. Preserve the section Entitled "History", Preserve its Title, and add
       to it an item stating at least the title, year, new authors, and
       publisher of the Modified Version as given on the Title Page.  If
       there is no section Entitled "History" in the Document, create one
       stating the title, year, authors, and publisher of the Document as
       given on its Title Page, then add an item describing the Modified
       Version as stated in the previous sentence.
    J. Preserve the network location, if any, given in the Document for
       public access to a Transparent copy of the Document, and likewise
       the network locations given in the Document for previous versions
       it was based on.  These may be placed in the "History" section.
       You may omit a network location for a work that was published at
       least four years before the Document itself, or if the original
       publisher of the version it refers to gives permission.
    K. For any section Entitled "Acknowledgements" or "Dedications",
       Preserve the Title of the section, and preserve in the section all
       the substance and tone of each of the contributor acknowledgements
       and/or dedications given therein.
    L. Preserve all the Invariant Sections of the Document,
       unaltered in their text and in their titles.  Section numbers
       or the equivalent are not considered part of the section titles.
    M. Delete any section Entitled "Endorsements".  Such a section
       may not be included in the Modified Version.
    N. Do not retitle any existing section to be Entitled "Endorsements"
       or to conflict in title with any Invariant Section.
    O. Preserve any Warranty Disclaimers.
    
    If the Modified Version includes new front-matter sections or
    appendices that qualify as Secondary Sections and contain no material
    copied from the Document, you may at your option designate some or all
    of these sections as invariant.  To do this, add their titles to the
    list of Invariant Sections in the Modified Version's license notice.
    These titles must be distinct from any other section titles.
    
    You may add a section Entitled "Endorsements", provided it contains
    nothing but endorsements of your Modified Version by various
    parties--for example, statements of peer review or that the text has
    been approved by an organization as the authoritative definition of a
    standard.
    
    You may add a passage of up to five words as a Front-Cover Text, and a
    passage of up to 25 words as a Back-Cover Text, to the end of the list
    of Cover Texts in the Modified Version.  Only one passage of
    Front-Cover Text and one of Back-Cover Text may be added by (or
    through arrangements made by) any one entity.  If the Document already
    includes a cover text for the same cover, previously added by you or
    by arrangement made by the same entity you are acting on behalf of,
    you may not add another; but you may replace the old one, on explicit
    permission from the previous publisher that added the old one.
    
    The author(s) and publisher(s) of the Document do not by this License
    give permission to use their names for publicity for or to assert or
    imply endorsement of any Modified Version.
    
    
    5. COMBINING DOCUMENTS
    
    You may combine the Document with other documents released under this
    License, under the terms defined in section 4 above for modified
    versions, provided that you include in the combination all of the
    Invariant Sections of all of the original documents, unmodified, and
    list them all as Invariant Sections of your combined work in its
    license notice, and that you preserve all their Warranty Disclaimers.
    
    The combined work need only contain one copy of this License, and
    multiple identical Invariant Sections may be replaced with a single
    copy.  If there are multiple Invariant Sections with the same name but
    different contents, make the title of each such section unique by
    adding at the end of it, in parentheses, the name of the original
    author or publisher of that section if known, or else a unique number.
    Make the same adjustment to the section titles in the list of
    Invariant Sections in the license notice of the combined work.
    
    In the combination, you must combine any sections Entitled "History"
    in the various original documents, forming one section Entitled
    "History"; likewise combine any sections Entitled "Acknowledgements",
    and any sections Entitled "Dedications".  You must delete all sections
    Entitled "Endorsements".
    
    
    6. COLLECTIONS OF DOCUMENTS
    
    You may make a collection consisting of the Document and other
    documents released under this License, and replace the individual
    copies of this License in the various documents with a single copy
    that is included in the collection, provided that you follow the rules
    of this License for verbatim copying of each of the documents in all
    other respects.
    
    You may extract a single document from such a collection, and
    distribute it individually under this License, provided you insert a
    copy of this License into the extracted document, and follow this
    License in all other respects regarding verbatim copying of that
    document.
    
    
    7. AGGREGATION WITH INDEPENDENT WORKS
    
    A compilation of the Document or its derivatives with other separate
    and independent documents or works, in or on a volume of a storage or
    distribution medium, is called an "aggregate" if the copyright
    resulting from the compilation is not used to limit the legal rights
    of the compilation's users beyond what the individual works permit.
    When the Document is included in an aggregate, this License does not
    apply to the other works in the aggregate which are not themselves
    derivative works of the Document.
    
    If the Cover Text requirement of section 3 is applicable to these
    copies of the Document, then if the Document is less than one half of
    the entire aggregate, the Document's Cover Texts may be placed on
    covers that bracket the Document within the aggregate, or the
    electronic equivalent of covers if the Document is in electronic form.
    Otherwise they must appear on printed covers that bracket the whole
    aggregate.
    
    
    8. TRANSLATION
    
    Translation is considered a kind of modification, so you may
    distribute translations of the Document under the terms of section 4.
    Replacing Invariant Sections with translations requires special
    permission from their copyright holders, but you may include
    translations of some or all Invariant Sections in addition to the
    original versions of these Invariant Sections.  You may include a
    translation of this License, and all the license notices in the
    Document, and any Warranty Disclaimers, provided that you also include
    the original English version of this License and the original versions
    of those notices and disclaimers.  In case of a disagreement between
    the translation and the original version of this License or a notice
    or disclaimer, the original version will prevail.
    
    If a section in the Document is Entitled "Acknowledgements",
    "Dedications", or "History", the requirement (section 4) to Preserve
    its Title (section 1) will typically require changing the actual
    title.
    
    
    9. TERMINATION
    
    You may not copy, modify, sublicense, or distribute the Document
    except as expressly provided under this License.  Any attempt
    otherwise to copy, modify, sublicense, or distribute it is void, and
    will automatically terminate your rights under this License.
    
    However, if you cease all violation of this License, then your license
    from a particular copyright holder is reinstated (a) provisionally,
    unless and until the copyright holder explicitly and finally
    terminates your license, and (b) permanently, if the copyright holder
    fails to notify you of the violation by some reasonable means prior to
    60 days after the cessation.
    
    Moreover, your license from a particular copyright holder is
    reinstated permanently if the copyright holder notifies you of the
    violation by some reasonable means, this is the first time you have
    received notice of violation of this License (for any work) from that
    copyright holder, and you cure the violation prior to 30 days after
    your receipt of the notice.
    
    Termination of your rights under this section does not terminate the
    licenses of parties who have received copies or rights from you under
    this License.  If your rights have been terminated and not permanently
    reinstated, receipt of a copy of some or all of the same material does
    not give you any rights to use it.
    
    
    10. FUTURE REVISIONS OF THIS LICENSE
    
    The Free Software Foundation may publish new, revised versions of the
    GNU Free Documentation License from time to time.  Such new versions
    will be similar in spirit to the present version, but may differ in
    detail to address new problems or concerns.  See
    http://www.gnu.org/copyleft/.
    
    Each version of the License is given a distinguishing version number.
    If the Document specifies that a particular numbered version of this
    License "or any later version" applies to it, you have the option of
    following the terms and conditions either of that specified version or
    of any later version that has been published (not as a draft) by the
    Free Software Foundation.  If the Document does not specify a version
    number of this License, you may choose any version ever published (not
    as a draft) by the Free Software Foundation.  If the Document
    specifies that a proxy can decide which future versions of this
    License can be used, that proxy's public statement of acceptance of a
    version permanently authorizes you to choose that version for the
    Document.
    
    11. RELICENSING
    
    "Massive Multiauthor Collaboration Site" (or "MMC Site") means any
    World Wide Web server that publishes copyrightable works and also
    provides prominent facilities for anybody to edit those works.  A
    public wiki that anybody can edit is an example of such a server.  A
    "Massive Multiauthor Collaboration" (or "MMC") contained in the site
    means any set of copyrightable works thus published on the MMC site.
    
    "CC-BY-SA" means the Creative Commons Attribution-Share Alike 3.0 
    license published by Creative Commons Corporation, a not-for-profit 
    corporation with a principal place of business in San Francisco, 
    California, as well as future copyleft versions of that license 
    published by that same organization.
    
    "Incorporate" means to publish or republish a Document, in whole or in 
    part, as part of another Document.
    
    An MMC is "eligible for relicensing" if it is licensed under this 
    License, and if all works that were first published under this License 
    somewhere other than this MMC, and subsequently incorporated in whole or 
    in part into the MMC, (1) had no cover texts or invariant sections, and 
    (2) were thus incorporated prior to November 1, 2008.
    
    The operator of an MMC Site may republish an MMC contained in the site
    under CC-BY-SA on the same site at any time before August 1, 2009,
    provided the MMC is eligible for relicensing.
    
    
    ADDENDUM: How to use this License for your documents
    
    To use this License in a document you have written, include a copy of
    the License in the document and put the following copyright and
    license notices just after the title page:
    
        Copyright (c)  YEAR  YOUR NAME.
        Permission is granted to copy, distribute and/or modify this document
        under the terms of the GNU Free Documentation License, Version 1.3
        or any later version published by the Free Software Foundation;
        with no Invariant Sections, no Front-Cover Texts, and no Back-Cover Texts.
        A copy of the license is included in the section entitled "GNU
        Free Documentation License".
    
    If you have Invariant Sections, Front-Cover Texts and Back-Cover Texts,
    replace the "with...Texts." line with this:
    
        with the Invariant Sections being LIST THEIR TITLES, with the
        Front-Cover Texts being LIST, and with the Back-Cover Texts being LIST.
    
    If you have Invariant Sections without Cover Texts, or some other
    combination of the three, merge those two alternatives to suit the
    situation.
    
    If your document contains nontrivial examples of program code, we
    recommend releasing these examples in parallel under your choice of
    free software license, such as the GNU General Public License,
    to permit their use in free software.

