Sample from [[Dr. Scott]] Crash Driver IEPD

```xml
<?xml version="1.0" encoding="UTF-8"?>
<exch:CrashDriverInfo 
    xmlns:exch="http://example.com/CrashDriver/1.0/"
    xmlns:j="http://release.niem.gov/niem/domains/jxdm/6.0/"
    xmlns:nc="http://release.niem.gov/niem/niem-core/4.0/"
    xmlns:priv="http://example.com/PrivacyMetadata/1.0/"
    xmlns:structures="http://release.niem.gov/niem/structures/4.0/"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <nc:Person structures:id="P01">
        <nc:PersonBirthDate structures:metadata="PMD01">
            <nc:Date>1890-05-04</nc:Date>
        </nc:PersonBirthDate>
        <nc:PersonName nc:personNameCommentText="copied">
            <nc:PersonGivenName nc:sequenceID="1">Peter</nc:PersonGivenName>
            <nc:PersonMiddleName nc:sequenceID="2">Death</nc:PersonMiddleName>
            <nc:PersonMiddleName nc:sequenceID="3">Bredon</nc:PersonMiddleName>
            <nc:PersonSurName>Wimsey</nc:PersonSurName>
        </nc:PersonName>
        <exch:PersonFictionalCharacterIndicator>true</exch:PersonFictionalCharacterIndicator>
    </nc:Person>
    <j:Crash>
        <nc:ActivityDate>
            <nc:Date>1900-05-04</nc:Date>
        </nc:ActivityDate>
        <nc:IncidentLocation>
            <nc:Location2DGeospatialCoordinate>
                <nc:GeographicCoordinateLatitude>
                    <nc:LatitudeDegreeValue>51</nc:LatitudeDegreeValue>
                    <nc:LatitudeMinuteValue>52</nc:LatitudeMinuteValue>
                </nc:GeographicCoordinateLatitude>
                <nc:GeographicCoordinateLongitude>
                    <nc:LongitudeDegreeValue>-1</nc:LongitudeDegreeValue>
                    <nc:LongitudeMinuteValue>17</nc:LongitudeMinuteValue>
                </nc:GeographicCoordinateLongitude>
            </nc:Location2DGeospatialCoordinate>
        </nc:IncidentLocation>
        <j:CrashVehicle>
            <j:CrashDriver>
                <nc:RoleOfPerson structures:ref="P01" xsi:nil="true"/>
                <j:DriverLicense>
                    <j:DriverLicenseCardIdentification>
                        <nc:IdentificationID>A1234567</nc:IdentificationID>
                    </j:DriverLicenseCardIdentification>
                    <exch:LicenseAugmentation>
                        <nc:ItemLengthMeasure>
                            <nc:MeasureDecimalValue>9.7</nc:MeasureDecimalValue>
                            <nc:LengthUnitCode>CMT</nc:LengthUnitCode>
                        </nc:ItemLengthMeasure>
                    </exch:LicenseAugmentation>
                </j:DriverLicense>
            </j:CrashDriver>
        </j:CrashVehicle>
        <j:CrashPerson>
            <nc:RoleOfPerson structures:ref="P01" xsi:nil="true"/>
            <j:CrashPersonInjury structures:metadata="PMD01 PMD02">
                <nc:InjuryDescriptionText>Broken Arm</nc:InjuryDescriptionText>
                <j:InjurySeverityCode>3</j:InjurySeverityCode>
            </j:CrashPersonInjury>
        </j:CrashPerson>
    </j:Crash>
    <j:PersonChargeAssociation structures:metadata="JMD01">
        <nc:Person structures:ref="P01" xsi:nil="true"/>
        <j:Charge structures:ref="CH01" xsi:nil="true"/>
        <j:JuvenileAsAdultIndicator>true</j:JuvenileAsAdultIndicator>
    </j:PersonChargeAssociation>
    <j:Charge structures:id="CH01" structures:metadata="JMD01">
        <j:ChargeDescriptionText>Furious Driving</j:ChargeDescriptionText>
        <j:ChargeFelonyIndicator>false</j:ChargeFelonyIndicator>
    </j:Charge>
    <j:JusticeMetadata structures:id="JMD01">
        <j:CriminalInformationIndicator>true</j:CriminalInformationIndicator>
    </j:JusticeMetadata>
    <priv:PrivacyMetadata structures:id="PMD01">
        <priv:PrivacyCode>PII</priv:PrivacyCode>
    </priv:PrivacyMetadata>
    <priv:PrivacyMetadata structures:id="PMD02">
        <priv:PrivacyCode>MEDICAL</priv:PrivacyCode>
    </priv:PrivacyMetadata>
</exch:CrashDriverInfo>

```

