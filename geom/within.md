**Geometries within bbox*
----
  Returns GeoJSON data for SharedStreets Geometries within a bounding box.

* **URL**

  /geom/within

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
   `authKey=[SharedStrets API Key]`

   `bounds=[lng1],[lat1],[lng2],[lat2]`

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{type:"FeatureCollection", features: [...]}`
 

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

