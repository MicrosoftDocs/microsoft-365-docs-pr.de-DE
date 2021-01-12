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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können häufig gestellte Fragen und Antworten zu isolierten Nachrichten in Exchange Online Protection (EOP) anzeigen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 58ddb5847706aef3d2c3b8ea8cd9a96fd65a9b3d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794412"
---
# <a name="quarantined-messages-faq"></a>Häufig gestellte Fragen zu isolierten Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dieses Thema enthält häufig gestellte Fragen und Antworten zu isolierten E-Mail-Nachrichten für Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständige Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer.

Fragen und Antworten zum Antispamschutz finden Sie unter Häufig gestellte Fragen zum [Antispamschutz.](anti-spam-protection-faq.md)

Fragen und Antworten zum Schutz vor Schadsoftware finden Sie unter Häufig gestellte Fragen zum [Schutz vor Schadsoftware.](anti-malware-protection-faq-eop.md)

Fragen und Antworten zum Schutz vor Spoofing finden Sie unter Häufig gestellte Fragen zum [Antis spoofing-Schutz.](anti-spoofing-protection-faq.md)

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Wie verwalte ich Nachrichten, die für Schadsoftware isoliert wurden?

Nur Administratoren können Nachrichten verwalten, die für Schadsoftware isoliert wurden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator.](manage-quarantined-messages-and-files.md)

## <a name="how-do-i-quarantine-spam"></a>Wie isoliere ich Spam?

Standardmäßig werden Nachrichten, die von der Spamfilterung als Spam oder Massen-E-Mail klassifiziert wurden, an das Postfach des Benutzers zugestellt und in den Junk-E-Mail-Ordner verschoben. Sie können jedoch antispamrichtlinien erstellen und konfigurieren, um Spam- oder Massen-E-Mail-Nachrichten stattdessen zu isolieren. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Wie vererbe ich Benutzern Zugriff auf die Quarantäne?

Ein Benutzer muss über ein gültiges Konto verfügen, um auf seine eigenen Nachrichten in Quarantäne zugreifen zu können. Für eigenständiges EOP müssen Benutzer als E-Mail-Benutzer in EOP dargestellt werden (manuell erstellt oder über die Verzeichnissynchronisierung erstellt). Weitere Informationen zum Verwalten von Benutzern in eigenständigen EOP-Umgebungen finden Sie unter [Verwalten von E-Mail-Benutzern in EOP.](manage-mail-users-in-eop.md)

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Auf welche Nachrichten können Endbenutzer in Quarantäne zugreifen?

Benutzer können auf Spam-, Massen-E-Mails und (ab April 2020) Phishingnachrichten zugreifen, bei denen sie Empfänger sind. Endbenutzer können nicht auf In-Quarantäne-Schadsoftware, Phishing mit hoher  Sicherheit oder Nachrichten zugreifen, die aufgrund der Aktion zum Isolieren der Nachricht an die gehostete Quarantäne in Nachrichtenflussregeln (auch als Transportregeln bekannt) isoliert wurden. Weitere Informationen zu Benutzern, die auf isolierte Nachrichten zugreifen, finden Sie unter "Suchen und Veröffentlichen von Isolierten Nachrichten [als Benutzer".](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Wie lange werden Nachrichten unter Quarantäne gestellt?

Sie konfigurieren mithilfe von Antispamrichtlinien, wie lange Spam-, Phishing- und Massen-E-Mail-Nachrichten in Quarantäne bleiben. Der Standardwert beträgt 30 Tage, was auch der Höchstwert ist. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)

Bei Nachrichten, die von der Nachrichtenflussregelaktion "Nachricht in gehostete Quarantäne isolieren" isoliert **wurden,** werden die Nachrichten 30 Tage lang in Quarantäne gehalten. Sie können diese Dauer nicht konfigurieren.

Nach Ablauf des Zeitraums werden die Nachrichten gelöscht und können nicht wiederhergestellt werden.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Kann ich mehr als eine Quarantänenachricht gleichzeitig freigeben oder melden?

Im Security & Compliance Center können Sie bis zu 100 Nachrichten gleichzeitig auswählen und frei geben.

Administratoren können die [Cmdlets "Get-QuarantineMessage"](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) und ["Release-QuarantineMessage"](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) in Exchange Online PowerShell oder in der eigenständigen EOP PowerShell verwenden, um isolierte Nachrichten in einer Massensendung zu finden und frei zu geben und falsch positive Ergebnisse als Massenmeldung zu melden.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Werden bei der Suche nach in der Quarantäne isolierte Nachrichten Platzhalterzeichen unterstützt? Kann ich für eine bestimmte Domäne nach Nachricht in Quarantäne suchen?

Platzhalter werden im Security & Compliance Center nicht unterstützt. Wenn Sie beispielsweise nach einem Absender suchen, müssen Sie die vollständige E-Mail-Adresse angeben. Sie können jedoch Platzhalter in Exchange Online PowerShell oder in der eigenständigen EOP PowerShell verwenden.

Führen Sie beispielsweise den folgenden Befehl aus, um Nachrichten in Spamquarantäne von allen Absendern in der Domäne contoso.com:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Führen Sie dann den folgenden Befehl aus, um diese Nachrichten für alle ursprünglichen Empfänger frei zu geben:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Nachdem Sie eine Nachricht freigegeben haben, können Sie sie nicht mehr los.
