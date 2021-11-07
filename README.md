# gd_setlists
Project to retrieve Grateful Dead concert setlists using BeautifulSoup and then export as a csv

The source site structure is:
    - A list of html pages for each year from 1972 to 1995 
    - That in turn has links to each concert in that year
    - And each link leads to a txt file with the setlist for each concert.

The notebook ending in 'test' was my development file to make sure all data was being retrieved the way I intended. The actual loop is in the 'loop' notebook.

I used BeautifulSoup (SoupStrainer) to grab all the links (a href) and then filtered out the external links, leaving just the txt file paths. I then utilized a loop to access each txt file, scrape/parse the data, and put each concert setlist into a dictionary with the concert details, setlist, and year. These dictionaries were stored in a list that was converted to a pandas DataFrame for further cleaning/processing.

Because of the dictionary structure I used JSON.Normalize to unpack the setlist out to rows in the DataFrame. My first time using this function and I'm glad to know it for future applications.

Source Data: https://www.cs.cmu.edu/~mleone/gdead/setlists.html
