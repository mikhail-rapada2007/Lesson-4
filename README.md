# Lesson-4

1. python manage.py startapp nameOfApp

makes a tweets app that only focuses on tweets no authentication, sign in or anythiong just focused on tweets

2. ensure that you add 'tweets', in settings.py of the project

3. class
   class works like this. it works like a table. the objects inside the classs act as a column.
  class Furniture
    material
    no_of_feet
    hardness
    color

null                       blank
null doesnt exist          existing attribute

4. "class Tweet(models.Model):" in the models.py


5. Relational and Non-relational database
SQLite3 is relational database and what we use
parvase(without sql) is a non-relational database

6. python manage.py makemigrations
   python manage.py migrate
   do this to make tables


7. to make admin acc
   python manage.py createsuperuser
   give name and password
   now you can access admin.py

8. Function and Method
   Class can have functions and methods. Functions can have methods. Methods are baseline.

9. CRUD
a webapplication has create, read, update, delete.
We start with read to analyze data first since you cannot create, update, delete something you cant read.

10. Include another url configuration. django makes it easy. urls.py in the main proj can just include() the urls in tweets

11. how to connect url patterns in different folders?
   11.1 yo what is query set

12. Context Dictionary
13. keyvaluepair
14. template_tags; we need to convert python to html using this; {{}} -> python objects ;  {% %}-> python functions

new code in views.py of tweets
from django.shortcuts import render
from .models import *

# Create your views here.
def list_view(request):
    my_tweets = Tweet.objects.all()
    print(my_tweets)
    context = {
        'qs': my_tweets,
    }
    
    return render(request, 'tweets/list.html', context)
