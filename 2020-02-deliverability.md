---
layout: post-layout.njk 
title: Deliverability
date: 2020-02-01
tags: ['post']
---
# Něco na úvod

<!-- Excerpt Start -->
Ano, nikdo nechce dostávat do schránky otravný maily. ISP (Internet Service Providers) se snaží udržet svoje zákazníky a vymýšlejí, jak si udržet svoje zákazníky, že je odfiltrujou od otravů. 
<!-- Excerpt End -->
V poslední době se ale stále více setkávám s tím, že firmy mají problém doručovat relevantní a pro zákazníky důležité maily. Zákazník pak marně čeká na licenční klíč, nemusí dostat mail na obnovu zapomenutého hesla nebo třeba nedostanou nabídku na produkt, který jim vyřeší jejich problém.
Podle statistik jen 85 % legitimních emailů se dostane ke svému adresátovi ([Return Path, 2018](https://www.validity.com/resource-center/report/2018-delivery-benchmark/)). 

Můžeme tedy přicházet o nemalou část obchodních příležitostí. Také kvalita služeb postavených na emailové komunikací získává trhliny. 

Co s tím? Co dělat, aby se relevantní mail dostal k tomu, kdo ho ocení?
Zkusme shrnout pár principů se zkušeností z každodenního emailového zoufalství. 
Celý problém je poměrně komplexní, vstupuje do něho spousta proměnných. Není proto jednoduché identifikovat problém.
Existuje ale několik pravidel, které je dobré dodržovat a kontrolovat. Je například důležité kolik posíláte mailů, jakou má doména historii, jestli používáte dedikovanou IP adresu, jak snadno umožňuje odhlásit se z mailing listu, i třeba to, co dáváte do předmětu zprávy. Ale postupně bod po bodu.

## Základní pojmy, hráči a obsazení

### ISPs (Internet Service Providers)
Než ISP doručí svým zákazníkům email, prověřují kredibilitu doménových IP adres odesílatele. Hodnotí tzv. reputaci IP adresy, ze které se doručuje. Když se jim nebudete líbit, nebo budete podezřelí, mail pravděpodobně nedoručí. To ještě nemusí znamenat, že spamujete. Aby bylo jasno, o kom zde mluvíme, mezi nejvýznamnějsí ISPs patří:

* Google 
* Outlook EUR 4.2 /mo
* Zoho 0 / 
* Yahoo!
* Yandex
* AOL
* Mail.ru

### ESP (email sending providers)
Nástroje pro rozesílaní emailů. Je jich celá řada. Většina nabízí možnost si prověřit schopnost doručovat v trial verzi. Pro limitovaný počet mailů bývá k dispozici i bezplatná verze slutby. Je dobré vybrat nástroj s dobrou reputací svých IP adres. Za těmito platformami stojí týmy odborníků, kteří se snaží držet kredibilitu na maximu. Zde je pár příkladů velkých hráčů na tomto poli:

* Mailgun
* SparkPost
* Sendinblue
* Postmark
* Postfix
* SendGrid

# Pro Admina

## Autentifikujte se  - Record, Key, Protocol

### SPF (Sender Policy Framework)

SPF records tell an incoming server which hosts or IP addresses are allowed to send emails with a given email address.

### DKIM (DomainKeys Identified Mail)

is used to validate if a given email message was sent by the owner of a given email address. It’s a digital signature that’s sent with every email message sent. It includes encrypted details such as message body or/and headers, sender’s domain and others. When an email with DKIM is received by an incoming server, it will recreate the signature with a public key and compare it against the DKIM received.

### DMARC (“Domain-based Message Authentication, Reporting & Conformance”)

is an email authentication, policy, and reporting protocol. It builds on the widely deployed SPF and DKIM protocols, adding linkage to the author (“From:”) domain name, published policies for recipient handling of authentication failures, and reporting from receivers to senders, to improve and monitor protection of the domain from fraudulent email.
[DMARC.org](https://dmarc.org) 
[DMARC report analyzer](https://mxtoolbox.com/DmarcReportAnalyzer.aspx)

Analýza hlaviček 
https://docs.microsoft.com/cs-cz/microsoft-365/security/office-365-security/anti-spam-message-headers?view=o365-worldwide
nástroje: 

https://mxtoolbox.com/EmailHeaders.aspx


## Prověřujte zpětnou vazbu od ISPs

## Zvažte dedikovanou IP adresu

## Zvažte [List-unsubscribe]
(https://help.returnpath.com/hc/en-us/articles/222445307-What-is-the-List-Unsubscribe-header-) do hlavičky mailu 
Návod k nastavení je [zde](https://help.returnpath.com/hc/en-us/articles/222445367-How-to-implement-the-List-Unsubscribe-header)
Jen je potřeba dát pozor na to, aby byl unsubscribe okamžitě zprocesován.
Také je třeba brát v úvahu fakt, že ne všichni klienti podporují http i mailto variantu. Více například [zde](https://litmus.com/blog/the-ultimate-guide-to-list-unsubscribe)



# Pro Email marketera
Tady to bude vypadat trochu banálně. Budete vám připadat, že to je logický. U většiny bodů si možná řeknete, že to tak i děláte. Jo, asi je to tak. Jsou to přesto body, ke kterým je dobré se opakovaně vracet a nastavovat si zrcadlo. Reputaci si budujete dlouho a poškodit se dá velmi rychle.


## Dobře se starejte o svůj mailing list
Posílejte maily jen těm, kteří dali najevo, že je chtějí.
Pravidelně mailing list udržujte.
Neschovávejte možnost se odhlásit 
Zvažte double opt-in


## Posílejte pravidelně a konzistentně
Pravidelnost, hodina, postupné navyšování
Personifikujte
Přivítejte
Nevymýšlejte spamové texty do předmětu zprávy
Posílejte relevantní obsah, segmentujte
Pokud nejste velká korporace neposílejte no-reply emails


## Sledujte svoji reputaci

### Co ovlivňuje reputaci
Technické parametry
Stížnosti - snažte se je držet pod 0,2 %
Počet neznámých adres v mailing listu
Výskyt na blacklistu 
Statistiky user engagementu

Bayes spam filtering [Short explanation and easy tricks how to bypass](https://blog.malwarebytes.com/security-world/2017/02/explained-bayesian-spam-filtering/)
SVM Spam Filter [Evaluation of both](http://www.fun.ac.jp/~niimi/ronbun/TUE-3-3.pdf)

[Machine Learnign Techniques](https://www.sciencedirect.com/science/article/pii/S2405844018353404)

Postmaster [Jak to funguje](https://sendpulse.com/blog/how-postmasters-work)

### Kde ověřit
SenderScore
Talos
[ISnotSPAM](https://isnotspam.com)s
služba https://spamassassin.apache.org/
Apache SpamAssassin is the #1 Open Source anti-spam platform giving system administrators a filter to classify email and block spam (unsolicited bulk email).
It uses a robust scoring framework and plug-ins to integrate a wide range of advanced heuristic and statistical analysis tests on email headers and body text including text analysis, [Bayesian filtering](https://blog.malwarebytes.com/security-world/2017/02/explained-bayesian-spam-filtering/), DNS blocklists, and collaborative filtering databases.

http://www.reputationauthority.org/
https://talosintelligence.com/reputation_center/

### Co s tím dělat
Analyzovat error code
Napsat trouble ticket
Registrovat se k získávání zpětné vazby od ISPs
Poslat požadavek na zapsání na whitelist

Zkusit urychlovač https://ipwarmup.com/


### Přístup vybraných ISPs 
Outlook
[Služby pro odesílatele](https://sendersupport.olc.protection.outlook.com/pm/services.aspx#Section1)
SNDS 
JMRP
> Smart Network Data Services (SNDS) and the Junk Mail Reporting Program (JMRP) are two services Outlook.com provides for email senders to receive feedback on their mail. SNDS provides an overview of your IP addresses, and shows relevant statistics like approximate inbox rate, complaint rate, and trap hits. JMRP lets you set up a feedback loop, so you can receive copies of messages Outlook.com users mark as junk.
[join page](https://sendersupport.olc.protection.outlook.com/snds/JMRP.aspx)

Google
AOL

hosting service
`dig MX <server name>`


## Pravidelně testujte doručitelnost
https://blog.mailtrap.io/test-email-deliverability/
https://blog.mailtrap.io/email-testing-checklist/

* [MX Toolbox](https://mxtoolbox.com/Pro/#/)
https://spam-check.glockapps.com/


## Používejte nástroje na trackování emailů


## Dedikovaná IP adresa?
> 50 tis. mailů týdně



# Realná zkušenost
Po registraci žádná změna. Doručitelnost na outlook se zásadním způsobem nezměnila. A informace o zařazování do spamu jsme měli pořád stejné, tedy žádné. 


Udělali jsme si závěr, že u malého počtu emailů je reputace daného serveru neznámá. Microsoft má v současné době opatrnou strategii. A maily od neznámých domén raději nedoručuje, i když na ně neexistují relevantní stížnosti.

Viz podobná diskuse a závěry [zde](https://serverfault.com/questions/896143/emails-are-constantly-marked-by-outlook-com-as-spam)


# Shrnutí a best practice
Záleží na počtu emailů Reputace

Zdroje: 

[Feedback loops](https://www.validity.com/blog/feedback-loops-all-about-being-in-the-loop/)

[11 Secret Ways of Improving... - Jellymetrics](https://jellymetrics.com/improving-email-deliverability/)

[Best practices - Returnpath](https://pages.returnpath.com/email-sending-best-practices.html)

[6 rules - Sparkpost](https://www.sparkpost.com/blog/6-rules-maximum-outlook-deliverability/)

[Ultimate Email Deliverability Guide](https://blog.mailtrap.io/email-deliverability/)

[Pieter Arntz](https://blog.malwarebytes.com/security-world/2017/02/explained-bayesian-spam-filtering/)