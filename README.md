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
- [Offensive Security](#offensive-security)
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

If you're researching a topic deeply, go read the originals — they're broader. This list is what I'd hand a junior engineer on day one.

---

## License

Content licensed under [Creative Commons Attribution 4.0 International (CC-BY-4.0)](LICENSE). Use it, remix it, link it back.

## Contributing

This is a personal opinionated list — PRs welcome but I'm picky. Open an issue first if you're suggesting an addition. Removals are easier: if a tool is abandoned or has a known security issue, just open an issue and I'll yank it.

---

**Maintained by [@jshepjr](https://github.com/jshepjr)** · **[sudojohnny.com](https://sudojohnny.com)**
