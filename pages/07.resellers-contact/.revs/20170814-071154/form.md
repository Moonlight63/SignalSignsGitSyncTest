---
title: 'Resellers Contact'
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
                subject: '[Website Contact] {{ form.value.email|e }}'
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

