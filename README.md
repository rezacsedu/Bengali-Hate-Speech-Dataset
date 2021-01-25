# Bengali Hate Speech Dataset
This repository contains the Bengali Hate Speech Datasets, data collection and annotation process, and supplementary information. There are two versions of this dataset: version v1.0 and v2.0.

## Warning!
The data and lexicons contain contenst that are racist, sexist, homophobic, and offensive in many different ways. Datasets are collected and subsequently annotated only for research related purposes. Besides, authors don't take any liability if some statements contain very offensive and hatred statements that are either directed towards a specific person or entity, or generalized towards a group. Therefore, please use it with your risk. 

## Bengali Hate Speech Dataset v1.0
v1.0 of the "Bengali hate speech dataset" was prepared as a part of our paper titled "Classification Benchmarks for Under-resourced Bengali Language based on Multichannel Convolutional-LSTM Network", in proc. of [7th IEEE International Conference on Data Science and Advanced Analytics (DSAA,2020)](http://dsaa2020.dsaa.co/), October 6-9 2020, Sydney, Australia. This paper also won the [best application paper award at DSAA'2020](https://twitter.com/IEEEDSAA/status/1317599586341462016), which also can be accessed on [arXiv](https://arxiv.org/pdf/2004.07807.pdf) as pre-print.

### Collection of raw dataset
Bengali articles were collected from numerous sources from Bangladesh and India including a Bengali Wikipedia dump, Bengali news articles (Daily Prothom Alo, Daily Jugontor, Daily Nayadiganta, Anandabazar Patrika, Dainik Jugasankha, BBC, and Deutsche Welle), news dumps of TV channels (NTV, ETV Bangla, ZEE News), books, blogs, sports portal, and social media (Twitter, Facebook pages and groups, LinkedIn). Facebook pages (e.g., celebrities, athletes, sports, and politicians) and newspaper sources were scrutinized because composedly, they have about 50 million followers, and many opinions, hate speech and review texts come or spread out from there. Altogether, our raw text corpus consists of 250 million articles.  

### Hate speech data annotation
From the collected raw texts, two linguists and three native Bengali speakers annotated the datasets. We used a bootstrapping approach, which starts with an initial search for specific types of texts or articles containing common slurs and terms used about targeting characteristics. We manually identify frequently occurring terms in the texts containing hate speech and references to specific entities. Subsequently, we annotated 10,000 statements, texts, or articles, which directly or indirectly express hate speech, but in a semi-automated way. Inspired by the creative political slang, we prepared normalized frequency vectors of [175 abusive terms](https://github.com/rezacsedu/Bengali-Hate-Speech-Dataset/blob/main/bengali_slung_abusive.txt) that are commonly used to express hates in Bengali.

We assign the label hate if at least one of these terms exists in the text. We provide the annotators' unbiased-text-only contents to make the decision based on the criteria of the objective. However, we encountered numerous challenges, e.g., different types of hate exist in the regions, distinguishing hate speech from offensive language was very challenging as they are not the same, although they would have overlapping. Fortunately, certain types of hate were easy to identify and annotate based on CSPlang that are nonstandard word for Bengali, which conveys a positive or negative attitude towards a person, a group of people, or an issue that is the subject of discussion in political discourse and can be easily annotated as a political hates.

Finally, non-hate statements were removed from the list, and hates were further categorized into political, personal, gender abusive, geopolitical, and religious hates in which 3.5% of annotated texts were classified as hate speech, were rather low and resulting in about 3,418 statements labeled as hate. The annotations are further validated and corrected by three experts (one South Asian linguist and two native speakers) into one of two categories: hate and non-hate/inoffensive. To reduce possible bias, each label was assigned based on a majority voting on the annotator's independent opinions. To measure the agreement among multiple annotators (i.e., the inter-annotator agreement), we compute the [Cohen's Kappa statistics](https://en.wikipedia.org/wiki/Cohen%27s_kappa).

### Statistics and frequent words
Following figure shows the most frequently used terms that express different types of hates in Bengali: 

<p align="center"><img src="word_cloud_hate.png?" width="400" height="350"></p>

The dataset has 3,418 samples, which has the following distribution: 

| Personal hate | Political hate | Religious hate | Geopoitical hate | Gender abusive hate |
| ------------- | ------------- | ------------- | ------------- | -------------|
| 629           |     1771      |     502       |     1179      |     316      |

Following columns describe different types of hate (i.e., label column in the [CSV file](https://github.com/rezacsedu/Bengali-Hate-Speech-Dataset/blob/main/Bengali_%20Hate_Speech_Dataset_Subset.csv)):
| Personal Hate | Political Hate |  Religious Hate | Geopoitical Hate | Gender abusive hate |
| --------------------------| --------------------------| -------------| --------------------------| --------------------------| 
| Hatred comment towards or directed towards a specific person | Hatred comment towards or directed towards a political group or person | Hatred comment towards or directed towards a specific religion | Hatred comment towards or directed towards a specific country, continent, or regions| Hatred comment towards or directed towards a specific gender | 

Following are a few examples of Bengali hate speech, either directed or generalized towards a specific person, entity, or a group: 
<p align="left"><img src="hate.png?" width="850" height="400"></p>

### Authors and contributors:
* Md. Rezaul Karim - [Research Scientist, Fraunhofer Institute for Applied Information Technology FIT, Germany](https://www.linkedin.com/in/karimanalytics/).

* Sumon Kanti Dey - [Engineer Scientist at Leadbook](https://www.linkedin.com/in/sumon-kanti-dey-96321b10b/).

* Bharathi Raja Chakravarthi - [Postdoctoral Researcher and Adjunct Lecturer, National University of Ireland, Galway](https://www.linkedin.com/in/bharathi-raja-asoka-chakravarthi-7a520393/).

* John McCrae - [Insight Centre for Data Analytics, National University of IrelandGalway, Ireland](https://www.linkedin.com/in/john-mccrae-6653471b/).

* Michael Cochez - [Assistant Professor, Vrije Universiteit Amsterdam, the Netherlands](https://www.linkedin.com/in/michaelcochez/).

### Citation request
If you use the dataset for your research, please consider citing the folowing paper:

    @inproceedings{karim2020BengaliNLP,
        title={Classification Benchmarks for Under-resourced Bengali Language based on Multichannel Convolutional-LSTM Network},
        author={Karim, Md. Rezaul and Chakravarti, Bharathi Raja and P. McCrae, John and Cochez, Michael},
        booktitle={7th IEEE International Conference on Data Science and Advanced Analytics (IEEE DSAA,2020)},
        publisher={IEEE},
        year={2020}
    }   

## Bengali Hate Speech Dataset v2.0
The v2.0 is used in our paper "DeepHateExplainer: Explainable Hate Speech Detection in Under-resourced Bengali Language", which is currently under review in IEEE Access journal. The preprint version can be found and read on arXiv (https://arxiv.org/ftp/arxiv/papers/2012/2012.14353.pdf). 

### Data collections and annotation process
We extend the Bengali Hate Speech Dataset (https://github.com/rezacsedu/Bengali-Hate-Speech-Dataset) with additional 3,000 labelled samples. The Bengali Hate Speech Dataset categorized into political, personal, geopolitical, religious, and gender abusive hates. However, our empirical study and linguist analysis observe that distinguishing personal from gender abusive hate is often not straightforward, as they often semantically overlap. To justify this, our study observes that distinguishing personal hates from gender abusive hates was very challenging. Often statements that express hatred statements towards a person commonly used Benglai words that are directed mostly towards women.
Therefore, we treated the gender abusive hate statements as personal hate, followed by categorizing the samples into political, personal, geopolitical, and religious hate.

During the data collection, we follow the bootstrap approach for the data collection, where specific types of texts containing common slurs and terms, either directed towards a specific person or entity or generalized towards a group, are only considered. Texts were collected from Facebook, YouTube comments, and newspapers. Three annotators - a linguist, a native Bengali speaker, and an NLP researcher participated in the annotation process. To reduce possible bias, unbiased contents are supplied to the annotators and each label is assigned based on a majority voting on the annotator's independent opinions. To evaluate the quality of the annotations and to ensure the decision based on the criteria of the objective, we measure inter-annotator agreement w.r.t Cohen's Kappa statistic.

### Data availability
We made publicly available this dataset (https://github.com/rezacsedu/Bengali-Hate-Speech-Dataset), but only for research purposes. So, if you use the code of this repository in your research, please consider citing the folowing papers:

    @inproceedings{karim2020BengaliNLP,
        title={Classification Benchmarks for Under-resourced Bengali Language based on Multichannel Convolutional-LSTM Network},
        author={Karim, Md. Rezaul and Chakravarti, Bharathi Raja and P. McCrae, John and Cochez, Michael},
        booktitle={7th IEEE International Conference on Data Science and Advanced Analytics (IEEE DSAA,2020)},
        publisher={IEEE},
        year={2020}
    }   
      @article{karim2020deephateexplainer,
      title={DeepHateExplainer: Explainable Hate Speech Detection in Under-resourced Bengali Language},
      author={Karim, Md and Dey, Sumon Kanti and Chakravarthi, Bharathi Raja and others},
      journal={arXiv preprint arXiv:2012.14353},
      year={2020}
    }

### Authors and contributors:
* Md. Rezaul Karim - [Research Scientist, Fraunhofer Institute for Applied Information Technology FIT, Germany](https://www.linkedin.com/in/karimanalytics/).

* Sumon Kanti Dey - [Engineer Scientist at Leadbook](https://www.linkedin.com/in/sumon-kanti-dey-96321b10b/).

* Bharathi Raja Chakravarthi - [Postdoctoral Researcher and Adjunct Lecturer, National University of Ireland, Galway](https://www.linkedin.com/in/bharathi-raja-asoka-chakravarthi-7a520393/).

### Contributing
For any questions, feel free to open an issue or contact at rezaul.karim@rwth-aachen.de
