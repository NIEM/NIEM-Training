## Create PersonDefenestrationIndicator

Uses existing NIEM type of `niem-xs:boolean`.

Uses `j:CrashPersonAugmentationPoint` as a substitution group head.

```xml
<xs:element name="PersonDefenestrationIndicator" type="niem-xs:boolean"
	substitutionGroup="j:CrashPersonAugmentationPoint">
	<xs:annotation>
		<xs:documentation>True if this person was thrown through a window; false otherwise.
		</xs:documentation>
	</xs:annotation>
</xs:element>
```

## Resulting Instance

```xml
<j:CrashPerson>
	<nc:RoleOfPerson structures:ref="P01" xsi:nil="true"/>
	<j:CrashPersonInjury structures:metadata="PMD01 PMD02">
		<nc:InjuryDescriptionText>Broken Arm</nc:InjuryDescriptionText>
		<j:InjurySeverityCode>3</j:InjurySeverityCode>
	</j:CrashPersonInjury>
	<ext:PersonDefenestrationIndicator>false</ext:PersonDefenestrationIndicator>
</j:CrashPerson>
```

___

## Create a Privacy Code

```xml
<xs:element name="PrivacyCode" type="ext:PrivacyCodeType"/>
<xs:complexType name="PrivacyCodeType">
	<xs:simpleContent>
		<xs:extension base="ext:PrivacyCodeSimpleType">
			<xs:attributeGroup ref="structures:SimpleObjectAttributeGroup"/>
		</xs:extension>
	</xs:simpleContent>
</xs:complexType>

<xs:simpleType name="PrivacyCodeSimpleType">
	<xs:restriction base="xs:token">
		<xs:enumeration value="PII"/>
		<xs:enumeration value="MEDICAL"/>
	</xs:restriction>
</xs:simpleType>
```

## Create a Metadata Object to Hold It

```xml
<xs:element name="PrivacyMetadata" type="ext:PrivacyMetadataType"/>
<xs:complexType name="PrivacyMetadataType">
	<xs:complexContent>
		<xs:extension base="structures:MetadataType">
			<xs:sequence>
				<xs:element ref="ext:PrivacyCode" minOccurs="0" maxOccurs="unbounded"/>
			</xs:sequence>
		</xs:extension>
	</xs:complexContent>
</xs:complexType>
```




## Resulting Instance

```xml
<ext:PrivacyMetadata structures:id="PMD01">
	<ext:PrivacyCode>PII</ext:PrivacyCode>
</ext:PrivacyMetadata>
```


