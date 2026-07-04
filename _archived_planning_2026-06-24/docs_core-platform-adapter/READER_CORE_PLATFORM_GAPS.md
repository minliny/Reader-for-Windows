# Reader-Core Platform Gap Notes - Windows

Snapshot date: 2026-06-23

This repository currently has no committed application scaffold. This document records
the Windows-owned platform gaps before implementation starts. It is a host-repo document
only and does not modify Reader-Core gates.

## Current State

| Area | Current state |
| --- | --- |
| App scaffold | Not present in the committed repo |
| Reader-Core bridge | Not present |
| Platform adapter evidence model | Not present |
| Build/test runner | Not present |
| Release evidence | Not present |

## Remaining Gaps

| Gap | Owner | Current blocker | Required close evidence |
| --- | --- | --- | --- |
| Local book file picker | Windows host app | No Windows UI/runtime scaffold exists | File picker smoke with redacted file metadata and permission/error mapping |
| TXT detector | Windows adapter | No adapter module exists | UTF BOM, UTF-8, GB18030/fallback detector report |
| EPUB/archive adapter | Windows adapter | No archive/parser module exists | Safe archive access, OPF/nav/ncx/cover/toc report |
| HTML/CSS/XPath/RSS parser | Windows adapter | No parser/feed runner exists | Matrix-compatible parser/feed run report |
| WebView runtime | Windows host runtime | No WebView2 or equivalent integration exists | `webview_dom_platform_smoke_runner` and redacted snapshot metadata |
| Cookie/session/credential boundary | Windows host runtime | No cookie store or secure storage backend exists | `webview_cookie_mirror_audit`, `session_cookie_login_platform_runner`, `secure_storage_platform_audit` |
| Release intake | Product governance + CI | No CI/build artifacts exist | CI artifact, host smoke report, external evidence ledger entry |

## Non-Goals

- Do not copy, translate, or adapt Legado Android implementation code.
- Do not store raw cookie values, credentials, authorization headers, query strings, HTML bodies, local file paths, or private book content.
- Do not mark Reader-Core release gates as passed from this repository.

## Next Small Windows Slice

Create the initial Windows app scaffold and a contract-only platform adapter evidence
model before implementing real file picker, parser, WebView, cookie/session, or secure
storage behavior.
