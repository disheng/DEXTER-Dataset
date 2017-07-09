# DEXTER-Dataset

This repository provides information to access 
the DEXTER Dataset described in VLDB2015 Research 
paper:

> DEXTER: Large-Scale Discovery and Extraction 
of Product Specifications on the Web 
[link](http://www.vldb.org/pvldb/vol8/p2194-qiu.pdf)

The dataset presents HTML pages collected by our 
focused crawler. The dataset is organised under the bucket dexter-pages in the 
following folders:

1. data
2. dexter_sources
3. dataset_local_categories.json

This dataset is complemental to the [DEXTER Specifications extraction](https://github.com/disheng/DEXTER) repository previously published.

## Data [Link](https://s3-eu-west-1.amazonaws.com/dexter-pages/data/)
	Under /data/*
	
The folder is organised in subfolder, a subfolder for each crawled website. 
Pages of a given website are stored as .gz files. Pages are stored with an incremental file number \<i>.txt.gz and the mapping between dumped file and original url is under an index.txt file. 

The index.txt file stores in each line a tab separated pair. Pairs are organised in \<i>.txt and <file_url>.

An example is:
<pre>
1.txt 	http://www.sample_website.com/productAAAA
2.txt 	http://www.sample_website.com/productBBBB
3.txt 	http://www.sample_website.com/productCCCC
</pre>

## Dexter Sources [Link] (https://s3-eu-west-1.amazonaws.com/dexter-pages/dexter_sources/)

	Under /dexter_sources/*

We provide also the output of the Dexter classification. 
Page urls are grouped in sources (pair \<category,website>),
the folder contains a single json file for each DEXTER classified source.

Files are named with the following pattern: \<category>_\<site>.json

File contains for each website a map with the following information:

1. "\<website_name>": list of pages urls
2. "entry_page": list of category entry page
3. "pages_number": number of pages

## Dataset Local Categories [Link](https://s3-eu-west-1.amazonaws.com/dexter-pages/dataset_local_categories.json)
	In dataset_local_categories.json

We present the locale categories crawled directly from the discovered websites. The file is a nested json that is organised as follows:
<pre>
{
	"site1": {
		"category_1": [
			url1,
			url2,
			...
		]
		...
	}, 
	"site2": {
	...
	}
</pre>

