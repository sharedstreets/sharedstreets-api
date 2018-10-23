# SharedStreets API

## Global SharedStreets Tile Sets

SharedStreets generates and publishes a global OpenStreetMap-derived tile set encoded in the SharedStreets protocol bufffer format. These tiles are generated from periodic weekly planet.osm snapshots and converted to mercator z-12 tiles. The tiles are made available for download via CDN endpoint:

`https://tiles.sharedstreets.io/osm/{planet-yymmdd}/12-{x}-{y}.{geometry|reference|metadata|intersection}.6.pbf` 

For a givien planet tile build (e.g. planet-180430) a valid request looks like:

`https://tiles.sharedstreets.io/osm/planet-180430/12-1171-1566.geometry.6.pbf`




## SharedStreets API 

SharedStreets maintains a AWS-backed API that provides convenience functions on top of the tile data sets. These functions convert data to JSON and GeoJSON formats and allow dynamic map matching from point and line geometries. 

#### Base URL + Versioning
SharedStreets API calls described below are semantically versioned and provided via the following endpoint:

`https://api.sharedstreets.io/v0.1.0[/request]`

All API endpoints require a valid key to be included in the request.

### Geometries

Endpoints for requesting SharedStreets data as GeoJSON:

* [Geometries within bbox](geom/within.md) : `GET /geom/within`


### Point and Geometry Matching

Each endpoint manipulates or displays information related to the User whose
Token is provided with the request:

* [Match point](match/point.md) : `GET /match/point`
* [Match points from GeoJSON](match/point.md) : `POST /match/points`
* [Match geometries from GeoJSON](match/geoms.md) : `POST /match/geoms`

