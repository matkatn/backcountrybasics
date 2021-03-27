---
title: Contact Form

form:
   name: contact

   fields:
      name:
         label: Name
         placeholder: Enter your name
         autofocus: on
         autocomplete: on
         type: text
         validate:
            required: true 
      email:
         label: Email
         placeholder: Enter your email address
         type: email
         validate:
            required: true

    #   message:
    #      label: Message
    #      placeholder: Enter your message
    #      type: textarea
    #      validate:
    #         required: true
 
      g-recaptcha-response:
         label: Captcha
         type: captcha
         recatpcha_site_key: 6LfQkZEaAAAAAIb1v992YYH54sLN1K_CGulxx856
         recatphcha_secret_key: 6LfQkZEaAAAAAJl0zgVM_vjG2Gvvx5wAazO74wuU
         recaptcha_not_validated: 'Captcha not valid!'
         validate:
            required: true

   buttons:
        submit:
            type: submit
            value: Submit
        reset:
            type: reset
            value: Reset

   process:
        email:
            subject: "[Site Contact Form] {{ form.value.name|e }}"
            body: "{% include 'forms/data.html.twig' %}"
        save:
            fileprefix: contact-
            dateformat: Ymd-His-u
            extension: txt
            body: "{% include 'forms/data.txt.twig' %}"
        message: Thank you for getting in touch!
        display: thankyou
---

Feel free to use this form for any questions regarding how you can become more involved with getting outside 