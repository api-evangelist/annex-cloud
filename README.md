# Annex Cloud (annex-cloud)

Annex Cloud is an enterprise loyalty and customer retention platform. Its Loyalty Experience Platform is built on a set of RESTful APIs that let brands enroll and manage loyalty members, issue and redeem points, track member activity and transactions, run referral (Refer A Friend) programs, and wire loyalty into their commerce and marketing stacks.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/annex-cloud/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/annex-cloud/refs/heads/main/apis.yml)

## Access Model (Read This First)

Annex Cloud's API is **real and publicly documented** on a Redocly developer portal ([annexcloud.redocly.app](https://annexcloud.redocly.app/introduction-1)), but it is **enterprise, partner/customer-gated**:

- **Credentials are provisioned per customer.** The documentation directs prospective users to *"Contact your Customer Success Manager for assistance with API Connectors."* There is no public self-serve signup, sandbox, or free tier.
- **Authentication is JWT-based**, with tokens created through the **Tenant API**.
- **The base host is tenant-specific** and is not disclosed in the public documentation. For that reason this catalog entry does not assert a public `baseURL`; the endpoint *paths* below are transcribed from the public reference, but each customer calls their own provisioned host.
- **No public pricing** is published - Annex Cloud is sold as an enterprise loyalty platform via sales/Customer Success, so plans are contact-sales.

Endpoint paths captured here are **documented, not fabricated**. Modules whose individual paths are not exposed on the public reference are described at the module level without inventing specific endpoints.

## Tags

- Loyalty
- Customer Retention
- Rewards
- Points
- Referrals
- Customer Engagement
- Enterprise
- Gated Access

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## APIs

### Annex Cloud Members API
Create, enroll, retrieve, update, delete, search, and merge loyalty members, and read a member's activity and activity summary. Documented operations include `POST /users`, `GET/PATCH /users/{memberId}`, `POST /users/search`, `POST /mergeuser`, `GET /users/{memberId}/activity`, `GET /users/{memberId}/activitysummary/{actionId}`, and bulk `POST /bulkpostusers` / `POST /bulkpatchusers`.

- **Human URL:** [https://annexcloud.redocly.app/loyalty/loyalty](https://annexcloud.redocly.app/loyalty/loyalty)

### Annex Cloud Issuance and Transactions API
Record purchase and non-purchase transactions that issue loyalty points, and manage their lifecycle. Documented operations include `POST /issuance`, `PUT/PATCH /issuance` (update, partial/full ship, partial/full cancel), and `POST /issuancedetails/{memberId}`.

- **Human URL:** [https://annexcloud.redocly.app/loyalty/loyalty/issuance](https://annexcloud.redocly.app/loyalty/loyalty/issuance)

### Annex Cloud Multi-Point Bucket Points API
Give, redeem, and award loyalty points to members, including across multiple point buckets (Multi-Point Bucket V3). The documented operation is `POST /points`.

- **Human URL:** [https://annexcloud.redocly.app/mpb/mpb](https://annexcloud.redocly.app/mpb/mpb)

### Annex Cloud Activity and Actions API
Track and read the loyalty actions and activities performed against a site. The documented operation is `GET /actions/{status}` (with status set to `all`).

- **Human URL:** [https://annexcloud.redocly.app/loyalty/loyalty/action/getactionstatus](https://annexcloud.redocly.app/loyalty/loyalty/action/getactionstatus)

### Annex Cloud Products API
Manage products participating in a loyalty program and their point calculation. Documented operations include `POST /products`, `POST /bulkproducts`, `GET /products/{prod_id}`, `PATCH /products/{prod_id}`, and `POST /bulkpatchproducts`.

- **Human URL:** [https://annexcloud.redocly.app/loyalty/loyalty/product](https://annexcloud.redocly.app/loyalty/loyalty/product)

### Annex Cloud Orders and Receipts API
Submit cart and order data and upload purchase receipts to drive loyalty accrual. Documented operations include `POST /cart` and receipt intake (upload-by-URL).

- **Human URL:** [https://annexcloud.redocly.app/loyalty/loyalty/orders/postcart](https://annexcloud.redocly.app/loyalty/loyalty/orders/postcart)

### Annex Cloud Refer A Friend API
Power Refer A Friend (referral) programs - generate and track referral invitations across email, SMS, social, and unique links, and reward advocates and referred friends. Exposed as the Refer A Friend V3 API.

- **Human URL:** [https://annexcloud.redocly.app/raf/raf](https://annexcloud.redocly.app/raf/raf)

### Annex Cloud Tenant and Authentication API
Manage internal users and issue the JWT tokens used to authenticate every other call to the platform.

- **Human URL:** [https://annexcloud.redocly.app/introduction-1](https://annexcloud.redocly.app/introduction-1)

### Annex Cloud Registration as a Service API
Hosted member registration and account creation flows that plug into the loyalty program.

- **Human URL:** [https://annexcloud.redocly.app/introduction-1](https://annexcloud.redocly.app/introduction-1)

### Annex Cloud Incentive Engine Management API
Configure the rules, promotions, and reward logic that govern how members earn and redeem.

- **Human URL:** [https://annexcloud.redocly.app/introduction-1](https://annexcloud.redocly.app/introduction-1)

### Annex Cloud Privacy Policy Management API
Manage member consent and privacy requests such as transaction erasure (right-to-be-forgotten).

- **Human URL:** [https://annexcloud.redocly.app/introduction-1](https://annexcloud.redocly.app/introduction-1)

### Annex Cloud Webhooks API
Subscribe to loyalty events so external systems receive HTTP POST callbacks when members, points, transactions, or referrals change. Server-to-endpoint HTTP callbacks, not a bidirectional WebSocket.

- **Human URL:** [https://annexcloud.redocly.app/introduction-1](https://annexcloud.redocly.app/introduction-1)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/annex-cloud)
- [Website](https://www.annexcloud.com)
- [Documentation](https://annexcloud.redocly.app/introduction-1)
- [Sign Up](https://www.annexcloud.com/api-documentation/)
- [Plans](plans/annex-cloud-plans-pricing.yml)
- [Rate Limits](rate-limits/annex-cloud-rate-limits.yml)
- [Fin Ops](finops/annex-cloud-finops.yml)

## Review

**Does Annex Cloud expose a documented public WebSocket API?** No. The documented developer surface is request/response REST over HTTPS, and the only event/push mechanism is Webhooks (HTTP POST callbacks). No WebSocket (`ws://`/`wss://`) or SSE endpoint is documented. See [review.yml](review.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
