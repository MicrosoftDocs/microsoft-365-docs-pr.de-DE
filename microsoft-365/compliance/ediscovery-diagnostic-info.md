---
title: Sammeln von eDiscovery-Diagnoseinformationen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie eDiscovery-Diagnoseinformationen für einen Microsoft-Supportfall sammeln.
ms.openlocfilehash: b2441e0b7af8a82e24a8acca9e000e954e1c8964
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362594"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Sammeln von eDiscovery-Diagnoseinformationen

Gelegentlich benötigen Microsoft-Supporttechniker bestimmte Informationen zu Ihrem Problem, wenn Sie einen Supportfall im Zusammenhang mit Core eDiscovery oder Advanced eDiscovery öffnen. Dieser Artikel enthält Anleitungen zum Sammeln von Diagnoseinformationen, die Supporttechnikern dabei helfen, Probleme zu untersuchen und zu beheben. In der Regel müssen Sie diese Informationen erst sammeln, wenn Sie von einem Microsoft-Supporttechniker dazu aufgefordert werden.

> [!IMPORTANT]
> Die Ausgabe der in diesem Artikel beschriebenen Cmdlets und Diagnoseinformationen kann vertrauliche Informationen zu Rechtsstreitigkeiten oder internen Untersuchungen in Ihrer Organisation enthalten. Bevor Sie die unformatierten Diagnoseinformationen an den Microsoft-Support senden, sollten Sie die Informationen überprüfen und vertrauliche Informationen (z. B. Namen oder andere Informationen über Parteien, die einem Rechtsstreit oder einer Untersuchung unterliegen) bearbeiten, indem Sie sie durch `XXXXXXX` ersetzen. Die Verwendung dieser Methode weist den Microsoft-Supporttechniker auch darauf hin, dass Informationen bearbeitet wurden.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Sammeln von Diagnoseinformationen für Core eDiscovery

Das Sammeln von Diagnoseinformationen für Core eDiscovery ist cmdletbasiert, daher müssen Sie Security & Compliance Center PowerShell verwenden. In den folgenden PowerShell-Beispielen werden Cmdlets ausgeführt und dann die Ausgabe in einer angegebenen Textdatei gespeichert. In den meisten Supportfällen sollten Sie nur einen dieser Befehle ausführen müssen.

Um die folgenden Cmdlets auszuführen, [stellen Sie eine </span> Verbindung mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell)her. Führen Sie nach der Verbindung einen oder mehrere der folgenden Befehle aus, und ersetzen Sie Platzhalter durch die tatsächlichen Objektnamen.

Nachdem Sie die generierte Textdatei überprüft und vertrauliche Informationen bearbeitet haben, senden Sie sie an den Microsoft-Supporttechniker, der an Ihrem Fall arbeitet.

> [!NOTE]
> Sie können auch die Befehle in diesem Abschnitt ausführen, um Diagnoseinformationen für die Auf der Seite **"Inhaltssuche"** im Microsoft 365 Compliance Center aufgeführten Suchen und Exporte zu sammeln.

### <a name="collect-information-about-searches"></a>Sammeln von Informationen zu Suchvorgängen

Der folgende Befehl sammelt Informationen, die bei der Untersuchung von Problemen mit einer Inhaltssuche oder einer Suche im Zusammenhang mit einem Core eDiscovery-Fall hilfreich sind.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Sammeln von Informationen zu Suchaktionen

Mit dem folgenden Befehl werden Informationen gesammelt, um Probleme beim Anzeigen der Vorschau, beim Exportieren oder Löschen der Ergebnisse einer Inhaltssuche oder einer Suche im Zusammenhang mit einem Core eDiscovery-Fall zu untersuchen. Sie können den Namen der Suchaktion identifizieren, indem Sie auf einen Export klicken, der auf der Registerkarte **"Exporte"** aufgeführt ist. Um die Namen von Vorschau- und Bereinigungsaktionen zu identifizieren, können Sie das Cmdlet **"Get-ComplianceSearchAction"** ausführen, um eine Liste aller Aktionen anzuzeigen. Das Format für den Namen der Suchaktion wird durch Anfügen `_Preview` oder an den Namen der entsprechenden Suche `_Export` `_Purge` erstellt.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Sammeln von Informationen zu eDiscovery-Haltebereichen

Wenn ein eDiscovery-Haltebereich, der einem Core eDiscovery-Fall zugeordnet ist, nicht wie erwartet funktioniert, führen Sie den folgenden Befehl aus, um Informationen zur Case Hold-Richtlinie und der zugehörigen Fall-Hold-Regel für den eDiscovery-Haltebereich zu sammeln. Der Name der Aufbewahrungsrichtlinie für *Groß-/Kleinschreibung* im folgenden Befehl entspricht dem Namen des eDiscovery-Haltebereichs. Sie können diesen Namen auf den Registerkarten **"Haltebereiche"** im Core eDiscovery-Fall identifizieren.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Sammeln aller Fallinformationen

Manchmal ist nicht ersichtlich, welche Informationen vom Microsoft-Support benötigt werden, um Ihr Problem zu untersuchen. In diesem Fall können Sie alle Diagnoseinformationen für einen Core eDiscovery-Fall sammeln. Der *Core eDiscovery-Fallname* im folgenden Befehl entspricht dem Namen eines Falls, der auf der **Core eDiscovery-Seite** im Microsoft 365 Compliance Center angezeigt wird.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{$_|fl;"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Sammeln von Diagnoseinformationen für Advanced eDiscovery

Auf der Registerkarte **Einstellungen** in einem Advanced eDiscovery Fall können Sie die Diagnoseinformationen für den Fall schnell kopieren. Die Diagnoseinformationen werden in der Zwischenablage gespeichert, damit Sie sie in eine Textdatei einfügen und an den Microsoft-Support senden können.

1. Wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **"Alle > eDiscovery > Erweitert anzeigen".**

2. Wählen Sie einen Fall aus, und klicken Sie dann auf die Registerkarte **Einstellungen.**

3. Klicken Sie unter **"Fallinformationen"** auf **"Auswählen".**

4. Klicken Sie auf der Flyoutseite auf **Diagnoseinformationen kopieren,** um die Informationen in die Zwischenablage zu kopieren.

5. Öffnen Sie eine Textdatei (in Editor), und fügen Sie die Informationen in die Textdatei ein.

6. Speichern Sie die Textdatei, und nennen Sie sie in etwa `AeD Diagnostic Info YYYY.MM.DD` so (z. B. `AeD Diagnostic Info 2020.11.03` ).

Nachdem Sie die Datei überprüft und vertrauliche Informationen bearbeitet haben, senden Sie sie an den Microsoft-Supporttechniker, der an Ihrem Fall arbeitet.
