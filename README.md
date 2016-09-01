# Project2_Advanced_Web_app
Programming Assignment #2

Your project is due on Thursday, March 19th 4:00 PM. Pacific Coast Time.

#Entry Point:

The entry point for your project is a file called login.html. This should go at the top level in your web_services/ folder. Thus, your all of your pages will be deliver by Tomcat, not Apache. The first page of your project (the login screen) will be displayed if the user directs the browser to: http://jadran.sdsu.edu/jadrnXXX/login.html

#Java Web Services:

This assignment is an introduction to Java servlets and JSP (Java Server Pages). You may not place any part of the project code in or below your public_html directory or the cgi-bin directory for this project. [ NOTE: you should leave all product images where they are. The URL for product images should be a location in your public_html/ directory tree, and they should stay there. ] You may not use anything other than Java servlets/JSP for dynamic server-side code in this assignment; no Perl or PHP etc.

For this assignment you will create a portion of an inventory application for your online retail site. This portion is an application that will handle receipts of new merchandise and returns to vendor or sales of existing merchandise. More generally, merchandise RECEIVED INTO INVENTORY and merchandise REMOVED FROM INVENTORY. The intention here is an application that warehouse staff might use the record movement of inventory into and out of the warehouse. The application consists of the following:

#A login screen  
The user must supply an authorized username/password pair to gain access to the system.
#Inventory Received    
This form should have the following fields: Date, SKU, Vendor, Category, Manufacturer's Identifier, Quantity. The date field should be pre-filled with today's date. Once the user enters the SKU, all remaining fields except the quantity should be filled in using AJAX. The record must be stored in the MySQL database on opatija.sdsu.edu. You will need to create addional tables for this. Only the Date, SKU, and quantity fields should be editable.
#Inventory Sent Out
The specifications for this form are the same as for the Inventory Received form. However, these records go into a different table.
#Confirmation.   
After submitting either an Inventory Received, or Inventory Sent Out form, a confirmation should be displayed in the browser.
A logout link.   When this link is clicked, the user is logged out.
The Details:

#The login screen
Present the user with two fields, the username and password. The form will also have a clear and a submit button. If the user enters a valid username/password, the Menu page will load. If the login is invalid, then the login screen should reappear, along with a helpful error message.

Username/password pairs must be stored in the MySQL database on opatija. The username should be stored in plain text, and the password MUST be stored in an encrypted form. You may not use a text file on disk, nor may you hard code any name or password in your Java source code. You must have at least four valid username/password pairs, one of which must be:

        username:   cs645
        password:   sp2015
    
You should use POST as the parameter passing method. Use Javascript to place the cursor on the username field when the page loads. Simple things can mean a lot for useability. The user should not have to grab the mouse and manually give focus to the username field.

#The Inventory Received/Sent Out Screens
You must verify that the SKU entered matches a record in inventory. You cannot receive merchandise not ordered by the buyer, nor can you sent out things you don't have. Do not allow the form the be submitted if the SKU is invalid. Make sure that the quantity field is not zero or negative. Be sure to use Javascript to put focus on the first field when the page loads.

#Database Tables
You will need to create three new tables for this portion of the application.

#merchandise_in 
Merchandise received into the warehouse. This table should include sku, date, quantity fields.
#merchandise_out 
Merchandise sent out from the warehouse. This table should include sku, date, quantity fields.
#on_hand 
The on hand quantity for each item in inventory. This table should include sku, last_date_modified, on_hand_quantity fields.
