Q: What happens if `maxOccurs` is less than `minOccurs`?

A: A validating XML editor will throw an error.
___

Q: What do you think happens if `maxOccurs` is set to zero? Why might you want to do that?

A: The element is disallowed. It's handy if you want to temporarily remove an object from an exchange, perhaps during testing, without actually deleting it from the schema. Of course, you could also just comment it out.
___

Q: What are some cases where you might want a `maxOccurs` that is greater than 1, but not unbounded?

A: Fingerprints is a good example. While some folks have more than ten fingers, there _is_ a realistic upper bounds on how many a person can have. Your database might also have upper limits on how often something can occur. Maybe you only support 3 address lines. You might then limit that element in an exchange to a `maxOccurs` of 3.