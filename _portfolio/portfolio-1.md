---
title: "Identifying Covid-19 positive individuals using respiratory and talking sounds of an individual"
excerpt: "This project is a web application and mobile application that saves user-profiles and detects covid-19. The aim of the research is to use it as a pre-screen tool before taking a PCR test"
collection: portfolio
---

###### Sophomore Year
<img src='/images/covid.png'>
<br>
This a group project, where I led 3 members. I played a role in building the data science part of this research project.  This project is a web application and mobile application that saves user-profiles and detects covid-19. The aim of the research is to use it as a pre-screen tool before taking a PCR test. The user has to record six types of sounds such as follows: Shallow cough, Shallow breathing, heavy cough, vowel E, vowel O, fast counting(from 1 to 10)
These sounds are pre-processed and converted to mel-spectrograms and are passed into the Convolutional Neural Network model. There are 6 unique CNN for each 6 sound. They are ensembled to give the prediction of this binary classification. The model is evaluated to have 72% of accuracy and an F1 score.
Limitation-data sparsity leading to model overfitting </br>

[![](https://img.shields.io/badge/Python-white?logo=Python)](#) [![](https://img.shields.io/badge/Jupyter-white?logo=Jupyter)](#) [![](https://img.shields.io/badge/Tensorflow-white?logo=Tensorflow)](#) [View code on github](https://github.com/kirthikasena/Covid_project) [![](https://img.shields.io/badge/Github-black?logo=Github)](#)

---

