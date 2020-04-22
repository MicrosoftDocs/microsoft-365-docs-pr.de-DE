---
title: Häufig gestellte Fragen (FAQ) zur Quarantäne
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Antworten auf häufig gestellte Fragen zur Quarantäne in Office 365.
ms.openlocfilehash: 3947fbed2a17380a18320a8bffd08a8178ad2b3f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634424"
---
# <a name="quarantine-faq"></a>Häufig gestellte Fragen (FAQ) zur Quarantäne

Dieses Thema enthält häufig gestellte Fragen und Antworten zur Quarantäne für Microsoft 365-Kunden mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutz Kunden (EoP) ohne Exchange Online Postfächer.

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a>F: Wie kann ich Nachrichten verwalten, die auf Schadsoftware unter Quarantäne gestellt wurden?

Nur Administratoren können Nachrichten verwalten, die auf Schadsoftware unter Quarantäne gestellt wurden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365](manage-quarantined-messages-and-files.md).

## <a name="q-how-do-i-quarantine-spam"></a>F: Wie kann ich Spam isolieren?

A: Standardmäßig werden Nachrichten, die durch Spamfilterung als Spam oder Massen-e-Mail klassifiziert werden, an das Postfach des Benutzers übermittelt und in den Junk-e-Mail-Ordner verschoben. Sie können jedoch Anti-Spam-Richtlinien erstellen und konfigurieren, um Spam-oder Massen-e-Mail-Nachrichten stattdessen zu isolieren. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a>F.: Wie kann ich Benutzern Zugriff auf die Quarantäne gewähren?

A: Ein Benutzer muss über ein gültiges Konto verfügen, um in der Quarantäne auf seine eigenen Nachrichten zuzugreifen. Eigenständige EoP erfordert, dass Benutzer als e-Mail-Benutzer in EoP dargestellt werden (manuell erstellt oder über die Verzeichnissynchronisierung erstellt). Weitere Informationen zum Verwalten von Benutzern in eigenständigen EoP-Umgebungen finden Sie unter [Verwalten von e-Mail-Benutzern in EoP](manage-mail-users-in-eop.md).

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a>F.: auf welche Nachrichten kann der Benutzer in der Quarantäne zugreifen?

A: Benutzer können auf Spam, Massen-e-Mails und (ab April 2020) Phishing-Nachrichten, bei denen es sich um einen Empfänger handelt, zugreifen. Endbenutzer können nicht auf isolierte Schadsoftware, Phishing mit hoher Zuverlässigkeit oder Nachrichten zugreifen, die aufgrund der **Nachrichtenübermittlung an die gehostete Quarantäne** Aktion in Nachrichtenfluss Regeln (auch bekannt als Transportregeln) unter Quarantäne gestellt wurden. Weitere Informationen zu Benutzern, die auf isolierte Nachrichten zugreifen, finden Sie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer in Office 365](find-and-release-quarantined-messages-as-a-user.md).

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a>F.: wie lange werden Nachrichten in der Quarantäne aufbewahrt?

A: Sie konfigurieren, wie lange Spam-, Phishing-und Massen-e-Mail-Nachrichten mithilfe von antispamregeln in der Quarantäne aufbewahrt werden. Der Standardwert ist 30 Tage, was auch das Maximum ist. Weitere Informationen finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md)

Bei Nachrichten, die von der Aktion Nachrichtenfluss Regel unter Quarantäne gestellt wurden, die **Nachricht an die gehostete Quarantäne senden**, werden die Nachrichten 30 Tage lang in Quarantäne aufbewahrt. Diese Dauer kann nicht konfiguriert werden.

Nach Ablauf des Zeitraums werden die Nachrichten gelöscht und können nicht mehr hergestellt werden.

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>F.: kann ich mehr als eine isolierte Nachricht gleichzeitig freigeben oder melden?

A: Im Security & Compliance Center können Sie bis zu 100 Nachrichten gleichzeitig auswählen und freigeben.

Administratoren können die Cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) und [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) in Exchange Online PowerShell oder eigenständiger Exchange Online Protection PowerShell verwenden, um isolierte Nachrichten massenhaft zu finden und freizugeben und falsch positive Ergebnisse in Massen zu melden.

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>F.: werden Platzhalter bei der Suche nach isolierten Nachrichten unterstützt? Kann ich für eine bestimmte Domäne nach Nachricht in Quarantäne suchen?

A: Platzhalter werden im Security & Compliance Center nicht unterstützt. Wenn Sie beispielsweise nach einem Absender suchen, müssen Sie die vollständige e-Mail-Adresse angeben. Sie können jedoch Platzhalter in Exchange Online PowerShell oder Exchange Online Protection PowerShell verwenden.

Führen Sie beispielsweise den folgenden Befehl aus, um nach Nachrichten mit Spamquarantäne von allen Absendern in der Domäne contoso.com zu suchen:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Führen Sie dann den folgenden Befehl aus, um diese Nachrichten an alle ursprünglichen Empfänger freizugeben:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Nachdem Sie eine Nachricht veröffentlicht haben, können Sie Sie nicht erneut freigeben.
