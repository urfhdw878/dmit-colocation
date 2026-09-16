# colocation data centres: how space, power and bandwidth actually work, and what DMIT offers across LAX, Hong Kong and Tokyo

You've got a server (or a rack of them), and nowhere sensible to run it. The office broom cupboard has no UPS, one broadband line, and a cooling strategy best described as "open a window". That's the moment colocation data centres enter the picture: you rent space, power, cooling and connectivity in a purpose-built facility, and keep ownership of the hardware itself.

This article explains what a colocation data centre actually sells you, how the pricing pieces fit together, and — since provider quality varies wildly — what DMIT (a hosting provider with carrier-neutral facilities in Los Angeles, Hong Kong and Tokyo) offers on this front, based on what's currently on their site.

## What a colocation data centre is, in plain terms

Colocation means you place your own servers, storage or network gear in a third-party facility, and rent the physical resources around them. The provider supplies the building, redundant power, cooling, physical security, and network connectivity. You supply — and keep owning — the hardware.

That's the key difference from cloud hosting. With cloud, you rent someone else's machine, usually by the hour or month. With colocation, the iron is yours: you decide the exact CPU, RAM, drives and network cards, and you can walk in (or send someone) to touch it. The trade-off is that you're also responsible for the hardware — if a drive dies at 3 a.m., either you or the facility's remote-hands team deals with it.

For most companies, the appeal is straightforward: a proper facility offers things almost no office can, like N+1 uninterruptible power supplies, diesel generator backup, biometric access control and direct connections to multiple carriers and internet exchanges.

## What you're actually paying for

Colocation pricing can look opaque until you break it into its four components. Once you understand these, quotes from different providers become comparable.

**Rack space.** Servers are measured in rack units (U). One U is 1.75 inches (about 4.45 cm) of vertical rack height. A typical pizza-box server is 1U or 2U; bulkier storage and network gear can be 4U. You rent space by the unit, or in bigger chunks — half cabinets, full cabinets, or private cages. The more contiguous, lockable space you need, the higher the tier, and the more isolation you get from other tenants.

**Power.** This is usually the real constraint, not space. Every facility allocates a power budget per rack (measured in amps), because power density drives both the facility's electrical capacity and its cooling load. Higher-density deployments — think GPU servers — need racks provisioned for more amps, which costs more. Providers typically offer metered billing (you pay for what you draw) or fixed power (a flat allocation), and serious facilities offer A/B power feeds: two independent power paths so a single feed failure doesn't take you down.

**Bandwidth.** Colocation providers generally sell network in one of three models:

- **95th percentile billing** — your throughput is sampled continuously; the top 5% of samples are discarded and you're billed on the highest remaining sample. This lets you burst occasionally without paying for the burst, which suits spiky traffic.
- **Committed rate** — you commit to a specific Mbps level, usually at a lower per-Mbps price, and stay near it.
- **Flat / unmetered** — a port with a fixed ceiling (say 1Gbps) and no traffic overage charges.

Port speeds of 1G and 10G are standard, with higher options available for larger deployments.

**Cross-connects.** A physical cable between your rack and a carrier, internet exchange (IX), or another tenant. Carrier-neutral facilities shine here: instead of one provider's network, you can cross-connect to several carriers and IXes, and blend routes yourself — or announce your own IP space via BGP.

## Footprint options: from one server to a private cage

DMIT's colocation offering is structured across three footprint tiers, which mirror how the wider market works: individual rack units, half cabinets, and full cabinets.

| Footprint | What you get | Best suited to | Pricing |
| --- | --- | --- | --- |
| Rack units (1U–4U) | Space in a shared, secured cabinet, billed per unit | Single servers or appliances, edge nodes, small deployments | Quote-based |
| Half cabinet | A lockable half cabinet with dedicated power and bandwidth | Mid-size clusters, storage, growing deployments that need isolation | Quote-based |
| Full cabinet | A full cabinet with committed power and bandwidth; private cages available on request | Dense, high-power racks and larger infrastructure | Quote-based |

One important note: DMIT publishes these tiers as reference configurations, and is explicit that availability, final specs, power density and pricing vary by location and capacity — the actual numbers come from a signed order or contract. If you're budgeting, 👉 [request a colocation quote from DMIT](https://bit.ly/DmiT) with your hardware list, power draw, bandwidth profile and preferred location, and their sales team puts together the specifics.

