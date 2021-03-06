# Shp2JSON

Converts ESRI Shapefile to a WGS84 GeoJSON file.

## Requirements

* Fiona (pip install fiona)
* PyPROJ (pip install pyproj)

## How to use

	usage: shp2json.py [-h] [-e] shp geojson

	Convert ESRI Shapefile to GeoJSON

	positional arguments:
  		shp         Shapefile
	    geojson     GeoJSON file

	optional arguments:
  		-h, --help  show this help message and exit
  		-e          Encode geojson geometry using the encoded polyline algorithm.

	shp2json.py Neighbourhoods.shp neighbourhoods.geojson
	
	cat neighbourhoods.geojson
	
	{"type": "FeatureCollection", "features": [{"geometry": {"type": "Polygon", "coordinates": [[[-120.37273534694833, 50.67716016936108], [-120.37080246306458, 50.67707673658443], [-120.36562460360317, 50.675414824845106], [-120.36414637936278, 50.67442668552551], [-120.36305847188238, 50.674425178501714], [-120.36109703243172, 50.67508529888049], [-120.36102327419162, 50.675046092223894], [-120.36087003559417, 50.67495662912456], [-120.36072804677677, 50.67486598173879], [-120.36053191906639, 50.67473363050565], [-120.36038030205606, 50.674622885742316]...
	
Or if you want to apply the Encoded Polyline Algorithm
	
	shp2json.py -e Neighbourhoods.shp neighbourhoods.egeojson
	
	cat neighbourhoods.egeojson
	
	{"type": "FeatureCollection", "features": [{"geometry": {"type": 	"Polygon", "coordinates": ["g{htHphu}UPaKjIk_@dEgH?	yEcCgKFMP]P]Xe@T]V]T[XYVW^]^YVQTM^S^O\\MZKd@Kd@Kb@G@?r@Kl@Kl@Ij@I\	\Gb@GXGd@I^I\\K\\I\\I^M^K^M^O`@OXOXKRKHE~@~FdAhHvAhKf@~E?@???@@@?@?@?@?@?	@@@?@?@?@?@?@@@?@?@???@?@@@?@?@?@?@?@?@@@?@?@?@?@?@@@?@?@???@?@?@@@?@?@?@?@?@?@@@?@?@?@?@?@?@@@?@?@?@???@?@?@@@?@?@?@?@?@?@?@@@?@?@?@?@?@?@?@?@@@?@?@???@?@?@?@?@@@?@?@?@?@?@?@?@?@?@@@?@?@?@?@?@?@?@?@?@@@?@???@?@?@?@?@?@?@?@?@@@?@?@?@?@?@?@?@?@?@?@?@?@@@?@?@?@?@?@?@?@?@?@?@???@?@?@@@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@@@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@???@?@?@?@?@?@?@?@?@?@?@?@?@?@?@@@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@???@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@???@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@???@?@?@?@?@?@A@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@A@?@?@?@?@?@?@?@?@?@???@?@?@?@?@?@?@?@A@?@?@?@?@?@?@?@?@?@?@?@?@?@?@?@A@?@?@?@?@?@?@?@?@?@?@???@?@A@?@?@?@?@?@?@?@?@?@?@?@A@?@?@?@?@?@?@?@?@?@?@?@A@?@?@?@?@???@?@?@?@A@?@?@?@?@?@?@?@?@?@?@A@?@SlCgFpEeA~@mBbBkB`BaBxA{ArAmAfAmAdAmAfAmAdAkC~BmAdA}AtAmAdAmAfAcCiEoCeDgBq@[uB"]}, "type...
	
**NOTE** Point features are not encoded, coordinates are passed through.
