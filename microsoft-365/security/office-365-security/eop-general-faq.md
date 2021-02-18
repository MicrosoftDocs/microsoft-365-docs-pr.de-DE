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
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Erhalten Sie Antworten auf die häufigsten allgemeinen Fragen zum in der Cloud gehosteten Exchange Online Protection (EOP)-E-Mail-Filterdienst.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1a1ce845ef50d7485113c211b0a8d7770ea57815
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290021"
---
# <a name="eop-general-faq"></a>EOP – Allgemeine häufig gestellte Fragen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection als eigenständige Lösung](exchange-online-protection-overview.md)

Hier werden die häufigsten allgemeinen Fragen zum cloudgehostenen E-Mail-Filterdienst Exchange Online Protection (EOP) beantwortet. Themen mit weiteren häufig gestellten Fragen (FAQs) finden Sie unter den folgenden Links:

- [Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten](eop-queued-deferred-and-bounced-messages-faq.md)

- [Häufig gestellte Fragen zur delegierten Verwaltung](delegated-administration-faq.md)

- [Häufig gestellte Fragen zum Antispamschutz](anti-spam-protection-faq.md)

- [Häufig gestellte Fragen (FAQ) zur Quarantäne](quarantine-faq.md)

- [Häufig gestellte Fragen zum Schutz vor Schadsoftware](anti-malware-protection-faq-eop.md)

- [Häufig gestellte Fragen zur Nachrichtenablaufverfolgung](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Was ist EOP?

EOP ist ein cloudgehosteter E-Mail-Filterdienst zum Schutz von Kunden vor Spam und Malware sowie zur Implementierung von benutzerdefinierten Richtlinienregeln. EOP ist in jedem Microsoft 365-Abonnement enthalten, das Exchange Online-Postfächer enthält. EOP steht auch als eigenständiges Angebot zum Schutz von lokalen E-Mail-Umgebungen zur Verfügung.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Wie kann ich mich für eine EOP-Testversion anmelden oder EOP kaufen?

Sie können sich über das Web auf der [Exchange Online Protection-Homepage](https://products.office.com/exchange/exchange-email-security-spam-protection) für eine EOP-Testversion anmelden oder EOP kaufen. Beachten Sie, dass die Funktionalität einer Testversion der eines bezahlten Abonnements entspricht und außerdem die Zusatzfeatures umfasst, die mit dem Abonnementplan [Exchange Enterprise CAL mit Service](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) geboten werden.

## <a name="how-is-eop-priced"></a>Was kostet EOP?

EOP wird auf Benutzerbasis lizenziert. Die aktuellen Preisinformationen finden Sie auf der [Exchange Online Protection-Homepage](https://products.office.com/exchange/exchange-email-security-spam-protection).

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Wie lange dauert es, um EOP in Produktion zu setzen?

Wenn Sie den MX-Eintrag gemäß den Anweisungen unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md) ändern, werden E-Mails sofort beim Durchlaufen von EOP gefiltert. Die Übertragung des MX-Eintrags über DNS kann 24 bis 48 Stunden dauern. Sie können Ihre Schutzeinstellungen während dieses Vorgangs jederzeit optimieren.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>Muss ich alle Features von Microsoft 365 verwenden, um EOP verwenden zu können? Was passiert, wenn ich nur den EOP-Schutz möchte und das alles ist?

Sie können EOP verwenden, um Ihre lokalen Postfächer zu schützen, ohne andere Features von Microsoft 365 zu verwenden. Dies wird als "eigenständiges Abonnement" bezeichnet. Eine Liste der EOP-Features finden Sie in der [Exchange Online Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Warum muss ich einen Microsoft 365-Mandanten benötigen, wenn ich mich für die E-Mail-Filterung über EOP ernenne?

Microsoft 365 ist der Name einer Sammlung von Produkten und Diensten, auf die über einen Microsoft 365-Mandanten zugegriffen werden kann. Denken Sie an den Microsoft 365-Mandanten als Ausgangspunkt, zu dem Sie Lizenzen für die E-Mail-Filterung hinzufügen können.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>Verfügt EOP über ein Kommunikationsportal, auf dem ich Informationen über bekannte Probleme und die zu erwartenden Lösungen abrufen kann? Wie verhält es sich mit neuen Funktionen?

Das Microsoft 365 Admin Center enthält einige dieser Informationen. Wenn Sie von einem Servicelevelereignis betroffen sind, sollte eine Kommunikationswarnung (in der Regel begleitet von einem Glockensymbol) angezeigt werden, nachdem Sie sich beim Microsoft 365 Admin Center anmelden. Es wird empfohlen, dass Sie sämtliche zugehörigen Hinweise lesen und entsprechend vorgehen.

Im Hinblick auf neue EOP-Features ist [die Microsoft 365 For](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) Business Roadmap eine gute Ressource, um Informationen zu bevorstehenden neuen Features zu erhalten. Außerdem veröffentlichen wir Blogartikel zu neuen Features auf der [Microsoft 365-Blogs-Website.](https://www.microsoft.com/microsoft-365/blog/)

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Funktioniert der Dienst mit älteren Exchange-Versionen (z. B. Exchange Server 2010) und in Umgebungen, die nicht auf Exchange basieren?

Ja, der Dienst ist serveragnostisch und kann mit einem beliebigen SMTP-E-Mail-Übertragungs-Agent verwendet werden.

## <a name="what-size-organization-can-use-the-service"></a>Welche Größe muss eine Organisation haben, um den Dienst verwenden zu können?

Die Größe spielt keine Rolle. Das EOP-Netzwerk bietet für das Wachstum Ihrer Organisation ausreichend Kapazität – unabhängig davon, wie schnell es erfolgt.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Welche Berechtigungen müssen für EOP eingerichtet werden?

Zum Konfigurieren von EOP müssen Sie ein globaler Administrator oder ein Exchange-Unternehmensadministrator (die Rollengruppe "Organisationsverwaltung").

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Woher weiß ich, ob meine Daten und persönlichen Informationen sicher sind?

Informationen zu den Maßnahmen, die zum Schutz Ihrer Daten und persönlichen Informationen ergriffen wurden, sowie zu Vereinbarungen zum Servicelevel (Service Level Agreements, SLAs) finden Sie im [Office 365 Trust Center](https://www.microsoft.com/trust-center).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Gibt es Beschränkungen, die ich beachten sollte, z. B. Beschränkungen der Nachrichtengröße?

Ja. Weitere Informationen zu Grenzen in EOP finden Sie unter [Beschränkungen von Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="does-eop-support-powershell"></a>Unterstützt EOP PowerShell?

Ja, die vollständige #A0 steht über PowerShell zur Verfügung: Exchange Online PowerShell für Organisationen mit Exchange Online-Postfächern; Eigenständige EOP PowerShell für eigenständige EOP-Organisationen. Weitere Informationen finden Sie unter [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) und [Exchange Online Protection PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)
