URL: https://joseph-greenwell.mybigcommerce.com/?ctk=421abaa6-0e27-4411-99e2-b46b752c8d2d
<br>
Preview Code: 4y3hfk7rq0
<br>

Preview Video: https://drive.google.com/file/d/1Z37pCz6BgehxP1IBfOnKtKfr_ykuNDJV/view?usp=sharing
<br>

Preview Code:
So starting with the hover card i modified the card compnent to filter through the custom fields of a card and
check for any custom_fields with the name of 'hover_image' and used it to render the image with handlebars
![hover card](https://github.com/Jgreenwell93/BigCommerceInterviewProject/assets/69323366/6c3ec57a-73c0-4d79-844e-b2a96287c213)

from there we added some custom scss to only show the image when the card was hovered on as well as a transition to smooth it out

![hover css](https://github.com/Jgreenwell93/BigCommerceInterviewProject/assets/69323366/23c593d1-12f0-4479-a0c7-7ac4073add80)


next up were the add all and delete all buttons which were added on in a custom template
<br>
![custom cat](https://github.com/Jgreenwell93/BigCommerceInterviewProject/assets/69323366/ba3fbe6e-3fee-420f-89d8-d748f0894321)
<br> 

![custom buttons](https://github.com/Jgreenwell93/BigCommerceInterviewProject/assets/69323366/3858b369-ab76-41a5-ae90-d586e784f8ad)

some scss stylings as well as hiding the removal all button until we made that visible

![button scss](https://github.com/Jgreenwell93/BigCommerceInterviewProject/assets/69323366/50a0a0e0-a136-4264-b22f-dda83c3ca8b5)

NOTE: Normally i would have placed the javascript not in a script tag but in it's own file, but i felt this might be easier for viewing upon review

now this isnt the order in which i created these functions but i felt showing the delete button visibility function
was import to show first since it's used as a call back in the button functionality.

so this function is called upon page load to use the storefront api to check to see if there are any values within the cart, and if true displays the button
and if false, keeps it hidden
![deletebutton visibility1](https://github.com/Jgreenwell93/BigCommerceInterviewProject/assets/69323366/202f886e-b178-46b8-97ef-668ea5579142)

so first we have the add all button that when clicked wll add the item by item id to the cart. further development i would created a function
that would use a for loop to loop over all items within a category and for each one with a product ID would run the add function. but i wanted
to make sure i got my MVP turned it by my soft deadline.
When it finishes it's function of added the item(s) it then chains the delete button visibility function as a promise at the end to make sure the delete button becomes visible after
items have been added (or stays hidden if not) as well as displaying a pop up to notify that all items had been added to cart.

![add all button1](https://github.com/Jgreenwell93/BigCommerceInterviewProject/assets/69323366/98eeac03-9626-44c6-8c56-2d69cf0b1ac4)
![add all button 2](https://github.com/Jgreenwell93/BigCommerceInterviewProject/assets/69323366/16f66a77-5c50-4d3c-870d-ff4a39664eaa)

next up was the delete button. First i had it run the storefront api to get the current cart and extract the id from the returned object and
pass that as a variable into the storefront cart delete api. and at the end of it had it promise chain a function for the pop up that notifys the client
that all items have been removed, and then also runs the delete button visibility function again to rehide the button after the card has been cleared.

![delete funt 1](https://github.com/Jgreenwell93/BigCommerceInterviewProject/assets/69323366/39f633b2-4583-4cca-9a09-08cc45aea189)
![delete funt 2](https://github.com/Jgreenwell93/BigCommerceInterviewProject/assets/69323366/31b52606-a58c-4b01-a465-14d55971024e)
![delete button pop up](https://github.com/Jgreenwell93/BigCommerceInterviewProject/assets/69323366/a49d4d9a-d795-460b-81eb-f2d767157279)


and finally we come to the bonus where i just added to the custom category template an html div element
contained within a handlebars #if to check for a boolean of true if there was a customer, and if true render this div with the
extracted information. (could also be added to the main category component to apply to all of them
but i read the assignment as specificed to this custom one so i changed it from the main one to the custom one)

![bonus1](https://github.com/Jgreenwell93/BigCommerceInterviewProject/assets/69323366/b8659375-2ce9-44eb-9853-3c3048ee2113)







