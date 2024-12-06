---
title: Day 11 & 12 - DNS
category: class-note
project: curso-dev
date: 2024-11-22
---
[curso-dev-ip-lookup]: https://dnschecker.org/domain-ip-lookup.php?query=curso.dev
[iana-domains-db]: https://iana.org/domains/root/db/
[1.1.1.1]: https://one.one.one.one/dns/
[dn-registrar]: https://www.cloudflare.com/learning/dns/glossary/what-is-a-domain-name-registrar/
[registro.br]: https;//registro.br
[nic.br]:https://nic.br/atividades/
[BIND]: https://en.wikipedia.org/wiki/BIND
[GeoDNS]: https://en.wikipedia.org/wiki/GeoDNS


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

---

## Registration

To register a domain, you need to contact a **[domain name registrar][dn-registrar]**, which will leverage the registration in the **registry** with the entity that manages the TLD. For example, when you request a domain from [registro.br] (a registrar) it will contact [nic.br], the entity responsible for the ccTLD '.br'.

It's important to note that the **registry** will contain the directions for an **Authoritative Server**, the *DNS Server* that holds our *DNS Records* (also called *Authoritative* **NameServer**). We can manage our own DNS Server, or use a provider's, like Cloudflare's or Vercel's. Either way, if we use a *name server* other than the registrar's, we'll have to configure it within the registrar interface.

Lastly, we add the records to the *DNS Server*. This means, add the actual "contact information" in our "contact card".

> It's important to notice that an *Authoritative NameServer* is **just a server**, running a software for a specific purpose (like [BIND]). It can delegate the resolution to yet another server, and so on (It's **recursive**!). This way it can have features like [GeoDNS].

---

## DNS Records

As our "contact card" would have multiple contact information (like multiple phone numbers, email, and address), our *DNS Record* will have multiple records of different types.

> These will be elaborated further in a future note.

---

## Related Issues



