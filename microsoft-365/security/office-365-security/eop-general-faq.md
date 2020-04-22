---
title: EOP - Allgemeine häufig gestellte Fragen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
description: 'Hier werden die häufigsten allgemeinen Fragen zum cloudgehosteten E-Mail-Filterdienst Microsoft Exchange Online Protection (EOP) beantwortet. Themen mit weiteren häufig gestellten Fragen (FAQs) finden Sie unter den folgenden Links:'
ms.openlocfilehash: 899109a768399f53674b97fc8df2f71aa822316d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636252"
---
# <a name="eop-general-faq"></a>EOP – Allgemeine häufig gestellte Fragen

Hier werden die häufigsten allgemeinen Fragen zum cloudgehosteten E-Mail-Filterdienst Microsoft Exchange Online Protection (EOP) beantwortet. Themen mit weiteren häufig gestellten Fragen (FAQs) finden Sie unter den folgenden Links:

- [Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten](eop-queued-deferred-and-bounced-messages-faq.md)

- [Häufig gestellte Fragen zur delegierten Verwaltung](delegated-administration-faq.md)

- [Häufig gestellte Fragen zum Antispamschutz](anti-spam-protection-faq.md)

- [Häufig gestellte Fragen (FAQ) zur Quarantäne](quarantine-faq.md)

- [Häufig gestellte Fragen zum Schutz vor Schadsoftware](anti-malware-protection-faq-eop.md)

- [Häufig gestellte Fragen zur Nachrichtenablaufverfolgung](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

**F. Was ist EOP?**

A. EOP ist ein cloudgehosteter E-Mail-Filterdienst zum Schutz von Kunden vor Spam und Malware sowie zur Implementierung von benutzerdefinierten Richtlinienregeln.

**F. Wie kann ich mich für eine EOP-Testversion anmelden oder EOP kaufen?**

A. Sie können sich über das Web auf der [Exchange Online Protection-Homepage](https://products.office.com/exchange/exchange-email-security-spam-protection) für eine EOP-Testversion anmelden oder EOP kaufen. Beachten Sie, dass die Funktionalität einer Testversion der eines bezahlten Abonnements entspricht und außerdem die Zusatzfeatures umfasst, die mit dem Abonnementplan [Exchange Enterprise CAL mit Service](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) geboten werden.

**F. Was kostet EOP?**

A. EOP wird auf Benutzerbasis lizenziert. Die aktuellen Preisinformationen finden Sie auf der [Exchange Online Protection-Homepage](https://products.office.com/exchange/exchange-email-security-spam-protection).

**F. Wie lange dauert es, um EOP in Produktion zu setzen?**

A. Wenn Sie den MX-Eintrag gemäß den Anweisungen unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md) ändern, werden E-Mails sofort beim Durchlaufen von EOP gefiltert. Die Übertragung des MX-Eintrags über DNS kann 24 bis 48 Stunden dauern. Die Schutzeinstellungen in der Exchange-Verwaltungskonsole (EAC) können während dieses Vorgangs jederzeit angepasst werden.

**F. muss ich alle Features von Microsoft 365 für die Verwendung von EoP verwenden? Was kann ich tun, wenn ich nur EoP Schutz möchte?**

A: Sie können EoP verwenden, um Ihre lokalen Postfächer zu schützen, ohne andere Features von Microsoft 365 zu verwenden. Dies wird als "eigenständiges Abonnement" bezeichnet. Eine Liste der EOP-Features finden Sie in der [Exchange Online Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

**F. Warum benötige ich einen Microsoft 365-Mandanten bei der Anmeldung zur e-Mail-Filterung über EoP?**

A: Microsoft 365 ist der Name für eine Sammlung von Produkten und Diensten, auf die über einen Microsoft 365-Mandanten zugegriffen werden kann. Stellen Sie sich den Microsoft 365-Mandanten als Ausgangspunkt für das Hinzufügen von Lizenzen für die e-Mail-Filterung vor.

**F. Verfügt EOP über ein Kommunikationsportal, auf dem ich Informationen über bekannte Probleme und die zu erwartenden Lösungen abrufen kann? Wie verhält es sich mit neuen Funktionen?**

A. Das Microsoft 365 Admin Center enthält einige dieser Informationen. Wenn Sie von einem Ereignis auf Dienstebene betroffen sind, sollte eine Kommunikations Warnung (in der Regel von einem Glockensymbol begleitet) angezeigt werden, nachdem Sie sich beim Microsoft 365 Admin Center angemeldet haben. Es wird empfohlen, dass Sie sämtliche zugehörigen Hinweise lesen und entsprechend vorgehen.

In Bezug auf neue EoP-Funktionen ist die [Roadmap von Microsoft 365 for Business](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) eine gute Ressource, um Informationen zu neuen Features zu finden. Außerdem werden Blog Artikel zu neuen Features auf der Website [Microsoft 365 Blogs](https://www.microsoft.com/microsoft-365/blog/) veröffentlicht.

**F. Funktioniert der Dienst mit älteren Exchange-Versionen (z. B. Exchange Server 2010) und in Umgebungen, die nicht auf Exchange basieren?**

A. Ja, der Dienst ist serveragnostisch und kann mit einem beliebigen SMTP-E-Mail-Übertragungs-Agent verwendet werden.

**F. Welche Größe muss eine Organisation haben, um den Dienst verwenden zu können?**

A. Die Größe spielt keine Rolle. Das EOP-Netzwerk bietet für das Wachstum Ihrer Organisation ausreichend Kapazität - unabhängig davon, wie schnell es erfolgt.

**Welche Berechtigungen müssen für EOP eingerichtet werden?**

Um EoP zu konfigurieren, müssen Sie ein globaler Administrator oder ein Exchange-Unternehmens Administrator (die Rollengruppe "Organisationsverwaltung") sein.

**F. Woher weiß ich, ob meine Daten und persönlichen Informationen sicher sind?**

A. Informationen zu den Maßnahmen, die zum Schutz Ihrer Daten und persönlichen Informationen ergriffen wurden, sowie zu Vereinbarungen zum Servicelevel (Service Level Agreements, SLAs) finden Sie im [Office 365 Trust Center](https://www.microsoft.com/trust-center).

**F: Gibt es Obergrenzen, die ich kennen sollte, z. B. bei der Nachrichtengröße?**

A. Ja. Weitere Informationen zu Grenzen in EOP finden Sie unter [Beschränkungen von Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

**F. unterstützt EoP PowerShell?**

A: Ja, die vollständige EoP-Funktionalität ist über PowerShell verfügbar. Weitere Informationen finden Sie unter [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).
