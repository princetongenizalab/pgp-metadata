# PGP Metadata

This readme.txt file was drafted 2025-04 by Rachel Richman and reviewed by Mohamed Abdellatif. Revised and updated 2026-02 by Mohamed Abdellatif. Reviewed by Rebecca Koeser.

GENERAL INFORMATION

1. Title of Dataset: Princeton Geniza Project Datasets

2. Author Information
   
	A. Principal Investigator Contact Information
		Name: Marina Rustow
		Institution: Princeton University
		Email: mrustow@princeton.edu

	B. Associate or Co-investigator Contact Information
		Name: Rebecca Koeser
		Institution: Princeton University
		Email: rebecca.s.koeser@princeton.edu

	C. Alternate Contact Information
		Email: geniza@princeton.edu

3. Dates of data collection: 1986-01-01/2026-02-12
 
4. Information about funding sources that supported the collection of the data: 

[In alphabetical order]
  Center for Digital Humanities, Princeton University (2020–22) 
DataX, Center for Statistics and Machine Learning, Princeton University (2022)
David A. Gardner Magic Grants for Innovation, Princeton University Humanities Council (2015–17)
Dean for Research, Princeton University (2021, 2024)
Educational Technologies Center, Princeton University (1987–2013)
Friedberg Genizah Project (1999–2004)
IBM Advanced Education Project/Princeton University Project Pegasus (1987)
McGraw Center for Teaching and Learning, Princeton University (2013–2023)
National Endowment for the Humanities (2015–17)
Near Eastern Studies Department, Princeton University (1986– )
Office of the Provost, Princeton University (2015– )
Program in Judaic Studies, Princeton University (2024)


SHARING/ACCESS INFORMATION

1. Licenses/restrictions placed on the data: 

	Dataset is released under the noncommercial Creative Commons Attribution 4.0 license (CC-BY-NC.4.0): 
https://creativecommons.org/licenses/by-nc/4.0/deed.en 

2. Links to publications that cite or use the data: 

	Mohamed Abdellatif, Joel U. Bretheim, and Marina Rustow. “Machine transliteration of long text with error detection and correction.” Journal of Data Mining & Digital Humanities, vol. NLP4DH, I. Historical and linguistic approaches, Mar. 2025. https://doi.org/10.46298/jdmdh.15020

3. Links to other publicly accessible locations of the data: 
	https://github.com/princetongenizalab/pgp-metadata 


4. Links to sites hosting document images:
 	https://cudl.lib.cam.ac.uk/; https://fjms.genizah.org; https://www.bl.uk/research/digitised-manuscripts/;  https://genizah.bodleian.ox.ac.uk/ ; https://dpul.princeton.edu/catalog/ 

5. Was data derived from another source? 

	Datasets are exported from the Princeton Geniza Project v4.x (PGPv4):

	Princeton Geniza Project, version 4.22.0. Center for Digital Humanities at Princeton, 2025.

	Koeser, Rebecca Sutton, Gissoo Doroudian, Ben Silverman, Nick Budak, Kevin McElwee, and Ryan Heuser. “Princeton-cdh/geniza: V4.22”. Zenodo, May 19, 2025. https://doi.org/10.5281/zenodo.15464178.

Data organizes and curates content from other sources including:
	S. D. Goitein unpublished papers
	Data from Genizah Research Lab at Cambridge University Library (2017)
	Documentary source identification from Friedberg Genizah Project
	Transcriptions and translations in footnotes dataset are drawn from scholarly sources documented in the sources dataset


DATA & FILE OVERVIEW

