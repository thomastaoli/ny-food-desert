Food Desert in NYC

In this project, I tried to visualize the location of grocery stores in NYC and try to answer a simple question: where are NYC's food deserts.

Data Collection Process

While it soun

I compiled it in this working speedsheet as a raference, to collate the urls for the directory of every mall.

An interesting part of this process — I tried to use both ChatGPT and Google's Bard to automate the process of collating urls. What I found was that Bard was more able, and more accurate in this task.

With the time available for this project, I ended up only being able to expand the project to 70 malls in Singapore.

Scraping
My process was a bit haphazard, and on hindsight I should have planned it better, but I basically categorised the malls by the way their website was organised and also how the website loads the directory.

Then, I wrote code snippets for each category and used playwright to scrape the directory. The work can be found in the notebook scraping-shops.ipynb.

Cleaning
The cleaning was the hardest part. The problem was that I had over 5000 different shop names who many of whom may actually refer to the same franchise, but is presented differently, depending on the directory.

I experimented with a few approaches.

First, I tried to use ChatGPT to clean it. It was not able to directly parse through the entire dataset to pick out every single inconsistency. But it did help clean the low-hanging fruit.

Next, I tried to prompt ChatGPT to give me a code snippet that could run through every single shop name to see which shop names are similar. It suggested using the difflib library.

At this point, I thought it easier to manually clean it, so I went through the dictionary given by difflib to check through for inconsistencies within the dataset.

I then tried to use ChatGPT again to clean ones that I might have missed out. It then suggested to use an NLP package fuzzywuzzy. When I ran it, it gave me a dictionary of shops that it thinks are similar, with better accuracy.

However, I thought it easier to manually double check it using the dictionary given by fuzzywuzzy. However, on hindsight, I think there is potential with fuzzywuzzy to automate the cleaning process if I had understood it better and could tweak the threshold to finetune what it was pulling out.

The cleaning process can be found in the notebook cleaning.ipynb.

Data Analysis
I wanted to know if there might be a more meaningful way to analyse how generic the malls were. I asked ChatGPT to suggest a few approaches and first experimented with counting overlap of shops.

I then resorted back to the original methodology I used before, but I decided to also try to factor the scores by base 10 so that it's more understandable.

I then explored the data by plotting a few graphs with both plotly and datawrapper. Here, I found that a lot of the unique malls are actually located in central Singapore.

The analysis can be found in the notebook analysis.ipynb.

Learning Points
I think I could have managed this project a lot better. If I had planned out the scope of the projet earlier, I think I could have definitely completed scraping of more malls for the dataset.

I heavily relied on Generative AI for this project. I learnt that it can be extremely helpful with quick turnaround projects like this, especially when you need a quick grasp of the data, or need to quickly implement something you understand the logic of.

Future work
There were many things I should have done better for this project, and hope to work on in time to come.

I should have also seeked help earlier. One thing I did not mnage to resolve was understandig the math better.

In terms of analysis, many more questions came up during the exploration phase that I wish I had time to pursue.

The question itself of why the more unique malls are crowded in Singapore is a question that could warrant more reporting.

In terms of data, I would also have liked to play around with the relationship of "genericity" with the age and size of the mall.
