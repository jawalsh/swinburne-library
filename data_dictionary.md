# Data Dictionary

A data dictionary for “The Personal library and presumed reading of Algernon Charles Swinburne” data file: [swinburne_library.xml](swinburne_library.xml).

|Name                                                    |Element or Attribute                                                          |Xpath                                                                                                                                                              |Description                                                                                                                                                                                                                                                                             |
|:--- |:--- |:--- |:--- |
| Rare Book Terminology | `<div n="glossary">` | `/TEI/text/front/div[@n='glossary']` | Glossary of rare book terms used within Swinburne's and Watts-Dunton's auction catalogs |
| Rare Book Terminology Term Name | `<label>` | `/TEI/text/front/div[@n='glossary']/list//label` | Term name for terms in the Rare Book Terminology |
| Rare Book Terminology Term description | `<item>` | `/TEI/text/front/div[@n='glossary']/list//item` | Term description for terms in the Rare Book Terminology |
| Place names authority list | `<div n="places">` | `/TEI/text/front/div[@n='places']` | Authority records to places referenced in `<pubPlace>` within the bibliographic entries |
| Place record | `<place>` | `/TEI/text/front/div[@n='places']/listPlace//place` | Contains all elements and attributes for the authority record of a place. |
| [TGN](https://www.getty.edu/research/tools/vocabularies/tgn/) reference | `@source` | `/TEI/text/front/div[@n='places']/listPlace/place/@source` | Contains a URL to the [Getty Thesaurus of Geographic Names](https://www.getty.edu/research/tools/vocabularies/tgn/) (TGN) record for that place. |
| Place identifier | `@xml:id` | `/TEI/text/front/div[@n='places']/listPlace/place/@xml:id` | Contains a unique reference for that place to be referenced by `@ref` in <pubPlace> |
| Place name | `<placeName>` | `/TEI/text/front/div[@n='places']/listPlace/place/placeName` | Name for place found in the `<pubPlace>` of the `<biblStruct>` elements. If a place is referenced in multiple ways, `<place>` will have multiple `<placeName>` child elements. |
| Preferred place name | `<placeName type="preferred">` | `/TEI/text/front/div[@n='places']/listPlace/place/placeName/@type="preferred"` | Indicates that the <placeName> with the attribute is the preferred place name. This is equivalent to the [TGN](https://www.getty.edu/research/tools/vocabularies/tgn/)'s preferred English name. |
| Authors, Editors, and other intellectual contributors | `<div n="authors">` | `/TEI/text/front/div[@n='authors']` | Authority records to authors, editors, and other intellectual contributors referenced within the bibliographic entries. |
| Author, editor, contributor record | `<person>` | `/TEI/text/front/div[@n='authors']/listPerson/person` | Contains all elements and attributes for the authority record of an author, editor, or other intellectual contributor |
| Author, editor, contributor identifier | `@xml:id` | `/TEI/text/front/div[@n='authors']/listPerson/person/@xml:id` | Unique reference for that person to be referenced by `@corresp` in `<bibl>` or `<biblStruct>` |
| Name of author, editor, contributor | `<persName>` | `/TEI/text/front/div[@n=’authors’]/listPerson/person/persName` | Name of the person, copied from [LCNAF](https://id.loc.gov/authorities/names.html) or [VIAF](https://viaf.org) ([VIAF](https://viaf.org) only used if [LCNAF](https://id.loc.gov/authorities/names.html) unavailable). If no [LCNAF](https://id.loc.gov/authorities/names.html) or [VIAF](https://viaf.org) is available, it is formatted as Last Name(s), First Name(s) |
| [LCNAF](https://id.loc.gov/authorities/names.html) or [VIAF](https://viaf.org) reference | `@source` | `/TEI/text/front/div[@n='authors']/listPerson/person/persName/@source` | URL for the [LCNAF](https://id.loc.gov/authorities/names.html) or [VIAF](https://viaf.org) record, if one is available |
| Birth year | `<birth>` | `/TEI/text/front/div[@n='authors']/listPerson/person/birth` | Element referencing birth year of person |
| Death year | `<death>` | `/TEI/text/front/div[@n='authors']/listPerson/person/death` | Element referencing death year of person |
| Floruit years | `<floruit>` | `/TEI/text/front/div[@n='authors']/listPerson/person/floruit` | Element referencing period of activity of person |
| Year reference | `@when` | `/TEI/text/front/div[@n='authors']/listPerson/person/birth|death|floruit/@when` | [W3C](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/#date) four-digit year reference to date to facilitate computational processing. BCE years are represented via negative numbers. |
| Beginning year reference | `@from` | `/TEI/text/front/div[@n='authors']/listPerson/person/birth|death|floruit/@from` | [W3C](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/#date) four-digit year reference to beginning year of a period to facilitate computational processing. BCE years are represented via negative numbers. |
| Ending year reference | `@to` | `/TEI/text/front/div[@n='authors']/listPerson/person/birth|death|floruit/@to` | [W3C](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/#date) four-digit year reference to ending year of a period to facilitate computational processing. BCE years are represented via negative numbers. |
| Publishers and printers | `<div n="publishers">` | `/TEI/text/front/div[@n='publishers']` | Authority records to publishers and printers within the bibliographic entries.  |
| Publishers and printers (organizations) | `<listOrg>` | `/TEI/text/front/div[@n='publishers']/listOrg` | Authority records of organizations acting as printers or publishers referenced in the bibliographic entries |
| Publisher/printer organization record | `<org>` | `/TEI/text/front/div[@n='publishers']/listOrg/org` | Contains all elements and attributes for the authority record of an organization acting as publisher/printer. |
| Publisher/printer organization identifier | `@xml:id` | `/TEI/text/front/div[@n='publishers']/listOrg/org/@xml:id` | Unique reference for that organization to be referenced by `@corresp` in `<bibl>` or `<biblStruct>` |
| Name of publisher/printer (organization) | `<orgName>` | `/TEI/text/front/div[@n='publishers']/listOrg/org/orgName` | Name of the organization, copied from [LCNAF](https://id.loc.gov/authorities/names.html) or [VIAF](https://viaf.org) ([VIAF](https://viaf.org) only used if [LCNAF](https://id.loc.gov/authorities/names.html) unavailable). If no [LCNAF](https://id.loc.gov/authorities/names.html) available, it is formatted as written in the book it appears in. |
| [LCNAF](https://id.loc.gov/authorities/names.html) or [VIAF](https://viaf.org) reference | `@source` | `/TEI/text/front/div[@n='publishers']/listOrg/org/orgName/@source` | URL for the [LCNAF](https://id.loc.gov/authorities/names.html) or [VIAF](https://viaf.org) record, if one is available |
| Publishers and printers (individuals) | `<listPerson>` | `/TEI/text/front/div[@n='publishers']/listPerson` | Authority records of individuals acting as printers or publishers referenced in the bibliographic entries |
| Publisher/printer individual record | `<person>` | `/TEI/text/front/div[@n='publishers']/listPerson/person` | Contains all elements and attributes for the authority record of an author, editor, or other intellectual contributor |
| Publisher printer individual identifier | `@xml:id` | `/TEI/text/front/div[@n='publishers']/listPerson/person/@xml:id` | Unique reference for that person to be referenced by `@corresp` in `<bibl>` or `<biblStruct>` |
| Name of publisher/printer (individual) | `<persName>` | `/TEI/text/front/div[@n='publishers']/listPerson/person/persName` | Name of the person, copied from [LCNAF](https://id.loc.gov/authorities/names.html) or [VIAF](https://viaf.org) ([VIAF](https://viaf.org) only used if [LCNAF](https://id.loc.gov/authorities/names.html) unavailable). If no [LCNAF](https://id.loc.gov/authorities/names.html) or [VIAF](https://viaf.org) is available, it is formatted as Last Name(s), First Name(s) |
| [LCNAF](https://id.loc.gov/authorities/names.html) or [VIAF](https://viaf.org) reference | `@source` | `/TEI/text/front/div[@n='publishers']/listPerson/person/persName/@source` | URL for the [LCNAF](https://id.loc.gov/authorities/names.html) or [VIAF](https://viaf.org) record, if one is available |
| Birth year | `<birth>` | `/TEI/text/front/div[@n='publishers']/listPerson/person/birth` | Element referencing birth year of person |
| Death year | `<death>` | `/TEI/text/front/div[@n='publishers']/listPerson/person/death` | Element referencing death year of person |
| Floruit years | `<floruit>` | `/TEI/text/front/div[@n='publishers']/listPerson/person/floruit` | Element referencing period of activity of person |
| Year reference | `@when` | `/TEI/text/front/div[@n='publishers']/listPerson/person/birth|death|floruit/@when` | [W3C](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/#date) four-digit year reference to date to facilitate computational processing. BCE years are represented via negative numbers. |
| Beginning year reference | `@from` | `/TEI/text/front/div[@n='publishers']/listPerson/person/birth|death|floruit/@from` | [W3C](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/#date) four-digit year reference to beginning year of a period to facilitate computational processing. BCE years are represented via negative numbers. |
| Ending year reference | `@to` | `/TEI/text/front/div[@n='publishers']/listPerson/person/birth|death|floruit/@to` | [W3C](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/#date) four-digit year reference to ending year of a period to facilitate computational processing. BCE years are represented via negative numbers. |
| Full-text source controlled vocabulary entry | `<category xml:id="termReference"><catDesc>Term</castDesc></category>` | `/TEI/teiHeader/encodingDesc/classDecl/taxonomy[xml:id=’full-text’]/category` | Entry in the full-text source vocabulary. The value of the `@xml:id` provides the ID to be referenced by the `@corresp` in <relatedItem> (e.g., “ia"); `<catDesc>` spells out the source’s name (e.g., “Internet Archive", “HathiTrust"). |
| Bibliographic features controlled vocabulary entry | `<category xml:id="termReference"><catDesc>Term</castDesc></category>` | `/TEI/teiHeader/encodingDesc/classDecl/taxonomy[xml:id=’biblFeatures’]/category` | Entry in the bibliographic features vocbulary. The value of the `@xml:id` provides the ID to be referenced by the `@corresp` in `<note type="description">` (e.g., “uncut") or `<edition>` (e.g., “first_ed"; `<catDesc>` gives the term for the bibliographic feature (e.g., “uncut pages," “first edition")  |
| Swinburne relationship controlled vocabulary entry | `<category xml:id="termReference"><catDesc>Term</castDesc></category>` | `/TEI/teiHeader/encodingDesc/classDecl/taxonomy[xml:id=’relatSwinburne’]/category` | Entry in the vocabulary listing the various relationships books have with Swinburne. The value of the `@xml:id` provides the ID to be referenced by the `@corresp` in `<biblStruct>` or `<bibl>` (e.g., “owned"; `<catDesc>` gives the term/description for the relationship (e.g., “owned by Swinburne")  |
| Swinburne auction catalogue | `<div source="#sales-catalogue-swinburne">` | `/TEI/text/body/div[@source="#sales-catalogue-swinburne"]` | Part of corpus consisting of bibliographic entries describing the books present in the auction catalogue of Swinburne’s library |
| Watts-Dunton auction catalogue | `<div source="#sales-catalogue-watts-dunton">` | `/TEI/text/body/div[@source="#sales-catalogue-watts-dunton"]` | Part of corpus consisting of bibliographic entries describing the books present in the auction catalogue of Watts-Dunton’s library that related to Swinburne in some manner. |
| Auction day | `<div type="day" n="NUMBER">` | `/TEI/text/body/div[@source='#sales-catalogue-swinburne' or @source='#sales-catalogue-watts-dunton']/div[@type='day' and @n='NUMBER']` | Grouping of books that were sold on the same day within either the Swinburne or Watts-Dunton auction. |
| Size grouping | `<div type="size" n="FORMAT">` | `/TEI/text/body/div[@source='#sales-catalogue-swinburne' or @source='#sales-catalogue-watts-dunton']/div[@type='day' and @n='1']/div[@type=’size’ and @n=’FORMAT’]` | Grouping of books of the same bibliographic format and sold on the same day within either the Swinburne or Watts-Dunton auction. |
| Lot | `<listBibl type="lot" xml:id="ID">` | `/TEI/text/body//div//listBibl` | Grouping of books belonging to the same lot in either the Swinburne or Watts-Dunton auction. |
| Best 100 Books list | `<div source="best-hundred-books">` | `/TEI/text/body/div[@source="#best-hundred-books"]` | Books not already referenced in the auction catalogues or provenance research but included in Swinburne’s list of one hundred best books published in Pall Mall Gazette. |
| Poetry-extracted books | `<div source="poetry">` | `/TEI/text/body/div[@source="#poetry"]` | Books not already referenced in the auction catalogues, Best 100 Books, or provenance research but referenced by Swinburne in his poetry. |
| Provenance research books | `<div source="libraries">` | `/TEI/text/body/div[@source="#libraries"]` | Books not present in the auction catalogues but that were owned by Swinburne as identified by the present repository’s catalog record. |
| Unstructured bibliographic entry | `<bibl xml:id="ID">` | `/TEI/text/body//bibl` | Bibliographic entries for which there is not sufficient bibliographic metadata to create a fully structured `<biblStruct>` entry.  |
| Structured bibliographic entry | `<biblStruct xml:id="ID">` | `/TEI/text/body//biblStruct` | A book for which there is sufficient metadata to create a structured bibliographic entry.  |
| Title | `<title>` | `//biblStruct/monogr/title` | Title of book |
| Author | `<author>` | `//biblStruct/monogr/author` | Author of book. When possible, contains `@corresp` with reference to the authority record in `<div n="authors">`. |
| Statement of responsibility | `<respStmt><resp>RESPONSIBILITY</resp><name>NAME</name></respStmt>` | `//biblStruct/monogr/respStmt` | Other intellectual contributors to the book such as translators and editors. `<resp>` contains the description of their contribution (e.g., “edited by") and `<name>` contains the name of the individual responsible. |
| Edition | `<edition>` | `//biblStruct/monogr/edition` | Edition information. May contain `@corresp` referencing the bibliographic features vocabulary. |
| Descriptive note | `<note type="description">` | `//biblStruct/monogr/note[@type=’description’]` | Additional descriptive information given in the auction catalogues that is not structured by other elements. May contain `@corresp` referencing the bibliographic features vocabulary. |
| Inscription | `<note type="inscription">` | `//biblStruct/monogr/note[@type=’inscription’]` | Contains the text of an inscription in the book. |
| Quoted material | `<q>` | `//biblStruct//q` | Quoted material in `<note type="inscription">` |
| Publisher | `<publisher>` | `//biblStruct/monogr/imprint/publisher` | Publisher of book. When possible, contains `@corresp` with reference to the authority record in `<div n="publishers">`. |
| Place of publication | `<pubPlace>` | `//biblStruct/monogr/imprint/pubPlace` | Place of publication. Contains `@ref` with reference to the authority record in `<div n="place">` |
| Publication date | `<date when="YYYY"/>` | `//biblStruct/monogr/imprint/date/@when` | Date of publication. |
| Scope note | `<biblScope @unit="volume|page|number|part">RANGE</biblScope>` | `//biblStruct/monogr/biblScope` | If Swinburne only owned/read a portion of a full work/edition, `<biblScope>` indicates the range of that portion. `@unit` indicates the unit (e.g., volume, page). The content of the element gives the range. |
| Quantity of multi-item set | `<extent><measure unit="volumes|parts|pages" quantity="NUMBER"></extent>` | `//biblStruct/monogr/extent` | Records the extent of a multi-item set. `@unit` specifies the unit (e.g., volumes) and `@quantity` specifies how many of that unit. |
| Provenance information | `<note type="provenance" target="LibraryRecordURL">INSTITUTION</note>` | `//biblStruct/note[@type=’provenance’]` | Provides provenance information  about where a book Swinburne owned is located now. `@target` contains the URL of a permalink to the institution’s catalog record. The content of the element is the name of the institution. |
| Series | `<series>` | `//biblStruct/series` | Lists the series a book belonged to. |
| Linked Item | `<relatedItem type="full-text" corresp="#FullTextSourceID" target="ItemURL"/>` | `//biblStruct//relatedItem` | Reference to a full-text version of the item. `@corresp` contains a reference to the full-text source controlled vocabulary, `@target` contains the URL of the item. |
| Linked Item note | `<note type="fulltext">` | `//biblStruct/note[@type=’fulltext’]` | Note about the full-text provided. Often indicates if the full-text linked is not the edition owned by Swinburne. |

{% include footer.html %}