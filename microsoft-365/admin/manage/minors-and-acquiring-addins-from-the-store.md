---
title: Minderjährige und Erwerb von Add-Ins aus dem Store
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
description: Erfahren Sie mehr über die allgemeinen Datenschutzverordnung (dsgvo)-Verordnungen, die die personenbezogenen Daten von Minderjährigen Regeln.
ms.openlocfilehash: dcf2c98906830e0007747e2dd90e67b9dc85a5bb
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103104"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="30325-103">Minderjährige und Erwerb von Add-Ins aus dem Store</span><span class="sxs-lookup"><span data-stu-id="30325-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="30325-104">Die allgemeine Datenschutzverordnung (dsgvo) ist eine Verordnung der Europäischen Union, die am 25. Mai 2018 wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="30325-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="30325-105">Es gibt Benutzern Rechte und Schutz Ihrer Daten.</span><span class="sxs-lookup"><span data-stu-id="30325-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="30325-106">Einer der Aspekte des dsgvo ist, dass Minderjährige Ihre persönlichen Daten nicht an Parteien senden dürfen, die ihre Eltern oder Erziehungsberechtigten nicht genehmigt haben.</span><span class="sxs-lookup"><span data-stu-id="30325-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="30325-107">Das spezifische Alter, das als Minderjährige definiert ist, hängt von der Region ab, in der sich die Person befindet.</span><span class="sxs-lookup"><span data-stu-id="30325-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="30325-108">Regionen mit gesetzlichen Bestimmungen zur elterlichen Zustimmung sind die Vereinigten Staaten, Südkorea, das Vereinigte Königreich und die Europäische Union.</span><span class="sxs-lookup"><span data-stu-id="30325-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="30325-109">Für diese Regionen wird ein Minderjähriger (über Azure Active Directory) daran gehindert, neue Office-Add-Ins aus dem Store abzurufen und Add-Ins auszuführen, die zuvor erworben wurden.</span><span class="sxs-lookup"><span data-stu-id="30325-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="30325-110">Für Länder ohne gesetzliche Bestimmungen gibt es keine Downloadbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="30325-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="30325-111">Ein Benutzer wird basierend auf den in Azure Active Directory angegebenen Daten als Minderjähriger festgelegt.</span><span class="sxs-lookup"><span data-stu-id="30325-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="30325-112">Der Organisationsadministrator ist für die Deklaration der legalen Altersgruppe und der elterlichen Zustimmung für diesen Benutzer verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="30325-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="30325-113">Wenn der übergeordnete/Erziehungsberechtigte einem Minderjährigen unter Verwendung eines bestimmten Add-ins zustimmt, kann der Organisationsadministrator die zentralisierte Bereitstellung verwenden, um das Add-in für alle Minderjährigen bereitzustellen, die Zustimmung haben.</span><span class="sxs-lookup"><span data-stu-id="30325-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="30325-114">Um dsgvo-konform für Minderjährige zu sein, müssen Sie sicherstellen, dass eine der folgenden Builds von Office in ihrer Schule/Organisation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="30325-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="30325-115">**Für Word, Excel, PowerPoint und Project**:</span><span class="sxs-lookup"><span data-stu-id="30325-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="30325-116">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="30325-116">**Platform**</span></span> <br/> |<span data-ttu-id="30325-117">**Buildnummer**</span><span class="sxs-lookup"><span data-stu-id="30325-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="30325-118">Microsoft 365 apps for Enterprise (aktueller Kanal)</span><span class="sxs-lookup"><span data-stu-id="30325-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="30325-119">9001,2138</span><span class="sxs-lookup"><span data-stu-id="30325-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="30325-120">Microsoft 365-Apps für Unternehmen (halbjährlicher Enterprise-Kanal)</span><span class="sxs-lookup"><span data-stu-id="30325-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="30325-121">8431,2159</span><span class="sxs-lookup"><span data-stu-id="30325-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="30325-122">Office 2016 für Windows</span><span class="sxs-lookup"><span data-stu-id="30325-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="30325-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="30325-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="30325-124">Office 2013 für Windows</span><span class="sxs-lookup"><span data-stu-id="30325-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="30325-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="30325-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="30325-126">Office 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="30325-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="30325-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="30325-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="30325-128">Office für das Web</span><span class="sxs-lookup"><span data-stu-id="30325-128">Office for the web</span></span>  <br/> |<span data-ttu-id="30325-129">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="30325-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="30325-130">**Für Outlook**:</span><span class="sxs-lookup"><span data-stu-id="30325-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="30325-131">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="30325-131">**Platform**</span></span> <br/> |<span data-ttu-id="30325-132">**Buildnummer**</span><span class="sxs-lookup"><span data-stu-id="30325-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="30325-133">Outlook 2016 für Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="30325-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="30325-134">Build kein feststellen</span><span class="sxs-lookup"><span data-stu-id="30325-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="30325-135">Outlook 2016 für Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="30325-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="30325-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="30325-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="30325-137">Office 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="30325-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="30325-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="30325-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="30325-139">Outlook Mobile für IOS</span><span class="sxs-lookup"><span data-stu-id="30325-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="30325-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="30325-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="30325-141">Outlook Mobile für Android</span><span class="sxs-lookup"><span data-stu-id="30325-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="30325-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="30325-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="30325-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="30325-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="30325-144">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="30325-144">N/A</span></span>  <br/> |

 <span data-ttu-id="30325-145">**Office 2013 Anforderungen**</span><span class="sxs-lookup"><span data-stu-id="30325-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="30325-146">Word-, Excel-und PowerPoint 2013 für Windows unterstützt die gleichen Minderjährigen überprüft, ob Active Directory Authentifizierungsbibliothek (Adal) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="30325-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="30325-147">Es gibt zwei Optionen für die Compliance, wie weiter erläutert.</span><span class="sxs-lookup"><span data-stu-id="30325-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="30325-148">**Aktivieren Sie Adal**.</span><span class="sxs-lookup"><span data-stu-id="30325-148">**Enable ADAL**.</span></span> <span data-ttu-id="30325-149">In diesem Artikel wird erläutert, wie Sie Adal für Office 2013 aktivieren: [Verwenden der modernen Authentifizierung von Microsoft 365 mit Office-Clients](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span><span class="sxs-lookup"><span data-stu-id="30325-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="30325-150">Sie müssen auch die Registrierungsschlüssel festlegen, um Adal zu aktivieren, wie unter [Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten](../security-and-compliance/enable-modern-authentication.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="30325-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="30325-151">Darüber hinaus müssen Sie die folgenden April-Updates für Office 2013 installieren:</span><span class="sxs-lookup"><span data-stu-id="30325-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="30325-152">Beschreibung des Sicherheitsupdates für Office 2013:10. April 2018</span><span class="sxs-lookup"><span data-stu-id="30325-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="30325-153">3. April 2018, Update für Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="30325-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="30325-154">**Aktivieren Sie Adal nicht**.</span><span class="sxs-lookup"><span data-stu-id="30325-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="30325-155">Wenn Sie Adal nicht in Office 2013 aktivieren können, empfehlen wir die Verwendung von Gruppenrichtlinien zum Deaktivieren des Speichers für die Office-Clients.</span><span class="sxs-lookup"><span data-stu-id="30325-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="30325-156">Informationen zum Deaktivieren der Einstellungen für die APP für Office finden Sie [hier](https://technet.microsoft.com/library/cc178992.aspx).</span><span class="sxs-lookup"><span data-stu-id="30325-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="30325-157">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="30325-157">Related articles</span></span>

[<span data-ttu-id="30325-158">Bereitstellen von Add-Ins im Admin Center</span><span class="sxs-lookup"><span data-stu-id="30325-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="30325-159">Verwalten von Add-Ins im Admin Center</span><span class="sxs-lookup"><span data-stu-id="30325-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
