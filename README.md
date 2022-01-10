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

        4. As a visiting user, I want to be able to quickly understand the purpose of the site
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
        16. As a customer, I want to be able to view my shopping basket
        17. As a customer, I want to be able to know the exact cost
        18. As a customer, I want to be able to make a secure purchase
        
-   ### Design
    -   #### Colour Scheme
        The use of colours has been kept to an absolute minimum on this site so as not to interfere with the product images. The background is kept white and the text black. The only time colours are used they are used for accents on messages or icons.
        
        ##### Accent colours
           ![Coolors rendering of effect colourscheme](https://github.com/MSierag/SiteStorage/blob/main/static/images/accent-colours.png?raw=true)
            
    -   #### Typography
        -   The font used throughout the site is 'Lato' from Google Fonts.

*   ### Wireframes
Due to the high number of pages and limited content on them I decided against creating wireframes in various formats as there would be very little difference between them.
The wireframes I did make can be viewed here [View](https://github.com/MSierag/SiteStorage/tree/main/static/images/wireframes)

## Database schema
The database for this website is run through HerokuPostgres, the schema can be found below.

![Dbdiagram.io rendering of the database schema](https://github.com/MSierag/SiteStorage/blob/main/static/images/dbschema.png?raw=true)


## Features
-   Top navbar at the top of the page is visible on all pages. The main navbar is visible on screensizes upwards of a tablet.

-   There is a banner below the navbars which informs the user of the free delivery threshold.

### Existing features

#### Page specific features

##### Welcome page

-   The page is largely taken up a by close up picture of a record player. 

-   On the background picture the bold statement to the user "Your vintage record in stock here" makes the purpose of the site instantly clear. 

-   Below the statement is a call to action button labelled "Shop now" which when clicked opens the Products page.

-   Other than the call to action button and the options on the navbars, the page is devoid of text or buttons.

##### Products page

-   Below the navbars and free delivery banner there is a page header which reads "Products".

-   Below the header the total number of products is displayed as well as a sort selection box.

-   The products are displayed as cards with the product image followed by the name, price, category and rating.

-   The product image serves as a button to lead the user to the product's detail page.

##### Product detail page

-   The product image is displayed on the left while the product info is displayed on the right.

-   The product info includes the name, price, category and rating followed by a more detailed description if available.  

-   Below the product info is a quantity selection box which is set to 1 by default.

-   Finally there are two buttons, one labelled "Keep Shopping" which when selected takes the user back to the Products page. The other button is labelled "Add to bag" which when selected adds the item to the shopping bag and causes a success message to be displayed in the top right hand corner of the screen.

##### Shopping bag page 

-   Below the navbars and free delivery banner there is a page header which reads "Shopping bag".

-   The contents of the shopping bag are displayed in a table with four columns: Product Info, Price, Quantity and Subtotal

-   Each product in the shopping bag is displayed as a row in this table. 

-   In the bottom right hand side of the screen below the last product are displayed the Bag total, Delivery cost, Grand Total and the message on which additional amount spent would secure the free delivery if the threshold hasn't been met.

-   Finally, there are two buttons: one labelled "Keep Shopping" which when selected takes the user back to the Products page. The other button is labelled "Secure Checkout" which when selected takes the user to the Checkout page. 

##### Checkout page

-   The Checkout page displays the order form to be completed on the left and the items in the shopping bag on the right.

-   If the user is logged in and has previously saved their delivery information this will be pre-filled in the relevant section of the order form.

-   The customer is required to fill out their Full Name and Email as well as put in their credit card information.

-   Below the order form are two buttons: one labelled "Adjust bag" which when selected takes the user back to the Shopping bag page. The other button is labelled "Complete Order" which when selected starts the payment process.

##### Sign up page

-   Below the navbars and free delivery banner there is a page header which reads "Sign up".

-   The user is asked to Log in if they already have an account.

-   The registration form requires the user to enter an email adress and confirm this, a user name and a password which also needs to be confirmed. 

-   Below the form are two buttons: one labelled "Back to login" which when selected takes the user to the Sign in page. The other button is labelled "Sign up" which when selected takes the user to the verification page. Here the user is informed that a verification email has been sent to their email address.

##### Sign in page

-   Below the navbars and free delivery banner there is a page header which reads "Sign in".

-   The user is asked to Sign up first if they do not already have an account.

-   The log in form requires the user to enter their username or email and their password. 

-   The user has the option to tick a "Remember Me" box

-   At the bottom of the form there are two buttons: one labelled "Home" which when selected takes the user back to the Welcome page. The other button is labelled "Sign in" which when selected and provided the sign in was successful will take the user back to the Welcome page with a success message displayed in the top right hand corner. 

##### Profile page

-   Below the navbars and free delivery banner there is a page header which reads "My Profile".

-   Any Default delivery information the user has previously saved is displayed here on the left.

-   Below the form is a button labelled "Update information" 

-   On the right hand side the Order history information for this user is displayed.


##### Product Management page

-   Below the navbars and free delivery banner there is a page header which reads "Product Manageent".

-   The form to be completed contains fields for Category, SKU, Name (required), Description (required), Has sizes, Price (required), Rating and Image URL.

-   Below the Image URL field is a button labelled "Select Image". 

-   At the bottom of the form there are two buttons: one labelled "Cancel" which when selected takes the user back to the Welcome page. The other button is labelled "Add Product" which when selected and provided the form was filled out correctly will take the user back to the Products page with a success message displayed in the top right hand corner.

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
1. [AWS:](https://www.aws.amazon.com/)
    - AWS S3 is used as storage for static files. 
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
-   Performance: 85%
-   Accessibility: 74%
-   Best Practices: 87%
-   SEO: 91%

The Performance score was negatively impacted by AWS and Stripe cache policies. The Accessibility score of 74% was among other things caused by the non-sequential use of headers on the Welcome Page. The text on the Shop Now button is larger than the text in the Free delivery banner. Also, some icons which are used as buttons are not explicitly declared as such in the HTML. The 87% in Best Practices was due to browser errors logged to the console caused by Stripe. 

### Responsiveness testing

To test the responsiveness of the site [Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools) and [Responsive Design Checker](https://responsivedesignchecker.com/) were used. 

#### Conclusions
Only on the smallest smartphone screen (320x480) did the background image interfere with the text on the buttons.  [Screensizemap](https://screensizemap.com/) was consulted to determine the popularity of this screen size.
The popularity listed for this type of screen hovers around 2% and seems to concern smartphones which can be considered at the end of their lifecycle. 
It is listed as a known issue.   

### Testing User Stories from User Experience (UX) Section

-   #### Owner Goals
    1. As an owner, I want to allow unregistered visitors to shop.
        1. The website allows all users (registered or unregistered) to view items, select them for purchase and complete a purchase without the need to create a profile or login. 
    2. As an owner, I want to encourage unregistered visitors to register
        1. Although all users are allowed to complete the purchase process without the requirement of registration, the navigation bar at the top includes a button labelled 'My Account' as gently encouragement to register.
        2. During the checkout process, customers are gently encouraged to create an account or login in the checkout form.
    3. As an owner, I want to restrict CRUD functionality on the site
        1. The ability to make changes to the product inventory is linked to the Product Management section. This section is only available to the admin superuser to ensure no unauthorised changes can be made. 
       
-   #### Visiting User Goals

    4. As a visiting user, I want to be able to quickly understand the purpose of the site.

        1. Upon reaching the Welcome page, users are automatically greeted with the clean and easily readable page which contains the background image of a vinyl record playing with the text 'Your vintage record in stock here' and a button labelled 'Shop Now'. [View](https://github.com/MSierag/SiteStorage/blob/main/static/images/testing/welcome.png?raw=true)
        2. Text has intentionally been kept to an absolute minimum. 
        3. At the top of the page are the top navigation bar which contains the Spincycle name and the main navigation bar below that which contains the various product categories.

    5. As a visiting user, I want to be able to easily navigate throughout the site

        1. The top of every page is reserved for the navigation bars. 
        2. The top navigation bar contains the Spincycle name (which also serves as a link to the Welcome page), the search bar and to the right the links to 'My Account' and the shopping bag with the current amount to be charged.
        3. Below the top navigation bar is the main navigation bar which contains the buttons for 'All Products', 'Vinyl', Cd's' and 'Special Offers'. Each of these contains a dropdown menu with further sub-classifications to allow the customer to drill down to their desired product category.
        4. The main navigation bar is reduced to a hamburger menu on mobile screens. The distinction between top and main navigation bar is otherwise not visible to the users.
        5. The various buttons on the respective pages are clearly marked and provide the expected functionality. The functionality is confirmed by flash messages.
    6. As a visiting user, I want to be able to search for specific items

        1. The top navigation bar which is always visible on all screens contains a search bar
        2. The main navigation bar below that contains the buttons for 'All Products', 'Vinyl', Cd's' and 'Special Offers'. Each of these contains a dropdown menu with further sub-classifications to allow the customer to drill down to their desired product category. 
    7. As a visiting user, I want to be able to make a purchase

        1. The ability to make a purchase is available to all users. It intentionally does not require the creation of an account or a login process.
    8. As a visiting user, I want to be able to distinguish between categories

        1. The main navigation bar contains the buttons for 'All Products', 'Vinyl', Cd's' and 'Special Offers'. Each of these contains a dropdown menu with further sub-classifications to allow the customer to drill down to their desired product category.
        2. When the user selects a particular subcategory, the page will display the selected category below the 'Products' heading.
        3. When the user selects the bottom option of the individual dropdown menus ('All Products', 'All vinyl', 'All CD's' and 'All Specials'), the page will display the available sub-categories for that category as buttons. For instance in 'All vinyl' the page will have the buttons 'Classical vinyl', 'Pop-vinyl', 'Folk-vinyl' and 'Oldies-vinyl'. 
    9. As a visiting user, I want to be able to register/create a profile

        1. The top navigation bar contains the link 'My Account' which when selected displays the dropdown menu of 'Register' and 'Login'
        2. The checkout form also contains the call to create an account or login.
        3. Selecting 'Register' in the top navigation bar or 'Create an account' in the checkout form leads the user to the Sign up page.
        4. In case of a problem an appropriate error message is displayed allowing the user to correct the mistake.
        5. Upon successful creation of an account, the user is taken to the confirm email page informing them a verification email has been sent to the email address they provided and the need to follow the link contained therein to complete the process. An appropriate alert is also displayed.

-   #### Registered User Goals

    10. As a registered user, I want to be able to login/log out.

        1. The top navigation bar which is visible on all pages contains the link 'My Account' which when selected displays the dropdown menu of 'Register' and 'Login'.
        2. Selecting 'Login' leads the user to the sign in page.
        3. While logged in / signed in the user can select 'My Account' to access the now updated dropdown menu with the options 'My Profile' and 'Logout'.
        4. Selecting 'Logout' leads the user to the sign out page. Here the user is presented with two buttons: 'Cancel' and 'Sign out'.
        5. Selecting 'Sign out' leads the user to the Welcome page while displaying an appropriate success message of 'You have signed out!'
        
    11. As a registered user, I want to be able to check my profile data
        
        1. While logged in / signed in the user can select 'My Account' to access the now updated dropdown menu with the options 'My Profile' and 'Logout'.
        2. Selecting 'My Profile' leads the user to the Profile page which displays the default delivery information as previously provided by the user as well as the order history(if any). 
        
    12. As a registered user, I want to be able to edit my profile data

        1. While logged in / signed in the user can select 'My Account' to access the now updated dropdown menu with the options 'My Profile' and 'Logout'.
        2. Selecting 'My Profile' leads the user to the Profile page which displays the default delivery information as previously provided by the user as well as the order history(if any). 
        3. The user has the option of updating the default delivery information.

    13. As a registered user, I want to be able to view my purchase history

        1. While logged in / signed in the user can select 'My Account' to access the now updated dropdown menu with the options 'My Profile' and 'Logout'.
        2. Selecting 'My Profile' leads the user to the Profile page which displays the default delivery information as previously provided by the user as well as the order history(if any).

-   #### Customer (both visiting and registered users) Goals

    14. As a customer, I want to be able to view details of the items

        1. On the Products page, the user is provided with condensed information on the various products consisting of the image, name, price, category and rating.
        2. Clicking on the product image, the user is lead to the product's detail page which displays the same information as well as a description, a quantity selector and two buttons labelled 'Keep shopping' and 'Add to bag'.

    15. As a customer, I want to be able to adjust the number of items to purchase

        1. On the product's detail page there is a quantity selector which is set to '1' by default.
        2. By clicking the plus and minus signs on either side of the selector, the user is able to adjust the quantity.
        3. Alternatively, the user may opt to alter the number displayed in the quantity selector directly.
        4. On the shopping bag page the user also has the option to adjust the quantity or remove the item altogether befor proceeding to the checkout.

    16. As a customer, I want to be able to view my shopping basket

        1. The top navigation bar contains a link to the shopping basket with the current amount contained therein.
        2. Clicking the shopping basket icon on the top navigation bar leads the user to the shopping bag page.

    17. As a customer, I want to be able to know the exact cost

        1. On the shopping bag page, the exact cost is displayed to the bottom right hand side. 
        2. The cost is broken down by Bag total, Delivery (if the threshold for free delivery has not been met) and the Grand total.
        3. Below the Grand total the user is informed in red which additional amount will secure free delivery if the threshold has not been met.

    18. As a customer, I want to be able to make a secure purchase

        1. On the shopping bag page in the bottom right hand corner is a button labelled 'Secure checkout'
        2. Alternatively, when an item has been added successfully a success message is displayed also containing a button labelled 'Secure checkout'
        3. Clicking either of these buttons leads the user to the checkout page which contains a form to be completed with the delivery information on the left and the order summary on the right.
        4. If the user is registered and has previously stored delivery information the form will be pre-filled with this information. Alternatively, the user can click the link provided to create an account or log in.
        5. The payment process is handled by Stripe to ensure secure payment.
                
### Known Issues

-   On mobile devices with a screen narrower than 360px the contents of the card section on index.html pushed out of alignment.
    -   Text and text on buttons disappears from view as a result.

## Deployment

### GitHub

The project is run on GitHub, but deployed to Heroku and uses AWS S3 for the static files:

#### Forking the GitHub Repository

By forking the GitHub Repository you make a copy of the original repository on your GitHub account to view and/or make changes without affecting the original repository by using the following steps:

1. Log in to GitHub and locate the [Spincycle repository](https://github.com/)
2. At the top of the Repository (not top of page) just above the "Settings" Button on the menu, locate the "Fork" Button.
3. You should now have a copy of the original repository in your GitHub account.

#### Making a Local Clone

1. Log in to GitHub and locate the [Spincycle repository](https://github.com/)
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
3. After the app has been created, click on the Resources tab and in Add ons type in and then select "Heroku Postgres". This will create a DATABASE_URL in the Config Vars.

#### Connect to Github repository

1. On the Heroku dashboard, select the Deploy tab
2. In the Deployment method section, select Github
3. Enter your repository name and select Search, once it has found your repository select Connect and enable automatic deployments
4. Now go back to your Github terminal and type `pip3 install dj_database_url` followed by `pip3 install psycopg2-binary` to enable use of the HerokuPostgres database.
5. Next type `pip3 freeze > requirements.txt` in the terminal
6. In the settings.py file import dj_database_url and comment out the default DATABASES
7. Set up a new database connection by typing in 
```
DATABASES = {
    "default": dj_database_url.parse("HerokuPostgresdatabase_url which can be found in the Heroku Config Vars")
}
```
8. Still in the Github terminal, type the following
```
    $ python3 manage.py showmigrations
    $ python3 manage.py migrate
    $ python3 manage.py loaddata categories
    $ python3 manage.py loaddata products
    $ python3 manage.py createsuperuser
```
This will correctly populate the database with categories and products.
9. In settings.py replace the DATABASES code with the following:
```
if 'DATABASE_URL' in os.environ:
    DATABASES = {
        'default': dj_database_url.parse(os.environ.get('DATABASE_URL'))
    }
else:
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.sqlite3',
            'NAME': BASE_DIR / 'db.sqlite3',
        }
    }
```
10. In the terminal type
```
    $ pip3 install gunicorn
    $ pip3 freeze > requirements.txt
```
11. Next, create a Procfile and type in:
```
web: gunicorn spincycle.wsgi:application
```
12. Login to Heroku using the command line by typing:
```
    $ npm install -g heroku
    $ heroku login -i
    (you will now be asked for your email and password)
    $ heroku config:set DISABLE_COLLECTSTATIC=1 --app (your app name here)
```
You can also set the DISABLE_COLLECTSTATIC in the Heroku Config Vars.
13. Add your Heroku app to settings.py Allowed hosts section
```
['your Heroku app url here', 'localhost']
```
14. Push to Github and Heroku
15. Generate a Django secret key and add it to the Heroku Config Vars as SECRET_KEY
16. In settings.py set SECRET_KEY to 
```
SECRET_KEY = os.environ.get('SECRET_KEY', '')
```
and DEBUG to
```
DEBUG = 'DEVELOPMENT' in os.environ
```
17. In Heroku in the Deploy tab set the connection to your Github repository to automatic deployment.
18. Push your code to Github, this should start the deployment of your app on Heroku. 

For more information on Heroku deployment click [here](https://devcenter.heroku.com/start)

### AWS S3

#### How to set up AWS S3

1. Go to [AWS](https://aws.amazon.com/) and login to your account. If you don't have an account, create one. If you have to create an account be mindful that you will need to enter your card details, no billing will occur unless you go over the free tier limit.

2. After logging in, go to the [S3](https://console.aws.amazon.com/s3/) and create a bucket.

3. Make sure you name your bucket the same as you did for Heroku and choose the nearest region to your location.

4. Scroll down to the "Block Public Access" section and unchecked the "Block public access" checkbox. Confirm that you want to allow access to the bucket. Scroll down to the bottom of the page and click on "Create bucket"

---

#### Customizing the bucket properties

1. Click on the Properties tab. Scroll to the end of that page and click on edit button.

2. At the top it will allow you to choose between "Enable" and "Disable" static website hosting. Choose Enable.

3. The section below will allow you to select "Host a static website", Select "Host a static website" and then scroll down to the index "Document inputs"

4. In the input field, enter the home file which is the "index.html" file and in the error field, enter "error.html".

5. Leave the redirection rules empty and click on "Save changes".

---

#### Setting up the Permissions

1. Next, go to the permissions tab. Scroll down to the bottom of the page and click edit the "Cross-Origin Resource Sharing (CORS)" section.

2. Add the following lines:

```
[{
  "AllowedHeaders": ["
  Authorization"
  ],
  "AllowedMethods": [
    "Get"
    ],
  "AllowedOrigins": [
    "*"
    ],
  "ExposeHeaders": [],
}]

```

3. Save the changes. Navigate to "Bucket Policy" section and click "edit"

#### Generating A Bucket Policy

1. Click on the "Policy Generator" button. Select "S3 Bucket Policy" from the dropdown list.

2. You will need to set following permissions:

   - Effect – Allow
   - Principle - \*
   - Actions – GetObject, GetObjectAcl, PutObject, PutObjectAcl and DeleteObject
   - Amazon Resource Name – This can be found on the previous page, under "Bucket ARN". Copy and paste it into this box

3. After these have been entered, click "Add Statemen" and "Generate Policy".

4. Copy the policy into the bucket policy editor, adding `/*` onto the end, the click "Save Changes".

---

#### Access Control List

1. While in the permissions tab, click "edit" under the "Access Control List" section.

2. Next, navigate to "Everyone (public access)" and tick the box on the left, "List" under the "Objects" heading. Tick the box that you understand the effect then click on "Save Changes".

---

#### Creating A Group and Policy with IAM

1. Next, search for IAM in the search bar at the top, and click on it to set up a group policy.

2. Under "Access Management", Select "User Groups" and create a new group.

3. Give the group a name (try keep it relational to the project name) and click "Create Group".

4. This will bring you to the IAM dashboard. Go to the "Access Management" section, and click on "Policies".

5. Click "Create Policy" and click on the JSON tab, and select "Import Managed Policy".

6. Search for "AmazonS3FullAccess" and select it, then Import".

7. Copy your ARN and place it in the code twice (the second time with `/*`) so that it looks like the following;

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:*",
                "s3-object-lambda:*"
            ],
            "Resource": [
                "arn:aws:s3:::YOUR-ARN",
                "arn:aws:s3:::YOUR-ARN/*"
            ]
        }
    ]
}
```

8. Select "Next: Tags", "Next: Review", Enter a name and click on "Create Policy".

---

#### Attaching the Group Policy

1. Go to "User Groups", under "Access Management". Click on the your newly created group and go over to the "Permissions" tab

2. Select the "Add Permissions" button, and select "Attach Policy".

3. Search for and click on the checkbox next to the policy you have just created, then Select "Add Permissions".

---

#### Create User for IAM

1. Head back to the IAM dashboard, click on "Users", then "Add User".

2. Choose a name and tick the checkbox to give the user access, then select "Next: Permissions".

3. Select the group to put the user in and keep clicking the next buttons until the very end and click "Create user".

4. Click on “Download .csv” file (**Keep this is a secure location as you wont be able to get these details again**), as you will not have access to this page again! This file will contain information required as shown in the Heroku table above.

---

### Github

1. In the terminal type 
```
    $ pip3 install boto3
    $ pip3 install django-storages
    $ pip3 freeze > requirements.txt
```
2. In settings.py in the Installed apps section add 'storages'. Under the MEDIA_ROOT add the following:
```
if 'USE_AWS' in os.environ:
    

    # Bucket Config
    AWS_STORAGE_BUCKET_NAME = 'your bucket name'
    AWS_S3_REGION_NAME = 'your region here'
    AWS_ACCESS_KEY_ID = os.environ.get('AWS_ACCESS_KEY_ID')
    AWS_SECRET_ACCESS_KEY = os.environ.get('AWS_SECRET_ACCESS_KEY')
    AWS_S3_CUSTOM_DOMAIN = f'{AWS_STORAGE_BUCKET_NAME}.s3.amazonaws.com'

    # Static and media files
    STATICFILES_STORAGE = 'custom_storages.StaticStorage'
    STATICFILES_LOCATION = 'static'
    DEFAULT_FILE_STORAGE = 'custom_storages.MediaStorage'
    MEDIAFILES_LOCATION = 'media'
```

---

### Heroku

1. In the Config Vars add the AWS_ACCESS_KEY_ID and the AWS_SECRET_ACCESS_KEY as well as setting USE_AWS to 'True' and removing the DISABLE_COLLECTSTATIC.

### Github

1. Create a custom_storages.py file and type the following:
```
from django.conf import settings
from storages.backends.s3boto3 import S3Boto3Storage


class StaticStorage(S3Boto3Storage):
    location = settings.STATICFILES_LOCATION


class MediaStorage(S3Boto3Storage):
    location = settings.MEDIAFILES_LOCATION
```
2. In settings.py add cache control to the if USE_AWS statement under MEDIA_ROOT:
```
# Cache control
    AWS_S3_OBJECT_PARAMETERS = {
        'Expires': 'Thu, 31 Dec 2099 20:00:00 GMT',
        'CacheControl': 'max-age=94608000',
    }
```
3. Push your code to Github

### Saving Images To S3 Bucket

If you need to save images to your S3 bucket, you will need to do the following;

1. Go to the S3 dashboard and click on the bucket you want to save the images to.

2. Click "Create Folder", call it "media" and click the second "Create Folder" button.

3. When you are in this folder, click "Upload", then 'Add Files" or "Add Folder", then "Upload".

---

### Stripe

1. Don't forget to add the STRIPE_PUBLIC_KEY and STRIPE_SECRET_KEY to the Heroku Config Vars as well as any other variables you may have.

## Credits

### Code

-   This app was built using the code for the Boutique Ado mini-project of CodeInstitute. Frankly, Django has me beat thus far, but I look forward to continuing to learn. 

### Images

-   Homepage background picture from: https://unsplash.com/photos/YpLN4HacUS4?utm_source=unsplash&utm_medium=referral&utm_content=creditShareLink (Photo by Ingo Ellerbusch on Unsplash)

### Acknowledgements

-  Code Institure Student Care for invaluable help.

-  Friends and family for feedback and helpful suggestions.
