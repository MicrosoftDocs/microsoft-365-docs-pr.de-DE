---
title: Bekämpfung von Junk-E-Mails, die an Office 365 gesendet werden
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5fd7d05b-96db-456f-81d6-1ac0e5bff530
ms.collection:
- M365-security-compliance
description: Die Roadmap zur E-Mail-Sicherheit von Microsoft beinhaltet einen neuen produktübergreifenden Ansatz. Exchange Online Protection (EOP)-Anti-Spam- und Anti-Phishing-Filtertechnologie wird plattformübergreifend über die E-Mail-Plattformen von Microsoft angewendet, um Benutzern die neuesten Anti-Spam- und Anti-Phishing-Tools und Innovationen im gesamten Netzwerk zur Verfügung zu stellen. Das Ziel für EOP ist ein umfassender und nutzbarer E-Mail-Dienst, der Ihnen hilft, Junk-E-Mails, betrügerische E-Mail-Gefahren (Phishing) und Schadsoftware zu erkennen und Benutzer davor zu schützen.
ms.openlocfilehash: 0a73d428e952c0c0cb340d91a52768a42ae204a1
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081289"
---
# <a name="fighting-junk-email-sent-to-office-365"></a>Bekämpfung von Junk-E-Mails, die an Office 365 gesendet werden

Die Roadmap zur E-Mail-Sicherheit von Microsoft beinhaltet einen neuen produktübergreifenden Ansatz. Exchange Online Protection (EOP)-Anti-Spam- und Anti-Phishing-Filtertechnologie wird plattformübergreifend über die E-Mail-Plattformen von Microsoft angewendet, um Benutzern die neuesten Anti-Spam- und Anti-Phishing-Tools und Innovationen im gesamten Netzwerk zur Verfügung zu stellen. Das Ziel für EOP ist ein umfassender und nutzbarer E-Mail-Dienst, der Ihnen hilft, Junk-E-Mails, betrügerische E-Mail-Gefahren (Phishing) und Schadsoftware zu erkennen und Benutzer davor zu schützen.
  
## <a name="the-challenge"></a>Die Herausforderung

E-Mail ist ein wichtiges Kommunikationstool geworden, nicht nur für Endkunden, sondern auch für Vermarkter, Supportmitarbeiter, Vertriebsorganisationen und Unternehmen aller Größen. Zusammen mit der E-Mail-Verwendung ist auch der E-Mail-Missbrauch gestiegen. Nicht überwachte Junk-E-Mails können Postfächer und Netzwerke verstopfen, sich auf die Benutzerzufriedenheit auswirken und die Effektivität der seriösen E-Mail-Kommunikation behindern. Deshalb investiert Microsoft weiter in Anti-Spam-Technologien. Einfach ausgedrückt beginnt alles mit dem Speichern und Filtern von Junk-E-Mails. 
  
## <a name="our-efforts"></a>Unsere Bemühungen

EOP bietet eine Reihe von Maßnahmen, um die negativen Auswirkungen von Junk-E-Mails auf die E-Mail-Erfahrung der Benutzer zu minimieren.
  
### <a name="exchange-online-protection-technology"></a>Exchange Online Protection-Technologie

Zur Verringerung von Junk-E-Mails enthält EOP Junk-E-Mail-Schutz mit proprietären EOP-Filtertechnologien, die E-Mails überprüfen, um Junk-E-Mails zu identifizieren und von rechtmäßigen E-Mails zu trennen. Der EOP-Inhaltsfilter lernt anhand bekannter Spam- und Phishing-Bedrohungen sowie anhand von Benutzerfeedback unserer Benutzerplattform, Outlook.com. Diese Arten von Daten tragen zum Optimieren der EOP-Technologien bei, um seriöse E-Mails- und Junk-E-Mails zu erkennen, und sind wichtige Faktoren für die Absenderzuverlässigkeit. Kontinuierliches Feedback von EOP-Benutzern im Junk-E-Mail-Klassifizierungsprogramm hilft dabei, sicherzustellen, dass die EOP-Technologien kontinuierlich trainiert und verbessert werden.
  
#### <a name="how-does-eop-work"></a>Wie funktioniert EOP?

Wenn ein externer Benutzer eine E-Mail-Nachricht an einen EOP-Benutzer sendet, werten EOP-Filtertechnologien den Inhalt der Nachricht aus und weisen der Nachricht eine Bewertung basierend auf der Wahrscheinlichkeit zu, dass es sich um eine Junk-E-Mail handelt. Diese Bewertung wird zusammen mit der Nachricht als Nachrichteneigenschaft gespeichert. Die Nachrichteneigenschaft wird als SCL-Bewertung (Spam Confidence Level, Spamwahrscheinlichkeit) bezeichnet. Die SCL-Bewertung bleibt bei der Nachricht, wenn sie an andere Anti-Spam-Schutzebenen in EOP gesendet wird. 
  
Regeln in EOP verarbeiten E-Mail-Nachrichten mit verschiedenen SCL-Bewertungen. Wenn eine Nachricht eine SCL-Bewertung oberhalb eines bestimmten Schwellenwerts hat, gilt sie als Spam. Die Nachricht wird unter Quarantäne gestellt oder in den Junk-E-Mail-Ordner des Benutzers übermittelt, je nachdem, wie der Systemadministrator die Spam-Zustellungsoption konfiguriert hat.
  
#### <a name="eop-filters"></a>EOP-Filter

