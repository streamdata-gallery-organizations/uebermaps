---
swagger: "2.0"
x-collection-name: uebermaps
x-complete: 0
info:
  title: uebermaps List your collaborator invitations
  description: List your collaborator invitations.
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