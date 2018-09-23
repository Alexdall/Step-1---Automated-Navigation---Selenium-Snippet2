# Step 1 - Automated Navigation - Selenium Snippet
#Hi everybody , this little snippet will show you how to use a selenium lib in order to make an automated web scraping you can use to #analyse data, find patterns,etc.

#This snippet is the first of many other, each one will show you the next step, this one shows the automated connection in a web page, #in this case, the facebook, the next will show you how to scraping a web page using beautiful soap, after we'll to download the data #and keep it in a database and so on.

#According with the documentation, the selenium package is used to automate web browser interaction from Python and used to make #automated tests.

#You can find more information in https://pypi.org/project/selenium/

#Several browsers/drivers are supported (Firefox, Chrome, Internet Explorer), as well as the Remote protocol.

#Supporte Python versions: Python 2.7, 3.4+

#For the installation you can use on of this 3 options:

#using pip:

#pip install -U selenium

#You can download the source distribution from PyPI (e.g. selenium-3.14.0.tar.gz), unarchive it, and run:

#python setup.py install

#Finally if you're using Anaconda:

#conda install -c conda-forge selenium

#The first thing we need to do is to import the libraries we'll use in this snippet.

#In this case, for this first step, the most important one is the selenium where we'll make the automated connection.


from urllib.request import urlopen as uReq
from bs4 import BeautifulSoup as soup
from datetime import datetime, timedelta
from selenium import webdriver
import time

#After importing the libs, in order to run the code, we need to choose the correct driver to use in.

#Selenium requires a driver to interface with the chosen browser.

#Here, we'll use the Chromium, but many other can be used.

#you can find the driver here:

#https://sites.google.com/a/chromium.org/chromedriver/downloads

#you can find more information in the Selenium project's page.

#With Chrome driver installed, we need to set some option in order to run it.


options = webdriver.ChromeOptions()
options.add_argument('--ignore-certificate-errors')
options.add_argument("--test-type")
options.binary_location = "D:\MachineLearning\chromedriver.exe"
driver = webdriver.Chrome("D:\MachineLearning\chromedriver.exe")

--------------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------------------------------
​
#Next step is to set the url we'll use and get it with the driver.
​
--------------------------------------------------------------------------------------------------------------------------------

my_url = 'https://www.facebook.com/'

driver.get(my_url)

#In our case we have a form to fill in order to access the web page, so we need to get the html ids from the respective fields. It's #easy to find them using the driver methods like find-element_by_id or find_elements_by_xpath.


driver.find_element_by_id
login = driver.find_element_by_id('email');      
senha = driver.find_element_by_id('pass');

login.send_keys('your user')
senha.send_keys('your password')

submit_button = driver.find_elements_by_xpath('//*[@id="loginbutton"]')[0]; 

#Now is just submit the information using the click method and <i>voilà</i>, we're in.
#Now is just submit the information using the click method and <i>voilà</i>, we're in.

submit_button.click()
submit_button.click()

#In the next topics we'll learn how to get the data using beautiful soap, store it in a database and analyse it using some tools like #pandas, matplotlib, sklearn, etc.

#Enjoy the code, improve it if you want!

#See you!!!!

​
