---
title: Melden von Spam-, Nichtspam- und Phishingnachrichten an Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
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
ms.openlocfilehash: 7b062c9529364e9fe26133fd1c039affcb8b7011
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689073"
---
# <a name="report-messages-and-files-to-microsoft"></a>Melden von Nachrichten und Dateien an Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer verfügen Benutzer und Administratoren über verschiedene Methoden zum Melden von E-Mail-Nachrichten und Dateien an Microsoft.

<br>

****

|Methode|Beschreibung|
|---|---|
|[Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln](admin-submission.md)|Die empfohlene Berichterstellungsmethode für Administratoren in Organisationen mit Exchange Online Postfächern (nicht verfügbar in eigenständigem EOP).|
|[Aktivieren der Berichtsnachricht oder der Phishing-Add-Ins melden](enable-the-report-message-add-in.md)|Funktioniert mit Outlook und Outlook im Web (früher als Outlook Web App). <p> Abhängig von Ihrem Abonnement sind Nachrichten, die Benutzer mit den Add-Ins gemeldet haben, im [Administrator-Übermittlungsportal,](admin-submission.md)im Air-Ergebnis [(Automated Investigation and Response),](air-view-investigation-results.md)im Bericht über von Benutzern gemeldete Nachrichten und im [Bedrohungs-Explorer verfügbar.](threat-explorer-views.md#email--submissions) [](view-email-security-reports.md#user-reported-messages-report) <p> Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen festgelegtes Postfach kopiert oder umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).
|[Melden falsch positiver und falsch negativer Ergebnisse in Outlook](report-false-positives-and-false-negatives.md)|Senden Sie falsch positive Ergebnisse (gute E-Mails, die blockiert oder an Junkordner gesendet wurden) und falsch negative Ergebnisse (unerwünschte E-Mails oder Phishingnachrichten, die an den Posteingang übermittelt wurden) mithilfe des Berichtsnachrichtenfeatures an Exchange Online Protection (EOP).|
|[Manuelles Übermitteln von Nachrichten zur Analyse an Microsoft](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Senden Sie angefügte Nachrichten manuell an bestimmte Microsoft-E-Mail-Adressen für Spam, nicht für Spam und Phishing.|
|[Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|Erfahren Sie, wie Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet) erstellen, die Sie benachrichtigt, wenn Benutzer Nachrichten zur Analyse an Microsoft melden.|
|[Übermitteln von Schadsoftware und Nicht-Schadsoftware zur Analyse an Microsoft](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Verwenden Sie die Microsoft Security Intelligence, um Anlagen und andere Dateien zu übermitteln.|
|

Wenn die Spam- oder Phishingnachrichten isoliert und nicht zugestellt wurden, können Benutzer die Nachrichten über das Quarantäneportal im Security & Compliance Center an Microsoft melden. Weitere Informationen finden Sie unter Suchen und Veröffentlichen isolierter Nachrichten [als Benutzer in Microsoft 365.](find-and-release-quarantined-messages-as-a-user.md)

> [!NOTE]
> Daten aus Übermittlungen an Microsoft befinden sich Office 365 compliance-Grenze in nordamerikanischen Rechenzentren. Die Daten werden von Analysten des Engineering-Teams überprüft, um die Effektivität der Filter zu verbessern.
