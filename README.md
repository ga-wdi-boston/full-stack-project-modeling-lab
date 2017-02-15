[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# Full Stack Project Modeling Lab

During this lab we are going to talk project ideas, how to take a 'shoot for
the stars' idea, and build it in a methodical fashion that will keep you on
track, while fixing *one* problem at a time.

When you're starting out as a developer, it's often a struggle to take a
grandiose idea and consolidate it into more managable pieces.

## Prerequisites

-   [full-stack-project-practice](https://github.com/ga-wdi-boston/full-stack-project-practice)

## Objectives

By the end of this, developers should be able to:

-   Properly scope projects.
-   Break apart an ERD into a 'to-do' list.
-   Plan feature progress effectively.
-   Prioritize objectives/tasks and descope accordingly.

## Preparation

1.  Fork and clone this repository.
 [FAQ](https://github.com/ga-wdi-boston/meta/wiki/ForkAndClone)

## What is `scope`? Why is it important?

Scope is typically a list of features or goals you have in mind for your
project for example, if I wanted to have users be able to sign up, log in,
change password, etc. those are all features I would like my application to have. They are *within* the scope of my project.

## Demo: Write an ERD and prioritize it

Let's take our 'library-api' as an example. In this domain, our main resource
is *books*. Books should belong to authors though, so we can look up all the
books that belong to an author, right!? What happens if an author has multiple
books, but some books have multiple authors!? We also probably need to have
*users* so that they can take out books, and users need to have passwords, and
need to be able to change their passwords, and what if we have multiple books,
can multiple users take out different versions of the same boo--[ohh no I've gone crosseyed](http://i.imgur.com/a7Yyjg8.gif).

Let's back it up, and take it one step at a time. Books. Books is our *main*
resource. So let's start there. The scope of my project would likely just start
with books. I would make sure I could CRUD on books, then I would add an
additional resource. How about authors?

It's OK for you ERD to change!

If I were building this out, I would start with just Book. ![Book](http://i.imgur.com/N1npKUD.png)

Once I had CRUD working on book (using curl and perhaps a dummy client), I
would move on to add authors.

To add authors I would make sure that books belonged to authors and that there
were no two authors the same, and add author's birthdays, and home town, and
favorite food, and--STOP! Add authors. That's IT.

![Author](http://i.imgur.com/lTnGitd.png)

That wasn't so hard, no was it? Test CRUD on authors! Now what do we need to
do? Well, we need to form some sort of relationship between authors and books.
Right, and we know that authors can have many books... but wait--can't books
have many authors!? Yep! But we aren't going to worry about that right now!
See how liberating this can be?! Let's get it working, THEN we'll change it.

![Relationship](http://i.imgur.com/vfWHyT6.png)

Test the relationship. Make sure you can get all books that belong to an
author, and that you can find an author that owns a book!

What's next? While we wanted to add a many-to-many relationship between authors
and books, it's not as important as allowing users to interact with books. So,
let's add our *User* model.

![User](http://i.imgur.com/sYjRXbz.png)

Boom. Now we have users. Let's test CRUD and pause for a second for some
`testing best practices`!

## CURL Scripts: But whyyyy?

CURL is your friend. It allows us as developers to *completely eliminate* the
front end or client from the equation. After you've built out a feature with
your API your FIRST inclination should be to test it with CURL. Because of this
we've put a `/scripts` directory in each of the templates we provide. Do
Future You a favor and start writing them out, save, and commit ones that you
know work. That way when you come back later and want to add a feature, it's
easy to test your previous work!

## Demo Continued...

Where were we? Because we have our overall ERD mapped out already, we have a
roadmap for where our final destination is. At this point, we want some sort of
association between a User and a Book.

It's time to choose your own adventure... Should you a) add a join table
because you know you're going to want books and users to have a `many-to-many`
relationship further down the road? OR b) build out your API methodically,
making sure everything is working before jumping in the deep end? If you picked
a) you're likely setting yourself up for headache.

a) ![a](http://i.imgur.com/4CPYxty.png)

b) ![b](http://i.imgur.com/XshAB3u.png)

Start with b. Once it's working properly, add the `Loan` resource, and create
the join table.

Remember: It's OK to change your ERD. It's ok to modify your database. There
are things to remember when you do, but don't feel like you need to get your
database and relationships all set up perfectly on Day 1. Things change, and
that's ok. The only way to be methodical when you build out these features is
to be ok with that inevitable change.

## Lab: Consider the previous example

Think about the example we just ran through. What are the *must* haves? What
are the nice to haves? Are there any resources we could do without? What would
we sacrifice if we aren't developing features as fast as we'd hoped? What if
all of a sudden, I wanted to add a Profile? How would our ERD change? What if
I wanted there to be two types of users, admins, and non-admins? What
priviliges would I allow? How would I control user AND admin ownership?

## Lab: Pitch Time!

You all should've completed the [full-stack-project-practice](https://github.com/ga-wdi-boston/full-stack-project-practice) at this point. We'll go around the room, and have people present,
or share their ideas and we'll descope and prioritize them together. Once we're
done, think about how YOUR project might be descoped, and what the priorities
are. Set yourself up for success! If you're unclear by the end of all of this,
schedule a 1-1 with a consultant to review your ERD, wireframes, and plan of
attack!

## [License](LICENSE)

1.  All content is licensed under a CC­BY­NC­SA 4.0 license.
1.  All software code is licensed under GNU GPLv3. For commercial use or
    alternative licensing, please contact legal@ga.co.
