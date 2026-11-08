# Linux hosted server: VPS or bare metal, how much RAM your workload needs, and the costs the price tag hides (full plan table)

A Linux hosted server at SpinServers starts at **$45/month** for 8 vCPU and 8 GB of RAM on the KVM VPS line, and **$79/month** for a bare-metal Intel Xeon with 32 GB of RAM, 1 TB of NVMe storage and dual 10Gbps ports. Those two prices frame the whole decision: whether your workload needs its own hardware, or a guaranteed slice of someone else's.

Two numbers outside the headline price decide more cases than the CPU count does. First the monthly bandwidth quota, which runs from 8 TB on the entry VPS to 20 TB on the 32 vCPU plan. Second, whether the provider lets the box send mail at all: outbound port 25 is closed by default on every SpinServers VPS, and opening it requires a ticket plus a justification they can refuse.

Below is the full plan line-up, what $45 and $79 actually buy next to other providers' published prices, and the add-on charges that turn a cheap-looking monthly into a bigger one.

> **Quick pick.** The 8 vCPU / 8 GB KVM plan at $45/mo covers most production web apps, a mid-size database, or a Docker host with headroom. A static site or small blog does not need that; Virtua.cloud sells 1 vCPU / 1 GB at €5/mo and 1 vCPU / 2 GB at €12/mo. Running a database that needs guaranteed cores? Skip VPS and go bare metal at $79/mo.
>
> 👉 See the current SpinServers KVM VPS plans and pricing

## The full plan table

SpinServers splits its Linux hosted server range into two products. The KVM VPS line below is quoted per month, all plans include 1 IPv4 and 1 IPv6 address, a 1Gbps port and RAID-10 SSD storage.

| Plan | vCPU / RAM | Storage | Monthly bandwidth | Price |
| --- | --- | --- | --- | --- |
| Simple Application Server | 6 vCPU / 8 GB DDR4 | 120 GB RAID-10 SSD | 8 TB | Quoted at checkout |
| KVM 8 vCPU (featured) | 8 vCPU / 8 GB DDR4 | 160 GB RAID-10 SSD | 10 TB | **$45.00/mo** |
| KVM 12 vCPU | 12 vCPU / 12 GB DDR4 | 160 GB RAID-10 SSD | 10 TB | Quoted at checkout |
| Advanced 16 vCPU (Xeon) | 16 vCPU / 16 GB DDR4 | 320 GB RAID-10 SSD | 15 TB | Quoted at checkout |
| Advanced 32 vCPU (Xeon) | 32 vCPU / 32 GB | 500 GB SSD | 20 TB | Quoted at checkout |

