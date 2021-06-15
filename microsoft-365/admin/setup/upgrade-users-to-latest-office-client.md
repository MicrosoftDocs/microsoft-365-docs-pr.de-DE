---
title: Aktualisieren Ihrer Office 2010 auf Microsoft 365 – Microsoft 365 Administrator
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID
- O365_Comm_SR_UpgradeOffice
- seo-marvel-may2020
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Erfahren Sie, wie Sie Microsoft Office für Benutzer in Ihrer Organisation auf den neuesten Office-Client aktualisieren.
ms.topic: article
ms.openlocfilehash: 877659e420079ed607adc13e5bbe44bdc979f5ac
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924695"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a><span data-ttu-id="00cb5-103">Aktualisieren Ihrer Microsoft 365 für Geschäftsbenutzer auf den neuesten Office-Client</span><span class="sxs-lookup"><span data-stu-id="00cb5-103">Upgrade your Microsoft 365 for business users to the latest Office client</span></span>

## <a name="office-2010-reaches-end-of-support"></a><span data-ttu-id="00cb5-104">Office 2010 erreicht das Ende des Supports</span><span class="sxs-lookup"><span data-stu-id="00cb5-104">Office 2010 reaches end-of-support</span></span>

<span data-ttu-id="00cb5-105">Office 2010 wurde der Support am 13. Oktober 2020 eingestellt.</span><span class="sxs-lookup"><span data-stu-id="00cb5-105">Office 2010 reached its end of support on October 13, 2020.</span></span> <span data-ttu-id="00cb5-106">Microsoft stellt Folgendes nicht mehr bereit:</span><span class="sxs-lookup"><span data-stu-id="00cb5-106">Microsoft will no longer provide the following:</span></span>

- <span data-ttu-id="00cb5-107">Technischer Support für Probleme</span><span class="sxs-lookup"><span data-stu-id="00cb5-107">Technical support for issues</span></span>

- <span data-ttu-id="00cb5-108">Fehlerbehebungen für ermittelte Probleme</span><span class="sxs-lookup"><span data-stu-id="00cb5-108">Bug fixes for issues that are discovered</span></span>

- <span data-ttu-id="00cb5-109">Sicherheitsfixes für erkannte Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="00cb5-109">Security fixes for vulnerabilities that are discovered</span></span>

<span data-ttu-id="00cb5-110">Weitere Informationen finden Sie [unter Office Roadmap zum Ende des Supports 2010.](/deployoffice/endofsupport/office-2010-end-support-roadmap)</span><span class="sxs-lookup"><span data-stu-id="00cb5-110">See [Office 2010 end of support roadmap](/deployoffice/endofsupport/office-2010-end-support-roadmap) for more information.</span></span>

 <span data-ttu-id="00cb5-111">**Ist dies das richtige Thema für Sie?**</span><span class="sxs-lookup"><span data-stu-id="00cb5-111">**Is this the right topic for you?**</span></span>
  
 <span data-ttu-id="00cb5-112">Wenn Sie der Administrator sind, der für das Microsoft 365 business-Abonnement in Ihrer Organisation verantwortlich ist, sind Sie am richtigen Ort.</span><span class="sxs-lookup"><span data-stu-id="00cb5-112">If you're the admin responsible for the Microsoft 365 for business subscription in your organization, you're in the right place.</span></span> <span data-ttu-id="00cb5-113">Administratoren sind in der Regel für Aufgaben wie das Verwalten von Benutzern, das Zurücksetzen von Kennwörtern, das Verwalten Office Installieren und Das Hinzufügen oder Entfernen von Lizenzen verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="00cb5-113">Admins are typically responsible for tasks like managing users, resetting passwords, managing Office installs and adding or removing licenses.</span></span>

 <span data-ttu-id="00cb5-114">Wenn Sie kein Administrator sind und über ein [Microsoft 365 Family](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) Produkt verfügen, finden Sie unter [How do I upgrade Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) informationen zum Aktualisieren Ihrer älteren Version für die private Nutzung von Office.</span><span class="sxs-lookup"><span data-stu-id="00cb5-114">If you're not an admin and you have a [Microsoft 365 Family](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) product, see [How do I upgrade Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) for information about upgrading your older, home use version of Office.</span></span>

## <a name="get-ready-to-upgrade-to-microsoft-365"></a><span data-ttu-id="00cb5-115">Vorbereiten des Upgrades auf Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="00cb5-115">Get ready to upgrade to Microsoft 365</span></span>

