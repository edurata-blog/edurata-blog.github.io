---
layout: default
title: Breakfast Info
nav_order: 1
---

# Breakfast Info

This workflow is translating "memes" from a telegram channel and tweeting them to X. The image-to-text extraction is made by [pytesseract](https://pypi.org/project/pytesseract/) and the translation with [deepl](https://www.deepl.com/translator).

## Quickstart

1. Create the necessary secrets
   1. Create a [telegram application](https://core.telegram.org/api/obtaining_api_id) and copy the tokens
      1. TELEGRAM_API_HASH
      2. TELEGRAM_API_ID
      3. TELEGRAM_API_SESSION
   2. Create a [twitter app](https://developer.twitter.com/en/apps) and copy the consumer key and secret
      1. TWITTER_CONSUMER_KEY
      2. TWITTER_CONSUMER_SECRET
      3. TWITTER_ACCESS_TOKEN
      4. TWITTER_ACCESS_TOKEN_SECRET
      5. TWITTER_BEARER_TOKEN
   3. Create a [deepl account](https://www.deepl.com/pro.html#developer) and copy the auth key
      1. DEEPL_API_KEY
1. Go to deployments and [create a new deployment](https://edurata.com/deployments)
   1. Enter any name, e.g. `ai-translation-example`
   2. Enter as source repoUrl: `github.com/Edurata/edurata-workflows` and path `examples/ai-translation` and ref `main`
   3. Save and deploy

## Showcase of features

- Using cache to work on images from several steps
-

## Workflow

- [definition](https://github.com/Edurata/edurata-workflows/blob/main/examples/ai-translator.eduwc.yaml)
-