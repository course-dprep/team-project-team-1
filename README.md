# **IMDB - the impact of runtime on average rating**
This project examines the relationship between the runtime and average rating of movies. We prepared IMDB data to analyze this.

## __Motivation__
Movies have a range of different runtimes. The longest movie ever made was over 35 days long (Lyon, 2023), while one of the shortest movies ever made was only 100 seconds long (Acuna, 2014). Even though these movies are definitely exceptions when it comes to runtimes, it does show the big range that exists in the movie industry. According to Follows (2021) "half of all Hollywood movies are between 96 and 120 minutes long, with the most popular running time being 101 minutes". 

__Relevance__ </br>
We want to know if the length of the movie runtime influences peoples opinion (average rating) about the movie. The results of this project can give useful insights to, for example, movie production companies and streaming services, into how the run times of their movies affect ratings, and with that likely, the popularity and profitability of their movies.    

## __Method and results__
For this research, the following research question was formulated: *What is the relationship between the runtime and the average user rating for movies?* 

To answer this question we make use of data from imdb.com, in specific the datasets 'title_basics.tsv' and 'title_ratings.tsv', which were downloaded from the following website: https://datasets.imdbws.com. 
The variables that were used for the analysis of our research question, were the following:

| Variable       | Description |
|------------|-----|
| titleType | the type/format of the title (e.g. movie, sohrt, tvseries, tvepisode, video, etc.  |
| primaryTitle   | the more popular title/the title used by the filmmakers on promotional material at the point of release  |
| runtimeMinutes | primary runtime of the title, in minutes |
| averageRating | weighted average of all the indidivual user ratings |

To analyse the data the program Rstudio was used. After downloading the data into Rstudio, the two datasets were merged into one dataset, 'data_merged.csv'. This merged dataset was used when cleaning our data. In cleaning the data, it was made sure that only movie data was left (e.g. excluding series), and observations with missing values for relevant variables (runtime and average rating) were removed. The dataset was extended with a variable that classifies movies as 'short' or 'long', and a variable that shows standardized ratings. Lastly, the analysis included assumption checks and the examination of the research question using a linear regression.  

## __Repository overview__
```
├── README.md 
├── data 
├── gen 
│   ├── analysis 
│   ├── data-preparation 
│   └── paper 
└── src 
    ├── analysis 
    ├── data-preparation 
    └── paper 
```

## __Prerequisites__
- R [Installation Guide](https://tilburgsciencehub.com/building-blocks/configure-your-computer/statistics-and-computation/r/)
- Make [Installation Guide](https://tilburgsciencehub.com/building-blocks/configure-your-computer/automation-and-workflows/make/)
- Pandoc [Installation Guide](https://pandoc.org/installing.html)

For R, the following packages are used:
```
install.packages(dplyr)
install.packages(tidyverse)
install.packages(car)
install.packages(lmtest)
```

## __Running instructions__
### __Step by step__
In order to run the code of this project, please follow these instructions:

_Step 1._ Fork this repository </br></br>
_Step 2._ Open your command line / terminal and run the following code: </br>
```git clone https://github.com/{your username}/movie-runtimes-on-average-rating_IMDB.git``` </br></br>
_Step 3._ Set your working directory to movie-runtimes-on-average-rating_IMDB and run the following command: ```make``` </br>

_Optional:_ To clean up all raw and unnecessary data files created during the pipeline process, run the following code in your command line / terminal: ```make clean```

_Note:_ the pipeline process wil not work anymore once you close your command line/terminal.

### Alternative way
In case you wish to run the code in a more manual way, you can replace step 3 by running the code files in the order below:
- ../src/data-prepraration/download_data.R
- ../src/data-prepraration/merge_data.R
- ../src/data-prepraration/clean_data.R
- ../src/analysis/model_results.R

## __More resources__
For this project, we used the following resources:
- Course material from [Data Preparation & Workflow Management](https://dprep.hannesdatta.com/) (Open Science course by dr. Hannes Datta)
- Installation guides and Principles of Project Setup and Workflow Management from [Tilburg Science Hub](https://tilburgsciencehub.com/tutorials/reproducible-research-and-automation/principles-of-project-setup-and-workflow-management/project-setup-overview/)

## __Last updated__
11 October 2023

## __About__
Thank you for your interest in our project! This project is part of our 'Data Preparation & Workflow Management' course at Tilburg University. The contributors are part of team 1, which consists of:
- [Lindsey Coover](https://github.com/lindseycoover) (l.e.coover@tilburguniversity.edu)
- [Renée Minten](https://github.com/ReneeMinten) (r.c.c.minten@tilburguniversity.edu)
- [Marlie Snoeijen](https://github.com/marliesnoeijen) (m.p.c.snoeijen@tilburguniversity.edu) 
- [Nikki Valen](https://github.com/NCPEValen) (n.c.p.e.valen@tilburguniversity.edu)
- [Fleur van Vugt](https://github.com/fleurvanvugt) (f.e.v.vanvugt@tilburguniversity.edu)
