---
title: Anzeigen der Ereignisse zur Verringerung der Angriffsfläche
description: Importieren Sie benutzerdefinierte Ansichten, um Angriffsflächenreduzierungsereignisse zu sehen.
keywords: Ereignisansicht, Exploit Guard, Überwachung, Überprüfung, Ereignisse
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0a2ec16685ede2e625528fc3944943923bba3fc9
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51569743"
---
# <a name="view-attack-surface-reduction-events"></a>Anzeigen der Ereignisse zur Verringerung der Angriffsfläche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Überprüfen Sie Ereignisse zur Reduzierung der Angriffsfläche in der Ereignisanzeige, um zu überwachen, welche Regeln oder Einstellungen funktionieren. Sie können auch bestimmen, ob Einstellungen zu laut sind oder sich auf Ihren täglichen Workflow auswirken.

Das Überprüfen von Ereignissen ist nützlich, wenn Sie die Features auswerten. Sie können den Überwachungsmodus für Features oder Einstellungen aktivieren und dann überprüfen, was passiert wäre, wenn sie vollständig aktiviert wären.

In diesem Artikel werden alle Ereignisse, die zugehörigen Features oder Einstellungen aufgeführt und beschrieben, wie Benutzerdefinierte Ansichten zum Filtern nach bestimmten Ereignissen erstellt werden.

