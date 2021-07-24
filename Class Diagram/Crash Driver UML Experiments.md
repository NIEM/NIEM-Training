Command line is `mmdc`, from [mermaid-js](https://github.com/mermaid-js)/[mermaid-cli](https://github.com/mermaid-js/mermaid-cli)

```
mmdc --input CrashDriverClassDiagram.mmd --output CrashDriverClassDiagram.svg --theme neutral
mmdc --input CrashDriverClassDiagram-NIEM.mmd --output CrashDriverClassDiagram-NIEM.svg --theme neutral
```

Try this for png?

```
/Applications/Inkscape.app/Contents/Resources/bin/inkscape -z -e test.png -w 1024 -h 1024 test.svg
```

___

## Sample

From [Mermaid Class diagrams](https://mermaid-js.github.io/mermaid/#/classDiagram):

```mermaid
classDiagram

      Animal <|-- Duck
      Animal <|-- Fish
      Animal <|-- Zebra
      Animal : +int age
      Animal : +String gender
      Animal: +isMammal()
      Animal: +mate()
      class Duck{
          +String beakColor
          +swim()
          +quack()
      }
      class Fish{
          -int sizeInFeet
          -canEat()
      }
      class Zebra{
          +bool is_wild
          +run()
      }

```
___
## Non-NIEM

```mermaid
classDiagram

	Person <|-- CrashDriver
	Person <|-- InjuredPerson
	
	class Person{
		+Date BirthDate
		+String FirstName
		+String MiddleName
		+String LastName
	}
	
	class CrashDriver{
		+String DriverLicenseNumber
	
	}

	class InjuredPerson{
		+String InjuryDescription
		+Code SeverityCode
	}

	class Charge{
		+String Description
		+boolean isFelony
	}

	class Crash{
		+Date CrashDate
		+String CrashLocationCoordinates
	}

	CrashVehicle <-- CrashDriver

	class CrashVehicle{
	}
	

```
___
## NIEM
```mermaid
classDiagram

	Person <-- PersonName
	Person <-- BirthDate

	class Person{
	}

	class PersonName{
		+String PersonGivenName
		+String PersonMiddleName
		+String PersonLastName
	}


	class BirthDate{
		+Date Date
	}

	Activity <|-- Incident
	Incident <|-- Crash
	Activity <-- ActivityDate
	Incident <-- Location
	class Crash{
	}

	class Incident{
	}
	
	class Activity{
	}

	class ActivityDate{
		+Date Date
	}


	Location <-- Location2DGeospatialCoordinate
	Location2DGeospatialCoordinate <-- GeographicCoordinateLatitude
	Location2DGeospatialCoordinate <-- GeographicCoordinateLongitude
	
	class Location{
		
	}

	class Location2DGeospatialCoordinate{
	}

	class GeographicCoordinateLatitude{
		+Number LatitudeDegreeValue
		+Number LatitudeMinuteValue
	}

	class GeographicCoordinateLongitude{
		LongitudeDegreeValue
		LongitudeMinuteValue
	}

```