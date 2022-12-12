# Generating a Network from a Wikipedia Page!

This project has the goal to generate a network from a single **Wikipedia** page (seed page) and to analyze how the pages are connected to each other based on different metrics. 

Due to the amount of computational power and time to process all data, we are only exploring the network until the second layer, which already include a lot of nodes and connections to be analyzed. 

Another goal of this project is to create a pipeline that receives a starting page from wikipedia and includes all the processing data phases. 


It's impotant to mention that this project is a collaboration between the students [Aryel Medeiros](https://github.com/aryelmedeiros) and [Deborah Moreira](https://github.com/deborahmoreira)


## Pipeline

The suggested data pipeline is consisted of 4 explicit steps: `Data Collecting`, `Data Cleaning`, `Truncate` and `Explore the Network*`. This last one is actually a "condensed" step that includes other tasks that analyze the network and generate graphs according to determined metrics. 

To define the pipeline we create a class and define the functions that represent each task as well as the corresponding task that it depends on to operate. This assures that the tasks will be executed in the correct order. 

## Data Collecting 
	
The first task of the pipe line receives the first wikipedia page to be explored. Then, using the wikipedia library the web scraping is performed to extract all the referenced pages in previous page to define the new nodes and connections of the network. 

Also, because of the numerous amount of pages that are connect and the huge amount of time that would take to process other layers of the network, we are only extracting nodes until the second layer. Moreover, we stipulated pages that are end point to the extraction by manually exploring the network, these pages are defined as `STOP` and should represents leaf nodes or nodes that possibly are not relevant to the original topic.

The seed page that we decided to explore in this project is the Wikipedia Page about Vertebrate. After the initial extraction of the network until the second layer, there were found around 2.8k nodes and 68k edges. 

## Data Cleaning 

After the initial definition of the nodes on the netwok, now we need to eliminate all duplicate nodes, nodes that are actually the same page and topic, the only difference would be the title having an extra 's'. Not only duplicate nodes, but we also remove all the loop edges, meaning a page that refers to itself. 
