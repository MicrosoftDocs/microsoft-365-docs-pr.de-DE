---
title: Dienste für Nichtkunden, die E-Mails an Microsoft 365 senden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Damit Benutzer das Vertrauen in der Verwendung von E-Mails nicht verlieren, hat Microsoft verschiedene Richtlinien und Technologien zum Schutz von Benutzern eingeführt.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206514"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>Dienste für Nichtkunden, die E-Mails an Microsoft 365 senden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


E-Mail-Missbrauch, Junk-E-Mails und betrügerische E-Mails (Phishing) belasten weiterhin das gesamte E-Mail-Ökosystem. Um das Vertrauen der Benutzer in die Verwendung von E-Mails zu erhalten, hat Microsoft verschiedene Richtlinien und Technologien zum Schutz unserer Benutzer entwickelt. Allerdings weiß Microsoft, dass seriösen E-Mails nicht negativ beeinträchtigt werden sollten. Aus diesem Grund haben wir eine Reihe von Diensten eingerichtet, mit deren Hilfe Absender ihre Fähigkeit verbessern können, E-Mails an Microsoft 365-Benutzer zu senden, indem sie ihre Sendere reputation proaktiv verwalten.

Diese Übersicht enthält Informationen zu Vorteilen, die wir Ihrer Organisation bieten, auch wenn Sie kein Kunde sind.

## <a name="sender-solutions"></a>Absenderlösungen

****

|Dienst|Vorteile|
|---|---|
|Onlinehilfeinhalt|Beschreibung: <ul><li>Ein Ausgangspunkt für alle Fragen im Zusammenhang mit der Bereitstellung von Kommunikationen an EOP-Benutzer.</li><li>Enthält eine einfache Onlineanleitung mit unseren Richtlinien und Anforderungen.</li><li>Eine Übersicht über die Junk-E-Mail-Filter und Authentifizierungstechnologien, die von Microsoft verwendet werden.</li><ul>|
|[Microsoft-Support](#microsoft-support)|Stellt Selbsthilfe und Weiterleitungssupport für Zustellungsprobleme bereit.|
|[Antispam-IP-Listenportal](#anti-spam-ip-delist-portal)|Ein Tool zum Übermitteln von Anforderungen zum Entfernen von IP-Adressen aus einer Liste. Vor dem Absenden dieser Anforderung hat der Absender die Verantwortung, sicherzustellen, dass alle weiteren E-Mails, die von der fraglichen IP-Adresse ausgehen, weder beleidigend noch böswillig sind.|
|[Missbrauchs- und Spammeldung für Junk-E-Mails aus Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Verhindert, dass Spam und andere unerwünschte E-Mails von Exchange Online gesendet werden und das Internet und Ihr E-Mail-System überladen.|
|

## <a name="microsoft-support"></a>Microsoft-Support

Microsoft bietet mehrere Supportoptionen für Personen, die Probleme beim Senden von E-Mails an Microsoft 365-Empfänger haben. Wir empfehlen, dass Sie wie folgt vorgehen:

- Folgen Sie den Anweisungen in allen Unzustellbarkeitsberichten, die Sie erhalten.

- Sehen Sie sich die am häufigsten auftretenden Probleme an, die für Nicht-Kunden in [Problembehandlung für E-Mail-Nachrichten, die an Office 365 gesendet werden](troubleshooting-mail-sent-to-office-365.md) auftreten.

- Verwenden Sie [das Microsoft 365-Listendelist-Portal,](https://sender.office.com) um eine Anforderung zu senden, damit Ihre IP aus der Liste blockierter Absender entfernt wird.

- Lesen Sie die [Microsoft-Communityforen](https://community.office365.com/f/).

- Wenden Sie sich an den Kunden, den Sie mit einer anderen Methode per E-Mail kontaktieren möchten, und bitten Sie ihn, sich an den Microsoft-Support zu wenden und in Ihrem Namen ein Supportticket zu öffnen. In einigen Fällen muss der Microsoft-Support aus rechtlichen Gründen direkt mit dem Absender kommunizieren, dem der gesperrte die IP-Adressraum gehört. Allerdings können Nicht-Kunden in der Regel keine Supporttickets öffnen.

  Weitere Informationen zum technischen Microsoft-Support für Office 365 finden Sie unter [Support](/office365/servicedescriptions/office-365-platform-service-description/support).

## <a name="anti-spam-ip-delist-portal"></a>Antispam-IP-Listenportal

Dies ist ein Self-Service-Portal, mit dem Sie sich selbst aus der Liste blockierter Absender von Microsoft 365 entfernen können. Verwenden Sie dieses Portal, wenn Sie eine Fehlermeldung erhalten, wenn Sie versuchen, eine E-Mail an einen Empfänger zu senden, dessen E-Mail-Adresse sich in Microsoft 365 befindet und Sie nicht denken, dass Sie dies sein sollten. Weitere Informationen finden Sie unter [Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender zu entfernen](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Missbrauchs- und Spammeldung für Junk-E-Mails aus Exchange Online

Manchmal wird Microsoft365 von Drittanbietern verwendet, um Junk-E-Mails zu senden, und dies unter Verstoß gegen unsere Nutzungsbedingungen und Richtlinien. Wenn Sie Junk-E-Mails von Office 365 erhalten, können Sie diese Nachrichten an Microsoft melden. Anweisungen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).