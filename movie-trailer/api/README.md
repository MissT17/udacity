# Movie Trailer Project Description

This program allows to dynamically create/generate a webpage with the list of user's favourite movies. The list of movies is created directly on the fly from the user inputs (titles of the movies). The links to the movie trailers, the short description of the films as well as the poster images are imported from [Youtube](https://www.youtube.com/) and from a movie database, [OMDB](http://www.omdbapi.com/). By hovering the movie images the user can read the description of each movie and watch the video trailers by clicking on corresponding film poster images. 

# Directory Structure

In the GitHub *udacity/movie-trailer/api* repository you will find the following files:
  1. `media.py` - the file contains all the information related to the `class Movie()`   
  2. `youtube_video_api.py` - contains the function that allows to execute the search of the corresponding video trailers on Youtube via the API.
  3. `test_api.py` - the core file of the API integration, it allows to dynamically construct the queries that are used to retrieve the data  from Youtube and OMDB (titles of the films, short descriptions, poster images and Youtube video trailers).
  4. `fresh_tomatoes.py` - contains all the HTML, CSS, JS, PYTHON code that allows to design, generate and create the .html file in the `/templates` folder
  5. `server.py` - contains the methods related to *flask*. *Flask* is used to create a server environment allowing to receive the user request in terms of the films that he/she would like to display on the page, run this information through the program and return the html page to the browser.
  6. `/templates` folder contains the `user_input.html` file that displays the form that the users fill in with the titles of their favourite movies.
  7. `README.md` - contains a short "How To" which I hope you are enjoying right now.

# Requirements

1. Please make sure that a 2.7 version of Python is installed on your machine (as the code is adapted to this version of Python). In order to check if you have the necessary Python version installed:
   1. Open the terminal on your computer (if you use Mac: go to Applications > Utilities > Terminal, on Windows machines it corresponds to Start >         Program Files > Accessories > Command Prompt)  
   2. Type `python` or `python -v` in the command line, which should return to you something similar to: 
      ```
      Python 2.7.5 (default, Jun 17 2014, 18:11:42)
      [GCC 4.8.2 20140120 (Red Hat 4.8.2-16)] on linux2
      Type “help”, “copyright”, “credits” or “license” for more information.
      ```
      If there is no Python installed, please install it on your machine. You can find the necessary links for download here: [Python](https://wiki.python.org/moin/BeginnersGuide/Download)
  
2. Please check if you also have Flask installed on the machine.
   1. Type `python` in the terminal
   2. Type `from flask import Flask` after `>>>` in the terminal. 
   If you get an error, it is most likely that *Flask* is not installed. To install, follow the [guidelines](https://pypi.python.org/pypi/Flask/0.12). 
3. You will also need to open a developer Youtube API account. Please follow a quick guide here: [https://youtu.be/Im69kzhpR3I](https://youtu.be/Im69kzhpR3I) 

# Installation

1. Download the files from the GitHub repository. It's important that *all* the files are saved within the same folder on your computer.
2. In your text editor create a new file called hidden.py. Insert the following piece of code into it:
   ```
   import os


   def passkey():
       os.environ['API_KEY'] = 'INSERT YOUR YOUTUBE API KEY'
       os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "/google_application_credentials.json"  # NOQA
       my_key = os.environ['API_KEY']
       my_cred = os.environ['GOOGLE_APPLICATION_CREDENTIALS']
       return my_key
       
   passkey()
   ```
   Insert your Youtube API Key into the corresponding field `os.environ['API_KEY'] = 'YOUR KEY GOES HERE'` and save the file in the            folder with the rest of the files. (Please read the [Requirements](https://github.com/MissT17/udacity/blob/master/movie-trailer/api/README.md#requirements) section to find out how to get your Youtube API Key.)  
3. Open the terminal on your machine (if you use Mac: go to Applications > Utilities > Terminal, on Windows machines it corresponds to Start > Program Files > Accessories > Command Prompt).
4. In the terminal navigate to the folder that contains the downloaded documents and start the local server by running the following code in it: `python server.py`
   The terminal will provide you with the address(URL) that you need to insert into the browser to start the program.
   ```
   * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
   * Restarting with stat
   * Debugger is active!
   * Debugger PIN: 129-045-349
   ```
   At this point you should see a form in the browser.
   
# Expected Outcome

Once the form appears in the browser, fill in the corresponding fields with the titles of your favourite movies. (Please make sure the spelling is correct and the titles are exact, if the titles are not accurate and the films have multiple versions, the latest Youtube trailer will be used as reference), then click **__Submit__**. On click a new page will open up with your favourite movies displayed. By clicking on a poster image, you will activate the video trailer which will be displayed in the center of the page. The video will start automatically once you click on the poster and the player window opens. The video will stop automatically and the player will be closed, if you click outside the video window or close the player. On hovering the images, a short movie description will be displayed over the poster. 

# License

The `fresh_tomatoes.py` code was provided by Udacity in its course, the code related to the Youtube API implementation was done according to the Youtube guidelines and influenced by its sample code, the rest of the files were created by the owner of this repository on the basis of the introductory course to Python class given by Udacity. All poster images and descriptions are provided by OMDB and the trailers are taken from Youtube.
