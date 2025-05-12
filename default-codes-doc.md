## Geometry Based Default Codes
These default codes are calculated and set when the geometry of a feature is changed.
| Code | Description | Example | Tags |
|------|------------|---------|------|
| !LEN | Length of the geometry in meters | !LENGTH | geometry, length |
| !AREA | 2D area of the geometry in square meters | !AREA | geometry, area |
| !FEATUREX | X coordinate of the geometry in the coordinate system defined by the project the feature belongs to. Only available for point geometries. | !FEATUREX | geometry, coordinates, point, easting |
| !FEATUREY | Y coordinate of the geometry in the coordinate system defined by the project the feature belongs to. Only available for point geometries. | !FEATUREY | geometry, coordinates, point, northing |
| !FEATUREZ | Z coordinate of the geometry in the coordinate system defined by the project the feature belongs to. Only available for point geometries. | !FEATUREZ | geometry, coordinates, point, elevation |
| !FEATUREALT | Altitude of the feature geometry. Only available for point geometries. | !FEATUREALT | geometry, coordinates, point, altitude |
