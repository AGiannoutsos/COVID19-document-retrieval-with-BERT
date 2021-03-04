# COVID19-document-retrieval-with-BERT
This project is about developing a document retrieval system to return titles and the context of scientificpapers containing the answer to a given user question.
We will ve using CORD-19 ![CORD-19 dataset](https://ai2-semanticscholar-cord-19.s3-us-west-2.amazonaws.com/historical_releases.html) for the dataset which is the biggest corpus of academic papers about COVID-19 and related coronavirus research.

## About the project

In this project we will use and evaluate 4 different methods for creating contexual sentence embeddings. These embeddings then will be used to find the most semantically meaningfull document that relates to our question. 

The 4 methods are:

*  pre-trained BERT average output layer as embeddings
*  GloVe embeddings
*  pre-trained BERT large model on a corpus of messages from Twitter about COVID-19
*  pre-trained Sentence-BERT embeddings


## About the implementation

Fisrtly the data is ectracted from the dataset and a Pytorch dataset class is used to access the corpus. Then each model is defiend seperalty. The corpus is 
feed in every model and embeddings for every sentence in the documents are generated and stored and ziped in the cloud.
After the transformation of the corpus into vectors of words, follows the question answering part. 
We download the and unzip the embeddings of eery document per each embedding model method. Afterwards, we ask for a question. We transform the question into an 
embedding vector and we search with cosine similarity through the dataset the most similar sentence embedding to our question for each model method.
Finaly we can evaluate our results.

## Code and report
Code, comments and report exist in the notebook which you can open in Colab from here 



## Resources

CORD-19 dataset: https://www.aclweb.org/anthology/2020.nlpcovid19-acl.1.pdf

S-BERT paper: https://arxiv.org/pdf/1908.100Bert84.pdf

GloVe: https://nlp.stanford.edu/projects/glove/

Ηuggingface library: https://huggingface.co/bert-base-uncased

ΒΕΡΤ model paper: https://arxiv.org/abs/1810.04805

BERT pretrained on Twiiter for COVID related tweets paper: https://github.com/digitalepidemiologylab/covid-twitter-bert