The 8 vCPU plan is the only tier with a price shown on the product page. The rest are quoted at checkout, and availability moves with stock, so treat that column as "confirm before you budget" rather than a fixed number. [👉 Check the 8 vCPU plan's current price](https://bit.ly/Spinservers)

Above the VPS line sits bare metal, which is a different product with a different billing model: month to month, no setup fee, provisioned in about 30 minutes on in-stock configurations. Published reviews of the dedicated catalogue from October 2026 put the entry machine here:

| Machine | Cores / RAM | Storage | Bandwidth | Price |
| --- | --- | --- | --- | --- |
| Intel Xeon E3-1280 v5 | 4c/8t, 32 GB | 1 TB NVMe SSD | 30 TB, 2×10Gbps | **$79/mo** |

Higher tiers scale into multi-socket territory, with 20-core Xeon Gold parts around $99/mo and quad-socket machines with 1.5 TB of RAM above $1,000/mo. Those figures come from third-party reviews, not from a page I could verify line by line, and reviewers note pricing shifts with location and stock. Dallas and San Jose are the two locations named in the reviews.

## What the $45 and $79 price tags leave out

Add-on charges are where monthly budgets quietly break. None of the examples below are SpinServers prices; they are what other hosts publish, and they show the categories you should ask about before paying.

**Extra IP addresses.** Atlantic.Net includes one IPv4 with every server and charges **$3.65/month** for each additional one. If you run separate TLS-terminated sites, or need a second IP for a migration, that line item repeats every month.

**Domain and certificate.** DigitalOcean states plainly that it provides no free domain and no free SSL certificate. You bring a commercial certificate or install Let's Encrypt yourself. SpinServers gives you one IPv4 and one IPv6 with each VPS, which covers the address side but not the certificate.

**"Included value" that isn't a discount.** InMotion Hosting lists Launch Assist onboarding and server setup as a **€187.99 one-time value** bundled with its VPS plans. It may well save you an afternoon, but it does not reduce the monthly rate, and you should not count it as money off.

**Bandwidth overage.** The SpinServers VPS quota steps from 8 TB to 10 TB to 15 TB to 20 TB as you move up the range. Ask what happens past the cap before you pick the cheapest tier for a video-heavy or backup-heavy workload.

**Outbound mail.** Port 25 is closed by default across the VPS range. If your application sends password resets or invoices directly from the server, plan on a ticket, a justification, and the possibility of a no. Route mail through a transactional provider instead and the restriction stops mattering.

## First-term price versus renewal price

Introductory pricing is the single most common source of surprise, and InMotion Hosting's public page is the clearest example in this batch of research because it shows both numbers side by side on a 24-month term.

| Plan | First term | Renewal | Multiple |
| --- | --- | --- | --- |
| VPS 8 vCPU | €19.32/mo | €45.43/mo | ~2.35× |
| VPS 16 vCPU | €38.67/mo | €108.26/mo | ~2.8× |

Over 24 months the 8 vCPU plan bills €463.68, then jumps to €545.16 for the following year at the renewal rate. The 16 vCPU plan goes from €928.08 across the first term to €1,299.12 in year three. These are InMotion's numbers, quoted to show how steep the gap can get, not a claim about SpinServers' pricing. SpinServers bills month to month on its dedicated line, which removes the multi-year lock-in but also means you should confirm the recurring rate in writing before ordering either product.

A month-to-month contract also changes the refund question. A review of the dedicated line notes that month-to-month services generally carry no refund policy. If you are testing a migration, budget for one month as the cost of finding out, and keep production on the old host until the new box has proven itself.

## How much server your workload actually needs

Spec floors matter more than brand loyalty at this stage. The reference prices below come from Virtua.cloud's published VPS tiers, which line up cleanly with workload types:

- **Static site, landing page, small blog:** 1 vCPU / 1 GB (€5/mo) is enough. 1 vCPU / 2 GB (€12/mo) if you run a CMS with plugins.
- **WordPress, small web app, API:** 2 vCPU / 4 GB (€24/mo) is the usual landing spot.
- **Production app with a database, or a Docker host running several containers:** 4 vCPU / 8 GB (€48/mo) and up.
- **Workloads that need cores nobody else can touch:** DigitalOcean's General Purpose Droplets, which reserve dedicated CPU, start at **$63/mo**. Atlantic.Net's Dedicated Cloud Host does the same thing at the physical-node level.

SpinServers' 6 vCPU / 8 GB entry plan carries more CPU than a typical small site needs and less RAM than a database server wants. That shape suits container hosts and multi-site setups. A single WordPress install with modest traffic will sit idle on it.

The difference between VPS and bare metal is resource reservation, and Atlantic.Net explains it better than most: shared hosting gives you unreserved resources, a dedicated server gives you 100% of the machine, and a VPS sits between them, sharing hardware but guaranteeing the allocated slice. A VPS with 200 GB of storage and 64 GB of RAM keeps those resources regardless of what other tenants do. Bare metal at $79 removes the shared layer entirely, which is why the price per core looks worse and the price per guaranteed core looks better.

## Managed or self-managed

Neither SpinServers product is a managed service. You get root access and you own the configuration. That is either the point or a dealbreaker.

For contrast, HosterDaddy's fully managed scope covers control panel installation, Linux hardening, CSF firewall setup, kernel patch updates, database optimisation, malware detection and removal, and migration. DigitalOcean sits at the opposite end: extensive documentation and tutorials, no one logging into your server for you.

Pick managed hosting if you do not want to own kernel patching. Pick self-managed if you already automate patching and would rather spend the difference on RAM. The middle ground, unmanaged server plus a control panel, works for people who want a GUI for sites and mail but no ticket queue: cPanel runs on CentOS, Plesk supports CentOS, Debian and Ubuntu. Confirm which images your chosen host actually offers at order time, since catalogue pages change.

## Who should not buy this

- **You want shared hosting.** If a $5 plan with a control panel covers a five-page site, nothing here is aimed at you.
- **You will not use a command line.** Managing a Linux server means SSH, package managers, and editing config files. Every host in this comparison assumes that.
- **You need Windows or a .NET stack.** SpinServers does list Windows and ESXi auto-install on the dedicated side, but the VPS line is a Linux product, and Windows licensing changes the maths.
- **You need a large IPv6 block or mail sending out of the box.** One IPv6 address is included per VPS, and port 25 is closed by default.

## FAQ

**Which Linux distribution should I pick?**
Ubuntu ships a new release every six months and a long-term support release every two years, which is why it dominates server images. Debian sits upstream of Ubuntu, so its architecture shapes what Ubuntu ships, and it carries less commercial support. Both appear on essentially every host's image list. Confirm the exact versions offered at checkout rather than assuming.

**Is a VPS as fast as a dedicated server?**
For bursty web traffic, usually yes. For sustained database write loads, no: a VPS shares the underlying hardware even when its CPU and RAM allocation is guaranteed. That is the gap the $79 bare-metal entry point closes.

**Do I need a control panel?**
Only if you want a browser interface for sites, mail and databases. It adds a licence cost and a patching surface. Command-line administration plus a config management tool covers the same ground for free.

**What happens if I outgrow the plan?**
On the VPS line you move up a tier; the range tops out at 32 vCPU and 32 GB, so a workload beyond that belongs on the dedicated catalogue. Plan the migration path before you commit to a platform, not after.

## The bottom line

Match the machine to the job and the rest gets simple:

- **One small site or a staging box** → 1–2 GB VPS. Do not pay for 8 vCPU.
- **Several apps, containers, or a busy CMS** → 8 vCPU / 8 GB at $45/mo, the best-value point in the SpinServers range.
- **A database or anything needing guaranteed cores** → bare metal from $79/mo with dual 10Gbps.
- **You want someone else to patch the kernel** → a managed host, not this.

Before you pay, confirm three things in writing: the recurring rate after any introductory term, the bandwidth overage policy above your quota, and whether outbound port 25 will be opened for your use case.

👉 [View the SpinServers KVM VPS plans and start an order](https://bit.ly/Spinservers)
