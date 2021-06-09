---
title: Untersuchen von Entitäten auf Geräten mithilfe von Liveantwort in Microsoft Defender für Endpunkt
description: Greifen Sie mithilfe einer sicheren Remoteshell-Verbindung auf ein Gerät zu, um Untersuchungsvorgänge auszuführen und sofortige Reaktionsaktionen auf einem Gerät in Echtzeit auszuführen.
keywords: remote, shell, connection, live, response, real-time, command, script, remediate, hunt, export, log, drop, download, file,
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d5e48f1e4f6bc2cfaa836d90e24f2ce8ba3f2114
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845330"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="9c682-104">Untersuchen von Entitäten auf Geräten mithilfe von Liveantwort</span><span class="sxs-lookup"><span data-stu-id="9c682-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9c682-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9c682-105">**Applies to:**</span></span>
- [<span data-ttu-id="9c682-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9c682-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9c682-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c682-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="9c682-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="9c682-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9c682-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9c682-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="9c682-110">Live Response bietet Sicherheitsteams sofortigen Zugriff auf ein Gerät (auch als Computer bezeichnet) über eine Remoteshell-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="9c682-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="9c682-111">Dadurch haben Sie die Möglichkeit, tiefgehende Untersuchungsarbeit zu leisten und sofortige Maßnahmen zu ergreifen, um erkannte Bedrohungen umgehend einzudämmen – in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="9c682-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="9c682-112">Live Response wurde entwickelt, um Untersuchungen zu verbessern, indem es Ihrem Sicherheitsteam ermöglicht, forensische Daten zu sammeln, Skripts auszuführen, verdächtige Entitäten zur Analyse zu senden, Bedrohungen zu beheben und proaktiv nach neuen Bedrohungen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="9c682-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="9c682-113">Mit Live-Antworten können Analysten alle folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="9c682-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="9c682-114">Führen Sie einfache und erweiterte Befehle aus, um untersuchungsrelevante Aufgaben auf einem Gerät auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9c682-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="9c682-115">Laden Sie Dateien wie Schadsoftwarebeispiele und Ergebnisse von PowerShell-Skripts herunter.</span><span class="sxs-lookup"><span data-stu-id="9c682-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="9c682-116">Dateien im Hintergrund herunterladen (neu!).</span><span class="sxs-lookup"><span data-stu-id="9c682-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="9c682-117">Hochladen sie ein PowerShell-Skript oder eine ausführbare Datei in die Bibliothek ein, und führen Sie es auf einem Gerät auf Mandantenebene aus.</span><span class="sxs-lookup"><span data-stu-id="9c682-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="9c682-118">Durchführen oder Rückgängigmachen von Korrekturmaßnahmen.</span><span class="sxs-lookup"><span data-stu-id="9c682-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9c682-119">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="9c682-119">Before you begin</span></span>

<span data-ttu-id="9c682-120">Bevor Sie eine Sitzung auf einem Gerät initiieren können, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="9c682-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="9c682-121">**Stellen Sie sicher, dass Sie eine unterstützte Version von Windows ausführen.**</span><span class="sxs-lookup"><span data-stu-id="9c682-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="9c682-122">Auf Geräten muss eine der folgenden Versionen von Windows</span><span class="sxs-lookup"><span data-stu-id="9c682-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="9c682-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="9c682-123">**Windows 10**</span></span>
    - <span data-ttu-id="9c682-124">[Version 1909](/windows/whats-new/whats-new-windows-10-version-1909) oder höher</span><span class="sxs-lookup"><span data-stu-id="9c682-124">[Version 1909](/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="9c682-125">[Version 1903](/windows/whats-new/whats-new-windows-10-version-1903) mit [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="9c682-125">[Version 1903](/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="9c682-126">[Version 1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809) [mit KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="9c682-126">[Version 1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="9c682-127">[Version 1803 (RS 4)](/windows/whats-new/whats-new-windows-10-version-1803) mit [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="9c682-127">[Version 1803 (RS 4)](/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="9c682-128">[Version 1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) mit [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="9c682-128">[Version 1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="9c682-129">**Windows Server 2019 – Gilt nur für öffentliche Vorschau**</span><span class="sxs-lookup"><span data-stu-id="9c682-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="9c682-130">Version 1903 oder (mit [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) später</span><span class="sxs-lookup"><span data-stu-id="9c682-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="9c682-131">Version 1809 (mit [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span><span class="sxs-lookup"><span data-stu-id="9c682-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="9c682-132">**Aktivieren Sie die Liveantwort von der Seite "Erweiterte Einstellungen".**</span><span class="sxs-lookup"><span data-stu-id="9c682-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="9c682-133">Sie müssen die Liveantwortfunktion auf der Seite ["Erweiterte Features"](advanced-features.md) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9c682-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="9c682-134">Nur Benutzer mit Sicherheits- oder globalen Administratorrollen können diese Einstellungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9c682-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="9c682-135">Aktivieren Sie die **Liveantwort für Server über die Seite "Erweiterte Einstellungen"** (empfohlen).</span><span class="sxs-lookup"><span data-stu-id="9c682-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="9c682-136">Nur Benutzer mit Sicherheits- oder globalen Administratorrollen können diese Einstellungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9c682-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="9c682-137">**Stellen Sie sicher, dass dem Gerät eine Automatisierungsbereinigungsstufe zugewiesen ist.**</span><span class="sxs-lookup"><span data-stu-id="9c682-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="9c682-138">Sie müssen mindestens die mindeste Korrekturstufe für eine bestimmte Gerätegruppe aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9c682-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="9c682-139">Andernfalls können Sie keine Live-Antwortsitzung für ein Mitglied dieser Gruppe einrichten.</span><span class="sxs-lookup"><span data-stu-id="9c682-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="9c682-140">Sie erhalten den folgenden Fehler:</span><span class="sxs-lookup"><span data-stu-id="9c682-140">You'll receive the following error:</span></span>

    ![Abbildung der Fehlermeldung](images/live-response-error.png)

- <span data-ttu-id="9c682-142">**Aktivieren Sie die Ausführung nicht signierter Skripts für Liveantworten** (optional).</span><span class="sxs-lookup"><span data-stu-id="9c682-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="9c682-143">Wenn Sie die Verwendung von nicht signierten Skripts zulassen, können Sie Bedrohungen mehr ausgesetzt sein.</span><span class="sxs-lookup"><span data-stu-id="9c682-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="9c682-144">Das Ausführen von nicht signierten Skripts wird nicht empfohlen, da dadurch Bedrohungen erhöht werden können.</span><span class="sxs-lookup"><span data-stu-id="9c682-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="9c682-145">Wenn Sie sie jedoch verwenden müssen, müssen Sie die Einstellung auf der Seite ["Erweiterte Features"](advanced-features.md) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9c682-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="9c682-146">**Stellen Sie sicher, dass Sie über die entsprechenden Berechtigungen verfügen.**</span><span class="sxs-lookup"><span data-stu-id="9c682-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="9c682-147">Nur Benutzer, die über die entsprechenden Berechtigungen verfügen, können eine Sitzung initiieren.</span><span class="sxs-lookup"><span data-stu-id="9c682-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="9c682-148">Weitere Informationen zu Rollenzuweisungen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="9c682-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="9c682-149">Die Option zum Hochladen einer Datei in die Bibliothek ist nur für Personen mit den entsprechenden RBAC-Berechtigungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9c682-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="9c682-150">Die Schaltfläche ist für Benutzer mit nur delegierten Berechtigungen abgeblendet.</span><span class="sxs-lookup"><span data-stu-id="9c682-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="9c682-151">Je nachdem, welche Rolle Ihnen zugewiesen wurde, können Sie einfache oder erweiterte Liveantwortbefehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="9c682-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="9c682-152">Benutzerberechtigungen werden von der benutzerdefinierten RBAC-Rolle gesteuert.</span><span class="sxs-lookup"><span data-stu-id="9c682-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="9c682-153">Übersicht über das Live-Antwortdashboard</span><span class="sxs-lookup"><span data-stu-id="9c682-153">Live response dashboard overview</span></span>
<span data-ttu-id="9c682-154">Wenn Sie eine Liveantwortsitzung auf einem Gerät initiieren, wird ein Dashboard geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9c682-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="9c682-155">Das Dashboard enthält Informationen über die Sitzung, z. B. die folgenden:</span><span class="sxs-lookup"><span data-stu-id="9c682-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="9c682-156">Wer die Sitzung erstellt</span><span class="sxs-lookup"><span data-stu-id="9c682-156">Who created the session</span></span>
- <span data-ttu-id="9c682-157">Zeitpunkt, zu dem die Sitzung gestartet wurde</span><span class="sxs-lookup"><span data-stu-id="9c682-157">When the session started</span></span>
- <span data-ttu-id="9c682-158">Die Dauer der Sitzung</span><span class="sxs-lookup"><span data-stu-id="9c682-158">The duration of the session</span></span>

<span data-ttu-id="9c682-159">Das Dashboard bietet Ihnen außerdem Zugriff auf:</span><span class="sxs-lookup"><span data-stu-id="9c682-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="9c682-160">Trennen einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="9c682-160">Disconnect session</span></span>
- <span data-ttu-id="9c682-161">Hochladen von Dateien in die Bibliothek</span><span class="sxs-lookup"><span data-stu-id="9c682-161">Upload files to the library</span></span> 
- <span data-ttu-id="9c682-162">Befehlskonsole</span><span class="sxs-lookup"><span data-stu-id="9c682-162">Command console</span></span>
- <span data-ttu-id="9c682-163">Befehlsprotokoll</span><span class="sxs-lookup"><span data-stu-id="9c682-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="9c682-164">Initiieren einer Liveantwortsitzung auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="9c682-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="9c682-165">Melden Sie sich bei Microsoft Defender Security Center an.</span><span class="sxs-lookup"><span data-stu-id="9c682-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="9c682-166">Navigieren Sie zur Gerätelistenseite, und wählen Sie ein Gerät aus, das untersucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="9c682-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="9c682-167">Die Geräteseite wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9c682-167">The devices page opens.</span></span>

3. <span data-ttu-id="9c682-168">Starten Sie die Liveantwortsitzung, indem Sie **"Liveantwortsitzung initiieren"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="9c682-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="9c682-169">Eine Befehlskonsole wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c682-169">A command console is displayed.</span></span> <span data-ttu-id="9c682-170">Warten Sie, während die Sitzung eine Verbindung mit dem Gerät herstellt.</span><span class="sxs-lookup"><span data-stu-id="9c682-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="9c682-171">Verwenden Sie die integrierten Befehle, um Ermittlungsarbeit zu leisten.</span><span class="sxs-lookup"><span data-stu-id="9c682-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="9c682-172">Weitere Informationen finden Sie unter [Live-Antwortbefehle.](#live-response-commands)</span><span class="sxs-lookup"><span data-stu-id="9c682-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="9c682-173">Wählen Sie nach Abschluss Der Untersuchung die **Sitzung trennen aus,** und wählen Sie dann **Bestätigen** aus.</span><span class="sxs-lookup"><span data-stu-id="9c682-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="9c682-174">Live-Antwortbefehle</span><span class="sxs-lookup"><span data-stu-id="9c682-174">Live response commands</span></span>

<span data-ttu-id="9c682-175">Je nachdem, welche Rolle Ihnen zugewiesen wurde, können Sie einfache oder erweiterte Liveantwortbefehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="9c682-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="9c682-176">Benutzerberechtigungen werden von benutzerdefinierten RBAC-Rollen gesteuert.</span><span class="sxs-lookup"><span data-stu-id="9c682-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="9c682-177">Weitere Informationen zu Rollenzuweisungen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="9c682-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="9c682-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span><span class="sxs-lookup"><span data-stu-id="9c682-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="9c682-179">Grundlegende Befehle</span><span class="sxs-lookup"><span data-stu-id="9c682-179">Basic commands</span></span>

<span data-ttu-id="9c682-180">Die folgenden Befehle sind für Benutzerrollen verfügbar, denen die Möglichkeit gewährt wird, **grundlegende** Liveantwortbefehle auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9c682-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="9c682-181">Weitere Informationen zu Rollenzuweisungen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="9c682-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="9c682-182">Befehl</span><span class="sxs-lookup"><span data-stu-id="9c682-182">Command</span></span> | <span data-ttu-id="9c682-183">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c682-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="9c682-184">Ändert das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9c682-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="9c682-185">Löscht den Konsolenbildschirm.</span><span class="sxs-lookup"><span data-stu-id="9c682-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="9c682-186">Initiiert eine Liveantwortsitzung auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="9c682-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="9c682-187">Zeigt alle aktiven Verbindungen an.</span><span class="sxs-lookup"><span data-stu-id="9c682-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="9c682-188">Zeigt eine Liste von Dateien und Unterverzeichnissen in einem Verzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="9c682-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`drivers` |  <span data-ttu-id="9c682-189">Zeigt alle auf dem Gerät installierten Treiber an.</span><span class="sxs-lookup"><span data-stu-id="9c682-189">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="9c682-190">Platzieren Sie den angegebenen Auftrag im Vordergrund im Vordergrund, sodass er der aktuelle Auftrag ist.</span><span class="sxs-lookup"><span data-stu-id="9c682-190">Place the specified job in the foreground in the foreground, making it the current job.</span></span> <br> <span data-ttu-id="9c682-191">HINWEIS: fg verwendet eine "Befehls-ID", die in Aufträgen verfügbar ist, nicht eine PID.</span><span class="sxs-lookup"><span data-stu-id="9c682-191">NOTE: fg takes a “command ID” available from jobs, not a PID</span></span> |
|`fileinfo` | <span data-ttu-id="9c682-192">Abrufen von Informationen zu einer Datei.</span><span class="sxs-lookup"><span data-stu-id="9c682-192">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="9c682-193">Sucht Dateien anhand eines bestimmten Namens auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="9c682-193">Locates files by a given name on the device.</span></span> |
|`getfile <file_path>` | <span data-ttu-id="9c682-194">Lädt eine Datei herunter.</span><span class="sxs-lookup"><span data-stu-id="9c682-194">Downloads a file.</span></span> |
|`help` | <span data-ttu-id="9c682-195">Enthält Hilfeinformationen für Liveantwortbefehle.</span><span class="sxs-lookup"><span data-stu-id="9c682-195">Provides help information for live response commands.</span></span> |
|`jobs` | <span data-ttu-id="9c682-196">Zeigt derzeit ausgeführte Aufträge, deren ID und Status an.</span><span class="sxs-lookup"><span data-stu-id="9c682-196">Shows currently running jobs, their ID and status.</span></span> |
|`persistence` | <span data-ttu-id="9c682-197">Zeigt alle bekannten Persistenzmethoden auf dem Gerät an.</span><span class="sxs-lookup"><span data-stu-id="9c682-197">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="9c682-198">Zeigt alle auf dem Gerät ausgeführten Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="9c682-198">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="9c682-199">Zeigt Registrierungswerte an.</span><span class="sxs-lookup"><span data-stu-id="9c682-199">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="9c682-200">Zeigt alle geplanten Aufgaben auf dem Gerät an.</span><span class="sxs-lookup"><span data-stu-id="9c682-200">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="9c682-201">Zeigt alle Dienste auf dem Gerät an.</span><span class="sxs-lookup"><span data-stu-id="9c682-201">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="9c682-202">Legt den Protokollierungsmodus des Terminal für das Debuggen fest.</span><span class="sxs-lookup"><span data-stu-id="9c682-202">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="9c682-203">Erweiterte Befehle</span><span class="sxs-lookup"><span data-stu-id="9c682-203">Advanced commands</span></span>
<span data-ttu-id="9c682-204">Die folgenden Befehle sind für Benutzerrollen verfügbar, denen die Möglichkeit gewährt wird, **erweiterte** Liveantwortbefehle auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9c682-204">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="9c682-205">Weitere Informationen zu Rollenzuweisungen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="9c682-205">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="9c682-206">Befehl</span><span class="sxs-lookup"><span data-stu-id="9c682-206">Command</span></span> | <span data-ttu-id="9c682-207">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c682-207">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="9c682-208">Analysiert die Entität mit verschiedenen Inkriminierungs-Engines, um eine Bewertung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="9c682-208">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `run` | <span data-ttu-id="9c682-209">Führt ein PowerShell-Skript aus der Bibliothek auf dem Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="9c682-209">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="9c682-210">Listet Dateien auf, die in die Liveantwortbibliothek hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="9c682-210">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="9c682-211">Platziert eine Datei aus der Bibliothek auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="9c682-211">Puts a file from the library to the device.</span></span> <span data-ttu-id="9c682-212">Dateien werden in einem Arbeitsordner gespeichert und gelöscht, wenn das Gerät standardmäßig neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="9c682-212">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="9c682-213">Behebt eine Entität auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="9c682-213">Remediates an entity on the device.</span></span> <span data-ttu-id="9c682-214">Die Korrekturaktion variiert je nach Entitätstyp:</span><span class="sxs-lookup"><span data-stu-id="9c682-214">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="9c682-215">- Datei: löschen</span><span class="sxs-lookup"><span data-stu-id="9c682-215">- File: delete</span></span><br><span data-ttu-id="9c682-216">- Prozess: beenden, Bilddatei löschen</span><span class="sxs-lookup"><span data-stu-id="9c682-216">- Process: stop, delete image file</span></span><br><span data-ttu-id="9c682-217">- Dienst: beenden, Bilddatei löschen</span><span class="sxs-lookup"><span data-stu-id="9c682-217">- Service: stop, delete image file</span></span><br><span data-ttu-id="9c682-218">- Registrierungseintrag: löschen</span><span class="sxs-lookup"><span data-stu-id="9c682-218">- Registry entry: delete</span></span><br><span data-ttu-id="9c682-219">– Geplante Aufgabe: entfernen</span><span class="sxs-lookup"><span data-stu-id="9c682-219">- Scheduled task: remove</span></span><br><span data-ttu-id="9c682-220">- Startordnerelement: Datei löschen</span><span class="sxs-lookup"><span data-stu-id="9c682-220">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="9c682-221">HINWEIS: Dieser Befehl verfügt über einen erforderlichen Befehl.</span><span class="sxs-lookup"><span data-stu-id="9c682-221">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="9c682-222">Sie können den `-auto` Befehl zusammen `remediate` verwenden, um den erforderlichen Befehl automatisch auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9c682-222">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="9c682-223">Stellt eine Entität wieder her, die korrigiert wurde.</span><span class="sxs-lookup"><span data-stu-id="9c682-223">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="9c682-224">Verwenden von Liveantwortbefehlen</span><span class="sxs-lookup"><span data-stu-id="9c682-224">Use live response commands</span></span>

<span data-ttu-id="9c682-225">Die Befehle, die Sie in der Konsole verwenden können, folgen ähnlichen Prinzipien wie [Windows Befehle.](/windows-server/administration/windows-commands/windows-commands#BKMK_c)</span><span class="sxs-lookup"><span data-stu-id="9c682-225">The commands that you can use in the console follow similar principles as [Windows Commands](/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="9c682-226">Die erweiterten Befehle bieten einen stabileren Satz von Aktionen, mit denen Sie leistungsstärkere Aktionen ausführen können, z. B. eine Datei herunterladen und hochladen, Skripts auf dem Gerät ausführen und Korrekturmaßnahmen für eine Entität ausführen können.</span><span class="sxs-lookup"><span data-stu-id="9c682-226">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="9c682-227">Abrufen einer Datei vom Gerät</span><span class="sxs-lookup"><span data-stu-id="9c682-227">Get a file from the device</span></span>

<span data-ttu-id="9c682-228">Für Szenarien, in dem Sie eine Datei von einem Gerät abrufen möchten, das Sie untersuchen, können Sie den `getfile` Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c682-228">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="9c682-229">Auf diese Weise können Sie die Datei zur weiteren Untersuchung vom Gerät speichern.</span><span class="sxs-lookup"><span data-stu-id="9c682-229">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="9c682-230">Es gelten die folgenden Dateigrößenbeschränkungen:</span><span class="sxs-lookup"><span data-stu-id="9c682-230">The following file size limits apply:</span></span>
>- <span data-ttu-id="9c682-231">`getfile` Grenzwert: 3 GB</span><span class="sxs-lookup"><span data-stu-id="9c682-231">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="9c682-232">`fileinfo` Grenzwert: 10 GB</span><span class="sxs-lookup"><span data-stu-id="9c682-232">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="9c682-233">`library` Grenzwert: 250 MB</span><span class="sxs-lookup"><span data-stu-id="9c682-233">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="9c682-234">Herunterladen einer Datei im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="9c682-234">Download a file in the background</span></span>

<span data-ttu-id="9c682-235">Damit Ihr Sicherheitsteam die Untersuchung eines betroffenen Geräts fortsetzen kann, können Dateien jetzt im Hintergrund heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="9c682-235">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="9c682-236">Um eine Datei im Hintergrund herunterzuladen, geben Sie in der Befehlskonsole für Liveantworten `download <file_path> &` .</span><span class="sxs-lookup"><span data-stu-id="9c682-236">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="9c682-237">Wenn Sie warten, bis eine Datei heruntergeladen wird, können Sie sie mit STRG +Z in den Hintergrund verschieben.</span><span class="sxs-lookup"><span data-stu-id="9c682-237">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="9c682-238">Um einen Dateidownload in den Vordergrund zu bringen, geben Sie in der Befehlskonsole der Liveantwort `fg <command_id>` .</span><span class="sxs-lookup"><span data-stu-id="9c682-238">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="9c682-239">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="9c682-239">Here are some examples:</span></span>


|<span data-ttu-id="9c682-240">Befehl</span><span class="sxs-lookup"><span data-stu-id="9c682-240">Command</span></span>  |<span data-ttu-id="9c682-241">Funktion der Einstellung</span><span class="sxs-lookup"><span data-stu-id="9c682-241">What it does</span></span>  |
|---------|---------|
|`getfile "C:\windows\some_file.exe" &`     |<span data-ttu-id="9c682-242">Startet das Herunterladen einer Datei mit dem Namen *some_file.exe* im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="9c682-242">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="9c682-243">Gibt einen Download mit der Befehls-ID *1234* im Vordergrund zurück.</span><span class="sxs-lookup"><span data-stu-id="9c682-243">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="9c682-244">Einfügen einer Datei in die Bibliothek</span><span class="sxs-lookup"><span data-stu-id="9c682-244">Put a file in the library</span></span>

<span data-ttu-id="9c682-245">Live response has a library where you can put files into.</span><span class="sxs-lookup"><span data-stu-id="9c682-245">Live response has a library where you can put files into.</span></span> <span data-ttu-id="9c682-246">Die Bibliothek speichert Dateien (z. B. Skripts), die in einer Liveantwortsitzung auf Mandantenebene ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="9c682-246">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="9c682-247">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span><span class="sxs-lookup"><span data-stu-id="9c682-247">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="9c682-248">Sie können über eine Sammlung von PowerShell-Skripts verfügen, die auf Geräten ausgeführt werden können, mit denen Sie Liveantwortsitzungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="9c682-248">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="9c682-249">So laden Sie eine Datei in die Bibliothek hoch</span><span class="sxs-lookup"><span data-stu-id="9c682-249">To upload a file in the library</span></span>

1. <span data-ttu-id="9c682-250">Klicken Sie auf **Hochladen Datei, um die Bibliothek zu öffnen.**</span><span class="sxs-lookup"><span data-stu-id="9c682-250">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="9c682-251">Klicken Sie auf **"Durchsuchen",** und wählen Sie die Datei aus.</span><span class="sxs-lookup"><span data-stu-id="9c682-251">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="9c682-252">Geben Sie eine kurze Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="9c682-252">Provide a brief description.</span></span>

4. <span data-ttu-id="9c682-253">Geben Sie an, ob Sie eine Datei mit demselben Namen überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="9c682-253">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="9c682-254">Wenn Sie möchten, wissen Sie, welche Parameter für das Skript erforderlich sind, aktivieren Sie das Kontrollkästchen "Skriptparameter".</span><span class="sxs-lookup"><span data-stu-id="9c682-254">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="9c682-255">Geben Sie in das Textfeld ein Beispiel und eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="9c682-255">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="9c682-256">Klicken Sie auf **"Bestätigen".**</span><span class="sxs-lookup"><span data-stu-id="9c682-256">Click **Confirm**.</span></span> 

7. <span data-ttu-id="9c682-257">(Optional) Führen Sie den Befehl aus, um zu überprüfen, ob die Datei in die Bibliothek hochgeladen `library` wurde.</span><span class="sxs-lookup"><span data-stu-id="9c682-257">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="9c682-258">Abbrechen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="9c682-258">Cancel a command</span></span>
<span data-ttu-id="9c682-259">Sie können einen Befehl jederzeit während einer Sitzung abbrechen, indem Sie STRG +C drücken.</span><span class="sxs-lookup"><span data-stu-id="9c682-259">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="9c682-260">Wenn Sie diese Verknüpfung verwenden, wird der Befehl auf agentseitiger Seite nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="9c682-260">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="9c682-261">Es wird nur der Befehl im Portal abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="9c682-261">It will only cancel the command in the portal.</span></span> <span data-ttu-id="9c682-262">Das Ändern von Vorgängen wie "Korrigieren" kann also fortgesetzt werden, während der Befehl abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="9c682-262">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

## <a name="run-a-powershell-script"></a><span data-ttu-id="9c682-263">Ausführen eines PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="9c682-263">Run a PowerShell script</span></span> 

<span data-ttu-id="9c682-264">Bevor Sie ein PowerShell-Skript ausführen können, müssen Sie es zuerst in die Bibliothek hochladen.</span><span class="sxs-lookup"><span data-stu-id="9c682-264">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="9c682-265">Verwenden Sie nach dem Hochladen des Skripts in die Bibliothek den `run` Befehl, um das Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9c682-265">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="9c682-266">Wenn Sie beabsichtigen, in der Sitzung ein nicht signiertes Skript zu verwenden, müssen Sie die Einstellung auf der Seite ["Erweiterte Features"](advanced-features.md) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9c682-266">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="9c682-267">Wenn Sie die Verwendung von nicht signierten Skripts zulassen, können Sie Bedrohungen mehr ausgesetzt sein.</span><span class="sxs-lookup"><span data-stu-id="9c682-267">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="9c682-268">Anwenden von Befehlsparametern</span><span class="sxs-lookup"><span data-stu-id="9c682-268">Apply command parameters</span></span>

- <span data-ttu-id="9c682-269">Sehen Sie sich die Konsolenhilfe an, um mehr über Befehlsparameter zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="9c682-269">View the console help to learn about command parameters.</span></span> <span data-ttu-id="9c682-270">Um mehr über einen einzelnen Befehl zu erfahren, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="9c682-270">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="9c682-271">Beachten Sie beim Anwenden von Parametern auf Befehle, dass Parameter basierend auf einer festen Reihenfolge behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="9c682-271">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="9c682-272">Geben Sie beim Angeben von Parametern außerhalb der festen Reihenfolge den Namen des Parameters mit einem Bindestrich an, bevor Sie den Wert angeben:</span><span class="sxs-lookup"><span data-stu-id="9c682-272">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="9c682-273">Wenn Sie Befehle verwenden, die über erforderliche Befehle verfügen, können Sie Flags verwenden:</span><span class="sxs-lookup"><span data-stu-id="9c682-273">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="9c682-274">`<command name> -type file -id <file path> - auto` oder `remediate file <file path> - auto`.</span><span class="sxs-lookup"><span data-stu-id="9c682-274">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="9c682-275">Unterstützte Ausgabetypen</span><span class="sxs-lookup"><span data-stu-id="9c682-275">Supported output types</span></span>

<span data-ttu-id="9c682-276">Live response supports table and JSON format output types.</span><span class="sxs-lookup"><span data-stu-id="9c682-276">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="9c682-277">Für jeden Befehl gibt es ein Standardausgabeverhalten.</span><span class="sxs-lookup"><span data-stu-id="9c682-277">For each command, there's a default output behavior.</span></span> <span data-ttu-id="9c682-278">Mit den folgenden Befehlen können Sie die Ausgabe im bevorzugten Ausgabeformat ändern:</span><span class="sxs-lookup"><span data-stu-id="9c682-278">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="9c682-279">Aufgrund des begrenzten Platzes werden weniger Felder im Tabellenformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c682-279">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="9c682-280">Um weitere Details in der Ausgabe anzuzeigen, können Sie den JSON-Ausgabebefehl verwenden, damit weitere Details angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9c682-280">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="9c682-281">Unterstützte Ausgabepipes</span><span class="sxs-lookup"><span data-stu-id="9c682-281">Supported output pipes</span></span>

<span data-ttu-id="9c682-282">Live response supports output pipeing to CLI and file.</span><span class="sxs-lookup"><span data-stu-id="9c682-282">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="9c682-283">CLI ist das Standardausgabeverhalten.</span><span class="sxs-lookup"><span data-stu-id="9c682-283">CLI is the default output behavior.</span></span> <span data-ttu-id="9c682-284">Mit dem folgenden Befehl können Sie die Ausgabe an eine Datei weiterleitung: [Befehl] > [Dateiname].txt.</span><span class="sxs-lookup"><span data-stu-id="9c682-284">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="9c682-285">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9c682-285">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="9c682-286">Anzeigen des Befehlsprotokolls</span><span class="sxs-lookup"><span data-stu-id="9c682-286">View the command log</span></span>

<span data-ttu-id="9c682-287">Wählen Sie die Registerkarte **"Befehlsprotokoll"** aus, um die Befehle anzuzeigen, die während einer Sitzung auf dem Gerät verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9c682-287">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="9c682-288">Jeder Befehl wird mit vollständigen Details nachverfolgt, z. B.:</span><span class="sxs-lookup"><span data-stu-id="9c682-288">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="9c682-289">ID</span><span class="sxs-lookup"><span data-stu-id="9c682-289">ID</span></span>
- <span data-ttu-id="9c682-290">Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="9c682-290">Command line</span></span>
- <span data-ttu-id="9c682-291">Dauer</span><span class="sxs-lookup"><span data-stu-id="9c682-291">Duration</span></span>
- <span data-ttu-id="9c682-292">Status- und Eingabe- oder Ausgabe-Seitenleiste</span><span class="sxs-lookup"><span data-stu-id="9c682-292">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="9c682-293">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9c682-293">Limitations</span></span>

- <span data-ttu-id="9c682-294">Live-Antwortsitzungen sind jeweils auf 25 Liveantwortsitzungen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="9c682-294">Live response sessions are limited to 25 live response sessions at a time.</span></span>
- <span data-ttu-id="9c682-295">Das inaktive Timeout der Live-Antwortsitzung beträgt 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="9c682-295">Live response session inactive timeout value is 30 minutes.</span></span> 
- <span data-ttu-id="9c682-296">Ein Benutzer kann bis zu 10 gleichzeitige Sitzungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="9c682-296">A user can initiate up to 10 concurrent sessions.</span></span>
- <span data-ttu-id="9c682-297">Ein Gerät kann sich jeweils nur in einer Sitzung enthalten.</span><span class="sxs-lookup"><span data-stu-id="9c682-297">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="9c682-298">Es gelten die folgenden Dateigrößenbeschränkungen:</span><span class="sxs-lookup"><span data-stu-id="9c682-298">The following file size limits apply:</span></span>
   - <span data-ttu-id="9c682-299">`getfile` Grenzwert: 3 GB</span><span class="sxs-lookup"><span data-stu-id="9c682-299">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="9c682-300">`fileinfo` Grenzwert: 10 GB</span><span class="sxs-lookup"><span data-stu-id="9c682-300">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="9c682-301">`library` Grenzwert: 250 MB</span><span class="sxs-lookup"><span data-stu-id="9c682-301">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="9c682-302">Verwandter Artikel</span><span class="sxs-lookup"><span data-stu-id="9c682-302">Related article</span></span>
- [<span data-ttu-id="9c682-303">Kommandobeispiele für Liveantworten</span><span class="sxs-lookup"><span data-stu-id="9c682-303">Live response command examples</span></span>](live-response-command-examples.md)