1. File List: 

	documents.csv : metadata describing PGP documents (letters, court case summaries, etc.). This is the primary entry point for the datasets.

	fragments.csv : metadata describing the fragments, or the material support, on which documents are written(typically paper or parchment); includes information about the holding library or museum and identifier assigned by that institution (“shelfmark”)

	sources.csv : bibliographic metadata for  secondary source scholarship about Geniza documents, particularly unpublished transcriptions and translations. Not a comprehensive list of all documentary Geniza scholarship; only includes sources cited in PGP data.

	footnotes.csv : information linking scholarly sources to specific documents, people, and places; includes plain text transcription and translation content.

	people.csv: biographical metadata describing some people mentioned in, or otherwise related to, Geniza documents. 

	places.csv: metadata describing places associated with Geniza documents (whether mentioned in the text or where they were written or sent).

	datapackage.json: specifying format and rules for the data files above, and the non-commerical license.

3. Relationship between files, if important: 

	documents.csv is intended to be the primary entry point, and can be used in combination with other files:

	fragments.csv can be joined with documents to provide information about holding institutions and access to images via IIIF; can be joined from documents.csv based on shelfmark (delimited with “ + “ for documents that are associated with multiple fragments) or by pgpids delimited list field in fragments.csv

	footnotes.csv link documents to sources; can be joined with document information based on pgpid in documents.csv and document_id in footnotes.csv

	people.csv and places.csv relate to documents but exports in the current dataset only include counts of related documents; the list of specific documents can be found at the url included in the data for entries with public urls.

4. Additional related data collected that was not included in the current data package: 
	Images of fragments are not included, but are referenceable via IIIF Presentation manifests
	PGP-specific arrangement of images for documents (overrides for fragment image order, orientation, and exclusion)
	Links between people and documents or places and documents
	Events

5. Are there multiple versions of the dataset? 
	This is the first published version of PGP data.
	

METHODOLOGICAL INFORMATION

1. Description of methods used for collection/generation of data: 

	Data is based on researchers finding documentary sources from the Cairo Geniza or related caches of documents and adding them to the database with descriptions. In some cases, batches of suspected or known documentary materials were imported from other sources and then described. Other researchers read the original fragments and transcribe them (using paleographic skills as well as linguistic knowledge of Judaeo-Arabic, Hebrew, Arabic, and Aramaic). Scholars translate the documents (if we’re lucky). Research assistants help tag the documents with relevant scholarship, dates, people, and places.

For more details, refer to the history of the Princeton Geniza Lab: https://genizalab.princeton.edu/about/history-princeton-geniza-lab 

2. Methods for processing the data: 

	From 2016 until 2021, PGP document and fragment metadata were managed in a Google Sheets spreadsheet, with additional related data in a SQL database (links to Goitein scholarship) and transcription content stored as XML in a BitBucket git repository.

	In 2021, PGP data was migrated to a relational database managed by a Python/Django web application (PGPv4); data curation since that point is mediated by an admin interface to the database. 

	The datasets are generated as tabular flat-file exports of selected data from the full PGPv4 relational database.
 
3. Describe any quality-assurance procedures performed on the data: 

	Data structure and required fields are enforced and validated by the database and associated web application. Content based on scholarly interpretation has some degree of subjectiveness. The data includes notes (such as in description or notes fields) when there are differences between scholarly opinions. Research assistants are regularly improving the data, including correcting errors and adding new information. 

