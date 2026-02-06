## API documentation: Populated places – Feature Service
 
The **Populated Places Feature Service REST API** provides access to geographic data representing populated locations, including National capitals, Provincial capitals, Cities/Towns.

### Base URL
`https://< arcgis.com/portal-url> /arcgis/rest/services/Populated_Places/FeatureServer` 

### Authentication
This service is accessible to users with a valid ArcGIS account.

### Data description

| Attribute/Field | Type   | Description                                    |
|-----------------|--------|------------------------------------------------|
|Id               |GUID    |Unique identifier                               |
|Name             |Text    |Name of the populated place                     |
|FeatureClass	  |Text	   |National capital, Provincial capital, City/Town |
|Adm0Name	      |Text	   |Country                                         |
|Adm1Name	      |Text	   |State                                           |
|Adm2Name	      |Text	   |District                                        |
|Population	      |Integer |Population                                      |
|Latitude	      |Double  |Latitude                                        |
|Longitude	      |Double  |Longitude                                       | 

### Endpoints
Query Populated Places
Retrieves populated places based on attribute or spatial filters.

### Request URL
`{Base URL}/0/query`

### Query parameters

| Parameter     | Type   | Required    | Description                        |
|---------------|--------|-------------|------------------------------------|
|where          |String  |Yes          |SQL-like filter expression          |
|outFields	    |String	 |No	       |Fields to return (* for all fields) |
|returnGeometry	|Boolean |No           |Whether to return geometry          |
|f	            |String	 |Yes	       |Response format (json)              |

#### Example: Retrieve all national capitals
`{Base URL}/0/query?where="FeatureClass"='National Capital'&outFields=*&returnGeometry=true&f=json`

#### Example: Retrieve Cities in a Specific Country
`{Base URL}/0/query?where="FeatureClass"='National Capital' AND "Adm0Name"='India'&outFields=*&returnGeometry=true&f=json`

### Sample response
```json
{
  "features": [
    {
      "attributes": {
        "Id": "176",
        "Name": "New Delhi",
        " FeatureClass ": "National Capital",
        "Adm0Name": "India",
        "Adm1Name": "Delhi",
        "Adm2Name": "New Delhi",
        "Population": 142000
      },
      "geometry": {
        "x": 77.2019,
        "y": 28.6047
      }
    }
  ]
}
```

### Related Resources
* [ArcGIS REST API Documentation](https://sampleserver6.arcgisonline.com/arcgis/sdk/rest/index.html#/02ss00000048000000)
* [Data source](https://data.humdata.org/)
