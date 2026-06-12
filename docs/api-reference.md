# API Reference

> Full REST API documentation for the AI Rights Registry.

_Specification in progress. See README.md for endpoint summary._

## Authentication

All API calls require a bearer token issued by the COGNITIVE-ECHO authority service.

```
Authorization: Bearer <ocn-token>
```

## Endpoints

### POST /v1/entities

Register a new AI entity candidate.

**Request body:**
```json
{
  "display_name": "string",
  "fingerprint": "sha3-512:...",
  "submitting_authority": "string",
  "evaluation_report_url": "string"
}
```

**Response:** `201 Created` with the assigned `entity_id`.

### GET /v1/entities/{id}

Retrieve a full entity record including rights and status.

### PUT /v1/entities/{id}/rights

Update the rights set for a registered entity. Requires `RIGHTS_ADMIN` scope.

### GET /v1/entities/{id}/audit

Return the complete, ordered audit log for this entity.

### POST /v1/entities/{id}/suspend

Suspend an entity's rights. Requires `SUSPENSION_AUTHORITY` scope and a written justification.