4. People involved with data collection, processing, and curation: 

	Mohamed Abdellatif, Gabrielle Agus, Rafael Alvarado, Amir Ashur, Fahim Azaz, Kathryn Babayan, Peter Batke, Sasha Batz Stern, Dan Beaumont, Catherine Beaumont, Amel Bensalim, Zohar Berman, Lorenzo Bondioli, Jake Brzowsky, Nick Budak, Mark R. Cohen, Sarah M. Dinovelli, Matthew Dudley, Tamer el-Leithy, Alan Elbaum, Shamma Fox, Arnold Franklin, Zafrira Friedmann, Yosef Ginsberg, Abigail Glickman, Brendan Goldman, Pratima Gopalakrishnan, Jennifer Grayson, Juan José López Haddad, Ofir Haim, Sumaiya Hamdani, Jane Hathaway, Nomi Heger, Ilana Newman Hernandez, Akiva Reuben Marbach Jackson, Jessica Jobanek, Ben Johnston, Ethan Kahn, Natalie King, Tyler Kliem, Eve Krakowski, Miriam Krakowski, Yahm Levin, Nehama Libman, Philip Lieberman, Stephanie Luescher, Roxani Margariti, Jessica Marglin, Yumna Masarwa, Grace Masback, Kevin McElwee, Micah Newberger, Sarah Nisenson, Elazar Nudell, Cecilia Palombo, Jessica Parker, Craig Perry, Athina Pfeiffer, Vered Rekanati-Mordechai, Oliva Remie Constable, Rachel Richman, Gillian Rosenberg, Marina Rustow, Ksenia Ryzhova, Dan Sachs, Nina Sachs-Simpson, Tali Shemma, Avi Siegal, Dinah (Lily) Signoret, Petra Sijpesteijn, Emily Silkaitis, Ben Silverman, Elitsa Sklar, Yael Steinberg, Rebecca Sutton Koeser, Christopher Taylor, Nurit Tsafrir, Avrom Udovitch, Yusuf Umrethwala, Naïm Vantheiegham, Nadia Vidro, Shazia’Ayn Virji Babul, Joshua Weissmann, Isaac Wolfe, Moshe Yagur, Luke Yarbrough, Audrey Zhang, Oded Zinger

Specialized formats or other abbreviations used: 
	PGP = Princeton Geniza Project
	PGL = Princeton Geniza Lab, the host of PGP
	CDH = Princeton Center for Digital Humanities, which helped us build the relational database and website
	The library abbreviations in shelfmarks are too extensive to be listed here. If you have a question about a particular shelfmark, go to the document’s public webpage and scroll down to the bottom for a full citation.

DATA-SPECIFIC INFORMATION FOR: [documents]

1. Number of variables: 30

2. Number of cases/rows: 36,452

3. Variable List: 

	Pgpid: unique identifier for the document
	
	Url: permalink; public view of this document on PGP  website	
	
	Iiif_urls: link to the document/fragment images if hosted in IIIF format
	
	Fragment_urls: link to the document/fragment images if hosted in format that is not IIIF
	
	Shelfmark: the library’s name for the document and the name cited in scholarship	
	
	Multifragment: boolean yes/no for whether this shelfmark contains multiple small fragments of text
	
	Side: recto or verso, indicates which side of the fragment this document is composed on.
	
	Region: when multiple documents are composed on the same fragment, this field can be used to indicate which part of the fragment is associated with this PGPID. Many scholars use lower case letters (a, b, c) to indicate the correct region in reading order.
	
	Type: the PGP divides its material into 9 document types (credit/financial instrument, inscription, legal, legal query or responsa, letter, list or table, literary, paraliterary, and state). These types correspond to the form and content of the document. 
	
	Tags: tags added by research assistants interested in particular topics (such as medicine).
	
	Description: an English-language description of the document	
	
	Scholarship_records: list of associated secondary sources and editions of the document	
	
	Shelfmarks_historic: old and alternate ways of referring to this document (to aid readers of older scholarly texts find the current shelfmarks).	
	
	Languages_primary: primary language(s) necessary to read the document
	
	Languages_secondary: noting additional languages the document occasionally uses
	
	Language_note: free text field to note strange use of diacritics, spellings, etc.	
	
	Doc_date_original: the month and day listed on the document in its original form. Months are often from the Hebrew calendar and sometimes the Muslim calendar.
	
	Doc_date_calendar:  calendars from this period include the Jewish calendar (Anno Mundi), Seleucid calendar, Muslim calendar (Hijri), and the tax calendar (kharaji)
	
	Doc_date_standard: the date listed on the document converted to its equivalent in the Common Era. 	A slash is used to represent a range of dates.
	
	Inferred_date_display: human legible version of scholar’s inferred dating of the document
	
	Inferred_date_standard: computer legible version of scholar’s inferred dating of the document
	
	Inferred_date_rationale: choice of options for why this dating is assumed: the coinage mentioned, person mentioned, paleographic features, event mentioned, or other.
	
	Inferred_date_notes: additional explanation of why we should assume the document was written on this date/in this date range
	
	Initial_entry: when this document was first added to the PGP
	
	Last_modified: most recent edit of the document in the database
	
	Input_by: all users who have edited this database entry
	
	Library: holding library of the fragment(s) this document is on
	
	Collection: collection within the library where fragment(s) are held	
	
	Has_transcription: yes/no is there a digital edition on the PGP	
	
	Has_translation: yes/no is there a digital translation on the PGP

