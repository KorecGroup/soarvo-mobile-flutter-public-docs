## Radio Group Option with Default Codes
Radio group attributes can have default codes added as an option (you can also add default codes as a nested option).
The default codes are processed when the attribute is opened and the processed value is added to the list of values the user can select.
Not all default codes are supported in radio group options. The supported codes are:
* Feature Created Default Codes
* Calculation Based Default Codes
    
## Radio Group and Checkbox Group Default Codes
For radio group and checkbox group attributes, you set the default code of the attribute by prefixing the first value in its
list of options with 'DEFAULTCODE-', for example if the first option is DEFAULTCODE-!MODIFIER-SHOWWHEN $CATCompetency == 'No' 
then the default code for that attribute would set to !MODIFIER-SHOWWHEN $CATCompetency == 'No'.
    
## Feature Type Metadata Settings
Feature Types can include **metadata settings attributes** which act like *settings* for that Feature Type and control specific pieces of functionality.
These are typically attributes whose names are prefixed with an underscore (e.g. `_ON_SAVE_ACTIONS`).

This list is **not comprehensive**. The SOARVO knowledgebase contains dedicated pages for some functionality (for example, auto-recording linear/area nodes)
which document the required metadata settings attributes for those workflows. The table below is only for metadata settings that don't require their own dedicated page.
    
## Feature Type Metadata Settings
Feature Types can include **metadata settings attributes** which act like *settings* for that Feature Type and control specific pieces of functionality.
These are typically attributes whose names are prefixed with an underscore (e.g. `_ON_SAVE_ACTIONS`).

This list is **not comprehensive**. The SOARVO knowledgebase contains dedicated pages for some functionality (for example, auto-recording linear/area nodes)
which document the required metadata settings attributes for those workflows. The table below is only for metadata settings that don't require their own dedicated page.
    

| Value | Description | Example value |
|------|------|------|
| `_AUTO_ACCEPT` | If present in the feature type (there is no actual value needed, the attribute just needs to be in the feature type), the app will automatically save the newly recorded feature after the attributes are filled via default codes and all the attributes have a value. This is only available for point features. Useful for rapid capture workflows. | `` |
| `_ON_SAVE_ACTIONS` | Comma-separated actions to run after a feature is saved (e.g. play a success sound and/or vibrate). Often stored as a hidden ShortText attribute. | `!MODIFIER-HIDE;successJingle,vibrate` |

## Feature Created Default Codes
These default codes are calculated and set only when a feature is created.

| Code | Description | Example | Tags |
|------|------|------|------|
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
| !RESTORE | Writes the attributes current value to the location scoped cache, the cache item is scoped to the user and location. Is a shorthand for !READLOCATIONCACHE where the key is the attribute id. | !RESTORE | restore, location, read |
| !WRITELOCATIONCACHE | Writes the attributes current value to the location scoped cache, the cache item is scoped to the user and location. | !WRITELOCATIONCACHE(key) | cache, location, write |
| !PARENTID | The ID of the parent feature, if the feature is a child feature | !PARENTID | feature, parent, id, child, child form |
| !FROMCSV | Processes the current attributes value as a CSV and parses out values. The indexes for the value are 1 based. | !FROMCSV(1) !FROMCSV(1,3,4) | CSV |
| !RD8K | Process a recorded RD8K measurement. !RD8K will load the full measurement NMEA string. !RD8K(n) will extract the nth value from the measurements NMEA string. On saving the feature, the RD8K measurement will be removed from the cache. | !RD8K, !RD8K(3) | RD8K, NMEA |
| !LOCATIONNAME | Name of the current location the feature is being created in | !LOCATIONNAME | location, name, location name |
| !PROJECTNAME | Name of the current project the feature is being created in | !PROJECTNAME | project, name, project name |

## Feature Saved Default Codes
These default codes are calculated and set only when a feature is saved.

| Code | Description | Example | Tags |
|------|------|------|------|
| !ONSAVEWRITEGLOBALCACHE | Writes the attributes current value to the global cache, the cache item is scoped to the user. | !ONSAVEWRITEGLOBALCACHE(key, value) | cache, global, write |
| !ONSAVEWRITEPROJECTCACHE | Writes the attributes current value to the project scoped cache, the cache item is scoped to the user and project. | !ONSAVEWRITEPROJECTCACHE(key) | cache, project, write |
| !ONSAVEWRITELOCATIONCACHE | Writes the attributes current value to the location scoped cache, the cache item is scoped to the user and location. | !ONSAVEWRITELOCATIONCACHE(key) | cache, location, write |
| !STORE | Writes the attributes current value to the location scoped cache, the cache item is scoped to the user and location. Shorthand for !ONSAVEWRITELOCATIONCACHE, where the key is the attribute id. | !STORE | cache, store |
| !RD8K | Process a recorded RD8K measurement. !RD8K will load the full measurement NMEA string. !RD8K(n) will extract the nth value from the measurements NMEA string. On saving the feature, the RD8K measurement will be removed from the cache. | !RD8K, !RD8K(3) | RD8K, NMEA |

