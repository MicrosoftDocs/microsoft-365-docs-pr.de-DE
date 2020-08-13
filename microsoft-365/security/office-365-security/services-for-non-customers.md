---
title: Dienste für nicht-Kunden, die e-Mails an Microsoft 365 senden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Damit Benutzer das Vertrauen in der Verwendung von E-Mails nicht verlieren, hat Microsoft verschiedene Richtlinien und Technologien zum Schutz von Benutzern eingeführt.
ms.openlocfilehash: 74389d3b975a0ffaebdc1619be40fd3ac74d72f4
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652657"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>Dienste für nicht-Kunden, die e-Mails an Microsoft 365 senden

E-Mail-Missbrauch, Junk-E-Mails und betrügerische E-Mails (Phishing) belasten weiterhin das gesamte E-Mail-Ökosystem. Um die Vertrauenswürdigkeit von Benutzern bei der Verwendung von e-Mail zu unterstützen, hat Microsoft verschiedene Richtlinien und Technologien eingeführt, um den Schutz unserer Benutzer zu gewährleisten. Allerdings weiß Microsoft, dass seriösen E-Mails nicht negativ beeinträchtigt werden sollten. Aus diesem Grund haben wir eine Reihe von Diensten eingerichtet, mit denen Absender ihre Fähigkeit, e-Mails an Microsoft 365-Benutzer zu übermitteln, durch proaktives Verwalten Ihrer Absenderzuverlässigkeit verbessern können.

Diese Übersicht enthält Informationen zu Vorteilen, die wir Ihrer Organisation bieten, auch wenn Sie kein Kunde sind.

## <a name="sender-solutions"></a>Absenderlösungen

****

|Dienst|Vorteile|
|---|---|
|Onlinehilfeinhalt|Beschreibung: <br/> Ausgangspunkt für alle Fragen im Zusammenhang mit der Bereitstellung von Kommunikation für EoP-Benutzer. <br/><br/> Enthält eine einfache Onlinedokumentation mit unseren Richtlinien und Anforderungen. <br/><br/> Eine Übersicht über die Junk-e-Mail-Filter und Authentifizierungstechnologien, die von Microsoft verwendet werden.|
|[Microsoft-Support](#microsoft-support)|Stellt Selbsthilfe und Weiterleitungssupport für Zustellungsprobleme bereit.|
|[Anti-Spam-IP-Delist-Portal](#anti-spam-ip-delist-portal)|Ein Tool zum Übermitteln von Anforderungen zum Entfernen von IP-Adressen aus einer Liste. Vor dem Absenden dieser Anforderung hat der Absender die Verantwortung, sicherzustellen, dass alle weiteren E-Mails, die von der fraglichen IP-Adresse ausgehen, weder beleidigend noch böswillig sind.|
|[Missbrauchs- und Spammeldung für Junk-E-Mails aus Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Verhindert, dass Spam und andere unerwünschte e-Mails von Exchange Online gesendet und das Internet und Ihr e-Mail-System überladen werden.|
|

## <a name="microsoft-support"></a>Microsoft-Support

Microsoft bietet verschiedene Supportoptionen für Benutzer, die Probleme beim Senden von e-Mails an Microsoft 365-Empfänger haben. Wir empfehlen, dass Sie wie folgt vorgehen:

- Folgen Sie den Anweisungen in allen Unzustellbarkeitsberichten, die Sie erhalten.

- Sehen Sie sich die am häufigsten auftretenden Probleme an, die für Nicht-Kunden in [Problembehandlung für E-Mail-Nachrichten, die an Office 365 gesendet werden](troubleshooting-mail-sent-to-office-365.md) auftreten.

- Verwenden Sie das [Microsoft 365-Delist-Portal](https://sender.office.com) , um eine Anforderung zu übermitteln, Ihre IP aus der Liste des blockierten Absenders zu entfernen.

- Lesen Sie die [Microsoft-Communityforen](https://community.office365.com/f/).

- Wenden Sie sich an den Kunden, den Sie mit einer anderen Methode per e-Mail versuchen, und bitten Sie ihn, sich an den Microsoft-Support zu wenden und ein Support Ticket in Ihrem Namen zu öffnen. In einigen Fällen muss der Microsoft-Support aus rechtlichen Gründen direkt mit dem Absender kommunizieren, dem der gesperrte die IP-Adressraum gehört. Allerdings können Nicht-Kunden in der Regel keine Supporttickets öffnen.

  Weitere Informationen zum technischen Microsoft-Support für Office 365 finden Sie unter [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).

## <a name="anti-spam-ip-delist-portal"></a>Anti-Spam-IP-Delist-Portal

Hierbei handelt es sich um ein Self-Service-Portal, das Sie verwenden können, um sich selbst aus der Liste der blockierten Absender von Microsoft 365 zu entfernen. Verwenden Sie dieses Portal, wenn Sie eine Fehlermeldung erhalten, wenn Sie versuchen, eine e-Mail an einen Empfänger zu senden, dessen e-Mail-Adresse sich in Microsoft 365 befindet, und Sie glauben, dass dies nicht der Fall sein sollte. Weitere Informationen finden Sie unter [Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender zu entfernen](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Missbrauchs- und Spammeldung für Junk-E-Mails aus Exchange Online

Manchmal wird Microsoft365 von Drittanbietern zum Senden von Junk-e-Mails verwendet, was gegen unsere Nutzungsbedingungen und Richtlinien verstößt. Wenn Sie eine Junk-e-Mail von Office 365 erhalten, können Sie diese Nachrichten an Microsoft melden. Anweisungen finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).
