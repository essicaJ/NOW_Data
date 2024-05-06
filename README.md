# NOW_Data
### NOW Data (Processed) Structure
- 9,658,887 US publisher news from 2010 to 2022 July
- Columns: 'ID'	'Text'	'#ofwords'	'Date'	'Country'	'Publisher'	'URL'	'Title'
### Where to get Data
- 2010-2020 available on https://www.lib.uchicago.edu/restricted/db/now-linguistic-corpus/
- After download, extract zip files, you can reference my approach in [this ipynb](extract_zip.ipynb)
- Text files are file names like "20-01-us1.txt" (Jan 2020 US news part 1) that contains article content with unique ID 'textID'
- Sources files are names like "now-sources-2020.txt" that contains article source information, including 'textID',	'#ofwords',	'Date',	'Country',	'Publisher',	'URL',	'Title'
- Merge by unique ID 'textID' to get complete information, [example of merge](merge_data.ipynb)
- 
