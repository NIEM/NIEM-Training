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

## Inherited Properties

Q.  How could you indicate a vehicle is a commercial vehicle? Can you find a second way?

A. Use a `nc:CommercialVehicle` element to represent it. Use `nc:VehicleCMVIndicator` and set it to `true`.

Q.  How could you describe the brand name of a commercial vehicle as text rather than a code?

A. `nc:ItemBrandName`

Q.  How could you indicate the primary color of a commercial vehicle? Can you find a second way? A third? A fourth?

- `nc:ItemColorDescriptionText`
- `nc:ConveyanceColorPrimaryText`
- `cbrn:ConveyanceColorPrimaryCode`
- `j:ConveyanceColorPrimaryCode`

## Associations

Q.  How might you associate a person with their aunt or uncle? (Hint: "Facet" is the term the SSGT uses for code table codes. Play with the search options there to find this. Wayfarer won't be a help with this.)

- `hs:PersonOtherKinAssociation`

```xml
<hs:PersonOtherKinAssociation>
	<hs:PersonOtherKinAssociationCategoryCode>Paternal Uncle</hs:PersonOtherKinAssociationCategoryCode>
	<hs:SourcePerson>
		<nc:PersonName>
			<nc:PersonGivenName>Me</nc:PersonGivenName>
		</nc:PersonName>
	</hs:SourcePerson>
	<hs:TargetPerson>
		<nc:PersonName>
			<nc:PersonGivenName>My Uncle</nc:PersonGivenName>
		</nc:PersonName>
	</hs:TargetPerson>
</hs:PersonOtherKinAssociation>
```

## Roles

Q. How many kinds of roles can an "item" play? What are they? (Hint: "Kinds of roles" refers to types.)

A. There are six different types that a `RoleOfItem` can be in:

-   [j:CrashVehicleType](http://niem5.org/wayfarer/j/CrashVehicleType.html)
-   [nc:EquipmentType](http://niem5.org/wayfarer/nc/EquipmentType.html)
-   [j:EvidenceType](http://niem5.org/wayfarer/j/EvidenceType.html)
-   [j:ToolType](http://niem5.org/wayfarer/j/ToolType.html)
-   [j:VictimType](http://niem5.org/wayfarer/j/VictimType.html)
-   [nc:WeaponType](http://niem5.org/wayfarer/nc/WeaponType.html)

Q.  How many different elements can represent these kinds of roles? What are they? (Hint: Wayfarer is the best tool for this.)

A. Wayfarer can show **all** the elements that are of or derived from any of these types.