# akc-meta

## Introduction

**akc-meta** and **akc-meta-query** are a pair of Polymer webcomponents that enable across DOM communication.  **akc-meta** is use to inject a *value* (value is a property of the elements) into global storage, whilst one or more **akc-meta-query** elements are used to read the value out again.

Values in global storage are accessed via  a *key* (again an element property) provided to the elements as strings. Values can be of any type including Object. 

## Changes to Values

Changes to values provided to the akc-meta value property are propogated to all related akc-meta-query elements, which in turn are "notified" to any data binding that may be attached to them.

## Changes to Keys

If an element changes the value of its key, then the value associated with it is re-evaluated.  For akc-meta elements, the values associated with the old key are either set to {} (where query elements are still looking at it) 0r deleted from global storage (where no query element is viewing it).  For akc-meta-query elements a key change will result in the value for the new key being notified.
