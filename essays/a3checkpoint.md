---
layout: essay
type: essay
title: A3 Checkpoint
# All dates must be YYYY-MM-DD format!
date: 2020-12-02
labels:
  - Assignment 3
  - Checkpoint
--- 

Show what each page will look like. The pages do not have to be “functional” but the design should clear. Here is an example PPT prototype


https://i.ibb.co/qgzCSKV/Untitled-presentation.jpg

Describe your design for your site’s shopping cart. That is, will it be a separate page that the user can view and edit, or will it be integrated into the product pages? If so, describe in detail how this will work on your site. Provide several examples of using the cart.

The shopping cart will be a separate page the user can view and edit. This will work by when the customer clicks the “add to cart” button the product will go into the cart, but the user won’t be directed into the cart. They will stay on the same page. A notification will appear that says “Added to cart!” so the user knows that they were successful. When the user clicks on the cart they will see their products and quantities and be able to edit them. 
Explain specifically how you will use sessions to manage your shopping cart. In particular, what shopping cart data will be stored in the session, what data format will be used (NOT what data type, but the format like with the data format used for your registration data). Use code examples showing what data structures (such as arrays and their objects) you will use to manage the shopping cart data and how they will be used in a session.

The shopping cart data that will be stored in the session is the product name and quantity. I have tested this and it seems to work, where when I have the same session ID the cart data is the same. However I need to figure out how to empty the cart after the purchase is complete. Right now what I have is  
function add_to_cart (i) {

   var incart = product_main_display[`quantity${i}`].value; 

   if (isNonNegInt(incart) = true) { 

       sessionStorage['products${i}'] = incart;

       console.log(incart) 

   } 

So the session storage should save the product${i} data. I'm basically using the array of products data and creating a function in order to add the product to the cart using sessionStorage.

How will you avoid access to your application when the user has not logged in or registered? What are the particular security concerns you must address?

I will avoid access to my application when the user is not logged in by writing an if / else statement. Basically, if the code recognizes that there is a user logged in with a cookie, they are able to access their invoice. If there is no cookie present, then they can’t see the invoice. Some security concerns I must address is stuff like making sure another user can’t see and edit another user’s cart, making sure others can’t use the same cookie, and making sure that when the invoice is processed it is secure. 
Upon a successful login, how do you provide personalization in your UI? Explain how you did or will do this (paste code if necessary)

I’ve been attempting to show personalization by doing <script>document.write(`You have ${cartitems.length} items in your cart!`);</script> but it has yet to actually work. However, on the invoice I have <script> document.write(`Thank you for your order ${params.get('name')}!`); </script> and that works to show the name. I still want/need to show login status and the number of items in the cart.
If you are working with partners, how will you split up the work in your team so that you are working in parallel as effectively as possible? That is, who is doing what and when?

I am not working with a partner. 
How are you approaching Assignment 3 differently than Assignment 2?

I’m starting way earlier. I am thinking more about what needs to be done in advance and planning better before starting. I am trying to remain calm but it is hard. I'm doing a lot more research and getting better at searching for more precise questions. I am thinking about what would be best for my project instead of doing what is easiest or most convenient.
