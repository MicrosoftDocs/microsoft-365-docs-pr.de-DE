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
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a><span data-ttu-id="ccf24-104">Behandeln von Problemen mit der Liveantwort von Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ccf24-104">Troubleshoot Microsoft Defender for Endpoint live response issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ccf24-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ccf24-105">**Applies to:**</span></span>
- [<span data-ttu-id="ccf24-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ccf24-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ccf24-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ccf24-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ccf24-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="ccf24-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ccf24-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ccf24-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="ccf24-110">Auf dieser Seite finden Sie ausführliche Schritte zur Behandlung von Problemen mit Liveantworten.</span><span class="sxs-lookup"><span data-stu-id="ccf24-110">This page provides detailed steps to troubleshoot live response issues.</span></span>

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a><span data-ttu-id="ccf24-111">Auf die Datei kann während der Liveantwortsitzungen nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="ccf24-111">File cannot be accessed during live response sessions</span></span>
<span data-ttu-id="ccf24-112">Wenn Sie während einer Live-Antwortsitzung versuchen, eine Aktion auszuführen, wird eine Fehlermeldung angezeigt, die besagt, dass auf die Datei nicht zugegriffen werden kann, müssen Sie die folgenden Schritte ausführen, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="ccf24-112">If while trying to take an action during a live response session, you encounter an error message stating that the file can't be accessed, you'll need to use the steps below to address the issue.</span></span>

1. <span data-ttu-id="ccf24-113">Kopieren Sie den folgenden Skriptcodeausschnitt, und speichern Sie ihn als PS1-Datei:</span><span class="sxs-lookup"><span data-stu-id="ccf24-113">Copy the following script code snippet and save it as a PS1 file:</span></span>

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


2. <span data-ttu-id="ccf24-114">Fügen Sie das Skript der Live-Antwortbibliothek hinzu.</span><span class="sxs-lookup"><span data-stu-id="ccf24-114">Add the script to the live response library.</span></span>
3. <span data-ttu-id="ccf24-115">Führen Sie das Skript mit einem Parameter aus: dem Dateipfad der zu kopierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="ccf24-115">Run the script with one parameter: the file path of the file to be copied.</span></span>
4. <span data-ttu-id="ccf24-116">Navigieren Sie zu Ihrem TEMP-Ordner.</span><span class="sxs-lookup"><span data-stu-id="ccf24-116">Navigate to your TEMP folder.</span></span>
5. <span data-ttu-id="ccf24-117">Führen Sie die Aktion aus, die Sie für die kopierte Datei ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="ccf24-117">Run the action you wanted to take on the copied file.</span></span>

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a><span data-ttu-id="ccf24-118">Langsame Liveantwortsitzungen oder Verzögerungen während der ersten Verbindungen</span><span class="sxs-lookup"><span data-stu-id="ccf24-118">Slow live response sessions or delays during initial connections</span></span>
<span data-ttu-id="ccf24-119">Live Response nutzt die Defender für Endpunkt-Sensorregistrierung beim WNS-Dienst in Windows.</span><span class="sxs-lookup"><span data-stu-id="ccf24-119">Live response leverages Defender for Endpoint sensor registration with WNS service in Windows.</span></span> <span data-ttu-id="ccf24-120">Wenn Verbindungsprobleme mit Liveantworten auftreten, bestätigen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="ccf24-120">If you are having connectivity issues with live response, confirm the following details:</span></span>
1. <span data-ttu-id="ccf24-121">`notify.windows.com` wird in Ihrer Umgebung nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="ccf24-121">`notify.windows.com` is not blocked in your environment.</span></span> <span data-ttu-id="ccf24-122">Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Geräteproxy und Internetverbindung.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="ccf24-122">For more information, see, [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>
2. <span data-ttu-id="ccf24-123">WpnService (Windows Pushbenachrichtigungssystemdienst) ist nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ccf24-123">WpnService (Windows Push Notifications System Service) is not disabled.</span></span>

<span data-ttu-id="ccf24-124">Lesen Sie die folgenden Artikel, um das Verhalten und die Anforderungen des WpnService-Diensts vollständig zu verstehen:</span><span class="sxs-lookup"><span data-stu-id="ccf24-124">Refer to the articles below to fully understand the WpnService service behavior and requirements:</span></span>
- [<span data-ttu-id="ccf24-125">Windows Übersicht über Pushbenachrichtigungsdienste (Push Notification Services, WNS)</span><span class="sxs-lookup"><span data-stu-id="ccf24-125">Windows Push Notification Services (WNS) overview</span></span>](/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [<span data-ttu-id="ccf24-126">Enterprise Firewall- und Proxykonfigurationen zur Unterstützung von WNS-Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="ccf24-126">Enterprise Firewall and Proxy Configurations to Support WNS Traffic</span></span>](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [<span data-ttu-id="ccf24-127">Öffentliche IP-Bereiche des Microsoft-Pushbenachrichtigungsdiensts (MPNS)</span><span class="sxs-lookup"><span data-stu-id="ccf24-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

