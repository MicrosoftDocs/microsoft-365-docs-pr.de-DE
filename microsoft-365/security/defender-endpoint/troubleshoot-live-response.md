---
title: Behandeln von Problemen mit der Liveantwort von Microsoft Defender for Endpoint
description: Behandeln von Problemen, die bei der Verwendung von Liveantworten in Microsoft Defender for Endpoint auftreten können
keywords: Problembehandlung für Liveantwort, Live, Antwort, gesperrt, Datei
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
ms.openlocfilehash: 2601001687fc22da98ca3cd81010237d12705ea4
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687411"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Behandeln von Problemen mit der Liveantwort von Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Diese Seite enthält detaillierte Schritte zur Problembehandlung bei Liveantwortproblemen.

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>Zugriff auf Datei während Liveantwortsitzungen nicht möglich
Wenn beim Versuch, während einer Liveantwortsitzung eine Aktion zu ergreifen, eine Fehlermeldung angezeigt wird, dass auf die Datei nicht zugegriffen werden kann, müssen Sie die folgenden Schritte ausführen, um das Problem zu beheben.

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


2. Fügen Sie das Skript der Liveantwortbibliothek hinzu.
3. Führen Sie das Skript mit einem Parameter aus: dem Dateipfad der zu kopierende Datei.
4. Navigieren Sie zu Ihrem TEMP-Ordner.
5. Führen Sie die Aktion aus, die Sie für die kopierte Datei ausführen möchten.

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>Langsame Liveantwortsitzungen oder Verzögerungen bei anfänglichen Verbindungen
Die Liveantwort nutzt die Defender for Endpoint-Sensorregistrierung beim WNS-Dienst in Windows. Wenn Konnektivitätsprobleme bei der Liveantwort auftreten, bestätigen Sie die folgenden Details:
1. `notify.windows.com` in Ihrer Umgebung nicht blockiert ist. Weitere Informationen finden Sie unter [Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)
2. WpnService (Windows Push Notifications System Service) ist nicht deaktiviert.

Lesen Sie die folgenden Artikel, um das Verhalten und die Anforderungen des WpnService-Diensts vollständig zu verstehen:
- [Übersicht über windows push Notification Services (WNS)](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [Unternehmensfirewall und Proxykonfigurationen zur Unterstützung des WNS-Datenverkehrs](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Öffentliche IP-Bereiche des Microsoft Push Notifications Service (MPNS)](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

