Developed for the proteomics community, the [Unicity checker](/tools/unicity-checker) analyzes up to 1,000 peptide sequences from mass spectrometry experiments. It determines the number of neXtProt entries and isoforms to which each submitted peptide is mapping. This tool is more than just a simple sequence mapping tool as it can take into account the wealth of sequence variants stored in neXtProt.

This release adds an important new feature for this tool, a "Download" option that allows users to get the results in CSV format.

A number of additional changes have been made to the user interface so as to improve usability:

* It is now possible to upload a TXT file containing peptide sequences for analysis.
* In order to return relevant results, duplicate peptides are removed and their number reported. Matching entries or isoforms are calculated and displayed for each distinct peptide. 
* A "Reset" button has been added that clears the form. 
