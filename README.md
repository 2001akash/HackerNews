# CopyCat - A Personalized News Interface/Clone

A Clone of the HackerNews website which keeps tab of all the latest news coming in along with a personalized experience.


### Problem Statement 
[HackerNews](https://news.ycombinator.com/) is very popular website among developers for latest news and projects. However sorting of the items is done via their own algorithms and we want to build a clone which keeps getting the top 90 articles and shows them in reverse chronological order. 

#### Requirements
Each news item will have the following fields: 
- Url
- Hacker news url
- Posted on
- Upvotes
- Comments
      
1. A script which crawls the first three pages, extracts the news items and adds in the database. If the news item already exists, it updates the upvote and comment counts.
2. A user can signup or login to the dashboard.
3. A dashboard where all news items are listed in reverse chronological order.
4. A user can bookmark an item in the list.
5. A user can mark a news item as read or delete it. Deleted items are not shown in his/her panel but are not deleted from the database.


___

## Solution 

**Tech Stack**: Python3 + Django3 + MySQL

The Django application is a clone of the Hackerrank Website with additional personalized features & a dashboard. 

As per the requirement, 

1. Each news item has the following field 
    - Url 
    - Hacker News ID/Url  
    - Posted On
    - Upvotes 
    - Comments

2. The application also enable a script in the background which extracts the news items and adds them in the database. It updates upvote & comment count if the news item exits. 
3. The application provides a SignUp and a Login Dashboard
4. The dashboard Index lists all the news items in reverse chronological order. 
5. A User is provided with the personalized feature to bookmark news items. 
6. A user also has the ability to read or delete a news item from this dashboard. 

___

 
### Details On the Application 

The Django application can be classified as follows 
    1. Urls/Paths 
    2. Views 
    3. Models 
    4. Templates
    5. External Logic
 
 Any other if exists
 
#### Urls 
 The application provides paths for view functions
 On the Project Urls, the application is routed to the following: 
1. `admin`          For Super User/Administrator 

2. `accounts`       For Login Related
 
3. ``               For Everything starting with None,
        
        
 On the app urls, the applications is meant to route as follows:
  
1. Creating Users/Sign Up           `accounts/signup`
2. Login View                       `accounts/login`
3. Logout View                      `accounts/logout`
4. Password Change View             `accounts/password-change`
5. Fill User Details View           `filldetails/`
6. Index View With News View        `index/`
7. User's Profile View              `profile/<user>` where <user> is specific to the registered user.
8. Marked As Read/Read History      `marked-read/`
9. All Bookmarks View               `bookmarks/`
    
From the above url routes, more logical views are written for 
    - Adding Bookmarks
    - Removing Bookmarks
    - Marking a news item as read,
    - Deleting a news item from a user's profile. 
    
    
#### Models 
The following models are the relationship with database. The database used for the application is `MySQL`.

1. `NewsFeed` (News Feed Details)
2. `Profile` (User's Personal Details)
3. `Bookmarks` (To hold the user specific Bookmark)
4. `UserRead` (Model to mark user's Read History)
5. `UserDelete` (Removed Items for a user)


For authentication, default `User` model from the module `django.contrib.auth.models` is utilized. 


#### Forms 

Following are the forms made use of in the application: 

1. `LoginForm`   # Form intended to login 
2. `FillUpForm` # Form intended to Fill in User's personal details like Name, DOB, email


The django forms that are imported are the following: 

1. `PasswordChangeForm` 
2. `UserCreationForm`


#### Templates 

There are primarily two sets of templates designed to uplift the look and feel of the website. 
What remains common is the usage of `static` files loaded into base templates in the form of `background.png` and `favicon.png`.

From the following two template sets `mainapp`(name of the app) and `registration`. 
The former's templates have been designed to meet the UI effects after login, and later's before login. 

Both sets have a common base template `base.html` but are segregated in the respective folders. 


#### External Logic 

Under the app `mainapp`, a certain file by the name `parser.py` is made use of by the `index` view of our application. 

This `parser.py` is a beautifulsoup `bs4` based module to act as the parsing engine for the [HackerNews](https://news.ycombinator.com) website. 
This  module can be used/reused or extended across various examples. 



    

 

 
