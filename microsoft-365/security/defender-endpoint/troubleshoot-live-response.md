---
title: Behandeln von Problemen mit der Liveantwort von Microsoft Defender für Endpunkt
description: Behandeln von Problemen, die bei Verwendung der Liveantwort in Microsoft Defender für Endpunkt auftreten können
keywords: Problembehandlung bei Liveantwort, Live, Antwort, gesperrt, Datei
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 99a52188dd5f6eca2f8368aa3c114d0bfb950b10
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844154"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Behandeln von Problemen mit der Liveantwort von Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Auf dieser Seite finden Sie ausführliche Schritte zur Behandlung von Problemen mit Liveantworten.

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>Auf die Datei kann während der Liveantwortsitzungen nicht zugegriffen werden.
Wenn Sie während einer Live-Antwortsitzung versuchen, eine Aktion auszuführen, wird eine Fehlermeldung angezeigt, die besagt, dass auf die Datei nicht zugegriffen werden kann, müssen Sie die folgenden Schritte ausführen, um das Problem zu beheben.

1. Kopieren Sie den folgenden Skriptcodeausschnitt, und speichern Sie ihn als PS1-Datei:

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. Fügen Sie das Skript der Live-Antwortbibliothek hinzu.
3. Führen Sie das Skript mit einem Parameter aus: dem Dateipfad der zu kopierenden Datei.
4. Navigieren Sie zu Ihrem TEMP-Ordner.
5. Führen Sie die Aktion aus, die Sie für die kopierte Datei ausführen möchten.

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>Langsame Liveantwortsitzungen oder Verzögerungen während der ersten Verbindungen
Live Response nutzt die Defender für Endpunkt-Sensorregistrierung beim WNS-Dienst in Windows. Wenn Verbindungsprobleme mit Liveantworten auftreten, bestätigen Sie die folgenden Details:
1. `notify.windows.com` wird in Ihrer Umgebung nicht blockiert. Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Geräteproxy und Internetverbindung.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)
2. WpnService (Windows Pushbenachrichtigungssystemdienst) ist nicht deaktiviert.

Lesen Sie die folgenden Artikel, um das Verhalten und die Anforderungen des WpnService-Diensts vollständig zu verstehen:
- [Windows Übersicht über Pushbenachrichtigungsdienste (Push Notification Services, WNS)](/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [Enterprise Firewall- und Proxykonfigurationen zur Unterstützung von WNS-Datenverkehr](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Öffentliche IP-Bereiche des Microsoft-Pushbenachrichtigungsdiensts (MPNS)](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

