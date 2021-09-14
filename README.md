# Extractive_QA_Pipeline

**Please note, the main purpose of this series of notebook is to explain the procedural steps required in building extractive QA pipeline using pre-trained and fine-tuned models with Elasticsearch and Haystack.  Do not be surprised if the overall performance of the pipeline does not improve compared to the baseline "bert-base-uncased" model as our training corpus is very small.**

In this repository we'll explore the process of building an open-domain extractive question and answer pipeline.  We'll be conducting continual pre-training of vanilla bert models (ie. bert-base-uncased), fine-tuning using Squad2 and a custom dataset, and using Elasticsearch and Haystack to explain the process of scaling QA pipelines for very large number of documents.

1. In the first notebook (#1 NAME), we'll build a extractive retriever-reader pipeline using Elasticsearch and Haystack.  We'll be using a sample employee handbook as the corpus for our contexts.  All models, including DPR models for denser vector representation and reader model will be pre-trained and fine-tuned models obtained from Huggingface.io.  

3. In the second notebook (#2 NAME), we'll apply continual pre-training to the "bert-base-uncased" model using the previously described sample employee handbook corpus.  It is important to remember the continual pre-training of the "bert-base-uncased" model is not another name for "fine-tuning".  By continuing to pre-train the model we hope to improve the contextual word embeddings above and beyond what the standard "bert-base-uncased" model provides.  Furthermore, as mentioned previously this series of notebooks is meant to provide a procedural example of the steps in building extractive QA models using Elasticsearch and Haystack.  Our employee handbook corpus is extremely small in-comparison to the amount of data used to train the original "bert-base-uncased" model.  Therefore, don't be surprised if new pre-trained model does not increase in performance.  

4. In the third notebook (#3 NAME), we'll use the further-pretrained model developed in the previous notebook (#2 NAME) and fine-tune the model for a Question/Answering task.  We'll use the Squad2 dataset to fine-tune our model.

5. In the fourth notebook (#3.1 NAME), we'll repeat the process of fine-tuning our model, however, instead of using Squad2 we'll use our sample employee handbook.  We have used Haystack's QA annotation tool which allowed us to create a dataset of questions/answers/contexts from our sample employee handbook corpus.  The data is in the same format as Squad2.

6. In the fifth notebook (#4 NAME), we'll use Elasticsearch and Haystack to build a scalable QA pipeline.  We'll try two readers, one using the Squad2 fine-tuned model and one using the employee handbook fine-tuned dataset.


