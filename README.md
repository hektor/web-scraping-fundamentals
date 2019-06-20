# **Python Web Scraping fundamentals**

Hektor Misplon

# Repo Structure

``` 
├───assets
│   ├───docs
│   │   └───examples (example tutorials)
│   └───images
└───examples (example code)
```

# Table of contents
- [**Python Web Scraping fundamentals**](#Python-Web-Scraping-fundamentals)
- [Repo Structure](#Repo-Structure)
- [Table of contents](#Table-of-contents)
  - [Web Scraping](#Web-Scraping)
  - [Python Web Scraping Tools](#Python-Web-Scraping-Tools)
    - [**Scrapy** (framework)](#Scrapy-framework)
      - [**+ Pros**](#Pros)
      - [**+ Cons**](#Cons)
    - [Urllib2 - HTTP module (reading/opening web pages)](#Urllib2---HTTP-module-readingopening-web-pages)
    - [Requests - HTTP module](#Requests---HTTP-module)
    - [BeautifulSoup](#BeautifulSoup)
    - [lxml](#lxml)
    - [selenium - automated web application testing](#selenium---automated-web-application-testing)
- [Practical aproach](#Practical-aproach)
  - [Scrapy Installation](#Scrapy-Installation)
    - [Linux](#Linux)
    - [Mac](#Mac)
    - [Windows](#Windows)
  - [Scrapy basics](#Scrapy-basics)
    - [CLI (command line interface)](#CLI-command-line-interface)
    - [Creating a Scrapy project](#Creating-a-Scrapy-project)

## Web Scraping

## Python Web Scraping Tools

### **[Scrapy](https://scrapy.org/)** (framework)

#### **+ Pros**
+ complete web scraping solution
+ built on top of **[Twisted](https://twistedmatrix.com/trac/)** library (= asynchronous networking library)
    * efficient
    * asynchronous
+ flexible
+ some similarities with **[Django](https://www.djangoproject.com/)** framework
#### **+ Cons**
+ steeper learning curve
+ windows installation can be a bit of a hassle

**[Twisted](https://twistedmatrix.com/trac/)** is an open source event-driven networking engine written in Python.


**[Scrapy](https://scrapy.org/)** is an asynchronous framework which makes it very efficient for web scraping.
The framework is built on top of the Twisted library, which is an asynchronous networking library.

Support:
- [X] Python 2
- [X] Python 3

### Urllib2 - HTTP module (reading/opening web pages)

+ included in standard Python library
- used to be more popular, 'Requests' became the more popular tool

Support:
- [X] Python 2
- [X] Python 3

### Requests - HTTP module

+ a very popular python library
+ well documented
- does not come preinstalled with python

Support:
- [X] Python 2
- [X] Python 3

### BeautifulSoup

Extract the data points from a loaded page.
The name derives from invalid markup which is also referred to as 'soup'.

+ well documented
+ good examples available

Support:
- [X] Python 2
- [X] Python 3

### lxml

Similar to BeautifulSoup

+ feature rich
+ fast
+ memory efficient
- examples in documentation are not the best

### selenium - automated web application testing

Tool for writing automated tests for web applications.
 
+ beginner friendly
+ handles javascript-heavy websites very well
+ well documented

Support:
- [X] Python 2
- [X] Python 3

# Practical aproach

## Scrapy Installation

### Linux

Install dependencies from terminal

```
sudo apt-get install python-dev python-pip libxml2-dev libxslt1-dev zlib1g-dev libffi-dev libssl-
```

Install Scrapy from terminal w/ pip

```
sudo pip install scrapy
```

### Mac

Install Scrapy from terminal w/ pip

```
sudo pip install scrapy
```

### Windows

1. first we need to install **[Anaconda](https://www.anaconda.com/)**
    - Go to https://www.anaconda.com/distribution/
    - Make sure you select the corresponding installer

2. use the following command to install **[Scrapy](https://scrapy.org/)**
    ```
    pip install scrapy
    ```

3. (optional) if the above did not work try the following command
    ```
    conda install -c conda-forge scrapy
    ```

## Scrapy basics

### CLI (command line interface)

To check which version of Scrapy you have installed or if you have installed Scrapy run ```~$ scrapy version```
All examples were made using Scrapy 1.6.0 so to prevent any unforseen errors I suggest you install the same version.

To check all the available commands use the ```~$ scrapy``` command.
I highly recommend going through these commands to get a quick overview of the scrapy CLI.
If you would like to learn more about the Scrapy CLI go and see the **[Scrapy docs](https://docs.scrapy.org/en/latest/topics/commands.html)**

Output:
```
Scrapy 1.6.0 - no active project

Usage:
  scrapy <command> [options] [args]

Available commands:
  bench         Run quick benchmark test
  fetch         Fetch a URL using the Scrapy downloader
  genspider     Generate new spider using pre-defined templates
  runspider     Run a self-contained spider (without creating a project)
  settings      Get settings values
  shell         Interactive scraping console
  startproject  Create new project
  version       Print Scrapy version
  view          Open URL in browser, as seen by Scrapy

  [ more ]      More commands available when run from project directory

Use "scrapy <command> -h" to see more info about a command
```

### Creating a Scrapy project

1. Create and navigate to the directory where you would like to init a new Scrapy project.e.g. 

    ```
    $ mkdir scrapy-projects
    $ cd scrapy-projects/
    ```  

2. start a new Scrapy project named 'first-project'   
        
    ```
    /scrapy-projects$ scrapy startproject first-project
    ```

3. Navigate to the directory that was created by Scrapy 

    ```
    /scrapy-projects$ cd first-project
    ```  

4. Check the directory to make sure if Scrapy created a new project. You should also see the current project on top when running
    
    ```
    $ scrapy
    ```
5. Generate a new spider, this command takes a name for the spider and the domain of the page you want to scrape 

    ```
    ~/scrapy-projects/first-project$ scrapy genspider first-spider example.com
    ``` 

6. Check the spiders for the current project 

    ```
    $ scrapy list
    ```

After creating the project, the directory should look something like this:
```
├───scrapy.cfg
└───first-project/
    ├───__init__.py
    ├───items.py
    ├───middlewares.py
    ├───pipelines.py
    ├───settings.py
    └───spiders/
        ├───__init__.py
        └───first-spider.py
        ...
```

The scrapy.cfg file in the root directory contains the scrapy settings for this project.
___

<a href="https://www.buymeacoffee.com/TZnRwH0" target="_blank"><img src="https://bmc-cdn.nyc3.digitaloceanspaces.com/BMC-button-images/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a>
