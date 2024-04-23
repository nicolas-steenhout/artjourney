---
layout: page
title: Testing contact form
permalink: /contact-test/
---
Testing Basin forms for contact.

<form action="https://usebasin.com/f/f369a9edd4dd"  method="POST">
    <label for="name" autocomplete="on">Name:</label>
    <input type="text" id="name" name="name" required>
     <label for="email" autocomplete="on">Email (required):</label>
   <input type="email" id="email" name="email" aria-required="true">
    <label for="msg">Message:</label>
    <textarea id="msg" name="msg" rows="5" cols="20"></textarea>
   <input type="submit" value="Submit">
</form>