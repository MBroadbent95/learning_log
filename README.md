# Learning Log
A full-stack web application built with Python and Django, 
allowing users to create accounts, log topics, and maintain 
private diary-style entries. Deployed to the live web.

🔗 [Live App](https://mbroadbent.pythonanywhere.com/)

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Django](https://img.shields.io/badge/Django-5.1-green)
![PostgreSQL](https://img.shields.io/badge/Database-SQLite%2FPostgreSQL-lightgrey)
![Bootstrap](https://img.shields.io/badge/UI-Bootstrap4-purple)

![Screenshot of home page](.//images/ll_homepage.jpg)

## Installation

1. Clone the repo: `git clone https://github.com/MBroadbent95/learning_log.git`
2. Create and activate a virtual environment:  
   `source ll_env/Scripts/activate` (Windows/Git Bash)
3. Install dependencies: `pip install -r requirements.txt`
4. Run migrations: `python manage.py migrate`
5. Start the dev server: `python manage.py runserver`
6. Visit `http://localhost:8000` in your browser

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

## Technical Decisions

- **Django ORM over raw SQL** — used Django's ORM for 
  query abstraction and security, with user-scoped 
  querysets to enforce data isolation per account.
- **User authorisation at the view level** — access 
  control is enforced in `views.py` by comparing 
  `request.user` against the topic owner, preventing 
  URL-manipulation exploits.
- **Virtual environment isolation** — dependencies 
  managed via `requirements.txt` and `ll_env` to 
  ensure consistent installs across environments.

Configuration –
This project does require virtual environments to be running from 2 terminals. I used Git Bash for my local server, and then the terminal inside of my vscode. You will need to activate both environments to begin development and see the project in action.
The command I used was as follows, keep in mind I that use Windows, when you are in the project directory- source ll_env/Scripts/Activate. And then on one of your terminals, python manage.py runserver - this should start a development server on yoir local port, usually 8000, on your preferred browser, type in http://localhost:8000/ - if the server is up and running ccorrectly, this should show you teh landing page.

Technologies Used –
This project utilised the following technologies:

- Python
- Django
- Bootstrap4

## Lessons Learned

Encountered a bug in `views.py` where an integer was 
passed where a user object was expected during 
authorisation checks. Diagnosed by reading Django's 
error trace and corrected by adjusting the queryset 
lookup. This reinforced the importance of consistent 
object typing when working with Django's ORM.

![Screenshot of Failing code](.//images/intcorrection.jpg)

![Screenshot of correct code](.//images/intcorrection2Edit.jpg)

## Roadmap
- [ ] Add DELETE functionality for topics and entries (currently read/create/edit only)
- [ ] Redirect to `/topics` on successful login rather than homepage
- [ ] Implement per-user entry limits with a configurable threshold
- [ ] Migrate from SQLite to PostgreSQL for production parity
- [ ] Add basic test coverage with Django's TestCase

Authors & Acknowledgments – Credits to contributors or inspirations.
Credit for this project goes to Eric Matthes, the author of the Python Crash Course.