Erhalten Sie detaillierte Berichte zu Ereignissen und Blöcken als Teil Windows-Sicherheit, wenn Sie über ein E5-Abonnement verfügen und [Microsoft Defender for Endpoint verwenden.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>Verwenden benutzerdefinierter Ansichten zum Überprüfen der Funktionen zur Reduzierung der Angriffsfläche

Erstellen Sie benutzerdefinierte Ansichten in Windows Ereignisanzeige, um nur Ereignisse für bestimmte Funktionen und Einstellungen zu sehen. Die einfachste Möglichkeit besteht im Importieren einer benutzerdefinierten Ansicht als XML-Datei. Sie können die XML direkt von dieser Seite kopieren.

Sie können auch manuell zu dem Ereignisbereich navigieren, der dem Feature entspricht.

### <a name="import-an-existing-xml-custom-view"></a>Importieren einer vorhandenen benutzerdefinierten XML-Ansicht

1. Erstellen Sie eine leere .txt, und kopieren Sie die XML für die benutzerdefinierte Ansicht, die Sie verwenden möchten, in die .txt Datei. Tun Sie dies für jede der benutzerdefinierten Ansichten, die Sie verwenden möchten. Benennen Sie die Dateien wie folgt um (stellen Sie sicher, dass Sie den Typ von .txt in .xml):
    - Benutzerdefinierte Ansicht für Kontrollierte *Ordnerzugriffsereignisse:cfa-events.xml*
    - Benutzerdefinierte Ansicht für Exploit-Schutzereignisse: *ep-events.xml*
    - Benutzerdefinierte Ansicht attack surface reduction events: *asr-events.xml*
    - Benutzerdefinierte Ansicht für Netzwerk-/Schutzereignisse: *np-events.xml*

2. Geben **Sie die Ereignisanzeige** im Menü Start ein, und öffnen Sie **die Ereignisanzeige**.

3.   >  **Aktionsimport benutzerdefinierte Ansicht auswählen...**

    ![Animation highlighting Import custom view on the left of the Even viewer window](/windows/security/threat-protection/images/events-import)

4. Navigieren Sie zu der Stelle, an der Sie die XML-Datei für die benutzerdefinierte Ansicht extrahiert haben, und wählen Sie sie aus.

5. Klicken Sie auf **Öffnen**.

6. Es wird eine benutzerdefinierte Ansicht erstellt, die filtert, um nur die Ereignisse im Zusammenhang mit diesem Feature zu zeigen.

### <a name="copy-the-xml-directly"></a>Kopieren der XML direkt

1. Geben **Sie die Ereignisanzeige** im Menü Start ein, und öffnen Sie Windows **Ereignisanzeige**.

2. Wählen Sie im linken Bereich unter **Aktionen** die Option **Benutzerdefinierte Ansicht erstellen... aus.**

    ![Animation, die die Option benutzerdefinierte Ansicht erstellen im Fenster "Ereignisanzeige" hervorhebt](/windows/security/threat-protection/images/events-create)

3. Wechseln Sie zur Registerkarte XML, und wählen Sie **Abfrage manuell bearbeiten aus.** Es wird eine Warnung angezeigt, dass Sie die Abfrage nicht mithilfe der Registerkarte **Filter** bearbeiten können, wenn Sie die XML-Option verwenden. Wählen Sie **Ja**.

4. Fügen Sie den XML-Code für das Feature ein, aus dem Sie Ereignisse filtern möchten, in den ABSCHNITT XML.

5. Klicken Sie auf **OK**. Geben Sie einen Namen für Den Filter an.

6. Es wird eine benutzerdefinierte Ansicht erstellt, die filtert, um nur die Ereignisse im Zusammenhang mit diesem Feature zu zeigen.

### <a name="xml-for-attack-surface-reduction-rule-events"></a>XML für Regelereignisse zur Reduzierung der Angriffsfläche

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a>XML für ereignisse mit kontrolliertem Ordnerzugriff

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a>XML für Exploitschutzereignisse

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

## <a name="list-of-attack-surface-reduction-events"></a>Liste der Ereignisse zur Reduzierung der Angriffsfläche

Alle Ereignisse zur Reduzierung der Angriffsfläche befinden sich unter Anwendungs- und Dienstprotokolle **> Microsoft > Windows** und dann im Ordner oder Anbieter, wie in der folgenden Tabelle aufgeführt.

Sie können auf diese Ereignisse in der Windows zugreifen:

1. Öffnen Sie **das Menü Start,** und geben Sie **die Ereignisanzeige ein,** und wählen Sie dann das **Ergebnis der Ereignisanzeige** aus.
2. Erweitern Sie Anwendungs- und **Dienstprotokolle > Microsoft > Windows,** und wechseln Sie dann zu dem Ordner, der unter **Anbieter/Quelle** in der folgenden Tabelle aufgeführt ist.
3. Doppelklicken Sie auf das Unterelement, um Ereignisse zu sehen. Scrollen Sie durch die Ereignisse, um das Gesuchte zu finden.

   ![Animation, die mithilfe der Ereignisanzeige angezeigt wird](/windows/security/threat-protection/images/event-viewer)

Feature | Anbieter/Quelle | Ereignis-ID | Beschreibung
:-|:-|:-:|:-
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 1 | ACG-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 2 | Erzwingen von ACG
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 3 | Überwachung untergeordneter Prozesse nicht zulassen
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 4  | Blockieren untergeordneter Prozesse nicht zulassen
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 5  | Überwachung von Bildern mit niedriger Integrität blockieren
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 6  | Blockieren von Bildern mit niedriger Integrität
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 7  | Remoteabbildüberwachung blockieren
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 8  | Blockierung von Remotebildern
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 9  | Deaktivieren der Überwachung von win32k-Systemaufrufen
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 10 | Deaktivieren des win32k-Systemanrufblocks
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 11 | Codeintegritätsschutz-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 12  | Codeintegritätsschutzblock
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 13 | EAF-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 14  | Erzwingen von EAF
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 15  | EAF+-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 16  | Erzwingen von EAF+
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 17  | IAF-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 18  | IAF erzwingen
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 19 | ROP StackPivot-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 20 | Erzwingen von ROP StackPivot
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) |  21 | ROP CallerCheck-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 22 | Erzwingen von ROP CallerCheck
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 23 | ROP SimExec-Überwachung
Exploit-Schutz. | Security-Mitigations (Kernelmodus/Benutzermodus) | 24 | Erzwingen von ROP SimExec
Exploit-Schutz. | WER-Diagnostics | 5  | CFG-Block
Exploit-Schutz. | Win32K (Betriebsbereit) | 260 | Nicht vertrauenswürdige Schriftart
Netzwerkschutz | Windows Defender (Betriebsbereit) | 5007 | Ereignis, wenn Einstellungen geändert werden
Netzwerkschutz | Windows Defender (Betriebsbereit) | 1125 | Ereignis, wenn der Netzwerkschutz im Überwachungsmodus abgeschaltet wird
Netzwerkschutz | Windows Defender (Betriebsbereit) | 1126 | Ereignis, wenn der Netzwerkschutz im Blockmodus aktiviert wird
Kontrollierter Ordnerzugriff | Windows Defender (Betriebsbereit) | 5007 | Ereignis, wenn Einstellungen geändert werden
Kontrollierter Ordnerzugriff | Windows Defender (Betriebsbereit) | 1124 | Überwachtes Kontrolliertes Ordnerzugriffsereignis
Kontrollierter Ordnerzugriff | Windows Defender (Betriebsbereit) | 1123 | Ereignis "Blockierter kontrollierter Ordnerzugriff"
Kontrollierter Ordnerzugriff | Windows Defender (Betriebsbereit) | 1127 | Blockereignis "Blockierter kontrollierter Ordnerzugriffssektor"
Kontrollierter Ordnerzugriff | Windows Defender (Betriebsbereit) | 1128 | Audited Controlled folder access sector write block event
Verringerung der Angriffsfläche | Windows Defender (Betriebsbereit) | 5007 | Ereignis, wenn Einstellungen geändert werden
Verringerung der Angriffsfläche | Windows Defender (Betriebsbereit) | 1122 | Ereignis, wenn die Regel im Überwachungsmodus abgeschaltet wird
Verringerung der Angriffsfläche | Windows Defender (Betriebsbereit) | 1121 | Ereignis, wenn die Regel im Blockmodus gestartet wird
