---
title: Erste Schritte mit dem lokalen Microsoft 365-DLP-Scanner (Data Loss Prevention, Verhinderung von Datenverlust) (Vorschau)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Einrichten des lokalen Microsoft 365-Scanners zur Verhinderung von Datenverlust
ms.openlocfilehash: 242956a3c6469756481fb823340e715a210562af
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114173"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="640ac-103">Erste Schritte mit dem lokalen Scanner zur Verhinderung von Datenverlust (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="640ac-103">Get started with the data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="640ac-104">Dieser Artikel führt Sie durch die Voraussetzungen und die Konfiguration für den lokalen Microsoft 365-Scanner zur Verhinderung von Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="640ac-104">This article walks you through the prerequisites and configuration for the Microsoft 365 data loss prevention on-premises scanner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="640ac-105">Vorabinformationen</span><span class="sxs-lookup"><span data-stu-id="640ac-105">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="640ac-106">SKU/Abonnement-Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="640ac-106">SKU/subscriptions licensing</span></span>

<span data-ttu-id="640ac-107">Bevor Sie mit dem lokalen DLP-Scanner beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und etwaige Add-Ons bestätigen.</span><span class="sxs-lookup"><span data-stu-id="640ac-107">Before you get started with DLP on-premises scanner, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="640ac-108">Um an der Vorschau teilnehmen zu können, muss dem Administratorkonto, das die DLP-Regeln erstellt, eine der folgenden Lizenzen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="640ac-108">To participate in the preview the admin account that sets up the DLP rules must be assigned one of the following licenses:</span></span>

- <span data-ttu-id="640ac-109">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="640ac-109">Microsoft 365 E5</span></span>
- <span data-ttu-id="640ac-110">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="640ac-110">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="640ac-111">Microsoft 365 E5 Information Protection & Governance</span><span class="sxs-lookup"><span data-stu-id="640ac-111">Microsoft 365 E5 Information Protection & Governance</span></span> 


