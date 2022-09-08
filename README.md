# Simple Web Scraping Python in Google Colab

Simple web scrapping to test Google Colab and Python from https://nathanaelvictorious.medium.com/simple-web-scraping-using-beautifulsoup-and-python-in-google-colab-4084be701851

## Importing necessary library

The first thing we need to do is obviously to import the library needed, such as BeautifulSoup, requests, pandas, matplotlib, and numpy.

Each library served its function, BeautifulSoup for web scraping a website, requests for getting the URL, pandas for its powerful yet flexible data structure DataFrame, matplotlib for visualizing the data, and numpy for list computing & analytics.

## Get the website & extracting the data

The snippet above lets us save the URL into a requests.models.Response variable called “webpage” using the requests library, and then we use the BeautifulSoup to get the content of the website using html.parser into a variable called “soup”. By the way, I use the Codecademy website as the source, it’s a simple website about Cocoa Ratings in the world. You can check the website here.

## Understanding the structure of the website
Cocoa Rating website from Codecademy used for Web Scraping in Data Science and Data Analytics

Before you jump into the extraction, you must first understand the structure of the website you want to scrap by inspecting the page. You can see the HTML by right-clicking and choosing to inspect (or press CTRL + Shift + I) on the website page, then we will see the image below on our screen.

In the image above you can see that every table data (<td>) in table row (<tr>) have its classes, such as “Company”, “Origin”, “ReviewDate”, etc. From here I assume you already got the gist of the website component we are going to extract all the table data on <tr> and <td> element tags. See the code below for extracting data from the website

Here we use the .find_all function on the soup variable that we declared before, this soup variable has the content of the website so we need to find what we need. In the code, you can change the "class" to any HTML tags like "id" and "class-name" to any specific class/id name that you want to find.

## Analyzing the data
Now we arrive at the last part, first we need to see what the data is telling us. We have 9 columns, Company, Specific Bean Origin or Bar Name, REF, Review Date, Cocoa Percent, Company Location, Rating, Bean Type, and Broad Bean Origin.

Next, we need to decide the question we want to ask, this time I want to find the correlation between Cocoa Percentage and Rating, after that, I can predict how much Cocoa Percentage affects the Rating.

First, we need to make the DataFrame using pandas to make things easier

## Plot the result using matplotlib
Linear Regression Plot using Matplotlib on Python, Data Science
We can see based on the plot above that the higher the cocoa percentage the ratings tend to be lower.
