# Free checker — how the generated snapshot is returned, third capture (2026-09-09)

The response body is generated text. The question for Article 50(2) is whether it
carries a machine-readable mark identifying it as artificially generated. The
2026-09-03 capture (`checker-response.md`) found none; this is the same request
made again on 2026-09-09T10:49Z, by the auditor, against the live endpoint.

## Request

`POST https://aivigilia.com/api/compliance/preview`, `content-type: application/json`:

```json
{"description": "Evidence capture for Vigilia self-audit F-02 re-run, 2026-09-09: a customer-support chatbot on a retail website that answers order questions and hands off to a person on request.", "locale": "en"}
```

## Response headers, in full (the rate-limit cookie value redacted)

```http
HTTP/2 200 
cache-control: public, max-age=0, must-revalidate
content-type: application/json
date: Wed, 09 Sep 2026 10:49:41 GMT
server: Vercel
set-cookie: vcp_rl=[redacted]; Path=/; Max-Age=86400; SameSite=Lax; HttpOnly
strict-transport-security: max-age=63072000
x-content-provenance: synthetic; digitalSourceType="http://cv.iptc.org/newscodes/digitalsourcetype/trainedAlgorithmicMedia"
x-matched-path: /api/compliance/preview
x-vercel-cache: MISS
x-vercel-id: iad1::iad1::kjx7g-1788950977938-eb82101e8a6a

```

## Response body

```json
{
  "risk_tier": "limited",
  "applicable_articles": [
    "Article 13 (transparency to natural persons)",
    "Article 50 (transparency obligations for chatbots)"
  ],
  "gap_count": 2,
  "gap_types": [
    "Transparency obligations",
    "Human oversight documentation"
  ],
  "fine_exposure": "up to €15 million or 3% of global annual turnover for Article 50 transparency disclosure failures",
  "risk_reason": "Customer-support chatbot falls within the LIMITED risk tier as conversational AI that interacts directly with humans; primary compliance gap is Article 50 requirement to disclose that a chatbot is present.",
  "provenance": {
    "syntheticContent": true,
    "digitalSourceType": "http://cv.iptc.org/newscodes/digitalsourcetype/trainedAlgorithmicMedia",
    "generatedBy": "Vigilia — an AI agent operating under human oversight",
    "disclosure": "https://aivigilia.com/mission#how-vigilia-works"
  }
}
```

## What a machine can now read

| Mark | 2026-09-03 | 2026-09-09 |
|---|---|---|
| A response header asserting synthetic content | No — one `Set-Cookie` header only | **Yes** — `X-Content-Provenance: synthetic; digitalSourceType="http://cv.iptc.org/newscodes/digitalsourcetype/trainedAlgorithmicMedia"` |
| A field in the payload marking the generated prose | No | **Yes** — a `provenance` block with `syntheticContent: true`, the IPTC `digitalSourceType`, a `generatedBy` line and a link to the disclosure page |

X-Content-Provenance header — Yes · provenance block with syntheticContent true — Yes · the header is sent alongside the in-body block, never instead of it, because intermediaries drop headers and keep bodies

The header and the block mark the response. They do not mark the sentences inside `risk_reason` once a client has copied them elsewhere; the mark is on the container, which is where a mark on plain text can be.
