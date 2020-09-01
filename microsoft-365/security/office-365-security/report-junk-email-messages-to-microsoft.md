---
title: Melden von Spam-, nicht-Spam-und Phishing-Nachrichten an Microsoft
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
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Administratoren können Informationen zu den unterschiedlichen Möglichkeiten zum Melden von guten und schlechten Nachrichten und Dateien an Microsoft zur Analyse erhalten.
ms.openlocfilehash: cff9d1b3524200fba9d7ba1775e0b9851027158d
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315863"
---
# <a name="report-messages-and-files-to-microsoft"></a>Melden von Nachrichten und Dateien an Microsoft

In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer haben sowohl Benutzer als auch Administratoren verschiedene Methoden zum Melden von e-Mail-Nachrichten und Dateien an Microsoft.

****

|Methode|Beschreibung|
|---|---|
|[Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln](admin-submission.md)|Die empfohlene Berichtsmethode für Administratoren in Organisationen mit Exchange Online Postfächern (nicht verfügbar in eigenständigen EoP).|
|[Aktivieren des Berichtsnachrichts-Add-Ins](enable-the-report-message-add-in.md)|Funktioniert mit Outlook, Outlook für Mac und Outlook im Internet (früher bekannt als Outlook Web App) und ist das empfohlene Add-in. <br/><br/> Je nach Ihrem Abonnement sind Nachrichten, die Benutzer mit dem Add-in gemeldet haben, im [Portal "admin-Übermittlungen"](admin-submission.md), in [automatischen Untersuchungen und Antwort Ergebnissen (Air)](air-view-investigation-results.md), im Bericht über vom [Benutzer gemeldeten Nachrichten](view-email-security-reports.md#user-reported-messages-report)und im [Bedrohungs-Explorer](threat-explorer-views.md#email--submissions)verfügbar. <br/><br/> Sie können gemeldete Nachrichten so konfigurieren, dass Sie kopiert oder an ein von Ihnen angegebenes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [Angeben eines Postfachs für Benutzer Übermittlungen von Spam-und Phishing-Nachrichten in EoP](user-submission.md).|
|[Installieren und Verwenden des Add-Ins für die Junk-e-Mail-Berichterstellung für Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Funktioniert nur in Outlook.|
|[Melden von Junk-und Phishing-e-Mails in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Verwenden Sie die integrierten Funktionen in Outlook im Internet für Organisationen mit Exchange Online Postfächern (nicht verfügbar in eigenständigen EoP). <br/><br/> Nachrichten, die von Benutzern gemeldet werden, stehen im [Portal für die Übermittlungen von Administratoren](admin-submission.md)zur Verfügung. <br/><br/> Sie können gemeldete Nachrichten so konfigurieren, dass Sie kopiert oder an ein von Ihnen angegebenes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [Angeben eines Postfachs für Benutzer Übermittlungen von Spam-und Phishing-Nachrichten in Exchange Online](user-submission.md).|
|[Melden von Junk-und Phishing-e-Mails in Outlook für IOS und Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Verwenden Sie die integrierten Funktionen in Outlook für IOS, ein Android für Organisationen mit Exchange Online-Postfächern (nicht verfügbar in eigenständigen EoP). <br/><br/> Nachrichten, die von Benutzern gemeldet werden, stehen im [Portal für die Übermittlungen von Administratoren](admin-submission.md)zur Verfügung. <br/><br/> Sie können gemeldete Nachrichten so konfigurieren, dass Sie kopiert oder an ein von Ihnen angegebenes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [Angeben eines Postfachs für Benutzer Übermittlungen von Spam-und Phishing-Nachrichten in Exchange Online](user-submission.md).|
|[Manuelles übermitteln von Nachrichten an Microsoft zur Analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Manuelles Senden angefügter Nachrichten an bestimmte Microsoft-e-Mail-Adressen für Spam, nicht Spam und Phishing.|
|[Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Erfahren Sie, wie Sie eine e-Mail-Fluss Regel (auch als Transportregel bezeichnet) erstellen, in der Sie benachrichtigt werden, wenn Benutzer Nachrichten an Microsoft zur Analyse melden.
|||
|[Übermitteln von Schadsoftware und nicht-Schadsoftware an Microsoft zur Analyse](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Verwenden Sie die Microsoft Security Intelligence-Website, um Anlagen und andere Dateien zu übermitteln.|
|

Wenn die Spam-oder Phishing-Nachrichten in Quarantäne statt zugestellt wurden, können Benutzer die Nachrichten über das Quarantäne Portal im Security & Compliance Center an Microsoft melden. Ausführliche Informationen finden Sie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).
