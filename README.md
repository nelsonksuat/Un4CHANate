# Un4CHANate
Use this repository to analyze 4CHAN data downloaded from the InternetArchive 4plebs 4chan data dumps. 

ABSTRACT

Data dumps of 4chan are available at the InternetArchive (https://archive.org/details/4plebs-org-data-dump-2024-01). The first notebook 'DATA_LOADER_4CHAN_v2' chunks the large dump files and removes unnecessary columns and rows. The columns of interest for 'DATA_LOADER_4CHAN_v2' are index columns 4 and 22, which contain the timestamp and the comment string (this can be adjusted manually). The notebook can extract a CSV file according to the desired timeframe. The second two notebooks 'DATA_ANALYSIS_4CHAN_I_' and 'DATA_ANALYSIS_4CHAN_II' consist of various methods to get insights into the 4CHAN data, utilizing Sentiment analysis and Topic modeling both utilized over time. 

The notebooks have been tested on Python 3.11. 


The **DATA_LOADER_4CHAN_v2.ipynb** is designed to process and extract data from 4plebs archives of a specified 4chan board. The notebook is structured into three main code cells:

*Unix Timestamp Conversion:* The first code cell converts the selected timeframe's dates into Unix timestamps. These Unix values are essential because the 4plebs dataset uses Unix timestamps as the standard time format. Transforming these Unix values beforehand would cost a lot of extra processing power that is why there was chosen to do that operation in the second notebook.

*Dataset Chunking and Cleaning:* The second code cell divides the large dataset into manageable chunks, each containing up to 10 million rows. Within each chunk, the cell performs the following operations: it retains only the timestamp and corresponding comment columns, removes any unnecessary columns, and applies a regular expression (regex) to filter out comments that begin with ">>". These comments were found to only contain reply IDs, which are not relevant for our data analysis. This chunking and cleaning process is repeated until the entire dataset is processed and saved as individual CSV files in a specified folder.

*Merging and Filtering:* The third code cell inspects the folder containing the processed CSV chunks. It filters the rows based on the Unix timestamp range defined in the first cell and merges the relevant chunks into a final dataset. This resulting dataset contains all timestamps and comments that fall within the user-specified timeframe.

This structured approach ensures efficient handling of large datasets and produces a clean, time-specific dataset for further analysis.

DATA_ANALYSIS_4CHAN_I_Performs topic modeling on a selected portion of the dataset and appends the extracted topics to the original dataset.

DATA_ANALYSIS_4CHAN_II_ Conducts sentiment analysis using DistilBERT on comments associated with the most relevant topics.

Example of the analysis done by this repository:

![WhatsApp Image 2025-01-30 at 14 47 51 (1)](https://github.com/user-attachments/assets/f0771737-ff1a-4353-8443-01304ed334af)
![WhatsApp Image 2025-01-30 at 14 47 51](https://github.com/user-attachments/assets/dd542d05-5888-4f4d-84c6-4ec725f57133)



