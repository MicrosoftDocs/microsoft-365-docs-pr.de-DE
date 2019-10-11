---
title: Dienste für Nicht-Kunden, die E-Mails an Office 365 senden
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/2/2016
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
ms.openlocfilehash: 17d069a9bee76087790b608ba3c00bae9c644f99
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441222"
---
# <a name="services-for-non-customers-sending-mail-to-office-365"></a>Dienste für Nicht-Kunden, die E-Mails an Office 365 senden

E-Mail-Missbrauch, Junk-E-Mails und betrügerische E-Mails (Phishing) belasten weiterhin das gesamte E-Mail-Ökosystem. Damit Benutzer das Vertrauen in der Verwendung von E-Mails nicht verlieren, hat Microsoft verschiedene Richtlinien und Technologien zum Schutz von Benutzern eingeführt. Allerdings weiß Microsoft, dass seriösen E-Mails nicht negativ beeinträchtigt werden sollten. Daher haben wir eine Reihe von Diensten zusammengestellt, die Absendern dabei helfen, den E-Mail-Versand an Office 365-Benutzer durch proaktives Verwalten ihres Senderufs zu verbessern.

Diese Übersicht enthält Informationen zu Vorteilen, die wir Ihrer Organisation bereitstellen, auch wenn kein Office 365-Kunde sind.

## <a name="sender-solutions"></a>Absenderlösungen

|**Dienst**|**Vorteile**|
|:-----|:-----|
|Onlinehilfeinhalt| Beschreibung:  <br/>  Ausgangspunkt für alle Fragen im Zusammenhang mit der Bereitstellung von Kommunikation für EOP-Benutzer  <br/>  Enthält einen einfachen Onlineleitfaden mit unseren Richtlinien und Anforderungen  <br/>  Eine Übersicht über die Filter für Junk-E-Mails und Authentifizierungstechnologien, die von Microsoft eingesetzt werden|
|[Microsoft-Support](#microsoft-support)|Stellt Selbsthilfe und Weiterleitungssupport für Zustellungsprobleme bereit.|
|[Office 365-Anti-Spam-IP-Delist-Portal](#office-365-anti-spam-ip-delist-portal)|Ein Tool zum Übermitteln von Anforderungen zum Entfernen von IP-Adressen aus einer Liste. Vor dem Absenden dieser Anforderung hat der Absender die Verantwortung, sicherzustellen, dass alle weiteren E-Mails, die von der fraglichen IP-Adresse ausgehen, weder beleidigend noch böswillig sind.|
|[Missbrauchs- und Spammeldung für Junk-E-Mails aus Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Verhindert, dass Spam und andere unerwünschte E-Mails von Exchange Online gesendet werden und das Internet und Ihr E-Mail-System überfrachten.|

## <a name="microsoft-support"></a>Microsoft-Support

Microsoft bietet verschiedene Supportoptionen für Personen an, die Probleme beim Senden von E-Mails an Office 365-Postfächer haben. Wir empfehlen, dass Sie wie folgt vorgehen:

- Folgen Sie den Anweisungen in allen Unzustellbarkeitsberichten, die Sie erhalten.

- Sehen Sie sich die am häufigsten auftretenden Probleme an, die für Nicht-Kunden in [Problembehandlung für E-Mail-Nachrichten, die an Office 365 gesendet werden](troubleshooting-mail-sent-to-office-365.md) auftreten.

- Verwenden Sie das [Office 365-Delist-Portal](https://sender.office.com) für eine Anforderung, um Ihre IP-Adresse aus der Liste der blockierten Absender zu entfernen.

- Lesen Sie die [Microsoft-Communityforen](https://community.office365.com/en-us/f/).

- Wenden Sie sich unter Verwendung einer anderen Methode an den Office 365-Kunden, an den Sie E-Mails senden möchten, und bitten Sie ihn, den Microsoft-Support zu kontaktieren und ein Supportticket in Ihrem Auftrag zu öffnen. In einigen Fällen muss der Microsoft-Support aus rechtlichen Gründen direkt mit dem Absender kommunizieren, dem der gesperrte die IP-Adressraum gehört. Allerdings können Nicht-Kunden in der Regel keine Supporttickets öffnen.

  Weitere Informationen zum technischen Microsoft-Support für Office 365 finden Sie unter [Support](https://technet.microsoft.com/library/office-365-support.aspx).

## <a name="office-365-anti-spam-ip-delist-portal"></a>Office 365-Anti-Spam-IP-Delist-Portal

Hierbei handelt es sich um ein Self-Service-Portal, das Sie verwenden können, um sich selbst aus der Liste der blockierten Absender von Office 365 zu entfernen. Verwenden Sie dieses Portal, wenn Sie eine Fehlermeldung erhalten, wenn Sie versuchen, eine E-Mail an einen Empfänger zu senden, dessen E-Mail-Adresse sich in Office 365 befindet, und Sie der Meinung sind, dass keine Fehlermeldung auftreten sollte. Weitere Informationen finden Sie unter [Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender von Office 365 zu entfernen](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Missbrauchs- und Spammeldung für Junk-E-Mails aus Exchange Online

Manchmal wird Office 365 von Drittanbietern zum Senden von Junk-E-Mails entgegen den allgemeinen Geschäftsbedingungen und Nutzungsrichtlinien verwendet. Wenn Sie Junk-E-Mails von Office 365 erhalten, können Sie diese Nachrichten an [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) melden. Fügen Sie die anstößigen Nachrichten einschließlich der vollständigen Kopfzeile im RFC 5322- oder ARF-Format an. Outlook im Web-Benutzer können integrierte Tools zum Melden von Junk-E-Mails verwenden. Informationen finden Sie unter [Report junk email and phishing scams in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).
