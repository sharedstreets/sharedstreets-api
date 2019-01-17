# SharedStreets API

## Global SharedStreets Tile Sets

SharedStreets generates and publishes a global OpenStreetMap-derived tile set of street segment references, geometries, intersections and metadata encoded in protocol bufffer format (see the [SharedStreets Referencing System](https://github.com/sharedstreets/sharedstreets-ref-system) for details). These tiles are generated from periodic weekly [planet.osm](https://planet.openstreetmap.org/) snapshots and converted to mercator z-12 tiles. The tiles are made available for download via the following endpoint:

`https://tiles.sharedstreets.io/osm/{planet-yymmdd}/12-{x}-{y}.{geometry|reference|metadata|intersection}.6.pbf` 

For a givien planet tile build (e.g. planet-180430) a valid request looks like:

`https://tiles.sharedstreets.io/osm/planet-180430/12-1171-1566.geometry.6.pbf`

### Versioned OSM data sources
SharedStreets maintains ~monthly global builds for OpenStreetMap, starting from March 2018. Currently available planet data sets are include:

* planet-180312
* planet-180430 (current default for API calls)
* planet-180528
* planet-180625
* planet-180730
* planet-180827
* planet-180924
* planet-181029
* planet-181126
* planet-181224



## SharedStreets API 

SharedStreets maintains an API that provides convenience functions on top of the tile data sets. These functions convert data to JSON and GeoJSON formats and allow dynamic map matching from point and line geometries. 

#### Base URL + Versioning
The SharedStreets API calls described below can be made via the following semantically versioned endpoint:

`https://api.sharedstreets.io/v0.1.0[/request]`

All API endpoints require a valid key to be included in the request.

#### Data source
SharedStreets API calls target specific data sources for matching and ID look up. Current API calls default to the planet-180430 OSM data source, but can be set to use any available OSM data source by using the `&dataSource=[osm/planet-yymmdd]` querystring parameter. Future versions of the API will allow selection of GIS and other non-OSM data sources.

### Public API Endpoints 

#### Identifiers

* [SharedStreets and OpenStreetMap ID lookup](query/id.md): `GET /id`

### API Endpoints requiring API Key authorization

#### Geometries

Endpoints for requesting SharedStreets data as GeoJSON:

* [Geometries within bbox](geom/within.md) : `GET /geom/within`


#### Point and Geometry Matching

Endpoints for dynamic map matching from point and line geometries:

* [Match point](match/point.md) : `GET /match/point`
* [Match points from GeoJSON](match/points.md) : `POST /match/points`
* [Match geometries from GeoJSON](match/geoms.md) : `POST /match/geoms`

