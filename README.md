# Fostering-Fairness
DiD and synthetic control analysis of Catholic Charities of Boston closing to estimate the effect of faith-based foster care on adoption rate. Full details of the analysis can be found on bradyearley.wordpress.com.


NOTES ON AFCARS DATASETS
Please note the terms of use agreement: “users of these data are required to deposit with the Archive a copy of any published work or report based wholly or in part on these data. A copy of any completed manuscript, thesis abstract, or reprint should be sent to the National Data Archive on Child Abuse and Neglect, Cornell University, Bronfenbrenner Center for Translational Research, Ithaca, New York 14853-4401.”  All users of this data must agree to the terms of use and fill out a short request form that is emailed to NDACAN. If the request is satisfactory, NDACAN will share the datasets with you through box. 

“Each fiscal year’s AFCARS data provide case-level information for children served by the foster care system and children whose adoptions were finalized during the federal fiscal year (October 1 to September 30 of the following year).”  This means that data for FY2020 will run from October 1, 2019 to Sep. 30, 2020.

“DUPLICATE RECORDS. In the adoption data files, each record is supposed to represent a unique child whose adoption was finalized during that fiscal year. However, there are duplicate child ID, so one child can be in the data more than once. The foster care file is intended to have just one child record (unique St+RecNumbr) per year. This is true of all FC Files since FY2005, but earlier years do have duplicate RecNumbrs.” 

Variable missingness was a potential drawback of the dataset, but further investigation revealed it was not worrisome. The discharge reason variable in the AFCARS Foster Files dataset was missing a substantial proportion of observations (in some years in certain states, up to half the observations across 20 years of data). However, I noticed that missing data was weighted heavily to around 2008-09 when the way disreasn was counted had changed. Instead of being marked as “missing”, they were now categorized as “NA” meaning that they were not discharged (i.e., still in foster care). When I checked the number of “Missing” disreasn observations before 2008 and the number of “NA” observations after 2008, they correlated 99% with the Annie E. Casey Foundation data on children in foster care.  This eased concerns that these observations were actually missing and instead just represented children who had not been discharged.

DOWNLOADING AFCARS DATASETS
Download “Foster Care” from National Data Archive on Child Abuse and Neglect. These datasets will be found in the Adoption and Foster Care Analysis and Reporting System (AFCARS) files. https://www.ndacan.acf.hhs.gov/datasets/datasets-list.cfm.

Unzip the “Foster Care” files after downloading. This includes all data from 2000 to 2020. Note that AFCARS is a product of both Title IV-E of the Social Security Act (Section 479) as amended in 1986 and the Family Preservation and Support Services Program Act (1993) which required states to “develop statewide automated child welfare information systems (SACWIS)”.  Note also that the data is split into two broad periods: 1995-1999 (which includes a codebook for each respective year) and 2000-present (which is contained in one, unified codebook). All private agencies who contract with the state are required to report children, however, “adoptions finalized in years prior to FY 1998 are not being updated because most states indicated that those data were not credible. Users are encouraged not to request or utilize these data.”  Consequently, only data beginning in 2000 or later should be used.

Use the file titled “fc2000v5.dta” found in the “Foster Care” folder.

Unzip “Foster Care”

Open “fc2000v5.dta” in Stata and save to the file path indicated by your working directory in Stata.

Repeat this process for each year of data from 2000 to 2020

After all files have been opened and saved to the same file path, use “fc2000v5.dta” to begin cleaning and appending adoption files as explained in the faith_based_foster_cleaning_paper.do file.

