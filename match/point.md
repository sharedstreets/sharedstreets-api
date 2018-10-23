**Matched point**
----
  Returns GeoJSON data for ShareStreets point references using map matching filters.

* **URL**

  `/match/point/[lng],[lat]`
  
  `/match/point/[lng],[lat],[bearing]`

* **Method:**

  `GET`
  
*  **URL Params**

   **Required**
   
    `authKey=[SharedStrets API Key]`

   **Optional:**
    
   `bearingTolerance=[decimalDegrees]`
   Degrees tolerance (+/-) to allow for directional point queries.

   `searchRadius=[meters]`
   Search radius in meters for snapping points to SharedStreets references.

   `maxCandidates=[integer]`
   Maximum number of candidate matches to include in results.
   

* **Data Params**

  `[lat]` Latitude in decimal degrees
  
  `[lng]` Longitude in decimal degrees
  
  `[bearing]` Bearing in decimal degrees (Optional)

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{type:"FeatureCollection", features: [...]}`
 

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

