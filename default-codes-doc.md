## Radio Group Option with Default Codes
Radio group attributes can have default codes added as an option (you can also add default codes as a nested option).
The default codes are processed when the attribute is opened and the processed value is added to the list of values the user can select.
Not all default codes are supported in radio group options. The supported codes are:
* Feature Created Default Codes
* Calculation Based Default Codes
    
## Feature Created Default Codes
These default codes are calculated and set only when a feature is created.
| Code | Description | Example | Tags |
|------|------------|---------|------|
| !TS | Current timestamp, with date and time in the format dd-MMM-yyyy HH:mm:ss (e.g. 01-Jan-2025 14:30:00) | !TS | date, time |
| !D | Current date, in the format dd-MMM-yyyy (e.g. 01-Jan-2025) | !D | date |
| !TIME | Current time, in the format HH:mm:ss (e.g. 14:30:00) | !TIME | time |
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
| !AUTOINC | Increment the attribute value by the specified amount (or by 1 as a default). The attribute must be a number. | !AUTOINC, !AUTOINC(5) | attributes, increment, number |
| !READGLOBALCACHE | Read a value from the global cache, the cache item is scoped to the user. | !READGLOBALCACHE(key) | cache, global, read |
| !WRITEGLOBALCACHE | Writes the attributes current value to the global cache, the cache item is scoped to the user. | !WRITEGLOBALCACHE(key, value) | cache, global, write |
| !READPROJECTCACHE | Read a value from the project scoped cache, the cache item is scoped to the user and project. | !READPROJECTCACHE(key) | cache, project, read |
| !WRITEPROJECTCACHE | Writes the attributes current value to the project scoped cache, the cache item is scoped to the user and project. | !WRITEPROJECTCACHE(key) | cache, project, write |
| !READLOCATIONCACHE | Read a value from the location scoped cache, the cache item is scoped to the user and location. | !READLOCATIONCACHE(key) | cache, location, read |
| !WRITELOCATIONCACHE | Writes the attributes current value to the location scoped cache, the cache item is scoped to the user and location. | !WRITELOCATIONCACHE(key) | cache, location, write |
| !PARENTID | The ID of the parent feature, if the feature is a child feature | !PARENTID | feature, parent, id, child, child form |
## Feature Saved Default Codes
These default codes are calculated and set only when a feature is saved.
| Code | Description | Example | Tags |
|------|------------|---------|------|
| !ONSAVEWRITEGLOBALCACHE | Writes the attributes current value to the global cache, the cache item is scoped to the user. | !WRITEGLOBALCACHE(key, value) | cache, global, write |
| !ONSAVEWRITEPROJECTCACHE | Writes the attributes current value to the project scoped cache, the cache item is scoped to the user and project. | !WRITEPROJECTCACHE(key) | cache, project, write |
| !ONSAVEWRITELOCATIONCACHE | Writes the attributes current value to the location scoped cache, the cache item is scoped to the user and location. | !WRITELOCATIONCACHE(key) | cache, location, write |
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
| !CALC | Perform a calculation using the given expression. The expression can include mathematical operations and field names. You can make the calculation react to attribute updates by prefixing the attribute name with $ | !CALC 2 + 2, !CALC field1 * field2, !CALC field1 + 5, !CALC $field1 + $field2 | calculation, math, expression |
| !CALCW3WNOW | Get the users current position's What3Words address. This calc code does not run when the feature type is opened - only when the attribute is selected/autoselected. | !CALCW3WNOW | calculation, w3w, what3words, location |
