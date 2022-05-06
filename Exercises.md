# Exercises

([[Exercise_Solutions|Solutions]])

## Understanding NIEM Objects

Let's think about cardinality a little:

1. What happens if `maxOccurs` is less than `minOccurs`? (You can try this out in an editor, or just think about what _should_ happen.)
2. What do you think happens if `maxOccurs` is set to zero? Why might you want to do that?
3. What are some cases where you might want a `maxOccurs` that is greater than 1, but not unbounded?

## Native Properties

This is an open-ended exercise. There's no answer. The idea is to get a little familiar with the tools and some of the major NIEM objects. Try using both the SSGT and Wayfarer:

1. Search for, then look around at some common NIEM elements:
	- `nc:Activity`
	- `nc:Identification`
	- `nc:Location`
	- `nc:Organization`
	- `nc:Person`

## Substitution Groups

1. What are all the different ways that NIEM can represent a date?
2. Take a look at the following elements and how they fit together via substitution groups. What do you think the reason for all this might be?
	- `nc:Entity` ([SSGT](https://tools.niem.gov/niemtools/ssgt/SSGT-GetProperty.iepd?propertyKey=o4-8ow)/[Wayfarer](http://niem5.org/wayfarer/nc/Entity.html))
	- `nc:EntityRepresentation` ([SSGT](https://tools.niem.gov/niemtools/ssgt/SSGT-GetProperty.iepd?propertyKey=o4-8ox)/[Wayfarer](http://niem5.org/wayfarer/nc/EntityRepresentation.html))
	- `nc:EntityOrganization` ([SSGT](https://tools.niem.gov/niemtools/ssgt/SSGT-GetProperty.iepd?propertyKey=o4-8oz)/[Wayfarer](http://niem5.org/wayfarer/nc/EntityOrganization.html))
	- `nc:EntityPerson` ([SSGT](https://tools.niem.gov/niemtools/ssgt/SSGT-GetProperty.iepd?propertyKey=o4-8oy)/[Wayfarer](http://niem5.org/wayfarer/nc/EntityPerson.html))


## Inherited Properties

Find out some information about commercial vehicles by finding the properties that answer these questions:

1. How could you indicate a vehicle is a commercial vehicle? Can you find a second way?
2. How could you describe the brand name of a commercial vehicle as text rather than a code?
3. How could you indicate the primary color of a commercial vehicle? Can you find a second way? A third? A fourth?

## Associations

1. How might you associate a person with their aunt or uncle? (Hint: "Facet" is the term the SSGT uses for code table codes. Play with the search options there to find this. Wayfarer won't be a help with this.)
2. Write up a little XML or JSON, or even YAML, showing this object.

## Roles

1. How many kinds of roles can an "item" play? What are they? (Hint: "Kinds of roles" refers to types.)
2. How many different elements can represent these kinds of roles? What are they? (Hint: Wayfarer is the best tool for this.)

## Code Tables

1. Going back to the primary color of a commercial vehicle, is there any difference between the different code tables, `cbrn:ConveyanceColorPrimaryCode` and `j:ConveyanceColorPrimaryCode`?
2. Why might there be all these different code tables for this? (You won't be expected to actually know this, but it's good to ponder it.)
3. Find all the values for a person's eye color.
4. What if you wanted to describe the eye color as "The color of my favorite pair of faded blue jeans"?
5. What do you think happens if a code table has no enumerations defined? What will validate and what won't?

## Metadata

1. What does the Human Services domain count as metadata?
2. What about the Screening domain?
3. Think up an example of metadata about this class.

## Combining Domains - Augmentations

1. Can you mix and match NIEM elements into your own Augmentation?

## Creating New Objects - Simple Data

1. Write up XML Schema (sorry JSON folks) to create a pair of elements to rate this class on a scale of 1-5 and provide a comment.
2. Write up the XML or JSON that matches.

## Creating New Objects - Complex Objects

1. Write up XML Schema to create an evaluation object, holding the pair of elements from the prior exercise.
2. Write up the XML or JSON that matches.