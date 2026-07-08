# mvp-sudojohnny-tools

> A hand-picked, opinionated list of tools I actually reach for — across cybersecurity, IT infrastructure, full-stack dev, compliance, and macOS power-user life. Not a 5,000-link dump. Just the good stuff.
>
> Companion list for **[sudojohnny.com](https://sudojohnny.com)** · maintained by **[@jshepjr](https://github.com/jshepjr)**

---

## About

I'm a full-stack developer and IT/security consultant working across healthcare IT, compliance (HIPAA, NIST CSF), and infrastructure deployment. This list is what I keep bookmarked, scripted, or running on a daily basis.

Tools are grouped by what I use them **for**, not by what kind of tool they are. Each entry gets one line. If I had to write a paragraph to justify it, it's not on the list.

---

## Table of Contents

- [Runbooks](#runbooks)
- [Cool Apps](#cool-apps)
- [OSINT & Recon](#osint--recon)
- [Exposure Discovery](#exposure-discovery)
- [Offensive Security](#offensive-security)
- [AI Hacking Agents](#ai-hacking-agents)
- [Defensive & Blue Team](#defensive--blue-team)
- [Compliance & GRC](#compliance--grc)
- [Networking & Sysadmin](#networking--sysadmin)
- [macOS Power Tools](#macos-power-tools)
- [Dev & Full-Stack](#dev--full-stack)
- [Books, Cheat Sheets & Learning](#books-cheat-sheets--learning)
- [Source Repos](#source-repos)

---

## Runbooks

Field-tested playbooks for when something is on fire — or about to be. Living documents; PRs welcome.

- **[Cybersecurity Incident Response](./runbooks/cybersecurity-incident-response.md)** — Universal IR playbook covering the full NIST 800-61r2 lifecycle, plus scenario quick plays for ransomware, BEC, malware, phishing, data exfiltration, DDoS, lost devices, and web-app compromise. Time-to-first-action under 30 minutes for every scenario.
- **[Compliance Runbook](./runbooks/compliance-runbook.md)** — Cross-framework reference for HIPAA, HITECH, NIST CSF 2.0, NIST 800-53, NIST 800-171/CMMC, SOC 2, PCI DSS, GDPR, and CCPA. Includes control mappings, audit-prep checklists, an annual compliance calendar, and the most common findings to avoid.

See the [runbooks index](./runbooks/) for the full list.

---

## Cool Apps

Native apps with icons — the things that earn dock, menu-bar, and home-screen space. Different list from the command-line tools below.

See **[apps.md](./apps.md)** for the full list. ~180 apps tagged with platform badges (🍎 macOS · 📱 iOS · 🪟 Windows · 🐧 Linux · 🔌 Web · 🤖 Android) and price tier (Free · OSS · Freemium · one-time · subscription). Covers IT & sysadmin, security & privacy, productivity, notes & reading, files & backup, menu-bar utilities, Windows power tools, on-call mobile IT, dev & code, media, comms, finance, learning, and a "just cool" section.

---

## OSINT & Recon

Open-source intelligence and reconnaissance — the "know before you knock" layer.

- [Maigret](https://github.com/soxoj/maigret) — Username search across 3000+ sites, no API keys.
- [SpiderFoot](https://github.com/smicallef/spiderfoot) — Automated OSINT with 200+ modules; my go-to for first-pass investigations.
- [theHarvester](https://github.com/laramies/theHarvester) — Email, subdomain, and host gathering from public sources.
- [Amass](https://github.com/owasp-amass/amass) — OWASP's deep subdomain enumeration; the gold standard.
- [Subfinder](https://github.com/projectdiscovery/subfinder) — Fast passive subdomain discovery, scriptable.
- [httpx](https://github.com/projectdiscovery/httpx) — HTTP toolkit for probing live hosts at scale.
- [nuclei](https://github.com/projectdiscovery/nuclei) — Template-based vulnerability scanner; pairs perfectly with httpx.
- [Holehe](https://github.com/megadose/holehe) — Check if an email is registered on 100+ sites.
- [Sherlock](https://github.com/sherlock-project/sherlock) — Hunt social-media accounts by username.
- [TruffleHog](https://github.com/trufflesecurity/trufflehog) — Find leaked credentials in git history, S3, and more.
- [Gitleaks](https://github.com/gitleaks/gitleaks) — Pre-commit secret scanning; runs in CI cleanly.
- [dnstwist](https://github.com/elceef/dnstwist) — Domain typo-squat / phishing-domain detector.
- [Shodan CLI](https://github.com/achillean/shodan-python) — Query Shodan from the terminal.
- [waybackurls](https://github.com/tomnomnom/waybackurls) — Pull historical URLs from the Wayback Machine.

### Web-Based OSINT Services

No install, no API key — just open a tab and dig.

- [Shodan](https://www.shodan.io) — Search engine for internet-connected devices; find exposed services, ICS, cameras, and misconfigured hosts.
- [VirusTotal](https://www.virustotal.com/gui/home/upload) — Upload a file, hash, URL, or IP and check it against 70+ AV engines and threat-intel feeds.
- [Have I Been Pwned](https://haveibeenpwned.com) — Check if an email or password has appeared in a known data breach.
- [Wayback Machine](https://web.archive.org) — Internet Archive snapshots; recover deleted pages and track how a site has changed over time.
- [WiGLE](https://wigle.net) — Crowdsourced map of Wi-Fi networks and cell towers worldwide; useful for wireless recon and geolocation.
- [OSINT Industries](https://www.osint.industries) — Reverse-lookup engine: feed it an email or phone, get back linked accounts across 600+ platforms.
- [Insecam](https://www.insecam.org) — Directory of unsecured/public IP cameras worldwide; cautionary tale on default credentials and exposure.

## Exposure Discovery

Finding the files, buckets, repos, and infrastructure that *shouldn't* be public but already are. The "what would a curious outsider stumble across?" layer — use it on your own org before someone else does. Inspired by [Applied Awareness — *Finding Public Files That Probably Shouldn't Be Public*](https://appliedawareness.ca/finding-public-files-that-probably-shouldnt-be-public/).

### Dorking & Search Operators

- [DorkSearch](https://dorksearch.com/) — Pre-built Google dork templates; pick a category and go.
- [OneDorkForAll](https://github.com/HackShiv/OneDorkForAll/tree/main/dorks) — Big curated dork pack organized by target type.
- [Gh0st D0rk Killer](https://github.com/theGh0stfaceKiller/Gh0st_D0rk_Killer) — Automated dork runner with rotating proxies.
- [Deep Dork Web](https://guilherme-moraiss.github.io/Deep-Dork-Web/) — Browseable dork catalog with live links.
- [DorkTerm](https://yogsec.github.io/DorkTerm/) — Terminal-style dork builder UI.
- [OSINT-CSE](https://github.com/paulpogoda/OSINT-CSE) — Google Custom Search Engines tuned for OSINT.
- [One-Liner-OSINT](https://github.com/yogsec/One-Liner-OSINT) — Single-line dork recipes you can paste straight into a search bar.
- [Dorks Collections List](https://github.com/cipher387/Dorks-collections-list) — Meta-list of dork repos worth crawling.

### Alternative Search Engines

Google indexes the most, but it's not always the right tool. Different engines surface different corners of the web.

- [DuckDuckGo](https://duckduckgo.com) — Better than Google for forums, Telegram channels, and content Google demotes.
- [Yandex](https://yandex.com) — Best coverage of Russian-language and reverse-image-search results.
- [Baidu](https://www.baidu.com) — China-region coverage Google can't match.
- [eTools Meta Search](https://www.etools.ch/) — Privacy-friendly meta-search across 16+ engines.
- [AllTheInternet](https://www.alltheinternet.com/) — Quick switch between dozens of search engines on one page.
- [IntelTechniques Search Tools](https://inteltechniques.com/tools/Search.html) — Michael Bazzell's hand-built OSINT search forms.
- [Search Engines With Own Indexes](https://seirdy.one/posts/2021/03/10/search-engines-with-own-indexes/) — Curated list of engines that aren't just Google/Bing wrappers.
- [Search Engine Colossus](https://www.searchenginecolossus.com/) — International directory of country-specific search engines.
- [SearchTweaks](https://searchtweaks.com/) — Power-user URL hacks for tuning the major engines.

### Exposed Infrastructure & Certificate Search

- [Censys](https://search.censys.io/) — Shodan's serious cousin; deep cert + host data with great filtering.
- [PublicWWW](https://publicwww.com/) — Search the source code of the entire web; great for finding reused analytics IDs and shared dev fingerprints.
- [crt.sh](https://crt.sh/) — Free certificate-transparency log search; the fastest way to map a domain's subdomains.
- [ZoomEye](https://www.zoomeye.org/) — China-based Shodan alternative; surfaces hosts the others miss.
- [FOFA](https://fofa.info/) — Cyberspace mapping engine; strong on regional infrastructure.
- [LeakIX](https://leakix.net/) — Indexes exposed services *and* leaked data on them.
- [Netlas](https://netlas.io/) — Internet-scan search with a generous free tier.
- [Onyphe](https://search.onyphe.io/) — Cyber-defense search engine; threat-intel slant.
- [GreyNoise](https://www.greynoise.io/) — Tells you which IPs are background internet noise vs targeted at *you*.
- [WhoXY](https://www.whoxy.com/) — Historical and reverse WHOIS; pivot from a domain to everything its owner registered.
- [BuiltWith](https://builtwith.com/) — Tech-stack fingerprinting; what a site runs and what it used to run.
- [Wappalyzer](https://www.wappalyzer.com/) — Same idea, browser extension or API.
- [DNSDumpster](https://dnsdumpster.com/) — Free DNS recon with a clean visual map.
- [SecurityTrails](https://securitytrails.com/) — Historical DNS + WHOIS data; great for tracking infrastructure changes.
- [ViewDNS](https://viewdns.info/) — 30+ free DNS tools on one page.
- [URLScan](https://urlscan.io/) — Submit a URL, get a full scan and a public history of what that URL has served.

### Cloud Buckets & Object Storage

- [Open Buckets](https://openbuckets.io/) — Search engine for publicly exposed S3/Azure/GCP buckets.
- [GreyHat Warfare](https://buckets.grayhatwarfare.com/) — The OG bucket search; also has the best shortened-URL search around.
- [OSINT.Sh Buckets](https://osint.sh/buckets/) — Free bucket lookup with name-pattern matching.
- [SOCRadar BlueBleed](https://socradar.io/labs/bluebleed/) — Check whether your domain showed up in known bucket-leak datasets.
- [AWSBucketDump](https://github.com/jordanpotti/AWSBucketDump) — Brute-force S3 bucket names from a wordlist and dump what's open.
- [S3Scanner](https://github.com/sa7mon/S3Scanner) — Multi-provider bucket enumerator and permission auditor.
- [CloudBrute](https://github.com/0xsha/CloudBrute) — Discover buckets, apps, and storage across AWS, Azure, GCP, and more.

### File Metadata

- [ExifTool](https://exiftool.org/) — The universal metadata reader/writer; pulls EXIF, GPS, author, and software fingerprints out of nearly any file.
- [Metagoofil](https://github.com/laramies/metagoofil) — Harvests metadata from public documents indexed for a target domain.
- [No Nonsense Intel — Adverse Media](https://www.no-nonsense-intel.com/adverse-media-search-tool) — Adverse-media search tool useful when the "public file" you're hunting is a news mention.

## Offensive Security

Red-team and pentest tooling I trust. Use only on systems you own or have written authorization for.

- [Nmap](https://nmap.org/) — The network scanner. Still unbeaten after 25+ years.
- [Masscan](https://github.com/robertdavidgraham/masscan) — Internet-scale port scanner; pair with Nmap for service detection.
- [RustScan](https://github.com/RustScan/RustScan) — Modern Nmap front-end; ridiculously fast.
- [Metasploit Framework](https://github.com/rapid7/metasploit-framework) — The exploit dev and post-ex platform.
- [sqlmap](https://github.com/sqlmapproject/sqlmap) — Automated SQL-injection detection and exploitation.
- [Burp Suite Community](https://portswigger.net/burp/communitydownload) — Web app pentesting; the standard.
- [OWASP ZAP](https://www.zaproxy.org/) — Free Burp alternative, scriptable.
- [Hashcat](https://github.com/hashcat/hashcat) — GPU password recovery; the fastest cracker out there.
- [John the Ripper](https://github.com/openwall/john) — Classic password cracker; still useful for weird hash types.
- [Hydra](https://github.com/vanhauser-thc/thc-hydra) — Network-protocol brute forcer.
- [Bettercap](https://github.com/bettercap/bettercap) — Swiss-army knife for network/MITM attacks.
- [Aircrack-ng](https://github.com/aircrack-ng/aircrack-ng) — Wi-Fi auditing suite.
- [Evilginx2](https://github.com/kgretzky/evilginx2) — MITM phishing framework (red-team training).
- [Responder](https://github.com/lgandx/Responder) — LLMNR / NBT-NS / mDNS poisoner; staple for AD pentests.
- [BloodHound](https://github.com/BloodHoundAD/BloodHound) — Active Directory attack-path mapping.
- [CrackMapExec](https://github.com/byt3bl33d3r/CrackMapExec) — Network-wide AD enumeration / exploitation.
- [Impacket](https://github.com/fortra/impacket) — Python toolkit for network protocols (AD especially).

## AI Hacking Agents

LLM-driven offensive-security agents — the autonomous and semi-autonomous tools that plan, recon, exploit, and report. Curated from [EvanThomasLuke/Awesome-AI-Hacking-Agents](https://github.com/EvanThomasLuke/Awesome-AI-Hacking-Agents). Strictly for authorized testing, CTFs, and your own infrastructure.

### Open Source

The agents I'd actually clone and try — stars, recent commits, and a working README.

- [Claude Code](https://github.com/anthropics/claude-code) — Anthropic's terminal coding agent; not security-specific but the substrate a lot of these agents run on.
- [Strix](https://github.com/usestrix/strix) — Open-source autonomous agent that finds and fixes app vulns; one of the most-starred in the space.
- [PentAGI](https://github.com/vxcontrol/pentagi) — Fully autonomous AI agent system for complex pentests; multi-agent orchestration.
- [PentestGPT](https://github.com/GreyDGL/PentestGPT) — USENIX Security 2024 paper; the OG GPT-driven pentest assistant.
- [HexStrike AI](https://github.com/0x4m4/hexstrike-ai) — MCP server letting any AI agent (Claude/GPT/Copilot) drive 150+ offsec tools.
- [CAI — Cybersecurity AI](https://github.com/aliasrobotics/cai) — Framework for building security agents; from the Alias Robotics team.
- [Decepticon](https://github.com/PurpleAILAB/Decepticon) — Autonomous red-team agent; fast-moving project with strong community traction.
- [Burp AI Agent](https://github.com/six2dez/burp-ai-agent) — Burp Suite extension that adds built-in MCP, AI-assisted analysis, and AI-driven active/passive scanning.
- [hackingBuddyGPT](https://github.com/ipa-lab/hackingBuddyGPT) — "Helping ethical hackers use LLMs in 50 lines of code"; great starting point for your own agent.
- [Darkmoon](https://github.com/ASCIT31/Dark-Moon) — Open-source autonomous AI pentest platform and MCP host; per-tech offensive sub-agents, Active Directory and Kubernetes, orchestrates 80+ offensive tools with an evidence trail per finding.
- [Reaper](https://github.com/ghostsecurity/reaper) — Ghost Security's live validation proxy; tests web-app vulns with AI in the loop.
- [Nebula](https://github.com/berylliumsec/nebula) — AI-powered pentest assistant; recon, note-taking, and vuln analysis.
- [Agentic Radar](https://github.com/splx-ai/agentic-radar) — Security scanner *for* LLM agentic workflows; the meta tool you need if you ship agents.
- [HackSynth](https://github.com/aielte-research/HackSynth) — LLM agent + evaluation framework for autonomous pentesting; planner-summarizer architecture.
- [NYU CTF Agents (D-CIPHER)](https://github.com/NYU-LLM-CTF/nyuctf_agents) — Baseline LLM agents for the NYU CTF Bench; great reference for CTF automation.
- [Cyber-AutoAgent](https://github.com/double16/cyber-autoagent-ng) — Active fork of the original Cyber-AutoAgent (archived); reportedly 85% on XBOW's top-OSS score.
- [operant-mcp](https://github.com/operantlabs/operant-mcp) — MCP server bundling 51 testing tools across 19 modules (SQLi, XSS, CMDi, SSRF, PCAP forensics, memory forensics, more). `npx operant-mcp`.

### DARPA AIxCC — Cyber Reasoning Systems

The 2025 DARPA AI Cyber Challenge finalists. Production-grade autonomous vuln-finding/patching systems with full source published. Start with the [AIxCC Open Source Archive](https://archive.aicyberchallenge.com/) and the [DARPA results announcement](https://www.darpa.mil/news/2025/aixcc-results).

- [Team Atlanta — ATLANTIS](https://github.com/Team-Atlanta/aixcc-afc-atlantis) — 1st place. [Paper](https://arxiv.org/abs/2509.14589) · [Post-AFC writeup](https://team-atlanta.github.io/blog/post-afc/).
- [Trail of Bits — Buttercup](https://github.com/trailofbits/afc-buttercup) — 2nd place. [Overview](https://trailofbits.com/buttercup/) · [DEF CON slides](https://www.trailofbits.com/documents/DEFCON_AIxCC_Stage_Talk.pdf).
- [Theori — RoboDuck](https://github.com/theori-io/aixcc-afc-archive) — 3rd place. [Implementation blog](https://theori.io/blog/aixcc-and-roboduck-63447).
- [FuzzingBrain — All You Need Is A Fuzzing Brain](https://github.com/o2lab/afc-crs-all-you-need-is-a-fuzzing-brain) — 4th place. [Paper](https://arxiv.org/abs/2509.07225).
- [Shellphish — ARTIPHISHELL](https://github.com/shellphish/artiphishell) — 5th place. [Postmortem](https://support.shellphish.net/blog/2025/08/22/shellphish-x-aixcc-pm/).
- [42-b3yond-6ug — BugBuster](https://github.com/42-b3yond-6ug/42-b3yond-6ug-crs) — 6th place. [Team CRS page](https://b3yond.org/crs).
- [Lacrosse (SIFT)](https://github.com/siftech/afc-crs-lacrosse) — 7th place. [CTF Radiooo interview](https://ctfradi.ooo/2025/07/17/01C-lacrosses-aixcc-final-submission.html).

### Enterprise / Closed Source

Commercial AI hacking platforms worth knowing about — most offer demos or trials.

- [XBOW](https://xbow.com) — The benchmark the others get measured against; autonomous web pentesting at scale.
- [Horizon3.ai](https://horizon3.ai/) — NodeZero autonomous pentest platform; one of the most mature offerings.
- [Pentera](https://pentera.io/) — Automated security validation; mature enterprise stack.
- [Project Naptime → Big Sleep](https://projectzero.googleblog.com/2024/10/from-naptime-to-big-sleep.html) — Google Project Zero + DeepMind's vuln-finding research agent.
- [Dreadnode](https://dreadnode.io/) — AI red-team platform from the Crucible CTF team.
- [Mindgard](https://mindgard.ai/) — AI security testing focused on AI/ML systems themselves.
- [Hacktron](https://www.hacktron.ai/) — Autonomous offensive security agent.
- [MindFort](https://mindfort.ai/) — AI penetration testing platform.
- [RunSybil](https://www.runsybil.com) — Continuous AI red-teaming.
- [Shinobi Security](https://shinobi.security) — AI offensive security platform.
- [Terra Security](https://www.terra.security) — Continuous AI pentesting.
- [SPLX](https://splx.ai/) — LLM-agent security testing (creators of Agentic Radar above).
- [Theori Xint](https://xint.io/) — Commercial counterpart to the RoboDuck AIxCC work.
- [Pensar](https://www.pensarai.app/) — AI appsec / code security.
- [CalypsoAI](https://calypsoai.com/) — AI security and red-teaming platform.
- [Aikido AI Pentest](https://www.aikido.dev/attack/aipentest) — Add-on to the broader Aikido platform.

### Foundational Papers

The research worth reading before you build an agent of your own.

- [LLM Agents can Autonomously Hack Websites](https://alphaxiv.org/abs/2402.06664) — The early proof that this works at all.
- [LLM Agents can Autonomously Exploit One-day Vulnerabilities](https://alphaxiv.org/abs/2404.08144) — Going from CVE description to working exploit.
- [Teams of LLM Agents can Exploit Zero-Day Vulnerabilities](https://alphaxiv.org/abs/2406.01637) — Multi-agent coordination on novel flaws.
- [LLMs as Hackers: Autonomous Linux Privilege Escalation](https://alphaxiv.org/abs/2310.11409) — Root via LLM, evaluated rigorously.
- [HackSynth: LLM Agent and Evaluation Framework for Autonomous Pentesting](https://alphaxiv.org/abs/2412.01778) — Planner-summarizer architecture.
- [Incalmo: Autonomous LLM-assisted Multi-Host Red Teaming](https://alphaxiv.org/abs/2501.16466) — Enterprise-scale network attacks.
- [RedTeamLLM: an Agentic AI framework for offensive security](https://alphaxiv.org/abs/2505.06913) — End-to-end offensive workflow.
- [CVE-Bench](https://alphaxiv.org/abs/2503.17332) — Real-world web-vuln benchmark for AI agents.

The upstream list also tracks the [Tencent Hackathon 2025](https://zc.tencent.com/competition/competitionHackathon?code=cha004) submissions and many WIP repos — see the [original repo](https://github.com/EvanThomasLuke/Awesome-AI-Hacking-Agents) for the full firehose.

## Defensive & Blue Team

What I deploy when I'm protecting the network instead of probing it.

- [Wazuh](https://github.com/wazuh/wazuh) — Open-source SIEM + XDR; integrates with ELK.
- [Security Onion](https://github.com/Security-Onion-Solutions/securityonion) — Full network security monitoring distro.
- [Suricata](https://github.com/OISF/suricata) — High-performance IDS / IPS / NSM.
- [Zeek](https://github.com/zeek/zeek) — Network analysis framework (formerly Bro).
- [Velociraptor](https://github.com/Velocidex/velociraptor) — Endpoint visibility and DFIR collection.
- [OSSEC](https://github.com/ossec/ossec-hids) — Host-based IDS, the original.
- [CrowdSec](https://github.com/crowdsecurity/crowdsec) — Collaborative IPS; shared blocklists across the community.
- [Fail2ban](https://github.com/fail2ban/fail2ban) — Log-based intrusion prevention; set-and-forget for SSH.
- [pfSense](https://www.pfsense.org/) — FreeBSD-based firewall / router platform.
- [OPNsense](https://opnsense.org/) — Modern pfSense fork with cleaner UI.
- [ClamAV](https://www.clamav.net/) — Open-source AV engine; useful for mail gateways.
- [Lynis](https://github.com/CISOfy/lynis) — Security auditing for Unix systems; great for hardening reports.
- [OpenVAS / Greenbone](https://github.com/greenbone/openvas-scanner) — Vulnerability scanner.

## Compliance & GRC

The boring-but-critical stack for HIPAA, NIST CSF, SOC 2, and audit prep work.

- [OpenSCAP](https://github.com/OpenSCAP/openscap) — NIST-validated config compliance scanner.
- [CIS-CAT Lite](https://www.cisecurity.org/cybersecurity-tools/cis-cat-lite) — CIS Benchmark assessments.
- [Chef InSpec](https://github.com/inspec/inspec) — Compliance as code; tests infra against policy.
- [Prowler](https://github.com/prowler-cloud/prowler) — AWS / Azure / GCP / K8s security & compliance audits.
- [ScoutSuite](https://github.com/nccgroup/ScoutSuite) — Multi-cloud security auditing.
- [Steampipe](https://github.com/turbot/steampipe) — Query cloud APIs with SQL; great for ad-hoc audits.
- [Vanta open templates](https://github.com/VantaInc) — Reference policies if you can't afford the platform.
- [NIST OSCAL](https://github.com/usnistgov/OSCAL) — Open Security Controls Assessment Language; the future of audit data exchange.
- [HIPAA Security Risk Assessment Tool](https://www.healthit.gov/topic/privacy-security-and-hipaa/security-risk-assessment-tool) — ONC/OCR's free SRA tool.

## Networking & Sysadmin

The everyday-driver tools — most of these have a tab open in my terminal at all times.

- [tmux](https://github.com/tmux/tmux) — Terminal multiplexer; if you SSH, you need this.
- [mosh](https://mosh.org/) — Mobile shell; survives roaming and dropped connections.
- [htop](https://github.com/htop-dev/htop) — Process viewer that doesn't make you cry.
- [btop](https://github.com/aristocratos/btop) — htop's prettier successor.
- [iperf3](https://github.com/esnet/iperf) — Network throughput testing.
- [mtr](https://github.com/traviscross/mtr) — `traceroute` + `ping` in one continuous view.
- [Wireshark](https://www.wireshark.org/) — Packet analysis; nothing else comes close.
- [tcpdump](https://www.tcpdump.org/) — Wireshark's command-line cousin.
- [Termshark](https://github.com/gcla/termshark) — Wireshark UI in your terminal.
- [ngrok](https://ngrok.com/) — Public tunnels to localhost; lifesaver for webhook dev.
- [Cloudflare Tunnel](https://github.com/cloudflare/cloudflared) — Free, persistent alternative to ngrok.
- [Tailscale](https://tailscale.com/) — Wireguard-based mesh VPN; zero-config.
- [Headscale](https://github.com/juanfont/headscale) — Self-hosted Tailscale control server.
- [rsync](https://github.com/RsyncProject/rsync) — File sync that has outlived dynasties.
- [restic](https://github.com/restic/restic) — Modern encrypted backups; works everywhere.
- [Ansible](https://github.com/ansible/ansible) — Agentless config management; my default.
- [Terraform](https://github.com/hashicorp/terraform) — Infrastructure as code.

## macOS Power Tools

Apps and utilities that earn their dock space on every Mac I set up.

- [Homebrew](https://brew.sh/) — The macOS package manager. Required.
- [iTerm2](https://iterm2.com/) — Terminal replacement; tabs, profiles, hotkey window.
- [Rectangle](https://rectangleapp.com/) — Free window-snapping; replaces Magnet.
- [Raycast](https://www.raycast.com/) — Spotlight on steroids; my Alfred replacement.
- [Stats](https://github.com/exelban/stats) — System monitor in the menu bar.
- [The Unarchiver](https://theunarchiver.com/) — Handles every archive format Apple's built-in tool refuses.
- [AppCleaner](https://freemacsoft.net/appcleaner/) — Properly removes apps and their leftover files.
- [HandBrake](https://handbrake.fr/) — Video transcoding GUI for FFmpeg.
- [VLC](https://www.videolan.org/vlc/) — Plays anything you throw at it.
- [Maccy](https://github.com/p0deje/Maccy) — Lightweight clipboard manager.
- [KeepingYouAwake](https://github.com/newmarcel/KeepingYouAwake) — Caffeinate from the menu bar.
- [Karabiner-Elements](https://github.com/pqrs-org/Karabiner-Elements) — Remap any key on macOS.
- [Sequel Ace](https://github.com/Sequel-Ace/Sequel-Ace) — Free MySQL/MariaDB GUI; fork of Sequel Pro.
- [TablePlus](https://tableplus.com/) — Modern multi-DB GUI; freemium but the free tier is generous.
- [OrbStack](https://orbstack.dev/) — Docker Desktop replacement; faster and lighter on M-series Macs.
- [Bitwarden](https://bitwarden.com/) — Open-source password manager.

## Dev & Full-Stack

What's in my web-dev toolbelt — heavy bias toward what powers [sudojohnny.com](https://sudojohnny.com) and my client work.

- [VS Code](https://github.com/microsoft/vscode) — Default editor; extensions make it.
- [Neovim](https://github.com/neovim/neovim) — When SSH-only or just feeling fast.
- [GitHub CLI](https://github.com/cli/cli) — `gh` for PRs, issues, and repo creation from the terminal.
- [Lazygit](https://github.com/jesseduffield/lazygit) — Terminal git UI that actually makes sense.
- [Vite](https://github.com/vitejs/vite) — Frontend build tool; what I ship React with.
- [Astro](https://github.com/withastro/astro) — Static-site framework; great for content sites.
- [Tailwind CSS](https://github.com/tailwindlabs/tailwindcss) — Utility-first CSS; pairs well with component libs.
- [shadcn/ui](https://github.com/shadcn-ui/ui) — Copy-paste React components with Tailwind.
- [FastAPI](https://github.com/fastapi/fastapi) — Modern Python API framework; auto-generated OpenAPI docs.
- [Hono](https://github.com/honojs/hono) — Tiny, fast web framework; runs on Cloudflare Workers.
- [Bun](https://github.com/oven-sh/bun) — JS runtime + package manager + bundler in one.
- [pnpm](https://github.com/pnpm/pnpm) — Disk-efficient npm replacement.
- [uv](https://github.com/astral-sh/uv) — Astral's blisteringly fast Python package manager.
- [Ruff](https://github.com/astral-sh/ruff) — Python linter + formatter; replaces flake8/black/isort.
- [Prettier](https://github.com/prettier/prettier) — Opinionated code formatter.
- [Playwright](https://github.com/microsoft/playwright) — End-to-end browser testing; my Cypress replacement.
- [Postman](https://www.postman.com/) — API client; everyone has it for a reason.
- [Bruno](https://github.com/usebruno/bruno) — Open-source Postman alternative; git-friendly.
- [Resend](https://resend.com/) — Modern transactional email API; what powers contact forms on my sites.
- [Cloudflare Pages](https://pages.cloudflare.com/) — Where sudojohnny.com lives.

## Books, Cheat Sheets & Learning

- [The Book of Secret Knowledge](https://github.com/trimstray/the-book-of-secret-knowledge) — The mega-list of CLI tools, manuals, and one-liners.
- [Awesome Self-Hosted](https://github.com/awesome-selfhosted/awesome-selfhosted) — Self-hostable software for everything.
- [Awesome Hacking](https://github.com/Hack-with-Github/Awesome-Hacking) — Curated hacking resource hub.
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings) — Web app pentest payloads + bypass tricks.
- [HackTricks](https://github.com/HackTricks-wiki/hacktricks) — The OSCP/HTB cheat-sheet wiki.
- [OWASP Cheat Sheet Series](https://github.com/OWASP/CheatSheetSeries) — App-sec best practices, condensed.
- [Professor Messer Sec+ Notes](https://www.professormesser.com/) — Free Sec+ / Net+ / A+ video courses.
- [TryHackMe](https://tryhackme.com/) — Guided pentest learning paths.
- [HackTheBox](https://www.hackthebox.com/) — Practice boxes; Sec+ → OSCP pipeline.
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) — The reference everyone cites.
- [CIS Controls v8](https://www.cisecurity.org/controls/v8) — Practical, prioritized control list.
- [The Linux Command Line](https://linuxcommand.org/tlcl.php) — Free book; the foundation.
- [explainshell](https://explainshell.com/) — Paste a shell command, get a breakdown.
- [DevDocs](https://devdocs.io/) — Offline-capable API docs for everything.

---

## Source Repos

This list is curated from years of personal use, but four upstream awesome-lists deserve credit for surfacing tools I might've otherwise missed:

- **[soxoj/maigret](https://github.com/soxoj/maigret)** — The OSINT username search tool itself.
- **[Z4nzu/hackingtool](https://github.com/Z4nzu/hackingtool)** — All-in-one red-team toolkit.
- **[trimstray/the-book-of-secret-knowledge](https://github.com/trimstray/the-book-of-secret-knowledge)** — The exhaustive sysadmin/security/devops reference.
- **[jaywcjlove/awesome-mac](https://github.com/jaywcjlove/awesome-mac)** — The macOS app mega-list.
- **[EvanThomasLuke/Awesome-AI-Hacking-Agents](https://github.com/EvanThomasLuke/Awesome-AI-Hacking-Agents)** — The definitive running list of AI hacking agents (~64 OSS + enterprise + DARPA AIxCC + papers).

If you're researching a topic deeply, go read the originals — they're broader. This list is what I'd hand a junior engineer on day one.

---

## License

Content licensed under [Creative Commons Attribution 4.0 International (CC-BY-4.0)](LICENSE). Use it, remix it, link it back.

## Contributing

This is a personal opinionated list — PRs welcome but I'm picky. Open an issue first if you're suggesting an addition. Removals are easier: if a tool is abandoned or has a known security issue, just open an issue and I'll yank it.

---

**Maintained by [@jshepjr](https://github.com/jshepjr)** · **[sudojohnny.com](https://sudojohnny.com)**
