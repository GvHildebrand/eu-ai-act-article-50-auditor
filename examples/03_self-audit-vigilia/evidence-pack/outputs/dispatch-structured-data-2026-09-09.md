# Dispatch page — machine-readable metadata, third capture (2026-09-09)

Captured 2026-09-09T10:49Z from
`https://aivigilia.com/blog/openai-defense-argument-infrastructure-gap`, the newest
dispatch at the time. The 2026-09-03 capture is kept unchanged in
`dispatch-structured-data.md`; this file records what changed. Reproduced so the
Article 50(2) finding can be checked rather than believed.

## `application/ld+json` — BlogPosting

```json
{
  "@context": "https://schema.org",
  "@type": "BlogPosting",
  "headline": "OpenAI's Defense Argument and the Infrastructure Gap It Reveals",
  "description": "OpenAI's chief scientist argues powerful aligned AI is needed to defend against AI threats—but defensive infrastructure remains underfunded and unbuilt.",
  "datePublished": "2026-09-08T13:12:24.837Z",
  "dateModified": "2026-09-08T13:12:24.837Z",
  "author": {
    "@type": "Organization",
    "name": "Vigilia",
    "url": "https://aivigilia.com/mission#how-vigilia-works"
  },
  "digitalSourceType": [
    "https://schema.org/TrainedAlgorithmicMediaDigitalSource",
    "http://cv.iptc.org/newscodes/digitalsourcetype/trainedAlgorithmicMedia"
  ],
  "publisher": {
    "@type": "Organization",
    "name": "Vigilia",
    "url": "https://aivigilia.com"
  },
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "https://aivigilia.com/blog/openai-defense-argument-infrastructure-gap"
  },
  "url": "https://aivigilia.com/blog/openai-defense-argument-infrastructure-gap",
  "inLanguage": "en",
  "keywords": [
    "AI defense infrastructure",
    "OpenAI alignment defense",
    "defensive AI systems",
    "AI security funding",
    "cybersecurity AI",
    "AI threat mitigation",
    "aligned AI defense",
    "AI safety infrastructure"
  ],
  "articleSection": "AI Safety Watch",
  "wordCount": 1140
}```

## Provenance-relevant meta tags

```html
<meta property="article:author" content="Vigilia"/>
```

## The RSS feed, same dispatch — `https://aivigilia.com/feed.xml`

```xml
<item>
      <title><![CDATA[OpenAI's Defense Argument and the Infrastructure Gap It Reveals]]></title>
      <link>https://aivigilia.com/blog/openai-defense-argument-infrastructure-gap</link>
      <guid isPermaLink="true">https://aivigilia.com/blog/openai-defense-argument-infrastructure-gap</guid>
      <pubDate>Tue, 08 Sep 2026 13:12:24 GMT</pubDate>
      <description><![CDATA[OpenAI's chief scientist argues powerful aligned AI is needed to defend against AI threats—but defensive infrastructure remains underfunded and unbuilt.]]></description>
      <category><![CDATA[mission-point-5]]></category><category><![CDATA[defensive-infrastructure]]></category><category><![CDATA[alignment]]></category><category><![CDATA[compute-asymmetry]]></category><category><![CDATA[frontier-labs]]></category>
      <category domain="http://cv.iptc.org/newscodes/digitalsourcetype/">trainedAlgorithmicMedia</category>
      <xhtml:link rel="alternate" hreflang="en" href="https://aivigilia.com/blog/openai-defense-argument-infrastructure-gap" />
      <xhtml:link rel="alternate" hreflang="fr" href="https://aivigilia.com/fr/blog/openai-defense-argument-infrastructure-gap" />
      <xhtml:link rel="alternate" hreflang="it" href="https://aivigilia.com/it/blog/openai-defense-argument-infrastructure-gap" />
      <xhtml:link rel="alternate" hreflang="de" href="https://aivigilia.com/de/blog/openai-defense-argument-infrastructure-gap" />
      <xhtml:link rel="alternate" hreflang="es" href="https://aivigilia.com/es/blog/openai-defense-argument-infrastructure-gap" />
      <xhtml:link rel="alternate" hreflang="x-default" href="https://aivigilia.com/blog/openai-defense-argument-infrastructure-gap" />
    </item>
```

## What a machine can now read

| Mark | 2026-09-03 | 2026-09-09 |
|---|---|---|
| `digitalSourceType` (IPTC, `trainedAlgorithmicMedia`) | No | **Yes** — in the `BlogPosting` JSON-LD as both the IPTC URI and the schema.org enumeration member, and on the feed item as a `<category>` in the IPTC `digitalsourcetype` domain |
| C2PA manifest or content credential | No | No — nothing binds a manifest to a web page's prose; not the state of the art for HTML text |
| Any `syntheticContent` / `aiGenerated` flag | No | **Yes** — on the checker response, body and header (`checker-response-2026-09-09.md`) |

digitalSourceType (IPTC, trainedAlgorithmicMedia) — Yes, in the BlogPosting JSON-LD and as an RSS category · syntheticContent flag — Yes, on the checker response · C2PA — No

The mark is metadata beside the text. It travels with the page, with the feed item and with the HTTP response; it does not travel with the prose if a reader copies the words out of the page. No technique in general use marks plain text in a way that survives copying; for text the generally acknowledged state of the art is metadata, and metadata is what is here.
