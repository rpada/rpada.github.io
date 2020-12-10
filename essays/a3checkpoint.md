---
layout: essay
type: essay
title: Assignment 3 Checkpoint 
# All dates must be YYYY-MM-DD format!
date: 2020-12-02
labels:
  - Checkpoint
  - Reflection
--- 
Show what each page will look like. The pages do not have to be “functional” but the design should clear.

https://i.ibb.co/qgzCSKV/Untitled-presentation.jpg

1. Describe your design for your site’s shopping cart. That is, will it be a separate page that the user can view and edit, or will it be integrated into the product pages? If so, describe in detail how this will work on your site. Provide several examples of using the cart.

The shopping cart will be a separate page the user can view and edit. This will work by when the customer clicks the “add to cart” button the product will go into the cart, but the user won’t be directed into the cart. They will stay on the same page. A notification will appear that says “Added to cart!” so the user knows that they were successful. When the user clicks on the cart they will see their products and quantities and be able to edit them. 

2. Explain specifically how you will use sessions to manage your shopping cart. In particular, what shopping cart data will be stored in the session, what data format will be used (NOT what data type, but the format like with the data format used for your registration data). Use code examples showing what data structures (such as arrays and their objects) you will use to manage the shopping cart data and how they will be used in a session.

When you assign a session and have users add products to the “cart”, the data is persistent. Since we are assigning a session ID to somebody, even if they leave and come back, that ID is still assigned thus the data stays the same. Using sessions will allow me to have the data be there even if the user goes to a different website.  

I will give different sessions to different users so users don’t override other people’s carts. The session tracks users given each request. Instead of using the server to sort out people’s data and cart, the session does it so everyone can have their own experience. 

The shopping cart data that will be stored in the session is the product name and quantity. I have tested this and it seems to work, where when I have the same session ID the cart data is the same. However I need to figure out how to empty the cart after the purchase is complete. Right now what I have is  
function add_to_cart (i) {
   var incart = product_main_display[`quantity${i}`].value; 
   if (isNonNegInt(incart) = true) { 
       sessionStorage['products${i}'] = incart;
       console.log(incart) 
   } 
So the session storage should save the product${i} data.
 
3. How will you avoid access to your application when the user has not logged in or registered? What are the particular security concerns you must address?

I will avoid access to my application when the user is not logged in by writing an if / else statement. Basically, if the code recognizes that there is a user logged in with a cookie, they are able to access their invoice. If there is no cookie present, then they can’t see the invoice. Some security concerns I must address is stuff like making sure another user can’t see and edit another user’s cart, making sure others can’t use the same cookie, and making sure that when the invoice is processed it is secure. 

When a user logs in, a cookie should be assigned to them. When they move back and forth, the user should still have the cookie at all times so the data stays present always (or until it expires). I can use cookies to handle security because if someone doesn't have the right cookie they won’t be able to access a page. 

4. Upon a successful login, how do you provide personalization in your UI? Explain how you did or will do this (paste code if necessary)

I’ve been attempting to show personalization by doing <script>document.write(`You have ${cartitems.length} items in your cart!`);</script> but it has yet to actually. However, on the invoice I have <script> document.write(`Thank you for your order ${params.get('name')}!`); </script> and that works to show the name. I still want/need to show login status and the number of items in the cart.

Instead of taking the username from the query string, I would take the username in the cookie and add it to the cart or invoice. 

5. If you are working with partners, how will you split up the work in your team so that you are working in parallel as effectively as possible? That is, who is doing what and when?

I am not working with a partner. 

6. How are you approaching Assignment 3 differently than Assignment 2?

I’m starting way earlier. I am thinking more about what needs to be done in advance and planning better before starting. 
