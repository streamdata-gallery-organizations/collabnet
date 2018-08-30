---
swagger: "2.0"
x-collection-name: CollabNet
x-complete: 0
info:
  title: CollabNet TeamForge API Documentation Gets project group members
  version: 1.0.0
  description: Gets project group members.
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
    delete:
      summary: UnMonitors the current object for the given username.
      description: Unmonitors the current object for the given username..
      operationId: unMonitorObjectByuser
      x-api-path-slug: monitoringusersbyusernameusernameobjectsobjectid-delete
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
      - UnMonitors
      - Current
      - Objectthe
      - Given
      - Username
  /monitoring/users/myself/objects:
    get:
      summary: Returns the list of monitoring items for current user
      description: Returns the list of monitoring items for current user.
      operationId: monitoringItemsForUser
      x-api-path-slug: monitoringusersmyselfobjects-get
      parameters:
      - in: query
        name: count
        description: Max
      - in: query
        name: offset
        description: Offset
      - in: query
        name: projectid
        description: Project id
      responses:
        200:
          description: OK
      tags:
      - Returns
      - List
      - Of
      - Monitoring
      - Itemscurrent
      - User
    post:
      summary: Monitors / Unmonitors the list of objects for current user.
      description: Monitors / unmonitors the list of objects for current user..
      operationId: monitorOrUnmonitorObjectsForUser
      x-api-path-slug: monitoringusersmyselfobjects-post
      parameters:
      - in: query
        name: action
        description: To perform action
      - in: body
        name: body
        description: Monitor / Unmonitor items
        schema:
          $ref: '#/definitions/holder'
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
      - Objectscurrent
      - User
  /monitoring/users/myself/objects/{objectid}:
    get:
      summary: The logged in user is monitoring the current object or not (true /
        false)
      description: The logged in user is monitoring the current object or not (true
        / false).
      operationId: isObjectMonitored
      x-api-path-slug: monitoringusersmyselfobjectsobjectid-get
      parameters:
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - The
      - Logged
      - In
      - User
      - Is
      - Monitoring
      - Current
      - Object
      - Not
      - (true
      - ""
      - ""
      - False)
    post:
      summary: Monitors the current object for current user.
      description: Monitors the current object for current user..
      operationId: monitorObjectForUser
      x-api-path-slug: monitoringusersmyselfobjectsobjectid-post
      parameters:
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Monitors
      - Current
      - Objectcurrent
      - User
    delete:
      summary: UnMonitors the current object for the current user,
      description: Unmonitors the current object for the current user,.
      operationId: unMonitorObject
      x-api-path-slug: monitoringusersmyselfobjectsobjectid-delete
      parameters:
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - UnMonitors
      - Current
      - Objectthe
      - Current
      - User
      - ""
  /monitoring/users/{userid}/objects:
    get:
      summary: Returns the list of monitoring items for the given userid
      description: Returns the list of monitoring items for the given userid.
      operationId: monitorSubforUserId
      x-api-path-slug: monitoringusersuseridobjects-get
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
        name: userid
        description: User id
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
      - Userid
    post:
      summary: Monitors / Unmonitors the list of objects for the given userid.
      description: Monitors / unmonitors the list of objects for the given userid..
      operationId: monitorOrUnmonitorObjectsByUserid
      x-api-path-slug: monitoringusersuseridobjects-post
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
        name: userid
        description: User id
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
      - Userid
  /monitoring/users/{userid}/objects/{objectid}:
    get:
      summary: Monitoring the current object or not for the given user id (true /
        false)
      description: Monitoring the current object or not for the given user id (true
        / false).
      operationId: isObjectMonitoredByUserid
      x-api-path-slug: monitoringusersuseridobjectsobjectid-get
      parameters:
      - in: path
        name: objectid
        description: Object id
      - in: path
        name: userid
        description: User id
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Current
      - Object
      - Notthe
      - Given
      - User
      - (true
      - ""
      - ""
      - False)
    post:
      summary: Monitors the current object for the given userid.
      description: Monitors the current object for the given userid..
      operationId: monitorObjectByUserid
      x-api-path-slug: monitoringusersuseridobjectsobjectid-post
      parameters:
      - in: path
        name: objectid
        description: Object id
      - in: path
        name: userid
        description: User id
      responses:
        200:
          description: OK
      tags:
      - Monitors
      - Current
      - Objectthe
      - Given
      - Userid
    delete:
      summary: UnMonitors the current object for given userid
      description: Unmonitors the current object for given userid.
      operationId: unMonitorObjectByid
      x-api-path-slug: monitoringusersuseridobjectsobjectid-delete
      parameters:
      - in: path
        name: objectid
        description: Object id
      - in: path
        name: userid
        description: User id
      responses:
        200:
          description: OK
      tags:
      - UnMonitors
      - Current
      - Objectgiven
      - Userid
  /myself/recent/objects:
    get:
      summary: Gets recent object list for the current user
      description: Gets recent object list for the current user.
      operationId: getMyRecentObjects
      x-api-path-slug: myselfrecentobjects-get
      parameters:
      - in: query
        name: count
        description: Max
      responses:
        200:
          description: OK
      tags:
      - Recent
      - Object
      - Listthe
      - Current
      - User
  /myself/recent/projects:
    get:
      summary: Gets recent project list for the current user
      description: Gets recent project list for the current user.
      operationId: getMyRecentProjects
      x-api-path-slug: myselfrecentprojects-get
      parameters:
      - in: query
        name: count
        description: Max
      responses:
        200:
          description: OK
      tags:
      - Recent
      - Project
      - Listthe
      - Current
      - User
  /objects/{artifactId}/comments/{commentId}/edit:
    post:
      summary: Edit a comment added by the same user, on the given artifact id
      description: Edit a comment added by the same user, on the given artifact id.
      operationId: editComment
      x-api-path-slug: objectsartifactidcommentscommentidedit-post
      parameters:
      - in: path
        name: artifactId
        description: Artifact id
      - in: body
        name: body
        description: Comment
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: commentId
        description: Comment id
      responses:
        200:
          description: OK
      tags:
      - Edit
      - Comment
      - Added
      - By
      - Same
      - User
      - ""
      - "On"
      - Given
      - Artifact
  /objects/{objectid}/associations:
    get:
      summary: Gets the association information for the given object id
      description: Gets the association information for the given object id.
      operationId: getObjectAssociations
      x-api-path-slug: objectsobjectidassociations-get
      parameters:
      - in: query
        name: depth
        description: Number of levels
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
      - in: path
        name: objectid
        description: Object/Activity id
      responses:
        200:
          description: OK
      tags:
      - Association
      - Informationthe
      - Given
      - Object
  /objects/{objectid}/associations/{targetid}:
    put:
      summary: Creates association
      description: Creates association.
      operationId: createAssociation
      x-api-path-slug: objectsobjectidassociationstargetid-put
      parameters:
      - in: body
        name: body
        description: Association parameters
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: objectid
        description: Origin object id
      - in: path
        name: targetid
        description: Target object id
      responses:
        200:
          description: OK
      tags:
      - Creates
      - Association
    delete:
      summary: Deletes association
      description: Deletes association.
      operationId: deleteAssociation
      x-api-path-slug: objectsobjectidassociationstargetid-delete
      parameters:
      - in: path
        name: objectid
        description: Origin object id
      - in: path
        name: targetid
        description: Target object id
      responses:
        200:
          description: OK
      tags:
      - Association
  /objects/{objectid}/auditlog:
    get:
      summary: Gets a collection of audit transactions performed on the specified
        TeamForge object
      description: Gets a collection of audit transactions performed on the specified
        teamforge object.
      operationId: getAuditLog
      x-api-path-slug: objectsobjectidauditlog-get
      parameters:
      - in: query
        name: count
        description: Max
      - in: path
        name: objectid
        description: Object identifier
      - in: query
        name: offset
        description: Offset
      responses:
        200:
          description: OK
      tags:
      - Collection
      - Of
      - Audit
      - Transactions
      - Performed
      - "On"
      - Specified
      - TeamForge
      - Object
  /objects/{objectid}/comments:
    get:
      summary: Gets the comments on the given object id
      description: Gets the comments on the given object id.
      operationId: getObjectComments
      x-api-path-slug: objectsobjectidcomments-get
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
      - in: query
        name: sortby
        description: Sort by column name
      responses:
        200:
          description: OK
      tags:
      - Comments
      - "On"
      - Given
      - Object
    post:
      summary: Posts a comment on the given object id
      description: Posts a comment on the given object id.
      operationId: postComment
      x-api-path-slug: objectsobjectidcomments-post
      parameters:
      - in: body
        name: body
        description: Comment
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Comment
      - "On"
      - Given
      - Object
  /objects/{objectid}/delivery:
    get:
      summary: Gets delivery information for the given object
      description: Gets delivery information for the given object.
      operationId: getObjectDeliveryInfo
      x-api-path-slug: objectsobjectiddelivery-get
      parameters:
      - in: path
        name: objectid
        description: Object id(commit or artifact)
      responses:
        200:
          description: OK
      tags:
      - Delivery
      - Informationthe
      - Given
      - Object
  /permission/{projectid}/{folderPath}/baseline:
    get:
      summary: Check Baseline Permission for given project
      description: Check baseline permission for given project.
      operationId: check baseline permission
      x-api-path-slug: permissionprojectidfolderpathbaseline-get
      parameters:
      - in: path
        name: folderPath
      - in: path
        name: projectPath
      responses:
        200:
          description: OK
      tags:
      - Check
      - Baseline
      - Permissiongiven
      - Project
  /projectgroups:
    get:
      summary: Gets paginated project group list
      description: Gets paginated project group list.
      operationId: getProjectGroups
      x-api-path-slug: projectgroups-get
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
      - Project
      - Group
      - List
    post:
      summary: Creates project group
      description: Creates project group.
      operationId: createProjectGroup
      x-api-path-slug: projectgroups-post
      parameters:
      - in: body
        name: body
        description: New project group data
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Creates
      - Project
      - Group
  /projectgroups/{projectgroupid}:
    get:
      summary: Gets project group information
      description: Gets project group information.
      operationId: getProjectGroup
      x-api-path-slug: projectgroupsprojectgroupid-get
      parameters:
      - in: path
        name: projectgroupid
        description: Project group identifier
      responses:
        200:
          description: OK
      tags:
      - Project
      - Group
      - Information
    delete:
      summary: Deletes a project group
      description: Deletes a project group.
      operationId: deleteProjectGroup
      x-api-path-slug: projectgroupsprojectgroupid-delete
      parameters:
      - in: query
        name: force
      - in: path
        name: projectgroupid
      responses:
        200:
          description: OK
      tags:
      - Project
      - Group
    patch:
      summary: Updates project group data
      description: Updates project group data.
      operationId: updateProjectGroup
      x-api-path-slug: projectgroupsprojectgroupid-patch
      parameters:
      - in: body
        name: body
        description: Updated project group info
        schema:
          $ref: '#/definitions/holder'
      - in: header
        name: If-Match
        description: Project version
      - in: path
        name: projectgroupid
      responses:
        200:
          description: OK
      tags:
      - Project
      - Group
      - Data
  /projectgroups/{projectgroupid}/admins:
    get:
      summary: Gets project group admins
      description: Gets project group admins.
      operationId: getProjectGroupAdmins
      x-api-path-slug: projectgroupsprojectgroupidadmins-get
      parameters:
      - in: path
        name: projectgroupid
        description: Project group identifier
      responses:
        200:
          description: OK
      tags:
      - Project
      - Group
      - Admins
  /projectgroups/{projectgroupid}/admins/{username}:
    put:
      summary: Adds project group admin
      description: Adds project group admin.
      operationId: addProjectGroupAdmin
      x-api-path-slug: projectgroupsprojectgroupidadminsusername-put
      parameters:
      - in: path
        name: projectgroupid
        description: Project group identifier
      - in: path
        name: username
        description: Username
      responses:
        200:
          description: OK
      tags:
      - Project
      - Group
      - Admin
    delete:
      summary: Removes project group admin
      description: Removes project group admin.
      operationId: removeProjectGroupAdmin
      x-api-path-slug: projectgroupsprojectgroupidadminsusername-delete
      parameters:
      - in: path
        name: projectgroupid
        description: Project group identifier
      - in: path
        name: username
        description: Username
      responses:
        200:
          description: OK
      tags:
      - Removes
      - Project
      - Group
      - Admin
  /projectgroups/{projectgroupid}/members:
    get:
      summary: Gets project group members
      description: Gets project group members.
      operationId: getProjectGroupMembers
      x-api-path-slug: projectgroupsprojectgroupidmembers-get
      parameters:
      - in: path
        name: projectgroupid
        description: Project group identifier
      responses:
        200:
          description: OK
      tags:
      - Project
      - Group
      - Members
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