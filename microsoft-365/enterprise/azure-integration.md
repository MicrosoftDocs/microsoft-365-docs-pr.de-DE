---
title: Azure-Integration mit Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Integrieren Sie Microsoft 365 mit Azure AD, wenn Sie die Kennwortsynchronisierung oder das einmalige Anmelden mit Ihrer lokalen Umgebung wünschen.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384749"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="11264-103">Azure-Integration mit Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="11264-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="11264-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="11264-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="11264-105">Microsoft 365 verwendet Azure Active Directory (Azure AD), um Benutzeridentitäten hinter den Kulissen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="11264-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="11264-106">Ihr Microsoft 365-Abonnement enthält ein kostenloses Azure AD-Abonnement, damit Sie Ihre lokalen Active Directory-Domänendienste (AD DS) integrieren können, um Benutzerkonten und Kennwörter zu synchronisieren oder einmaliges Anmelden einzurichten.</span><span class="sxs-lookup"><span data-stu-id="11264-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="11264-107">Sie können auch erweiterte Funktionen erwerben, um Ihre Konten besser zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="11264-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="11264-108">Azure Ad bietet auch andere Funktionen wie das Verwalten integrierter apps, mit denen Sie Ihre Microsoft 365-Abonnements erweitern und anpassen können.</span><span class="sxs-lookup"><span data-stu-id="11264-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="11264-109">Sie können die Azure AD-Bereitstellungs Ratgeber für eine gesteuerte Setup-und Konfigurationsumgebung im Microsoft 365 Admin Center verwenden (Sie müssen bei Microsoft 365 angemeldet sein):</span><span class="sxs-lookup"><span data-stu-id="11264-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="11264-110">Azure AD Connect-Ratgeber</span><span class="sxs-lookup"><span data-stu-id="11264-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="11264-111">Bereitstellungsratgeber für AD FS</span><span class="sxs-lookup"><span data-stu-id="11264-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="11264-112">Azure AD-Installationshandbuch</span><span class="sxs-lookup"><span data-stu-id="11264-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="11264-113">Azure AD Editionen und Microsoft 365 Identity Management</span><span class="sxs-lookup"><span data-stu-id="11264-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="11264-114">Wenn Sie ein kostenpflichtiges Abonnement für Microsoft 365 haben, haben Sie auch ein kostenloses Azure AD-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="11264-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="11264-115">Sie können Azure AD verwenden, um Benutzer-und Gruppenkonten zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="11264-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="11264-116">Wenn Sie dieses Abonnement aktivieren möchten, müssen Sie eine einmalige Registrierung durchführen.</span><span class="sxs-lookup"><span data-stu-id="11264-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="11264-117">Anschließend können Sie über Ihr Microsoft 365 Admin Center auf Azure AD zugreifen.</span><span class="sxs-lookup"><span data-stu-id="11264-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="11264-118">Anweisungen zum Registrieren Ihres kostenlosen Azure AD-Abonnements finden Sie unter [Verwenden Ihres kostenlosen Azure AD-Abonnements](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="11264-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="11264-119">Gehen Sie nicht direkt zu Azure.Microsoft.com, um sich anzumelden, oder Sie erhalten ein Test-oder kostenpflichtiges Abonnement für Microsoft Azure, das von Ihrem kostenlosen Azure AD-Abonnement mit Microsoft 365 getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="11264-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="11264-120">Mit dem kostenlosen Abonnement können Sie mit lokalen Verzeichnissen synchronisieren, einmaliges Anmelden einrichten und mit vielen Software als Dienstanwendungen wie Salesforce, Dropbox und vielem mehr synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="11264-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="11264-121">Wenn Sie Erweiterte AD DS Funktionalität, bidirektionale Synchronisierung und andere Verwaltungsfunktionen wünschen, können Sie Ihr kostenloses Abonnement auf ein kostenpflichtiges Premium-Abonnement upgraden.</span><span class="sxs-lookup"><span data-stu-id="11264-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="11264-122">Ausführliche Informationen finden Sie unter [Azure Active Directory Editions](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="11264-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="11264-123">Weitere Informationen zu Microsoft 365 und Azure AD finden Sie unter [Microsoft 365 Identity Models](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="11264-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="11264-124">Erweitern der Funktionen Ihres Microsoft 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="11264-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="11264-125">**Feature**</span><span class="sxs-lookup"><span data-stu-id="11264-125">**Feature**</span></span>|<span data-ttu-id="11264-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="11264-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="11264-127">Integrierte apps</span><span class="sxs-lookup"><span data-stu-id="11264-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="11264-128">Sie können einzelnen apps Zugriff auf Ihre Microsoft 365-Daten gewähren, beispielsweise e-Mails, Kalender, Kontakte, Benutzer, Gruppen, Dateien und Ordner.</span><span class="sxs-lookup"><span data-stu-id="11264-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="11264-129">Sie können diese apps auch auf globaler Administratorebene autorisieren und Sie für Ihr gesamtes Unternehmen zur Verfügung stellen, indem Sie die apps in Azure AD registrieren.</span><span class="sxs-lookup"><span data-stu-id="11264-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="11264-130">Informationen zu Leistungsange finden Sie unter [Integrated apps and Azure ad for Microsoft 365 Administrators](integrated-apps-and-azure-ads.md).</span><span class="sxs-lookup"><span data-stu-id="11264-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="11264-131">Siehe auch [Single Sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="11264-131">Also see [Single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="11264-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="11264-132">PowerApps</span></span>  <br/> | <span data-ttu-id="11264-133">Power apps sind fokussierte Apps für mobile Geräte, die mit Ihren vorhandenen Datenquellen wie SharePoint-Listen und anderen Daten-apps verbunden werden können.</span><span class="sxs-lookup"><span data-stu-id="11264-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="11264-134">Weitere Informationen finden Sie unter [Erstellen eines PowerApp für eine Liste in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) und auf der [PowerApps-Seite](https://powerapps.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="11264-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="11264-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11264-135">See also</span></span>

[<span data-ttu-id="11264-136">Übersicht zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="11264-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
