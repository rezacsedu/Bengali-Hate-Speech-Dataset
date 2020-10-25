# Bengali-Hate-Speech-Dataset
This is the subset of the "Bengali hate speech dataset", which was prepared as a part of our recently accepted paper titled "Classification Benchmarks for Under-resourced Bengali Language based on Multichannel Convolutional-LSTM Network", in proc. of [7th IEEE International Conference on Data Science and Advanced Analytics (DSAA,2020)](http://dsaa2020.dsaa.co/), October 2020, Sydney, Australia. This paper also won the [best application paper award at DSAA'2020](https://twitter.com/IEEEDSAA/status/1317599586341462016). The pre-print of the paper can be accessed on [aRxiv](https://arxiv.org/pdf/2004.07807.pdf). Once ready, we'll make publicly accessible the full dataset.

## Collection of raw datset
First, Bengali articles were collected from numerous sources from Bangladesh and India including a Bengali Wikipedia dump, Bengali news articles (Daily Prothom Alo, Daily Jugontor, Daily Nayadiganta, Anandabazar Patrika, Dainik Jugasankha, BBC, and Deutsche Welle), news dumps of TV channels (NTV, ETV Bangla, ZEE News), books, blogs, sports portal, and social media (Twitter, Facebook pages and groups, LinkedIn). We also categorized the raw articles for ease preprocessing for a later stage. Facebook pages (e.g., celebrities, athletes, sports, and politicians) and newspaper sources were scrutinized because composedly, they have about 50 million followers, and many opinions, hate speech and review texts come or spread out from there. All text samples were collected from publicly available sources. Altogether, our raw text corpus consists of 250 million articles. If you want to get the access to full raw dataset, please write an email, with justification, at rezaul.karim.fit@gmail.com.  

## Hate speech data annotation
From the collected raw texts, two linguists and three native Bengali speakers annotated the datasets. We used a bootstrapping approach, which starts with an initial search for specific types of texts or articles containing common slurs and terms used about targeting characteristics. We manually identify frequently occurring terms in the texts containing hate speech and references to specific entities. Subsequently, we annotated 10,000 statements, texts, or articles, which directly or indirectly express hate speech, but in a semi-automated way. In particular, inspired by the creative political slang, we attempted to annotation. We prepare normalized frequency vectors of [175 abusive terms](https://github.com/rezacsedu/Classification_Benchmarks_Benglai_NLP/blob/master/bengali_slung_abusive.txt) that are commonly used to express hates. 

We assign the label hate if at least one of these terms exists in the text. We provide the annotators' unbiased-text-only contents to make the decision based on the criteria of the objective. However, we encountered numerous challenges, e.g., there exist different types of hates in the regions, distinguishing hate speech from offensive language was very challenging as they are not the same, although they would have overlapping. Fortunately, certain types of hate were easy to identify and annotate based on CSPlang that are nonstandard word for Bengali, which conveys a positive or negative attitude towards a person, a group of people, or an issue that is the subject of discussion in political discourse and can be easily annotated as a political hates.

<p align="center"><img src="word_cloud_hate.png?" width="500" height="400"></p>

Finally, non-hate statements were removed from the list, and hates were further categorized into political, personal, gender abusive, geopolitical, and religious hates in which 3.5% of annotated texts were classified as hate speech, were rather low (3.5%) resulting in 35,000 statements labeled as hate. The annotations are further validated and corrected by three experts (one South Asian linguist and two native speakers) into one of two categories: hate and non-hate/inoffensive. To reduce possible bias, each label was assigned based on a majority voting on the annotator's independent opinions. To measurement the agreement among multiple annotators (i.e., the inter-annotator agreement), we compute the [Cohen's Kappa statistics](https://en.wikipedia.org/wiki/Cohen%27s_kappa).

## Dataset statistics and frequent words
The following figure shows the most frequently used terms expressing hates; whereas, the statistics can be found in table 1.

| Language  |  UTF-8 | Vector Size | Corpus Size  | Vocabulary Size | 
| ---       |---        |---           |---           |---           |
|[Bengali (BengFastText)](https://drive.google.com/open?id=1Q_45PQpRWQvZL2p8sIngmgg6Tr5YbKmH) \| [Bengali (f)](https://drive.google.com/open?id=1Q_45PQpRWQvZL2p8sIngmgg6Tr5YbKmH)|bn|300|250M |30059| negative sampling |

## Citation request
If you use the dataset for your research, please consider citing the folowing paper:

    @inproceedings{karim2020BengaliNLP,
        title={Classification Benchmarks for Under-resourced Bengali Language based on Multichannel Convolutional-LSTM Network},
        author={Md. Rezaul Karim, Bharathi Raja Chakravarti, John P. McCrae, and Michael Cochez},
        conference={7th IEEE International Conference on Data Science and Advanced Analytics (IEEE DSAA,2020)},
        year={2020}
    }

## Contributing
For any questions, feel free to open an issue or contact at rezaul.karim@rwth-aachen.de
