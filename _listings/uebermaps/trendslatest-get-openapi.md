---
swagger: "2.0"
x-collection-name: uebermaps
x-complete: 0
info:
  title: uebermaps List latest maps
  description: List latest maps.
  termsOfService: https://uebermaps.com/terms/
  contact:
    name: uebermaps API Team
  version: "2.0"
host: uebermaps.com
basePath: /api/v2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /account:
    patch:
      summary: Update account
      description: Update account. Wrap map parameters in [user].
      operationId: account.patch
      x-api-path-slug: account-patch
      parameters:
      - in: body
        name: user
        description: user attributes
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Account
  /attachments/{id}:
    delete:
      summary: Delete attachment
      description: Delete attachment.
      operationId: attachments.id.delete
      x-api-path-slug: attachmentsid-delete
      parameters:
      - in: path
        name: id
        description: Attachment id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Attachment
  /authentication:
    post:
      summary: Sign in user
      description: Sign in user. Wrap authentication parameters in [user].
      operationId: authentication.post
      x-api-path-slug: authentication-post
      parameters:
      - in: body
        name: user
        description: user authentication attributes
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Sign
      - In
      - User
  /collaborator_invitations:
    get:
      summary: List your collaborator invitations
      description: List your collaborator invitations.
      operationId: collaborator_invitations.get
      x-api-path-slug: collaborator-invitations-get
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Your
      - Collaborator
      - Invitations
    post:
      summary: Invite user to collaborate on map
      description: Invite user to collaborate on map.
      operationId: collaborator_invitations.post
      x-api-path-slug: collaborator-invitations-post
      parameters:
      - in: body
        name: body
        description: Supply map_id and either a comma separated list of user_ids or
          emails
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Invite
      - User
      - To
      - Collaborate
      - "On"
      - Map
  /collaborator_invitations/{id}:
    delete:
      summary: Delete collaborator invitation
      description: Delete collaborator invitation.
      operationId: collaborator_invitations.id.delete
      x-api-path-slug: collaborator-invitationsid-delete
      parameters:
      - in: path
        name: id
        description: Collaborator invitation id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Collaborator
      - Invitation
    get:
      summary: Show collaborator invitation
      description: Show collaborator invitation
      operationId: collaborator_invitations.id.get
      x-api-path-slug: collaborator-invitationsid-get
      parameters:
      - in: path
        name: id
        description: Collaborator invitation id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Show
      - Collaborator
      - Invitation
    patch:
      summary: Accept collaborator invitation.
      description: Accept collaborator invitation.
      operationId: collaborator_invitations.id.patch
      x-api-path-slug: collaborator-invitationsid-patch
      parameters:
      - in: path
        name: id
        description: Collaborator invitation id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Accept
      - Collaborator
      - Invitation
  /comments/{id}:
    delete:
      summary: Delete comment
      description: Delete comment.
      operationId: comments.id.delete
      x-api-path-slug: commentsid-delete
      parameters:
      - in: path
        name: id
        description: Comment id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Comment
    patch:
      summary: Update comment
      description: Update comment. Wrap comment parameters in [comment].
      operationId: comments.id.patch
      x-api-path-slug: commentsid-patch
      parameters:
      - in: body
        name: comment
        description: Comment attributes
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: Comment id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Comment
  /events:
    get:
      summary: List your own events
      description: List your own events.
      operationId: events.get
      x-api-path-slug: events-get
      parameters:
      - in: query
        name: bounds
        description: To refine your event index request to contain only events within                                                             a
          geographical box pass the followng bounds parameters
      - in: query
        name: timeframe_end
        description: End of time range of event (ISO 8601 date format)
      - in: query
        name: timeframe_start
        description: Begin of time range of event (ISO 8601 date format)
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Your
      - Own
      - Events
  /events/{id}:
    delete:
      summary: Delete event
      description: Delete event.
      operationId: events.id.delete
      x-api-path-slug: eventsid-delete
      parameters:
      - in: path
        name: id
        description: Event id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Event
    get:
      summary: Get event
      description: Get basic information about an event
      operationId: events.id.get
      x-api-path-slug: eventsid-get
      parameters:
      - in: path
        name: id
        description: Id of event
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Event
    patch:
      summary: Update event
      description: Update event. Wrap event parameters in [event].
      operationId: events.id.patch
      x-api-path-slug: eventsid-patch
      parameters:
      - in: body
        name: event
        description: Event attributes
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: Event id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Event
  /maps:
    get:
      summary: List your own maps
      description: List your own maps.
      operationId: maps.get
      x-api-path-slug: maps-get
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Your
      - Own
      - Maps
    post:
      summary: Create map
      description: Create map. Wrap map parameters in [map]. To add a map header picture
        pass a base64 encoded string to [map][picture].
      operationId: maps.post
      x-api-path-slug: maps-post
      parameters:
      - in: body
        name: map
        description: map attributes
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Map
  /maps/search:
    get:
      summary: Search maps
      description: Search maps
      operationId: maps.search.get
      x-api-path-slug: mapssearch-get
      parameters:
      - in: query
        name: d
        description: Distance
      - in: query
        name: lat
        description: 'Latitude for search radius (default distance: 2000 meter)'
      - in: query
        name: lon
        description: 'Longitude for search radius (default distance: 2000 meter)'
      - in: query
        name: q
        description: Query
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Search
      - Maps
  /maps/{id}:
    delete:
      summary: Delete map
      description: Delete map.
      operationId: maps.id.delete
      x-api-path-slug: mapsid-delete
      parameters:
      - in: path
        name: id
        description: map id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Map
    get:
      summary: Get map
      description: Get basic information about a map
      operationId: maps.id.get
      x-api-path-slug: mapsid-get
      parameters:
      - in: path
        name: id
        description: Id of map
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Map
    patch:
      summary: Update map
      description: Update map. Wrap map parameters in [map]. To update the map header
        picture pass a base64 encoded string to [map][picture].
      operationId: maps.id.patch
      x-api-path-slug: mapsid-patch
      parameters:
      - in: path
        name: id
        description: map id
      - in: body
        name: map
        description: map settings attributes
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Map
  /maps/{id}/attachments:
    get:
      summary: List attachments for a given map
      description: List attachments for a given map.
      operationId: maps.id.attachments.get
      x-api-path-slug: mapsidattachments-get
      parameters:
      - in: path
        name: id
        description: Map id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Attachmentsa
      - Given
      - Map
    post:
      summary: Upload map attachment
      description: Upload map attachment. Wrap attachment parameters in [attachment]
      operationId: maps.id.attachments.post
      x-api-path-slug: mapsidattachments-post
      parameters:
      - in: path
        name: id
        description: Map id
      - in: body
        name: image
        description: Base64 encoded image
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Upload
      - Map
      - Attachment
  /maps/{id}/collaborators/:
    get:
      summary: List collaborators of a map
      description: List collaborators of a map.
      operationId: maps.id.collaborators.get
      x-api-path-slug: mapsidcollaborators-get
      parameters:
      - in: path
        name: id
        description: Map id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Collaborators
      - Of
      - Map
  /maps/{id}/collaborators/{user_id}:
    delete:
      summary: Delete collaboration
      description: Delete collaboration.
      operationId: maps.id.collaborators.user_id.delete
      x-api-path-slug: mapsidcollaboratorsuser-id-delete
      parameters:
      - in: path
        name: id
        description: map id
      - in: path
        name: user_id
        description: user id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Collaboration
    patch:
      summary: Update collaborator
      description: Update collaborator. Wrap collaborator parameters in [collaborator]
      operationId: maps.id.collaborators.user_id.patch
      x-api-path-slug: mapsidcollaboratorsuser-id-patch
      parameters:
      - in: body
        name: collaborator
        description: collaborator attributes
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: map id
      - in: path
        name: user_id
        description: user id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Collaborator
  /maps/{id}/comments:
    get:
      summary: List comments for a given map
      description: List comments for a given map.
      operationId: maps.id.comments.get
      x-api-path-slug: mapsidcomments-get
      parameters:
      - in: path
        name: id
        description: Id of map
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Commentsa
      - Given
      - Map
    post:
      summary: Create map comment
      description: Create map comment. Wrap comment parameters in [comment].
      operationId: maps.id.comments.post
      x-api-path-slug: mapsidcomments-post
      parameters:
      - in: body
        name: comment
        description: comment attributes
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: map id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Map
      - Comment
  /maps/{id}/respots:
    get:
      summary: List respots of a map
      description: List respots of a map.
      operationId: maps.id.respots.get
      x-api-path-slug: mapsidrespots-get
      parameters:
      - in: path
        name: id
        description: Map Id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Respots
      - Of
      - Map
  /maps/{id}/spots:
    get:
      summary: List spots for a given map
      description: List spots for a given map.
      operationId: maps.id.spots.get
      x-api-path-slug: mapsidspots-get
      parameters:
      - in: path
        name: id
        description: Id of map
      - in: query
        name: order
        description: Order of spots
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Spotsa
      - Given
      - Map
    post:
      summary: Create spot
      description: Create spot. Wrap parameters in [spot]. To add a spot picture pass
        a base64 encoded string to [spot][picture].
      operationId: maps.id.spots.post
      x-api-path-slug: mapsidspots-post
      parameters:
      - in: path
        name: id
        description: Id of map
      - in: body
        name: spot
        description: spot attributes
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Spot
  /maps/{id}/subscriptions:
    delete:
      summary: Unsubscribe from map
      description: Unsubscribe from map.
      operationId: maps.id.subscriptions.delete
      x-api-path-slug: mapsidsubscriptions-delete
      parameters:
      - in: path
        name: id
        description: map id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Unsubscribe
      - From
      - Map
    get:
      summary: List subscriptions for a given map
      description: List subscriptions for a given map.
      operationId: maps.id.subscriptions.get
      x-api-path-slug: mapsidsubscriptions-get
      parameters:
      - in: path
        name: id
        description: Id of map
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Subscriptionsa
      - Given
      - Map
  /maps/{map_id}/spots/{id}:
    get:
      summary: Get spot
      description: Get basic information about a spot
      operationId: maps.map_id.spots.id.get
      x-api-path-slug: mapsmap-idspotsid-get
      parameters:
      - in: path
        name: id
        description: Id of spot
      - in: path
        name: map_id
        description: Id of map
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Spot
  /maps/{map_id}/spots/{spot_id}/respot:
    delete:
      summary: Delete respot from map by spot id
      description: Delete respot from map by spot id.
      operationId: maps.map_id.spots.spot_id.respot.delete
      x-api-path-slug: mapsmap-idspotsspot-idrespot-delete
      parameters:
      - in: path
        name: map_id
        description: Map Id
      - in: path
        name: spot_id
        description: Spot Id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Respot
      - From
      - Map
      - By
      - Spot
      - Id
  /respot_maps:
    get:
      summary: List maps that user can respot to
      description: List maps that user can respot to.
      operationId: respot_maps.get
      x-api-path-slug: respot-maps-get
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Maps
      - That
      - User
      - Can
      - Respot
      - To
  /respots/{id}:
    delete:
      summary: Delete respot
      description: Delete respot.
      operationId: respots.id.delete
      x-api-path-slug: respotsid-delete
      parameters:
      - in: path
        name: id
        description: Respot Id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Respot
    get:
      summary: Get respot
      description: Get basic information about a respot
      operationId: respots.id.get
      x-api-path-slug: respotsid-get
      parameters:
      - in: path
        name: id
        description: Id of respot
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Respot
  /share/map/{id}:
    get:
      summary: Get secret access token to share map
      description: Get secret access token of an uebermap with access set to 'Secret
        link'. Pass the 'token' on every request you make to access this uebermap
        and its resources. F.e. token=1-x_gqu7eLBe3uKoAGAGXy
      operationId: share.map.id.get
      x-api-path-slug: sharemapid-get
      parameters:
      - in: path
        name: id
        description: Id of map
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Secret
      - Access
      - Token
      - To
      - Share
      - Map
  /spots:
    get:
      summary: List your own spots
      description: List your own spots.
      operationId: spots.get
      x-api-path-slug: spots-get
      parameters:
      - in: query
        name: order
        description: Order of spots
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Your
      - Own
      - Spots
  /spots/search:
    get:
      summary: Search spots
      description: Search spots
      operationId: spots.search.get
      x-api-path-slug: spotssearch-get
      parameters:
      - in: query
        name: d
        description: Distance
      - in: query
        name: lat
        description: Latitude for search radius (2 km)
      - in: query
        name: lon
        description: Longitude for search radius (2 km)
      - in: query
        name: q
        description: Query
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Search
      - Spots
  /spots/{id}:
    delete:
      summary: Delete spot
      description: Delete spot.
      operationId: spots.id.delete
      x-api-path-slug: spotsid-delete
      parameters:
      - in: path
        name: id
        description: spot id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Spot
    patch:
      summary: Update spot
      description: Update spot. Wrap parameters in [spot]. To update the spot picture
        pass a base64 encoded string to [spot][picture].
      operationId: spots.id.patch
      x-api-path-slug: spotsid-patch
      parameters:
      - in: path
        name: id
        description: spot id
      - in: body
        name: spot
        description: spot attributes
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Spot
  /spots/{id}/attachments:
    get:
      summary: List attachments for a given spot
      description: List attachments for a given spot.
      operationId: spots.id.attachments.get
      x-api-path-slug: spotsidattachments-get
      parameters:
      - in: path
        name: id
        description: Spot id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Attachmentsa
      - Given
      - Spot
    post:
      summary: Upload spot attachment
      description: Upload spot attachment. Wrap attachment parameters in [attachment]
      operationId: spots.id.attachments.post
      x-api-path-slug: spotsidattachments-post
      parameters:
      - in: path
        name: id
        description: Spot id
      - in: body
        name: image
        description: Base64 encoded image
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Upload
      - Spot
      - Attachment
  /spots/{id}/comments:
    get:
      summary: List comments for a given spot
      description: List comments for a given spot.
      operationId: spots.id.comments.get
      x-api-path-slug: spotsidcomments-get
      parameters:
      - in: path
        name: id
        description: Id of spot
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Commentsa
      - Given
      - Spot
    post:
      summary: Create spot comment
      description: Create spot comment. Wrap comment parameters in [comment].
      operationId: spots.id.comments.post
      x-api-path-slug: spotsidcomments-post
      parameters:
      - in: body
        name: comment
        description: comment attributes
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: spot id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Spot
      - Comment
  /spots/{id}/events:
    get:
      summary: List events for a given spot
      description: List maps for a given spot.
      operationId: spots.id.events.get
      x-api-path-slug: spotsidevents-get
      parameters:
      - in: query
        name: bounds
        description: To refine your event index request to contain only events within                                                             a
          geographical box pass the followng bounds parameters
      - in: path
        name: id
        description: Id of spot
      - in: query
        name: timeframe_end
        description: End of time range of event (ISO 8601 date format)
      - in: query
        name: timeframe_start
        description: Begin of time range of event (ISO 8601 date format)
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Eventsa
      - Given
      - Spot
    post:
      summary: Create event
      description: Create event. Wrap map parameters in [event].
      operationId: spots.id.events.post
      x-api-path-slug: spotsidevents-post
      parameters:
      - in: body
        name: event
        description: Event attributes
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: Spot id
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Event
  /spots/{id}/respots:
    post:
      summary: Respot a spot onto a map
      description: Respot a spot onto a map.
      operationId: spots.id.respots.post
      x-api-path-slug: spotsidrespots-post
      parameters:
      - in: path
        name: id
        description: Spot Id
      - in: body
        name: map_id
        description: Map Id
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Respot
      - Spot
      - Onto
      - Map
  /subscriptions:
    get:
      summary: List subscriptions. Pass no parameters to get own subscriptions
      description: List subscriptions.
      operationId: subscriptions.get
      x-api-path-slug: subscriptions-get
      parameters:
      - in: query
        name: map_id
        description: Id of map
      - in: query
        name: user_id
        description: Id of user
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Subscriptions
      - ""
      - Pass
      - "No"
      - Parameters
      - To
      - Get
      - Own
      - Subscriptions
    post:
      summary: Create map subscription
      description: Create map subscription.
      operationId: subscriptions.post
      x-api-path-slug: subscriptions-post
      parameters:
      - in: body
        name: map_id
        description: map id
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Map
      - Subscription
  /trends/latest:
    get:
      summary: List latest maps
      description: List latest maps.
      operationId: trends.latest.get
      x-api-path-slug: trendslatest-get
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Latest
      - Maps
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