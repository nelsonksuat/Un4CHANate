# Un4CHANate
Use this repository to analyze 4CHAN data downloaded from the InternetArchive 4CHAN data dumps. 

ABSTRACT

Data dumps of 4CHAN are available at the InternetArchive (https://archive.org/details/4plebs-org-data-dump-2024-01). The first notebook 'DATA_LOADER_4CHAN' chunks the large dump files and removes unnecessary columns and rows. The columns of interest for 'DATA_LOADER_4CHAN' are index columns 4 and 22, which contain the timestamp and the comment string (this can be adjusted manually). The notebook can extract a CSV file according to the desired timeframe. The second notebook '4CHAN_ANALYZER' consists of various methods to get insights into the 4CHAN data, utilizing Sentiment analysis, Topic modeling & Network analysis. 
