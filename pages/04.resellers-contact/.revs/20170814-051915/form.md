---
title: 'Resellers Contact'
form:
    name: 'New Wholeseller Account'
    fields:
        -
            name: name
            label: Name
            placeholder: 'Enter your name'
            autofocus: 'on'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        -
            name: email
            label: Email
            placeholder: 'Enter your email address'
            type: email
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
            message: 'Thank you for your feedback!'
        -
            display: thankyou
---

