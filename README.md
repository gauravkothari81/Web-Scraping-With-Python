# Web-Scraping-using-python

This project explains how to scrape website data with Python using Jupiter Notebook.

I have divided code into mainly 7 parts.

1) Importing libraries

There are mainly 4 libraries used for this project. pandas, numpy, urllib and BeautifulSoup.

2) Creating a function to get data in HTML format from the website.

Here, we are creating a function to read the URL and then extracting the HTML from the same. 'html.parser' is used to extract the HTML data from the website. The function returns the output which we can then use to extract our actual data.

3) Using a function 'getHTML' to get data from Wikipedia.

We are simply using a function 'getHTML' which was defined in the previous and passing the URL for the desired webpage.

4) Get the whole table as well as links for each city page.

Now, as we already have the HTML information for the full webpage, we can not use it as a whole. We need to find the specific information which we need. In this case, we need the only table containing information about US cities. By visiting the webpage and after careful inspection, we can see that the table information is under tags (<table></table>). A table in HTML is comprised of rows denoted by the tags <tr></tr>. Each row has cells which can either be 'headings' defined using (<th></th>) or 'data' defined using (<td></td>). 

In our case, the class of our table is 'wikitable sortable'. First, we store that information in a particular variable and then we find all the rows for that table. We are creating a for loop to find mainly two things. First to take a look at all the links for the individual city pages and to take a look at how the data in whole looks.

5) Defining a function to get data from individual city pages. Here we are extracting the only name of 'Mayor' for each city.

The links do not include the base address, so whenever we access any of these links, we’ll append https://en.wikipedia.org as the prefix. Now, in this step, with the help of 'for' loop and 'if' statements, we extract the names of 'Mayor' which can be found in the individual city pages.

6) Combining all the collected data and defining a data frame.

After we get all the desired information (table as a whole + information from individual pages) we combine these data into a single array and create a final DataFrame.

7) Define column headings

After creating a DataFrame, we extract headings of all the columns as well as renaming the headings where required.

8) Data Cleaning

This is our last and final step where we remove all the unnecessary information from our DataFreame like brackets, signs, etc. and export the DataFrame to csv which is ready to be uploaded to a BigQuery table.
