---
title: Definieren, wie mobile Geräte von Microsoft Defender Antivirus aktualisiert werden
description: Verwalten Sie, wie mobile Geräte, z. B. Laptops, mit Microsoft Defender Antivirus Schutzupdates aktualisiert werden sollen.
keywords: Updates, Schutz, Updates planen, Akku, mobiles Gerät, Laptop, Notizbuch, Anmelden, Microsoft Update, wsus, außer Kraft setzen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 809f4573c91f7f1882693cbd8c63d88b06b55c67
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926007"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a><span data-ttu-id="dc564-104">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="dc564-104">Manage updates for mobile devices and virtual machines (VMs)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dc564-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="dc564-105">**Applies to:**</span></span>

- [<span data-ttu-id="dc564-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="dc564-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="dc564-107">Mobile Geräte und VMs erfordern möglicherweise mehr Konfiguration, um sicherzustellen, dass die Leistung nicht durch Updates beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="dc564-107">Mobile devices and VMs may require more configuration to ensure performance is not impacted by updates.</span></span>

<span data-ttu-id="dc564-108">Es gibt zwei Einstellungen, die für diese Geräte nützlich sind:</span><span class="sxs-lookup"><span data-stu-id="dc564-108">There are two settings that are useful for these devices:</span></span>

- <span data-ttu-id="dc564-109">Aktivieren von Microsoft Update auf mobilen Computern ohne WSUS-Verbindung</span><span class="sxs-lookup"><span data-stu-id="dc564-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>
- <span data-ttu-id="dc564-110">Verhindern von Security Intelligence-Updates bei Akkubetrieb</span><span class="sxs-lookup"><span data-stu-id="dc564-110">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="dc564-111">Die folgenden Artikel können auch in diesen Situationen hilfreich sein:</span><span class="sxs-lookup"><span data-stu-id="dc564-111">The following articles may also be useful in these situations:</span></span>
- [<span data-ttu-id="dc564-112">Konfigurieren von geplanten Scans und Nachholscans</span><span class="sxs-lookup"><span data-stu-id="dc564-112">Configuring scheduled and catch-up scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dc564-113">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="dc564-113">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dc564-114">Bereitstellungshandbuch für Microsoft Defender Antivirus in einer VDI-Umgebung (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="dc564-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a><span data-ttu-id="dc564-115">Aktivieren von Microsoft Update auf mobilen Computern ohne WSUS-Verbindung</span><span class="sxs-lookup"><span data-stu-id="dc564-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>

<span data-ttu-id="dc564-116">Sie können Microsoft Update verwenden, um die Security Intelligence auf mobilen Geräten, die Microsoft Defender Antivirus ausgeführt werden, auf dem neuesten Stand zu halten, wenn sie nicht mit dem Unternehmensnetzwerk verbunden sind oder andernfalls keine WSUS-Verbindung haben.</span><span class="sxs-lookup"><span data-stu-id="dc564-116">You can use Microsoft Update to keep Security intelligence on mobile devices running Microsoft Defender Antivirus up to date when they are not connected to the corporate network or don't otherwise have a WSUS connection.</span></span> 

<span data-ttu-id="dc564-117">Dies bedeutet, dass Schutzupdates an Geräte (über Microsoft Update) übermittelt werden können, auch wenn Sie WSUS so festgelegt haben, dass Microsoft Update überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="dc564-117">This means that protection updates can be delivered to devices (via Microsoft Update) even if you have set WSUS to override Microsoft Update.</span></span>

<span data-ttu-id="dc564-118">Sie können Microsoft Update auf dem mobilen Gerät auf eine der folgenden Arten aktivieren:</span><span class="sxs-lookup"><span data-stu-id="dc564-118">You can opt in to Microsoft Update on the mobile device in one of the following ways:</span></span>

- <span data-ttu-id="dc564-119">Ändern Sie die Einstellung mithilfe von Gruppenrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="dc564-119">Change the setting with Group Policy.</span></span>
- <span data-ttu-id="dc564-120">Verwenden Sie ein VBScript, um ein Skript zu erstellen, und führen Sie es dann auf jedem Computer in Ihrem Netzwerk aus.</span><span class="sxs-lookup"><span data-stu-id="dc564-120">Use a VBScript to create a script, then run it on each computer in your network.</span></span>
- <span data-ttu-id="dc564-121">Melden Sie sich manuell über das **Menü Einstellungen** auf jedem Computer in Ihrem Netzwerk an.</span><span class="sxs-lookup"><span data-stu-id="dc564-121">Manually opt in every computer on your network through the **Settings** menu.</span></span>

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a><span data-ttu-id="dc564-122">Verwenden von Gruppenrichtlinien zum Aktivieren von Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="dc564-122">Use Group Policy to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="dc564-123">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="dc564-123">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="dc564-124">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="dc564-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="dc564-125">Wählen Sie **"Richtlinien"** und dann **"Administrative Vorlagen" aus.**</span><span class="sxs-lookup"><span data-stu-id="dc564-125">Select **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="dc564-126">Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Signaturupdates.**</span><span class="sxs-lookup"><span data-stu-id="dc564-126">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**.</span></span>

5. <span data-ttu-id="dc564-127">Legen Sie **"Sicherheitsintelligenz-Updates von Microsoft Update zulassen"** auf **"Aktiviert"** fest, und wählen Sie dann  **"OK"** aus.</span><span class="sxs-lookup"><span data-stu-id="dc564-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select  **OK**.</span></span>


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a><span data-ttu-id="dc564-128">Verwenden von VBScript zum Anmelden an Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="dc564-128">Use a VBScript to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="dc564-129">Verwenden Sie die Anweisungen im [MSDN-Artikel "Anmelden bei Microsoft Update",](/windows/win32/wua_sdk/opt-in-to-microsoft-update) um VBScript zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc564-129">Use the instructions in the MSDN article [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) to create the VBScript.</span></span>

2. <span data-ttu-id="dc564-130">Führen Sie das VBScript aus, das Sie auf jedem Computer in Ihrem Netzwerk erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="dc564-130">Run the VBScript you created on each computer in your network.</span></span>

### <a name="manually-opt-in-to-microsoft-update"></a><span data-ttu-id="dc564-131">Manuelles Anmelden bei Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="dc564-131">Manually opt in to Microsoft Update</span></span>

1. <span data-ttu-id="dc564-132">Öffnen Sie **Windows Update** in Update **& Sicherheitseinstellungen** auf dem Computer, den Sie sich anmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="dc564-132">Open **Windows Update** in **Update & security** settings on the computer you want to opt in.</span></span>

2. <span data-ttu-id="dc564-133">Wählen Sie **"Erweiterte** Optionen" aus.</span><span class="sxs-lookup"><span data-stu-id="dc564-133">Select **Advanced** options.</span></span>

3. <span data-ttu-id="dc564-134">Aktivieren Sie das Kontrollkästchen für **"Updates für andere Microsoft-Produkte bereitstellen", wenn ich Windows aktuaktuiere.**</span><span class="sxs-lookup"><span data-stu-id="dc564-134">Select the checkbox for **Give me updates for other Microsoft products when I update Windows**.</span></span>

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a><span data-ttu-id="dc564-135">Verhindern von Security Intelligence-Updates bei Akkubetrieb</span><span class="sxs-lookup"><span data-stu-id="dc564-135">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="dc564-136">Sie können Microsoft Defender Antivirus so konfigurieren, dass nur Schutzupdates heruntergeladen werden, wenn der PC mit einer kabelgebundenen Stromquelle verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="dc564-136">You can configure Microsoft Defender Antivirus to only download protection updates when the PC is connected to a wired power source.</span></span> 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a><span data-ttu-id="dc564-137">Verwenden von Gruppenrichtlinien, um Sicherheitsupdates bei Akkubetrieb zu verhindern</span><span class="sxs-lookup"><span data-stu-id="dc564-137">Use Group Policy to prevent security intelligence updates on battery power</span></span>

1.  <span data-ttu-id="dc564-138">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))wählen Sie das Gruppenrichtlinienobjekt aus, das Sie konfigurieren möchten, und öffnen Sie es zur Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="dc564-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), choose the Group Policy Object you want to configure, and open it for editing.</span></span>

2.  <span data-ttu-id="dc564-139">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="dc564-139">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3.  <span data-ttu-id="dc564-140">Wählen Sie **"Richtlinien"** und dann **"Administrative Vorlagen" aus.**</span><span class="sxs-lookup"><span data-stu-id="dc564-140">Select **Policies** then **Administrative templates**.</span></span>

4.  <span data-ttu-id="dc564-141">Erweitern Sie die Struktur bis **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Signaturupdates,** und legen Sie dann **"Allow security intelligence updates when running on battery power" auf** **"Disabled"** fest.</span><span class="sxs-lookup"><span data-stu-id="dc564-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**, and then set **Allow security intelligence updates when running on battery power** to **Disabled**.</span></span> <span data-ttu-id="dc564-142">Wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="dc564-142">Then select **OK**.</span></span> 

<span data-ttu-id="dc564-143">Diese Aktion verhindert, dass Schutzupdates heruntergeladen werden, wenn der PC mit Akkubetrieb betrieben wird.</span><span class="sxs-lookup"><span data-stu-id="dc564-143">This action prevents protection updates from downloading when the PC is on battery power.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dc564-144">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="dc564-144">Related articles</span></span>

- [<span data-ttu-id="dc564-145">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen</span><span class="sxs-lookup"><span data-stu-id="dc564-145">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dc564-146">Aktualisieren und Verwalten von Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="dc564-146">Update and manage Microsoft Defender Antivirus in Windows 10</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)