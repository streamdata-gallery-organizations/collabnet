---
swagger: "2.0"
x-collection-name: CollabNet
x-complete: 0
info:
  title: CollabNet TeamForge API Documentation Removes a user from usergroup
  version: 1.0.0
  description: Removes a user from usergroup.
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
  /appconfiguration/by-name/{configname}/value:
    patch:
      summary: Updates the configuration value
      description: Updates the configuration value.
      operationId: updateConfigurationValue
      x-api-path-slug: appconfigurationbynameconfignamevalue-patch
      parameters:
      - in: body
        name: body
        description: Update the configuration value
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: configname
        description: configname
      responses:
        200:
          description: OK
      tags:
      - Configuration
      - Value
  /approval-requests/summary:
    get:
      summary: Gets a summary of pending approval requests on TF server
      description: Gets a summary of pending approval requests on tf server.
      operationId: getApprovalRequestSummary
      x-api-path-slug: approvalrequestssummary-get
      parameters:
      - in: query
        name: projectId
        description: Project identifier
      responses:
        200:
          description: OK
      tags:
      - Summary
      - Of
      - Pending
      - Approval
      - Requests
      - "On"
      - TF
      - Server
  /associations:
    get:
      summary: Gets the association information for the given object/activity ids
      description: Gets the association information for the given object/activity
        ids.
      operationId: getAssociations
      x-api-path-slug: associations-get
      parameters:
      - in: query
        name: depth
        description: Number of levels
      - in: query
        name: ids
        description: Comma separated object ids
      - in: query
        name: includeDependencies
        description: Include dependency associations (parent and child)
      - in: query
        name: includeEvents
        description: Include events
      - in: query
        name: includePhantoms
        description: Include phantom events
      - in: query
        name: limit
        description: Maximum number of generic associations for an object
      responses:
        200:
          description: OK
      tags:
      - Association
      - Informationthe
      - Given
      - Object
      - Activitys
  /groups:
    get:
      summary: Gets paginated user group list
      description: Gets paginated user group list.
      operationId: getUserGroups
      x-api-path-slug: groups-get
      parameters:
      - in: query
        name: count
        description: Max
      - in: query
        name: offset
        description: Offset
      - in: query
        name: sortby
        description: Sort by column name
      responses:
        200:
          description: OK
      tags:
      - Paginated
      - User
      - Group
      - List
    post:
      summary: Creates user group
      description: Creates user group.
      operationId: createUserGroup
      x-api-path-slug: groups-post
      parameters:
      - in: body
        name: body
        description: New user group data
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Creates
      - User
      - Group
  /groups/by-name/{name}:
    get:
      summary: Gets group data by fullname
      description: Gets group data by fullname.
      operationId: getItemByName
      x-api-path-slug: groupsbynamename-get
      parameters:
      - in: path
        name: name
        description: Groups full name
      responses:
        200:
          description: OK
      tags:
      - Group
      - Data
      - By
      - Fullname
  /groups/{groupid}:
    get:
      summary: Gets group data by id
      description: Gets group data by id.
      operationId: getUserGroup
      x-api-path-slug: groupsgroupid-get
      parameters:
      - in: path
        name: groupid
      responses:
        200:
          description: OK
      tags:
      - Group
      - Data
      - By
    delete:
      summary: Deletes group data by id
      description: Deletes group data by id.
      operationId: deleteUserGroup
      x-api-path-slug: groupsgroupid-delete
      parameters:
      - in: path
        name: groupid
      responses:
        200:
          description: OK
      tags:
      - Group
      - Data
      - By
    patch:
      summary: Updates group data by id
      description: Updates group data by id.
      operationId: updateUserGroup
      x-api-path-slug: groupsgroupid-patch
      parameters:
      - in: body
        name: body
        description: Updated user group info
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: groupid
      - in: header
        name: If-Match
        description: Group version
      responses:
        200:
          description: OK
      tags:
      - Group
      - Data
      - By
  /groups/{groupid}/members:
    get:
      summary: Gets usergroup members
      description: Gets usergroup members.
      operationId: getUserGroupMembers
      x-api-path-slug: groupsgroupidmembers-get
      parameters:
      - in: path
        name: groupid
      responses:
        200:
          description: OK
      tags:
      - Usergroup
      - Members
  /groups/{groupid}/members/{username}:
    put:
      summary: Adds a user to usergroup
      description: Adds a user to usergroup.
      operationId: addUserGroupMember
      x-api-path-slug: groupsgroupidmembersusername-put
      parameters:
      - in: path
        name: groupid
      - in: path
        name: username
      responses:
        200:
          description: OK
      tags:
      - User
      - To
      - Usergroup
    delete:
      summary: Removes a user from usergroup
      description: Removes a user from usergroup.
      operationId: removeUserGroupMember
      x-api-path-slug: groupsgroupidmembersusername-delete
      parameters:
      - in: path
        name: groupid
      - in: path
        name: username
      responses:
        200:
          description: OK
      tags:
      - Removes
      - User
      - From
      - Usergroup
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