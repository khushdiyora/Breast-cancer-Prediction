# Breast-cancer-Prediction

## What is meant by invasive ductal carcinoma? <a class="anchor" id="intro"></a>

<a title="Mikael Häggström, M.D. - Author info - Reusing images [CC BY (https://creativecommons.org/licenses/by/2.5)]" href="https://commons.wikimedia.org/wiki/File:Lobules_and_ducts_of_the_breast.jpg"><img width="309" alt="Lobules and ducts of the breast" style="float:left; margin:0px 15px 15px 15px" src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/47/Lobules_and_ducts_of_the_breast.jpg/256px-Lobules_and_ducts_of_the_breast.jpg"></a>


This illustration created [Mikael Häggström](https://commons.wikimedia.org/wiki/File:Lobules_and_ducts_of_the_breast.jpg) shows the anatomy of a healthy breast. One can see the lobules, the glands that can produce milk which flews through the milk ducts. Ductal carcinoma starts to develop in the ducts whereas lobular carcinoma has its origin in the lobules. Invasive carcinoma is able to leave its initial tissue compartment and can form metastases. 

## Motivation

Inasive ductal carcinoma (IDC) is - with ~ 80 % of cases - one of the most common types of breast cancer. It's malicious and able to form metastases which makes it especially dangerous. Often a biopsy is done to remove small tissue samples. Then a pathologist has to decide whether a patient has IDC, another type of breast cancer or is healthy. In addition sick cells need to be located to find out how advanced the disease is and which grade should be assigned. This has to be done manually and is a time consuming process. Furthermore the decision depends on the expertise of the pathologist and his or her equipment. Therefor deep learning could be of great help to automatically detect and locate tumor tissue cells and to speed up the process. In order to exploit the full potential one could build a pipeline using massive amounts of tissue image data of various hospitals that were evaluated by different experts. This way one would be able to overcome the dependence on the pathologist which would be especially useful in regions where no experts are available .      

## Our goal

As we started with this analysis we asked ourselves if we would be able to improve the results that were presented in 2024. 

## Methods presented in the paper

Collecting information... ;-)

* In the paper tissue slices of 162 patients were used all having IDC (113 used for training and 49 for validation)
* One pathologist was used to determine regions of IDC given a tissue slice 
* evaluation metric: F1 score and balanced accuracy


* Our goal: Given a patient and a patch of a tissue slice predict wheather it contains IDC or not.
    * 3 possibilities: healthy tissue, IDC, another subtype of breast cancer
* business case: prediction so far is done manually by pathologists and varies from expert to expert. The goal is to assist with an automatic detection of tumors (not expert dependent). 


## Table of contents

1. [What is meant by invasive ductal carcinoma?](#intro) 
2. [Preparation & peek at the data structure](#prep)
    * [Loading packages and settings](#setup)
    * [Exploring the data structure](#explorestructure)
3. [Exploratory analysis](#eda)
    * [What do we know about our data?](#data)
    * [Looking at healthy and invasive ductal carcinoma patches](#patches)
    * [Visualising the breast tissue](#tissue)
4. [Setting up the machine learning workflow](#workflow)
    * [Settings](#ml_settings)
    * [Validation strategy](#validation)
    * [Target distributions](#target_dists)
    * [Creating pytorch image datasets](#image_datasets)
    * [Creating pytorch dataloaders](#dataloaders)
    * [Defining the model structure](#model_structure)
    * [Setting up the loss function](#loss_eva)
    * [Selecting an evaluation metric](#e_metric)
    * [Building the training loop](#train_loop)
    * [Searching for an optimal cyclical learning rate](#lr_cycle_optima)
    * [Performing the training or loading results](#run)
5. [Exploring results and errors](#error_analysis)
    * [Loss convergence](#losses)
    * [The probability landscape of invasive ductal carcinoma](#landscape)
    * [Going into details](#details)
7. [Conclusion](#conclusion)



* * *

If you have suggestions, please feel free to contribute, looking forward to practice and learn more.

### Please refrain from using material for personal use, we sofely tell you. 

## If we find that this can be used for personal use, it must be illegal under the Copyright Law of India 2000 (Section 43 of the Information Technology Act, 2000). This project is not allowed to be changed in any way because it may contain copyright offenses. Instead, it is for Bussiness purposes.

## Section 43 of the Information Technology Act, 2000 contains:

## provides for compensation to the aggrieved party up to One Crore of Rupees from a person, who without the permission of the owner or the person who is in charge of computer, computer system or computer net-work secures, access to the system or down-loads data or down-loads ...

![Khush diyora](https://github.com/user-attachments/assets/36fe9f73-a9d7-49f6-b5db-8a10c32b24bc)


