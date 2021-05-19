---
title: Microsoft Defender Antivirus auf Windows Server
description: Erfahren Sie, wie Sie Microsoft Defender Antivirus Server Windows Server 2016 server 2019 Windows konfigurieren.
keywords: Windows Defender, Server, Scep, System Center Endpoint Protection, Server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 05/13/2021
ms.openlocfilehash: 1a1083d15698eb5bbdf2f6080b152b6f326c689a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539275"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Microsoft Defender Antivirus auf Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus ist in den folgenden Editionen/Versionen von Windows Server verfügbar:
- Windows Server 2019
- Windows Server, Version 1803 oder höher
- Windows Server 2016. 

In einigen Fällen wird Microsoft Defender Antivirus als *"Endpoint Protection" bezeichnet.* Das Schutzmodul ist jedoch identisch. Obwohl Die Funktionalität, Konfiguration und Verwaltung für Microsoft Defender Antivirus auf Windows 10 weitgehend identisch [sind,](microsoft-defender-antivirus-in-windows-10.md)gibt es einige wichtige Unterschiede auf Windows Server:

- Auf Windows Server werden [automatische Ausschlüsse](configure-server-exclusions-microsoft-defender-antivirus.md) basierend auf Ihrer definierten Serverrolle angewendet.
 
- Wenn Windows Server eine Nicht-Microsoft-Antiviren-/Antischalwarelösung ausführen, wechselt Microsoft Defender Antivirus nicht automatisch in den passiven oder deaktivierten Modus. Sie können die Microsoft Defender Antivirus jedoch manuell auf den passiven oder deaktivierten Modus festlegen.

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Einrichten von Microsoft Defender Antivirus auf Windows Server

Das Einrichten und Ausführen von Microsoft Defender Antivirus auf einer Serverplattform umfasst mehrere Schritte:

