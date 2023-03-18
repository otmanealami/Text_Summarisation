# Context
In this project, we worked on the Abstract Summarization task which consists in summarizing an abstract in two or three sentences. This task has become an important application of deep learning, using deep learning models such as Transformers. Our goal was to use this technique to summarize a set of scientific articles using pre-trained models of Transformers. Thus, we sought to answer the question, "Is it possible to efficiently summarize abstracts of scientific articles using pre-trained deep learning models?"

We started with a literature review to understand the different approaches used in the field of Abstract Summarization. We then selected several pre-trained models of Transformers and fit these models to our specific task using a training dataset.

We finally evaluated the performance of each model using standard evaluation measures such as RED, which is a widely used measure for evaluating the quality of summaries. The results of our experiments showed that Transformers' pre-trained models can be effectively used to summarize abstracts of scientific papers, with ROUGE scores as high as 0.4.





## State of the art
Models based on Transformers have revolutionized the field of natural language understanding and automatic language processing. Transformers have been successfully used for a variety of natural language processing tasks, including machine translation, text generation, and more recently, automatic abstract summarization of scientific papers.

The BERTSUM model proposed by Liu et al. (2019) is one of the first models to use Transformers for abstract summarization. This model uses a fine-tuning method with sentence selection to solve the problem of abstract length, selecting the most important sentences for the abstract.

The PreSumm model, proposed by Zhang et al. (2019), uses an encoder-decoder architecture to generate abstracts. This model also uses a sentence selection method, but also adds a sentence decomposition method to improve the quality of the generated summaries.

The Pegasus model, also proposed by Zhang et al. (2020), uses a pre-training and fine-tuning method to improve summary performance. This model uses a sentence decomposition method similar to PreSumm, but also uses a pre-training method on a large corpus of text data.

The T5 model, proposed by Raffel et al. (2020), is a model architecture that can be used to solve many natural language processing tasks, including abstract summarization. T5 uses a fill-in-the-blank task to pre-train the model on a large amount of text data, and then fine-tune the model for the abstract summarization task.

In terms of evaluation metrics, RED is widely used to evaluate the quality of generated abstracts. ROUGE measures the similarity between the generated abstract and the reference abstract using several similarity metrics such as word, sentence and subsequence similarity.

In conclusion, the Transformer-based models showed impressive performance for the abstract summarization task, with several approaches proposed to improve summarization performance. Sentence selection and sentence decomposition have been popular methods for improving the quality of summaries, and pre-trained models such as T5 have opened up new opportunities for automatic summarization applications in scientific research.

## Data Preprocessing 

The tokenize.py file defines the tokenize function that models the tokenization process for the text summarization task. The process consists of several steps:



* Lowercase: The input text is converted to lower case to standardize the text and reduce the number of unique tokens.
* Special Character Removal: All non-alphanumeric characters in the input text are replaced with a space. This step helps eliminate punctuation and special characters that add no semantic meaning to the text.
* Tokenization: The text is divided into individual words using the space as a delimiter.
* Stemming: An optional stemming process is applied to the tokens using a provided stemmer. Stemming reduces the words to their basic form, which can reduce the number of unique tokens and improve the efficiency of the subsequent analysis. However, in this implementation, stemming is only applied to words longer than 3 characters.
* Filtering: The last step filters out all invalid or empty tokens using regular expressions. Only alphanumeric tokens are kept, and all tokens that do not meet this criterion are discarded.

## Model Evaluation

First, we define : 
* The save_file function takes data and a file path as input, creates the directory if necessary, and saves the data to a file according to the extension provided. If the extension is .pkl, the data is saved using the pickle library, otherwise it is saved using the json library.

* The store_results function takes the name of a model and an evaluator object as input, creates a results directory for the model if necessary, displays and saves the results of the performance measurements using the evaluator object and calling the get_avg_stats_dicts, to_str, to_csv and plot_red_distributions methods. The results are saved using CSV and PDF files.

For the evaluation of the "Abstractive Summarizing" task The RED metric is often used to assess the quality of automatic summaries by comparing the similarity between generated summaries and reference summaries written by humans. The RED-1, RED-2, and RED-L scores measure the similarity between unigrams, bigrams, and the longest common subsequence between the generated summary and the reference summary, respectively.

The F-score, precision and recall scores measure different aspects of similarity. The F-score is the overall measure that combines precision and recall to assess the overall quality of the generated summary. Precision measures the proportion of generated terms that are also present in the reference summary, while recall measures the proportion of terms in the reference summary that were included in the generated summary.