<span data-ttu-id="00cb5-116">Als Administrator steuern Sie, welche Version von Office Personen in Ihrer Organisation installieren können.</span><span class="sxs-lookup"><span data-stu-id="00cb5-116">As an admin, you control what version of Office people in your organization can install.</span></span> <span data-ttu-id="00cb5-117">Es wird dringend empfohlen, Benutzern in Ihrer Organisation, die ältere Versionen von Office wie Office 2010, Office 2013 oder Office 2016 ausführen, ein Upgrade auf die neueste Version zu ermöglichen, um die Vorteile der Sicherheits- und Produktivitätsverbesserungen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="00cb5-117">We highly recommend that you help users in your organization running older versions of Office such as Office 2010, Office 2013, or Office 2016 upgrade to the latest version to take advantage of its security and productivity improvements.</span></span>

## <a name="upgrade-steps"></a><span data-ttu-id="00cb5-118">Upgradeschritte</span><span class="sxs-lookup"><span data-stu-id="00cb5-118">Upgrade steps</span></span>

<span data-ttu-id="00cb5-p104">Im Folgenden werden Sie schrittweise durch den Prozess der Aktualisierung Ihrer Benutzer auf den neuesten Office-Desktopclient geführt. Es wird empfohlen, diese Schritte vor dem Beginn des Upgradeprozesses durchzulesen.</span><span class="sxs-lookup"><span data-stu-id="00cb5-p104">The steps below will guide you through the process of upgrading your users to the latest Office desktop client. We recommend you read through these steps before beginning the upgrade process.</span></span>
  
## <a name="step-1---check-system-requirements"></a><span data-ttu-id="00cb5-121">Schritt 1 - Prüfen der Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="00cb5-121">Step 1 - Check system requirements</span></span>

<span data-ttu-id="00cb5-122">[Überprüfen Sie die Systemanforderungen](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) für Office, um sicherzustellen, dass Ihre Geräte mit der neuesten Version von Office kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="00cb5-122">[Check the system requirements](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) for Office to make sure your devices are compatible with the latest version of Office.</span></span> <span data-ttu-id="00cb5-123">Neuere Versionen von Office können beispielsweise nicht auf Computern mit Windows XP oder Windows Vista installiert werden.</span><span class="sxs-lookup"><span data-stu-id="00cb5-123">For example, newer versions of Office can't be installed on computers running Windows XP or Windows Vista.</span></span>
  