Zusätzlich zu den Anti-Spam-Filtertechnologien gibt EOP dem Systemadministrator auch die Möglichkeit, Filterebenen festzulegen, um die Übermittlung von E-Mails an Benutzerkonten weiter anzupassen. Administratoren können problemlos einen Absender oder Domänennamen zur Liste der sicheren Absender und Domänen hinzufügen, damit E-Mails von diesem Absender oder dieser Domäne niemals als Junk eingeordnet werden, unabhängig vom Inhalt der Nachricht. Informationen dazu finden Sie unter [Listen sicherer und blockierter Absender in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md).
  
### <a name="phishing-protection"></a>Schutz gegen Phishing

Phishing („Fisching" ausgesprochen) ist eine Form von Identitätsdiebstahl und eine der am schnellsten wachsenden Bedrohungen im Internet. Sie können eine Phishingnachricht häufig erkennen, wenn sie persönliche oder finanzielle Informationen anfordert oder einen Link zu einer Website enthält, die derartige Informationen anfordert. EOP bietet Phishingschutz als Teil der proprietären EOP-Filtertechnologien an. EOP-Filtertechnologien analysieren E-Mails, um betrügerische Links oder gefälschte Domänen zum Schutz der Benutzer vor diesen Arten von Onlinebetrug zu erkennen.
  
#### <a name="how-does-phishing-protection-work"></a>Wie funktioniert der Phishingschutz?

Häufig wird eine Phishing-E-Mail mit einem Link gesendet. Wenn der Benutzer auf diesen Link klickt, wird er auf eine betrügerische Website weitergeleitet, die echt erscheint (beispielsweise Ihre Bank oder ein Onlinedienst). Diese Phishingwebsite fordert in der Regel Benutzer auf, persönliche Informationen wie Benutzernamen, Kennwörter und Sozialversicherungsnummern einzugeben. Alle auf der Phishingwebsite eingegebenen Informationen helfen dem Phisher beim Diebstahl Ihrer Identität. Mithilfe von bekannten vertrauenswürdigen Markennamen und -logos können Phisher durchaus seriös erscheinen. Die in EOP angebotene Phishing-Filtertechnologie sucht nach potenziellen Phishing-Merkmalen in E-Mails. Wird ein solches Merkmal gefunden, wird die E-Mail in den Junk-Ordner verschoben.
  
Microsoft konzentriert seine Anti-Phishing-Technologie auf zwei Punkte: Erstens soll verhindert werden, dass E-Mail-Phishingnachrichten unsere Benutzer erreichen, und zweitens soll die Möglichkeit, dass Benutzer durch gefälschte E-Mails und Websites geschädigt werden, eliminiert werden. 
  
> [!TIP]
> Internet Explorer ab Version 7 blockiert oder warnt Benutzer, wenn sie bekannte potenzielle Phishing-Websites besuchen, damit sie keine persönlichen Informationen bereitstellen.[Stellen Sie sicher, dass Sie die neueste Version von Internet Explorer haben](https://www.microsoft.com/windows/ie/default.mspx). 
  
#### <a name="authentication"></a>Authentication

Domänen-Spoofing ist eine Möglichkeit, eine seriöse E-Mail-Adresse zu imitieren, damit betrügerische E-Mails seriös erscheinen. Spoofing wird von böswilligen Personen oder Organisationen in Phishing-Betrugsversuchen verwendet, um Personen zum Preiszugeben vertraulicher persönlicher Informationen zu verleiten. Die Offenlegung dieser Informationen kann zu Identitätsdiebstahl und anderen Arten von Betrug führen.
  
EOP verwendet Sender Protection Framework (SPF), DomainKeys Identified Mail (DKIM) und Domain-based Message Authentication, Reporting, and Conformance (DMARC) sowie andere implizite Authentifizierungen, um sicherzustellen, dass Nachrichten aus der Domäne stammen, die angegeben wird. Es wird empfohlen, dass alle Absender SPF und DKIM verwenden, um ihre Empfänger vor Junk-E-Mails und Phishing-Betrug zu schützen. Absender sollten einen DMARC veröffentlichen, um E-Mails abzulehnen oder zu isolieren, die von unbefugten Absendern gesendet werden.
  
- Weitere Informationen zu SPF finden Sie unter [RFC 7208](https://tools.ietf.org/html/rfc7208) und [Sender Policy Framework](http://www.openspf.org/).
    
- Weitere Informationen zu DKIM finden Sie unter [RFC 6376](https://tools.ietf.org/html/rfc6376) und [DKIM.org](http://dkim.org/).
    
- Weitere Informationen zu DMARC finden Sie unter [DMARC.org](https://dmarc.org/).
    
### <a name="legislation"></a>Gesetzgebung

Bei Microsoft glauben wir, dass die Entwicklung neuer Technologien und Selbstregulierungsmaßnahmen die Unterstützung durch effektive behördliche Richtlinien und gesetzliche Rahmen erfordert. Die weltweite Spam-Ausbreitung hat eine Vielzahl von Behörden dazu veranlasst, kommerzielle E-Mails zu regulieren. Viele Länder/Regionen verfügen mittlerweile über Anti-Spam-Gesetze. Die Vereinigten Staaten haben sowohl staatliche als auch bundesstaatliche Anti-Spam-Gesetze. Dieser ergänzende Ansatz trägt dazu bei, Spam einzudämmen und das Wachstum des legitimen e-Commerce zu ermöglichen. Die CAN SPAM Act erweitert die Tools, die zum Eindämmen betrügerischer und täuschender E-Mail-Nachrichten zur Verfügung stehen.
  

