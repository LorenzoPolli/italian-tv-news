# Italian TV News
Sentiment Analysis and Topic Modelling of three popular Italian TV news.

## Sentiment Analysis
For the Sentiment Analysis part, I used two different classifiers to evaluate polarity of my text corpora.
For what concerns the **FEEL-IT** classifier, please refer to this link https://github.com/MilaNLProc/feel-it.
For what concerns the **SentITA** classifier, please refer to this link https://github.com/NicGian/SentITA.

To install **FEEL-IT**:
```sh
pip install -U feel-it
```

To install **SentITA** it is necessary having installed or downgraded Python from a more recent version to the version 3.6. The model requires also Keras 2.2.4, Tensorflow 1.11 and Spacy 2.0 to run properly. 
The package Sentita 0.2.0 can be dowloaded from a link present at the GitHub repository of the creator (see above). It is a compressed file (.zip format). 

Instructions to install it:
1. Unzip the .zip file
2. Activate your virtual environment
3. *cd* into the unzipped folder from the console
```sh
cd sentita_0.2.0 > sentita
```
4. Type in the console "pip install ." and the package will be installed locally.
```sh
pip install .
```

### Possible issues
Once the function "calculate_polarity" is called in your editor, it is possible an error message occurs.
It says "OSError: can't find model 'it'".

First, remember to install the default trained pipeline package available in the Spacy website.  
```sh
python -m spacy download it_core_news_sm
```
If you want to work with a more precise package, which includes word vectors, upgrade Spacy to version 3.1.0 and consequently run in the console
```sh
python -m spacy download it_core_news_md
```
After this operation is done, download/upgrade the h5py package to version 2.10.0.

Finally, open the folder where your virtual environment is installed and at the following directory 
```sh
lib > site_packages > sentita > __init__
```
open the \_init_ file and substitute 
```sh
nlp = spacy.load('it')
```
with the pipeline package you have downloaded. E.g.
```sh
nlp = spacy.load('it_core_news_md')
```
You can now use the **Sentita** package to perform Sentiment Analysis.

Other useful packages that I have installed together with their dependencies are Pandas and Matplotlib.

## Topic Modelling
For this part, in addition to some of the aforementioned packages, it is necessary to install scikit-learn in order to apply **LDA and NMF**. If you want to filter out stop words and visualize nice word clouds, it is also necessary to install the stop_words and wordcloud packages.

Nevertheless, to install all the packages used to develop my project, you can find the requirements.txt file under my project repository and save the content on your computer. Then, just follow the next steps
1. Activate your virtualenv
2. *cd* to the directory where requirements.txt is located
3. Run in your console
```sh
pip install -r requirements.txt
```
...and all is ready at once!

## Contact
Lorenzo Polli - lorenzo.polli1@studenti.unimi.it - https://www.linkedin.com/in/lorenzopolli-1996/

Project Link: https://github.com/LorenzoPolli/italian-tv-news
