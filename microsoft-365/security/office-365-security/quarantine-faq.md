---
title: Häufig gestellte Fragen zu Nachrichten in Quarantäne
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
description: Administratoren können häufig gestellte Fragen und Antworten zu unter Quarantäne gestellten Nachrichten in Exchange Online Protection (EoP) anzeigen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 896a83d4a09e8d0fcafeb6885cf2c63b6d8bb045
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826789"
---
# <a name="quarantined-messages-faq"></a>Häufig gestellte Fragen zu Nachrichten in Quarantäne

Dieses Thema enthält häufig gestellte Fragen und Antworten zu isolierten e-Mail-Nachrichten für Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächern.

Fragen und Antworten zum Antispamschutz finden Sie unter [Anti-Spam Protection FAQ](anti-spam-protection-faq.md).

Fragen und Antworten zum Schutz vor Schadsoftware finden Sie unter [Anti-Malware Protection FAQ](anti-malware-protection-faq-eop.md).

Fragen und Antworten zum Schutz vor Spoofing finden Sie unter [Anti-Spoofing-Schutz – FAQ](anti-spoofing-protection-faq.md).

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Wie kann ich Nachrichten verwalten, die auf Schadsoftware unter Quarantäne gestellt wurden?

Nur Administratoren können Nachrichten verwalten, die auf Schadsoftware unter Quarantäne gestellt wurden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator](manage-quarantined-messages-and-files.md).

## <a name="how-do-i-quarantine-spam"></a>Wie kann ich Spam isolieren?

Standardmäßig werden Nachrichten, die durch Spamfilterung als Spam oder Massen-e-Mail klassifiziert werden, an das Postfach des Benutzers übermittelt und in den Junk-e-Mail-Ordner verschoben. Sie können jedoch Anti-Spam-Richtlinien erstellen und konfigurieren, um Spam-oder Massen-e-Mail-Nachrichten stattdessen zu isolieren. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Wie gebe ich Benutzern Zugriff auf die Quarantäne?

Ein Benutzer muss über ein gültiges Konto verfügen, um in der Quarantäne auf seine eigenen Nachrichten zuzugreifen. Eigenständige EoP erfordert, dass Benutzer als e-Mail-Benutzer in EoP dargestellt werden (manuell erstellt oder über die Verzeichnissynchronisierung erstellt). Weitere Informationen zum Verwalten von Benutzern in eigenständigen EoP-Umgebungen finden Sie unter [Verwalten von e-Mail-Benutzern in EoP](manage-mail-users-in-eop.md).

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Auf welche Nachrichten kann der Benutzer in der Quarantäne zugreifen?

Benutzer können auf Spam, Massen-e-Mails und (ab April 2020) Phishing-Nachrichten zugreifen, wenn Sie ein Empfänger sind. Endbenutzer können nicht auf isolierte Schadsoftware, Phishing mit hoher Zuverlässigkeit oder Nachrichten zugreifen, die aufgrund der **Nachrichtenübermittlung an die gehostete Quarantäne** Aktion in Nachrichtenfluss Regeln (auch bekannt als Transportregeln) unter Quarantäne gestellt wurden. Weitere Informationen zu Benutzern, die auf isolierte Nachrichten zugreifen, finden Sie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer](find-and-release-quarantined-messages-as-a-user.md).

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Wie lange werden Nachrichten in der Quarantäne aufbewahrt?

Sie konfigurieren, wie lange Spam-, Phishing-und Massen-e-Mail-Nachrichten mithilfe von antispamregeln in der Quarantäne aufbewahrt werden. Der Standardwert ist 30 Tage, was auch das Maximum ist. Weitere Informationen finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md)

Bei Nachrichten, die von der Aktion Nachrichtenfluss Regel unter Quarantäne gestellt wurden, die **Nachricht an die gehostete Quarantäne senden**, werden die Nachrichten 30 Tage lang in Quarantäne aufbewahrt. Diese Dauer kann nicht konfiguriert werden.

Nach Ablauf des Zeitraums werden die Nachrichten gelöscht und können nicht mehr hergestellt werden.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Kann ich mehr als eine Quarantänenachricht gleichzeitig freigeben oder melden?

Im Security & Compliance Center können Sie bis zu 100 Nachrichten gleichzeitig auswählen und freigeben.

Administratoren können die Cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) und [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) in Exchange Online PowerShell oder eigenständiger EoP-PowerShell verwenden, um isolierte Nachrichten massenhaft zu finden und freizugeben und falsch positive Ergebnisse in Massen zu melden.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Werden bei der Suche nach in der Quarantäne isolierte Nachrichten Platzhalterzeichen unterstützt? Kann ich für eine bestimmte Domäne nach Nachricht in Quarantäne suchen?

Platzhalter werden im Security & Compliance Center nicht unterstützt. Wenn Sie beispielsweise nach einem Absender suchen, müssen Sie die vollständige e-Mail-Adresse angeben. Sie können jedoch Platzhalter in Exchange Online PowerShell oder eigenständiger EoP PowerShell verwenden.

Führen Sie beispielsweise den folgenden Befehl aus, um nach Nachrichten mit Spamquarantäne von allen Absendern in der Domäne contoso.com zu suchen:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Führen Sie dann den folgenden Befehl aus, um diese Nachrichten an alle ursprünglichen Empfänger freizugeben:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Nachdem Sie eine Nachricht veröffentlicht haben, können Sie Sie nicht erneut freigeben.
