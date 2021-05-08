---
title: Microsoft Defender Antivirus auf Windows Server
description: Erfahren Sie, wie Sie Microsoft Defender Antivirus unter Windows Server 2016 und Windows Server 2019 aktivieren und konfigurieren.
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
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269492"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Microsoft Defender Antivirus auf Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus ist in den folgenden Editionen/Versionen von Windows Server verfügbar:
- Windows Server 2019
- Windows Server, Version 1803 oder höher
- Windows Server 2016. 

In einigen Fällen wird Microsoft Defender Antivirus als Endpoint *Protection bezeichnet.* Das Schutzmodul ist jedoch identisch. Obwohl Funktionalität, Konfiguration und Verwaltung für Microsoft Defender Antivirus unter [Windows 10](microsoft-defender-antivirus-in-windows-10.md)weitgehend identisch sind, gibt es einige wichtige Unterschiede in Windows Server:

- Unter Windows Server [werden automatische Ausschlüsse](configure-server-exclusions-microsoft-defender-antivirus.md) basierend auf Ihrer definierten Serverrolle angewendet.
 
- Wenn Sie unter Windows Server eine Nicht-Microsoft-Antiviren-/Antischalwarelösung ausführen, wechselt Microsoft Defender Antivirus nicht automatisch in den passiven oder deaktivierten Modus. Sie können Microsoft Defender Antivirus jedoch manuell auf den passiven oder deaktivierten Modus festlegen.

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Einrichten von Microsoft Defender Antivirus auf Windows Server

Das Einrichten und Ausführen von Microsoft Defender Antivirus auf einer Serverplattform umfasst mehrere Schritte:

1. [Aktivieren Sie die Schnittstelle](#enable-the-user-interface-on-windows-server).
2. [Installieren Sie Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).
3. [Überprüfen Sie, ob Microsoft Defender Antivirus ausgeführt wird.](#verify-microsoft-defender-antivirus-is-running)
4. [Aktualisieren Sie Ihre Antischalware Security Intelligence](#update-antimalware-security-intelligence).
5. (Nach Bedarf) [Senden Von Beispielen](#submit-samples).
6. (Nach Bedarf) [Konfigurieren von automatischen Ausschlüssen](#configure-automatic-exclusions).
7. (Nur bei Bedarf) [Legen Sie Microsoft Defender Antivirus auf den passiven Modus .](#need-to-set-microsoft-defender-antivirus-to-passive-mode)

## <a name="enable-the-user-interface-on-windows-server"></a>Aktivieren der Benutzeroberfläche unter Windows Server

Standardmäßig ist Microsoft Defender Antivirus unter Windows Server installiert und funktionsfähig. Manchmal ist die Benutzeroberfläche (GUI) standardmäßig installiert, die GUI ist jedoch nicht erforderlich. Sie können PowerShell, Gruppenrichtlinien oder andere Methoden zum Verwalten von Microsoft Defender Antivirus verwenden. 

Wenn die GUI nicht auf Ihrem Server installiert ist und Sie sie installieren möchten, verwenden Sie entweder den Assistenten Zum Hinzufügen von Rollen und **Features** oder PowerShell-Cmdlets.

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>Aktivieren der GUI mithilfe des Assistenten zum Hinzufügen von Rollen und Features

1. Weitere Informationen finden Sie unter Installieren von [Rollen, Rollendiensten](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)und Features mithilfe des Assistenten zum Hinzufügen von Rollen und Features und verwenden Sie den Assistenten zum Hinzufügen von **Rollen und Features.**

2. Wenn Sie zum Schritt **Features** des Assistenten kommen, wählen Sie **unter Windows Defender Features** die Option GUI für **Windows Defender** aus.

   In Windows Server 2016 sieht der Assistent zum Hinzufügen von **Rollen und Features** wie dies aus:

   ![Hinzufügen von Rollen und Feature-Assistenten, der die GUI für Windows Defender zeigt](images/server-add-gui.png)

   In Windows Server 2019 ist der Assistent zum Hinzufügen von **Rollen und Features** ähnlich.

### <a name="turn-on-the-gui-using-powershell"></a>Aktivieren der GUI mithilfe von PowerShell

Das folgende PowerShell-Cmdlet aktiviert die Schnittstelle: 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Installieren von Microsoft Defender Antivirus auf Windows Server

Wenn Sie Microsoft Defender Antivirus auf Windows Server installieren oder neu installieren müssen, können Sie dies entweder mit dem Assistenten zum Hinzufügen von Rollen und **Features** oder powerShell tun.

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>Verwenden des Assistenten zum Hinzufügen von Rollen und Features zum Installieren von Microsoft Defender Antivirus

1. Lesen Sie [diesen Artikel,](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)und verwenden Sie den Assistenten zum Hinzufügen **von Rollen und Features.**

2. Wenn Sie zum Schritt **Features** des Assistenten kommen, wählen Sie die Option Microsoft Defender Antivirus aus. Wählen Sie auch die **GUI für Windows Defender** aus.

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>Installieren von Microsoft Defender Antivirus mithilfe von PowerShell

Führen Sie das folgende Cmdlet aus, um Microsoft Defender Antivirus mithilfe von PowerShell zu installieren:

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

Ereignismeldungen für das in Microsoft Defender Antivirus enthaltene Antischalsoftwaremodul finden Sie unter [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).


## <a name="verify-microsoft-defender-antivirus-is-running"></a>Überprüfen, ob Microsoft Defender Antivirus ausgeführt wird

Sobald Microsoft Defender Antivirus installiert ist, müssen Sie im nächsten Schritt überprüfen, ob es ausgeführt wird. Führen Sie auf Dem Windows Server-Endpunkt das folgende PowerShell-Cmdlet aus:

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

Der `sc query` Befehl gibt Informationen zum Microsoft Defender Antivirus-Dienst zurück. Wenn Microsoft Defender Antivirus ausgeführt wird, wird `STATE` der Wert `RUNNING` angezeigt.

## <a name="update-antimalware-security-intelligence"></a>Aktualisieren von Antischalware Security Intelligence 

Um aktualisierte Antischalware-Sicherheitsintelligenz zu erhalten, muss der Windows Update-Dienst ausgeführt werden. Wenn Sie einen Updateverwaltungsdienst wie Windows Server Update Services (WSUS) verwenden, stellen Sie sicher, dass Updates für Microsoft Defender Antivirus Security Intelligence für die von Ihnen verwalteten Computer genehmigt werden.

Standardmäßig werden Updates von Windows Update nicht automatisch unter Windows Server 2019 oder Windows Server 2016 heruntergeladen und installiert. Sie können diese Konfiguration mithilfe einer der folgenden Methoden ändern:


|Methode  |Beschreibung  |
|---------|---------|
|**Windows Update** in der Systemsteuerung     |- **Die automatische Installation von** Updates führt dazu, dass alle Updates automatisch installiert werden, einschließlich Windows Defender Security Intelligence-Updates. <br/>- **Laden Sie Updates** herunter, aber lassen Sie mich auswählen, ob sie installiert werden sollen Windows Defender sicherheitsintelligente Updates automatisch herunterladen und installieren können, andere Updates werden jedoch nicht automatisch installiert.       |
|**Gruppenrichtlinie**     | Sie können Windows Update mithilfe der in der Gruppenrichtlinie verfügbaren Einstellungen im folgenden Pfad einrichten und **verwalten: Administrative Vorlagen\Windows-Komponenten\Windows Update\Automatische Updates konfigurieren**         |
|Der **AUOptions-Registrierungsschlüssel**     |Die folgenden beiden Werte ermöglichen Windows Update das automatische Herunterladen und Installieren von Security Intelligence-Updates: <br/>- **4**  -  **Installieren Sie Updates automatisch**. Dieser Wert führt dazu, dass alle Updates automatisch installiert werden, einschließlich Windows Defender Security Intelligence-Updates. <br/>- **3**  -  **Laden Sie Updates herunter, aber lassen Sie mich auswählen, ob sie installiert werden sollen.**  Dieser Wert ermöglicht Windows Defender, Sicherheitsintelligenzupdates automatisch herunterzuladen und zu installieren, andere Updates werden jedoch nicht automatisch installiert.         |

Um sicherzustellen, dass der Schutz vor Schadsoftware erhalten bleibt, wird empfohlen, die folgenden Dienste zu aktivieren:

- Windows-Fehlerberichtsdienst

- Windows Update-Dienst

In der folgenden Tabelle sind die Dienste für Microsoft Defender Antivirus und die abhängigen Dienste aufgeführt.

|Dienstname|Dateispeicherort|Beschreibung|
|--------|---------|--------|
|Windows Defender Service (WinDefend)|`C:\Program Files\Windows Defender\MsMpEng.exe`|Dies ist der wichtigste Microsoft Defender Antivirus-Dienst, der jederzeit ausgeführt werden muss.|
|Windows Error Reporting Service (Wersvc)|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|Dieser Dienst sendet Fehlerberichte zurück an Microsoft.|
|Windows Defender Firewall (MpsSvc)|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|Es wird empfohlen, Windows Defender Firewalldienst aktiviert zu lassen.|
|Windows Update (Wuauserv)|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|Windows Update ist erforderlich, um Sicherheitsintelligenzupdates und Antischalwaremodulupdates zu erhalten.|

## <a name="submit-samples"></a>Übermitteln von Beispielen

Die Beispielübermittlung ermöglicht Microsoft das Sammeln von Beispielen potenziell schädlicher Software. Um weiterhin und auf dem neuesten Stand zu sein, verwenden Microsoft-Forscher diese Beispiele, um verdächtige Aktivitäten zu analysieren und aktualisierte Sicherheitsintelligenz für Antischalware zu erstellen. Wir sammeln ausführbare Dateien des Programms, z. B. .exe dateien und .dll Dateien. Wir sammeln keine Dateien, die personenbezogene Daten enthalten, z. B. Microsoft Word-Dokumente und PDF-Dateien.

### <a name="submit-a-file"></a>Senden einer Datei

1. Lesen Sie das [Übermittlungshandbuch](/windows/security/threat-protection/intelligence/submission-guide).

2. Besuchen Sie [das Beispielübermittlungsportal,](https://www.microsoft.com/wdsi/filesubmission)und übermitteln Sie Ihre Datei.


### <a name="enable-automatic-sample-submission"></a>Aktivieren der automatischen Beispielübermittlung

Um die automatische Beispielübermittlung zu aktivieren, starten Sie eine Windows PowerShell-Konsole als Administrator, und legen Sie die **SubmitSamplesConsent-Wertdaten** gemäß einer der folgenden Einstellungen ein:

|Einstellung  |Beschreibung  |
|---------|---------|
|**0**  -  **Always-Eingabeaufforderung**     |Der Microsoft Defender Antivirus-Dienst fordert Sie auf, die Übermittlung aller erforderlichen Dateien zu bestätigen. Dies ist die Standardeinstellung für Microsoft Defender Antivirus, wird jedoch nicht für Installationen unter Windows Server 2016 oder 2019 ohne GUI empfohlen.         |
|**1**   -  **Automatisches Senden sicherer Beispiele**     |Der Microsoft Defender Antivirus-Dienst sendet alle Dateien, die als "sicher" gekennzeichnet sind, und fordert die restlichen Dateien auf.         |
|**2**  -  **Nie senden**      |Der Microsoft Defender Antivirus-Dienst fordert keine Eingabeaufforderungen auf und sendet keine Dateien.         |
|**3**  -  **Alle Beispiele automatisch senden**     |Der Microsoft Defender Antivirus-Dienst sendet alle Dateien ohne Bestätigungsaufforderung.         |

## <a name="configure-automatic-exclusions"></a>Konfigurieren automatischer Ausschlüsse

Um Sicherheit und Leistung sicherzustellen, werden bestimmte Ausschlüsse automatisch basierend auf den Rollen und Features hinzugefügt, die Sie bei Verwendung von Microsoft Defender Antivirus unter Windows Server 2016 oder 2019 installieren.

Weitere [Informationen finden Sie unter Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md). 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>Müssen Sie Microsoft Defender Antivirus auf den passiven Modus festlegen?

Wenn Sie ein Nicht-Microsoft-Antivirenprodukt als primäre Antivirenlösung unter Windows Server verwenden, müssen Sie Microsoft Defender Antivirus auf den passiven oder deaktivierten Modus festlegen.

- Unter Windows Server, Version 1803 oder neuer, oder Windows Server 2019, können Sie Microsoft Defender Antivirus auf den passiven Modus festlegen.  

- Unter Windows Server 2016 wird Microsoft Defender Antivirus nicht zusammen mit einem Nicht-Microsoft-Antiviren-/Antischalwareprodukt unterstützt. In diesen Fällen müssen Sie Microsoft Defender Antivirus auf den deaktivierten Modus festlegen.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a>Festlegen des passiven Modus von Microsoft Defender Antivirus mithilfe von PowerShell

Wenn Sie Windows Server, Version 1803 oder Windows Server 2019 verwenden, können Sie Microsoft Defender Antivirus mithilfe des folgenden PowerShell-Cmdlets auf den passiven Modus festlegen:

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a>Festlegen des passiven Modus von Microsoft Defender Antivirus mithilfe von Gruppenrichtlinien

VERFAHREN ERFORDERLICH

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>Festlegen des passiven Modus von Microsoft Defender Antivirus mithilfe eines Registrierungsschlüssels

Wenn Sie Windows Server, Version 1803 oder Windows Server 2019 verwenden, können Sie Microsoft Defender Antivirus auf den passiven Modus festlegen, indem Sie den folgenden Registrierungsschlüssel festlegen:
- Pfad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Name: `ForceDefenderPassiveMode`
- Typ: `REG_DWORD`
- Wert: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>Deaktivieren von Microsoft Defender Antivirus mithilfe des Assistenten zum Entfernen von Rollen und Features

1. Weitere Informationen finden Sie unter Installieren oder Deinstallieren von [Rollen, Rollendiensten](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)oder Features, und verwenden Sie den Assistenten zum Entfernen **von Rollen und Features.** 

2. Wenn Sie zum Schritt **Features** des Assistenten kommen, deaktivieren Sie **die Option Windows Defender Features.** 

    Wenn Sie **Windows Defender** im Abschnitt **Windows Defender Features** selbst löschen, werden Sie aufgefordert, die GUI für die Benutzeroberflächenoption für Windows Defender **.** 
    
    Microsoft Defender Antivirus wird weiterhin normal ohne die Benutzeroberfläche ausgeführt, aber die Benutzeroberfläche kann nicht aktiviert werden, wenn Sie das **Hauptfeature** Windows Defender deaktivieren.

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>Deaktivieren der Microsoft Defender Antivirus-Benutzeroberfläche mithilfe von PowerShell

Verwenden Sie das folgende PowerShell-Cmdlet, um die Microsoft Defender Antivirus-GUI zu deaktivieren:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>Verwenden Sie Windows Server 2016?

Wenn Sie Windows Server 2016 und ein Antivirenprodukt eines Drittanbieters verwenden, das nicht von Microsoft angeboten oder entwickelt wird, müssen Sie Microsoft Defender Antivirus deaktivieren/deinstallieren. 

> [!NOTE]
> Sie können die Windows Security-App nicht deinstallieren, aber Sie können die Benutzeroberfläche mit diesen Anweisungen deaktivieren.

Das folgende PowerShell-Cmdlet deinstalliert Microsoft Defender Antivirus unter Windows Server 2016:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

Verwenden Sie das folgende PowerShell-Cmdlet, um Microsoft Defender Antivirus unter Windows Server 2016 zu deaktivieren:

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a>Siehe auch

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus-Kompatibilität](microsoft-defender-antivirus-compatibility.md)
