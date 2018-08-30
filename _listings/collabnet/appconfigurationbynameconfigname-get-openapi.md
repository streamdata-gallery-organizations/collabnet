---
swagger: "2.0"
x-collection-name: CollabNet
x-complete: 0
info:
  title: CollabNet TeamForge API Documentation Get value for specified configuration
    property
  version: 1.0.0
  description: Get value for specified configuration property.
basePath: /ctfrest/foundation/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /appconfiguration:
    patch:
      summary: Updates configuration properties
      description: Updates configuration properties.
      operationId: setConfigurations
      x-api-path-slug: appconfiguration-patch
      parameters:
      - in: body
        name: body
        description: List of configuration properties
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Configuration
      - Properties
  /appconfiguration/by-name/{configname}:
    get:
      summary: Get value for specified configuration property
      description: Get value for specified configuration property.
      operationId: getValueForSpecifiedConfigurationProperty
      x-api-path-slug: appconfigurationbynameconfigname-get
      parameters:
      - in: path
        name: configname
        description: configname
      responses:
        200:
          description: OK
      tags:
      - Valuespecified
      - Configuration
      - Property
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---