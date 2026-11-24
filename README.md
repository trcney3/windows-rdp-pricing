# Cheapest Windows RDP: Is the $3.99 Headline Real, How Many Users Do You Get, and Which Plan Fits One Trader vs a Team? (Full Plan Table)

The cheapest Windows RDP plans advertise **$3.99 to $5.49 a month**, and the $3.99 one is a 180-day Microsoft evaluation license. Past day 180 the server shuts down every hour until you add a license at $6.31 per vCPU per month, which turns a 2-vCPU box into $16.61. Evoxt sells the same class of machine on a single flat price per VM: **$2.99/mo for the smallest, $5.99 for the 2 GB configuration that a Windows desktop can actually use**, weekly offsite backups included at no extra cost.

What follows is the full Evoxt plan list, the license arithmetic that the cheap landing pages leave out, the two-session ceiling that bites anyone sharing a box, and a per-scenario rule for picking a plan.

> **Most readers should take VM-1 at $5.99/mo** (1 core, 2 GB RAM, 20 GB storage, 500 GB transfer). Two gigabytes is the practical floor for Windows, and one core is enough for a single trader, a script runner or a remote office desktop. Teams of three or more should read the session-limit section before buying anything.
> 👉 [See Evoxt's current plan prices](https://bit.ly/EvoXt)

## Every Evoxt plan on the pricing page

Evoxt's lineup runs from 512 MB to 32 GB, all on the same high-clock CPU platform (the company advertises up to 6.0 GHz), all with a weekly offsite backup included and 250 GB to 5 TB of monthly transfer. Billing runs monthly up to three years, and you can add individual resources to a VM without switching plans.

| Plan | vCPU / RAM / Storage | Transfer | Price | Order |
| --- | --- | --- | --- | --- |
| VM-0.5 | 1 core / 512 MB / 5 GB | 250 GB | $2.99/mo | [ Order VM-0.5](https://bit.ly/EvoXt) |
| VM-0.75 | 1 core / 1 GB / 10 GB | 250 GB | $4.99/mo | [ Order VM-0.75](https://bit.ly/EvoXt) |
| VM-1 | 1 core / 2 GB / 20 GB | 500 GB | $5.99/mo | [ Order VM-1](https://bit.ly/EvoXt) |
| VM-1.5 | 2 cores / 2 GB / 20 GB | 500 GB | $6.95/mo | [ Order VM-1.5](https://bit.ly/EvoXt) |
| VM-2 | 2 cores / 4 GB / 30 GB | 1,000 GB | $11.99/mo | [ Order VM-2](https://bit.ly/EvoXt) |
| VM-3 | 4 cores / 4 GB / 30 GB | 1,000 GB | $14.99/mo | [ Order VM-3](https://bit.ly/EvoXt) |
| VM-4 | 4 cores / 8 GB / 60 GB | 2,000 GB | $23.99/mo | [ Order VM-4](https://bit.ly/EvoXt) |
| VM-6 | 8 cores / 8 GB / 60 GB | 2,000 GB | $29.99/mo | [ Order VM-6](https://bit.ly/EvoXt) |
| VM-8 | 8 cores / 16 GB / 80 GB | 3,000 GB | $47.99/mo | [ Order VM-8](https://bit.ly/EvoXt) |
| VM-12 | 16 cores / 16 GB / 80 GB | 3,000 GB | $60.95/mo | [ Order VM-12](https://bit.ly/EvoXt) |
| VM-16 | 16 cores / 32 GB / 100 GB | 5,000 GB | $95.99/mo | [ Order VM-16](https://bit.ly/EvoXt) |

Two things about that table matter more than the price column. First, the 512 MB and 1 GB entries exist because Linux runs fine there; Windows does not. Second, **20 GB of storage on VM-1 is tight for a Windows install plus updates**. Evoxt lets you bolt on extra storage as an add-on rather than jumping a whole tier, which is the cheaper fix.

Evoxt's Windows VPS page lists Windows RDP among the installable operating systems and shows this same plan lineup. The public pages do not spell out which Windows Server versions you get, whether the license is bundled into the plan price, or what the minimum RAM is for a Windows template. Those are questions for support before you pay, not after.

## What the "$3.99 Windows RDP" actually costs

The cheapest headline in this market comes from MassiveGRID, and the number is real: Windows Server from $3.99/mo on a 1 GB shared-vCPU box. It ships as Microsoft's 180-day evaluation build. It must be activated online within the first 10 days, the desktop counts down the days remaining, and after day 180 the machine keeps your data but **powers off every hour** and takes only security updates until a license is attached. The license costs $6.31 per vCPU per month, converted in place without a reinstall.

Run the arithmetic on a 2-vCPU box:

| What you pay for | Monthly |
| --- | --- |
| Base Windows VPS, evaluation license | $3.99 |
| License, 2 vCPU × $6.31 | $12.62 |
| **Effective total, licensed** | **$16.61** |
| Evoxt VM-2, same 2 cores / 4 GB class | $11.99 |

That gap is the single most useful fact in this category. A headline price and a sustainable price are two different numbers, and the difference on a 2-vCPU machine is roughly $12 a month, or $150 in the first year.

Desktop Windows works differently again. Microsoft does not let hosting providers rent out Windows 10 or 11 Pro licenses, so those templates install unactivated and you supply your own key. Windows 11 Pro also carries a 2 GB RAM minimum at most providers, which is why the cheapest genuinely usable Windows desktop plan tends to sit around $4.79 to $5.99 rather than $2.99. And **Windows 10 reached end of support on 14 October 2025**, so any host still steering you toward a Windows 10 template is selling you an unpatched desktop.

If Evoxt's Windows template turns out to be included in the plan price rather than billed as a separate line, VM-2 at $11.99 undercuts the equivalent licensed configuration above. Confirm that with support first, because it changes the math by about 30%.

👉 [Check the VM-2 price against your license quote](https://bit.ly/EvoXt)

## The two-session ceiling nobody puts on the pricing page

Windows Server ships with **two administrator RDP sessions**. That is fine for one person who occasionally opens a second connection from another device, and it is a wall the moment a third person needs in. Additional RDP user licenses run **$8.90 per user per month** at MassiveGRID.

A five-person team on a single box therefore pays the server price plus three extra user licenses: 3 × $8.90 = **$26.70/mo on top of the host**, which is more than the host itself in the cheap tiers. At that point the sensible move is a bigger VM with more RAM per session, or Windows Server with proper Remote Desktop Services licensing. If five people need a desktop, you are not shopping in the $5 tier any more, and no amount of plan comparison changes that.

Single-user setups skip all of this. A trader running MT4 or MT5, a marketer running a scraper, an accountant opening QuickBooks: one session, no extra licenses, and the two-session default is generous rather than limiting.

## Which plan for which job

**One trader, one bot, one script runner.** VM-1 at $5.99 with 2 GB. MetaTrader and most automation tools are single-threaded and latency-sensitive, not core-hungry, and Evoxt's pitch is high clock speed per core rather than core count. If you want a little headroom for backtests, VM-1.5 at $6.95 doubles the cores for 96 cents more.

**A remote office desktop with a browser and Office.** VM-2 at $11.99. Four gigabytes is where Chrome, Office and a chat client stop fighting each other, and 30 GB of storage leaves room for the Windows install plus a working set of files.

**Two to four people sharing one machine.** VM-4 at $23.99 gives 8 GB and 60 GB. Divide 8 GB by four users and you have 2 GB each, which is the minimum for a desktop session. Check the session licensing question above before you assume all four can log in at once.

**Anything with a database, an emulator farm or constant CPU load.** The 8-core VM-6 at $29.99 or VM-8 at $47.99, or move to a reserved-core product. MassiveGRID's dedicated-core Windows VPS starts at $18.84/mo, LightNode's 8 GB / 4 vCPU tier is $27.70/mo — Evoxt's VM-4 at $23.99 sits between them on price and closer to the dedicated tier on resources.

👉 [Start with the 2 GB VM-1 plan](https://bit.ly/EvoXt)

## How Evoxt compares with the other cheap RDP hosts

| Provider | Entry price | Entry configuration | What's bundled, what isn't |
| --- | --- | --- | --- |
| Evoxt | $2.99/mo | 1 core / 512 MB / 5 GB, 250 GB transfer | Weekly offsite backup on every VM; Windows licensing terms not published; no hourly billing |
| MassiveGRID | $3.99/mo | Windows Server, 1 GB shared vCPU | 180-day eval license, then $6.31/vCPU/mo; 2 admin sessions, extra users $8.90; 15-day refund; Windows 11 Pro from $4.79 |
| RDP.cheap | $4.99/mo | 2 cores / 4 GB / 40 GB, unlimited bandwidth | Dedicated IPv4, NVMe, KVM; page does not say whether a Windows license is included |
| BearHost | $5.49/mo | configuration table not published on the page | Full admin access, dedicated IP, 30-day money-back guarantee |
| LightNode | $7.71/mo or $0.012/hr | 1 vCPU / 2 GB / 50 GB NVMe / 1 TB | Hourly billing, 40+ locations, dedicated IP, two free IP changes |
| Liquid Web | $54/mo | general RDP VPS, 17% off at the time of that page | Managed support, automatic backups; this figure comes from a January 2025 page and is best treated as evidence that a premium tier exists |

RDP.cheap's $4.99 for 4 GB is the standout spec at that price, and the missing Windows license disclosure is the thing to resolve before ordering. LightNode is the one to pick if you want to rent by the hour and walk away after a weekend; Evoxt bills monthly upward, so a two-day experiment costs you a month. BearHost's 30-day money-back window is the most generous refund term in the group, and Evoxt does not publish a refund window on its pricing page at all — ask before you pay if that risk matters to you.

Two capability gaps are worth naming. Evoxt's feature list covers firewall rules, floating IPs, VM cloning, monitoring and a REST API, backed by 18 data centers across four continents per VPSBenchmarks' host profile. DDoS filtering is not part of that list, per the same profile, while RDP.cheap advertises up to 3.2 Tbps and MassiveGRID 12 Tbps. For a private desktop that difference rarely matters; for a public-facing box it does.

## Before you click order

- **Ask support which Windows versions are available on your plan and whether the license is included.** This is the one unknown that swings the real monthly cost by 30% or more.
- **Pick the location by ping, not by price.** A remote desktop stops feeling local above roughly 50 ms of latency. Test from where you actually sit, or from where your broker's servers sit if you are running trading bots.
- **Check the RAM floor against the Windows version.** 2 GB is the workable minimum for a desktop; Windows 11 Pro templates generally refuse to configure below it.
- **Do the storage math.** A Windows install plus a year of updates will eat most of a 20 GB disk. Evoxt sells storage as an add-on, which is cheaper than a full tier upgrade.
- **Payment methods:** cards, PayPal, Bitcoin and USDt Tron, with account credits you can draw down against future invoices.
- **No hourly billing.** If your need is measured in days rather than months, a monthly commitment is the wrong shape regardless of the price.

The decision rule, short version: one user, light workload, 2 GB is enough, take VM-1 at $5.99. One user with a browser and Office, take VM-2 at $11.99. Three or more people logging in at once, price the extra RDP user licenses before you compare host prices, because that line item usually decides the purchase.

👉 [Compare all Evoxt plans and pick your location](https://bit.ly/EvoXt)
