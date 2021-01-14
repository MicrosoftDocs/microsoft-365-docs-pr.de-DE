---
title: Melden von Spam-, Nichtspam- und Phishingnachrichten an Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Administratoren können sich über die verschiedenen Möglichkeiten informieren, um gute und schlechte Nachrichten und Dateien zur Analyse an Microsoft zu melden.
ms.openlocfilehash: 52ca0287e65fa338b06dc7df7c1e6c214af860c2
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865092"
---
# <a name="report-messages-and-files-to-microsoft"></a>Melden von Nachrichten und Dateien an Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer haben Benutzer und Administratoren mehrere verschiedene Methoden zum Melden von E-Mail-Nachrichten und Dateien an Microsoft.

****

|Methode|Beschreibung|
|---|---|
|[Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln](admin-submission.md)|Die empfohlene Berichterstellungsmethode für Administratoren in Organisationen mit Exchange Online-Postfächern (nicht verfügbar in EOP als eigenständige Lösung).|
|[Aktivieren des Berichtsnachrichts-Add-Ins](enable-the-report-message-add-in.md)|Kann mit Outlook und Outlook im Web (früher als Outlook Web App bekannt) verwendet werden. <p> In Abhängigkeit von Ihrem Abonnement sind Nachrichten, die Benutzer mit dem Add-in gemeldet haben, im [](view-email-security-reports.md#user-reported-messages-report) [Verwaltungsübermittlungsportal,](admin-submission.md)in den Ergebnissen der automatisierten Untersuchung und Reaktion [(AIR),](air-view-investigation-results.md)im Bericht über vom Benutzer gemeldete Nachrichten und im [Bedrohungs-Explorer verfügbar.](threat-explorer-views.md#email--submissions) <p> Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien.](user-submission.md)
|[Aktivieren des Phishing-Add-Ins "Melden"](enable-the-report-phish-add-in.md)|Kann mit Outlook und Outlook im Web (früher als Outlook Web App bekannt) verwendet werden. <p> In Abhängigkeit von Ihrem Abonnement sind Nachrichten, die Benutzer mit dem Add-in gemeldet haben, im [](view-email-security-reports.md#user-reported-messages-report) [Verwaltungsübermittlungsportal,](admin-submission.md)in den Ergebnissen der automatisierten Untersuchung und Reaktion [(AIR),](air-view-investigation-results.md)im Bericht über vom Benutzer gemeldete Nachrichten und im [Bedrohungs-Explorer verfügbar.](threat-explorer-views.md#email--submissions) <p> Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien.](user-submission.md)|
|[Installieren und Verwenden des Junk-E-Mail-Berichterstellungs-Add-Ins für Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Funktioniert nur in Outlook.|
|[Melden von Junk- und Phishing-E-Mails in Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Verwenden Sie die integrierten Funktionen in Outlook im Web für Organisationen mit Exchange Online-Postfächern (nicht verfügbar in EOP als eigenständige Lösung). <p> Nachrichten, die Benutzer melden, sind im [Verwaltungsübermittlungsportal verfügbar.](admin-submission.md) <p> Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien.](user-submission.md)|
|[Melden von Junk- und Phishing-E-Mails in Outlook für iOS und Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Verwenden Sie die integrierten Funktionen in Outlook für iOS und Android für Organisationen mit Exchange Online-Postfächern (nicht verfügbar in EOP als eigenständige Lösung). <p> Nachrichten, die Benutzer melden, sind im [Verwaltungsübermittlungsportal verfügbar.](admin-submission.md) <p> Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien.](user-submission.md)|
|[Manuelles Übermitteln von Nachrichten zur Analyse an Microsoft](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Senden Sie angefügte Nachrichten manuell an bestimmte Microsoft-E-Mail-Adressen für Spam, nicht für Spam und Phishing.|
|[Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Erfahren Sie, wie Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet) erstellen, die Sie benachrichtigt, wenn Benutzer Nachrichten zur Analyse an Microsoft melden.
|||
|[Übermitteln von Schadsoftware und Nicht-Schadsoftware zur Analyse an Microsoft](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Verwenden Sie die Microsoft Security Intelligence-Website, um Anlagen und andere Dateien zu übermitteln.|

Wenn die Spam- oder Phishingnachrichten isoliert und nicht zugestellt wurden, können Benutzer die Nachrichten über das Quarantäneportal im Security & Compliance Center an Microsoft melden. Weitere Informationen finden Sie unter "Suchen und Veröffentlichen von Nachrichten in Quarantäne [als Benutzer in Microsoft 365".](find-and-release-quarantined-messages-as-a-user.md)