## Feature Opened Default Codes
These default codes are calculated and set when a feature is opened (so created/edited).

| Code | Description | Example | Tags |
|------|------|------|------|
| !ONOPENTS | Current timestamp, with date and time in the format dd-MMM-yyyy HH:mm:ss (e.g. 01-Jan-2025 14:30:00) | !TS | date, time |
| !ONOPEND | Current date, in the format dd-MMM-yyyy (e.g. 01-Jan-2025) | !D | date |
| !ONOPENTIME | Current time, in the format HH:mm:ss (e.g. 14:30:00) | !TIME | time |
| !ONOPENWRITEGLOBALCACHE | Writes the attributes current value to the global cache, the cache item is scoped to the user. | !ONOPENWRITEGLOBALCACHE(key, value) | cache, global, write |
| !ONOPENWRITEPROJECTCACHE | Writes the attributes current value to the project scoped cache, the cache item is scoped to the user and project. | !ONOPENWRITEPROJECTCACHE(key) | cache, project, write |
| !ONOPENWRITELOCATIONCACHE | Writes the attributes current value to the location scoped cache, the cache item is scoped to the user and location. | !ONOPENWRITELOCATIONCACHE(key) | cache, location, write |
| !ONOPENGETLOCATIONNAME | Gets the name of the location the feature is in. | !ONOPENGETLOCATIONNAME | location, name, location name |
| !ONOPENGETPROJECTNAME | Gets the name of the current project the feature is in. | !ONOPENGETPROJECTNAME | project, name, project name |
| !CHNATTRIBUTE | Gets the value of an attribute from the alignment feature, the parameter is the name of the attribute to get (e.g. !CHNATTRIBUTE(Units)). | !CHNATTRIBUTE(AlignmentAttributeName) | chainage, alignment, attribute, field, attribute |

## Geometry Based Default Codes
These default codes are calculated and set when the geometry of a feature is changed.

| Code | Description | Example | Tags |
|------|------|------|------|
| !LEN | Length of the geometry in meters | !LEN | geometry, length |
| !AREA | 2D area of the geometry in square meters | !AREA | geometry, area |
| !FEATUREX | X coordinate of the geometry in the coordinate system defined by the project the feature belongs to. Only available for point geometries. | !FEATUREX | geometry, coordinates, point, easting |
| !FEATUREY | Y coordinate of the geometry in the coordinate system defined by the project the feature belongs to. Only available for point geometries. | !FEATUREY | geometry, coordinates, point, northing |
| !FEATUREZ | Z coordinate of the geometry in the coordinate system defined by the project the feature belongs to. Only available for point geometries. | !FEATUREZ | geometry, coordinates, point, elevation |
| !FEATURELAT | Latitude of the feature geometry. Only available for point geometries. | !FEATURELAT | geometry, coordinates, point, latitude |
| !FEATURELNG | Longitude of the feature geometry. Only available for point geometries. | !FEATURELNG | geometry, coordinates, point, longitude |
| !FEATUREALT | Altitude of the feature geometry. Only available for point geometries. | !FEATUREALT | geometry, coordinates, point, altitude |
| !SNAPPEDSTART | Gets the attribute value from a point feature snapped to the start of a linestring. Parameter 1 is the attribute name to get the value from. The example would get the CONVER_LEV attribute from the point feature snapped to the start of the linestring. | !SNAPPEDSTART(COVER_LEV) | pipe, snapping, start |
| !SNAPPEDEND | Gets the attribute value from a point feature snapped to the end of a linestring. Parameter 1 is the attribute name to get the value from. The example would get the CONVER_LEV attribute from the point feature snapped to the end of the linestring. | !SNAPPEDEND(COVER_LEV) | pipe, snapping, end |
| !CHN | Chainage along the map alignment for the feature geometry. Only available for point geometries. | !CHN | chainage, chain |
| !CHNOFFSET | Offset from the map alignment for the feature geometry. Only available for point geometries. | !CHNOFFSET | chainage, offset |
| !CHNMIN | Minimum chainage along the map alignment for the feature geometry. Available for point and linear geometries. | !CHNMIN | chainage, min |
| !CHNMAX | Maximum chainage along the map alignment for the feature geometry. Available for point and linear geometries. | !CHNMAX | chainage, max |

## Calculation Based Default Codes
These default codes are for calculation based fields, They run when they are autonavigated over and when the form is opened.

