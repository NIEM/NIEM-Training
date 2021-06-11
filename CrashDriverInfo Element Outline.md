## exch:CrashDriverInfo
 
### nc:Person

- nc:PersonBirthDate
	- nc:Date
- nc:PersonName
	- nc:PersonGivenName
	- nc:PersonMiddleName
	- nc:PersonMiddleName
	- nc:PersonSurName
- exch:PersonFictionalCharacterIndicator

### j:Crash

- nc:ActivityDate
	- nc:Date
- nc:IncidentLocation
	- nc:Location2DGeospatialCoordinate
		- nc:GeographicCoordinateLatitude
			- nc:LatitudeDegreeValue
			- nc:LatitudeMinuteValue
		- nc:GeographicCoordinateLongitude
			- nc:LongitudeDegreeValue
			- nc:LongitudeMinuteValue
- j:CrashVehicle
	- j:CrashDriver
		- nc:RoleOfPerson
		- j:DriverLicense
			- j:DriverLicenseCardIdentification
				- nc:IdentificationID
			- exch:LicenseAugmentation
				- nc:ItemLengthMeasure
					- nc:MeasureDecimalValue
					- nc:LengthUnitCode
- j:CrashPerson
	- nc:RoleOfPerson
	- j:CrashPersonInjury
		- nc:InjuryDescriptionText
		- j:InjurySeverityCode

### j:PersonChargeAssociation

- nc:Person
- j:Charge
- j:JuvenileAsAdultIndicator

### j:Charge

- j:ChargeDescriptionText
- j:ChargeFelonyIndicator

### j:JusticeMetadata

- j:CriminalInformationIndicator





