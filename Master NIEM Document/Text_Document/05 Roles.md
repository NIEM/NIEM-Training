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
+		j:CrashPerson
+			nc:RoleOfPerson
+			j:CrashPersonInjury
+				nc:InjuryDescriptionText
	j:PersonChargeAssociation
		nc:Person
		j:Charge
		j:JuvenileAsAdultIndicator
	j:Charge
		j:ChargeDescriptionText
		j:ChargeFelonyIndicator
```