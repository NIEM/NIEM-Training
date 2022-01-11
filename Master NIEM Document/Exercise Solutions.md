# Solutions

## Understanding NIEM Objects
Q: What happens if `maxOccurs` is less than `minOccurs`?

A: A validating XML editor will throw an error.
___

Q: What do you think happens if `maxOccurs` is set to zero? Why might you want to do that?

A: The element is disallowed. It's handy if you want to temporarily remove an object from an exchange, perhaps during testing, without actually deleting it from the schema. Of course, you could also just comment it out.
___

Q: What are some cases where you might want a `maxOccurs` that is greater than 1, but not unbounded?

A: Fingerprints is a good example. While some folks have more than ten fingers, there _is_ a realistic upper bounds on how many a person can have. Your database might also have upper limits on how often something can occur. Maybe you only support 3 address lines. You might then limit that element in an exchange to a `maxOccurs` of 3.

## Native Properties

Open-ended exercise.

## Substitution Groups

Q: What are all the different ways that NIEM can represent a date?

A: `nc:DateRepresentation` can be replaced with:

- `nc:Date`: A full date.
- `nc:DateRange`: A time period measured by a starting and ending point.
- `nc:DateTime`: A full date and time.
- `nc:DayDate`: A day date.
- `nc:FiscalYearDate`: A year of a twelve month period that does not necessarily correspond to the calendar year.
- `nc:MonthDate`: A month.
- `nc:QuarterID`: An identifier of a three-month period in a calendar or fiscal year.
- `nc:YearDate`: A year.
- `nc:YearMonthDate`: A year and month.
- `nc:ZuluDateTime`: A date and time with no offset from Coordinated Universal Time (UTC).

___

Q: Take a look at the following elements and how they fit together via substitution groups. What do you think the reason for all this might be?

- `nc:Entity`
- `nc:EntityRepresentation`
- `nc:EntityOrganization`
- `nc:EntityPerson`

A: Some sorts of things can be either a person or an organization. Think `j:CaseDefendantParty` ([SSGT](https://tools.niem.gov/niemtools/ssgt/SSGT-GetProperty.iepd?propertyKey=o4-9j)/[Wayfarer](http://niem5.org/wayfarer/j/CaseDefendantParty.html))
