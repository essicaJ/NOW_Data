# NOW_Data
### NOW Data (Processed) Structure
- 9,658,887 US publisher news from 2010 to 2022 July
- Columns: 'ID'	'Text'	'#ofwords'	'Date'	'Country'	'Publisher'	'URL'	'Title'
### How to get Data
- 2010-2020 available on https://www.lib.uchicago.edu/restricted/db/now-linguistic-corpus/
- After download, extract zip files, you can reference my approach in [this ipynb](extract_zip.ipynb)
- Text files are file names like "20-01-us1.txt" (Jan 2020 US news part 1) that contains article content with unique ID 'textID'
- Sources files are names like "now-sources-2020.txt" that contains article source information, including 'textID',	'#ofwords',	'Date',	'Country',	'Publisher',	'URL',	'Title'
- Merge by unique ID 'textID' to get complete dataframe (article content and information), [ipynb example](merge_data.ipynb)
### Some Notes about Data Processing
- NOW contains articles from many different countries, you can choose specific country to extract, for example, only extract file with 'us' like  "20-01-us1.txt", to save space
- May contain duplicated articles, you can choose to de-duplicate by your own criteria, such as matching title, content or URL
- Publisher names are not standardized!
    - Ex: Wall Street Journal and Wall Street Journa; Huffinton Post and Huffpost; nytimes.com and nytimes
    - Suggestions: Standardized all publisher names: lower case, remove punctuation and ‘.com’, use fuzzywuzzy to match similar names (situations like Wall Street Journal and Wall Street Journa)
- If you are handling a large number of articles over many years, be aware of RAM usage as the dataset takes a lot of RAM and it will kill your terminal
    - Possible solutions: use high performance computing (HPC) environments, Colab high-RAM runtime for high RAM
    - Save your progress or dataset often; you can consider batch processing and save your data after each batch if still out of RAM or running processes that take a long time 
