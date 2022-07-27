# Python_HealthCare_DataExtraction

Problem statement
-----------------------------------------------
According to government regulations, health insurance providers must follow a number of steps in order to process claims. To achieve this, they must process patient data images and prescription images sent by hospitals or independent doctors and extract relevant information from them. The majority of insurance companies outsource workforce from companies like "Avis data Analytics" to manually extract the data from images for these processes.

Avis Data Analytics use software that displays scanned images of patient information or prescriptions. The user must manually enter the information after looking at the image in the right-hand column and choosing the appropriate information type. Because it is a manual procedure, errors will be frequent, and the same number of workers won't be able to handle the massive set of photographs like during the pandemic. Additionally, the insurance companies have asked that the data be sent within 24 hours of being sent for extraction. All of these limitations compelled Avis Data Analytics to consider about replacing their outdated software.

Solution approach
---------------------------------------------
To solve all these problems, we are building a program which can do the extraction of data from images automatically. As always, machines can not replace humans. A person will recheck the extracted data and submit. So, that it will save a tremendous amount which was taken to type the data manually.

Here, we are using the Python programming language and pytesseract google library for extracting the data and Regex module to process the data and get distilled desired output.


Technologies used
-------------------------------------------
• Python

• oops

• Pdf2image module

• Opencv

• pytesseract

• Regular expression

• pytest

• Postman

• FastApi

Work Flow
-----------------------------------------------
![workflow](https://user-images.githubusercontent.com/34138198/181340063-4480be22-a06d-4770-8669-f9cfbcc8f022.jpg)

PDF to Image
-----------------------------------------------
For converting PDF to image, we have used pdf2image library.

Without preprocessing extracting data
Tried extracting data from source files without any processing, as they are not in proper format to be extracted, the extracted data was not as expected.


![dark_image](https://user-images.githubusercontent.com/34138198/181340516-e22e0901-512c-4307-8971-93cda468094a.jpg)
--------------
Extracted data from the above image
-------------------------
Dr John Smith, M.D
2 Non-Important Street,
New York, Phone (000)-111-2222

Name: Maria Sharapova Date: 5/11/2022

Address: 9 tennis court, new Russia, DC

—momennannenncmneneunnmnnnnninsissiyoinnitnahaadaanih issn earnttneenrenen:

Prednisone 20 mg
Lialda 2.4 gram

3 days,

or 1 month

Image processing
-------------------------------
we decided to preprocess the image using opencv module, before extracting data from them. For that we have first used normal thresholding and checked, which resulted in below image.
![filter_dark](https://user-images.githubusercontent.com/34138198/181340924-e7712603-e23a-426c-87c5-2cf27c395c7c.jpg)


Therefore, the typical thresholding will fade out the area if there is any shadow or noise. which will lead to data loss.

We choose to apply the adaptive thresholding technique in our hunt for a better solution to this issue. This method divides the image into smaller images and applies a different thresholding value to each smaller section. And when compared to conventional thresholding, the outcome of adaptive thresholding is far superior.

![adaptive_filter_dark](https://user-images.githubusercontent.com/34138198/181341127-5a0834e0-f62b-43b7-9f54-108c98dd27d1.jpg)

After preprocessing the image data extraction
---------------------------------------------------
Dr John Smith, M.D
2 Non-Important Street,
New York, Phone (000)-111-2222

Name: Marta Sharapova Date: 5/11/2022

Address: 9 tennis court, new Russia, DC

K

Prednisone 20 mg
Lialda 2.4 gram

Directions:

Prednisone, Taper 5 mg every 3 days,
Finish in 2.5 weeks a
Lialda - take 2 pill everyday for 1 month

Notebook
-----------
For all these above trials, used jupyter books and developed the small bits of the functionalities., which can be used later while designing the class.

OOPS design
------------------
The code was written in using OOPs concepts for extracting the medical data from prescription and patient details documents.

Regular expression
-------------------
using regular expression module we can match the patterns and extract the data we want from the files. For this project, analyst the medical files and as fact all the medical documents will follow same pattern, we wrote patterns that match only the required data. Before writing the python code, It is advisable to practise and match the patterns in regex 101 website.

Test driven Development
--------------------------
In this project test driven development methodology was used to develop the code. For testing pytest module was used. For all the methods and final result the test cases was designed and checked simultaneously while developing the code.


FastApi
------------------------------
Used FastAPI for hosting the server of the project. FastApi, as name suggest is help us to develop fast and some other advantages are,

In build Data validation
In build Documentation
Fast running and performance

Postman
---------------------------------
As it is a backend project, not developed frontend part. For checking how the server responds for http requests, used postman to trigger http requests and tested the outcome.
<img width="960" alt="postman" src="https://user-images.githubusercontent.com/34138198/181341744-471ddd34-7cc3-4dbe-94f2-ef0837236488.png">

Result
-----------------------
This backend functionality can be integrated into the Avis Analytics existing software and data can be extracted automatically. The extracted data may have some errors, the person who is performing the work has to correct it and submit the response.

Benefits
Avis Analytics can save at least of 30 secs for each document. It is small amount of time when looking for one document, but cumulatively it can save a tremendous amount of time which can help the company to complete more documents within the given time and make more profit
The company doesn't have to hire extra people in the season time.
As it is a combination of automation and manual the error will be very much low.

