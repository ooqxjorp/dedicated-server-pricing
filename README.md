# Cheap dedicated server: what $50 really buys, which fees land after the headline price, and how to pick a config by workload (SpinServers plan table plus a four-provider price check)

US bare metal now starts around $44 a month, and European listings go as low as €4.99. Those numbers rarely survive to the invoice, because installation fees, VAT and control-panel licences get billed on top of the monthly rate.

SpinServers sits higher up that band and is the easier call for most people reading this: **$79/mo** in Dallas buys 4 cores, 32GB DDR4 ECC, a 1TB M.2 NVMe disk and 30TB of traffic on a 10Gbps port, with automatic provisioning. Below is what that price includes and leaves out, why the $44 tier is built from DDR3 and spinning disks, and how to decide which one you actually need.

> **Quick pick for most readers:** the Dallas **Xeon E3-1280 v5 at $79/mo** — 4 cores/8 threads at 3.7GHz turbo, 32GB DDR4 ECC, 1TB M.2 NVMe, 30TB/month on a 10Gbps port, one IPv4, auto-provisions on payment. Enough for a busy WordPress site, a game server, a CI runner or a VPN/egress box, without the DDR3-and-HDD compromises of the sub-$50 tier. 👉 [Check the $79 Dallas configuration](https://bit.ly/Spinservers)

## The SpinServers lineup: Dallas and San Jose

SpinServers runs two US locations. Dallas, Texas carries the priced preconfigured stock; San Jose, California lists higher-core machines on dual 10Gbps ports, most of them marked for instant provisioning.

**Dallas, TX**

| Plan | CPU | RAM / storage | Price (USD) | Order |
| --- | --- | --- | --- | --- |
| Xeon E3-1280 v5 | 4c/8t, 3.7GHz turbo | 32GB DDR4 ECC / 1TB M.2 NVMe | from **$79/mo** | [Order the E3-1280 v5](https://bit.ly/Spinservers) |
| Dual Xeon E5-2630L v3 | 16c/32t, 2.9GHz turbo | 128GB DDR4 ECC / 1TB NVMe | shown at order | [Order the dual E5-2630L v3](https://bit.ly/Spinservers) |
| Dual Xeon Gold 6148 | 40c/80t, 3.7GHz turbo | 256GB DDR4 / 2×1.92TB SSD | from **$235/mo** | [Order the dual Gold 6148](https://bit.ly/Spinservers) |
| Dual Xeon Platinum 8173M | 56c/112t, 3.5GHz turbo | 512GB DDR4 / 4×1.92TB SSD | from **$390/mo** | [Order the dual Platinum 8173M](https://bit.ly/Spinservers) |

All four include 30TB of monthly transfer over 10Gbps; the Gold and Platinum machines carry two 10Gbps ports in LACP. SpinServers groups these as "from" prices, so the dual E5-2630L v3 with 128GB sits between the $79 and $235 groups and its exact figure appears on the order page rather than the listing.

**San Jose, CA** — configurations listed, price confirmed per machine at order:

| CPU | RAM | Storage | Network |
| --- | --- | --- | --- |
| 12c/24t, 2.6–3.1GHz | 64GB DDR3 ECC | 1×240GB SSD | 2×10Gbps, 30TB |
| 4c/8t, 3.7–4.0GHz | 32GB DDR4 ECC | 1×1TB M.2 NVMe | 2×10Gbps, 30TB |
| 16c/32t, 1.8–2.9GHz | 64GB DDR4 ECC | 1×1.6TB SSD or 1.6TB NVMe | 2×10Gbps, 30TB |
| 24c/48t, 1.8–2.5GHz | 64GB DDR4 ECC | 1×1.6TB SSD | 2×10Gbps, 30TB |
| 16c/32t, 1.8–2.9GHz | 256GB DDR4 ECC | 2×1.6TB SSD, hardware RAID | 2×10Gbps, 30TB |
| 32c/64t, 2.1–3.0GHz | 512GB DDR4 ECC | 2×3.84TB SSD, RAID + battery cache | 2×10Gbps, 30TB |

The 12-core San Jose box is the one to read carefully: 64GB of DDR3 is a lot of memory on a last-generation platform, and for a database the 4-core E3-1280 v5 with DDR4 and NVMe will often finish queries sooner.

## Why "starting at" prices can't be ranked against each other

The cheapest advertised numbers describe very different machines, and in two cases they aren't even the machines you can buy today.

Scaleway's €4.99/month Start-2-S-SSD is an Intel C2350: two cores at 1.7GHz, 4GB of RAM, one 120GB SSD. That's a DNS or backup node, not a web server. The next step up, €19.99/month, is a Xeon E3-1220v2 with 16GB and two 1TB hard drives capped at 200Mbps. OVHcloud's Eco range opens at £8.89 ex VAT with a 120GB disk and 500Mbps public bandwidth, and every configuration pairs its monthly rate with an installation fee of the same amount. Dedicated.com advertises "starting at $35.75/mo", yet the lowest monthly configuration visible on the page is $43.99: a Xeon E3-1230v2 with 8GB of DDR3 and two 2TB hard drives, in Los Angeles, with two units left. Several other cheap configurations are marked sold out everywhere. HostFinch quotes a $49.75 floor across 17 configurations under $120.

Put next to those, SpinServers' $79 entry is not the cheapest number on the page and is the cheapest machine most people would actually keep. You get four cores of DDR4-era Xeon, an NVMe system disk and a 10Gbps port with 30TB attached. The $44 boxes give you DDR3, hard drives and 1Gbps.

## Three charges that appear after the headline price

**Installation fees.** OVHcloud charges one month's rent as a setup fee on the Eco configurations it displays: £15.19 ex VAT per month with a £15.19 ex VAT installation fee, £48.99 with £48.99. On the £15.19 plan that makes the first 12 months £197.47 ex VAT rather than £182.28. Dedicated.com advertises free setup on every term, and HostFinch charges none. On SpinServers, read the order summary rather than the listing, since the amount due is confirmed at checkout.

**VAT.** OVHcloud's UK pages print both figures side by side: £15.19 ex VAT or £18.23 incl. VAT, £48.99 ex VAT or £58.79 incl. VAT. That's roughly 20% on top, and it applies to the installation fee too. If you're comparing a GBP ex-VAT price with a USD price, you're comparing two different things.

**Control-panel licences.** HostFinch sells LiteSpeed at $38.99/mo for one CPU, $48.99 for two, $66.99 for four and $88.99 for eight; Nginx with cPanel is $69.99/mo. A $49.75 server plus a four-CPU LiteSpeed licence comes to $116.74 a month. If you're running a single site behind Nginx or Caddy, none of this applies. If you're migrating a cPanel estate, budget for it before you compare server prices.

👉 [See the SpinServers server list and the total due at checkout](https://bit.ly/Spinservers)

## Prepay discounts, in actual dollars

Dedicated.com discounts prepayment at 3% for three months, 6% for six and 12% for twelve. On the $55.99 configuration, twelve months prepaid is $591.25 against $671.88 paid monthly, a saving of $80.63. On the $183.99 machine, $1,942.93 against $2,207.88, a saving of $264.95. Real money, and the percentage is displayed next to each option so you don't have to work it out.

Scaleway takes the other approach: the price you see is already the commitment price. The Ryzen 5 PRO 3600 with 32GB and 2×1TB NVMe at €33.99/month assumes 36 months, and the company advertises up to 15% off for locking in. That's a fine deal if the machine is still the right one in year three. Moving off a committed box after eight months costs more than the discount returns, so check what a migration would involve before you sign a multi-year term on any provider.

## Choosing a configuration by workload

**Clock speed beats core count for single-threaded work.** Game servers, PHP-FPM WordPress, Node apps and CI jobs spend most of their time on one or two threads. The 4-core E3-1280 v5 at 3.7GHz turbo will outperform a 16-core E5-2630L v3 at 2.9GHz on those loads, at a third of the price.

**Cores matter when you're splitting the machine up.** Proxmox, Docker hosts with many services, database servers under concurrent load and batch processing all want the 16c/32t E5-2630L v3 or the 40c/80t Gold 6148. The Gold also brings two 10Gbps ports in LACP, which matters if you're pushing more than a single gigabit of sustained traffic.

**Memory: 32–64GB covers most sites and game servers.** Move to 128GB or more when you're running large databases, a stack of virtual machines, or in-memory caches that need to stay resident. Above 256GB you're into the San Jose 512GB machine or the Platinum 8173M.

**Disk: NVMe for anything with a write path.** Databases, application servers and mail stores benefit from NVMe directly. SATA SSD and spinning disks are cheaper per terabyte and fine for backups and archives. Whatever you choose, run RAID 1 or RAID 10 on a production box, which is why the higher San Jose configurations ship with hardware RAID controllers and battery-backed cache.

## Stock, delivery and what "instant" means

Dedicated.com's page shows 43 configurations with 37 in stock, and a good number of the cheap ones flagged as sold out everywhere, with the remainder down to two or six units per location. HostFinch delivers most in-stock servers within 1 to 24 hours, some within 1 to 12, and emails the IP, root password and IPMI/KVM details. SpinServers lists the Dallas machines as "ready to go, auto-provisions" and the San Jose ones as instant provisioning.

The practical upshot: the configuration you want may not be available the day you want it. Order the machine you need for the next 12 months rather than the cheapest one that happens to be in stock, and if you're on a deadline, buy a week early.

## Who should stay on a VPS

If your site fits in under 8–16GB of RAM and you're not virtualising anything, a dedicated server is a fixed cost you don't need. HostFinch's VPS plans start at $7.99/month, and $79/month works out to $948 a year for a machine that sits mostly idle. The break-even is roughly where your VPS bill and your noisy-neighbour complaints both start climbing: sustained CPU contention, more than 16GB of RAM, or a workload that needs its own kernel and IPMI console.

## How the four cheapest-looking providers compare

| Provider | Entry configuration | Price | Term and extras |
| --- | --- | --- | --- |
| Scaleway | Start-2-S-SSD: Intel C2350, 2C/2T, 4GB, 1×120GB SSD, up to 1Gbps | €4.99/mo | Rolling; Start-1-L (E3-1220v2, 16GB, 2×1TB HDD, 200Mbps) at €19.99/mo |
| OVHcloud | Eco range, Xeon E5 v2 through Epyc 7451, 16GB–256GB, 120GB–12TB | £8.89–£55+ ex VAT/mo | Installation fee equal to first month; 300–500Mbps public bandwidth, no private bandwidth |
| Dedicated.com | Xeon E3-1230v2, 8GB DDR3, 2×2TB HDD (Los Angeles) | $43.99/mo | Free setup on all terms, IPMI, /29 with 5 usable IPv4, DDoS filter, 3/6/12% prepay |
| HostFinch | 17 configs at or below $120/mo, Xeon E3/D, Core i5-13500, Ryzen 7 7700, EPYC 4244P | from $49.75/mo | No setup fee, unmetered at 500Mbps–3Gbps, 1–24h delivery |

The pattern is consistent: the sub-$50 tier is DDR3 or small-disk hardware on a 200Mbps–1Gbps port, the $79 tier gets you DDR4, NVMe and 10Gbps, and everything above $230 buys cores and memory rather than speed.

## FAQ

**Are cheap dedicated servers second-hand hardware?** HostFinch states directly that its lower prices come from older-generation or lower-core CPUs and smaller storage. You're renting a previous-generation platform, not a refurbished consumer desktop. The spec sheet tells you which: DDR3 instead of DDR4, a 120–240GB boot disk, 1Gbps instead of 10Gbps.

**Is there a setup fee?** It varies by provider. OVHcloud charges one equal to the first month on the Eco configurations shown. Dedicated.com advertises free setup on every term and HostFinch charges none. Check the order total before paying, since setup fees are invoiced once and then disappear from the monthly figure you'll compare later.

**Can I install Windows or Proxmox?** HostFinch installs Ubuntu, Debian, AlmaLinux, Rocky Linux, Proxmox and Windows Server free, and you can reinstall through IPMI/KVM yourself. If a specific template or Windows licence matters for your workload, confirm it with support before ordering, whichever provider you use.

**What happens if I go over the traffic allowance?** SpinServers includes 30TB per month on a 10Gbps port; overage pricing isn't shown on the server listings, so ask before you commit a bandwidth-heavy workload. Port-capped "unmetered" plans bill nothing extra but limit the rate instead, at 500Mbps to 3Gbps depending on the machine.

**Can I get a refund or a trial?** None of the providers here publish a trial or money-back window on dedicated stock. Monthly billing is the only real escape hatch: run month to month for the first two or three months, watch the disk and network, then prepay once you know the machine is right.

## What to order

Under 16GB of RAM, one low-traffic site, no virtualisation: stay on a VPS at $7.99–$20/month.

One busy site, a game server, a CI runner or an egress box with a 32GB working set: the Dallas Xeon E3-1280 v5 at $79/mo, where the NVMe disk and 10Gbps port do more for you than extra cores would.

Proxmox, a database with a working set north of 100GB, or parallel batch jobs: the dual E5-2630L v3 with 128GB, and step up to the dual Gold 6148 if you also need the LACP pair and 40 cores.

Two things to confirm before you pay: that the exact configuration is in stock in the location you want, and whether IPMI/KVM access and OS reinstalls are included in the price you're looking at. Both change what the monthly number is worth more than a $10 difference in rent.

👉 [Start with the $79 Dallas configuration](https://bit.ly/Spinservers)
