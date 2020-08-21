---
title: EOP - Allgemeine häufig gestellte Fragen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Hier finden Sie Antworten auf die häufigsten allgemeinen Fragen zum Exchange Online Protection (EoP) Cloud-Hosted Email Filtering Service.
ms.openlocfilehash: 42162ea841f876fc5e958d67fab61dbe4bffe9de
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827761"
---
# <a name="eop-general-faq"></a>EOP – Allgemeine häufig gestellte Fragen

Hier werden die häufigsten allgemeinen Fragen zu Exchange Online Protection (EoP) Cloud-Hosted e-Mail-Filterdienst beantwortet. Themen mit weiteren häufig gestellten Fragen (FAQs) finden Sie unter den folgenden Links:

- [Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten](eop-queued-deferred-and-bounced-messages-faq.md)

- [Häufig gestellte Fragen zur delegierten Verwaltung](delegated-administration-faq.md)

- [Häufig gestellte Fragen zum Antispamschutz](anti-spam-protection-faq.md)

- [Häufig gestellte Fragen (FAQ) zur Quarantäne](quarantine-faq.md)

- [Häufig gestellte Fragen zum Schutz vor Schadsoftware](anti-malware-protection-faq-eop.md)

- [Häufig gestellte Fragen zur Nachrichtenablaufverfolgung](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Was ist EOP?

EOP ist ein cloudgehosteter E-Mail-Filterdienst zum Schutz von Kunden vor Spam und Malware sowie zur Implementierung von benutzerdefinierten Richtlinienregeln. EoP ist in einem Microsoft 365-Abonnement enthalten, das Exchange Online Postfächer enthält. EoP ist auch als eigenständiges Angebot verfügbar, um lokale e-Mail-Umgebungen zu schützen.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Wie kann ich mich für eine EOP-Testversion anmelden oder EOP kaufen?

Sie können sich über das Web auf der [Exchange Online Protection-Homepage](https://products.office.com/exchange/exchange-email-security-spam-protection) für eine EOP-Testversion anmelden oder EOP kaufen. Beachten Sie, dass die Funktionalität einer Testversion der eines bezahlten Abonnements entspricht und außerdem die Zusatzfeatures umfasst, die mit dem Abonnementplan [Exchange Enterprise CAL mit Service](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) geboten werden.

## <a name="how-is-eop-priced"></a>Was kostet EOP?

EOP wird auf Benutzerbasis lizenziert. Die aktuellen Preisinformationen finden Sie auf der [Exchange Online Protection-Homepage](https://products.office.com/exchange/exchange-email-security-spam-protection).

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Wie lange dauert es, um EOP in Produktion zu setzen?

Wenn Sie den MX-Eintrag gemäß den Anweisungen unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md) ändern, werden E-Mails sofort beim Durchlaufen von EOP gefiltert. Die Übertragung des MX-Eintrags über DNS kann 24 bis 48 Stunden dauern. Während dieses Vorgangs können Sie die Einstellungen für den Schutz jederzeit optimieren.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>Muss ich alle Features von Microsoft 365 für die Verwendung von EoP verwenden? Was kann ich tun, wenn ich nur EoP Schutz möchte?

Sie können EoP verwenden, um Ihre lokalen Postfächer zu schützen, ohne andere Features von Microsoft 365 zu verwenden. Dies wird als "eigenständiges Abonnement" bezeichnet. Eine Liste der EOP-Features finden Sie in der [Exchange Online Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Warum benötige ich einen Microsoft 365-Mandanten bei der Anmeldung zur e-Mail-Filterung über EoP?

Microsoft 365 ist der Name für eine Sammlung von Produkten und Diensten, auf die über einen Microsoft 365-Mandanten zugegriffen werden kann. Stellen Sie sich den Microsoft 365-Mandanten als Ausgangspunkt für das Hinzufügen von Lizenzen für die e-Mail-Filterung vor.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>Verfügt EOP über ein Kommunikationsportal, auf dem ich Informationen über bekannte Probleme und die zu erwartenden Lösungen abrufen kann? Wie verhält es sich mit neuen Funktionen?

Das Microsoft 365 Admin Center enthält einige dieser Informationen. Wenn Sie von einem Ereignis auf Dienstebene betroffen sind, sollte eine Kommunikations Warnung (in der Regel von einem Glockensymbol begleitet) angezeigt werden, nachdem Sie sich beim Microsoft 365 Admin Center angemeldet haben. Es wird empfohlen, dass Sie sämtliche zugehörigen Hinweise lesen und entsprechend vorgehen.

In Bezug auf neue EoP-Funktionen ist die [Roadmap von Microsoft 365 for Business](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) eine gute Ressource, um Informationen zu neuen Features zu finden. Außerdem werden Blog Artikel zu neuen Features auf der Website [Microsoft 365 Blogs](https://www.microsoft.com/microsoft-365/blog/) veröffentlicht.

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Funktioniert der Dienst mit älteren Exchange-Versionen (z. B. Exchange Server 2010) und in Umgebungen, die nicht auf Exchange basieren?

Ja, der Dienst ist serveragnostisch und kann mit einem beliebigen SMTP-E-Mail-Übertragungs-Agent verwendet werden.

## <a name="what-size-organization-can-use-the-service"></a>Welche Größe muss eine Organisation haben, um den Dienst verwenden zu können?

Die Größe spielt keine Rolle. Das EOP-Netzwerk bietet für das Wachstum Ihrer Organisation ausreichend Kapazität – unabhängig davon, wie schnell es erfolgt.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Welche Berechtigungen müssen für EOP eingerichtet werden?

Um EoP zu konfigurieren, müssen Sie ein globaler Administrator oder ein Exchange-Unternehmens Administrator (die Rollengruppe "Organisationsverwaltung") sein.

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Woher weiß ich, ob meine Daten und persönlichen Informationen sicher sind?

Informationen zu den Maßnahmen, die zum Schutz Ihrer Daten und persönlichen Informationen ergriffen wurden, sowie zu Vereinbarungen zum Servicelevel (Service Level Agreements, SLAs) finden Sie im [Office 365 Trust Center](https://www.microsoft.com/trust-center).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Gibt es Einschränkungen, die ich beachten sollte, beispielsweise Beschränkungen der Nachrichtengröße?

Ja. Weitere Informationen zu Grenzen in EOP finden Sie unter [Beschränkungen von Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="does-eop-support-powershell"></a>Unterstützt EoP PowerShell?

Ja, die vollständige EoP-Funktionalität steht über PowerShell zur Verfügung: Exchange Online PowerShell für Organisationen mit Exchange Online Postfächern; eigenständige EoP PowerShell für eigenständige EoP-Organisationen. Weitere Informationen finden Sie unter [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) und [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell).
