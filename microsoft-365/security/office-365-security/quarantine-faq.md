---
title: Häufig gestellte Fragen (FAQ) zur Quarantäne
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
description: Unter diesem Thema werden häufig gestellte Fragen und Antworten zur gehosteten Quarantäne bereitgestellt.
ms.openlocfilehash: b4112bf785a6ee2f4c833ab08d2c199388585093
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598662"
---
# <a name="quarantine-faq"></a>Häufig gestellte Fragen (FAQ) zur Quarantäne

Unter diesem Thema werden häufig gestellte Fragen und Antworten zur gehosteten Quarantäne bereitgestellt. Die Antworten richten sich an Kunden von Microsoft Exchange Online und Exchange Online Protection.

 **F. Wie verwalte ich Nachrichten mit Schadsoftware in Quarantäne?**

Sie müssen das Security #a0 Compliance Center verwenden, um Nachrichten anzuzeigen und zu bearbeiten, die an die Quarantäne gesendet wurden, da Sie Schadsoftware enthalten. Weitere Informationen finden Sie unter [Quarantäne für e-Mail-Nachrichten in Office 365](quarantine-email-messages.md).

 **F. Wie wird der Dienst konfiguriert, damit Spamnachrichten in Quarantäne gesendet werden?**

A. Standardmäßig werden durch die Inhaltsfilterung abgefangene Nachrichten an den Junk-E-Mail-Ordner des Empfängers gesendet. Als Administrator können Sie Richtlinien für die Inhaltsfilterung jedoch auch so konfigurieren, dass Spamnachrichten stattdessen in Quarantäne verschoben werden. Weitere Informationen zu den verschiedenen Aktionen, die bei inhaltsgefilterten Nachrichten durchgeführt werden können, finden Sie unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md).

 **F. Bietet der Dienst Administrator- und Endbenutzerverwaltung von Nachrichten in der Spamquarantäne?**

A: Als Administrator können Sie im Security and Compliance Center (SCC) nach Details zu allen isolierten e-Mail-Nachrichten suchen und diese anzeigen. Nach dem Auffinden der Nachricht können Sie sie für bestimmte Benutzer freigeben und dem Microsoft-Spamanalyseteam optional als falsch positiv (kein Junk) melden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365](manage-quarantined-messages-and-files.md).

Als Endbenutzer können Sie Ihre eigenen Nachrichten in der Spamquarantäne verwalten über:

- Der Spam-Quarantäne-Benutzeroberfläche. Weitere Informationen finden Sie unter [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Office 365](find-and-release-quarantined-messages-as-a-user.md).

 **F. wie erteile ich dem Benutzer Zugriff auf Quarantäne?**

A: Für den Zugriff auf die Spam-Quarantäne von Endbenutzern benötigen Endbenutzer eine gültige Office 365-Benutzer-ID samt Kennwort. EoP Kunden, die lokale Postfächer schützen, müssen gültige e-Mail-Benutzer sein, die über die Verzeichnissynchronisierung oder die Exchange-Verwaltungskonsole erstellt werden. Weitere Informationen zum Verwalten von Benutzern finden Sie in den EoP-Administratoren unter [Verwalten von e-Mail-Benutzern in EoP](manage-mail-users-in-eop.md). Für EoP-eigenständige Kunden empfehlen wir die Verwendung der Verzeichnissynchronisierung und die Aktivierung der verzeichnisbasierten Edge-Blockierung; Weitere Informationen finden Sie unter [Verwenden der verzeichnisbasierten Edge-Blockierung zum ablehnen von Nachrichten, die an ungültige Empfänger gesendet](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)werden.

 **F. welche Nachrichten können Endbenutzern in der Quarantäne zugreifen?**

A: Endbenutzer können auf Ihre eigenen Phishing-, Spam-und Massen-e-Mails zugreifen. Endbenutzer können nicht auf Ihre eigene Schadsoftware, Phishing mit hoher Zuverlässigkeit oder Nachrichten zugreifen, die mit einer Nachrichtenfluss Regel übereinstimmen (auch als Transportregel bezeichnet); Diese sind nur in der Administrator Quarantäne verfügbar. 

 **F. Wie lange bleiben Nachrichten in der Quarantäne?**

A: Standardmäßig werden Spam isolierte Nachrichten 30 Tage lang in der Quarantäne aufbewahrt, während isolierte Nachrichten, die einer e-Mail-Fluss Regel entsprechen, in der Quarantäne für bis zu 30 Tage aufbewahrt werden, basierend auf dem in der standardmäßigen Inhaltsfilter Richtlinie festgelegten Aufbewahrungszeitraum. Nach dieser Zeitspanne werden die Nachrichten gelöscht und können nicht abgerufen werden. Der Aufbewahrungszeitraum für isolierte Nachrichten, die mit einer e-Mail-Fluss Regel übereinstimmen, kann nicht konfiguriert werden. Der Aufbewahrungszeitraum für Nachrichten mit Spamquarantäne kann jedoch über die Einstellung **Spam für (Tage)** in den Inhaltsfilter Richtlinien beibehalten werden. Weitere Informationen finden Sie unter [Konfigurieren Ihrer Richtlinien für Spamfilter](configure-your-spam-filter-policies.md).

 **F. Kann ich mehr als eine Quarantänenachricht gleichzeitig freigeben oder melden?**

A. Ja, es können bis zu 100 Nachrichten gleichzeitig im Quarantäne Portal freigegeben werden. Darüber hinaus können Administratoren ein Remote Windows PowerShell Skript erstellen, um diese Aufgabe auszuführen. Verwenden Sie das [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)-Cmdlet, um nach Nachrichten zu suchen, und das [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)-Cmdlet, um sie freizugeben.

 **F. Werden bei der Suche nach in der Quarantäne isolierte Nachrichten Platzhalterzeichen unterstützt? Kann ich für eine bestimmte Domäne nach Nachricht in Quarantäne suchen?**

A. Platzhalterzeichen werden bei der Angabe von Suchkriterien im Admin Center von Exchange nicht unterstützt. Wenn Sie beispielsweise nach einem Absender suchen, müssen Sie die vollständige E-Mail-Adresse angeben.

Administratoren können Windows Remote-PowerShell verwenden, um mit dem Cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) nach Nachrichten in Quarantäne für eine bestimmte Domäne (z. B. "contoso.com") zu suchen:

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

Die Ergebnisse können an das Cmdlet [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) übergeben werden. Fügen Sie den Parameter "-ReleaseToAll" hinzu, um die Nachricht für alle Empfänger freizugeben. Nachdem eine Nachricht freigegeben wurde, kann nicht nicht nochmals freigegeben werden.

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```
