---
title: Azure-Integration in Microsoft 365
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
description: Integrieren Sie Microsoft 365 in Azure AD, wenn Sie eine Kennwortsynchronisierung oder einmaliges Anmelden in Ihre lokale Umgebung wünschen.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905332"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="7cf45-103">Azure-Integration in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7cf45-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="7cf45-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="7cf45-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7cf45-105">Microsoft 365 verwendet Azure Active Directory (Azure AD) zum Verwalten von Benutzeridentitäten hinter den Kulissen.</span><span class="sxs-lookup"><span data-stu-id="7cf45-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="7cf45-106">Ihr Microsoft 365-Abonnement umfasst ein kostenloses Azure AD-Abonnement, damit Sie Ihre lokalen Active Directory Domain Services (AD DS) integrieren können, um Benutzerkonten und Kennwörter zu synchronisieren oder einmaliges Anmelden einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="7cf45-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="7cf45-107">Sie können auch erweiterte Features erwerben, um Ihre Konten besser zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="7cf45-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="7cf45-108">Azure AD bietet auch andere Funktionen, z. B. die Verwaltung integrierter Apps, die Sie zum Erweitern und Anpassen Ihrer Microsoft 365-Abonnements verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7cf45-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="7cf45-109">Sie können die Azure AD-Bereitstellungsratgeber für eine geführte Einrichtung und Konfiguration im Microsoft 365 Admin Center verwenden (Sie müssen bei Microsoft 365 angemeldet sein):</span><span class="sxs-lookup"><span data-stu-id="7cf45-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="7cf45-110">Azure AD Connect-Ratgeber</span><span class="sxs-lookup"><span data-stu-id="7cf45-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="7cf45-111">Bereitstellungsratgeber für AD FS</span><span class="sxs-lookup"><span data-stu-id="7cf45-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="7cf45-112">Azure AD-Einrichtungshandbuch</span><span class="sxs-lookup"><span data-stu-id="7cf45-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="7cf45-113">Azure AD-Editionen und Microsoft 365-Identitätsverwaltung</span><span class="sxs-lookup"><span data-stu-id="7cf45-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="7cf45-114">Wenn Sie über ein kostenpflichtiges Abonnement für Microsoft 365 verfügen, haben Sie auch ein kostenloses Azure AD-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="7cf45-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="7cf45-115">Sie können Azure AD verwenden, um Benutzer- und Gruppenkonten zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="7cf45-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="7cf45-116">Um dieses Abonnement zu aktivieren, müssen Sie eine einmalregistrierung abschließen.</span><span class="sxs-lookup"><span data-stu-id="7cf45-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="7cf45-117">Anschließend können Sie über Ihr Microsoft 365 Admin Center auf Azure AD zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7cf45-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="7cf45-118">Anweisungen zur Registrierung Ihres kostenlosen Azure AD-Abonnements finden Sie [unter Verwenden Ihres kostenlosen Azure AD-Abonnements.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="7cf45-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="7cf45-119">Gehen Sie nicht direkt zu azure.microsoft.com, um sich zu registrieren, oder Sie erhalten ein Test- oder kostenpflichtiges Abonnement für Microsoft Azure, das von Ihrem kostenlosen Azure AD-Abonnement mit Microsoft 365 getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="7cf45-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="7cf45-120">Mit dem kostenlosen Abonnement können Sie mit lokalen Verzeichnissen synchronisieren, einmaliges Anmelden einrichten und mit vielen Software als Dienstanwendungen synchronisieren, z. B. Salesforce, DropBox und viele mehr.</span><span class="sxs-lookup"><span data-stu-id="7cf45-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="7cf45-121">Wenn Sie erweiterte AD DS-Funktionen, bidirektionale Synchronisierung und andere Verwaltungsfunktionen wünschen, können Sie Ihr kostenloses Abonnement auf ein kostenpflichtiges Premium-Abonnement aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7cf45-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="7cf45-122">Weitere Informationen finden Sie unter [Azure Active Directory Editions](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="7cf45-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="7cf45-123">Weitere Informationen zu Microsoft 365 und Azure AD finden Sie unter [Microsoft 365 Identity Models](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="7cf45-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="7cf45-124">Erweitern der Funktionen Ihres Microsoft 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="7cf45-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="7cf45-125">**Feature**</span><span class="sxs-lookup"><span data-stu-id="7cf45-125">**Feature**</span></span>|<span data-ttu-id="7cf45-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7cf45-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7cf45-127">Integrierte Apps</span><span class="sxs-lookup"><span data-stu-id="7cf45-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="7cf45-128">Sie können einzelnen Apps Zugriff auf Ihre Microsoft 365-Daten gewähren, z. B. E-Mails, Kalender, Kontakte, Benutzer, Gruppen, Dateien und Ordner.</span><span class="sxs-lookup"><span data-stu-id="7cf45-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="7cf45-129">Sie können diese Apps auch auf globaler Administratorebene autorisieren und für Ihr gesamtes Unternehmen verfügbar machen, indem Sie die Apps in Azure AD registrieren.</span><span class="sxs-lookup"><span data-stu-id="7cf45-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="7cf45-130">Weitere Informationen finden Sie unter [Integrierte Apps und Azure AD für Microsoft 365-Administratoren.](integrated-apps-and-azure-ads.md)</span><span class="sxs-lookup"><span data-stu-id="7cf45-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="7cf45-131">Weitere Informationen finden [Sie unter Einmaliges Anmelden](/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="7cf45-131">Also see [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>  <br/> |
|<span data-ttu-id="7cf45-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="7cf45-132">PowerApps</span></span>  <br/> | <span data-ttu-id="7cf45-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span><span class="sxs-lookup"><span data-stu-id="7cf45-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="7cf45-134">Weitere Informationen finden Sie unter Erstellen einer [PowerApp für eine Liste in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) und auf der [PowerApps-Seite.](https://powerapps.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7cf45-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7cf45-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cf45-135">See also</span></span>

[<span data-ttu-id="7cf45-136">Übersicht zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7cf45-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)