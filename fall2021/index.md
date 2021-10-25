# Computer systems(Database) \(CMP2242\) - Spring 2021

## Teaching Staff

Instructor: Dr. Mohamed Ibrahim.

Demonstrators:  Eng. Ayman Anwar.  


## Section Hours

| Section | Day | Time Slot |
|---------|-----|-----------|
|   1     | Wenesday | 1st  |
|   2     | Wenesday | 2nd |

## Office Hours

| Day | Time |
|-----|-----------|
| Thursday | from **12pm** to **6pm** |

extra office hours requested via E-Mail to **ayman.m.anwar@eng1.cu.edu.eg** (Subject : EXOFH)

## Course Outline

| Week | Content |  Tasks
|------|-----------------|-----|
|   1  | Introduction to full stack development and database management systems | ---- |
|   2  | ER model and basic SQL statements | ---- |
|   3  | Join statment | ---- |
|   4  | Introduction to python  | ---- |
|   5  | python  with mysql-connector | ---- |
|   6  | Midterm | ---- |
|   7  | Flask Apps | ---- |


## Required installations

visit [AMPPS](https://www.ampps.com/downloads) and download the latest version according to your distributions.

1. windows 
* for installation please follow regular installation steps (next >> next >> finish)
* please make sure you have internet connection during installation
2. Linux
* please make sure you have internet connection during installation.
type the following command after routing to download directory.
```
cd /download/location
chmod 0755 Ampps-<version>-<arch>.run
sudo ./Ampps-<version>-<arch>.run
```
To run ampps
```
sudo /usr/local/ampps/Ampps
```
## On startup
You should see something like this indicating the server has started properly.
![](images/amppsStart.png)

## common issues for LINUX installation

if you have a problem installing ampps on linux type the following:

```
cd /usr/local/ampps/apache/lib
sudo mkdir backup
sudo mv ./libapr* ./backup/
sudo apt-get -y install libaprutil1 libaprutil1-dev libapr1 libapr1-dev 
```
then restart your device and run the following every time you want to start it.

```
cd ~
sudo QT_X11_NO_MITSHM=1 /usr/local/ampps/Ampps 
```


## Tutorials

### SBE306

* Week 1
    * [Slides]({{ site.baseurl }}{% link fall2021/presentations/1_week1/index.md %}){:target="_blank"}
    * [notes]({{ site.baseurl }}{% link fall2021/notes/SBEw01.md %}){:target="_blank"}
    * Videos 
        * [part-1](https://drive.google.com/file/d/1g7Lq_ph9wHPUdiiLCMsD9eiXtd8X7TQc/view?usp=sharing)
        * [part-2](https://drive.google.com/file/d/1LguA_tJhiFX7cWYNBr_6mSPoqrHbvhLf/view?usp=sharing)
        * [part-3](https://drive.google.com/file/d/1HcEF0jvhsT_39NcyJuMtg2MJ2zTMQQmp/view?usp=sharing)

* Week 2
    * SQL statements
        * [notes]({{ site.baseurl }}{% link fall2021/notes/SBEw02.md %}){:target="_blank"}
        * [Videos](https://drive.google.com/file/d/1ZybuoOmKNO_EsxSbjZ27E14is1mBME4r/view?usp=sharing)
        
* Week 3
    * SQL Constrains
        * [notes]({{ site.baseurl }}{% link fall2021/notes/SBEw03.md %}){:target="_blank"}
        * [Videos](https://drive.google.com/file/d/1I5fYwk5DC4tIq5oJNObd6oYiSJO6sxW1/view?usp=sharing)
        
* week 4
    * python installation: [windows](https://docs.anaconda.com/anaconda/install/windows/) [Linux](https://docs.anaconda.com/anaconda/install/linux/)    
    * Python Introduction
        * [notes]({{ site.baseurl }}{% link fall2021/notes/SBEw04pythonIntroduction.md %}){:target="_blank"}
        * [Videos](https://drive.google.com/file/d/1s35Uk6ClMgZgpuTI5Tx09gE7h4hvR5ge/view?usp=sharing)
    * python quick source:[w3schools](https://www.w3schools.com/python/)
    * python exercises:[exercism](https://exercism.io/)

* week 5
    * Python mySQL
        * [notes]({{ site.baseurl }}{% link fall2021/notes/SBEw05pythonMysql.md %}){:target="_blank"}
        * [Videos](https://drive.google.com/file/d/1we9rIwgTtj3z7dDShztm_dpn_13p0fOe/view?usp=sharing)
    * HTML quick source:[w3schools](https://www.w3schools.com/html/default.asp)
    * CSS exercises:[w3schools](https://www.w3schools.com/css/default.asp)
    * Javascript exercises:[w3schools](https://www.w3schools.com/js/default.asp)

* week 6
    * mySQL Exercise:
        * [notes]({{ site.baseurl }}{% link fall2021/notes/SBEw06.md %}){:target="_blank"}
        * [Videos](https://drive.google.com/file/d/1vRASCxuPiETN4zBrIikrT68rFG5f9z4c/view?usp=sharing)

* Week 7
    * Basic Flask App:
        * [notes]({{ site.baseurl }}{% link fall2021/notes/SBEw07.md %}){:target="_blank"}
        * [Videos](https://drive.google.com/file/d/15U_qQhuADQ5j4DVhsdvv1p1gCA7_i3Nn/view?usp=sharing)

* Week 8
    * Dynamic Flask App:
        * [notes]({{ site.baseurl }}{% link fall2021/notes/SBEw08.md %}){:target="_blank"}
        * **Videos:**[part1](https://drive.google.com/file/d/1wc8tKi7nkLLnuL8QyWn4utnUxnYUHdf1/view?usp=sharing)[part2](https://drive.google.com/file/d/1DnHtbSPiBE7WpnOcRVm4arHmv4fM40L5/view?usp=sharing)

## Project

* [main-statement]({{ site.baseurl }}{% link fall2021/notes/SBEProjectStatment.md %}){:target="_blank"}
