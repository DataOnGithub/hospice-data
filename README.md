This repo contains processed data used for publication with [Hospice, Inc.](http://projects.huffingtonpost.com/hospice-inc/), published by The Huffington Post on June 19, 2014. This data was used in part to identify [troubled hospices detailed in a Dec. 30, 2014 story](http://projects.huffingtonpost.com/hospice-inc/top-offending-hospices-rarely-punished).


The original database was sent by [The Centers for Medicare and Medicaid Services](http://cms.gov/) on April 1, 2014, in response to a Freedom of Information Act request filed by The Huffington Post. An updated version was received on Oct. 24, 2014.

##Fields and Files

The `hospices_export.csv` file describes hospice providers where at least one full "certification" survey occurred between January 2, 2004 and Oct. 16, 2014.  Fields are as follows:

1. Provider ID: The field used by CMS/CASPER applications to uniquely identify a provider (hospice, in this case)
2. Name: Name of the hospice
3. State
4. City
5. Address
6. ZIP Code
7. Ownership type - simple: A grouped categorization of the CMS provider owner type. Options are **nonprofit**, **for-profit**, **government**, **other**
8. Ownership type - detailed: The CMS/Casper field fully describing the owner type
9. Total surveys: The number of all surveys conducted by state inspectors. The Office of the Inspector General recommends that hospices be fully inspected and certified once every six years. CMS maintains three survey classifications: **standard/certification**, **complaint** and **federal monitoring surveys**.
10. Total certification surveys: The number of full government certification surveys. 
11. Total complaint surveys: The number of complaint surveys. 
12. Date of last certification survey: The date of the most recent **certification** survey. This field has been updated to reflect certification surveys conducted by private accreditation organizations. More [here](http://projects.huffingtonpost.com/hospice-inc/database#gotomethodology).
13. Total deficiencies: Total deficiency (violation) count from all three types of surveys.
14. Complaint deficiencies: Total deficiencies from **complaint** surveys.
15. Certification deficiencies: Total deficiencies from **certification** surveys.
16. FMS deficiencies: Total deficiencies from **federal monitoring surveys**.
17. Is active: Indicates if the hospice is still actively providing care.
18. Deemed: Indicates if the hospice is inspected by an accrediting organization.

Because the data is nested, some fields must be looked up in additional files.

Deficiencies for each hospice are listed in the `hospice_deficiencies_export.csv` file. Use the **Provider ID** found in `hospices_export.csv` to lookup all deficiencies associated with a given hospice. This file describes a deficiency as:

1. Provider ID: A hospice’s provider id.
2. Date: Date of the survey 
3. Code: The deficiency code. For the complete details use this value to lookup a short and full descriptions listed in `hospice_deficiency_lookup_export.csv`
4. Survey type: The type of survey conducted when the deficiency was recorded. The three possible values **S** (standard/certification survey), **C** (complaint survey) and **F** (federal monitoring survey)

The `hospice_deficiency_lookup_export.csv` file lists the description of each hospice deficiency code. The original codes were described by CMS at this [url](http://www.cms.gov/Regulations-and-Guidance/Guidance/Manuals/downloads/som107ap_m_hospice.pdf). Codes reserved for provider types other than hospice are not included and not described. The file’s fields are as follows:

1. Code: A unique identify for a deficiency
2. Edited description: The full descriptions found in [this](http://www.cms.gov/Regulations-and-Guidance/Guidance/Manuals/downloads/som107ap_m_hospice.pdf) document were edited by The Huffington Post.
3. Short description: A brief description of the deficiency provided by CMS.

The `loc_export.json` file contains a dump of all the above files inside a single file.


###Notes
The data here reflects Huffington Posts's Oct. 24, 2014 calculations of recent Medicare data. Some surveys and data points provided by The Centers for Medicare and Medicaid Services may be missing or out of date, because the regulator is not legally required to validate each entry.


###Updates
Added fields describing total counts for different types of surveys. Added fields describing whether each hospice is active and if each hospice is inspected by an accrediting organization. Removed date calculated field.

Med West-Harris Hospice was fully certified more recently than Medicare data indicated.

Community Hospice of Northeast Florida was incorrectly reported by Medicare as a for-profit provider. The data was updated to reflect their nonprofit status.

Central New Hampshire VNA and Hospice was incorrectly reported by Medicare as a for-profit provider. The data was updated to reflect their nonprofit status.

Pikes Peak Hospice and Palliative Care was incorrectly reported by Medicare as a for-profit provider. The data was updated to reflect their nonprofit status.

Sparrow Hospice was incorrectly reported by Medicare as a for-profit provider. The data was updated to reflect their nonprofit status.

Hospice of Michigan was incorrectly reported by Medicare as a for-profit provider. The data was updated to reflect their nonprofit status.

Harbor Hospice was incorrectly reported by Medicare as a for-profit provider. The data was updated to reflect their nonprofit status.

Mt. Hood Hospice, Inc. was incorrectly reported by Medicare as a for-profit provider. The data was updated to reflect their nonprofit status.