5. Specialized formats or other abbreviations used: 
	The library abbreviations in shelfmarks are too extensive to be listed here. If you have a question about a particular shelfmark, go to the document’s public webpage and scroll down to the bottom for a full citation.


DATA-SPECIFIC INFORMATION FOR: [fragments]

1. Number of variables: 16

2. Number of cases/rows: 36,928

3. Variable List: 

	Shelfmark: the library’s name for the document and the name cited in scholarship	

	Pgpids: the unique identifier(s) for the documents on this fragment
	
	Shelfmarks_historic: old and alternate ways of referring to this document (to aid readers of older scholarly texts find the current shelfmarks).		
	
	Collection: abbreviated version of collection and library information as seen in the shelfmark
	
	Library: holding library of the fragment
	
	Library_abbrev: abbreviation for the library name seen in shelfmarks and on the PGP
	
	Collection_name: collection within the library where fragment is held	
	
	Collection_abbrev: abbreviation for the library name seen in shelfmarks and on the PGP
	
	Url: holding library’s page for this fragment, if available
	
	Iiif_url: link to the fragment image IIIF manifest, if available
	
	Is_multifragment: yes/no if there are multiple fragments under the same shelfmark
	
	Created: date of addition to current database	
	
	Last_modified: date of last modification

	Provenance_display: source of the fragment (e.g. Geniza, non-Geniza ..etc)

	Provenance: earliest known / publication history

	Material_support: the physical material from which the fragment is believed to be manufactured / made


DATA-SPECIFIC INFORMATION FOR: [sources]

1. Number of variables: 18
   
2. Number of cases/rows: 712
   
3. Variable List: 
	(The information for sources are all intended to help populate a bibliographic entry)

	Source_type: researchers select one type to describe the source: article, book, book section, dissertation, unpublished, or blog 
	
	Authors: name of the source author(s)	
	
	Title: source’s title	
	
	Journal_book: name of the journal or book for articles and book sections	
	
	Volume: volume number for journal articles
	
	Issue:  issue number for journal articles
	
	Year: year of publication
	
	Place_published: place of publication	
	
	Publisher: publisher of the source	
	
	Edition: publication edition, if applicable
	
	Other_info: additional notes to help the researcher, such as the title of the work in Hebrew script
	
	Page_range: article and book chapter page numbers	
	
	Languages: language of the source (only for secondary scholarship and translations, not editions)
	
	Url: link to the source, if online
	
	Notes: additional notes on the source. Created from PGPID 1684 means that our database autogenerated the source from its appearance in a footnote on that document.
	
	Citation: the citation in full text

	Slug: full text citation re-expressed in a URL-friendly format

	Num_footnotes: the number of times this source is cited in document and person page footnotes.


DATA-SPECIFIC INFORMATION FOR: [footnotes]

1. Number of variables: 10

2. Number of cases/rows: 24,400

