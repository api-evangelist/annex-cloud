# Annex Cloud (annex-cloud)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
