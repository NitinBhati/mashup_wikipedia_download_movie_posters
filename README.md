# Mashup_wikipedia_download_movie_posters
Using Mashup: APIs, Downloading Files Programmatically from Wikipedia website of list of movies

Aim: download posters of the movies from the wikipedia website. Then sort them in rank and create a data frame. 

Steps:
1. Wikipedia Page Titles:
To access Wikipedia page data via the MediaWiki API with wptools, we need each movie's Wikipedia page title, i.e., what comes after the last slash in en.wikipedia.org/wiki/ in the URL.

2. Downloading Image Files
Downloading images may seem tricky from a reading and writing perspective, in comparison to text files which we can read line by line, for example. But in reality, image files aren't special—they're just binary files. To interact with them, we don't need special software (like Photoshop or something) that "understands" images. We can use regular file opening, reading, and writing techniques, like this:

import requests
r = requests.get(url)
with open(folder_name + '/' + filename, 'wb') as f:
        f.write(r.content)
		
3. I am going to use the PIL library (short for Pillow) and BytesIO from the io library for non-text requests, like images.

Summary:
We're going to query the MediaWiki API using wptools to get a movie poster URL via each page object's image attribute.
Using that URL, we'll programmatically download that image into a folder called bestofrt_posters.
