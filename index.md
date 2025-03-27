# Text-as-Data 
### Annabel Mendum
This is where I will record my progress on my final project for DACSS 758, Text-as-Data. 

## Blog Post 1 
My background is in sociology, and I’m especially interested in family sociology. I’m interested in household labor and queer family construction. For this project, I’m thinking about how I can investigate representations of family in media and see how they have evolved over time. I would like to see how portrayals of non-traditional families (single parents, step-families, adoption, queer parents, chosen families, etc.) are approached in media and see what I can learn about changing norms in American family life. 

My research question is: how have non-traditional family structures been portrayed in popular media over time, and what insights can we gain from these portrayals about changing norms and culture? 

To investigate this research question, I intend to use the TV Corpus available at English-Corpora.org. Since this is a very large corpus of TV show transcripts starting from the 1950s, I think it will have more than enough data for me to work with. I'm thinking of focusing on sitcoms, as I feel that they often are a good representation of what is considered normative, as well as what is considered to be funny, in popular culture over time. Additionally, I'm thinking of also looking at news media to see if similar trends show up between different types of media and understand to what extent conversations about family in news and popular culture overlap. To get a corpus of news media, I would turn to the Proquest databases; in particular, it seems like the GenderWatch database might be very useful. I don't think this would be too much work for data collection and processing, but I'm unsure if this idea to take a comparative approach might be too complicated down the line and if it would make more sense to focus on just one corpus. 


## Blog Post 2 
For this project, I would like to investigate how news media depicts families, especially non-traditional families such as single parents, stepfamilies, multi-generational families, queer families, adoptive/foster families, etc. I imagine that portrayals may change over time as well as being associated with the topics of news articles. However, I am still a bit unsure of if this research question is something I will reasonably be able to answer within the scope of this project. I wonder if it would be easier to look into gender representation in news, which I would also find very interesting. I think I may need to edit my research question as I understand more about what strategies are available in text analysis and start working with the data. 

I was looking into using local newspapers, specifically starting with the Amherst Bulletin, available from the UMass library via NewsBank. However, I was informed that text mining from this particular database is not allowed, so I am now trying to switch gears a little bit. Based on my communication with one of our librarians, I understand that I am allowed to use any ProQuest database for text mining, so I’ve been looking into my options there. ProQuest does provide access to some newspapers. I’ve been looking at the Boston Globe archive, which seems to be a reasonable option for me. So far, I’ve been able to acquire every Boston Globe article from 2010 that mentions the word “family.” I’m running into a few issues/questions. First of all, I’m not really sure how much data I need; I would like to have data from multiple years to be able to see if there are changes over time, but I wonder if that will get me too much data—in that case, how do I determine which articles to pick: a random selection, the most relevant, some other method? I also realize that just downloading articles that mention family may be problematic—there are undoubtedly some relevant articles that I’m missing. Another issue I’m running into is the format of documents. Currently, I’ve simply been downloading articles from ProQuest in 100-article chunks. Since each file has 100 articles, I don’t think there is a simple way to separate them back into separate articles after importing the text into R, although I might be able to separate at certain words if there are consistent headings, which I think there are. I also don’t have metadata for the articles, although some important information (such as date) is likely in my data and probably can be extracted. At this point, I’m wondering if I should proceed with the current format or try to web scrape the data instead, as it might be easier to separate articles, get metadata, and acquire a much larger number of articles this way. 

Since starting to look at ProQuest as a data source, I have now learned that ProQuest has its own platform specifically for text mining, called TDM Studio. I’m going to investigate this further, as it seems like the most promising way to access this data in an easy-to-use format; however, I don’t yet know if I’ll run into any new issues with TDM Studio. So far, I've created a dataset in TDM Studio, but it seems like it takes some time to process the documents before the dataset is ready for use, so I don't have any further progress with it as yet. 

## Blog Post 3
In this project, I am investigating the portrayal of families in news media using a dataset of Boston Globe articles. I am currently working with a dataset of 2024 articles which mention the word family; there are 7855 articles in my dataset at the moment, but it should not be difficult to expand this dataset if necessary (e.g., by getting multiple years of articles). 

Since my last blog post, I spent some time exploring TDM Studio, and I now have my environment and data set up and have been able to start the real work of the final project. 

As I began exploring the data, one of the first things I did was to visualize feature co-occurrence. 

![Screenshot 2025-03-26 101942](https://github.com/user-attachments/assets/6796ecb3-d40b-4fa9-a489-1765586dce11)


When looking at this graph, the first thing I noticed is that there are very strong relationships between words that seem to be describing houses or apartments. Since these are probably not very relevant to what I'm investigating, I might need to look into dropping housing listings from my dataset. Before I did that though, I wanted to look into what other topics are prevalent in my data. After fitting an LDA model with 10 topics, I looked at the relevant words associated with each topic. With lambda set to 0.2, the top ten words for each topic can be seen in the table below: 

![image](https://github.com/user-attachments/assets/8734b143-ec2e-47a8-9a51-4cea786b1453)


Each column represents a different topic, and it's clear that the LDA model is able to pick up on some topics that definitely make sense in the context of newspaper articles; in large part, these topics seem to mirror the sections of the newspaper. I then plotted the distribution of topics for the first document, shown here: 

![image](https://github.com/user-attachments/assets/66210fa7-99b0-48b9-a667-57c16e908140)


The first document is very heavily leaning towards topic five, which includes words such as funeral, survived, and beloved. The first document in my dataset happens to be an obituary, so seeing that it is full of words from topic five makes complete sense. Based on these results, I'm pretty happy with how well LDA worked for my data, although I may play around with it a bit more to see if there is a more ideal number of topics than 10. I'm also curious about going deeper into the data; can I subset the documents into the original topics and then fit another LDA model to find subtopics? 

At this point, I've largely just been playing around with applying the various tools we've learned in class to my data. I intend to do a bit more of that---I'm thinking of trying out clustering next---but after that, my next main goal is to determine which tools are most useful for answering my research question and optimize their use in my data analysis.
