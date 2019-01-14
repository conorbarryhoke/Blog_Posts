# Job Descriptions Analyzer

The goal of this project is to identify key words in job descriptions you are interested in. With these words you can improve keyword searches on sites like indeed, or tweak your resume to make sure it is emphasizing the elements that employers are looking for.

The primary notebook, Job_Description_Analyzer, is configured to run analysis on files contained in the appropriate folders, then output useful tables and word clouds. In the notebook, simply run all. 
## Methodology
### Simple Text Cloud
The basic idea is to load in job postings from Word or other text documents. Once the data is in the path Data/job_descriptions/, the notebook will read all files in the folder. It will collect these into a Word Cloud based on total word occurences, showing the most common words overall.

### Word Significance
A refinement of the above, the model then looks in Data/corpuses/for_baseline and picks up some baseline text to create a custom of TF-IDF vector. The current text base is from some random Reddit pages collected in September 2018 for a different project (The source subreddits for each post are in the file). This corpus is then used to develop a word frequency baseline.

The counts for each word from the first part are then divided by relative frequency from the Reddit corpus to get a 'Significance'. The idea is that we don't just want the overall count of a word - just about every post out there is looking for 'teamwork'. By identifying rare words that occur frequently in the job posts you're looking at, you can get a sense of what makes them unique.  

### Topic Analysis
In process.


## Data
By default, I have saved all of my job descriptions in word documents, however any text file should be fine.

I also used the naming convention Job Title - Company for the file names to make the resulting DataFrame more meaningful.
