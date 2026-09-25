# Ethical Hacking Attack Simulation Lab

A walkthrough of a controlled home lab I built to practice the full attack chain — reconnaissance, enumeration, exploitation, and post-exploitation — against intentionally vulnerable machines, then reviewed from the defender's side to see what my own attack would have looked like in the logs. Built as a single self-contained web page, no backend or build step required.

**[▶ Live demo](https://raheemmohd.github.io/redteam-lab-portfolio-project/)**

![status](https://img.shields.io/badge/status-complete-brightgreen) ![type](https://img.shields.io/badge/type-portfolio%20project-blue) ![stack](https://img.shields.io/badge/stack-HTML%2FCSS%2FJS-informational)

---

## Why I built this

My SOC and threat-intel projects are both defender-side. I wanted one project that shows I understand the other half — what the attacker is actually doing that those alerts and indicators are reacting to. So I set up an isolated virtual lab (Kali Linux attacker VM, Metasploitable2 and a Windows target, all on a host-only network with no route out), ran a full attack chain against my own machines, and then went back and asked: what would a defender have seen?

That last part is the piece I think matters most. Both case studies here — the vsftpd backdoor exploit and the Windows privilege escalation — connect directly back to detections I documented in my SOC and IOC projects. Running both sides of the same incident made the detection logic concrete instead of theoretical.

## What's inside

| Section | What it covers |
|---|---|
| Lab environment | The isolated host-only network setup — attacker and target VMs, no route to the internet |
| Attack methodology | The 4-stage chain: reconnaissance → enumeration → exploitation → post-exploitation |
| Tools & Metasploit workflow | Nmap, Metasploit, Hydra, John the Ripper, Wireshark, and the actual msfconsole commands I run |
| Case study 1 | Exploiting Metasploitable2's known vsftpd 2.3.4 backdoor for an instant root shell |
| Case study 2 | Brute-forcing a foothold on a Windows target, then escalating to SYSTEM via Meterpreter |
| Turning around: the blue team view | What each attack step would actually trigger in a SIEM/EDR — tied back to my other two projects |
| **Live demo — attack path walkthrough** | Click through all 4 stages of the chain with real command output at each step |
| What I measured | Time to initial access, escalation path count, detection coverage, noise generated |
| Where red teaming is heading | Breach and attack simulation, purple teaming, cloud attack paths, AI-assisted recon |

## Skills demonstrated

`Kali Linux` · `Metasploit Framework` · `Nmap enumeration` · `Credential brute-forcing (Hydra)` · `Privilege escalation (Windows & Linux)` · `Meterpreter post-exploitation` · `Attacker-to-defender detection mapping`

## Tech stack & approach

Pure HTML, CSS, and vanilla JavaScript — no frameworks, no dependencies, no build tooling, same as my other projects. All diagrams are hand-built inline SVG, and the attack-path walkthrough is a small state machine in plain JS.

## Running it locally

```bash
git clone https://github.com/raheemmohd/redteam-lab-portfolio-project.git
cd redteam-lab-portfolio-project
open index.html
```

## A note on scope and safety

Every technique documented here was run entirely inside an isolated, host-only virtual network I control, against machines I own — Metasploitable2 is a publicly available, intentionally vulnerable VM built specifically for this kind of training. Nothing here was run against a real system, network, or organization, and this repo intentionally stops short of documenting persistence or lateral-movement techniques, since those carry the highest misuse risk relative to what they add for a portfolio audience.

## License

MIT

## Author

Mohammed Abdul Raheem
