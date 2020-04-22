---
TIP: 42
Title: Terra Payments URI Scheme
Created: 2020-04-23
Authors: Terraform Labs, PTE <ecosystem@terra.money>
Type: Standards Track
Status: Draft
---

This TIP introduces a URI scheme for Terra payments, which aims to establish a standard format for encoding **payment request** details into a serial URI format that can be loaded by a variety of user-facing Terra wallet applications to simplify user experience.

TIP21 draws inspiration from URI schemes for payments in well-established blockchain protocols, such as BIP21 and EIP67.

NOTE: "Terra Payments," as employed in this document, refers specifically to a simple transaction which includes a `MsgSend`, conveying the properties of

- sender (Terra address)
- recipient (Terra address)
- amount, a set of Coins of varying denominations.

## Motivation

Currently, the procedure for Terra payments is based on manual input entry for the majority of Terra wallet and client applications (such as station).

This TIP would allow users to simply paste in a URL, click a link, or scan a QR code which would populate the necessary payment details instead of having to enter fields in, where errors in payment address, amount, memo, and fee may arise.

## Specification

### General rules for handling

Terra clients MUST NOT act on URIs without getting the user's authorization. They SHOULD require the user to manually approve each payment individually, though in some cases they MAY allow the user to automatically make this decision.

## Operating system integration

Graphical Terra clients SHOULD register themselves as the handler for the "terra:" URI scheme by default, if no other handler is already registered. If there is already a registered handler, they MAY prompt the user to change it once when they first run the client.

## General Format

Terra Payment URIs will follow the general format for URIs as set forth in RFC 3986. The path component consists of a Terra address, and query component provides additional payment options.

Elements of the query component may contain characters outside the valid range. These must first be encoded according to UTF-8, and then each octet of the corresponding UTF-8 sequence must be percent-encoded as described in RFC 3986.

```
terra://<address>?amount=<coins>&memo=<memo-str>

address = Terra Bech32 account address of recipient
coins = comma-separated list of Coins of <amount><denom>
  amount = [0-9]+
  denom = e.g. uluna, ukrw, ...
memo-str = URL-encoded string
```

## Implementation

## Notable Problems

Signing?
