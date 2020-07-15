# Interface


There are two parts to the SourceScape interface. There is an interactive editor for the query. There is also a results table where the results of the query are displayed, refreshing when you update the query.

<img src="https://github.com/sourcescapeio/sourcescape-docs/blob/master/pics/interface.png?raw=true" width="400"/>

## Query Display


A query is made up of many selectors, similar to JQuery selectors or a GraphQL query.

It starts with a root selector.

<img src="https://github.com/sourcescapeio/sourcescape-docs/blob/master/pics/root.png?raw=true" width="400"/>

From this selector, you can add other selectors of a specific type.

For example, from this class selector, you can add a class-method selector.

<img src="https://github.com/sourcescapeio/sourcescape-docs/blob/master/pics/add1.png?raw=true" width="400"/>

<img src="https://github.com/sourcescapeio/sourcescape-docs/blob/master/pics/add2.png?raw=true" width="400"/>

Most selectors have a name and some selectors have an index.

Here, our class-method selector's name is "render"

The query results display a table of traces from the root selector.

<img src="https://github.com/sourcescapeio/sourcescape-docs/blob/master/pics/results1.png?raw=true" width="400"/>

In this case, it's getting all classes and then all methods in those classes named "render".

The query display can contain multiple root selectors, each of which is assigned its own block in the query and tab in the results.

<img src="https://github.com/sourcescapeio/sourcescape-docs/blob/master/pics/blocks.png?raw=true" width="400"/>

Some selectors have filters that are essentially a WHERE statement for a particular selector. Our class selector has an extends filter that we can use.

<img src="https://github.com/sourcescapeio/sourcescape-docs/blob/master/pics/filter1.png?raw=true" width="400"/>

Filters can be specified by adding a quick search through the pop-up menu, as above.

Or by dragging an already specified query into it.

<img src="https://github.com/sourcescapeio/sourcescape-docs/blob/master/pics/filter2.png?raw=true" width="400"


# Quick Search

Quick search is a way of adding several selectors all at once.

## Root selectors

`require('express')` will select any imports.
`<identifier>` will select an identifier.


## Chained selectors

`()` will select the call of a selector.

For example: `require('express')()` selects all calls of require


`.<name>` will select the member <name> of a selector.

For example: `require('react').Component`.


```
require('express')().use()
```

These can be chained together.


## Function selector


```
function() {}
```
Get an empty function selector. This will select any function.

```
function myFunc() {}
```
This will select any function named myFunc.


```
function(arg) {}
```
This will select any function and its first argument.

```
function(_, arg) {}
```
This will select any function and its second argument.


## Class selector

```
class {}
```
This will select any class.

```
class myClass {}
```
This will select any class named myClass.

## React

```
<? />
```
This will select any React element.

```
<div />
```
This will select any React element with a `div` tag.
 
```
<div style={} />
```
This will select any React element with a `div` tag and `style` attribute.
/>

