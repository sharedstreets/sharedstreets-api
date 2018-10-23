**Matched point**
----
  Returns GeoJSON data for ShareStreets line references using map matching filters, based on POST request containing GeoJSON LineString or MultiLineString FeatureCollection.

* **URL**

  /match/geoms 

* **Method:**

  `POST`
  
   **Request Body**

   `{type:"FeatureCollection", features: [line features...]`

*  **URL Params**

   **Required**
    `authKey=[SharedStrets API Key]`

   **Optional:**
    
   `bearingTolerance=[decimalDegrees]`
   Degrees tolerance (+/-) to allow for directional queries.

   `searchRadius=[meters]`
   Search radius in meters for snapping points to SharedStreets references.


* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{type:"FeatureCollection", features: [...]}`
 

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

