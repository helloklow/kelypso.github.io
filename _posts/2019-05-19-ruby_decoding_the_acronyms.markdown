---
layout: post
title:      "Ruby: Decoding the Acronyms"
date:       2019-05-20 00:49:12 +0000
permalink:  ruby_decoding_the_acronyms
---


After completing object-oriented Ruby, we immediately launched into orbit to find ourselves adventuring amidst an entire universe of new languages, gems, and frameworks... Most of which are commonly and confusingly referred to by acronym. Before your head begins spinning with letters and single-syllable words, let's deconstruct these various acronyms and additions to our developer toolbox.

**OOP** Object-oriented programming. Based around the concept of objects, which may contain data that can be accessed and manipulated through programmed methods.

**WAF** Web application framework. A software framework that provides a standard way to build and deploy web applications.

**ORM** Object relational mapping. Allows developers to access a relational database using object-oriented programming. Enables the ability to map tables to classes and rows to instances of that class.

**MVC** Model-View-Controller. A common way to build web application frameworks. MVC relies on separation of concerns, where files are grouped based on their function and how they interact with one another. Models represent the logic, where data is stored or manipulated. Views represent the front-end that users interact with. Controllers represent the bridge between the models and views, passing data from the users to the back-end.

**CRUD** Create, retrieve, update, delete. These actions represent the fundamental functions that ActiveRecord provides to a database. This powerful functionality helps developers implement RESTful routes between the views (users) and the database.

**RESTful** Representation State Transfer. This is an architectural style for defining routes, a way of mapping HTTP routes while implementing CRUD. It consists of seven routes, each of which either receive requests from the user or determine what to return to the user.

**HTML** Hypertext markup language. The standard markup language for webpages and web applications.

**CSS** Cascading style sheets.  A style sheet language that describes the presentation or visual design of a markup language document, such as HTML.

**SQL (SQLite3)** Structured query language. Manages the data that's held in a relational database.

**ActiveRecord** A Ruby gem and ORM for working with relational databases, mapping rows to Ruby objects. It connects to the database to provide built-in, powerful functionality through class inheritance. Rather than manually coding SQL queries, create and retrieve data with simple Ruby code and using ActiveRecord to abstract the rest.

**Sinatra** A Ruby gem and WAF that is able to pre-write common abstract methods to build Ruby web applications easily and efficiently.

**Rack** A Ruby gem that acts as interface between the webserver and web application (Sinatra or Rails). It provides the "common ground", functioning as the translator between the webserver and Ruby framework.

**Tux** A Ruby gem that allows developers to access a database and perform CRUD actions on it through the terminal. Useful for testing if the database and ActiveRecord associations are working poperly and for playing with Ruby objects.

**Capybara** A Ruby gem that allows developers to write code that simulates how a user would interact with the application. It automates web application testing for behavior-driven development.
