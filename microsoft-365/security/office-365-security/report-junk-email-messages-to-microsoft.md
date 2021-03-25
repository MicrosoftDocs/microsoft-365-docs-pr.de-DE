---
title: Melden von Spam-, Nichtspam- und Phishingnachrichten an Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Administratoren können sich über die verschiedenen Möglichkeiten informieren, um gute und schlechte Nachrichten und Dateien zur Analyse an Microsoft zu melden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 64b5708194d7597b8a2b1a84b51f2196415e56ea
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206604"
---
# <a name="report-messages-and-files-to-microsoft"></a>Melden von Nachrichten und Dateien an Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer verfügen Benutzer und Administratoren über verschiedene Methoden zum Melden von E-Mail-Nachrichten und Dateien an Microsoft.

****

|Methode|Beschreibung|
|---|---|
|[Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln](admin-submission.md)|Die empfohlene Berichterstellungsmethode für Administratoren in Organisationen mit Exchange Online-Postfächern (nicht verfügbar in eigenständigem EOP).|
|[Aktivieren des Berichtsnachrichts-Add-Ins](enable-the-report-message-add-in.md)|Funktioniert mit Outlook und Outlook im Web (früher als Outlook Web App bekannt). <p> Abhängig von Ihrem Abonnement sind Nachrichten, die Benutzer mit dem Add-In gemeldet haben, im [Administrator-Übermittlungsportal,](admin-submission.md)den Ergebnissen der automatisierten Untersuchung und Reaktion [(Automated Investigation and Response, AIR),](air-view-investigation-results.md)dem Bericht über von Benutzern gemeldete Nachrichten und dem [Bedrohungs-Explorer verfügbar.](threat-explorer-views.md#email--submissions) [](view-email-security-reports.md#user-reported-messages-report) <p> Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen festgelegtes Postfach kopiert oder umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).
|[Aktivieren des Add-Ins „Phishing melden“](enable-the-report-phish-add-in.md)|Funktioniert mit Outlook und Outlook im Web (früher als Outlook Web App bekannt). <p> Abhängig von Ihrem Abonnement sind Nachrichten, die Benutzer mit dem Add-In gemeldet haben, im [Administrator-Übermittlungsportal,](admin-submission.md)den Ergebnissen der automatisierten Untersuchung und Reaktion [(Automated Investigation and Response, AIR),](air-view-investigation-results.md)dem Bericht über von Benutzern gemeldete Nachrichten und dem [Bedrohungs-Explorer verfügbar.](threat-explorer-views.md#email--submissions) [](view-email-security-reports.md#user-reported-messages-report) <p> Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen festgelegtes Postfach kopiert oder umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).|
|[Installieren und Verwenden des Junk-E-Mail-Berichts-Add-Ins für Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Funktioniert nur in Outlook.|
|[Melden von Junk- und Phishing-E-Mails in Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Verwenden Sie die integrierten Funktionen in Outlook im Web für Organisationen mit Exchange Online-Postfächern (nicht verfügbar in eigenständigem EOP). <p> Nachrichten, die Benutzer melden, sind im [Administrator-Übermittlungsportal verfügbar.](admin-submission.md) <p> Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen festgelegtes Postfach kopiert oder umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).|
|[Melden von Junk- und Phishing-E-Mails in Outlook für iOS und Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Verwenden Sie die integrierten Funktionen in Outlook für iOS und Android für Organisationen mit Exchange Online-Postfächern (nicht verfügbar in eigenständigem EOP). <p> Nachrichten, die Benutzer melden, sind im [Administrator-Übermittlungsportal verfügbar.](admin-submission.md) <p> Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen festgelegtes Postfach kopiert oder umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).|
|[Manuelles Übermitteln von Nachrichten zur Analyse an Microsoft](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Senden Sie angefügte Nachrichten manuell an bestimmte Microsoft-E-Mail-Adressen für Spam, nicht für Spam und Phishing.|
|[Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Erfahren Sie, wie Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet) erstellen, die Sie benachrichtigt, wenn Benutzer Nachrichten zur Analyse an Microsoft melden.|
|[Übermitteln von Schadsoftware und Nicht-Schadsoftware zur Analyse an Microsoft](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Verwenden Sie die Microsoft Security Intelligence-Website, um Anlagen und andere Dateien zu übermitteln.|

Wenn die Spam- oder Phishingnachrichten isoliert und nicht zugestellt wurden, können Benutzer die Nachrichten über das Quarantäneportal im Security & Compliance Center an Microsoft melden. Weitere Informationen finden Sie unter Suchen und Veröffentlichen isolierter Nachrichten [als Benutzer in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).

> [!NOTE]
> Daten aus Übermittlungen an Microsoft befinden sich an der Office 365-Compliancegrenze in nordamerikanischen Rechenzentren. Die Daten werden von Analysten des Engineering-Teams überprüft, um die Effektivität der Filter zu verbessern.
