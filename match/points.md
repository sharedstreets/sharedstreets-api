**Matched point**
----
  Returns GeoJSON data for ShareStreets point references using map matching filters, based on POST request containing GeoJSON Point FeatureCollection.

* **URL**

  /match/points 

* **Method:**

  `POST`
  
   **Request Body**

   `{type:"FeatureCollection", features: [point features...]}` A collection of point features. Point features may optionally include a `bearing` properity expressing point bearing in decimal degress. 

*  **URL Params**

   **Required**
    `authKey=[SharedStrets API Key]`

   **Optional:**
    
   `bearingTolerance=[decimalDegrees]`
   Degrees tolerance (+/-) to allow for directional point queries.

   `searchRadius=[meters]`
   Search radius in meters for snapping points to SharedStreets references.


* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{type:"FeatureCollection", features: [...]}`
 

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

