---
title: 'Get in Touch'
menu: Contacts
form:
    addressstring: Address
    name: contact
    fields:
        -
            name: name
            label: 'Your name'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        -
            name: email
            label: 'Your e-mail address'
            type: email
            validate:
                required: true
        -
            name: message
            label: 'Your message'
            type: textarea
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
        -
            type: reset
            value: Reset
    process:
        -
            email:
                subject: '[Site Contact Form] {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: contact-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            message: 'Thank you for getting in touch!'
        -
            display: thankyou
---

If you need further information, you may just send us an e-mail or give us a call.