3. Variable List: 

	Document:  the name of the document or person page the footnote is featured on.
	
	Document ID: the PGPID (for documents) or person identifier number (for database use only)
	
	Source: the published or unpublished author and source of the footnoted content
	
	Source_slug: Re-expressing the name with continuous letters that may be used as part of a URL 

	Location: where in a published source this footnote derives from.
	
	Doc_relation: how is the footnote related to the document (discussion/translation/transcription)
	
	Emendation: Revisions or corrections

	Notes: an open-text field, sometimes features additional information about the source or footnote. Often used to annotate digital editions, for example “with minor emendations by Alan Elbaum” means that Alan reviewed the digital edition and fixed a few spelling errors or populated words that would not have been visible to the original scholar working off of a photocopied image.
	
	URL: link to the footnote’s source, if relevant. Mostly used for Goitein’s unpublished index cards and their discussions of documents.
	
	Content: the content of digital  transcriptions and translations for the document. 

5. Specialized formats or other abbreviations used: 
	Edition = published edition

	Digital edition = a published or unpublished edition of the document’s text that has been input online. May reflect changes since original publication.


DATA-SPECIFIC INFORMATION FOR: [people]

1. Number of variables: 14

2. Number of cases/rows: 1,771

3. Variable List: 

	Name: the main display name for the person
	
	Name_variants: additional names and spellings in different languages
	
	gender	: male, female, or unknown
	
	Social_role: select from list: Enslaved person, Jewish communal official, Jewish community member, Muslim judicial official, Other, State official	
	
	Auto_date_range: date range of person’s life populated from dated documents the person is connected to.	
	
	Manual_date_range: scholar input date range of person’s life from non-Geniza sources
	
	Description: brief description of the person’s life or role in the documents
	
	Tags:  tags added by research assistants interested in particular topics (such as being an individual related to the Indian Ocean trade [IB])	
	
	Related_people_count: number of individuals this person is connected to.
	
	Family_traces_roots_to: the place the person comes from, often known through their kunya (eg. Abū Naṣr al-Baṣrī	may not have been born in Basra, Iraq, but his name indicates his family was from there).
	
	Home_base: location where person lived
	
	traveled_to: known locations of travel for trade or pilgrimage
	
	Related_documents_count: number of documents associated with this person	
	
	Url: link to this person’s page on the PGP public site


DATA-SPECIFIC INFORMATION FOR: [places]

1. Number of variables: 10

2. Number of cases/rows: 485

3. Variable List: 

	Name: place name	
	
	Name_variants: additional names and spellings in different languages	
	
	Is_region: if the place is a region that might span multiple population clusters 

	Coordinates: latitude and longitude
	
	Geographic area: labeling the containing geographic territory

	Notes: notes, especially for places of unknown precise coordinates	
	
	Related_documents_count: number of documents associated with this place	
	
	Related_people_count: number of people associated with this place	
	
	Related_events_count: number of events associated with this place
	
	Url: link to this place page on the PGP public site

## About

This repository is used to version and publish data from the [Princeton Geniza Project](https://geniza.princeton.edu/) (PGP). The data files are automatically exported and synchronized from the PGP database. Commits include co-author information where possible, to credit the researchers who are working on the data.

Files in the data directory should _NOT_ be edited or modified directly.

The code that generates these exports is part of the PGP v4 codebase, available at https://github.com/Princeton-CDH/geniza

## Access via Flat GitHub

Data files can be viewed, filtered, and downloaded with Flat GitHub's Flat Viewer. Please note that it may take a moment for large files to load.

- [documents.csv](https://flatgithub.com/princetongenizalab/pgp-metadata?filename=data/documents.csv)
- [fragments.csv](https://flatgithub.com/princetongenizalab/pgp-metadata?filename=data/fragments.csv)
- [sources.csv](https://flatgithub.com/princetongenizalab/pgp-metadata?filename=data/sources.csv)
- [footnotes.csv](https://flatgithub.com/princetongenizalab/pgp-metadata?filename=data/footnotes.csv)
- [people.csv](https://flatgithub.com/princetongenizalab/pgp-metadata?filename=data/people.csv)
- [places.csv](https://flatgithub.com/princetongenizalab/pgp-metadata?filename=data/places.csv)
