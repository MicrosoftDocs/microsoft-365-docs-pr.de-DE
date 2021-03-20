---
title: Minderjährige und Erwerben von Add-Ins aus dem Store
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Erfahren Sie mehr über die Datenschutz-Grundverordnung (DSGVO), die die personenbezogenen Daten von Minderjährigen regeln.
ms.openlocfilehash: c49ea719bc85166cc8082200eb833273b0ab5835
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915254"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="59836-103">Minderjährige und Erwerben von Add-Ins aus dem Store</span><span class="sxs-lookup"><span data-stu-id="59836-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="59836-104">Die Datenschutz-Grundverordnung (DSGVO) ist eine Verordnung der Europäischen Union, die am 25. Mai 2018 wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="59836-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="59836-105">Es gibt Benutzern Rechte an und Schutz ihrer Daten.</span><span class="sxs-lookup"><span data-stu-id="59836-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="59836-106">Einer der Aspekte der DSGVO ist, dass Minderjährige ihre personenbezogenen Daten nicht an Parteien übermitteln lassen können, die von ihren Eltern oder Erziehungsberechtigten nicht genehmigt wurden.</span><span class="sxs-lookup"><span data-stu-id="59836-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="59836-107">Das spezifische Alter, das als Nebenperson definiert ist, hängt von der Region ab, in der sich die Person befindet.</span><span class="sxs-lookup"><span data-stu-id="59836-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="59836-108">Zu den Regionen mit gesetzlichen Bestimmungen über die Zustimmung der Eltern gehören die USA, Südkorea, Großbritannien und die Europäische Union.</span><span class="sxs-lookup"><span data-stu-id="59836-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="59836-109">Für diese Regionen wird ein Minderjähriger (über Azure Active Directory) daran blockiert, neue Office-Add-Ins aus dem Store zu erhalten und zuvor erworbene Add-Ins ausführen.</span><span class="sxs-lookup"><span data-stu-id="59836-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="59836-110">Für Länder ohne gesetzliche Bestimmungen gibt es keine Downloadeinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="59836-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="59836-111">Ein Benutzer wird basierend auf den in Azure Active Directory angegebenen Daten als Nebenbenutzer bestimmt.</span><span class="sxs-lookup"><span data-stu-id="59836-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="59836-112">Der Organisationsadministrator ist für die Deklarieren der gesetzlichen Altersgruppe und der elterlichen Zustimmung für den Benutzer verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="59836-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="59836-113">Wenn das Übergeordnete/Erziehungsberechtigte einer Minderjährigen mithilfe eines bestimmten Add-Ins zuwilligt, kann der Organisationsadministrator die zentrale Bereitstellung verwenden, um dieses Add-In für alle Minderjährigen mit Zustimmung zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="59836-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="59836-114">Damit die DSGVO für Minderjährige kompatibel ist, müssen Sie sicherstellen, dass eine der folgenden Builds von Office in Ihrer Schule/Organisation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="59836-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="59836-115">**Für Word, Excel, PowerPoint und Project**:</span><span class="sxs-lookup"><span data-stu-id="59836-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="59836-116">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="59836-116">**Platform**</span></span> <br/> |<span data-ttu-id="59836-117">**Buildnummer**</span><span class="sxs-lookup"><span data-stu-id="59836-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="59836-118">Microsoft 365 Apps for Enterprise (Aktueller Kanal)</span><span class="sxs-lookup"><span data-stu-id="59836-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="59836-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="59836-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="59836-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span><span class="sxs-lookup"><span data-stu-id="59836-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="59836-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="59836-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="59836-122">Office 2016 für Windows</span><span class="sxs-lookup"><span data-stu-id="59836-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="59836-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="59836-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="59836-124">Office 2013 für Windows</span><span class="sxs-lookup"><span data-stu-id="59836-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="59836-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="59836-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="59836-126">Office 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="59836-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="59836-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="59836-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="59836-128">Office für das Web</span><span class="sxs-lookup"><span data-stu-id="59836-128">Office for the web</span></span>  <br/> |<span data-ttu-id="59836-129">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="59836-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="59836-130">**Für Outlook**:</span><span class="sxs-lookup"><span data-stu-id="59836-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="59836-131">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="59836-131">**Platform**</span></span> <br/> |<span data-ttu-id="59836-132">**Buildnummer**</span><span class="sxs-lookup"><span data-stu-id="59836-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="59836-133">Outlook 2016 für Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="59836-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="59836-134">Build No TBD</span><span class="sxs-lookup"><span data-stu-id="59836-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="59836-135">Outlook 2016 für Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="59836-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="59836-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="59836-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="59836-137">Office 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="59836-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="59836-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="59836-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="59836-139">Outlook mobile für iOS</span><span class="sxs-lookup"><span data-stu-id="59836-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="59836-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="59836-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="59836-141">Outlook mobile für Android</span><span class="sxs-lookup"><span data-stu-id="59836-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="59836-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="59836-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="59836-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="59836-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="59836-144">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="59836-144">N/A</span></span>  <br/> |

 <span data-ttu-id="59836-145">**Office 2013-Anforderungen**</span><span class="sxs-lookup"><span data-stu-id="59836-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="59836-146">Word, Excel und PowerPoint 2013 für Windows unterstützen dieselben Nebenprüfungen, ob die Active Directory Authentication Library (ADAL) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="59836-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="59836-147">Es gibt zwei Optionen für die Compliance, wie im nächsten Schritt erläutert.</span><span class="sxs-lookup"><span data-stu-id="59836-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="59836-148">**Aktivieren Sie ADAL**.</span><span class="sxs-lookup"><span data-stu-id="59836-148">**Enable ADAL**.</span></span> <span data-ttu-id="59836-149">In diesem Artikel wird erläutert, wie Sie ADAL für Office 2013 aktivieren: Verwenden der [modernen Microsoft 365-Authentifizierung mit Office-Clients.](../../enterprise/modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="59836-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span><br/><span data-ttu-id="59836-150">Sie müssen auch die Registrierungsschlüssel festlegen, um ADAL zu aktivieren, wie unter [Enable Modern Authentication for Office 2013 on Windows devices erläutert.](../security-and-compliance/enable-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="59836-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="59836-151">Darüber hinaus müssen Sie die folgenden Aprilupdates für Office 2013 installieren:</span><span class="sxs-lookup"><span data-stu-id="59836-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="59836-152">Beschreibung des Sicherheitsupdates für Office 2013: 10. April 2018</span><span class="sxs-lookup"><span data-stu-id="59836-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="59836-153">Update vom 3. April 2018 für Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="59836-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="59836-154">**Aktivieren Sie ADAL nicht.**</span><span class="sxs-lookup"><span data-stu-id="59836-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="59836-155">Wenn Sie ADAL in Office 2013 nicht aktivieren können, empfehlen wir, den Store für die Office-Clients mithilfe von Gruppenrichtlinien zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="59836-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="59836-156">Informationen zum Deaktivieren der App für Office-Einstellungen finden Sie [hier.](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="59836-156">Information on how to turn off the app for Office settings is located [here](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).</span></span>

## <a name="related-articles"></a><span data-ttu-id="59836-157">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="59836-157">Related articles</span></span>

[<span data-ttu-id="59836-158">Bereitstellen von Add-Ins im Admin Center</span><span class="sxs-lookup"><span data-stu-id="59836-158">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

[<span data-ttu-id="59836-159">Verwalten von Add-Ins im Admin Center</span><span class="sxs-lookup"><span data-stu-id="59836-159">Manage add-ins in the admin center</span></span>](./manage-addins-in-the-admin-center.md)
