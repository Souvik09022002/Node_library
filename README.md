# Library-Management-System-Nodejs & mysql
here i create a projet that can handel the librarian day to day task very easyly .here have two part on this project one is the 
admin part: here the admin person first login use his user email and password and than its take on the dashboard page where he show alaround his management status and customer details.
       * show all details in dashboard
       * check its own profile
       * update his profile
       *change password
       *show all customer details
       *add customer & delete customer
       *edit customer details
       *show all book records in a list format
       *here he can add new book
       *check issed books
       *accept the requested of the user
       *view the requested books
user part:
       *user create new account
       *login via email & password
       *show this dashboard
       *show is Total books borrowed
       *show his profile
       *edit & change password of own details
       *show his recive books list down
       *request any book with there details
       *shoe book history and borrowd book.

stucture:
       |--/controller
            |-admin.js
            |-customer.js
            |-login.js
            |-logout.js
            |-singup.js
       |
       |--/css
            |-admin.css
            |-customer.css
            |-login.css
            |-singup.css
       |
       |--/iages
       |
       |--/models
            |-bookModel.js
            |-config.js
            |-userModel.js
       |
       |--/views
            |---/admin
            |---/customer
            |---/partials
            |--login.ejs
            |--singup.ejs
       |----app.js
       
*system requrements:
1)XAMPP server
2)nodejs
3)vs code

# 1st step:
   open XAMPP server  & run my (libray_management_system.sql);
   
# 2nd step:
1way:
*make a New folder
*open terminal of it and type this.
      1)git clone https://github.com/Souvik09022002/Node_library.git
      2)npm i
      3)npm start


2nd way:
download zip and extract it 
and than flow this steps
    a.   npm init -y,
    b.  npm install
    c.  npm start

# 3rd step:
    1)create a account
    2)singup

