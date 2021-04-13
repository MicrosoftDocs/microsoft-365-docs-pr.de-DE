---
title: Definieren, wie mobile Geräte von Microsoft Defender Antivirus aktualisiert werden
description: Verwalten, wie mobile Geräte, z. B. Laptops, mit Microsoft Defender Antivirus Protection-Updates aktualisiert werden sollen.
keywords: updates, protection, schedule updates, battery, mobile device, laptop, notebook, opt-in, microsoft update, wsus, override
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f67330e1ccd7361c3982b76a6ab8754db23bd110
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690395"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a><span data-ttu-id="cabf1-104">Verwalten von Updates für mobile Geräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="cabf1-104">Manage updates for mobile devices and virtual machines (VMs)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cabf1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cabf1-105">**Applies to:**</span></span>

- [<span data-ttu-id="cabf1-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cabf1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cabf1-107">Mobile Geräte und virtuelle Computer erfordern möglicherweise mehr Konfiguration, um sicherzustellen, dass die Leistung nicht von Updates betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="cabf1-107">Mobile devices and VMs may require more configuration to ensure performance is not impacted by updates.</span></span>

<span data-ttu-id="cabf1-108">Es gibt zwei Einstellungen, die für diese Geräte nützlich sind:</span><span class="sxs-lookup"><span data-stu-id="cabf1-108">There are two settings that are useful for these devices:</span></span>

- <span data-ttu-id="cabf1-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span><span class="sxs-lookup"><span data-stu-id="cabf1-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>
- <span data-ttu-id="cabf1-110">Verhindern von Sicherheitsintelligenzupdates bei Akkubetrieb</span><span class="sxs-lookup"><span data-stu-id="cabf1-110">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="cabf1-111">Die folgenden Artikel können auch in diesen Situationen hilfreich sein:</span><span class="sxs-lookup"><span data-stu-id="cabf1-111">The following articles may also be useful in these situations:</span></span>
- [<span data-ttu-id="cabf1-112">Konfigurieren geplanter Und Nachholscans</span><span class="sxs-lookup"><span data-stu-id="cabf1-112">Configuring scheduled and catch-up scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cabf1-113">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="cabf1-113">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cabf1-114">Bereitstellungshandbuch für Microsoft Defender Antivirus in einer Virtuellen Desktopinfrastruktur (Virtual Desktop Infrastructure, VDI)-Umgebung</span><span class="sxs-lookup"><span data-stu-id="cabf1-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a><span data-ttu-id="cabf1-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span><span class="sxs-lookup"><span data-stu-id="cabf1-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>

<span data-ttu-id="cabf1-116">Sie können Microsoft Update verwenden, um die Sicherheitsintelligenz auf mobilen Geräten mit Microsoft Defender Antivirus auf dem neuesten Stand zu halten, wenn sie nicht mit dem Unternehmensnetzwerk verbunden sind oder anderweitig keine WSUS-Verbindung haben.</span><span class="sxs-lookup"><span data-stu-id="cabf1-116">You can use Microsoft Update to keep Security intelligence on mobile devices running Microsoft Defender Antivirus up to date when they are not connected to the corporate network or don't otherwise have a WSUS connection.</span></span> 

<span data-ttu-id="cabf1-117">Dies bedeutet, dass Schutzupdates auf Geräten (über Microsoft Update) zugestellt werden können, auch wenn Sie WSUS so festgelegt haben, dass Microsoft Update außer Kraft gesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="cabf1-117">This means that protection updates can be delivered to devices (via Microsoft Update) even if you have set WSUS to override Microsoft Update.</span></span>

<span data-ttu-id="cabf1-118">Sie können sich auf dem mobilen Gerät auf einer der folgenden Arten für Microsoft Update entscheiden:</span><span class="sxs-lookup"><span data-stu-id="cabf1-118">You can opt in to Microsoft Update on the mobile device in one of the following ways:</span></span>

- <span data-ttu-id="cabf1-119">Ändern Sie die Einstellung mit Gruppenrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="cabf1-119">Change the setting with Group Policy.</span></span>
- <span data-ttu-id="cabf1-120">Verwenden Sie ein VBScript, um ein Skript zu erstellen, und führen Sie es dann auf jedem Computer im Netzwerk aus.</span><span class="sxs-lookup"><span data-stu-id="cabf1-120">Use a VBScript to create a script, then run it on each computer in your network.</span></span>
- <span data-ttu-id="cabf1-121">Wählen Sie jeden Computer im Netzwerk manuell über das Menü **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="cabf1-121">Manually opt in every computer on your network through the **Settings** menu.</span></span>

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a><span data-ttu-id="cabf1-122">Verwenden von Gruppenrichtlinien zum Opt-in für Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="cabf1-122">Use Group Policy to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="cabf1-123">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="cabf1-123">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="cabf1-124">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="cabf1-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="cabf1-125">Wählen **Sie Richtlinien** und dann Administrative Vorlagen **aus.**</span><span class="sxs-lookup"><span data-stu-id="cabf1-125">Select **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="cabf1-126">Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus** Signature  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="cabf1-126">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**.</span></span>

5. <span data-ttu-id="cabf1-127">Legen **Sie Sicherheitsintelligenzupdates von Microsoft Update** zulassen auf **Aktiviert,** und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="cabf1-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select  **OK**.</span></span>


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a><span data-ttu-id="cabf1-128">Verwenden eines VBScripts zum Opt-in für Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="cabf1-128">Use a VBScript to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="cabf1-129">Verwenden Sie die Anweisungen im [MSDN-Artikel Opt-In to Microsoft Update,](/windows/win32/wua_sdk/opt-in-to-microsoft-update) um das VBScript zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cabf1-129">Use the instructions in the MSDN article [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) to create the VBScript.</span></span>

2. <span data-ttu-id="cabf1-130">Führen Sie das vbScript aus, das Sie auf jedem Computer in Ihrem Netzwerk erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="cabf1-130">Run the VBScript you created on each computer in your network.</span></span>

### <a name="manually-opt-in-to-microsoft-update"></a><span data-ttu-id="cabf1-131">Manuelles Aktivieren von Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="cabf1-131">Manually opt in to Microsoft Update</span></span>

1. <span data-ttu-id="cabf1-132">Öffnen **Sie Windows Update** in Update **&** Sicherheitseinstellungen auf dem Computer, für den Sie sich entscheiden möchten.</span><span class="sxs-lookup"><span data-stu-id="cabf1-132">Open **Windows Update** in **Update & security** settings on the computer you want to opt in.</span></span>

2. <span data-ttu-id="cabf1-133">Wählen Sie **Erweiterte** Optionen aus.</span><span class="sxs-lookup"><span data-stu-id="cabf1-133">Select **Advanced** options.</span></span>

3. <span data-ttu-id="cabf1-134">Aktivieren Sie das Kontrollkästchen Updates für andere **Microsoft-Produkte geben, wenn ich Windows update.**</span><span class="sxs-lookup"><span data-stu-id="cabf1-134">Select the checkbox for **Give me updates for other Microsoft products when I update Windows**.</span></span>

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a><span data-ttu-id="cabf1-135">Verhindern von Sicherheitsintelligenzupdates bei Akkubetrieb</span><span class="sxs-lookup"><span data-stu-id="cabf1-135">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="cabf1-136">Sie können Microsoft Defender Antivirus so konfigurieren, dass nur Schutzupdates heruntergeladen werden, wenn der PC mit einer verkabelten Stromquelle verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="cabf1-136">You can configure Microsoft Defender Antivirus to only download protection updates when the PC is connected to a wired power source.</span></span> 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a><span data-ttu-id="cabf1-137">Verwenden von Gruppenrichtlinien zum Verhindern von Sicherheitsintelligenzupdates bei Akkubetrieb</span><span class="sxs-lookup"><span data-stu-id="cabf1-137">Use Group Policy to prevent security intelligence updates on battery power</span></span>

1.  <span data-ttu-id="cabf1-138">Öffnen Sie auf dem Computer [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))für die Gruppenrichtlinienverwaltung die Gruppenrichtlinienverwaltungskonsole, wählen Sie das Gruppenrichtlinienobjekt aus, das Sie konfigurieren möchten, und öffnen Sie es zur Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="cabf1-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), choose the Group Policy Object you want to configure, and open it for editing.</span></span>

2.  <span data-ttu-id="cabf1-139">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="cabf1-139">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3.  <span data-ttu-id="cabf1-140">Wählen **Sie Richtlinien** und dann Administrative Vorlagen **aus.**</span><span class="sxs-lookup"><span data-stu-id="cabf1-140">Select **Policies** then **Administrative templates**.</span></span>

4.  <span data-ttu-id="cabf1-141">Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus** Signature  >  **Updates,** und legen Sie dann **Allow security intelligence updates when running on battery power** auf Disabled .</span><span class="sxs-lookup"><span data-stu-id="cabf1-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**, and then set **Allow security intelligence updates when running on battery power** to **Disabled**.</span></span> <span data-ttu-id="cabf1-142">Wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="cabf1-142">Then select **OK**.</span></span> 

<span data-ttu-id="cabf1-143">Mit dieser Aktion wird verhindert, dass Schutzupdates heruntergeladen werden, wenn der PC mit Strom verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="cabf1-143">This action prevents protection updates from downloading when the PC is on battery power.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cabf1-144">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="cabf1-144">Related articles</span></span>

- [<span data-ttu-id="cabf1-145">Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten</span><span class="sxs-lookup"><span data-stu-id="cabf1-145">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cabf1-146">Aktualisieren und Verwalten von Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="cabf1-146">Update and manage Microsoft Defender Antivirus in Windows 10</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)