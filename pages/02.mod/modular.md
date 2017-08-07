---
title: Mod
content:
    items: '@self.modular'
    order:
        by: date
        dir: desc
body_classes: modular
recaptchacontact:
    enabled: false
twittercardoptions: summary
articleenabled: false
article:
    '@context': 'http://schema.org/'
    '@type': NewsArticle
    image:
        '@type': ImageObject
    publisher:
        '@type': Organization
        logo:
            '@type': ImageObject
musiceventenabled: false
musicevent:
    '@context': 'http://schema.org/'
    '@type': MusicEvent
    location:
        '@type': MusicVenue
    offers:
        '@type': Offer
        priceCurrency: AED
personenabled: false
person:
    '@context': 'http://schema.org/'
    '@type': person
    address:
        '@type': PostalAddress
eventenabled: false
event:
    '@context': 'http://schema.org/'
    '@type': Event
    location:
        '@type': Place
musicalbumenabled: false
musicalbum:
    '@context': 'http://schema.org/'
    '@type': MusicAlbum
    byArtist:
        '@type': MusicGroup
restaurantenabled: false
restaurant:
    '@context': 'http://schema.org/'
    '@type': Restaurant
    acceptsReservations: 'yes'
    priceRange: $
    address:
        '@type': PostalAddress
facebookenable: true
---

