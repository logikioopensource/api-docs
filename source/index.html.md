---
title: Logik.io API Reference

language_tabs:
  - http: HTTP
  - shell: cURL
  - python: Python
  - javascript: Javascript
  - javascript--nodejs: Node.JS
  - java: Java
  - ruby: Ruby
  - go: Go

toc_footers:
  - <a href='https://logikio3.my.site.com/s/'>Logik.io Support Portal</a>
  - <a href='https://github.com/logikioopensource/API-Documentation'>Logik.io Open Source Repo</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - content
  - errors
search: true
code_clipboard: true
highlight_theme: monokai
headingLevel: 2
meta:
  - name: description
    content: Documentation for the Logik.io Admin APIs
---

# Introduction

Welcome to the Logik.io API! You can use our API to access Logik.io Admin API endpoints, to access Blueprints, Managed Tables and perform various automation tasks like importing and exporting data.

We have language examples available for several common languages. You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

Logik.io uses API keys to allow access to the API. You can register a new Admin API key in your environment, by navigating to "Utilities" > "Admin API Keys" in the Logik.io admin screen.

Logik.io expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer example123456789`

<aside class="notice">
You must replace <code>example123456789</code> with your specific Admin API key.
</aside>

# Servers

Base URLs:

- <a href="https://{tenant}.{sector}.logik.io">https://{tenant}.{sector}.logik.io</a>

  - **tenant** - Logik.io tenant

    - Default value: example

  - **sector** - Logik.io sector

    - Default value: test

<a href="mailto:support@logik.io">Contact Support</a>
