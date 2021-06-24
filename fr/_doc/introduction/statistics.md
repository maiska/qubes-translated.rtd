---
lang: fr
layout: site
permalink: /fr/statistics/
redirect_from:
- /fr/counter/
ref: 127
title: Statistics
---

<div class="center-block more-bottom">
  <a href="https://tools.qubes-os.org/counter/stats.png">
    <img src="https://tools.qubes-os.org/counter/stats.png" alt="Estimated Qubes OS userbase graph"/>
  </a>
</div>

## FAQ
<a id="faq"></a>

### How often is this graph updated?
<a id="how-often-is-this-graph-updated"></a>

Daily.

### Why is the bar for the current month so low?
<a id="why-is-the-bar-for-the-current-month-so-low"></a>

Since the graph is updated daily, the bar for the current month will be very low at the start of the month and rise gradually until the end of the month.

### How is the userbase estimated?
<a id="how-is-the-userbase-estimated"></a>

We simply count the number of unique IPv4 addresses that connect to the Qubes update servers each month (except for Tor connections; see [below](#how-has-the-methodology-for-counting-tor-users-changed)).

### How has the methodology for counting Tor users changed?
<a id="how-has-the-methodology-for-counting-tor-users-changed"></a>

Before, we simply counted the number of unique Tor exit node IPv4 addresses that connected to the Qubes update servers each month.
However, this underestimated the actual number of Tor users, since many Tor users can use the same exit node.
The new methodology is to estimate the number of Tor users as a proportion of the total number of *requests* from Tor exit nodes on the assumption that the proportion of users to requests is roughly the same for both clearnet and Tor users.
To be precise, the formula is:

```
tor_users = tor_requests * (plain_users / plain_requests)
```

Where:

- `tor_users` is the estimated number of Qubes users who download updates via Tor each month.
- `tor_requests` is the total number of requests the Qubes update servers receive from Tor exit nodes each month.
- `plain_users` is the number of unique clearnet IPv4 addresses that connect to the Qubes update servers each month.
- `plain_requests` is the total number of requests the Qubes update servers receive from clearnet IPv4 addresses each month.

We cross-reference the list of connecting IP addresses with [TorDNSEL's exit lists](https://metrics.torproject.org/collector.html#type-tordnsel) in order to distinguish Tor and clearnet IPs and requests.
For this purpose, we count an IP address as belonging to a Tor exit node if there was a Tor exit node active for that address within the 24-hour periods before or after it connected to the Qubes update servers.

### What kinds of data do you collect about Qubes users?
<a id="what-kinds-of-data-do-you-collect-about-qubes-users"></a>

Please see our [Privacy Policy](/fr/privacy/).

### Where can I find the raw data and source code?
<a id="where-can-i-find-the-raw-data-and-source-code"></a>

The raw data is available [here](https://tools.qubes-os.org/counter/stats.json).
(This does not include any personally-identifying user data.)
Please note that the format of this data is not documented and may change any time if the developers feel the need to include something else.
The source code is available [here](https://github.com/woju/qubes-stats).