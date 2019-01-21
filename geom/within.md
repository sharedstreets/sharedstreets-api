**Geometries within bbox**
----
  Returns GeoJSON data for SharedStreets Geometries within a bounding box.

* **URL**

  /geom/within

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
   
   `authKey=[SharedStreets API Key]`

   `bounds=[lng1],[lat1],[lng2],[lat2]` a bounding box defined by two corners (e.g. NE and SW) expressed in decimal degrees

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{type:"FeatureCollection", features: [...]}`
 

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

