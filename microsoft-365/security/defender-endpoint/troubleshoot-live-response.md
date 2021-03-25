---
title: Behandeln von Problemen mit der Liveantwort von Microsoft Defender ATP
description: Behandeln von Problemen, die bei der Verwendung von Liveantworten in Microsoft Defender ATP auftreten können
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
ms.openlocfilehash: 27f2c7eb01a857ec38b11797c0703710c02ac1bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068760"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a><span data-ttu-id="c70e7-104">Behandeln von Problemen mit der Liveantwort von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c70e7-104">Troubleshoot Microsoft Defender for Endpoint live response issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c70e7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c70e7-105">**Applies to:**</span></span>
- [<span data-ttu-id="c70e7-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c70e7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="c70e7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c70e7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c70e7-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="c70e7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c70e7-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c70e7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="c70e7-110">Diese Seite enthält detaillierte Schritte zur Problembehandlung bei Liveantwortproblemen.</span><span class="sxs-lookup"><span data-stu-id="c70e7-110">This page provides detailed steps to troubleshoot live response issues.</span></span>

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a><span data-ttu-id="c70e7-111">Zugriff auf Datei während Liveantwortsitzungen nicht möglich</span><span class="sxs-lookup"><span data-stu-id="c70e7-111">File cannot be accessed during live response sessions</span></span>
<span data-ttu-id="c70e7-112">Wenn beim Versuch, während einer Liveantwortsitzung eine Aktion zu ergreifen, eine Fehlermeldung angezeigt wird, dass auf die Datei nicht zugegriffen werden kann, müssen Sie die folgenden Schritte ausführen, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="c70e7-112">If while trying to take an action during a live response session, you encounter an error message stating that the file can't be accessed, you'll need to use the steps below to address the issue.</span></span>

1. <span data-ttu-id="c70e7-113">Kopieren Sie den folgenden Skriptcodeausschnitt, und speichern Sie ihn als PS1-Datei:</span><span class="sxs-lookup"><span data-stu-id="c70e7-113">Copy the following script code snippet and save it as a PS1 file:</span></span>

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


2. <span data-ttu-id="c70e7-114">Fügen Sie das Skript der Liveantwortbibliothek hinzu.</span><span class="sxs-lookup"><span data-stu-id="c70e7-114">Add the script to the live response library.</span></span>
3. <span data-ttu-id="c70e7-115">Führen Sie das Skript mit einem Parameter aus: dem Dateipfad der zu kopierende Datei.</span><span class="sxs-lookup"><span data-stu-id="c70e7-115">Run the script with one parameter: the file path of the file to be copied.</span></span>
4. <span data-ttu-id="c70e7-116">Navigieren Sie zu Ihrem TEMP-Ordner.</span><span class="sxs-lookup"><span data-stu-id="c70e7-116">Navigate to your TEMP folder.</span></span>
5. <span data-ttu-id="c70e7-117">Führen Sie die Aktion aus, die Sie für die kopierte Datei ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="c70e7-117">Run the action you wanted to take on the copied file.</span></span>

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a><span data-ttu-id="c70e7-118">Langsame Liveantwortsitzungen oder Verzögerungen bei anfänglichen Verbindungen</span><span class="sxs-lookup"><span data-stu-id="c70e7-118">Slow live response sessions or delays during initial connections</span></span>
<span data-ttu-id="c70e7-119">Die Liveantwort nutzt die Defender for Endpoint-Sensorregistrierung beim WNS-Dienst in Windows.</span><span class="sxs-lookup"><span data-stu-id="c70e7-119">Live response leverages Defender for Endpoint sensor registration with WNS service in Windows.</span></span> <span data-ttu-id="c70e7-120">Wenn Konnektivitätsprobleme bei der Liveantwort auftreten, bestätigen Sie die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="c70e7-120">If you are having connectivity issues with live response, confirm the following details:</span></span>
1. <span data-ttu-id="c70e7-121">`notify.windows.com` in Ihrer Umgebung nicht blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="c70e7-121">`notify.windows.com` is not blocked in your environment.</span></span> <span data-ttu-id="c70e7-122">Weitere Informationen finden Sie unter [Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="c70e7-122">For more information, see, [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>
2. <span data-ttu-id="c70e7-123">WpnService (Windows Push Notifications System Service) ist nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c70e7-123">WpnService (Windows Push Notifications System Service) is not disabled.</span></span>

<span data-ttu-id="c70e7-124">Lesen Sie die folgenden Artikel, um das Verhalten und die Anforderungen des WpnService-Diensts vollständig zu verstehen:</span><span class="sxs-lookup"><span data-stu-id="c70e7-124">Refer to the articles below to fully understand the WpnService service behavior and requirements:</span></span>
- [<span data-ttu-id="c70e7-125">Übersicht über windows push Notification Services (WNS)</span><span class="sxs-lookup"><span data-stu-id="c70e7-125">Windows Push Notification Services (WNS) overview</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [<span data-ttu-id="c70e7-126">Unternehmensfirewall und Proxykonfigurationen zur Unterstützung des WNS-Datenverkehrs</span><span class="sxs-lookup"><span data-stu-id="c70e7-126">Enterprise Firewall and Proxy Configurations to Support WNS Traffic</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [<span data-ttu-id="c70e7-127">Öffentliche IP-Bereiche des Microsoft Push Notifications Service (MPNS)</span><span class="sxs-lookup"><span data-stu-id="c70e7-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

