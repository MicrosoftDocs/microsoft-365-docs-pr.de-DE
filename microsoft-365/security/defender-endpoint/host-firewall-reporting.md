---
title: Hostfirewall-Berichterstellung in Microsoft Defender für Endpunkt
description: Hosten und Anzeigen von Firewallberichten in Microsoft 365 Security Center.
keywords: Windows Defender, Firewall
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809308"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="1e100-104">Hostfirewall-Berichterstellung in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1e100-104">Host firewall reporting in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1e100-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1e100-105">**Applies to:**</span></span>
- [<span data-ttu-id="1e100-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1e100-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1e100-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e100-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="1e100-108">Wenn Sie Administrator sind, können Sie jetzt Firewallberichte für [Microsoft 365 Security Center hosten.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1e100-108">If you are an admin, you can now host firewall reporting to [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="1e100-109">Mit diesem Feature können Sie Windows 10 und Windows Server 2019-Firewallberichte von einem zentralen Ort anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e100-109">This feature enables you to view Windows 10 and Windows Server 2019 firewall reporting from a centralized location.</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1e100-110">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="1e100-110">What do you need to know before you begin?</span></span> 

- <span data-ttu-id="1e100-111">Sie müssen Windows 10 oder Windows Server 2019 ausführen.</span><span class="sxs-lookup"><span data-stu-id="1e100-111">You must be running Windows 10 or Windows Server 2019.</span></span>
- <span data-ttu-id="1e100-112">Informationen zum Onboarding von Geräten in den Microsoft Defender für Endpunktdienst finden Sie [hier.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="1e100-112">To onboard devices to the Microsoft Defender for Endpoint service, see [here](onboard-configure.md).</span></span> 
- <span data-ttu-id="1e100-113">Damit Microsoft 365 Security Center mit dem Empfangen der Daten beginnt, müssen Sie **Überwachungsereignisse** für Windows Defender Firewall mit erweiterter Sicherheit aktivieren:</span><span class="sxs-lookup"><span data-stu-id="1e100-113">For Microsoft 365 security center to start receiving the data, you must enable **Audit Events** for Windows Defender Firewall with Advanced Security:</span></span> 
    - [<span data-ttu-id="1e100-114">Audit Filtering Platform Packet Drop</span><span class="sxs-lookup"><span data-stu-id="1e100-114">Audit Filtering Platform Packet Drop</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [<span data-ttu-id="1e100-115">Überwachen der Filterplattformverbindung</span><span class="sxs-lookup"><span data-stu-id="1e100-115">Audit Filtering Platform Connection</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- <span data-ttu-id="1e100-116">Aktivieren Sie diese Ereignisse mithilfe des Gruppenrichtlinienobjekt-Editors, der lokalen Sicherheitsrichtlinie oder der befehle auditpol.exe.</span><span class="sxs-lookup"><span data-stu-id="1e100-116">Enable these events by using Group Policy Object Editor, Local Security Policy, or the auditpol.exe commands.</span></span> <span data-ttu-id="1e100-117">Weitere Informationen finden Sie [hier.](/windows/win32/fwp/auditing-and-logging)</span><span class="sxs-lookup"><span data-stu-id="1e100-117">For more information, see [here](/windows/win32/fwp/auditing-and-logging).</span></span> 
    - <span data-ttu-id="1e100-118">Die beiden PowerShell-Befehle sind:</span><span class="sxs-lookup"><span data-stu-id="1e100-118">The two PowerShell commands are:</span></span>
        - <span data-ttu-id="1e100-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="1e100-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span></span> 
        - <span data-ttu-id="1e100-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="1e100-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span></span> 

## <a name="the-process"></a><span data-ttu-id="1e100-121">Der Prozess</span><span class="sxs-lookup"><span data-stu-id="1e100-121">The process</span></span>
> [!NOTE]
> <span data-ttu-id="1e100-122">Stellen Sie sicher, dass Sie die Anweisungen aus dem obigen Abschnitt befolgen und Ihre Geräte ordnungsgemäß für die frühe Vorschauteilnahme konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1e100-122">Make sure to follow the instructions from the section above and properly configure your devices for the early preview participation.</span></span>

- <span data-ttu-id="1e100-123">Nach dem Aktivieren der Ereignisse beginnt Microsoft 365 Security Center mit der Überwachung der Daten.</span><span class="sxs-lookup"><span data-stu-id="1e100-123">After enabling the events, Microsoft 365 security center will start to monitor the data.</span></span>
    - <span data-ttu-id="1e100-124">Remote-IP, Remoteport, lokaler Port, lokale IP, Computername, Prozess über eingehende und ausgehende Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="1e100-124">Remote IP, Remote Port, Local Port, Local IP, Computer Name, Process across inbound and outbound connections.</span></span>
- <span data-ttu-id="1e100-125">Administratoren können jetzt Windows Firewallaktivität [sehen.](https://security.microsoft.com/firewall)</span><span class="sxs-lookup"><span data-stu-id="1e100-125">Admins can now see Windows host firewall activity [here](https://security.microsoft.com/firewall).</span></span>
    - <span data-ttu-id="1e100-126">Zusätzliche Berichte können durch Herunterladen des Skripts für [benutzerdefinierte Berichterstellung](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) erleichtert werden, um die Windows Defender Firewall Aktivitäten mithilfe von Power BI zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="1e100-126">Additional reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 
    - <span data-ttu-id="1e100-127">Es kann bis zu 12 Stunden dauern, bis die Daten widergespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="1e100-127">It can take up to 12 hours before the data is reflected.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="1e100-128">Unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="1e100-128">Supported scenarios</span></span>
<span data-ttu-id="1e100-129">Die folgenden Szenarien werden während der Ring0-Vorschau unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1e100-129">The following scenarios are supported during Ring0 Preview.</span></span> 

### <a name="firewall-reporting-in-security-center"></a><span data-ttu-id="1e100-130">Firewall-Berichterstellung im Security Center</span><span class="sxs-lookup"><span data-stu-id="1e100-130">Firewall reporting in security center</span></span>

<span data-ttu-id="1e100-131">Nachfolgend finden Sie einige Beispiele für die Firewallberichtsseiten.</span><span class="sxs-lookup"><span data-stu-id="1e100-131">Here is a couple of examples of the firewall report pages.</span></span> <span data-ttu-id="1e100-132">Hier finden Sie eine Zusammenfassung der eingehenden, ausgehenden und Anwendungsaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="1e100-132">Here you will find a summary of inbound, outbound, and application activity.</span></span> <span data-ttu-id="1e100-133">Sie können direkt auf diese Seite zugreifen, indem Sie zu https://security.microsoft.com/firewall .</span><span class="sxs-lookup"><span data-stu-id="1e100-133">You can access this page directly by going to https://security.microsoft.com/firewall.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1e100-134">![Hostfirewall-Berichtsseite](\images\host-firewall-reporting-page.png)</span><span class="sxs-lookup"><span data-stu-id="1e100-134">![Host firewall reporting page](\images\host-firewall-reporting-page.png)</span></span>

<span data-ttu-id="1e100-135">Auf diese Berichte können Sie auch zugreifen, indem Sie zum Abschnitt  >    >  **"Berichtssicherheitsberichtsgeräte"** am unteren Rand der Karte **"Firewall blocked Inbound Connections"** wechseln.</span><span class="sxs-lookup"><span data-stu-id="1e100-135">These reports can also be accessed by going to **Reports** > **Security Report** > **Devices** (section) located at the bottom of the **Firewall Blocked Inbound Connections** card.</span></span>

### <a name="from-computers-with-a-blocked-connection-to-device"></a><span data-ttu-id="1e100-136">Von "Computer mit blockierter Verbindung" zum Gerät</span><span class="sxs-lookup"><span data-stu-id="1e100-136">From "Computers with a blocked connection" to device</span></span>

<span data-ttu-id="1e100-137">Karten unterstützen interaktive Objekte.</span><span class="sxs-lookup"><span data-stu-id="1e100-137">Cards support interactive objects.</span></span> <span data-ttu-id="1e100-138">Sie können einen Drilldown zur Aktivität eines Geräts ausführen, indem Sie auf den Gerätenamen klicken, der auf einer neuen Registerkarte gestartet https://securitycenter.microsoft.com wird, und Sie direkt zur Registerkarte **"Gerätezeitachse"** führen.</span><span class="sxs-lookup"><span data-stu-id="1e100-138">You can drill into the activity of a device by clicking on the device name, which will launch https://securitycenter.microsoft.com in a new tab, and take you directly to the **Device Timeline** tab.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1e100-139">![Computer mit einer blockierten Verbindung](\images\firewall-reporting-blocked-connection.png)</span><span class="sxs-lookup"><span data-stu-id="1e100-139">![Computers with a blocked connection](\images\firewall-reporting-blocked-connection.png)</span></span>

<span data-ttu-id="1e100-140">Sie können jetzt die Registerkarte **"Zeitachse"** auswählen, auf der Sie eine Liste der Ereignisse erhalten, die diesem Gerät zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1e100-140">You can now select the **Timeline** tab, which will give you a list of events associated with that device.</span></span> 

<span data-ttu-id="1e100-141">Nachdem Sie auf die Schaltfläche **"Filter"** in der oberen rechten Ecke des Anzeigebereichs geklickt haben, wählen Sie den gewünschten Ereignistyp aus.</span><span class="sxs-lookup"><span data-stu-id="1e100-141">After clicking on the **Filters** button on the upper right-hand corner of the viewing pane, select the type of event you want.</span></span> <span data-ttu-id="1e100-142">Wählen Sie in diesem Fall **Firewall-Ereignisse** aus, und der Bereich wird nach Firewallereignissen gefiltert.</span><span class="sxs-lookup"><span data-stu-id="1e100-142">In this case, select **Firewall events** and the pane will be filtered to Firewall events.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1e100-143">![Filterschaltfläche](\images\firewall-reporting-filters-button.png)</span><span class="sxs-lookup"><span data-stu-id="1e100-143">![Filters button](\images\firewall-reporting-filters-button.png)</span></span>

### <a name="drill-into-advanced-hunting-preview-refresh"></a><span data-ttu-id="1e100-144">Drilldown zur erweiterten Suche (Vorschauaktualisierung)</span><span class="sxs-lookup"><span data-stu-id="1e100-144">Drill into advanced hunting (preview refresh)</span></span>

<span data-ttu-id="1e100-145">Firewallberichte unterstützen das Drillthrough von der Karte direkt in die **erweiterte Suche,** indem Sie auf die Schaltfläche **"Erweiterte Suche öffnen"** klicken.</span><span class="sxs-lookup"><span data-stu-id="1e100-145">Firewall reports support drilling from the card directly into **Advanced Hunting** by clicking the **Open Advanced hunting** button.</span></span> <span data-ttu-id="1e100-146">Die Abfrage wird vorab ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="1e100-146">The query will be pre-populated.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1e100-147">![Schaltfläche "Erweiterte Suche öffnen"](\images\firewall-reporting-advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="1e100-147">![Open Advanced hunting button](\images\firewall-reporting-advanced-hunting.png)</span></span>

<span data-ttu-id="1e100-148">Die Abfrage kann jetzt ausgeführt werden, und alle zugehörigen Firewallereignisse der letzten 30 Tage können untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="1e100-148">The query can now be executed, and all related Firewall events from the last 30 days can be explored.</span></span> 

<span data-ttu-id="1e100-149">Für zusätzliche Berichte oder benutzerdefinierte Änderungen kann die Abfrage zur weiteren Analyse in Power BI exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="1e100-149">For additional reporting, or custom changes, the query can be exported into Power BI for further analysis.</span></span> <span data-ttu-id="1e100-150">Benutzerdefinierte Berichte können durch Herunterladen des Skripts für [benutzerdefinierte Berichterstellung](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) erleichtert werden, um die Windows Defender Firewall Aktivitäten mithilfe von Power BI zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="1e100-150">Custom reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 

 