| Code | Description | Example | Tags |
|------|------|------|------|
| !CALC | Perform a calculation using the given expression. The expression can include mathematical operations and field names. You can make the calculation react to attribute updates by prefixing the attribute name with $ | !CALC 2 + 2, !CALC field1 * field2, !CALC field1 + 5, !CALC $field1 + $field2 | calculation, math, expression |
| !CALCW3WNOW | Get the users current position's What3Words address. This calc code does not run when the feature type is opened - only when the attribute is selected/autoselected. | !CALCW3WNOW | calculation, w3w, what3words, location |
| !CALCRPR | Calculates the RPR (Root Protection Radius), typically of a tree, based on the number of stems and stem diameters provided. You must have a 'StemCnt' attribute indicating the number of stems, and 'StemDia1', 'StemDia2', etc. attributes for each stem diameter in millimeters. The calculated RPR is capped at a maximum of 15 meters. The average IR (Instantaneous Radius) is also calculated and cached for use in other features via the location cache. | !CALCRPR |  |

## Modifier Default Codes
These default codes modify properties of an attribute (mandatory, hidden, read only etc) depending on a condition.

| Code | Description | Example | Tags |
|------|------|------|------|
| !MODIFIER-FORCEPHOTOCAPTURE | Modifies a FileUpload attribute to be mandatory and visible if the expression evaluates to true, otherwise it is hidden and not mandatory. The example below makes the attribute mandatory and visible if the value of the attribute with the code 'condition_field' is 'needs_repair'. The dollar sign makes this reactive, so it will reevaluate when the value of 'condition_field' changes. The expression must evaluate to a boolean value. | !MODIFIER-FORCEPHOTOCAPTURE $condition_field == 'needs_repair' | modifier, photo, nested photo |
| !MODIFIER-SHOWWHEN | Modifies an attribute to be visible if the expression evaluates to true, otherwise it is hidden. The example below makes the attribute visible if the value of the attribute with the name 'status' is set to 'active'. The dollar sign makes this reactive, so it will reevaluate when the value of 'status' changes. The expression must evaluate to a boolean value. If the attribute is being hidden and it has a value, the value will be removed. | !MODIFIER-SHOWWHEN $status == 'active' | modifier, hidden |
| !MODIFIER-HIDEWHEN | Modifies an attribute to be hidden if the expression evaluates to true, otherwise it is visible. The example below makes the attribute hidden if the value of the attribute with the name 'status' is set to 'inactive'. The dollar sign makes this reactive, so it will reevaluate when the value of 'status' changes. The expression must evaluate to a boolean value. If the attribute is being hidden and it has a value, the value will be removed. | !MODIFIER-HIDEWHEN $status == 'inactive' | modifier, hidden |
| !MODIFIER-HIDE | Modifies an attribute to be hidden. | !MODIFIER-HIDE | modifier, hidden |
| !MODIFIER-READONLY | Modifies an attribute to be read only. | !MODIFIER-READ_ONLY | modifier, read-only |
| !MODIFIER-SHOWTHUMBNAIL | Modifies a FileUpload (if it's a sketch or photo) attribute to use a thumbnail in the feature type attribute list. | !MODIFIER-THUMBNAIL | modifier, thumbnail, photo |

## Sketch Attribute Default Codes
These default codes are used specifically with sketch attributes (FileUpload attributes with a Drawing attribute setting) to load images into the sketch canvas.
The PNG images must be uploaded to a location with the format like 'filename.png.system'. But can then be accessed across a project.
| Code | Description | Example | Tags |
|------|------------|---------|------|
| !LOADIMAGE(filename) | Loads a specific image file directly into the sketch canvas, assumes the extension is .png | !LOADIMAGE(photoname) | sketch, image, load |
| !LOADIMAGE([attributename]) | Loads an image linked to an attribute value, where the attribute name in square brackets is replaced with the actual attribute value. Assumes the extension is .png | !LOADIMAGE([inspection_id]) | sketch, image, load, dynamic |
## !CALC Expressions
!CALC uses Excel-like expressions to generate values from attributes and functions. 
You can reference attributes by name, and make expressions reactive by prefixing with a dollar sign (e.g. $field1).
It's impossible to list all the different things you can do with !CALC expressions, if a !CALC expression fails to evaluate
then an error should be present in the logs. Here are some examples of different things you can do with !CALC expressions:

### Examples
* `!CALC $Field1 + 10`
* `!CALC ($length * $width) / 2`
* `!CALC $status == 'active' ? 'Yes' : 'No'`

### Utility Functions
Utility functions are helpers you can call inside expressions to transform or combine values.
* **join(parts, separator)** — Join a list into a string.
  * Example: `!CALC join([Field1, Field2], '-')`
* **number(value)** — Parse a value to a number (returns 0 on failure).
  * Example: `!CALC number($Field1) + 10`
* **numberOrNull(value)** — Parse a value to a number (returns null on failure).
  * Example: `!CALC numberOrNull($Field2)`

### Expressions in Modifier Default Codes
Modifier default codes use the same expression parser, so you can write boolean expressions there too.

Examples:
* `!MODIFIER-SHOWWHEN $status == 'active'`
* `!MODIFIER-HIDEWHEN number($riskScore) > 10`

