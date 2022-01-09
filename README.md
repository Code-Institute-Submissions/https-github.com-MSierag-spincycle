<h1 align="center">Spincycle Records</h1>

[View the live project here.](https://github.com/MSierag/SiteStorage)
[or view it here](https://spincycle-records.herokuapp.com/)

## Purpose of the website

This is a simple app for inventory management on a construction site. In my previous career I was fortunate enough to work on a few construction sites for a German mulitinational, where I was responsible for site logistics. This company had an integrated system for delivery tracking, but this was only available for the large items sent to site by the logistics department. However, the construction team received daily deliveries of small items which sometimes went missing as they were untracked or the information wasn't shared.  

The purpose of this app is to provide an easy to use platform for a construction team to track any and all small deliveries. It is intented to be made available only to the construction team to facilitate the communication between them. It's intentionally devoid of images and frills to facilitate readability in a construction environment. The website is designed to be responsive and accessible on a range of devices, making it easy to navigate for potential users.

## User Experience (UX)

-   ### User stories

    -   #### Owner Goals

        1. As an owner, I want to allow unregistered visitors to shop
        2. As an owner, I want to encourage unregistered visitors to register
        3. As an owner, I want to restrict CRUD functionality on the site
            
    -   #### Visiting User Goals

        4. As a visiting user, I want to be able to auickly understand the purpose of the site
        5. As a visiting user, I want to be able to easily navigate throughout the site
        6. As a visiting user, I want to be able to search for specific items
        7. As a visiting user, I want to be able to make a purchase
        8. As a visiting user, I want to be able to distinguish between categories        
        9. As a visiting user, I want to be able to register/create a profile 
    
    -   #### Registered User Goals

        10. As a registered user, I want to be able to login/log out
        11. As a registered user, I want to be able to check my profile data
        12. As a registered user, I want to be able to edit my profile data
        13. As a registered user, I want to be able to view my purchase history

    -   #### Customer (both visiting and registered users) Goals

        14. As a customer, I want to be able to view details of the items
        15. As a customer, I want to be able to adjust the number of items to purchase
        16. As a customer, I want to be able to easily identify items on special offer
        17. As a customer, I want to be able to view my shopping basket
        18. As a customer, I want to be able to know the exact cost

        
-   ### Design
    -   #### Colour Scheme
        -   There are six colours used throughout the site, the first three are the main colours and the remaining three are used for accents.
        ##### Main colours
           ![MaterializeCSS rendering of main colour scheme](https://github.com/MSierag/SiteStorage/blob/main/static/images/main-colours.jpg?raw=true)
            
            The colour #009688 was chosen from the MaterializeCSS colour options as it approaches the colour used by the German multinational, this is the main colour throughout the site. The colours #26a69a and #4db6ac are variations on this colour used where some additional contrast with the background was needed.
        ##### Accent colours
           ![Coolors rendering of effect colourscheme](https://github.com/MSierag/SiteStorage/blob/main/static/images/accent-colours.png?raw=true)
            
            The colours #4caf50, #f4436, and #03a9f4 are accent colours. They are used on buttons throughout the site. 
    -   #### Typography
        -   The font used throughout the site are the standard fonts defined by MaterializeCSS.

*   ### Wireframes
Due to the high number of pages and limited content on them I decided against creating wireframes in various formats as there would be very little difference between them.
The wireframes I did make can be viewed here [View](https://github.com/MSierag/SiteStorage/tree/main/static/images/wireframes)

## Database schema
The database for this website is run through MongeDB, the schema can be found below.

![Dbdiagram.io rendering of the database schema](https://github.com/MSierag/SiteStorage/blob/main/static/images/dbschema.png?raw=true)


## Features
-   Navbar at the top of the page is not visible on the Welcome page, but on all subsequent pages. The Register and Login pages 
    show no buttons on the navbar yet. Once the user is successfully logged in the navbar displays the buttons "Home", "New item", "Locations" and "Logout". The buttons have a hover effect.
-   Delete functions throughout the site are intentionally without defensive programming. 

### Existing features

#### Page specific features

##### Welcome page

-   Large title welcomes visitor to SiteStorage. 

-   A card the text Please register / login below is displayed underneath the title.

-   Call to action button labelled "Register" which when clicked opens the Register page.

-   Call to action button labelled "Login" which when clicked opens the Login page. 

-   The page is intentionally without a navbar, to ensure only registered users enter the site.  

##### Register page

-   Top of the screen shows the navbar which is empty apart from the logo, no further buttons visible to visitors.

-   Middle section holds a form with fields for Username and Password prefixed by an icon.

-   Below the fields is a call to action button labelled "Register" which when clicked has two options:
        -if the registration was successfull, the user is redirected to the Profile page with a flash message of "You are now registered"
        -if the registration was unsuccessfull, the user receives a flash message "Username already exists" and is redirected to the Registration page.

##### Login page

-   Top of the screen shows the navbar which is empty apart from the logo, no further buttons visible to visitors.

-   Middle section holds a form with fields for Username and Password prefixed by an icon.  

-   Below the fields is a call to action button labelled "Login" which when clicked has two options:
        -if the login was successfull, the user is redirected to the Home page with a flash message of "Welcome (username)" 
        -if the login was unsuccessfull, the user is redirected to the Login page with a flash message of "Username and / or password incorrect".

##### Profile page

-   Top of the screen shows the navbar which now show the buttons "Home", "New item", "Locations" and "Logout".

-   Middle section is formed by a card which displays the message "(username) logged in successfully".  

-   Below this section is a simple statement invites the user to select a task above. 

##### Home page

-   Top of the screen shows the navbar which now show the buttons "Home", "New item", "Locations" and "Logout".

-   Below the navbar the page title of All Items is displayed.

-   Below the title is a search field with two buttons to the right, Reset and Search. This allows the user to search the    items listed below.

-   Middle section holds a collapsible  which displays all items in the database. The collapsed items displays a down caret, two buttons Edit and Used, the item name and the date it was received. When the user selects the down caret, the unfolded item shows the storage location, the item description and who took receipt of it. 
    -   The Used button serves as the delete function. When pushed, the item is deleted from the database and the user receives a flash message of "Item deleted"
    -   The Edit button when pushed redirects the user to the Edit Item page

##### New Item page

-   Top of the screen shows the navbar which now show the buttons "Home", "New item", "Locations" and "Logout".

-   Below the navbar the page title of Add Item is displayed.

-   Middle section holds a form with fields to be completed by the user to add a new item to the database. The first field is a dropdown menu for the storage location, followed by Item Name, Item Description and Date received. The latter is a date picker. 

-   At the bottom of the form is a large button labelled Add item which when pushed has two possible outcomes:
    -if all fields were filled out correctly, the user is redirected to the Home page where the item has been added to the list and a flash message reads "Item added successfully"
    -if all fields were not filled out correctly, the user is alerted to the missing or incorrect information by the validation functionality.

##### Edit Item page

-   Top of the screen shows the navbar which now show the buttons "Home", "New item", "Locations" and "Logout".

-   Below the navbar the page title of Edit Item is displayed.

-   Middle section holds a form with prefilled fields to be edited by the user to edite the item in the database.

-   At the bottom of the form there are two large buttons labelled Cancel and Edit Item 
    -Cancel takes the user back to the Home page 
    -Edit Item will, if all fields were filled out correctly, redirect the user to Home page with a flash message of "Item updated successfully" 
    -Edit Item will, if all fields were not filled out correctly, alert the user to the missing or incorrect information by the validation functionality.

##### Locations page

-   Top of the screen shows the navbar which now show the buttons "Home", "New item", "Locations" and "Logout".

-   Below the navbar the page title of Manage Locations is displayed.

-   Below the title is a large button labelled Add Location which when pushed redirects the user to the Add Location page.

-   Middle section holds a collection of cards which display all locations currently in the database. The cards have two buttons Delete and Edit 
    -   The Delete button deletes the location from the database and the user receives a flash message of "Location deleted successfully"
    -   The Edit button when pushed redirects the user to the Edit Location page

##### Add location page

-   Top of the screen shows the navbar which now show the buttons "Home", "New item", "Locations" and "Logout".

-   Below the navbar the page title of Add Location is displayed.

-   Middle section holds a form with a single field to be completed by the user to add a new location to the database. 

-   At the bottom of the form is a large button labelled Add location which when pushed redirects the user to the Locations page where the new location has been added and a flash message of "New storage location added".

##### Edit location page

-   Top of the screen shows the navbar which now show the buttons "Home", "New item", "Locations" and "Logout".

-   Below the navbar the page title of Edit Location is displayed.

-   Middle section holds a form with a single prefilled field to be completed by the user to edit the current location in the database. 

-   At the bottom of the form there are two large buttons labelled Cancel and Edit Item 
    -Cancel takes the user back to the Locations page 
    -Edit Location will redirect the user to Locations page with a flash message of "Location updated successfully" 

### Future features

-   Currently no future features are envisioned.

## Technologies Used

### Languages Used

-   [HTML5](https://en.wikipedia.org/wiki/HTML5)
-   [CSS3](https://en.wikipedia.org/wiki/Cascading_Style_Sheets)
-   [JavaScript](https://en.wikipedia.org/wiki/JavaScript)
-   [Python](https://www.python.org/)


### Frameworks, Libraries & Programs Used

1. [MaterializeCSS:](https://materializecss.com/)
    - MaterializeCSS was used to assist with the responsiveness and styling of the website.
1. [jQuery:](https://jquery.com/)
    - jQuery was used for the functionality of the MaterializeCSS components.
1. [Git:](https://git-scm.com/)
    - Git was used for version control by utilizing the Gitpod terminal to commit to Git and Push to GitHub.
1. [GitHub:](https://github.com/)
    - GitHub is used to store the projects code after being pushed from Git.
1. [MongoDB:](https://www.mongodb.com/)
    - MongoDB is used for the database. 
1. [Heroku:](https://heroku.com/)
    - Herokuapp is the platform used to display the project after being pushed from Git.
1. [Balsamiq:](https://balsamiq.com/)
    - Balsamiq was used to create the wireframes during the design process.
1. [Coolors:](https://coolors.co/)
    - Coolors was used to generate the palette for accent colours used throughout the site.
1. [Dbdiagram:](https://dbdiagram.io/)
    - Dbdiagram was used to generate the rendering of the database schema.

## Testing

### Validation 

The W3C Markup Validator, W3C CSS Validator Services and JSHint were used to validate every page of the project to ensure there were no syntax errors in the project.

-   [W3C Markup Validator](https://jigsaw.w3.org/css-validator/#validate_by_input) 
-   [W3C CSS Validator](https://jigsaw.w3.org/css-validator/#validate_by_input)  
-   [JSHint](https://jshint.com/)   
    No errors or warnings were given for the respective codes.

### Google Lighthouse

I used Google Lighthouse to audit the site's performance, accessibility, use of best practices and search engine optimization.

Testing resulted in the following [score](https://github.com/MSierag/SiteStorage/blob/main/static/images/lighthouse.png?raw=true):
-   Performance: 99%
-   Accessibility: 92%
-   Best Practices: 87%
-   SEO: 91%

The 87% in Best Practices was due to the deployed Heroku site not being secured ( http:// instead of https:// ). This unfortunately is beyond my control and is therefore left as it is. 

### Responsiveness testing

To test the responsiveness of the site [Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools) and [Responsive Design Checker](https://responsivedesignchecker.com/) were used. 

#### Conclusions
Only on the smallest smartphone screen (320x480) did the background image interfere with the text on the buttons.  [Screensizemap](https://screensizemap.com/) was consulted to determine the popularity of this screen size.
The popularity listed for this type of screen hovers around 2% and seems to concern smartphones which can be considered at the end of their lifecycle. 
It is listed as a known issue.   

### Testing User Stories from User Experience (UX) Section

-   #### Owner Goals
    1. As an owner, I want to keep out unregistered visitors to the site.
        1. The Welcome page has only two buttons which allow a visitor to either register or login. There is no navigation bar to ensure there is no other way to enter the site than through these two buttons. 
       
-   #### Visiting User Goals

    2. As a visiting user, I want to be able to register/login to use the site.

        1. Upon reaching the Welcome page, users are automatically greeted with the clean and easily readable page which contains the title heading "Welcome to SiteStorage" and underneath that the subheading "Please register / login" with two buttons to go to the page of their choice. [View](https://github.com/MSierag/SiteStorage/blob/main/static/images/testing/welcome.png?raw=true)
        2. Pushing these buttons leads to the corresponding page where the user can still change their mind and be redirected to the other page. There is no button on either of those pages leading back to the Welcome page as casual visitors are not intended to even reach this app. 
        3. Text has intentionally been kept to an absolute minimum.

-   #### Registered User Goals

    3. As a registered user, I want to be able to easily navigate throughout the site.

        1. The buttons on the navbar provide the user with clearly marked links to the respective pages. These buttons are the same across all pages. [View](https://github.com/MSierag/SiteStorage/blob/main/static/images/testing/user-navbar.png?raw=true)
        2. The various buttons on the respective pages are clearly marked and provide the expected functionality. The functionality is confirmed by flash messages.
        
    4. As a registered user, I want to be able to perform full CRUD functionality.
        
        1. CRUD functionality is provided for items and locations. Once logged in the user has access to the buttons on the navbar which provide the desired functionality reinforced by flash messages. Numerous screenshots can be found 
        [here](https://github.com/MSierag/SiteStorage/tree/main/static/images/testing)
                      
    
### Known Issues

-   On mobile devices with a screen narrower than 360px the contents of the card section on index.html pushed out of alignment.
    -   Text and text on buttons disappears from view as a result.

### Bug fix

During testing it turned out if a user logged out, clicking on the logo would return them to the All Items page anyway. This was fixed by wrapping the link in a condition depending on the user having a valid session cookie.

```
{% if session.user %}
    <a href="{{ url_for('get_items') }}" class="brand-logo">Site storage</a>
{% else %}
    <a href="{{ url_for('welcome') }}" class="brand-logo">Site storage</a>
{% endif %}
```

## Deployment

### GitHub

The project is run on GitHub, but deployed to Heroku and uses MongeDB for the database:

#### Forking the GitHub Repository

By forking the GitHub Repository you make a copy of the original repository on your GitHub account to view and/or make changes without affecting the original repository by using the following steps:

1. Log in to GitHub and locate the [SiteStorage repository](https://github.com/)
2. At the top of the Repository (not top of page) just above the "Settings" Button on the menu, locate the "Fork" Button.
3. You should now have a copy of the original repository in your GitHub account.

#### Making a Local Clone

1. Log in to GitHub and locate the [SiteStorage repository](https://github.com/)
2. Under the repository name, click "Clone or download".
3. To clone the repository using HTTPS, under "Clone with HTTPS", copy the link.
4. Open Git Bash
5. Change the current working directory to the location where you want the cloned directory to be made.
6. Type `git clone`, and then paste the URL you copied in Step 3.

```
$ git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
```

7. Press Enter. Your local clone will be created.

Click [Here](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository#cloning-a-repository-to-github-desktop) to retrieve pictures for some of the buttons and more detailed explanations of the above process.

### MongoDB

#### Create the database

1. Login or register with MongoDB
2. Create a cluster and a database
3. Create three collections in the database: users, items and locations
4. Add the key:value pairs for each of the collections per the [schema](#database-schema)

#### Create the environment variables

1. Create a `.gitignore` file in the root directory of the project in Github
2. Add the `env.py` file to the `.gitignore` file 
3. Create the `env.py` file in the root directory of the project in Github
4. Enter the environment variables in the `env.py` file:

```
    import os

    os.environ.setdefault("IP", "insert IP here")
    os.environ.setdefault("PORT", "insert port here")
    os.environ.setdefault("SECRET_KEY", "insert secret key")
    os.environ.setdefault("MONGO_URI", "insert mongo uri")
    os.environ.setdefault("MONGO_DBNAME", "insert mongo db name")
```

For more information on creating a MongoDB database click [here](https://docs.atlas.mongodb.com/)

### Heroku

#### Prerequisites

Before creating the Heroku app, you must first set up two files needed for Heroku to properly run:
1. Requirements.txt (this contains all the packages required to run this project)
2. Procfile (this specifies the commands that are executed by the app on startup)

To create these files, type the following in the Github terminal:

```
pip3 freeze --local > requirements.txt
echo web: python app.py > Procfile
```

Open the Procfile and ensure there is no blank line at the end of the file as this may cause problems on Heroku.

#### Creating the app

1. Sign in or create an account on [Heroku](https://www.heroku.com)
2. Provide a unique app name, select region and click Create app

#### Connect to Github repository

1. On the Heroku dashboard, select the Deploy tab
2. In the Deployment method section, select Github
3. Enter your repository name and select Search, once it has found your repository select Connect
4. Next, select the Settings tab on the Heroku dashboard
5. Click Reveal Config Vars and enter the same environment variables from your `env.py` file
6. Click Hide Config Vars
7. In your Github terminal, use the following commands to push your requirements.txt and Procfile 

```
    $ git add requirements.txt
    $ git commit -m "Add requirements.txt file."
    $ git add Procfile 
    $ git commit -m "Add procfile."
    $ git push 
```
8. On the Heroku dashboard, return to the Deploy tab and select Automatic deploys followed by Deploy Branch (main)

Heroku will now start the deployment, this may take a while. When successfully deployed, you can select Open App which will open your live site in another tab.

For more information on Heroku deployment click [here](https://devcenter.heroku.com/start)

## Credits

### Code

-   The bulk of this app was built using the code for the Boutique Ado mini-project of CodeInstitute. 

### Images

-   Homepage background picture from: https://unsplash.com/photos/YpLN4HacUS4?utm_source=unsplash&utm_medium=referral&utm_content=creditShareLink (Photo by Ingo Ellerbusch on Unsplash)

### Acknowledgements

-  Code Institure Student Care for invaluable help.

-  Friends and family for feedback and helpful suggestions.
