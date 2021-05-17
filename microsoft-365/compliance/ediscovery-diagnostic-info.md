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
description: Erfahren Sie, wie Sie eDiscovery-Diagnoseinformationen für einen Microsoft Support-Fall erfassen.
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926555"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Sammeln von eDiscovery-Diagnoseinformationen

Gelegentlich benötigen Microsoft Support-Techniker spezifische Informationen zu Ihrem Problem, wenn Sie einen Supportfall im Zusammenhang mit Core eDiscovery oder Advanced eDiscovery. Dieser Artikel enthält Anleitungen zum Sammeln von Diagnoseinformationen, mit deren Hilfe Techniker Probleme untersuchen und beheben können. In der Regel müssen Sie diese Informationen erst erfassen, wenn Sie von einem Microsoft Support-Techniker dazu aufgefordert wurden.

> [!IMPORTANT]
> Die Ausgabe der Cmdlets und Diagnoseinformationen, die in diesem Artikel beschrieben werden, kann vertrauliche Informationen zu Rechtsstreitigkeiten oder internen Untersuchungen in Ihrer Organisation enthalten. Bevor Sie die unformatierte Diagnoseinformationen an den Microsoft Support senden, sollten Sie die Informationen überprüfen und vertrauliche Informationen (z. B. Namen oder andere Informationen zu Parteien, die an Einem Rechtsstreit oder Untersuchung beteiligten) durch redactieren, indem Sie sie durch `XXXXXXX` ersetzen. Wenn Sie diese Methode verwenden, wird dem Microsoft-Supporttechniker auch angezeigt, dass informationen redacted wurden.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Sammeln von Diagnoseinformationen für Core eDiscovery

Das Sammeln von Diagnoseinformationen für Core eDiscovery ist cmdlet-basiert, sodass Sie Security & Compliance Center PowerShell verwenden müssen. In den folgenden PowerShell-Beispielen werden Cmdlets ausgeführt und die Ausgabe dann in einer angegebenen Textdatei gespeichert. In den meisten Supportfällen sollten Sie nur einen dieser Befehle ausführen müssen.

Um die folgenden Cmdlets ausführen zu können, stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell ein. </span> ](/powershell/exchange/connect-to-scc-powershell) Führen Sie nach der Verbindung einen oder mehrere der folgenden Befehle aus, und ersetzen Sie Platzhalter durch die tatsächlichen Objektnamen.

Nachdem Sie die generierte Textdatei überprüft und vertrauliche Informationen umaktiviert haben, senden Sie sie an den Microsoft Support-Techniker, der an Ihrem Fall arbeitet.

> [!NOTE]
> Sie können die Befehle in diesem Abschnitt auch ausführen, um Diagnoseinformationen für die auf der Seite Inhaltssuche im Compliance Center aufgeführten Microsoft 365 zu erfassen. 

### <a name="collect-information-about-searches"></a>Sammeln von Informationen zu Suchen

Der folgende Befehl sammelt Informationen, die bei der Untersuchung von Problemen mit einer Inhaltssuche oder einer Suche im Zusammenhang mit einem Core eDiscovery-Fall hilfreich sind.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Sammeln von Informationen zu Suchaktionen

Mit dem folgenden Befehl werden Informationen gesammelt, um Probleme beim Anzeigen, Exportieren oder Löschen der Ergebnisse einer Inhaltssuche oder einer Suche zu untersuchen, die einem Core eDiscovery-Fall zugeordnet ist. Sie können den Namen der Suchaktion identifizieren, indem Sie auf einen Export klicken, der auf der Registerkarte **Exporte aufgeführt** ist. Zum Identifizieren der Namen von Vorschau- und Bereinigungsaktionen können Sie das **Cmdlet Get-ComplianceSearchAction** ausführen, um eine Liste aller Aktionen anzuzeigen. Das Format für den Namen der Suchaktion wird durch Anfügen , oder an den Namen der `_Preview` `_Export` entsprechenden Suche `_Purge` erstellt.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Sammeln von Informationen zu eDiscovery-Halteinformationen

Wenn ein eDiscovery-Haltebereich, der einem Core eDiscovery-Fall zugeordnet ist, nicht wie erwartet funktioniert, führen Sie den folgenden Befehl aus, um Informationen zur Case Hold Policy und der zugehörigen Fall hold Rule für das eDiscovery-Haltebereich zu sammeln. Der *Name der Case-Hold-Richtlinie* im folgenden Befehl entspricht dem Namen des eDiscovery-Halteraums. Sie können diesen Namen auf den **Registerkarten** Haltebereich im Fall Core eDiscovery identifizieren.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Sammeln aller Fallinformationen

Manchmal ist nicht ersichtlich, welche Informationen vom Microsoft Support benötigt werden, um Ihr Problem zu untersuchen. In diesem Fall können Sie alle Diagnoseinformationen für einen Core eDiscovery-Fall erfassen. Der *Core eDiscovery-Fallname* im folgenden Befehl entspricht dem Namen eines Falls, der auf der Seite Core **eDiscovery** im Microsoft 365 Compliance Center angezeigt wird.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Sammeln von Diagnoseinformationen für Advanced eDiscovery

Auf **Einstellungen** Registerkarte in einem Advanced eDiscovery können Sie die Diagnoseinformationen für den Fall schnell kopieren. Die Diagnoseinformationen werden in der Zwischenablage gespeichert, damit Sie sie in eine Textdatei einfügen und an den Microsoft Support senden können.

1. Wechseln Sie zu, und klicken Sie dann auf Alle [https://compliance.microsoft.com](https://compliance.microsoft.com/) **> eDiscovery > Advanced anzeigen.**

2. Wählen Sie einen Fall aus, und klicken Sie **dann auf Einstellungen** Klicken.

3. Klicken **Sie unter Fallinformationen** auf **Auswählen**.

4. Klicken Sie auf der Flyoutseite auf **Diagnoseinformationen kopieren,** um die Informationen in die Zwischenablage zu kopieren.

5. Öffnen Sie eine Textdatei (in Editor), und fügen Sie die Informationen dann in die Textdatei ein.

6. Speichern Sie die Textdatei, und nennen Sie sie etwa `AeD Diagnostic Info YYYY.MM.DD` (z. B. `AeD Diagnostic Info 2020.11.03` ).

Nachdem Sie die Datei überprüft und vertrauliche Informationen umaktiviert haben, senden Sie sie an den Microsoft Support-Techniker, der an Ihrem Fall arbeitet.