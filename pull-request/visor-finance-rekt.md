---
title: Visor Finance - REKT
date: 12/22/2021
rekt:
  amount: 8200000
  audit: Unaudited 
  date: 12/21/2021
tags:
  - Visor Finance
  - REKT
excerpt: Es ist die Zeit des Schenkens und Visor Finance geht aufs Ganze. Visor ermöglichte es einem anonymen Täter, 8,2 Millionen US-Dollar in VISR zu minten.
banner: https://raw.githubusercontent.com/RektHQ/Assets/main/images/2021/12/visor-header.png
---
![](https://raw.githubusercontent.com/RektHQ/Assets/main/images/2021/12/visor-header.png)
**Es ist die Zeit des Schenkens und Visor Finance geht aufs Ganze.**

[Visor](https://www.visor.finance/) erlaubte bestimmten Smart-Contracts, unbegrenzte Belohnungen zu minten.

Gestern nutzte ein anonymer Täter dieses Geschenk und zog 8,8 Millionen VISR von der Plattform ab; 8,2 Millionen US-Dollar zu Vor-Hack-Preisen.

**Allerdings musste der Hacker beim Dumping von VISR über den VISR-ETH-Pool von Uniswap Verluste hinnehmen.**

![](https://raw.githubusercontent.com/RektHQ/Assets/main/images/2021/12/visor-priceimpact.png)

**-87%**

>rekt.

Bereits im Juni spielte Visor, ein Liquiditätsmanagementprotokoll für [Uni v3](https://rekt.news/uniswap-v3-lp-rekt/), den Verlust von 500.000 US-Dollar (damals 3 Millionen US-Dollar TVL) bei einem [Sicherheitsverletzung](https://visorfinance.medium.com/visor-beta-incident-report-1b2521b9266) herunter.

Dann, letzten Monat, wurde das Projekt Opfer dessen, was das Visor-Team defensiv als „_wirtschaftliche Arbitrage_“ [bezeichnete](https://twitter.com/VisorFinance/status/1464574917056385025).

Zählt das „[_Abhängigkeit von Kassakursen für die Ausgabe von Aktien_](https://twitter.com/Mudit__Gupta/status/1464657484367339527)“ nicht als Smart-Contract-Bug?...

_Was war es dieses Mal?_

![](https://raw.githubusercontent.com/RektHQ/Assets/main/images/2021/09/rekt-investigates-linebreak.png)

**Adresse des Hackers:** [0x8efab89b497b887cdaa2fb08ff71e4b3827774b2](https://etherscan.io/address/0x8efab89b497b887cdaa2fb08ff71e4b3827774b2)

[Finanziert](https://etherscan.io/tx/0x660b97542ade1e533bd5e098dbe53da26b63d53a3c2c4dd46b481a91bd075ead) durch Tornado Cash wenige Minuten vor der [Ausführung](https://etherscan.io/tx/0x69272d8c84d67d1da2f6425b339192fa472898dce936f24818fda415c1c1ff3f) des Angriffs.

Aufgrund einer anfälligen _require()_-Prüfung in der _deposit()_-Funktion des [vVISR Rewards Contract](https://etherscan.io/address/0xc9f27a50f82571c1c8423a42970613b8dbda14ef#code) konnte der Hacker unbegrenzt Anteile mit seinem eigenen [Contract](https://etherscan.io/address/0x10c509aa9ab291c76c45414e7cdbd375e1d5ace8) minten.

![](https://raw.githubusercontent.com/RektHQ/Assets/main/images/2021/12/visor-code.png)

**Solange der Hacker seinen eigenen Contract als „_from_“ übergibt und der Contract eine _Owner()_-Methode von _msg.sender_ hat, kann er mit _vvisr.mint()_ beliebig viele Anteile an jede beliebige Adresse minten.**

_Quelle: [@storming0x](https://twitter.com/storming0x/status/1473321779250802693)_

**Der Angreifer [übertrug die Eigentümerschaft](https://etherscan.io/tx/0x27f2210536553392cf180c0b37055b3dc92094a5d585d7d2a51f790c9145e47c) des Contracts an seine eigene Adresse, bevor er die Exploit-Transaktion ausführte und 195.000 vVISR-Tokens [mintete](https://etherscan.io/tx/0x69272d8c84d67d1da2f6425b339192fa472898dce936f24818fda415c1c1ff3f).**

Diese wurden dann für 8,8 Millionen VISR [verbrannt](https://etherscan.io/tx/0x6eabef1bf310a1361041d97897c192581cd9870f6a39040cd24d7de2335b4546), bevor sie über Uniswap v2 gegen ETH geswapt und über Tornado Cash in [dieser](https://etherscan.io/tx/0x0e16210218ecc487a35b9ff48fe3d9f3e9b0f50330f9e7805e38135732b85270) und 6 wieteren Transaktionen mit insgesamt 113 ETH (450.000 US-Dollar) gewaschen wurden.

![](https://raw.githubusercontent.com/RektHQ/Assets/main/images/2021/03/rekt-linebreak.png)

**In ihrem [offiziellen Post-Mortem](https://medium.com/visorfinance/post-mortem-for-vvisr-staking-contract-exploit-and-upcoming-migration-7920e1dee55a) hat Visor eine [Token-Migration](https://twitter.com/VisorFinance/status/1473317327601078279) basierend auf einem Snapshot vor dem Exploit vorgeschlagen.**

Sie erklären auch, dass:

„_Wir sind sowohl mit Quantstamp als auch mit ConsenSys Diligence für Dezember- und Januar-[Audits](https://docs.visor.finance/learn/audits) beschäftigt und dieser neue Staking Contract wird mit einbezogen._“

Da die Nutzer eine Rückerstattung erhalten, scheint der einzige Schaden der Ruf des Visor-Teams zu sein.

**Zumindest sammeln sie Erfahrung in der Post-Hack-PR...**

Wie [BlockSec](https://twitter.com/BlockSecTeam/status/1473343144620015619) auf Twitter schrieb:

>„Da das letzte Mal ein Angriff als Arbitrage bezeichnet wurde, können wir ihn dieses Mal _Airdrop_ nennen?“

![](https://raw.githubusercontent.com/RektHQ/Assets/main/images/2021/08/rekt-outline-conc.png)
