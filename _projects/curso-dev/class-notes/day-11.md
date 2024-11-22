---
title: Day 11 - DNS
category: class-note
project: curso-dev
date: 2024-11-22
---
[curso-dev-ip-lookup]: https://dnschecker.org/domain-ip-lookup.php?query=curso.dev
[iana-domains-db]: https://iana.org/domains/root/db/
[1.1.1.1]: https://one.one.one.one/dns/


## Domain Name System

At the core, the DNS is responsible for mapping IP (Internet Protocol) addresses like *[104.26.13.195][curso-dev-ip-lookup]* to domain names like *curso.dev*. However, there are more features to this system, much like a contacts list which can have more than one number and other additional information.

The domain names in it's complete format is called **F**ully **Q**ualified **D**omain **N**ame (FQDN), and works like a file path. Each piece will tell us where to find the next one, untill it is resolved into an IP. This "path" also maps directly to the DNS' authorities hierarchy.

In the FQDN format, the domain names ends with a *"."* (which is usually hidden in the browser). This *"."* represents the **Root Zone**, the very top of this hierarchy. The *Root Zone Servers* retain the information relating to the next level of this hierarchy: the **T**op **L**evel **D**omain (TLD). These are separated into 2 categories:

* **ccTLD**: The **C**ountry **C**ode TLDs, like *".ca"* or *".br"*.
* **gTLD**: The **G**eneric TLDs, like *".com"* or *".dev"*.

> We can look at the IANA's (a root zone authority) [TLD information][iana-domains-db] to see the category of the TLD and their managing entity. - Hint: Use a wide window to view as a table.

Based on the domain's suffix, the **root server** will point to the responsible **TDL servers**. These will then point to an **Authorative Server**, which are the ones that actually holds the **DNS Records**, the "contact card" in our "contacts list".

The machine responsible for dealing with these requests is called **Recursive Resolver**. It can be provided by the ISP (Internet Service Provider), or by an entity like Cloudflare's [1.1.1.1].

Each lookup in this process is cached for performance improvements, with a time-based reevaluation - this is a *cache invalidation* strategy called **T**ime **T**o **L**ive (**TTL**).
