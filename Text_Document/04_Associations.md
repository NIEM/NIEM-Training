```
	nc:Person
		nc:PersonBirthDate
			nc:Date
		nc:PersonName
			nc:PersonGivenName
			nc:PersonMiddleName
			nc:PersonSurName
	j:Crash
		nc:ActivityDate
			nc:Date
+	j:PersonChargeAssociation
+		nc:Person
+		j:Charge
+	j:Charge
+		j:ChargeDescriptionText
+		j:ChargeFelonyIndicator
```
