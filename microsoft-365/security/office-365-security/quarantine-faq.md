---
title: Häufig gestellte Fragen zu isolierten Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können häufig gestellte Fragen und Antworten zu isolierten Nachrichten in Exchange Online Protection (EOP) anzeigen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 112f8a9f0714d962f8ea18ade5455178ba773858
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908842"
---
# <a name="quarantined-messages-faq"></a>Häufig gestellte Fragen zu isolierten Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Dieses Thema enthält häufig gestellte Fragen und Antworten zu isolierten E-Mail-Nachrichten für Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer.

Fragen und Antworten zum Antispamschutz finden Sie unter Häufig gestellte Fragen zu [Antispamschutz](anti-spam-protection-faq.md).

Fragen und Antworten zum Schutz vor Schadsoftware finden Sie unter Häufig gestellte Fragen zum Schutz [vor Schadsoftware.](anti-malware-protection-faq-eop.md)

Fragen und Antworten zum Schutz vor Spoofing finden Sie unter Häufig gestellte Fragen zum Schutz [vor Spoofing.](anti-spoofing-protection-faq.md)

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Wie verwalte ich Nachrichten, die für Schadsoftware isoliert wurden?

Nur Administratoren können Nachrichten verwalten, die für Schadsoftware isoliert wurden. Weitere Informationen finden Sie unter [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).

## <a name="how-do-i-quarantine-spam"></a>Wie isoliere ich Spam?

Standardmäßig werden Nachrichten, die per Spamfilterung als Spam oder Massen-E-Mail klassifiziert werden, an das Postfach des Benutzers zugestellt und in den Junk-E-Mail-Ordner verschoben. Sie können jedoch Antispamrichtlinien erstellen und konfigurieren, um Spam- oder Massen-E-Mail-Nachrichten zu isolieren. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Wie kann ich Benutzern Zugriff auf die Quarantäne ermöglichen?

Ein Benutzer muss über ein gültiges Konto verfügen, um in Quarantäne auf eigene Nachrichten zugreifen zu können. Eigenständiges EOP erfordert, dass Benutzer in EOP als E-Mail-Benutzer dargestellt werden (manuell erstellt oder über die Verzeichnissynchronisierung erstellt). Weitere Informationen zum Verwalten von Benutzern in eigenständigen EOP-Umgebungen finden Sie unter [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Auf welche Nachrichten können Endbenutzer in Quarantäne zugreifen?

Benutzer können auf Spam-, Massen-E-Mails und (ab April 2020) Phishingnachrichten zugreifen, wenn sie Empfänger sind. Endbenutzer können nicht auf isolierte Schadsoftware, Phishing mit hoher  Vertrauenssicherheit oder Nachrichten zugreifen, die aufgrund der Nachricht an die gehostete Quarantäneaktion in Nachrichtenflussregeln (auch als Transportregeln bekannt) isoliert wurden. Weitere Informationen zu Benutzern, die auf isolierte Nachrichten zugreifen, finden Sie unter Suchen und Veröffentlichen isolierter Nachrichten [als Benutzer.](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Wie lange werden Nachrichten in der Quarantäne aufbewahrt?

Sie konfigurieren, wie lange Spam-, Phishing- und Massen-E-Mail-Nachrichten mithilfe von Antispamrichtlinien in der Quarantäne aufbewahrt werden. Der Standardwert ist 30 Tage, was auch das Maximum ist. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)

Für Nachrichten, die von der Nachrichtenflussregelaktion isoliert wurden **Die** Nachricht in die gehostete Quarantäne senden, werden die Nachrichten 30 Tage lang in Quarantäne gehalten. Sie können diese Dauer nicht konfigurieren.

Nach Ablauf des Zeitraums werden die Nachrichten gelöscht und können nicht mehr wiederhergestellt werden.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Kann ich mehr als eine Quarantänenachricht gleichzeitig freigeben oder melden?

Im Security & Compliance Center können Sie bis zu 100 Nachrichten gleichzeitig auswählen und veröffentlichen.

Administratoren können die [Cmdlets Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) und [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage) in Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwenden, um isolierte Nachrichten in Massen zu finden und frei zu geben und falsch positive Ergebnisse in Massen zu melden.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Werden bei der Suche nach in der Quarantäne isolierte Nachrichten Platzhalterzeichen unterstützt? Kann ich für eine bestimmte Domäne nach Nachricht in Quarantäne suchen?

Platzhalter werden im Security & Compliance Center nicht unterstützt. Wenn Sie beispielsweise nach einem Absender suchen, müssen Sie die vollständige E-Mail-Adresse angeben. Sie können jedoch Platzhalter in Exchange Online PowerShell oder in der eigenständigen EOP PowerShell verwenden.

Kopieren Sie beispielsweise den folgenden PowerShell-Code in NotePad, und speichern Sie die Datei als PS1 an einem Speicherort, den Sie leicht finden können (z. B. C:\Data\QuarantineRelease.ps1).

Führen Sie dann nach der Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) oder [Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)den folgenden Befehl aus, um das Skript auszuführen:

```powershell
& C:\Data\QuarantineRelease.ps1
```

Das Skript führt die folgenden Aktionen aus:

- Suchen Sie unveröffentlichte Nachrichten, die von allen Absendern in der fabrikam-Domäne als Spam isoliert wurden. Die maximale Anzahl der Ergebnisse beträgt 50.000 (50 Seiten mit 1.000 Ergebnissen).
- Speichern Sie die Ergebnisse in einer CSV-Datei.
- Geben Sie die übereinstimmenden isolierten Nachrichten für alle ursprünglichen Empfänger frei.

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

Nachdem Sie eine Nachricht veröffentlicht haben, können Sie sie nicht mehr veröffentlichen.