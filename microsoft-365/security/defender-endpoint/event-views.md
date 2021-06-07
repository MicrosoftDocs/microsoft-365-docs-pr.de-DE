---
title: Anzeigen der Ereignisse zur Verringerung der Angriffsfläche
description: Importieren Sie benutzerdefinierte Ansichten, um Attack Surface Reduction-Ereignisse anzuzeigen.
keywords: Ereignisansicht, Exploit-Schutz, Überwachung, Überprüfung, Ereignisse
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ff82819f4e168fc57b649411fbe5e9136b0e36f4
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769317"
---
# <a name="view-attack-surface-reduction-events"></a>Anzeigen der Ereignisse zur Verringerung der Angriffsfläche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Überprüfen Sie die Ereignisse zur Verringerung der Angriffsfläche in der Ereignisanzeige, um zu überwachen, welche Regeln oder Einstellungen funktionieren. Sie können auch feststellen, ob Einstellungen zu "laut" sind oder sich auf Ihren täglichen Workflow auswirken.

Das Überprüfen von Ereignissen ist praktisch, wenn Sie die Features auswerten. Sie können den Überwachungsmodus für Features oder Einstellungen aktivieren und dann überprüfen, was passiert wäre, wenn sie vollständig aktiviert wären.

In diesem Artikel werden alle Ereignisse, die zugehörigen Features oder Einstellungen aufgelistet und beschrieben, wie Sie benutzerdefinierte Ansichten erstellen, um nach bestimmten Ereignissen zu filtern.

Erhalten Sie detaillierte Berichte zu Ereignissen und Blöcken als Teil Windows-Sicherheit, wenn Sie über ein E5-Abonnement verfügen und [Microsoft Defender für Endpunkt](microsoft-defender-endpoint.md)verwenden.

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>Verwenden von benutzerdefinierten Ansichten zum Überprüfen der Attack Surface Reduction-Funktionen

Erstellen Sie benutzerdefinierte Ansichten in der Windows Ereignisanzeige, um nur Ereignisse für bestimmte Funktionen und Einstellungen anzuzeigen. Die einfachste Möglichkeit besteht darin, eine benutzerdefinierte Ansicht als XML-Datei zu importieren. Sie können den XML-Code direkt von dieser Seite kopieren.

Sie können auch manuell zum Ereignisbereich navigieren, der dem Feature entspricht.

### <a name="import-an-existing-xml-custom-view"></a>Importieren einer vorhandenen benutzerdefinierten XML-Ansicht

1. Erstellen Sie eine leere .txt datei, und kopieren Sie den XML-Code für die benutzerdefinierte Ansicht, die Sie verwenden möchten, in die datei .txt. Führen Sie dies für jede benutzerdefinierte Ansicht aus, die Sie verwenden möchten. Benennen Sie die Dateien wie folgt um (stellen Sie sicher, dass Sie den Typ von .txt in .xml ändern):
    - Ereignisse für den kontrollierten Ordnerzugriff in der *benutzerdefinierten* Ansicht:cfa-events.xml
    - Benutzerdefinierte Ansicht für Exploit-Schutz-Ereignisse: *ep-events.xml*
    - Benutzerdefinierte Ansicht für Attack Surface Reduction-Ereignisse: *asr-events.xml*
    - Benutzerdefinierte Ansicht für Netzwerk-/Schutzereignisse: *np-events.xml*

2. Geben Sie die **Ereignisanzeige** im Startmenü ein, und öffnen **Sie die Ereignisanzeige.**

3. Auswählen der benutzerdefinierten Ansicht zum Importieren von   >  **Aktionen...**

    ![Animation, die die benutzerdefinierte Ansicht importieren auf der linken Seite des Fensters "Gerade Anzeige" hervorhebt](/windows/security/threat-protection/images/events-import)

4. Navigieren Sie zu der extrahierten XML-Datei für die gewünschte benutzerdefinierte Ansicht, und wählen Sie sie aus.

5. Klicken Sie auf **Öffnen**.

6. Es wird eine benutzerdefinierte Ansicht erstellt, die filtert, um nur die Ereignisse im Zusammenhang mit diesem Feature anzuzeigen.

### <a name="copy-the-xml-directly"></a>Xml direkt kopieren

1. Geben Sie die **Ereignisanzeige** im Startmenü ein, und öffnen Sie die Windows **Ereignisanzeige.**

2. Wählen Sie im linken Bereich unter **"Aktionen"** die Option **"Benutzerdefinierte Ansicht erstellen" aus...**

    ![Animation, die die Option "Benutzerdefinierte Ansicht erstellen" im Fenster "Ereignisanzeige" hervorhebt](/windows/security/threat-protection/images/events-create)

3. Wechseln Sie zur XML-Registerkarte, und wählen Sie **Abfrage manuell bearbeiten** aus. Es wird eine Warnung angezeigt, dass Sie die Abfrage nicht mithilfe der Registerkarte **"Filter"** bearbeiten können, wenn Sie die XML-Option verwenden. Wählen Sie **Ja**.

4. Fügen Sie den XML-Code für das Feature, aus dem Sie Ereignisse filtern möchten, in den XML-Abschnitt ein.

