# Data Mining Project - Booking.com webscraper
A booking.com webscraper project 
## General Information
- In this project we scrape the website Booking.com using Selenium.
- The user inputs a desired country, check-in and check-out dates
- based on that input, specific data is collected from all page results and stored in a local SQL Database

## Installation
After downloading the Data_mininig_project_2021 directory to your computer (or clone the repository from the github) you will need to creat an empty virtual environment.  
Create & activate virtual environment on bare Python installation: \
Create: (inside main project folder):
```bash
python -m venv venv
```
Activate: \
Linux: 
```bash
source venv/bin/activate
```
Windows: 
```bash
venv\Scripts\activate.bat
```
Use the package manager [pip](https://pip.pypa.io/en/stable/) to install the requirements.txt file. 
```bash
pip install -r requirements.txt
```
Other alternative is to install: \
beautifulsoup4==4.9.3 \
certifi==2021.5.30 \
charset-normalizer==2.0.3 \
idna==3.2 \
requests==2.26.0 \
selenium==3.141.0 \
soupsieve==2.2.1 \
urllib3==1.26.6 

We use Python 3.7.7 

For this project you will need a WebDriver and adding executables to your PATH \
For more information you can check the link below: \
[driver_requirements](https://www.selenium.dev/documentation/en/webdriver/driver_requirements/)
## Usage

For running the program one need to find the main.py file under the sources directory.
runing the main.py file with no input will generate the usage message below:

```bash
usage: main.py [-h] -d DESTINATION -s START_DATE -e END_DATE
main.py: error: the following arguments are required: -d/--destination, -s/--start_date, -e/--end_date
```
Use the command-line interfaces to enter your input, for example:

```bash
main.py -d germany -s 2021-08-15 -e 2021-08-21
```
All you need to do now is wait... \
For this input it might take about 10 minutes so go make yourself a cup of coffee.

## Output
The output is a list of dictionaries, one dictionary for example: \
{'name': 'Wyndham Stuttgart Airport Messe', 'location': 'Stuttgart', 'rating': '8', 'reviewers_amount': '3', 'price': 1616, 'max people': '2'} \
Each dictionary contain the data about one stay that match the location and available be the dates the user specified.

## Implementation
We use the beautifulsoup4 and selenium libarary to scrap information from the Booking website.
We use the argparse module to make a user-friendly command-line interfaces.
Our project is implemente by hierarchy of two classes:
1. The class Website that recieve the url of the Booking website: "https://www.booking.com" and return a list of the urls of all the different pages that match the user search.
2. The class Page that will be called for each url from the list mention above and will retrieve the data about each stay that appear in that page. 

For each stay we create a dictionary with the information about the stay (name, location, rating, number of reviews, price and the maximum number of people).
Then we create a list of all the dictionaries and print it.

## The goal
Creating a big database with all the data that being extrarct from Booking website. 

## The motivation
This project is for learning purposes. We will practice with writing a complex code with Python, using Git to collaborate and in the future, creating a big database by working with SQL.
