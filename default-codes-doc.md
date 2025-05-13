## Feature Created Default Codes
These default codes are calculated and set only when a feature is created.
| Code | Description | Example | Tags |
|------|------------|---------|------|
| !TS | Current timestamp | !TS | date, time |
| !LAT | Latitude of the user position in degrees | !LAT | coordinates, latitude |
| !LNG | Latitude of the user position in degrees | !LNG | coordinates, longitude |
| !ALT | Altitude of the user position in meters | !ALT | coordinates, altitude |
| !X | X coordinate of the user position in the coordinate system defined by the project the feature belongs to | !X | coordinates, easting |
| !Y | Y coordinate of the user position in the coordinate system defined by the project the feature belongs to | !Y | coordinates, northing |
| !Z | Z coordinate of the user position in the coordinate system defined by the project the feature belongs to | !Z | coordinates, elevation |
| !ACC | Accuracy of the user position in meters | !ACC | coordinates, accuracy |
| !SATS | Number of satellites used for the user position | !SATS | coordinates, satellites |
| !HDOP | Horizontal dilution of precision of the user position | !HDOP | coordinates, hdop |
| !USER | User name of the user creating the feature | !USER | user, name |
| !QA | Quality assurance status of the user position, it's the position accuracy followed by the unit. E.g 1.3m | !QA | coordinates, qa |
## Geometry Based Default Codes
These default codes are calculated and set when the geometry of a feature is changed.
| Code | Description | Example | Tags |
|------|------------|---------|------|
| !LEN | Length of the geometry in meters | !LEN | geometry, length |
| !AREA | 2D area of the geometry in square meters | !AREA | geometry, area |
| !FEATUREX | X coordinate of the geometry in the coordinate system defined by the project the feature belongs to. Only available for point geometries. | !FEATUREX | geometry, coordinates, point, easting |
| !FEATUREY | Y coordinate of the geometry in the coordinate system defined by the project the feature belongs to. Only available for point geometries. | !FEATUREY | geometry, coordinates, point, northing |
| !FEATUREZ | Z coordinate of the geometry in the coordinate system defined by the project the feature belongs to. Only available for point geometries. | !FEATUREZ | geometry, coordinates, point, elevation |
| !FEATUREALT | Altitude of the feature geometry. Only available for point geometries. | !FEATUREALT | geometry, coordinates, point, altitude |
## Calculation Based Default Codes
These default codes are for calculation based fields, They run when they are autonavigated over and when the form is opened.
| Code | Description | Example | Tags |
|------|------------|---------|------|
| !CALC | Perform a calculation using the given expression. The expression can include mathematical operations and field names. | !CALC 2 + 2, !CALC field1 * field2, !CALC field1 + 5 | calculation, math, expression |
