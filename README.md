# Text-Similarity-Detecton-using-NLP

## Please visit my Portfolio page to get detailed explanation about this project - [Text_Similarity Detection](https://aishwaryakshirsagar.github.io/Portfolio_Website/post/chapter-6/)


<!-- ## For a detailed explaination of the project. Please refer this link - https://docs.google.com/document/d/1cq_UiXKnWqe90lb5A60ZOrKDloo1XNQ3/edit?usp=sharing&ouid=106624957789776254669&rtpof=true&sd=true -->

### In this project, , I have demonstrated the implementation of the code and methods that I have used to find similarity between the texts in the two columns in an unsupervised manner. 

* `Goal` → Text-Similarity-Detecton
* `Method Used` → Unsupervised Learning using Transformers
* `Field` → Natural Language Processing and Deep Learning

---
## Problem Description
Text-Similarity-Detecton using Natural Language Processing and Deep Learning

#### Similarity between Paragraphs

The dataset provided includes Unique Id, and the two columns of texts. 
Similarity scores were to be calculated between the texts of columns 1 and 2. Since the labels for the texts were not provided.
I opted for unsupervised way to get the results.
Here I used Sentence Transformers-BERT sentence embeddings using Siamese BERT Network.

<img src="https://miro.medium.com/max/1104/1*7A2tpPCmNFy3Ii5F9ZJj3w.png" width="700" height ="550"> 
Bert is a self-attention model and does not use sequence to sequence aligned RNNs. Traditional Attention was used in combination with RNNs to improve their performance. Self-attention is used INSTEAD OF RNNs and they do a much better job and are also much faster. So in that sense they are pretty different.

As the paragraph size was crossing the 510 token limit (512 - after starting and ending tokens are added) of typical Transformer BERT architecture.
I tried to explore various things which could be used in order to reduce the text size without actually changing the meaning of the texts.
After researching, I came across Text abstraction. This method is better than other methods I came across previously which also provides data preprocessing facilities.
Implemented the Pegasus text abstraction method to summarize each paragraph in text1 and text2.
Refer this link:
https://towardsdatascience.com/pegasus-google-state-of-the-art-abstractive-summarization-model-627b1bbbc5ce

Luckily with this method I was able to reduce the document size within the token limit. 
I implemented this in batches of 500 rows for each iteration on Google Colab which provided limited GPU access and runtime constraints.
So in the codefile, there are 2 cells with both text1 and text2 summaries.
Used Siamese BERT Network which is a neural network which takes 2 different texts in tandem to give output of 2 vectors. Each vector the result of embeddings created.
I used cosine similarity method to get the difference between the vectors.

<img src="https://th.bing.com/th/id/R.a6aa56b92e497148c0d0dea140770462?rik=8%2bUlFD8YqBHesw&riu=http%3a%2f%2fdataconomy.com%2fwp-content%2fuploads%2f2015%2f04%2fFive-most-popular-similarity-measures-implementation-in-python-4-620x475.png&ehk=eaiVTD7h%2bqaVcnR%2b398ZX64sTc3s437ZRde35%2fJEKC8%3d&risl=&pid=ImgRaw&r=0" width="700" height ="550"> 


<!-- <img src="https://user-images.githubusercontent.com/67967781/138293539-a829234d-80ab-4634-92d4-cbf392405f9b.png" width="300" height ="500">
 -->
<!--  
 
<!--  
## Requirements
| Languguage & Library | version|
| :-------- | :------- |
| `python` | `3.7.11` | 
| `pandas`     | `1.1.5`|
| `numpy`      | `1.19.5`|
| `cv2`      | `4.5.3`|
| `os`      | `--`|
| `tqdm`      | `4.59.0`|
| `sklearn`    | `3.2.2`|
| `tensorflow` | `2.5.0`|
| `keras`      | `2.5.0`|
| `matplotlib` | `0.22.2.post1`|
| `YOLOv4`  |Version 4|
|`OpenCV`|
|`HTML`|
|`CSS`|
|`Flask`| -->

| Enviroment | Used|
| :-------- | :------- |
| `Editor`  |`JupyterLab`| 
| `Runtime type` | `CPU`| |'GPU'|`Google Colab`|
