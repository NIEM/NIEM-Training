```
exch:CrashDriverInfo
    nc:Person structures:id
        nc:PersonBirthDate structures:metadata
            nc:Date
        nc:PersonName nc:personNameCommentText
            nc:PersonGivenName structures:sequenceID
            nc:PersonMiddleName structures:sequenceID
            nc:PersonMiddleName structures:sequenceID
            nc:PersonSurName
        exch:PersonFictionalCharacterIndicator
    j:Crash
        nc:ActivityDate
            nc:Date
        j:CrashVehicle
            j:CrashDriver
                nc:RoleOfPerson structures:ref
                j:DriverLicense
                    j:DriverLicenseCardIdentification
                        nc:IdentificationID
        j:CrashPerson
            nc:RoleOfPerson structures:ref
            j:CrashPersonInjury structures:metadata
                nc:InjuryDescriptionText
                j:InjurySeverityCode
        nc:Location
            geo:LocationGeospatialPoint
                gml:Point gml:id
                    gml:pos srsName srsDimension
            nc:Location2DGeospatialCoordinate
                nc:GeographicCoordinateLatitude
                    nc:LatitudeDegreeValue
                    nc:LatitudeMinuteValue
                nc:GeographicCoordinateLongitude
                    nc:LongitudeDegreeValue
                    nc:LongitudeMinuteValue
    j:PersonChargeAssociation structures:metadata
        nc:Person structures:ref
        j:Charge structures:ref
        j:JuvenileAsAdultIndicator
    j:Charge structures:id structures:metadata
        j:ChargeDescriptionText
        j:ChargeFelonyIndicator
    j:Metadata structures:id
        j:CriminalInformationIndicator
    priv:PrivacyMetadata structures:id
        priv:PrivacyCode
    priv:PrivacyMetadata structures:id
        priv:PrivacyCode
```