5. Wählen Sie **OK** aus. Geben Sie einen Namen für den Filter an.

6. Es wird eine benutzerdefinierte Ansicht erstellt, die filtert, um nur die Ereignisse im Zusammenhang mit diesem Feature anzuzeigen.

### <a name="xml-for-attack-surface-reduction-rule-events"></a>XML für Regelereignisse zur Verringerung der Angriffsfläche

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a>XML für Ereignisse des kontrollierten Ordnerzugriffs

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a>XML für Exploit-Schutz-Ereignisse

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-network-protection-events"></a>XML für Netzwerkschutzereignisse

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

## <a name="list-of-attack-surface-reduction-events"></a>Liste der Ereignisse zur Verringerung der Angriffsfläche

Alle Ereignisse zur Verringerung der Angriffsfläche befinden sich unter **Anwendungs- und Dienstprotokolle > Microsoft > Windows** und dann unter dem Ordner oder Anbieter, wie in der folgenden Tabelle aufgeführt.

Sie können auf diese Ereignisse in Windows Ereignisanzeige zugreifen:

1. Öffnen **Sie** das Startmenü, geben Sie **die Ereignisanzeige** ein, und wählen Sie dann das Ergebnis der **Ereignisanzeige** aus.
2. Erweitern Sie **die Anwendungs- und Dienstprotokolle > Microsoft > Windows,** und wechseln Sie dann zu dem Ordner, der in der folgenden Tabelle unter **"Anbieter/Quelle"** aufgeführt ist.
3. Doppelklicken Sie auf das Unterelement, um Ereignisse anzuzeigen. Scrollen Sie durch die Ereignisse, um das gesuchte Ereignis zu finden.

   ![Animation mithilfe der Ereignisanzeige](/windows/security/threat-protection/images/event-viewer)

Feature | Anbieter/Quelle | Ereignis-ID | Beschreibung
:-|:-|:-:|:-
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 1 | ACG-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 2 | ACG-Erzwingung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 3 | Überwachung untergeordneter Prozesse nicht zulassen
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 4  | Blockieren untergeordneter Prozesse nicht zulassen
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 5  | Blockieren der Überwachung von Images mit niedriger Integrität
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 6  | Blockierung von Bildern mit niedriger Integrität
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 7  | Remoteimageüberwachung blockieren
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 8  | Blockieren von Remoteimages blockieren
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 9  | Deaktivieren der Überwachung von Win32k-Systemaufrufen
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 10 | Deaktivieren der Blockierung von win32k-Systemaufrufen
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 11 | Codeintegritätsüberwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 12  | Codeintegritätsschutzblock
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 13 | EAF-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 14  | EAF-Erzwingung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 15 | EAF+-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 16  | EAF+ erzwingen
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 17  | IAF-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 18  | IAF-Erzwingung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 19 | ROP StackPivot-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 20 | Erzwingen von ROP StackPivot
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) |  21 | ROP CallerCheck-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 22 | Erzwingen von ROP CallerCheck
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 23 | ROP SimExec-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 24 | ROP SimExec erzwingen
Exploit-Schutz. | WER-Diagnostics | 5  | CFG-Block
Exploit-Schutz. | Win32K (Betriebsbereit) | 260 | Nicht vertrauenswürdige Schriftart
Netzwerkschutz | Windows Defender (Betriebsbereit) | 5007 | Ereignis, wenn Einstellungen geändert werden
Netzwerkschutz | Windows Defender (Betriebsbereit) | 1125 | Ereignis, wenn der Netzwerkschutz im Überwachungsmodus ausgelöst wird
Netzwerkschutz | Windows Defender (Betriebsbereit) | 1126 | Ereignis beim Auslösen des Netzwerkschutzes im Blockierungsmodus
Kontrollierter Ordnerzugriff | Windows Defender (Betriebsbereit) | 5007 | Ereignis, wenn Einstellungen geändert werden
Kontrollierter Ordnerzugriff | Windows Defender (Betriebsbereit) | 1124 | Überwachtes Ereignis für den kontrollierten Ordnerzugriff
Kontrollierter Ordnerzugriff | Windows Defender (Betriebsbereit) | 1123 | Blockiertes Ereignis für den kontrollierten Ordnerzugriff
Kontrollierter Ordnerzugriff | Windows Defender (Betriebsbereit) | 1127 | Blockierungsereignis für blockierten Ordnerzugriffssektor
Kontrollierter Ordnerzugriff | Windows Defender (Betriebsbereit) | 1128 | Überwachter kontrollierter Ordnerzugriffssektor – Schreibblockereignis
Verringerung der Angriffsfläche | Windows Defender (Betriebsbereit) | 5007 | Ereignis, wenn Einstellungen geändert werden
Verringerung der Angriffsfläche | Windows Defender (Betriebsbereit) | 1122 | Ereignis, wenn die Regel im Überwachungsmodus ausgelöst wird
Verringerung der Angriffsfläche | Windows Defender (Betriebsbereit) | 1121 | Ereignis beim Auslösen der Regel im Blockierungsmodus
