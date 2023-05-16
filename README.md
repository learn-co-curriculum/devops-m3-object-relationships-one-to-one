# Modeling a One-to-One Relationship in Python

## Learning Goals

- Practice modeling a one-to-one relationship in Python.

## Introduction

Now that we know all the ways we can associate classes together in Python, let
us revisit the relationships we learned in SQL:

- one-to-one
- one-to-many
- many-to-many

In this lesson, we will learn how to model a one-to-one relationship in Python.
Let's take a look!

## One-to-One Relationships

Consider the one-to-one relationship in the ER diagram below:

![student-idcard-one-to-one](https://curriculum-content.s3.amazonaws.com/pe-mod-3/object-relationships/student-idcard-er-diagram.png)

Each `Student` has one `IdCard` and each `IdCard` belongs to one `Student`.

We already know how to model this in a database, but how would we relate these
two in Python? Let's create two classes: a `Student` class and an `IdCard`
class!

```py
class Student:
    def __init__(self, name, birthday):
        self.name = name
        self.birthday = birthday
        
class IdCard:
    def __init__ (self, id, active):
        self.id = id
        self.active = active

```

Currently, these two classes are not associated with each other. In order to
create a relationship between them, we'll need to add an `IdCard` instance to
the `Student` class.

```py
class Student:
    def __init__(self, name, birthday, idCard):
        self.name = name
        self.birthday = birthday
        self.idCard = idCard
        
class IdCard:
    def __init__ (self, id, active):
        self.id = id
        self.active = active

```

We can create this one-to-one relationship by adding an `IdCard` instance to
the `__init__` method.

## Knowledge Check

Let's assume that a person can only have one passport in our next use case.

![person-passport-one-to-one](https://curriculum-content.s3.amazonaws.com/pe-mod-3/object-relationships/person-passport-er-diagram.png)

Each `Person` has exactly one `Passport` and a `Passport` belongs to exactly
one `Person`.

<details>
  <summary>
      We'll need to create two classes in Python: a <code>Person</code> class and a <code>Passport</code> class.<br>
      How would we associate these two classes together to form a one-to-one relationship?
  </summary>

  <p>Add a <code>Passport</code> instance to the <code>__init__</code> method in the <code>Person</code> class.</p>

</details>

<details>
  <summary>What would the <code>Passport</code> class look like after we form the relationship?</summary>

  <img src="https://curriculum-content.s3.amazonaws.com/pe-mod-3/object-relationships/passport-class-python.png">

</details>

<details>
  <summary>What would the <code>Person</code> class look like after we form the relationship?</summary>

  <img src="https://curriculum-content.s3.amazonaws.com/pe-mod-3/object-relationships/person-class-python.png">

</details>
