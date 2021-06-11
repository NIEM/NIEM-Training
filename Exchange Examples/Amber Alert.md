Sample [Amber Alert message from Nlets](https://wiki.nlets.org/index.php/Section_34:_Amber_Alert#Amber_Alert_NIEM_Examples).


```xml
<n2:NLETS xmlns:nh2="http://www.nlets.org/niem/nlets-hdr/1.0" n2:version="4.00" xmlns:nc="http://niem.gov/niem/niem-core/2.0" xmlns:n2="http://www.nlets.org/niem/1.0">
	<n2:NLETSMessageHeader>
		<nh2:MessageKeyCodeText>AA</nh2:MessageKeyCodeText>
		<nh2:OriginatingORIID>AZNLETS20</nh2:OriginatingORIID>
		<nh2:DestinationORIID>AZ</nh2:DestinationORIID>
		<nh2:DocumentControlFieldText>
			<![CDATA[TSTMESSAGE]]>
		</nh2:DocumentControlFieldText>
		<nh2:MessageReceiveDate>11/27/2019</nh2:MessageReceiveDate>
		<nh2:MessageReceiveTime>05:36</nh2:MessageReceiveTime>
		<nh2:MessageSendDate>11/27/2019</nh2:MessageSendDate>
		<nh2:MessageSendTime>05:36</nh2:MessageSendTime>
		<nh2:ReceiveMessageNumeric>00000</nh2:ReceiveMessageNumeric>
		<nh2:SendMessageNumeric>00006</nh2:SendMessageNumeric>
	</n2:NLETSMessageHeader>
	<n2:NLETSMailData n2:key="AA">
		<n2-aa:AmberAlert xmlns:n2-aa="http://www.nlets.org/niem/nlets-amber-alert/1.0">
			<n2-aa:AmberAlertID>12345</n2-aa:AmberAlertID>
			<n2-aa:AmberAlertDateTime>
				<nc:DateTime xmlns:nc="http://release.niem.gov/niem/niem-core/3.0/">2015-01-01T00:00:00Z</nc:DateTime>
			</n2-aa:AmberAlertDateTime>
			<n2-aa:AmberAlertStatusText>Activate</n2-aa:AmberAlertStatusText>
			<nc:ContactInformation xmlns:nc="http://release.niem.gov/niem/niem-core/3.0/">
				<nc:ContactEmailID>amber@ncmec.org</nc:ContactEmailID>
				<nc:ContactTelephoneNumber>
					<nc:FullTelephoneNumber>
						<nc:TelephoneNumberFullID>1231231234</nc:TelephoneNumberFullID>
					</nc:FullTelephoneNumber>
				</nc:ContactTelephoneNumber>
				<nc:ContactWebsiteURI>www.ncmec.org</nc:ContactWebsiteURI>
				<nc:ContactEntity>
					<nc:EntityOrganization>
						<nc:OrganizationName>Organization Name</nc:OrganizationName>
					</nc:EntityOrganization>
				</nc:ContactEntity>
			</nc:ContactInformation>
			<n2-aa:AmberAlertDisseminationTarget>
				<nc:LocationPostalCode xmlns:nc="http://release.niem.gov/niem/niem-core/3.0/">85085</nc:LocationPostalCode>
			</n2-aa:AmberAlertDisseminationTarget>
			<n2-aa:AmberAlertShortMessage>
				<nc:MessageText xmlns:nc="http://release.niem.gov/niem/niem-core/3.0/">Juvenile last seen in green Honda Civic Plate ABC123</nc:MessageText>
				<n2-aa:MessageIntendedDevice>Telephone text message</n2-aa:MessageIntendedDevice>
			</n2-aa:AmberAlertShortMessage>
			<nc:Vehicle xmlns:nc="http://release.niem.gov/niem/niem-core/3.0/">
				<nc:ConveyanceColorPrimaryText>Blue</nc:ConveyanceColorPrimaryText>
				<nc:ConveyanceColorSecondaryText>Black</nc:ConveyanceColorSecondaryText>
				<nc:ItemMakeName>Honda</nc:ItemMakeName>
				<nc:ItemModelName>Civic</nc:ItemModelName>
				<nc:ItemModelYearDate>2010</nc:ItemModelYearDate>
				<n2-aa:ConveyanceAugmentation>
					<j:ConveyanceRegistration xmlns:j="http://release.niem.gov/niem/domains/jxdm/5.0/">
						<j:ConveyanceRegistrationPlateIdentification>
							<nc:IdentificationID>ABC123</nc:IdentificationID>
							<nc:IdentificationJurisdiction>
								<nc:LocationStateName>AZ</nc:LocationStateName>
							</nc:IdentificationJurisdiction>
						</j:ConveyanceRegistrationPlateIdentification>
					</j:ConveyanceRegistration>
				</n2-aa:ConveyanceAugmentation>
			</nc:Vehicle>
			<j:MissingPerson xmlns:j="http://release.niem.gov/niem/domains/jxdm/5.0/">
				<nc:RoleOfPerson xmlns:nc="http://release.niem.gov/niem/niem-core/3.0/">
					<nc:PersonAgeDescriptionText>7 years old</nc:PersonAgeDescriptionText>
					<nc:PersonBirthDate>
						<nc:Date>2008-01-01</nc:Date>
					</nc:PersonBirthDate>
					<nc:PersonCitizenshipText>United States</nc:PersonCitizenshipText>
					<nc:PersonDescriptionText>7 year old boy, brown hair and glasses carrying blue backpack</nc:PersonDescriptionText>
					<nc:PersonEthnicityText>Not Hispanic</nc:PersonEthnicityText>
					<nc:PersonEyeColorText>Brown</nc:PersonEyeColorText>
					<nc:PersonHairColorText>Brown</nc:PersonHairColorText>
					<nc:PersonHeightMeasure>
						<nc:MeasureValueText>400</nc:MeasureValueText>
					</nc:PersonHeightMeasure>
					<nc:PersonName>
						<nc:PersonFullName>DOE,JOHN</nc:PersonFullName>
					</nc:PersonName>
					<nc:PersonRaceText>White</nc:PersonRaceText>
					<nc:PersonSexText>Male</nc:PersonSexText>
					<n2-aa:PersonAugmentation>
						<n2-aa:PersonJewelry>
							<nc:ItemDescriptionText>black bracelet</nc:ItemDescriptionText>
						</n2-aa:PersonJewelry>
						<n2-aa:NCICEntry>
							<n2-aa:NCICEntryMadeIndicator>true</n2-aa:NCICEntryMadeIndicator>
							<n2-aa:NCICMessageKeyUsedText>EM-J</n2-aa:NCICMessageKeyUsedText>
							<j:PersonNCICIdentification>
								<nc:IdentificationID>M123456789</nc:IdentificationID>
							</j:PersonNCICIdentification>
						</n2-aa:NCICEntry>
					</n2-aa:PersonAugmentation>
					<j:PersonAugmentation>
						<j:PersonClothing>
							<j:ClothingDescriptionText>white shirt, blue backpack</j:ClothingDescriptionText>
						</j:PersonClothing>
					</j:PersonAugmentation>
				</nc:RoleOfPerson>
				<j:MissingPersonCircumstanceText>Last seen leaving park with subject</j:MissingPersonCircumstanceText>
				<j:MissingPersonLastSeenDate>
					<nc:DateTime xmlns:nc="http://release.niem.gov/niem/niem-core/3.0/">2015-01-01T00:00:00Z</nc:DateTime>
				</j:MissingPersonLastSeenDate>
				<j:MissingPersonLastSeenLocation>
					<nc:Address xmlns:nc="http://release.niem.gov/niem/niem-core/3.0/">
						<nc:AddressFullText>1918 W. Whispering Wind Dr.</nc:AddressFullText>
					</nc:Address>
				</j:MissingPersonLastSeenLocation>
			</j:MissingPerson>
			<j:Subject xmlns:j="http://release.niem.gov/niem/domains/jxdm/5.0/">
				<nc:RoleOfPerson xmlns:nc="http://release.niem.gov/niem/niem-core/3.0/">
					<nc:PersonAgeDescriptionText>Late 40s</nc:PersonAgeDescriptionText>
					<nc:PersonBirthDate>
						<nc:Date>2008-01-01</nc:Date>
					</nc:PersonBirthDate>
					<nc:PersonDescriptionText>Male late 40's wearing dark sweatshirt</nc:PersonDescriptionText>
					<nc:PersonEthnicityText>Not Hispanic</nc:PersonEthnicityText>
					<nc:PersonEyeColorText>Brown</nc:PersonEyeColorText>
					<nc:PersonHairColorText>Brown</nc:PersonHairColorText>
					<nc:PersonName>
						<nc:PersonFullName>Smith,Joe</nc:PersonFullName>
					</nc:PersonName>
					<nc:PersonRaceText>White</nc:PersonRaceText>
					<nc:PersonSexText>Male</nc:PersonSexText>
					<j:PersonAugmentation>
						<j:PersonClothing>
							<j:ClothingDescriptionText>dark sweatshirt and jeans</j:ClothingDescriptionText>
						</j:PersonClothing>
						<j:PersonCautionInformationText>armed and dangerous</j:PersonCautionInformationText>
					</j:PersonAugmentation>
				</nc:RoleOfPerson>
			</j:Subject>
		</n2-aa:AmberAlert>
	</n2:NLETSMailData>
</n2:NLETS>
```