That's actually how most colocation deals work, not just DMIT's. Rack pricing depends heavily on how many amps you draw and which facility you're in, so a public price list would be misleading more often than helpful.

## Colocation vs cloud vs bare metal

People searching for colocation are often weighing it against two alternatives: renting cloud instances, or renting dedicated (bare metal) servers. The distinction is about who owns the hardware and what you manage.

|  | Colocation | Bare metal rental | Cloud instances |
| --- | --- | --- | --- |
| Who owns the hardware | You | Provider | Provider |
| Hardware choice | Fully yours, built to spec | Provider's stock, fully dedicated | Virtualised, shared host |
| Your responsibilities | Hardware + OS + everything above | OS and above | OS and above |
| Cost model | Facility fee + power + bandwidth, hardware is capex | Flat monthly rent | Pay-as-you-go |

Colocation tends to win when you have purpose-built or specialised servers, strict compliance or data-ownership requirements, or long-running workloads where owning hardware and paying facility fees beats perpetual rent. It also wins when you need a physical presence near specific carriers or exchanges — a network edge node is a classic use case.

Cloud wins when workloads are elastic, short-lived, or when you'd rather not think about hardware at all. A hybrid of the two is common: owned hardware in a facility for the steady baseline, cloud capacity on top for bursts and disaster recovery.

## Inside DMIT's three facilities

DMIT operates colocation out of three locations: Los Angeles, Hong Kong and Tokyo. All three are carrier-neutral facilities, which is the part that matters most for colocation — you're not locked into one carrier's network.

The Los Angeles presence spans two campuses, CoreSite and Digital Realty, with an aggregate of up to 3.8Tbps of connectivity to major Tier 1 carriers (the site notes this is maximum capacity under ideal conditions). The Hong Kong node sits inside Equinix HK2; the Tokyo node is at Equinix TY8 in Shinagawa. If you've read anything about data centres, those are familiar names — Equinix campuses are among the most interconnected buildings on the planet, which means cross-connect options are plentiful.

What stands out in DMIT's case is the routing angle. The Los Angeles network maintains direct, high-capacity peering with all three major Chinese carriers — China Telecom (AS4809), China Unicom (AS9929) and China Mobile International (AS58807) — plus premium China Telecom CN2 GIA transit on their premium network series. Reaching mainland China reliably from overseas is genuinely hard; standard routes get congested and lossy at peak hours. If your users are in China, colocating gear in a facility with engineered routes toward those carriers is one of the few legitimate fixes that doesn't involve hosting inside China itself.

The facilities themselves offer the checklist items you'd expect from a serious site, and DMIT publishes them explicitly:

- N+1 UPS with diesel generator backup, diverse utility feeds and A/B power
- Precision cooling with hot/cold aisle containment
- Tier III-class, audited facilities, with badge and biometric access control, 24/7 CCTV and on-site guards
- A **99.99% facility uptime SLA**
- Carrier-neutral fabric with cross-connects to carriers and IXes, and flexible port speeds and billing models

> Worth knowing: the 99.99% figure is the *facility* uptime SLA (power, cooling, physical access). The network service SLA is separate — DMIT's terms currently specify a 99% network SLA, with compensation tiers if it falls below that.

## What the process actually looks like

For anyone who hasn't colocated hardware before, the logistics are the intimidating part. Here's how DMIT describes the workflow, which is broadly typical of the industry:

1. **Quote.** You submit your hardware specs, power draw, bandwidth needs and location; sales returns a tailored plan and price.
2. **Ship.** You send your equipment to the facility. Their team receives it and runs an inventory check.
3. **Rack and stack.** Engineers rack the gear, run structured cabling, label everything, then handle power-on, BIOS/IPMI setup and testing — with photos and documentation sent back on completion. This service matters: you don't have to fly anyone out.
4. **Operate.** From then on, the 24/7 on-site team acts as your remote hands — reboots, reseating cards, part swaps, media handling, visual diagnostics, scheduled inspections and emergency response.