1. [Aktivieren Sie die Schnittstelle](#enable-the-user-interface-on-windows-server).
2. [Installieren Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).
3. [Überprüfen, Microsoft Defender Antivirus ausgeführt wird.](#verify-microsoft-defender-antivirus-is-running)
4. [Aktualisieren Sie Ihre Antischalware Security Intelligence](#update-antimalware-security-intelligence).
5. (Nach Bedarf) [Senden Von Beispielen](#submit-samples).
6. (Nach Bedarf) [Konfigurieren von automatischen Ausschlüssen](#configure-automatic-exclusions).
7. (Nur bei Bedarf) [Legen Microsoft Defender Antivirus passiven Modus .](#need-to-set-microsoft-defender-antivirus-to-passive-mode)

## <a name="enable-the-user-interface-on-windows-server"></a>Aktivieren der Benutzeroberfläche auf Windows Server

Standardmäßig ist Microsoft Defender Antivirus server installiert und Windows funktionsfähig. Manchmal ist die Benutzeroberfläche (GUI) standardmäßig installiert, die GUI ist jedoch nicht erforderlich. Sie können PowerShell, Gruppenrichtlinien oder andere Methoden zum Verwalten von Microsoft Defender Antivirus. 

Wenn die GUI nicht auf Ihrem Server installiert ist und Sie sie installieren möchten, verwenden Sie entweder den Assistenten Zum Hinzufügen von Rollen und **Features** oder PowerShell-Cmdlets.

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>Aktivieren der GUI mithilfe des Assistenten zum Hinzufügen von Rollen und Features

1. Weitere Informationen finden Sie unter Installieren von [Rollen, Rollendiensten](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)und Features mithilfe des Assistenten zum Hinzufügen von Rollen und Features und verwenden Sie den Assistenten zum Hinzufügen von **Rollen und Features.**

2. Wenn Sie zum Schritt **Features** des Assistenten kommen, wählen Sie **unter Windows Defender Features** die Option GUI für **Windows Defender** aus.

   In Windows Server 2016 sieht der Assistent zum Hinzufügen von **Rollen und Features** wie dies aus:

   ![Hinzufügen von Rollen und Feature-Assistenten mit der GUI für Windows Defender Option](images/server-add-gui.png)

   In Windows Server 2019 ist der Assistent zum Hinzufügen von Rollen **und Features** ähnlich.

### <a name="turn-on-the-gui-using-powershell"></a>Aktivieren der GUI mithilfe von PowerShell

Das folgende PowerShell-Cmdlet aktiviert die Schnittstelle: 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Installieren Microsoft Defender Antivirus auf Windows Server

Wenn Sie Microsoft Defender Antivirus auf Windows Server installieren oder neu installieren müssen, können  Sie dies entweder mit dem Assistenten zum Hinzufügen von Rollen und Features oder powerShell tun.

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>Verwenden Sie den Assistenten zum Hinzufügen von Rollen und Features zum Installieren Microsoft Defender Antivirus

1. Lesen Sie [diesen Artikel,](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)und verwenden Sie den Assistenten zum Hinzufügen **von Rollen und Features.**

2. Wenn Sie zum Schritt **Features** des Assistenten kommen, wählen Sie die Option Microsoft Defender Antivirus aus. Wählen Sie auch die **GUI für Windows Defender** aus.

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>Verwenden von PowerShell zum Installieren Microsoft Defender Antivirus

Führen Sie das folgende Cmdlet aus, um Microsoft Defender Antivirus PowerShell zu installieren:

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

Ereignismeldungen für das im Lieferumfang enthaltene Antischalwaremodul Microsoft Defender Antivirus finden Sie unter [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).


## <a name="verify-microsoft-defender-antivirus-is-running"></a>Überprüfen, Microsoft Defender Antivirus ausgeführt wird

Sobald Microsoft Defender Antivirus installiert ist, müssen Sie im nächsten Schritt überprüfen, ob sie ausgeführt wird. Führen Sie auf Windows Server-Endpunkt das folgende PowerShell-Cmdlet aus:

```PowerShell
Get-Service -Name windefend
```

Führen Sie das folgende PowerShell-Cmdlet aus, um zu überprüfen, ob der Firewallschutz aktiviert ist:

```PowerShell 
Get-Service -Name mpssvc
```

Als Alternative zu PowerShell können Sie mithilfe der Eingabeaufforderung überprüfen, ob Microsoft Defender Antivirus ausgeführt wird. Führen Sie dazu den folgenden Befehl an einer Eingabeaufforderung aus: 

```console
sc query Windefend
```

Der `sc query` Befehl gibt Informationen zum Microsoft Defender Antivirus zurück. Wenn Microsoft Defender Antivirus ausgeführt wird, wird `STATE` der Wert `RUNNING` angezeigt.

## <a name="update-antimalware-security-intelligence"></a>Aktualisieren von Antischalware Security Intelligence 

Um aktualisierte Antischalwaresicherheitsintelligenz zu erhalten, muss der Windows Updatedienst ausgeführt werden. Wenn Sie einen Updateverwaltungsdienst wie Windows Server Update Services (WSUS) verwenden, stellen Sie sicher, dass Updates für Microsoft Defender Antivirus Security Intelligence für die von Ihnen verwalteten Computer genehmigt werden.

Standardmäßig werden Windows Updates nicht automatisch auf Server 2019 oder Windows server 2019 Windows Server 2016. Sie können diese Konfiguration mithilfe einer der folgenden Methoden ändern:


|Methode  |Beschreibung  |
|---------|---------|
|**Windows Update** in der Systemsteuerung     | **Die automatische Installation von** Updates führt dazu, dass alle Updates automatisch installiert werden, einschließlich Windows Defender Security Intelligence-Updates. <p>**Laden Sie Updates** herunter, aber lassen Sie mich entscheiden, ob sie installiert werden sollen, Windows Defender security intelligence updates automatisch herunterladen und installieren können, andere Updates werden jedoch nicht automatisch installiert.       |
|**Gruppenrichtlinie**     | Sie können Windows Update mithilfe der in der Gruppenrichtlinie verfügbaren Einstellungen im folgenden Pfad einrichten und verwalten: **Administrative Vorlagen\Windows-Komponenten\Windows Update\Automatische Updates konfigurieren**         |
|Der **AUOptions-Registrierungsschlüssel**     | Die folgenden beiden Werte ermöglichen Windows Update, Sicherheitsintelligenzupdates automatisch herunterzuladen und zu installieren: <p>**4**  -  **Installieren Sie Updates automatisch**. Dieser Wert führt dazu, dass alle Updates automatisch installiert werden, einschließlich Windows Defender Security Intelligence-Updates. <p>**3**  -  **Laden Sie Updates herunter, aber lassen Sie mich auswählen, ob sie installiert werden sollen.**  Dieser Wert ermöglicht Windows Defender, Sicherheitsintelligenzupdates automatisch herunterzuladen und zu installieren, andere Updates werden jedoch nicht automatisch installiert.         |

Um sicherzustellen, dass der Schutz vor Schadsoftware erhalten bleibt, wird empfohlen, die folgenden Dienste zu aktivieren:

- Windows-Fehlerberichterstattung-Dienst

- Windows Updatedienst

In der folgenden Tabelle sind die Dienste für Microsoft Defender Antivirus und die abhängigen Dienste aufgeführt.

|Dienstname|Dateispeicherort|Beschreibung|
|--------|---------|--------|
|Windows Defender Dienst (WinDefend)|`C:\Program Files\Windows Defender\MsMpEng.exe`|Dies ist der Microsoft Defender Antivirus, der immer ausgeführt werden muss.|
|Windows-Fehlerberichterstattung Dienst (Wersvc)|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|Dieser Dienst sendet Fehlerberichte zurück an Microsoft.|
|Windows Defender Firewall (MpsSvc)|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|Es wird empfohlen, den Windows Defender Firewall aktiviert zu lassen.|
|Windows Update (Wuauserv)|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|Windows Update ist erforderlich, um Updates für Security Intelligence und Antischalwaremodulupdates zu erhalten.|

## <a name="submit-samples"></a>Übermitteln von Beispielen

Die Beispielübermittlung ermöglicht Microsoft das Sammeln von Beispielen potenziell schädlicher Software. Um weiterhin und auf dem neuesten Stand zu sein, verwenden Microsoft-Forscher diese Beispiele, um verdächtige Aktivitäten zu analysieren und aktualisierte Sicherheitsintelligenz für Antischalware zu erstellen. Wir sammeln ausführbare Dateien des Programms, z. B. .exe dateien und .dll Dateien. Wir sammeln keine Dateien, die personenbezogene Daten enthalten, z. B. Microsoft Word und PDF-Dateien.

### <a name="submit-a-file"></a>Senden einer Datei

1. Lesen Sie das [Übermittlungshandbuch](/windows/security/threat-protection/intelligence/submission-guide).

2. Besuchen Sie [das Beispielübermittlungsportal,](https://www.microsoft.com/wdsi/filesubmission)und übermitteln Sie Ihre Datei.


### <a name="enable-automatic-sample-submission"></a>Aktivieren der automatischen Beispielübermittlung

Starten Sie zum Aktivieren der automatischen Beispielübermittlung eine Windows PowerShell als Administrator, und legen Sie die **SubmitSamplesConsent-Wertdaten** gemäß einer der folgenden Einstellungen ein:

|Einstellung  |Beschreibung  |
|---------|---------|
|**0**  -  **Always-Eingabeaufforderung**     |Der Microsoft Defender Antivirus fordert Sie auf, die Übermittlung aller erforderlichen Dateien zu bestätigen. Dies ist die Standardeinstellung für Microsoft Defender Antivirus, wird jedoch nicht für Installationen unter Windows Server 2016 oder 2019 ohne GUI empfohlen.         |
|**1**   -  **Automatisches Senden sicherer Beispiele**     |Der Microsoft Defender Antivirus sendet alle als "sicher" markierten Dateien und fordert die restlichen Dateien auf.         |
|**2**  -  **Nie senden**      |Der Microsoft Defender Antivirus wird nicht aufgefordert und sendet keine Dateien.         |
|**3**  -  **Alle Beispiele automatisch senden**     |Der Microsoft Defender Antivirus sendet alle Dateien ohne Bestätigungsaufforderung.         |

## <a name="configure-automatic-exclusions"></a>Konfigurieren automatischer Ausschlüsse

Um Sicherheit und Leistung sicherzustellen, werden bestimmte Ausschlüsse automatisch basierend auf den Rollen und Features hinzugefügt, die Sie bei verwendung von Microsoft Defender Antivirus auf Windows Server 2016 oder 2019 installieren.

Weitere Informationen finden Sie unter Configure [exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md). 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>Müssen Sie Microsoft Defender Antivirus passiven Modus festlegen?

Wenn Sie ein Nicht-Microsoft-Antivirenprodukt als primäre Antivirenlösung auf Windows Server verwenden, müssen Sie Microsoft Defender Antivirus passiven oder deaktivierten Modus festlegen.

- Auf Windows Server, Version 1803 oder neuer, oder Windows Server 2019 können Sie Microsoft Defender Antivirus passiven Modus festlegen.  

- On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/anmalware product. In diesen Fällen müssen Sie Microsoft Defender Antivirus deaktivierten Modus festlegen.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>Festlegen Microsoft Defender Antivirus auf den passiven Modus mithilfe eines Registrierungsschlüssels

Wenn Sie Windows Server, Version 1803 oder Windows Server 2019 verwenden, können Sie Microsoft Defender Antivirus auf den passiven Modus festlegen, indem Sie den folgenden Registrierungsschlüssel festlegen:
- Pfad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Name: `ForceDefenderPassiveMode`
- Typ: `REG_DWORD`
- Wert: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>Deaktivieren Microsoft Defender Antivirus mithilfe des Assistenten zum Entfernen von Rollen und Features

1. Weitere Informationen finden Sie unter Installieren oder Deinstallieren von [Rollen, Rollendiensten](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)oder Features, und verwenden Sie den Assistenten zum Entfernen **von Rollen und Features.** 

2. Wenn Sie zum Schritt **Features** des Assistenten kommen, deaktivieren Sie **die Option Windows Defender Features.** 

    Wenn Sie **Windows Defender** im Abschnitt **Windows Defender Features** selbst löschen, werden Sie aufgefordert, die GUI für die Benutzeroberflächenoption für Windows Defender **.** 
    
    Microsoft Defender Antivirus wird weiterhin normal ohne die Benutzeroberfläche ausgeführt, aber die Benutzeroberfläche kann nicht aktiviert werden, wenn Sie das **Kernfeature Windows Defender** deaktivieren.

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>Deaktivieren der Microsoft Defender Antivirus benutzeroberfläche mithilfe von PowerShell

Verwenden Sie das folgende PowerShell-Cmdlet, um die Microsoft Defender Antivirus zu deaktivieren:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>Verwenden Sie Windows Server 2016?

Wenn Sie Windows Server 2016 und ein Antivirenprodukt eines Drittanbieters verwenden, das nicht von Microsoft angeboten oder entwickelt wird, müssen Sie die Software deaktivieren/Microsoft Defender Antivirus. 

> [!NOTE]
> Sie können die app nicht Windows-Sicherheit deinstallieren, aber Sie können die Schnittstelle mit diesen Anweisungen deaktivieren.

Das folgende PowerShell-Cmdlet deinstalliert Microsoft Defender Antivirus auf Windows Server 2016:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

Verwenden Sie das folgende PowerShell-Cmdlet, um Microsoft Defender Antivirus Windows Server 2016 zu deaktivieren:

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a>Siehe auch

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus Kompatibilität](microsoft-defender-antivirus-compatibility.md)
