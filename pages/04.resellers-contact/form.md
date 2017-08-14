---
title: 'Wholesale Info'
recaptchacontact:
    enabled: false
form:
    name: 'New Wholeseller Account'
    fields:
        -
            name: name
            label: 'Name on Account'
            placeholder: 'Enter your name'
            autofocus: 'on'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        -
            name: email
            label: 'Email on Account'
            placeholder: 'Enter your email address'
            type: email
            validate:
                required: true
        -
            name: phone
            label: 'Contact Phone Number'
            placeholder: 'Enter your phone number'
            type: text
            validate:
                required: true
        -
            name: g-recaptcha-response
            label: Captcha
            type: captcha
            recaptcha_not_validated: 'Captcha not valid!'
            validate:
                required: true
    buttons:
        -
            type: submit
            value: Submit
    process:
        -
            email:
                from: '{{ config.plugins.email.from }}'
                to: ['{{ config.plugins.email.from }}', '{{ form.value.email }}']
                subject: '[Website Wholeseller Request] {{ form.value.email|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: wholeseller-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            captcha: null
        -
            message: 'Thank you for signing up! Your account will be converted as soon as possible.'
        -
            display: /thankyou
---

[center] 
### Resellers, please note that wholesale pricing has gone to a flat rate!

To access wholesale pricing, you must create a shopping account with Signal Signs, then fill out this request form to have your account elevated to whole-seller status. This is a very simple 1 time process and takes about 2 minutes.
If you are an existing reseller with Signal Signs (From before the re-branding), please be aware that your old login credentials will no longer function.
[/center]
1. Click [here](/shop/#!/~/accountSettings?target=_blank) to go to the login page.
2. Then, click on Create new account.
3. Fill out your Name, Email, and create a Password, then click Register.
4. That's It! Come on back to this page and fill out the form below.
5. If you don't see any changes when placing your order right away, please allow up to 24 hours for your account to be upgraded. Generally this happens within one bushiness day or sooner.
6. Resellers in Washington state, your account will automatically become tax exempt.