From [[Crash Driver]]

```xml
        <nc:Location>
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
        </nc:Location>
```


- [j:Crash](http://niem5.org/wayfarer/j/Crash.html)
	- [nc:Location](http://niem5.org/wayfarer/nc/Location.html)
		- \[[nc:LocationGeospatialCoordinateAbstract](http://niem5.org/wayfarer/nc/LocationGeospatialCoordinateAbstract.html)\]
			- [nc:Location2DGeospatialCoordinate](http://niem5.org/wayfarer/nc/Location2DGeospatialCoordinate.html)
			- [geo](https://tools.niem.gov/niemtools/ssgt/SSGT-GetNamespace.iepd?namespaceKey=o3-4c):[LocationGeospatialPoint](https://tools.niem.gov/niemtools/ssgt/SSGT-GetProperty.iepd?propertyKey=o3-m73) (This is the adapter.)
				- [gml](https://tools.niem.gov/niemtools/ssgt/SSGT-GetNamespace.iepd?namespaceKey=o3-8m):[Point](https://tools.niem.gov/niemtools/ssgt/SSGT-GetProperty.iepd?propertyKey=o3-fux) (This is the external element.): "A gml:Point is defined by a single coordinate tuple. The direct position of a point is specified by the gml:pos element which is of type gml:DirectPositionType."



http://www.datypic.com/sc/niem21/e-gml32_Point.html

Point examples:

Statue of Liberty

```xml
<gml:Point gml:id="point1">  
	<gml:pos srsName="urn:ogc:def:crs:EPSG::4326" srsDimension="2">40.689167 -74.044444</gml:pos>  
</gml:Point>
```
