---
title: Verwalten, wie und wo Microsoft Defender Antivirus Updates empfängt
description: Verwalten Sie die Fallbackreihenfolge, wie Microsoft Defender Antivirus Schutzupdates empfängt.
keywords: Updates, Sicherheitsgrundwerte, Schutz, Fallbackreihenfolge, ADL, MMPC, UNC, Dateipfad, Freigeben, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: d218e9dea58f064fd54dbd9bb976f512a721df91
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007326"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a><span data-ttu-id="653fa-104">Verwalten der Quellen für Updates für Microsoft Defender Antivirus-Schutz</span><span class="sxs-lookup"><span data-stu-id="653fa-104">Manage the sources for Microsoft Defender Antivirus protection updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="653fa-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="653fa-105">**Applies to:**</span></span>

- [<span data-ttu-id="653fa-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="653fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

<span data-ttu-id="653fa-107">Es ist wichtig, den Virenschutz auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="653fa-107">Keeping your antivirus protection up to date is critical.</span></span> <span data-ttu-id="653fa-108">Es gibt zwei Komponenten zum Verwalten von Schutzupdates für Microsoft Defender Antivirus:</span><span class="sxs-lookup"><span data-stu-id="653fa-108">There are two components to managing protection updates for Microsoft Defender Antivirus:</span></span> 
- <span data-ttu-id="653fa-109">*Wo* die Updates heruntergeladen werden; Und</span><span class="sxs-lookup"><span data-stu-id="653fa-109">*Where* the updates are downloaded from; and</span></span> 
- <span data-ttu-id="653fa-110">*Wenn* Updates heruntergeladen und angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="653fa-110">*When* updates are downloaded and applied.</span></span> 

<span data-ttu-id="653fa-111">In diesem Artikel wird beschrieben, wie Sie angeben, von wo Updates heruntergeladen werden sollen (dies wird auch als Fallbackreihenfolge bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="653fa-111">This article describes how to specify from where updates should be downloaded (this is also known as the fallback order).</span></span> <span data-ttu-id="653fa-112">Eine Übersicht über die Funktionsweise von Updates und das Konfigurieren anderer Aspekte von Updates (z. B. Planen von Updates) finden Sie im Thema "Verwalten von [Microsoft Defender Antivirus-Updates und Anwenden](manage-updates-baselines-microsoft-defender-antivirus.md) von Basisplänen".</span><span class="sxs-lookup"><span data-stu-id="653fa-112">See [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md) topic for an overview on how updates work, and how to configure other aspects of updates (such as scheduling updates).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="653fa-113">Microsoft Defender Antivirus Security Intelligence-Updates werden über Windows Update bereitgestellt, und ab Montag, dem 21. Oktober 2019, werden alle Security Intelligence-Updates ausschließlich SHA-2 signiert.</span><span class="sxs-lookup"><span data-stu-id="653fa-113">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update and starting Monday, October 21, 2019, all security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="653fa-114">Ihre Geräte müssen aktualisiert werden, um SHA-2 zu unterstützen, um Ihre Sicherheitsintelligenz zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="653fa-114">Your devices must be updated to support SHA-2 in order to update your security intelligence.</span></span> <span data-ttu-id="653fa-115">Weitere Informationen finden Sie unter [2019 SHA-2 Code Signing Support-Anforderung für Windows und WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span><span class="sxs-lookup"><span data-stu-id="653fa-115">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>  


<a id="fallback-order"></a>

## <a name="fallback-order"></a><span data-ttu-id="653fa-116">Fallbackreihenfolge</span><span class="sxs-lookup"><span data-stu-id="653fa-116">Fallback order</span></span>

<span data-ttu-id="653fa-117">In der Regel konfigurieren Sie Endpunkte, um Updates aus einer primären Quelle, gefolgt von anderen Quellen, basierend auf Ihrer Netzwerkkonfiguration in der Reihenfolge ihrer Priorität einzeln herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="653fa-117">Typically, you configure endpoints to individually download updates from a primary source followed by other sources in order of priority, based on your network configuration.</span></span> <span data-ttu-id="653fa-118">Updates werden aus Quellen in der von Ihnen angegebenen Reihenfolge abgerufen.</span><span class="sxs-lookup"><span data-stu-id="653fa-118">Updates are obtained from sources in the order you specify.</span></span> <span data-ttu-id="653fa-119">Wenn keine Quelle verfügbar ist, wird die nächste Quelle in der Liste sofort verwendet.</span><span class="sxs-lookup"><span data-stu-id="653fa-119">If a source is not available, the next source in the list is used immediately.</span></span>

<span data-ttu-id="653fa-120">Wenn Updates veröffentlicht werden, wird eine Logik angewendet, um die Größe des Updates zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="653fa-120">When updates are published, some logic is applied to minimize the size of the update.</span></span> <span data-ttu-id="653fa-121">In den meisten Fällen werden nur die Unterschiede zwischen dem neuesten Update und dem update, das derzeit auf dem Gerät installiert ist (dies wird als Delta bezeichnet) heruntergeladen und angewendet.</span><span class="sxs-lookup"><span data-stu-id="653fa-121">In most cases, only the differences between the latest update and the update that is currently installed (this is referred to as the delta) on the device is downloaded and applied.</span></span> <span data-ttu-id="653fa-122">Die Größe des Deltas hängt jedoch von zwei Hauptfaktoren ab:</span><span class="sxs-lookup"><span data-stu-id="653fa-122">However, the size of the delta depends on two main factors:</span></span>
- <span data-ttu-id="653fa-123">Das Alter des letzten Updates auf dem Gerät; Und</span><span class="sxs-lookup"><span data-stu-id="653fa-123">The age of the last update on the device; and</span></span> 
- <span data-ttu-id="653fa-124">Die Quelle, die zum Herunterladen und Anwenden von Updates verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="653fa-124">The source used to download and apply updates.</span></span> 

<span data-ttu-id="653fa-125">Je älter die Updates auf einem Endpunkt sind, desto größer ist der Download.</span><span class="sxs-lookup"><span data-stu-id="653fa-125">The older the updates on an endpoint, the larger the download will be.</span></span> <span data-ttu-id="653fa-126">Sie müssen jedoch auch die Downloadhäufigkeit berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="653fa-126">However, you must also consider download frequency as well.</span></span> <span data-ttu-id="653fa-127">Ein häufigerer Updatezeitplan kann zu einer höheren Netzwerkauslastung führen, während ein weniger häufiger Zeitplan zu größeren Dateigrößen pro Download führen kann.</span><span class="sxs-lookup"><span data-stu-id="653fa-127">A more frequent update schedule can result in more network usage, whereas a less-frequent schedule can result in larger file sizes per download.</span></span> 

<span data-ttu-id="653fa-128">Es gibt fünf Speicherorte, an denen Sie angeben können, wo ein Endpunkt Updates erhalten soll:</span><span class="sxs-lookup"><span data-stu-id="653fa-128">There are five locations where you can specify where an endpoint should obtain updates:</span></span> 

- [<span data-ttu-id="653fa-129">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="653fa-129">Microsoft Update</span></span>](https://support.microsoft.com/help/12373/windows-update-faq)
- [<span data-ttu-id="653fa-130">Windows Server Update Service</span><span class="sxs-lookup"><span data-stu-id="653fa-130">Windows Server Update Service</span></span>](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [<span data-ttu-id="653fa-131">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="653fa-131">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/core/servers/manage/updates)
- [<span data-ttu-id="653fa-132">Netzwerkdateifreigabe</span><span class="sxs-lookup"><span data-stu-id="653fa-132">Network file share</span></span>](#unc-share)
- <span data-ttu-id="653fa-133">[Updates zur Sicherheitsintelligenz für Microsoft Defender Antivirus und andere Microsoft-Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates) (in Ihrer Richtlinie und Registrierung ist diese möglicherweise als Microsoft Malware Protection Center (MMPC) Security Intelligence aufgeführt, der frühere Name.)</span><span class="sxs-lookup"><span data-stu-id="653fa-133">[Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates) (Your policy and registry might have this listed as Microsoft Malware Protection Center (MMPC) security intelligence, its former name.)</span></span>

<span data-ttu-id="653fa-134">Um ein optimales Schutzniveau zu gewährleisten, ermöglicht Microsoft Update schnelle Versionen, was häufig kleinere Downloads bedeutet.</span><span class="sxs-lookup"><span data-stu-id="653fa-134">To ensure the best level of protection, Microsoft Update allows for rapid releases, which means smaller downloads on a frequent basis.</span></span> <span data-ttu-id="653fa-135">Die Updatequellen Windows Server Update Service, Microsoft Endpoint Configuration Manager und Microsoft Security Intelligence bieten weniger häufige Updates.</span><span class="sxs-lookup"><span data-stu-id="653fa-135">The Windows Server Update Service, Microsoft Endpoint Configuration Manager, and Microsoft security intelligence updates sources deliver less frequent updates.</span></span> <span data-ttu-id="653fa-136">Daher kann das Delta größer sein, was zu größeren Downloads führen kann.</span><span class="sxs-lookup"><span data-stu-id="653fa-136">Thus, the delta can be larger, resulting in larger downloads.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="653fa-137">Wenn Sie [Microsoft Security Intelligence-Seitenupdates](https://www.microsoft.com/security/portal/definitions/adl.aspx) nach Windows Server Update Service oder Microsoft Update als Fallbackquelle festgelegt haben, werden Updates nur dann von Security Intelligence-Updates heruntergeladen, wenn das aktuelle Update als veraltet betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="653fa-137">If you have set [Microsoft Security intelligence page](https://www.microsoft.com/security/portal/definitions/adl.aspx) updates as a fallback source after Windows Server Update Service or Microsoft Update, updates are only downloaded from security intelligence updates when the current update is considered out-of-date.</span></span> <span data-ttu-id="653fa-138">(Standardmäßig sind dies sieben aufeinander folgende Tage, an denen Updates aus dem Windows Server Update Service oder den Microsoft Update-Diensten nicht angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="653fa-138">(By default, this is seven consecutive days of not being able to apply updates from the Windows Server Update Service or Microsoft Update services).</span></span>
> <span data-ttu-id="653fa-139">Sie können jedoch [die Anzahl der Tage festlegen, bevor der Schutz als veraltet gemeldet wird.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)</span><span class="sxs-lookup"><span data-stu-id="653fa-139">You can, however, [set the number of days before protection is reported as out-of-date](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span><p>
> <span data-ttu-id="653fa-140">Ab Montag, 21. Oktober 2019, werden Security Intelligence-Updates ausschließlich SHA-2 signiert.</span><span class="sxs-lookup"><span data-stu-id="653fa-140">Starting Monday, October 21, 2019, security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="653fa-141">Geräte müssen aktualisiert werden, um SHA-2 zu unterstützen, um die neuesten Security Intelligence-Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="653fa-141">Devices must be updated to support SHA-2 in order to get the latest security intelligence updates.</span></span> <span data-ttu-id="653fa-142">Weitere Informationen finden Sie unter [2019 SHA-2 Code Signing Support-Anforderung für Windows und WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span><span class="sxs-lookup"><span data-stu-id="653fa-142">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>

<span data-ttu-id="653fa-143">Jede Quelle verfügt über typische Szenarien, die davon abhängen, wie Ihr Netzwerk konfiguriert ist, und wie oft updates veröffentlicht werden, wie in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="653fa-143">Each source has typical scenarios that depend on how your network is configured, in addition to how often they publish updates, as described in the following table:</span></span>

|<span data-ttu-id="653fa-144">Speicherort</span><span class="sxs-lookup"><span data-stu-id="653fa-144">Location</span></span> | <span data-ttu-id="653fa-145">Beispielszenario</span><span class="sxs-lookup"><span data-stu-id="653fa-145">Sample scenario</span></span> |
|---|---|
|<span data-ttu-id="653fa-146">Windows Server Update Service</span><span class="sxs-lookup"><span data-stu-id="653fa-146">Windows Server Update Service</span></span> | <span data-ttu-id="653fa-147">Sie verwenden den Windows Server Update Service zum Verwalten von Updates für Ihr Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="653fa-147">You are using Windows Server Update Service to manage updates for your network.</span></span>|
|<span data-ttu-id="653fa-148">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="653fa-148">Microsoft Update</span></span> | <span data-ttu-id="653fa-149">Sie möchten, dass Ihre Endpunkte eine direkte Verbindung mit Microsoft Update herstellen.</span><span class="sxs-lookup"><span data-stu-id="653fa-149">You want your endpoints to connect directly to Microsoft Update.</span></span> <span data-ttu-id="653fa-150">Dies kann für Endpunkte nützlich sein, die unregelmäßig eine Verbindung mit Ihrem Unternehmensnetzwerk herstellen, oder wenn Sie Ihre Updates nicht mit dem Windows Server Update Service verwalten.</span><span class="sxs-lookup"><span data-stu-id="653fa-150">This can be useful for endpoints that irregularly connect to your enterprise network, or if you do not use Windows Server Update Service to manage your updates.</span></span>|
|<span data-ttu-id="653fa-151">Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="653fa-151">File share</span></span> | <span data-ttu-id="653fa-152">Sie verfügen über nicht mit dem Internet verbundene Geräte (z. B. VMs).</span><span class="sxs-lookup"><span data-stu-id="653fa-152">You have non-Internet-connected devices (such as VMs).</span></span> <span data-ttu-id="653fa-153">Sie können Ihren mit dem Internet verbundenen VM-Host verwenden, um die Updates auf eine Netzwerkfreigabe herunterzuladen, von der die VMs die Updates abrufen können.</span><span class="sxs-lookup"><span data-stu-id="653fa-153">You can use your Internet-connected VM host to download the updates to a network share, from which the VMs can obtain the updates.</span></span> <span data-ttu-id="653fa-154">Im [VDI-Bereitstellungshandbuch](deployment-vdi-microsoft-defender-antivirus.md) erfahren Sie, wie Dateifreigaben in VDI-Umgebungen (Virtual Desktop Infrastructure) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="653fa-154">See the [VDI deployment guide](deployment-vdi-microsoft-defender-antivirus.md) for how file shares can be used in virtual desktop infrastructure (VDI) environments.</span></span>|
|<span data-ttu-id="653fa-155">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="653fa-155">Microsoft Endpoint Manager</span></span> | <span data-ttu-id="653fa-156">Sie verwenden Microsoft Endpoint Manager, um Ihre Endpunkte zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="653fa-156">You are using Microsoft Endpoint Manager to update your endpoints.</span></span>|
|<span data-ttu-id="653fa-157">Security Intelligence-Updates für Microsoft Defender Antivirus und andere Microsoft-Antischadsoftware (früher mmpc genannt)</span><span class="sxs-lookup"><span data-stu-id="653fa-157">Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware (formerly referred to as MMPC)</span></span> |<span data-ttu-id="653fa-158">[Stellen Sie sicher, dass Ihre Geräte aktualisiert wurden, um SHA-2 zu unterstützen.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)</span><span class="sxs-lookup"><span data-stu-id="653fa-158">[Make sure your devices are updated to support SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span> <span data-ttu-id="653fa-159">Microsoft Defender Antivirus Security Intelligence-Updates werden über Windows Update bereitgestellt, und ab Montag, dem 21. Oktober 2019, werden Security Intelligence-Updates ausschließlich SHA-2 signiert.</span><span class="sxs-lookup"><span data-stu-id="653fa-159">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update, and starting Monday October 21, 2019 security intelligence updates will be SHA-2 signed exclusively.</span></span> <br/><span data-ttu-id="653fa-160">Laden Sie die neuesten Schutzupdates aufgrund einer kürzlichen Infektion herunter, oder um ein sicheres Basisimage für die [VDI-Bereitstellung](deployment-vdi-microsoft-defender-antivirus.md)bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="653fa-160">Download the latest protection updates because of a recent infection or to help provision a strong, base image for [VDI deployment](deployment-vdi-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="653fa-161">Diese Option sollte in der Regel nur als endgültige Fallbackquelle und nicht als primäre Quelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="653fa-161">This option should generally be used only as a final fallback source, and not the primary source.</span></span> <span data-ttu-id="653fa-162">Es wird nur verwendet, wenn Updates für eine bestimmte [Anzahl von Tagen](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)nicht aus Windows Server Update Service oder Microsoft Update heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="653fa-162">It will only be used if updates cannot be downloaded from Windows Server Update Service or Microsoft Update for [a specified number of days](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span>|

<span data-ttu-id="653fa-163">Sie können die Reihenfolge verwalten, in der Updatequellen mit Gruppenrichtlinien, Microsoft Endpoint Configuration Manager, PowerShell-Cmdlets und WMI verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="653fa-163">You can manage the order in which update sources are used with Group Policy, Microsoft Endpoint Configuration Manager, PowerShell cmdlets, and WMI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="653fa-164">Wenn Sie Windows Server Update Service als Downloadspeicherort festlegen, müssen Sie die Updates unabhängig vom Verwaltungstool genehmigen, das Sie zum Angeben des Speicherorts verwenden.</span><span class="sxs-lookup"><span data-stu-id="653fa-164">If you set Windows Server Update Service as a download location, you must approve the updates, regardless of the management tool you use to specify the location.</span></span> <span data-ttu-id="653fa-165">Sie können eine automatische Genehmigungsregel mit Windows Server Update Service einrichten, die hilfreich sein kann, wenn Updates mindestens einmal täglich eintreffen.</span><span class="sxs-lookup"><span data-stu-id="653fa-165">You can set up an automatic approval rule with Windows Server Update Service, which might be useful as updates arrive at least once a day.</span></span> <span data-ttu-id="653fa-166">Weitere Informationen finden Sie unter [Synchronisieren von Endpunktschutzupdates im eigenständigen Windows Server Update Service.](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="653fa-166">To learn more, see [synchronize endpoint protection updates in standalone Windows Server Update Service](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

<span data-ttu-id="653fa-167">In den Verfahren in diesem Artikel wird zuerst beschrieben, wie die Reihenfolge festgelegt und dann die **Dateifreigabeoption** eingerichtet wird, wenn Sie sie aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="653fa-167">The procedures in this article first describe how to set the order, and then how to set up the **File share** option if you have enabled it.</span></span>

## <a name="use-group-policy-to-manage-the-update-location"></a><span data-ttu-id="653fa-168">Verwenden von Gruppenrichtlinien zum Verwalten des Updatespeicherorts</span><span class="sxs-lookup"><span data-stu-id="653fa-168">Use Group Policy to manage the update location</span></span>

1. <span data-ttu-id="653fa-169">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="653fa-169">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="653fa-170">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="653fa-170">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="653fa-171">Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="653fa-171">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="653fa-172">Erweitern Sie die Struktur bis zu **Windows-Komponenten,** die  >  **Windows Defender**  >  **Signature aktualisiert,** und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="653fa-172">Expand the tree to **Windows components** > **Windows Defender** > **Signature updates** and configure the following settings:</span></span>

   1.  <span data-ttu-id="653fa-173">Doppelklicken Sie auf die Einstellung **"Definieren der Reihenfolge der Quellen für das Herunterladen von Sicherheitsupdates",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="653fa-173">Double-click the **Define the order of sources for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   2.  <span data-ttu-id="653fa-174">Geben Sie die Reihenfolge der Quellen, getrennt durch eine einzelne Pipe, ein, z. B.: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` , wie im folgenden Screenshot dargestellt.</span><span class="sxs-lookup"><span data-stu-id="653fa-174">Enter the order of sources, separated by a single pipe, for example: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC`, as shown in the following screenshot.</span></span>

      :::image type="content" source="../../media/wdav-order-update-sources.png" alt-text="Gruppenrichtlinieneinstellung, die die Reihenfolge der Quellen auflistet":::

   3. <span data-ttu-id="653fa-176">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="653fa-176">Select **OK**.</span></span> <span data-ttu-id="653fa-177">Dadurch wird die Reihenfolge der Schutzaktualisierungsquellen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="653fa-177">This will set the order of protection update sources.</span></span>

   4. <span data-ttu-id="653fa-178">Doppelklicken Sie auf die Einstellung **"Dateifreigaben zum Herunterladen von Sicherheitsupdates definieren",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="653fa-178">Double-click the **Define file shares for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   5. <span data-ttu-id="653fa-179">Geben Sie die Dateifreigabequelle an.</span><span class="sxs-lookup"><span data-stu-id="653fa-179">Specify the file share source.</span></span> <span data-ttu-id="653fa-180">Wenn Sie über mehrere Quellen verfügen, geben Sie jede Quelle in der Reihenfolge ein, in der sie verwendet werden sollen, getrennt durch ein einzelnes Pipe.</span><span class="sxs-lookup"><span data-stu-id="653fa-180">If you have multiple sources, enter each source in the order they should be used, separated by a single pipe.</span></span> <span data-ttu-id="653fa-181">Verwenden Sie [die Standard-UNC-Notation](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) zum Angeben des Pfads, z. B.: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` .</span><span class="sxs-lookup"><span data-stu-id="653fa-181">Use [standard UNC notation](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) for denoting the path, for example: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name`.</span></span>  <span data-ttu-id="653fa-182">Wenn Sie keine Pfade eingeben, wird diese Quelle übersprungen, wenn der virtuelle Computer Updates herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="653fa-182">If you do not enter any paths, then this source will be skipped when the VM downloads updates.</span></span>

   6. <span data-ttu-id="653fa-183">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="653fa-183">Click **OK**.</span></span> <span data-ttu-id="653fa-184">Dadurch wird die Reihenfolge der Dateifreigaben festgelegt, wenn auf diese Quelle in der Gruppenrichtlinieneinstellung **"Definieren der Reihenfolge der Quellen...** " verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="653fa-184">This will set the order of file shares when that source is referenced in the **Define the order of sources...** group policy setting.</span></span>

> [!NOTE]
> <span data-ttu-id="653fa-185">Für Windows 10, Version 1703 bis einschließlich 1809, lautet der Richtlinienpfad **Windows-Komponenten > Microsoft Defender Antivirus > Signaturupdates** für Windows 10, Version 1903, der Richtlinienpfad **ist Windows-Komponenten > Microsoft Defender Antivirus > Security Intelligence Updates.**</span><span class="sxs-lookup"><span data-stu-id="653fa-185">For Windows 10, versions 1703 up to and including 1809, the policy path is **Windows Components > Microsoft Defender Antivirus > Signature Updates** For Windows 10, version 1903, the policy path is **Windows Components > Microsoft Defender Antivirus > Security Intelligence Updates**</span></span>

## <a name="use-configuration-manager-to-manage-the-update-location"></a><span data-ttu-id="653fa-186">Verwenden von Configuration Manager zum Verwalten des Updatespeicherorts</span><span class="sxs-lookup"><span data-stu-id="653fa-186">Use Configuration Manager to manage the update location</span></span>

<span data-ttu-id="653fa-187">Weitere Informationen zum Konfigurieren von Microsoft Endpoint Manager (current branch) finden Sie unter Konfigurieren von [Security Intelligence-Updates für Endpoint Protection.](/configmgr/protect/deploy-use/endpoint-definition-updates)</span><span class="sxs-lookup"><span data-stu-id="653fa-187">See [Configure Security intelligence Updates for Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a><span data-ttu-id="653fa-188">Verwenden von PowerShell-Cmdlets zum Verwalten des Updatespeicherorts</span><span class="sxs-lookup"><span data-stu-id="653fa-188">Use PowerShell cmdlets to manage the update location</span></span>

<span data-ttu-id="653fa-189">Verwenden Sie die folgenden PowerShell-Cmdlets, um die Updatereihenfolge festzulegen.</span><span class="sxs-lookup"><span data-stu-id="653fa-189">Use the following PowerShell cmdlets to set the update order.</span></span>

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
<span data-ttu-id="653fa-190">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="653fa-190">See the following articles for more information:</span></span>
- [<span data-ttu-id="653fa-191">Set-MpPreference -SignatureFallbackOrder</span><span class="sxs-lookup"><span data-stu-id="653fa-191">Set-MpPreference -SignatureFallbackOrder</span></span>](/powershell/module/defender/set-mppreference)
- [<span data-ttu-id="653fa-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span><span class="sxs-lookup"><span data-stu-id="653fa-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span></span>](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [<span data-ttu-id="653fa-193">Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="653fa-193">Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="653fa-194">Defender-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="653fa-194">Defender cmdlets</span></span>](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a><span data-ttu-id="653fa-195">Verwenden der Windows-Verwaltungsanweisung (Windows Management Instruction, WMI) zum Verwalten des Updatespeicherorts</span><span class="sxs-lookup"><span data-stu-id="653fa-195">Use Windows Management Instruction (WMI) to manage the update location</span></span>

<span data-ttu-id="653fa-196">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="653fa-196">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

<span data-ttu-id="653fa-197">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="653fa-197">See the following articles for more information:</span></span>
- [<span data-ttu-id="653fa-198">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="653fa-198">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a><span data-ttu-id="653fa-199">Verwenden der mobilen Geräteverwaltung (Mobile Device Management, MDM) zum Verwalten des Updatespeicherorts</span><span class="sxs-lookup"><span data-stu-id="653fa-199">Use Mobile Device Management (MDM) to manage the update location</span></span>

<span data-ttu-id="653fa-200">Weitere Informationen zum Konfigurieren von MDM finden Sie unter ["Richtlinien-CSP – Defender/SignatureUpdateFallbackOrder".](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder)</span><span class="sxs-lookup"><span data-stu-id="653fa-200">See [Policy CSP - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) for details on configuring MDM.</span></span>

## <a name="what-if-were-using-a-third-party-vendor"></a><span data-ttu-id="653fa-201">Was geschieht, wenn wir einen Drittanbieter verwenden?</span><span class="sxs-lookup"><span data-stu-id="653fa-201">What if we're using a third-party vendor?</span></span>

<span data-ttu-id="653fa-202">In diesem Artikel wird beschrieben, wie Updates für Microsoft Defender Antivirus konfiguriert und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="653fa-202">This article describes how to configure and manage updates for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="653fa-203">Für diese Aufgaben können jedoch Drittanbieter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="653fa-203">However, third-party vendors can be used to perform these tasks.</span></span> 

<span data-ttu-id="653fa-204">Angenommen, Contoso hat Fabrikam für die Verwaltung seiner Sicherheitslösung eingestellt, die Microsoft Defender Antivirus umfasst.</span><span class="sxs-lookup"><span data-stu-id="653fa-204">For example, suppose that Contoso has hired Fabrikam to manage their security solution, which includes Microsoft Defender Antivirus.</span></span> <span data-ttu-id="653fa-205">Fabrikam verwendet in der Regel [Windows Verwaltungsinstrumentation,](./use-wmi-microsoft-defender-antivirus.md) [PowerShell-Cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md)oder [Windows Befehlszeile,](./command-line-arguments-microsoft-defender-antivirus.md) um Patches und Updates bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="653fa-205">Fabrikam typically uses [Windows Management Instrumentation](./use-wmi-microsoft-defender-antivirus.md), [PowerShell cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md), or [Windows command-line](./command-line-arguments-microsoft-defender-antivirus.md) to deploy patches and updates.</span></span> 

> [!NOTE]
> <span data-ttu-id="653fa-206">Microsoft teste keine Drittanbieterlösungen für die Verwaltung von Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="653fa-206">Microsoft does not test third-party solutions for managing Microsoft Defender Antivirus.</span></span>

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a><span data-ttu-id="653fa-207">Erstellen einer UNC-Freigabe für Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="653fa-207">Create a UNC share for security intelligence updates</span></span>

<span data-ttu-id="653fa-208">Richten Sie eine Netzwerkdateifreigabe (UNC/zugeordnetes Laufwerk) ein, um Sicherheitsupdates mithilfe einer geplanten Aufgabe von der MMPC-Website herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="653fa-208">Set up a network file share (UNC/mapped drive) to download security intelligence updates from the MMPC site by using a scheduled task.</span></span>

1. <span data-ttu-id="653fa-209">Erstellen Sie auf dem System, auf dem Sie die Freigabe bereitstellen und die Updates herunterladen möchten, einen Ordner, in dem Sie das Skript speichern.</span><span class="sxs-lookup"><span data-stu-id="653fa-209">On the system on which you want to provision the share and download the updates, create a folder to which you will save the script.</span></span>
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. <span data-ttu-id="653fa-210">Erstellen Sie den Ordner, in dem Sie die Signaturupdates speichern.</span><span class="sxs-lookup"><span data-stu-id="653fa-210">Create the folder to which you will save the signature updates.</span></span>
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. <span data-ttu-id="653fa-211">Laden Sie das PowerShell-Skript aus [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)herunter.</span><span class="sxs-lookup"><span data-stu-id="653fa-211">Download the PowerShell script from [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).</span></span>

4. <span data-ttu-id="653fa-212">Klicken Sie auf **"Manuell herunterladen".**</span><span class="sxs-lookup"><span data-stu-id="653fa-212">Click **Manual Download**.</span></span>

5. <span data-ttu-id="653fa-213">Klicken Sie auf **die unformatierte nupkg-Datei herunterladen.**</span><span class="sxs-lookup"><span data-stu-id="653fa-213">Click **Download the raw nupkg file**.</span></span>

6. <span data-ttu-id="653fa-214">Extrahieren Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="653fa-214">Extract the file.</span></span>

7. <span data-ttu-id="653fa-215">Kopieren Sie die Datei SignatureDownloadCustomTask.ps1 in den zuvor erstellten Ordner C:\Tool\PS-Scripts\.</span><span class="sxs-lookup"><span data-stu-id="653fa-215">Copy the file SignatureDownloadCustomTask.ps1 to the folder you previously created, C:\Tool\PS-Scripts\ .</span></span>

8. <span data-ttu-id="653fa-216">Verwenden Sie die Befehlszeile, um die geplante Aufgabe einzurichten.</span><span class="sxs-lookup"><span data-stu-id="653fa-216">Use the command line to set up the scheduled task.</span></span>
    > [!NOTE]
    > <span data-ttu-id="653fa-217">Es gibt zwei Arten von Updates: vollständig und delta.</span><span class="sxs-lookup"><span data-stu-id="653fa-217">There are two types of updates: full and delta.</span></span>
   - <span data-ttu-id="653fa-218">Für x64 Delta:</span><span class="sxs-lookup"><span data-stu-id="653fa-218">For x64 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="653fa-219">Für x64 vollständig:</span><span class="sxs-lookup"><span data-stu-id="653fa-219">For x64 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="653fa-220">Für x86-Delta:</span><span class="sxs-lookup"><span data-stu-id="653fa-220">For x86 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="653fa-221">Für x86 vollständig:</span><span class="sxs-lookup"><span data-stu-id="653fa-221">For x86 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

    > [!NOTE]
    > <span data-ttu-id="653fa-222">Wenn die geplanten Vorgänge erstellt werden, finden Sie diese im Aufgabenplaner unter Microsoft\Windows\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="653fa-222">When the scheduled tasks are created, you can find these in the Task Scheduler under Microsoft\Windows\Windows Defender</span></span>
9. <span data-ttu-id="653fa-223">Führen Sie jede Aufgabe manuell aus, und stellen Sie sicher, dass Daten (mpam-d.exe, mpam-fe.exe und nis_full.exe) in den folgenden Ordnern vorhanden sind (Möglicherweise haben Sie unterschiedliche Speicherorte ausgewählt):</span><span class="sxs-lookup"><span data-stu-id="653fa-223">Run each task manually and verify that you have data (mpam-d.exe, mpam-fe.exe, and nis_full.exe) in the following folders (you might have chosen different locations):</span></span>

   - <span data-ttu-id="653fa-224">C:\Temp\TempSigs\x86</span><span class="sxs-lookup"><span data-stu-id="653fa-224">C:\Temp\TempSigs\x86</span></span>
   - <span data-ttu-id="653fa-225">C:\Temp\TempSigs\x64</span><span class="sxs-lookup"><span data-stu-id="653fa-225">C:\Temp\TempSigs\x64</span></span>

   <span data-ttu-id="653fa-226">Wenn die geplante Aufgabe fehlschlägt, führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="653fa-226">If the scheduled task fails, run the following commands:</span></span>

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```
    > [!NOTE]
    > <span data-ttu-id="653fa-227">Probleme können auch auf die Ausführungsrichtlinie zurückzuführen sein.</span><span class="sxs-lookup"><span data-stu-id="653fa-227">Issues could also be due to execution policy.</span></span>
    
10. <span data-ttu-id="653fa-228">Erstellen Sie eine Freigabe, die auf C:\Temp\TempSigs verweist (z. B. \\ Server\Updates).</span><span class="sxs-lookup"><span data-stu-id="653fa-228">Create a share pointing to C:\Temp\TempSigs (e.g. \\server\updates).</span></span>
    > [!NOTE]
    > <span data-ttu-id="653fa-229">Authentifizierte Benutzer müssen mindestens über Lesezugriff verfügen.</span><span class="sxs-lookup"><span data-stu-id="653fa-229">At a minimum, authenticated users must have "Read" access.</span></span>
11. <span data-ttu-id="653fa-230">Legen Sie den Freigabespeicherort in der Richtlinie auf die Freigabe fest.</span><span class="sxs-lookup"><span data-stu-id="653fa-230">Set the share location in the policy to the share.</span></span>

    > [!NOTE]
    > <span data-ttu-id="653fa-231">Fügen Sie dem Pfad nicht den Ordner "x64" (oder "x86") hinzu.</span><span class="sxs-lookup"><span data-stu-id="653fa-231">Do not add the x64 (or x86) folder in the path.</span></span> <span data-ttu-id="653fa-232">Der mpcmdrun.exe Prozess fügt ihn automatisch hinzu.</span><span class="sxs-lookup"><span data-stu-id="653fa-232">The mpcmdrun.exe process adds it automatically.</span></span>

## <a name="related-articles"></a><span data-ttu-id="653fa-233">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="653fa-233">Related articles</span></span>

- [<span data-ttu-id="653fa-234">Bereitstellen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="653fa-234">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="653fa-235">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen</span><span class="sxs-lookup"><span data-stu-id="653fa-235">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="653fa-236">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="653fa-236">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="653fa-237">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="653fa-237">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="653fa-238">Verwalten von Updates für mobile Geräte und virtuelle Computer</span><span class="sxs-lookup"><span data-stu-id="653fa-238">Manage updates for mobile devices and VMs</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="653fa-239">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="653fa-239">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
