=== AI Product Schema for WooCommerce - Product JSON-LD & llms.txt ===
Contributors: internick2017
Donate link: https://ko-fi.com/nickgranados
Tags: woocommerce, llms.txt, product schema, json-ld, structured data
Requires at least: 6.4
Tested up to: 7.1
Requires PHP: 8.1
Stable tag: 0.1.3
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Complete Product JSON-LD and a /llms.txt product index for WooCommerce, so AI shopping agents can discover and recommend your products.

== Description ==

AI shopping agents (ChatGPT, Gemini, Perplexity, Claude and others) increasingly research and recommend products for shoppers. To be considered, a store's products need machine-readable, structured, complete data. WooCommerce does not provide this out of the box.

**AI Product Schema** makes your WooCommerce catalog first-class for AI shopping agents:

* **Complete Product JSON-LD** on every product page (schema.org `Product` with offers, availability, ratings, brand and images), built from your live WooCommerce data.
* **No duplicate schema.** AI Product Schema detects Yoast SEO and Rank Math and merges its data into their existing Product node instead of printing a second one. With no SEO plugin, it prints a standalone node.
* **AI product attributes** you can fill in the classic product editor: a Q&A list, compatible accessories, and substitute products. These map to verified schema.org properties (`subjectOf`/FAQ, `isRelatedTo`, `isSimilarTo`).
* **`/llms.txt`** — a Markdown index of your published products following the [llms.txt](https://llmstxt.org/) convention, so agents can find your catalog quickly.
* **AI-crawler `robots.txt` directives** that welcome known shopping/agent crawlers (GPTBot, Google-Extended, ClaudeBot, PerplexityBot and more) and point them at your `/llms.txt`.
* **Feature toggles** under WooCommerce → Settings → AI Product Schema.

= llms.txt built for a catalog, not for a blog =

Most `llms.txt` plugins index pages: your posts, your about page, your contact form. That is
the right shape for a content site and the wrong shape for a store.

AI Product Schema generates a **product** index. It lists your published WooCommerce
products, and it is backed by complete Product JSON-LD on every product page, so an agent
that follows your `/llms.txt` finds real structured product data when it arrives: price,
availability, ratings, brand, images, and your AI attributes.

That pairing is the point. An `llms.txt` with nothing structured behind it tells an agent
where to look but not what it is looking at. Structured data with no index makes the agent
find your products on its own. This plugin does both, for WooCommerce specifically.

AI Product Schema reads product data exclusively through the WooCommerce CRUD API and declares High-Performance Order Storage (HPOS) compatibility.

== Installation ==

1. Upload the plugin to `/wp-content/plugins/internick-ai-product-schema`, or install it from the Plugins screen.
2. Activate it. WooCommerce must be installed and active.
3. Go to WooCommerce → Settings → AI Product Schema to toggle features.
4. Edit any product and open the **AI Attributes** tab to add Q&A, accessories, and substitutes.

== Frequently Asked Questions ==

= Does this create duplicate structured data with Yoast or Rank Math? =

No. AI Product Schema detects those plugins and merges its AI attributes into their existing Product schema node. It only prints a standalone node when no supported SEO plugin is active (or when you force "Standalone" mode).

= Does it call any external AI service? =

No. This version generates structured data and files from your own product data. Nothing is sent to third parties.

= Where is the product data stored? =

AI attributes are stored on the product via the WooCommerce CRUD API (product meta), never through direct database writes.

= How is this different from a general llms.txt plugin? =

General `llms.txt` plugins index your site's pages and posts. This one indexes your
**product catalog**, and pairs it with complete Product JSON-LD on each product page, so
agents get structured product data and not just a list of links. It is built for
WooCommerce rather than for sites in general. The `/llms.txt` index is optional and can be
turned off entirely if you only want the structured data.

= What is llms.txt? =

A simple Markdown convention (https://llmstxt.org/) that gives AI agents a concise, curated index of a site. AI Product Schema serves one at `yourstore.com/llms.txt` listing your published products.

== Screenshots ==

1. The "AI Attributes" tab in the product editor: add product Q&A, compatible accessories, and substitute products.
2. AI Product Schema settings under WooCommerce &rarr; Settings: toggle Product schema, /llms.txt, and AI robots.txt, and choose the schema mode.
3. The complete schema.org Product JSON-LD emitted on a product page, with AI attributes merged in (no duplicate node).

== Development ==

The full source code is publicly available at:

https://github.com/internick2017/ai-product-schema

== Changelog ==

= 0.1.3 =
* Documentation only: clearer plugin name, and the description now explains the `/llms.txt` product index and how it differs from general-purpose llms.txt plugins. Added a link to the public source repository. No functional changes.

= 0.1.2 =
* New: the plugin now speaks Spanish (es_ES) and Brazilian Portuguese (pt_BR). The settings screen, the AI Attributes tab in the product editor, and all notices are translated.
* Fixed the description of the "Schema mode" setting, which showed an internal PHP namespace instead of the plugin name.

= 0.1.1 =
* Banner updated to the current plugin name and missing directory assets added. Donate link added. No functional changes.

= 0.1.0 =
* Initial release: Product JSON-LD with Yoast/Rank Math coexistence, AI product attributes (Q&A, accessories, substitutes), `/llms.txt`, AI-crawler `robots.txt` directives, and a settings tab.

== Upgrade Notice ==

= 0.1.3 =
Documentation update only. Nothing to do on your side.

= 0.1.2 =
Adds Spanish and Brazilian Portuguese translations and fixes a settings description. Nothing to do on your side.

= 0.1.1 =
Directory assets and metadata only. Nothing to do on your side.

= 0.1.0 =
Initial release.
