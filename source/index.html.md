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
  - rt1
  - rt2
  - bom
  - content
  - errors
search: true
code_clipboard: true
highlight_theme: github
headingLevel: 2
meta:
  - name: description
    content: Documentation for the Logik.io Admin APIs
---

# Introduction

Welcome to the Logik.io API Documentation. The Logik.io APIs are divided into two categories: Runtime APIs and Admin APIs.

The Runtime APIs are used to create, update and save configurations and are the same APIs that are used in the Logik End User Configurator.

You can use the Admin APIs to work with Blueprints, Fields, Rules, Configurable Products and Managed Tables and perform various automation tasks like importing and exporting data.

We have language examples available for several common languages. You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

Logik.io uses API keys to allow access to the API. They are passed in the HTTP Authorization Header with the `Bearer <token>` scheme.

`Authorization: Bearer example123456789`

<aside class="notice">
You must replace <code>example123456789</code> with your specific API key.
</aside>

- HTTP Authentication, scheme: bearer, RuntimeApiBearerToken
- HTTP Authentication, scheme: bearer, AdminApiBearerToken

## Runtime Authentication

A Runtime Token is used for requests to the Configuration and the BOM APIs. Created in the Logik.io Admin, under Runtime Clients. This token must also be configured to allow the Origin that is passed as a Header parameter in all Runtime Configuration requests. Runtime Tokens cannot be used to access Admin APIs.

## Admin Authentication

An Admin API Token is used for requests to the Logik Admin endpoints. You can register a new Admin API key in your environment, by navigating to "Utilities" > "Admin API Keys" in the Logik.io admin screen. This is different from the Runtime Token and will not work for the Configuration and BOM APIs.

# Servers

Base URLs:

- <a href="https://{tenant}.{sector}.logik.io">https://{tenant}.{sector}.logik.io</a>

  - **tenant** - Logik.io tenant
  - **sector** - Logik.io sector

<a href="mailto:support@logik.io">Contact Support</a>
