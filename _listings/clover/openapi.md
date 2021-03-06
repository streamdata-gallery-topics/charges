swagger: "2.0"
x-collection-name: Clover
x-complete: 1
info:
  title: ""
  version: 1.0.0
host: /merchants
basePath: https://api.clover.com
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /v3/merchants/{mId}/default_service_charge:
    get:
      summary: Get default service charge for a merchant
      description: The Merchant's default service charge, set via the Setup App (https://www.clover.com/setupapp).
      operationId: GetDefaultServiceCharge
      x-api-path-slug: v3merchantsmiddefault-service-charge-get
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Default
      - Service
      - Charge
  /v3/merchants/{mId}/orders/{orderId}/service_charge/:
    post:
      summary: ""
      description: .
      operationId: ApplyServiceCharge
      x-api-path-slug: v3merchantsmidordersorderidservice-charge-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: orderId
        description: Order Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Orders
      - OrderId
      - Service
      - Charge
  /v3/merchants/{mId}/orders/{orderId}/service_charge/{chargeId}:
    delete:
      summary: Remove service charge from an order
      description: Remove service charge from an order.
      operationId: RemoveServiceCharge
      x-api-path-slug: v3merchantsmidordersorderidservice-chargechargeid-delete
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: chargeId
        description: Service Charge Id
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: orderId
        description: Order Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Orders
      - OrderId
      - Service
      - Charge
      - ChargeId