<span data-ttu-id="640ac-112">Ausführliche Informationen zur Lizenzierung finden Sie unter: [Microsoft 365-Lizenzierungsrichtlinien für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="640ac-112">For full licensing details see: [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span></span>

### <a name="permissions"></a><span data-ttu-id="640ac-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="640ac-113">Permissions</span></span>


<span data-ttu-id="640ac-114">Daten vom lokalen DLP-Scanner können im [Aktivitäts-Explorer](data-classification-activity-explorer.md) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="640ac-114">Data from DLP on-premises scanner can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="640ac-115">Es gibt vier Rollen, die Berechtigungen für den Aktivitäten-Explorer gewähren; das Konto, das Sie für den Zugriff auf die Daten verwenden, muss eine der folgenden Rollen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="640ac-115">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="640ac-116">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="640ac-116">Global administrator</span></span>
- <span data-ttu-id="640ac-117">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="640ac-117">Compliance administrator</span></span>
- <span data-ttu-id="640ac-118">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="640ac-118">Security administrator</span></span>
- <span data-ttu-id="640ac-119">Compliancedatenadministrator</span><span class="sxs-lookup"><span data-stu-id="640ac-119">Compliance data administrator</span></span>

### <a name="dlp-on-premises-scanner-prerequisites"></a><span data-ttu-id="640ac-120">Voraussetzungen für den lokalen DLP-Scanner</span><span class="sxs-lookup"><span data-stu-id="640ac-120">DLP on-premises scanner prerequisites</span></span>

- <span data-ttu-id="640ac-p103">Der Azure Information Protection (AIP)-Scanner implementiert DLP-Richtlinienabgleich und -Richtliniendurchsetzung. Der Scanner wird als Teil des AIP-Clients installiert, sodass Ihre Installation alle Voraussetzungen für AIP, den AIP-Client und den AIP Unified Labeling-Scanner (Scanner für einheitliche Bezeichnungen) erfüllen muss.</span><span class="sxs-lookup"><span data-stu-id="640ac-p103">The Azure Information Protection (AIP) scanner implements DLP policy matching and policy enforcement. The scanner is installed as part of the AIP client so your installation must meet all the prerequisites  for AIP, the AIP client, and the AIP unified labeling scanner.</span></span>
- <span data-ttu-id="640ac-123">Bereitstellen des AIP-Clients und Scanners</span><span class="sxs-lookup"><span data-stu-id="640ac-123">Deploy the AIP  client and scanner.</span></span> <span data-ttu-id="640ac-124">Weitere Informationen finden Sie unter: [Installieren des einheitlichen AIP-Bezeichnungsclients](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) und [], unter [Konfigurieren und Installieren des Azure Information Protection Unified Labeling-Scanners](/azure/information-protection/deploy-aip-scanner-configure-install).</span><span class="sxs-lookup"><span data-stu-id="640ac-124">For more information [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) and [], see [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install).</span></span>
- <span data-ttu-id="640ac-125">Es muss mindestens ein Etikett und eine Richtlinie im Mandanten veröffentlicht sein, auch wenn alle Ihre Erkennungsregeln nur auf vertraulichen Informationstypen basieren.</span><span class="sxs-lookup"><span data-stu-id="640ac-125">There must be at least one label and policy published in the tenant, even if all your detection rules are based on sensitive information types only.</span></span>

## <a name="deploy-the-dlp-on-premises-scanner"></a><span data-ttu-id="640ac-126">Bereitstellen des lokalen DLP-Scanners</span><span class="sxs-lookup"><span data-stu-id="640ac-126">Deploy the DLP on-premises scanner</span></span>

1. <span data-ttu-id="640ac-127">Folgen Sie den Anweisungen unter [Installieren des AIP Unified Labeling-Clients](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span><span class="sxs-lookup"><span data-stu-id="640ac-127">Follow the procedures in [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> 
2. <span data-ttu-id="640ac-128">Folgen Sie den Anweisungen unter [Konfigurieren und Installieren des Azure Unified Labeling-Scanners](/azure/information-protection/deploy-aip-scanner-configure-install), um die Scannerinstallation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="640ac-128">Follow the procedures in [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install) to complete the scanner installation.</span></span>
    1. <span data-ttu-id="640ac-129">Die Konfiguration von Netzwerkerkennungsaufträgen ist ein optionaler Schritt.</span><span class="sxs-lookup"><span data-stu-id="640ac-129">Network discovery jobs configuration is an optional step.</span></span> <span data-ttu-id="640ac-130">Sie können es überspringen und bestimmte Repositorys definieren, die in Ihrem Inhaltsscanauftrag gescannt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="640ac-130">You can skip it and define specific repositories to be scanned in your content scan job.</span></span>
    2. <span data-ttu-id="640ac-131">Sie müssen einen Inhaltsscanauftrag erstellen und die Repositorys angeben, in denen Dateien gehostet werden, die vom DLP-Modul ausgewertet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="640ac-131">You must create content scan job and specify the repositories that host files that need to be evaluated by the DLP engine.</span></span>
    3. <span data-ttu-id="640ac-132">Aktivieren Sie DLP-Regeln im erstellten Inhaltsscanauftrag und setzen Sie die Option **Erzwingen** auf **Aus**, es sei denn, Sie möchten direkt mit der DLP-Durchsetzungsphase fortfahren.</span><span class="sxs-lookup"><span data-stu-id="640ac-132">Enable DLP rules in the created Content scan job, and set the **Enforce** option to **Off**, unless you want to proceed directly to the DLP enforcement stage.</span></span>
3. <span data-ttu-id="640ac-p106">Bestätigen Sie, das Ihr Inhaltsscanauftrag dem richtigen Cluster zugewiesen ist. Wenn Sie noch keinen Inhaltsscanauftrag erstellt haben, erstellen Sie einen neuen Auftrag und weisen Sie ihn dem Cluster zu, der die Scannerknoten enthält, auf denen die Public Preview-Version ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="640ac-p106">Verify that you content scan job is assigned to the right cluster. If you still did not create a content scan job create a new one and assign it to the cluster that contains the scanner nodes that run the public preview version.</span></span>

4. <span data-ttu-id="640ac-135">Stellen Sie eine Verbindung her zur [Azure Information Protection-Erweiterung im Azure-Portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) und fügen Sie Ihre Repositorys dem Inhaltsscanauftrag hinzu, der den Scan ausführt.</span><span class="sxs-lookup"><span data-stu-id="640ac-135">Connect to the [Azure Information Protection extension in Azure portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) and add your repositories to the content scan job that will perform the scan.</span></span>

5. <span data-ttu-id="640ac-136">Führen Sie einen der folgenden Schritte aus, um den Scan auszuführen:</span><span class="sxs-lookup"><span data-stu-id="640ac-136">Do one of the following to run your scan:</span></span>
    1. <span data-ttu-id="640ac-137">Festlegen des Scannerzeitplans</span><span class="sxs-lookup"><span data-stu-id="640ac-137">set the scanner schedule</span></span>
    1. <span data-ttu-id="640ac-138">Verwenden der manuellen Option **Jetzt scannen** im Portal</span><span class="sxs-lookup"><span data-stu-id="640ac-138">use the manual **Scan Now** option in the portal</span></span>
    1. <span data-ttu-id="640ac-139">oder führen Sie das **Start-AIPScan** PowerShell Cmdlet aus</span><span class="sxs-lookup"><span data-stu-id="640ac-139">or run **Start-AIPScan** PowerShell cmdlet</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="640ac-140">Denken Sie daran, dass der Scanner standardmäßig einen Delta-Scan des Repositorys ausführt und die Dateien, die bereits im vorherigen Scan-Zyklus gescannt wurden, übersprungen werden, es sei denn, die Datei wurde geändert oder Sie haben einen vollständigen erneuten Scan eingeleitet.</span><span class="sxs-lookup"><span data-stu-id="640ac-140">Remember that the scanner runs a delta scan of the repository by default and the files that were already scanned in the previous scan cycle will be skipped unless the file was changed or you initiated a full rescan.</span></span> <span data-ttu-id="640ac-141">Ein vollständiger Rescan kann mithilfe der Option **Alle Dateien erneut scannen** in der Benutzeroberfläche oder durch Ausführen von **Start-AIPScan-Reset** eingeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="640ac-141">Full rescan can be initiated by using **Rescan all files** option in the UI or by running **Start-AIPScan-Reset**.</span></span>

6.  <span data-ttu-id="640ac-142">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies) im Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="640ac-142">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center.</span></span>

7. <span data-ttu-id="640ac-143">Wählen Sie **Richtlinie erstellen** und erstellen Sie eine Test-DLP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="640ac-143">Choose **Create policy** and create a test DLP policy.</span></span> <span data-ttu-id="640ac-144">Weitere Informationen finden Sie unter [Erstellen einer DLP-Richtlinie aus einer Vorlage](create-a-dlp-policy-from-a-template.md) wenn Sie Hilfe beim Erstellen einer Richtlinie benötigen.</span><span class="sxs-lookup"><span data-stu-id="640ac-144">See [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md) if you need help creating a policy.</span></span> <span data-ttu-id="640ac-145">Stellen Sie sicher, dass Sie es im Test ausführen, bis Sie mit diesem Feature vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="640ac-145">Be sure to run it in test until you are comfortable with this feature.</span></span> <span data-ttu-id="640ac-146">Verwenden Sie diese Parameter für Ihre Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="640ac-146">Use these parameters for your policy:</span></span>
    1. <span data-ttu-id="640ac-147">Scope die lokale DLP-Scannerregel bei Bedarf auf bestimmte Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="640ac-147">Scope the DLP on-premises scanner rule to specific locations if needed.</span></span> <span data-ttu-id="640ac-148">Wenn Sie **Speicherorte** auf **Alle** festlegen, unterliegen alle vom Scanner gescannten Dateien der DLP-Regelübereinstimmung und -durchsetzung.</span><span class="sxs-lookup"><span data-stu-id="640ac-148">If you scope **locations** to **All**, all files scanned by the scanner will be subject to the DLP rule matching and enforcement.</span></span>
    1. <span data-ttu-id="640ac-149">Bei der Angabe der Standorte können Sie entweder eine Ausschluss- oder eine Einschlussliste verwenden.</span><span class="sxs-lookup"><span data-stu-id="640ac-149">When specifying the locations, you can use either exclusion or inclusion list.</span></span> <span data-ttu-id="640ac-150">Während der öffentlichen Vorschau können Sie nicht beide festlegen.</span><span class="sxs-lookup"><span data-stu-id="640ac-150">During public preview you cannot set both of them.</span></span> <span data-ttu-id="640ac-151">Sie können entweder festlegen, dass die Regel nur für Pfade relevant ist, die mit einem der in der Einschlussliste aufgeführten Muster übereinstimmen, oder für alle Dateien mit Ausnahme der Dateien, die mit dem in der Einschlussliste aufgeführten Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="640ac-151">You can either define that the rule is relevant only to paths matching one of the patterns listed in inclusion list or, all files, except the files matching the pattern listed in inclusion list.</span></span> <span data-ttu-id="640ac-152">Es werden keine lokalen Pfade unterstützt.</span><span class="sxs-lookup"><span data-stu-id="640ac-152">No local paths are supported.</span></span> <span data-ttu-id="640ac-153">Hier sind einige Beispiele für gültige Pfade:</span><span class="sxs-lookup"><span data-stu-id="640ac-153">Here are some examples of valid paths:</span></span>
      - <span data-ttu-id="640ac-154">\\\server\share</span><span class="sxs-lookup"><span data-stu-id="640ac-154">\\\server\share</span></span>
      - <span data-ttu-id="640ac-155">\\\server\share\folder1\subfolderabc</span><span class="sxs-lookup"><span data-stu-id="640ac-155">\\\server\share\folder1\subfolderabc</span></span>
      - <span data-ttu-id="640ac-156">\*\\folder1</span><span class="sxs-lookup"><span data-stu-id="640ac-156">\*\\folder1</span></span>
      - <span data-ttu-id="640ac-157">\*secret\*.docx</span><span class="sxs-lookup"><span data-stu-id="640ac-157">\*secret\*.docx</span></span>
      - <span data-ttu-id="640ac-158">\*secret\*.\*</span><span class="sxs-lookup"><span data-stu-id="640ac-158">\*secret\*.\*</span></span>
      - <span data-ttu-id="640ac-159"> https:// sp2010.local/sites/HR</span><span class="sxs-lookup"><span data-stu-id="640ac-159">https:// sp2010.local/sites/HR</span></span>
      - <span data-ttu-id="640ac-160"> https://\*/HR</span><span class="sxs-lookup"><span data-stu-id="640ac-160">https://\*/HR</span></span> 
    3. <span data-ttu-id="640ac-161">Hier sind einige Beispiele für nicht akzeptable Werte:</span><span class="sxs-lookup"><span data-stu-id="640ac-161">Here are some examples of unacceptable values use:</span></span>
      - \*
      - <span data-ttu-id="640ac-162">\*\\a</span><span class="sxs-lookup"><span data-stu-id="640ac-162">\*\\a</span></span>
      - <span data-ttu-id="640ac-163">Aaa</span><span class="sxs-lookup"><span data-stu-id="640ac-163">Aaa</span></span>
      - <span data-ttu-id="640ac-164">c:</span><span class="sxs-lookup"><span data-stu-id="640ac-164">c:</span></span>\
      - <span data-ttu-id="640ac-165">C:\test</span><span class="sxs-lookup"><span data-stu-id="640ac-165">C:\test</span></span>

> [!IMPORTANT]
> <span data-ttu-id="640ac-166">Die Ausschlussliste hat Vorrang vor der Einschlussliste.</span><span class="sxs-lookup"><span data-stu-id="640ac-166">The exclusion list takes precedence over the inclusions list.</span></span>

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="640ac-167">Anzeigen von lokalen DLP-Scannerwarnungen im DLP-Verwaltungsdashboard unter Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="640ac-167">Viewing DLP on-premises scanner alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="640ac-168">Öffnen Sie die [Seite zur Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies) im Microsoft 365 Compliance Center und wählen Sie **Warnungen** aus.</span><span class="sxs-lookup"><span data-stu-id="640ac-168">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center and select **Alerts**.</span></span>

2. <span data-ttu-id="640ac-169">Wenden Sie in [Konfigurieren und Anzeigen von Warnungen für DLP-Richtlinien](dlp-configure-view-alerts-policies.md) beschriebenen Verfahrensweisen an, um Warnungen für Ihre Endpunkt-DLP-Richtlinien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="640ac-169">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a><span data-ttu-id="640ac-170">Anzeigen des lokalen DLP-Scanners im Aktivitäten-Explorer und im Überwachungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="640ac-170">Viewing DLP on-premises scanner in activity explorer and audit log</span></span>

> [!NOTE]
> <span data-ttu-id="640ac-171">Für den lokalen Scanner muss die Überwachung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="640ac-171">The on-premises scanner requires that auditing be enabled.</span></span> <span data-ttu-id="640ac-172">In Microsoft 365 ist die Überwachung standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="640ac-172">In Microsoft 365 auditing is enabled by default.</span></span>

1. <span data-ttu-id="640ac-173">Öffnen Sie die Seite [Datenklassifizierung](https://compliance.microsoft.com/dataclassification?viewid=overview) für Ihre Domäne im Microsoft 365 Compliance Center und wählen Sie Aktivitäten-Explorer aus.</span><span class="sxs-lookup"><span data-stu-id="640ac-173">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and select Activity explorer.</span></span>

2. <span data-ttu-id="640ac-174">Beziehen Sie sich auf die Anweisungen unter [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md), um auf alle Daten für Ihre lokalen Scannerstandorte zuzugreifen und diese zu filtern.</span><span class="sxs-lookup"><span data-stu-id="640ac-174">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your on-premises scanner locations.</span></span>

3. <span data-ttu-id="640ac-175">Öffnen Sie das [Überwachungsprotokoll im Compliance Center](https://security.microsoft.com/auditlogsearch).</span><span class="sxs-lookup"><span data-stu-id="640ac-175">Open the [Audit log in the Compliance center](https://security.microsoft.com/auditlogsearch).</span></span> <span data-ttu-id="640ac-176">Während der öffentlichen Vorschau sind die DLP-Regelübereinstimmungen in der Benutzeroberfläche des Überwachungsprotokolls verfügbar oder können über [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps)PowerShell aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="640ac-176">During the public preview the DLP rule matches are available in Audit log UI or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell</span></span> 


## <a name="next-steps"></a><span data-ttu-id="640ac-177">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="640ac-177">Next steps</span></span>
<span data-ttu-id="640ac-178">Nachdem Sie eine Testrichtlinie für lokale DLP-Standorte bereitgestellt haben und die Aktivitätsdaten im Aktivitäten-Explorer anzeigen können, können Sie mit dem nächsten Schritt fortfahren. Sie können nun DLP-Richtlinien erstellen, die Ihre vertraulichen Elemente schützen.</span><span class="sxs-lookup"><span data-stu-id="640ac-178">Now that you have deployed a test policy for DLP on-premises locations and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="640ac-179">Verwendung von lokalem DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="640ac-179">Using DLP on-premises (preview)</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="640ac-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="640ac-180">See also</span></span>

- [<span data-ttu-id="640ac-181">Erfahren Sie mehr über den lokalen DLP-Scanner (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="640ac-181">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="640ac-182">Verwenden Sie den lokalen DLP-Scanner (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="640ac-182">Use DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="640ac-183">Informationen zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="640ac-183">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="640ac-184">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="640ac-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="640ac-185">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="640ac-185">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="640ac-186">Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="640ac-186">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)