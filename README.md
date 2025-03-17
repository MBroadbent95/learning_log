# Learning Log

Project Title – Learning_Log
Description –
This was my final project following the Python Crash Course 3rd edition by Eric Matthes.
This project involved the development of an app, using Python and Django, to be accessable by the internet.
At it's core, the project is an online diary.

![Screenshot of home page](.//images/ll_homepage.jpg)

Installation – Steps to install and set up the project.
This project will require you to use Python & Django.
Bootstrap will also be used to give the project a bit of styling.
You will need to install these programs using pip before starting.

Here is the deployed requirements.txt
beautifulsoup4==4.13.3
Django==5.1.1
django-bootstrap4==25.1
soupsieve==2.6
sqlparse==0.5.1
typing_extensions==4.12.2
tzdata==2024.2

Features –
A user can sign in or register if not already, create a topic, and then contribute entries to that topic much like a diary.
As a user, you are free to view and edit your topics/ and entries exclusively.
You cannot see other peoples topics and should you attempt to be cheeky and bypass this by adjusting the url, it will deny your access.
A user can currently create an unlimited number of topics and entries.

![Screenshot of Topics page](.//images/ll_topicpage.jpg)

Configuration –
This project does require virtual environments to be running from 2 terminals. I used Git Bash for my local server, and then the terminal inside of my vscode. You will need to activate both environments to begin development and see the project in action.
The command I used was as follows, keep in mind I that use Windows, when you are in the project directory- source ll_env/Scripts/Activate. And then on one of your terminals, python manage.py runserver - this should start a development server on yoir local port, usually 8000, on your preferred browser, type in http://localhost:8000/ - if the server is up and running ccorrectly, this should show you teh landing page.

Technologies Used –
This project utilised the following technologies:

- Python
- Django
- Bootstrap4

Known Issues / Bugs –
The main error was in the views.py file, the way that the program checked the user needed adjustment. The previous code resulted in an int being passed when an object was expected. Here is the previous code, and here is the newly corrected code:
Screenshot of bad code
![Screenshot of Failing code](.//images/intcorrection.jpg)

![Screenshot of correct code](.//images/intcorrection2Edit.jpg)

Roadmap – Planned future improvements.
Possible improvements could be:

- The ability to delete your entry/ topic. Currently there is no way to delete an entry even if you might want to.
- After logging in, it takes you back to the homepage and prompts you to register, perhaps an alternative home page or just take you directly to the topics.
- Limit number of topics and entries, currently there is no limit.

Authors & Acknowledgments – Credits to contributors or inspirations.
Credit for this project goes to Eric Matthes, the author of the Python Crash Course.
