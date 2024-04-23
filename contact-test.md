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

## Form suggested by Basin (using ChatGPT)

<form action="https://usebasin.com/f/f369a9edd4dd" method="POST">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required autocomplete="name" placeholder="Enter your full name" />
    
    <label for="email">Email (required):</label>
    <input type="email" id="email" name="email" required aria-required="true" autocomplete="email" placeholder="you@example.com" />
    
    <label for="msg">Message:</label>
    <textarea id="msg" name="msg" rows="5" cols="20" aria-describedby="msgHelp" placeholder="Type your message here"></textarea>
    <small id="msgHelp">Please keep your message brief and to the point.</small>
    
    <input type="submit" value="Submit" />
</form>
<script>
document.getElementById('contactForm').addEventListener('submit', function(event) {
    event.preventDefault();
    let isValid = true;
    clearErrors();

    // Validate Name
    let name = this.name.value.trim();
    if (!name) {
        showError('nameError', 'Name is required.');
        isValid = false;
    }

    // Validate Email
    let email = this.email.value.trim();
    if (!email) {
        showError('emailError', 'Email is required.');
        isValid = false;
    } else if (!/\S+@\S+\.\S+/.test(email)) {
        showError('emailError', 'Please enter a valid email address.');
        isValid = false;
    }

    // Validate Message
    let message = this.msg.value.trim();
    if (!message) {
        showError('msgError', 'Message cannot be empty.');
        isValid = false;
    }

    if (isValid) {
        this.submit();
    }
});

function showError(id, message) {
    let errorDiv = document.getElementById(id);
    errorDiv.textContent = message;
    errorDiv.style.display = 'block';
}

function clearErrors() {
    document.querySelectorAll('.error').forEach(function(errorDiv) {
        errorDiv.textContent = '';
        errorDiv.style.display = 'none';
    });
}
</script>
<style>
.error {
    color: red;
}
</style>