> [!TIP]
> <span data-ttu-id="00cb5-124">Wenn Benutzer in Ihrer Organisation ältere Versionen von Windows auf ihren PCs oder Laptops ausführen, empfehlen wir ein Upgrade auf Windows 10.</span><span class="sxs-lookup"><span data-stu-id="00cb5-124">If you have users in your organization running older versions of Windows on their PCs or laptops, we recommend upgrading to Windows 10.</span></span> <span data-ttu-id="00cb5-125">Windows 7 hat das Ende des Supports erreicht.</span><span class="sxs-lookup"><span data-stu-id="00cb5-125">Windows 7 has reached end of support.</span></span> <span data-ttu-id="00cb5-126">Weitere Informationen finden Sie [unter "Support für Windows 7 endet im Januar 2020".](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="00cb5-126">Read [Support for Windows 7 ends in January 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) for more info.</span></span>

<span data-ttu-id="00cb5-127">Sehen Sie sich die [systemanforderungen Windows 10](https://www.microsoft.com/windows/windows-10-specifications) an, um festzustellen, ob Sie deren Betriebssysteme aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="00cb5-127">Check out the [Windows 10 system requirements](https://www.microsoft.com/windows/windows-10-specifications) to see if you can upgrade their operating systems.</span></span>

### <a name="check-application-compatibility"></a><span data-ttu-id="00cb5-128">Prüfen der Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="00cb5-128">Check application compatibility</span></span>

<span data-ttu-id="00cb5-129">Um ein erfolgreiches Upgrade zu gewährleisten, ist es empfehlenswert, Ihre Office-Anwendungen (einschließlich VBA-Skripts, Makros, Add-Ins von Drittanbietern sowie komplexe Dokumente und Kalkulationstabellen) zu identifizieren und deren Kompatibilität mit der neuesten Office-Version einzuschätzen.</span><span class="sxs-lookup"><span data-stu-id="00cb5-129">To ensure a successful upgrade, we recommend identifying your Office applications--including VBA scripts, macros, third-party add-ins, and complex documents and spreadsheets--and assessing their compatibility with the latest version of Office.</span></span>
  
<span data-ttu-id="00cb5-130">Wenn Sie beispielsweise mit der aktuellen Office-Installation Add-Ins von Drittanbietern verwenden, wenden Sie sich an den Hersteller, um sich zu vergewissern, dass diese mit der neuesten Version von Office kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="00cb5-130">For example, if you're using third-party add-ins with your current Office install, contact the manufacture to make sure they're compatible with the latest version of Office.</span></span>
  
## <a name="step-2---check-your-existing-subscription-plan"></a><span data-ttu-id="00cb5-131">Schritt 2 - Überprüfen des vorhandenen Abonnementplans</span><span class="sxs-lookup"><span data-stu-id="00cb5-131">Step 2 - Check your existing subscription plan</span></span>

<span data-ttu-id="00cb5-132">Einige Microsoft 365 Pläne enthalten nicht die vollständigen Desktopversionen von Office, und die Schritte zum Upgrade unterscheiden sich, wenn Ihr Plan keine Office enthält.</span><span class="sxs-lookup"><span data-stu-id="00cb5-132">Some Microsoft 365 plans don't include the full desktop versions of Office and the steps to upgrade are different if your plan doesn't include Office.</span></span>
  
<span data-ttu-id="00cb5-133">Sind Sie unsicher, welchen Abonnementplan Sie verwenden?</span><span class="sxs-lookup"><span data-stu-id="00cb5-133">Not sure which subscription plan you have?</span></span> <span data-ttu-id="00cb5-134">Erfahren [Sie, welche Microsoft 365 business-Abonnement ich habe?](../admin-overview/what-subscription-do-i-have.md)</span><span class="sxs-lookup"><span data-stu-id="00cb5-134">See [What Microsoft 365 for business subscription do I have?](../admin-overview/what-subscription-do-i-have.md)</span></span>
  
<span data-ttu-id="00cb5-135">Wenn Ihr vorhandener Plan Office enthält, fahren Sie mit [Schritt 3 - Deinstallieren von Office](#step-3---uninstall-office) fort.</span><span class="sxs-lookup"><span data-stu-id="00cb5-135">If your existing plan includes Office, move on to [Step 3 - Uninstall Office](#step-3---uninstall-office).</span></span>
  
<span data-ttu-id="00cb5-136">Wenn Ihr vorhandener Plan Office nicht enthält, wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="00cb5-136">If your existing plan doesn't include Office, then select from the options below:</span></span>
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a><span data-ttu-id="00cb5-137">Upgrade-Optionen für Pläne ohne Office</span><span class="sxs-lookup"><span data-stu-id="00cb5-137">Upgrade options for plans that don't include Office</span></span>

 <span data-ttu-id="00cb5-138">**Option 1: Wechseln Office Abonnements**</span><span class="sxs-lookup"><span data-stu-id="00cb5-138">**Option 1: Switch Office subscriptions**</span></span>

<span data-ttu-id="00cb5-139">Wechseln Sie zu einem Abonnement, das Office enthält.</span><span class="sxs-lookup"><span data-stu-id="00cb5-139">Switch to a subscription that includes Office.</span></span> <span data-ttu-id="00cb5-140">Weitere Informationen finden Sie unter [Wechseln zu einem anderen Microsoft 365 business-Plan.](../../commerce/subscriptions/switch-to-a-different-plan.md)</span><span class="sxs-lookup"><span data-stu-id="00cb5-140">See [Switch to a different Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md).</span></span>

<span data-ttu-id="00cb5-141">**Option 2: Kaufen einzelner, einmaliger Käufe von Office oder Kaufen von Office über eine Volumenlizenz**</span><span class="sxs-lookup"><span data-stu-id="00cb5-141">**Option 2: Buy individual, one-time purchases of Office, or buy Office through a volume license**</span></span>

 - <span data-ttu-id="00cb5-142">Kaufen Sie einen einzelnen, einmaligen Kauf von Office.</span><span class="sxs-lookup"><span data-stu-id="00cb5-142">Buy an individual, one-time purchase of Office.</span></span> <span data-ttu-id="00cb5-143">Siehe [Office Home &amp; Business](https://www.microsoft.com/microsoft-365/buy/compare-all-microsoft-365-products-b) oder [Office Professional](https://www.microsoft.com/microsoft-365/p/office-professional-2019/CFQ7TTC0K7C5/)</span><span class="sxs-lookup"><span data-stu-id="00cb5-143">See [Office Home &amp; Business](https://www.microsoft.com/microsoft-365/buy/compare-all-microsoft-365-products-b) or [Office Professional](https://www.microsoft.com/microsoft-365/p/office-professional-2019/CFQ7TTC0K7C5/)</span></span>

     <span data-ttu-id="00cb5-144">ODER</span><span class="sxs-lookup"><span data-stu-id="00cb5-144">OR</span></span>

 - <span data-ttu-id="00cb5-145">Kaufen Sie mehrere Kopien von Office über eine Volumenlizenz.</span><span class="sxs-lookup"><span data-stu-id="00cb5-145">Buy multiple copies of Office through a volume license.</span></span> <span data-ttu-id="00cb5-146">Lesen Sie [Vergleich der Suites, die über die Volumenlizenzierung zur Verfügung stehen](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).</span><span class="sxs-lookup"><span data-stu-id="00cb5-146">See, [Compare suites available through volume licensing](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).</span></span>

## <a name="step-3---uninstall-office"></a><span data-ttu-id="00cb5-147">Schritt 3 - Deinstallieren von Office</span><span class="sxs-lookup"><span data-stu-id="00cb5-147">Step 3 - Uninstall Office</span></span>

<span data-ttu-id="00cb5-148">Vor der Installation der neuesten Version von Office wird empfohlen, alle älteren Versionen von Office zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="00cb5-148">Before installing the latest version of Office, we recommend you uninstall all older versions of Office.</span></span> <span data-ttu-id="00cb5-149">Wenn Sie sich jedoch für das Upgrade von Office entscheiden, beachten Sie die folgenden Fälle, in denen Sie Office nach der Deinstallation nicht neu installieren können.</span><span class="sxs-lookup"><span data-stu-id="00cb5-149">However, if you change your mind about upgrading Office, note the following instances where you won't be able to reinstall Office after uninstalling it.</span></span>
  
<span data-ttu-id="00cb5-150">Wenn Sie über Add-Ins von Drittanbietern verfügen, wenden Sie sich an den Hersteller, um festzustellen, ob ein Update vorhanden ist, das mit der neuesten Version von Office funktioniert.</span><span class="sxs-lookup"><span data-stu-id="00cb5-150">We recommend if you have third-party add-ins, contact the manufacturer to see if there's an update that will work with the latest version of Office.</span></span>

> [!TIP]
> <span data-ttu-id="00cb5-151">Wenn beim Deinstallieren von Office Probleme auftreten, können Sie mit dem Microsoft Support- und Wiederherstellungs-Assistent-Tool Office entfernen: [Microsoft Support- und Wiederherstellungs-Assistent herunterladen und ausführen.](https://go.microsoft.com/fwlink/?LinkID=2155008)</span><span class="sxs-lookup"><span data-stu-id="00cb5-151">If you run into issues while uninstalling Office, you can use the Microsoft Support and Recovery Assistant tool to help you remove Office: [Download and run the Microsoft Support and Recovery Assistant](https://go.microsoft.com/fwlink/?LinkID=2155008).</span></span>

### <a name="select-the-version-of-office-you-want-to-uninstall"></a><span data-ttu-id="00cb5-152">Wählen Sie die Office-Version aus, die Sie deinstallieren möchten:</span><span class="sxs-lookup"><span data-stu-id="00cb5-152">Select the version of Office you want to uninstall</span></span>

- [<span data-ttu-id="00cb5-153">Von einem PC</span><span class="sxs-lookup"><span data-stu-id="00cb5-153">From a PC</span></span>](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [<span data-ttu-id="00cb5-154">Von einem Mac</span><span class="sxs-lookup"><span data-stu-id="00cb5-154">From a Mac</span></span>](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a><span data-ttu-id="00cb5-155">Bekannte Probleme bei dem Versuch, ältere Office-Versionen nach einer Deinstallation erneut zu installieren</span><span class="sxs-lookup"><span data-stu-id="00cb5-155">Known issues trying to reinstall older versions of Office after an uninstall</span></span>

 <span data-ttu-id="00cb5-156">**Office über eine Volumenlizenz** Wenn Sie keinen Zugriff mehr auf die Quelldateien dieser Volumenlizenzversionen von Office haben, können Sie sie nicht erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="00cb5-156">**Office through a volume license** If you no longer have access to the source files of these volume license versions of Office, you won't be able to reinstall it.</span></span>

 <span data-ttu-id="00cb5-157">**Office auf Ihrem Computer vorinstalliert** Wenn Sie keinen Datenträger oder Product Key mehr haben (wenn Office mit einem datenträger oder Product Key enthalten ist), können Sie ihn nicht erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="00cb5-157">**Office pre-installed on your computer** If you no longer have a disc or product key (if Office came with one) you won't be able to reinstall it.</span></span>

 <span data-ttu-id="00cb5-158">**Nicht unterstützte Abonnements** Wenn Ihre Kopie von Office über nicht mehr gekündigte Abonnements wie Office 365 Small Business Premium oder Office 365 Mid-size Business abgerufen wurde, können Sie keine ältere Version von Office installieren, es sei denn, Sie verfügen über den Product Key, der in Ihrem Abonnement enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="00cb5-158">**Non-supported subscriptions** If your copy of Office was obtained through discontinued subscriptions, such as Office 365 Small Business Premium or Office 365 Mid-size Business, you won't be able to install an older version of Office unless you have the product key that came with your subscription.</span></span>

<span data-ttu-id="00cb5-p112">Wenn Sie die neueste Version von Office neben der älteren Version installieren möchten, können Sie unter [Installieren und Verwenden verschiedener Office-Versionen auf demselben PC](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf) eine Liste der Versionen abrufen, bei denen dies unterstützt wird. Eine Installation, bei der zwei Versionen nebeneinander installiert sind, ist möglicherweise die richtige Wahl, wenn Sie z. B. Add-Ins von Drittanbietern installiert haben, die Sie mit der älteren Office-Version verwenden, und Sie nicht sicher sind, ob sie mit der neuesten Version kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="00cb5-p112">If you'd prefer to install your older version of Office side-by-side with the latest version, you can see a list of versions where this is supported in, [Install and use different versions of Office on the same PC](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf). A side-by-side installation might be the right choice for you, if for example, you've installed third-party add-ins you're using with your older version of Office and you're not yet sure they're compatible with the latest version.</span></span>

## <a name="step-4---assign-office-licenses-to-users"></a><span data-ttu-id="00cb5-161">Schritt 4 - Zuweisen von Office-Lizenzen zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="00cb5-161">Step 4 - Assign Office licenses to users</span></span>

<span data-ttu-id="00cb5-162">Wenn Sie dies noch nicht getan haben, weisen Sie Allen Benutzern in Ihrer Organisation Lizenzen zu, die Office installieren müssen. Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern in Microsoft 365 for Business.](../manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="00cb5-162">If you haven't already done so, assign licenses to any users in your organization who need to install Office, see [Assign licenses to users in Microsoft 365 for business](../manage/assign-licenses-to-users.md).</span></span>
  
## <a name="step-5---install-office"></a><span data-ttu-id="00cb5-163">Schritt 5 - Installieren von Office</span><span class="sxs-lookup"><span data-stu-id="00cb5-163">Step 5 - Install Office</span></span>

<span data-ttu-id="00cb5-164">Nachdem Sie überprüft haben, dass alle Benutzer, die Sie aktualisieren möchten, Über Lizenzen verfügen, besteht der letzte Schritt darin, sie Office installieren zu lassen. Weitere Informationen finden Sie [unter Herunterladen und Installieren oder Erneutes Installieren Office auf Ihrem PC oder Mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="00cb5-164">After you've verified the users you want to upgrade all have licenses, the final step is to have them install Office, see [Download and install or reinstall Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span>
  
> [!TIP]
> <span data-ttu-id="00cb5-165">Wenn Sie nicht möchten, dass Ihre Benutzer Office selbst installieren, lesen Sie die [Informationen unter Verwalten von Softwaredownloadeinstellungen in Office 365](/DeployOffice/manage-software-download-settings-office-365).</span><span class="sxs-lookup"><span data-stu-id="00cb5-165">If you don't want your users installing Office themselves, see [Manage software download settings in Office 365](/DeployOffice/manage-software-download-settings-office-365).</span></span> <span data-ttu-id="00cb5-166">Sie können das [Office-Bereitstellungstool](/DeployOffice/overview-office-deployment-tool) verwenden, um die Office-Software in Ihr lokales Netzwerk herunterzuladen und dann Office mithilfe der in der Regel verwendeten Softwarebereitstellungsmethode bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="00cb5-166">You can use the [Office Deployment Tool](/DeployOffice/overview-office-deployment-tool) to download the Office software to your local network and then deploy Office by using the software deployment method you typically use.</span></span>