If you'd rather get a sense of their colocation setup before committing hardware, 👉 [browse DMIT's colocation details and talk to their team](https://bit.ly/DmiT).

## The fine print worth reading

A few things from DMIT's terms and product pages that a buyer should factor in honestly:

- **It's unmanaged.** DMIT states most services are unmanaged, with a 72-hour support ticket response guarantee. The remote-hands team handles physical tasks, but the OS, software and configuration are yours.
- **Refunds are time-boxed.** For new orders: a full refund is available within 3 days of purchase if you've used no more than 30GB of transfer; a partial refund is available within 30 days. Renewals and credit-funded invoices are non-refundable, and there's a list of non-refundable cases (DDoS targeting, network-quality complaints and the like).
- **Discount codes exist but have rules.** DMIT periodically releases promo codes, and their terms state these apply to new customers only — using a code not meant for you can result in suspension. Check what's currently on offer rather than relying on old codes found on coupon sites.
- **Public reviews are thin.** Their Trustpilot profile currently shows a low score (2.6) from only a handful of reviews — the sample is too small to say much either way, but it's a reminder to do your own diligence, especially for a colocation commitment, which is typically a longer-term relationship than a monthly VPS.

## If you don't actually want to own hardware: DMIT's cloud plans

Here's a confession many colocation shoppers arrive at: owning servers is a job. If your actual requirement is "reliable compute in a well-connected facility" rather than "my specific hardware in a specific building", renting instances in the same network is worth considering — same routing quality, none of the capex or hardware maintenance.

DMIT's pricing page currently lists the following cloud plans for Los Angeles on their Premium Network (CN2 GIA routing, AS3 hardware platform). All include free setup, one IPv4 plus IPv6, and basic DDoS protection:

| Plan | vCPU | RAM | Storage | Transfer | Port speed | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TINY | 1 | 2GB | 20GB SSD | 1000GB | 1Gbps | $10.90/mo | [Order TINY](https://bit.ly/DmiT) |
| Pocket | 2 | 2GB | 40GB SSD | 1500GB | 4Gbps | $16.90/mo | [Order Pocket](https://bit.ly/DmiT) |
| STARTER | 2 | 2GB | 80GB SSD | 3000GB | 10Gbps | $34.90/mo | [Order STARTER](https://bit.ly/DmiT) |
| MINI | 4 | 4GB | 80GB SSD | 5000GB | 10Gbps | $62.90/mo | [Order MINI](https://bit.ly/DmiT) |
| MICRO | 4 | 4GB | 160GB SSD | 7000GB | 10Gbps | $87.90/mo | [Order MICRO](https://bit.ly/DmiT) |
| MEDIUM | 6 | 8GB | 160GB SSD | 15000GB | 10Gbps | $199.90/mo | [Order MEDIUM](https://bit.ly/DmiT) |

Two caveats, straight from the source. DMIT notes the prices in their tables may not always be updated in real time, so treat these as reference figures and confirm at checkout. And the LAX AS3 platform is still being built out — the company warns of potentially reduced disk performance and a lower SLA on that platform while they tune it. Other locations (Hong Kong, Tokyo) and other network series (Eyeball, Tier 1) carry different pricing, configured through the same ordering flow. Backups are available starting at $0.45/GB per month if you want them handled in-platform.

To compare all locations and network series yourself, 👉 [check DMIT's current plan pages](https://bit.ly/DmiT).

## How to decide, quickly

Colocation makes sense if you tick most of these boxes:

- You already own hardware, or your workload needs hardware you can't rent off the shelf
- You need a physical presence near specific carriers, IXes or regions (DMIT's LAX/HKG/TYO footprint and China-optimised routing fit the Asia-Pacific case well)
- Your workloads are steady and long-running, so facility fees beat perpetual instance rental
- You're comfortable running an unmanaged environment, or have someone who is

If instead your traffic is bursty, your hardware needs are generic, and you'd rather not own anything — cloud or bare metal rental will be cheaper and less hassle. There's no prize for collocating out of principle.

For those in the first group, the next step is the same regardless of provider: put together a hardware list with power draw and bandwidth expectations, and get quotes. 👉 [Start a colocation enquiry with DMIT](https://bit.ly/DmiT) and see what their three facilities come back with — the quote costs you nothing but an email thread.
