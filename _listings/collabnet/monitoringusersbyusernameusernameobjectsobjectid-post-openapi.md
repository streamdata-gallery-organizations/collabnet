---
swagger: "2.0"
x-collection-name: CollabNet
x-complete: 0
info:
  title: CollabNet TeamForge API Documentation Monitors the current object for the
    given username.
  version: 1.0.0
  description: Monitors the current object for the given username..
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
  /integrationdata/by-objectid/{objectid}/by-name/{namespace}:
    get:
      summary: Gets integration data for an object by namespace name
      description: Gets integration data for an object by namespace name.
      operationId: getIntegrationDataByName
      x-api-path-slug: integrationdatabyobjectidobjectidbynamenamespace-get
      parameters:
      - in: query
        name: dataname
        description: Data name
      - in: path
        name: namespace
        description: Namespace name
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Integration
      - Dataan
      - Object
      - By
      - Namespace
      - Name
    put:
      summary: Sets integration data for an object by namespace name
      description: Sets integration data for an object by namespace name.
      operationId: setIntegrationDataByName
      x-api-path-slug: integrationdatabyobjectidobjectidbynamenamespace-put
      parameters:
      - in: body
        name: body
        description: Integration data
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: createNamespace
        description: Create namespace if missing?
      - in: path
        name: namespace
        description: Namespace name
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Sets
      - Integration
      - Dataan
      - Object
      - By
      - Namespace
      - Name
    delete:
      summary: Removes integration data for an object by namespace name
      description: Removes integration data for an object by namespace name.
      operationId: removeIntegrationDataByName
      x-api-path-slug: integrationdatabyobjectidobjectidbynamenamespace-delete
      parameters:
      - in: query
        name: dataname
        description: Data name
      - in: path
        name: namespace
        description: Namespace name
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Removes
      - Integration
      - Dataan
      - Object
      - By
      - Namespace
      - Name
  /integrationdata/by-objectid/{objectid}/{namespaceid}:
    get:
      summary: Gets integration data for an object by namespace id
      description: Gets integration data for an object by namespace id.
      operationId: getIntegrationData
      x-api-path-slug: integrationdatabyobjectidobjectidnamespaceid-get
      parameters:
      - in: query
        name: dataname
        description: Data name
      - in: path
        name: namespaceid
        description: Namespace id
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Integration
      - Dataan
      - Object
      - By
      - Namespace
    put:
      summary: Sets integration data for an object by namespace id
      description: Sets integration data for an object by namespace id.
      operationId: setIntegrationData
      x-api-path-slug: integrationdatabyobjectidobjectidnamespaceid-put
      parameters:
      - in: body
        name: body
        description: Integration data
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: namespaceid
        description: Namespace id
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Sets
      - Integration
      - Dataan
      - Object
      - By
      - Namespace
    delete:
      summary: Removes integration data for an object by namespace id
      description: Removes integration data for an object by namespace id.
      operationId: removeIntegrationData
      x-api-path-slug: integrationdatabyobjectidobjectidnamespaceid-delete
      parameters:
      - in: query
        name: dataname
        description: Data name
      - in: path
        name: namespaceid
        description: Namespace id
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Removes
      - Integration
      - Dataan
      - Object
      - By
      - Namespace
  /integrationdata/myself/by-name/{namespace}:
    get:
      summary: Gets integration data for current user by namespace name
      description: Gets integration data for current user by namespace name.
      operationId: getMyIntegrationDataByName
      x-api-path-slug: integrationdatamyselfbynamenamespace-get
      parameters:
      - in: query
        name: dataname
        description: Data name
      - in: path
        name: namespace
        description: Namespace name
      responses:
        200:
          description: OK
      tags:
      - Integration
      - Datacurrent
      - User
      - By
      - Namespace
      - Name
    put:
      summary: Sets integration data for current user by namespace name
      description: Sets integration data for current user by namespace name.
      operationId: setMyIntegrationDataByName
      x-api-path-slug: integrationdatamyselfbynamenamespace-put
      parameters:
      - in: body
        name: body
        description: Integration data
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: createNamespace
        description: Create namespace if missing?
      - in: path
        name: namespace
        description: Namespace name
      responses:
        200:
          description: OK
      tags:
      - Sets
      - Integration
      - Datacurrent
      - User
      - By
      - Namespace
      - Name
    delete:
      summary: Removes integration data for current user by namespace name
      description: Removes integration data for current user by namespace name.
      operationId: removeMyIntegrationDataByName
      x-api-path-slug: integrationdatamyselfbynamenamespace-delete
      parameters:
      - in: query
        name: dataname
        description: Data name
      - in: path
        name: namespace
        description: Namespace name
      responses:
        200:
          description: OK
      tags:
      - Removes
      - Integration
      - Datacurrent
      - User
      - By
      - Namespace
      - Name
  /integrationdata/myself/{namespaceid}:
    get:
      summary: Gets integration data for current user by namespace id
      description: Gets integration data for current user by namespace id.
      operationId: getMyIntegrationData
      x-api-path-slug: integrationdatamyselfnamespaceid-get
      parameters:
      - in: query
        name: dataname
        description: Data name
      - in: path
        name: namespaceid
        description: Namespace id
      responses:
        200:
          description: OK
      tags:
      - Integration
      - Datacurrent
      - User
      - By
      - Namespace
    put:
      summary: Sets integration data for current user by namespace id
      description: Sets integration data for current user by namespace id.
      operationId: setMyIntegrationData
      x-api-path-slug: integrationdatamyselfnamespaceid-put
      parameters:
      - in: body
        name: body
        description: Integration data
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: namespaceid
        description: Namespace id
      responses:
        200:
          description: OK
      tags:
      - Sets
      - Integration
      - Datacurrent
      - User
      - By
      - Namespace
    delete:
      summary: Removes integration data for current user by namespace id
      description: Removes integration data for current user by namespace id.
      operationId: removeMyIntegrationData
      x-api-path-slug: integrationdatamyselfnamespaceid-delete
      parameters:
      - in: query
        name: dataname
        description: Data name
      - in: path
        name: namespaceid
        description: Namespace id
      responses:
        200:
          description: OK
      tags:
      - Removes
      - Integration
      - Datacurrent
      - User
      - By
      - Namespace
  /integrationdata/namespaces:
    post:
      summary: Registers namespace
      description: Registers namespace.
      operationId: registerNamespace
      x-api-path-slug: integrationdatanamespaces-post
      parameters:
      - in: body
        name: body
        description: Namespace
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Registers
      - Namespace
  /integrationdata/namespaces/by-name/{namespace}:
    get:
      summary: Gets namespace info by name
      description: Gets namespace info by name.
      operationId: getNamespaceByName
      x-api-path-slug: integrationdatanamespacesbynamenamespace-get
      parameters:
      - in: path
        name: namespace
        description: Namespace name
      responses:
        200:
          description: OK
      tags:
      - Namespace
      - Info
      - By
      - Name
  /monitoring/objects/{objectid}/users:
    get:
      summary: Returns the list of monitoring users for the object(Folder/Item).
      description: Returns the list of monitoring users for the object(folder/item)..
      operationId: listUsersForObject
      x-api-path-slug: monitoringobjectsobjectidusers-get
      parameters:
      - in: query
        name: count
        description: Max
      - in: path
        name: objectid
        description: Object id
      - in: query
        name: offset
        description: Offset
      responses:
        200:
          description: OK
      tags:
      - Returns
      - List
      - Of
      - Monitoring
      - Usersthe
      - Object(Folder
      - Item)
  /monitoring/users/by-username/{username}/objects:
    get:
      summary: Returns the list of monitoring items for the given username
      description: Returns the list of monitoring items for the given username.
      operationId: monitoringItemsForUsername
      x-api-path-slug: monitoringusersbyusernameusernameobjects-get
      parameters:
      - in: query
        name: count
        description: Max
      - in: query
        name: offset
        description: Offset
      - in: query
        name: projectid
        description: Project Id
      - in: path
        name: username
        description: Username
      responses:
        200:
          description: OK
      tags:
      - Returns
      - List
      - Of
      - Monitoring
      - Itemsthe
      - Given
      - Username
    post:
      summary: Monitors / Unmonitors the list of objects for the given username
      description: Monitors / unmonitors the list of objects for the given username.
      operationId: monitorOrUnmonitorObjectsByUsername
      x-api-path-slug: monitoringusersbyusernameusernameobjects-post
      parameters:
      - in: query
        name: action
        description: To perform action
      - in: body
        name: body
        description: Monitor / Unmonitor items
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: username
        description: Username
      responses:
        200:
          description: OK
      tags:
      - Monitors
      - ""
      - ""
      - Unmonitors
      - List
      - Of
      - Objectsthe
      - Given
      - Username
  /monitoring/users/by-username/{username}/objects/{objectid}:
    get:
      summary: Monitoring the current object or not for the given username (true /
        false)
      description: Monitoring the current object or not for the given username (true
        / false).
      operationId: isObjectMonitoredByUsername
      x-api-path-slug: monitoringusersbyusernameusernameobjectsobjectid-get
      parameters:
      - in: path
        name: objectid
        description: Object id
      - in: path
        name: username
        description: Username
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Current
      - Object
      - Notthe
      - Given
      - Username
      - (true
      - ""
      - ""
      - False)
    post:
      summary: Monitors the current object for the given username.
      description: Monitors the current object for the given username..
      operationId: monitorObjectByUsername
      x-api-path-slug: monitoringusersbyusernameusernameobjectsobjectid-post
      parameters:
      - in: path
        name: objectid
        description: Object id
      - in: path
        name: username
        description: Username
      responses:
        200:
          description: OK
      tags:
      - Monitors
      - Current
      - Objectthe
      - Given
      - Username
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