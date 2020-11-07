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
description: Hier erfahren Sie, wie Sie eDiscovery-Diagnoseinformationen für einen Microsoft-Support Fall sammeln.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944392"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Sammeln von eDiscovery-Diagnoseinformationen

Gelegentlich benötigen Microsoft-Supporttechniker spezifische Informationen zu Ihrem Problem, wenn Sie einen Support Fall öffnen, der sich auf die zentrale eDiscovery oder die erweiterte eDiscovery bezieht. Dieser Artikel enthält Anleitungen zum Sammeln von Diagnoseinformationen, um Support Ingenieure bei der Untersuchung und Lösung von Problemen zu unterstützen. Normalerweise müssen Sie diese Informationen erst sammeln, wenn Sie von einem Microsoft-Support Techniker dazu aufgefordert werden.

> [!IMPORTANT]
> Die Ausgabe der in diesem Artikel beschriebenen Cmdlets und Diagnoseinformationen kann vertrauliche Informationen zu Rechtsstreitigkeiten oder internen Untersuchungen in Ihrer Organisation enthalten. Vor dem Senden der RAW-Diagnoseinformationen an den Microsoft-Support sollten Sie die Informationen überprüfen und alle vertraulichen Informationen (wie Namen oder andere Informationen zu redact oder Ermittlungsverfahren) durch ersetzen `XXXXXXX` . Durch die Verwendung dieser Methode wird dem Microsoft-Support Techniker auch angezeigt, dass die Informationen verarbeitet wurden.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Sammeln von Diagnoseinformationen für die zentrale eDiscovery

Das Sammeln von Diagnoseinformationen für die zentrale eDiscovery ist Cmdlet-basiert, daher müssen Sie Sicherheits & Compliance Center PowerShell verwenden. In den folgenden PowerShell-Beispielen werden Cmdlets ausgeführt, und anschließend wird die Ausgabe in einer angegebenen Textdatei gespeichert. In den meisten Supportfällen sollten Sie nur einen der folgenden Befehle ausführen.

Wenn Sie die folgenden Cmdlets ausführen möchten, stellen [Sie eine Verbindung mit </span> Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell). Nachdem Sie eine Verbindung hergestellt haben, führen Sie einen oder mehrere der folgenden Befehle aus, und stellen Sie sicher, dass Sie Platzhalter durch die tatsächlichen Objektnamen ersetzen.

Nachdem Sie die generierte Textdatei überprüft und vertrauliche Informationen verarbeitet haben, senden Sie Sie an den Microsoft-Support Techniker, der an Ihrem Fall arbeitet.

> [!NOTE]
> Sie können auch die Befehle in diesem Abschnitt ausführen, um Diagnoseinformationen zu den suchen und Exporten zu sammeln, die auf der Seite " **Inhaltssuche** " im Microsoft 365 Compliance Center aufgeführt sind.

### <a name="collect-information-about-searches"></a>Sammeln von Informationen zu Suchvorgängen

Mit dem folgenden Befehl werden Informationen gesammelt, die beim Untersuchen von Problemen mit einer Inhaltssuche oder einer Suche im Zusammenhang mit einem zentralen eDiscovery-Fall hilfreich sind.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Sammeln von Informationen zu Suchaktionen

Mit dem folgenden Befehl werden Informationen zum Untersuchen von Problemen bei der Vorschau, beim Exportieren oder Löschen der Ergebnisse einer Inhaltssuche oder einer Suche im Zusammenhang mit einem zentralen eDiscovery-Fall gesammelt. Sie können den Namen der Suchaktion identifizieren, indem Sie auf die Registerkarte **Exports** klicken. Zum Identifizieren der Namen von Vorschau-und Löschaktionen können Sie das Cmdlet **Get-ComplianceSearchAction** ausführen, um eine Liste aller Aktionen anzuzeigen. Das Format für den Namen der Suchaktion wird durch Anfügen von `_Preview` `_Export` oder `_Purge` an den Namen der entsprechenden Suche erstellt.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Sammeln von Informationen über eDiscovery-Haltestatus

Wenn ein eDiscovery-Haltestatus, der einem zentralen eDiscovery-Fall zugeordnet ist, nicht wie erwartet funktioniert, führen Sie den folgenden Befehl aus, um Informationen zur Case Hold-Richtlinie und der zugehörigen Fall halten-Regel für den eDiscovery-Haltestatus zu sammeln. Der *Name der Case Hold-Richtlinie* im folgenden Befehl entspricht dem Namen des eDiscovery-Haltestatus. Sie können diesen Namen auf den Registerkarten "halte **Status** " im zentralen eDiscovery-Fall identifizieren.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Sammeln aller Fall Informationen

Manchmal ist nicht ersichtlich, welche Informationen der Microsoft-Support zur Untersuchung Ihres Problems benötigt. In dieser Situation können Sie alle Diagnoseinformationen für einen zentralen eDiscovery-Fall erfassen. Der *Name des zentralen eDiscovery-Falls* im folgenden Befehl entspricht dem Namen eines Falls, der auf der **zentralen eDiscovery** -Seite im Microsoft 365 Compliance Center angezeigt wird.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Sammeln von Diagnoseinformationen für Advanced eDiscovery

Auf der Registerkarte **Einstellungen** in einem erweiterten eDiscovery-Fall können Sie schnell die Diagnoseinformationen für den Fall kopieren. Die Diagnoseinformationen werden in der Zwischenablage gespeichert, sodass Sie Sie in eine Textdatei einfügen und an den Microsoft-Support senden können.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **alle > eDiscovery > erweitert anzeigen**.

2. Wählen Sie einen Fall aus, und klicken Sie dann auf die Registerkarte **Einstellungen** .

3. Klicken Sie unter **Fall Informationen** auf **auswählen**.

4. Klicken Sie auf der Seite Flyout auf **Diagnoseinformationen kopieren** , um die Informationen in die Zwischenablage zu kopieren.

5. Öffnen Sie eine Textdatei (im Editor), und fügen Sie die Informationen in die Textdatei ein.

6. Speichern Sie die Textdatei, und nennen Sie Sie so etwas wie `AeD Diagnostic Info YYYY.MM.DD` (beispielsweise `AeD Diagnostic Info 2020.11.03` ).

Nachdem Sie die Datei überprüft und vertrauliche Informationen verarbeitet haben, senden Sie Sie an den Microsoft-Support Techniker, der an Ihrem Fall arbeitet.
