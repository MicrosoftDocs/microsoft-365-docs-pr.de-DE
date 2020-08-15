---
title: Azure-Integration mit Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
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
ms.openlocfilehash: 045760f000abdbf053e09d89b296fbafa4c24786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690836"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="4dc65-103">Azure-Integration mit Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4dc65-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="4dc65-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4dc65-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4dc65-105">Microsoft 365 verwendet Azure Active Directory (Azure AD), um Benutzeridentitäten hinter den Kulissen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="4dc65-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="4dc65-106">Ihr Microsoft 365-Abonnement enthält ein kostenloses Abonnement für Azure AD, damit Sie Microsoft 365 mit Azure AD integrieren können, wenn Sie Kennwörter synchronisieren oder einmaliges Anmelden mit Ihrer lokalen Umgebung einrichten möchten.</span><span class="sxs-lookup"><span data-stu-id="4dc65-106">Your Microsoft 365 subscription includes a free subscription to Azure AD so that you can integrate Microsoft 365 with Azure AD if you want to sync passwords or set up single sign-on with your on-premises environment.</span></span> <span data-ttu-id="4dc65-107">Sie können auch erweiterte Funktionen erwerben, um Ihre Konten besser zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="4dc65-107">You can also buy advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="4dc65-108">Azure bietet auch andere Funktionen wie das Verwalten integrierter apps, mit denen Sie Ihre Microsoft 365-Abonnements erweitern und anpassen können.</span><span class="sxs-lookup"><span data-stu-id="4dc65-108">Azure also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="4dc65-109">Sie können die Azure AD-Bereitstellungs Ratgeber für eine gesteuerte Setup-und Konfigurationsumgebung verwenden (Sie müssen bei Microsoft 365 angemeldet sein):</span><span class="sxs-lookup"><span data-stu-id="4dc65-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="4dc65-110">Azure AD Connect-Ratgeber</span><span class="sxs-lookup"><span data-stu-id="4dc65-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="4dc65-111">Bereitstellungsratgeber für AD FS</span><span class="sxs-lookup"><span data-stu-id="4dc65-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="4dc65-112">Azure AD-Installationshandbuch</span><span class="sxs-lookup"><span data-stu-id="4dc65-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="4dc65-113">Azure AD Editionen und Microsoft 365 Identity Management</span><span class="sxs-lookup"><span data-stu-id="4dc65-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="4dc65-114">Wenn Sie ein kostenpflichtiges Abonnement für Microsoft 365 haben, haben Sie auch ein kostenloses Abonnement für Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4dc65-114">If you have a paid subscription to Microsoft 365, you also have a free subscription to Azure AD.</span></span> <span data-ttu-id="4dc65-115">Sie können Azure AD verwenden, um Benutzer-und Gruppenkonten zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="4dc65-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="4dc65-116">Um dieses Abonnement zu aktivieren, müssen Sie eine einmalige Registrierung durchführen.</span><span class="sxs-lookup"><span data-stu-id="4dc65-116">To activate this subscription you have to complete a one-time registration.</span></span> <span data-ttu-id="4dc65-117">Anschließend können Sie über Ihr Microsoft 365 Admin Center auf Azure AD zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4dc65-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="4dc65-118">Anweisungen finden Sie unter [Verwenden Ihres kostenlosen Azure AD-Abonnements](https://go.microsoft.com/fwlink/p/?LinkId=617127).</span><span class="sxs-lookup"><span data-stu-id="4dc65-118">For instructions, see [use your free Azure AD subscription](https://go.microsoft.com/fwlink/p/?LinkId=617127).</span></span> <span data-ttu-id="4dc65-119">Befolgen Sie die Anweisungen, um das ﻿kostenlose Azure AD-Abonnement zu registrieren, das mit Ihrem Abonnement für Microsoft 365 geliefert wird.</span><span class="sxs-lookup"><span data-stu-id="4dc65-119">Follow the instructions to register the free Azure AD subscription that comes with your subscription to Microsoft 365.</span></span> <span data-ttu-id="4dc65-120">Gehen Sie nicht direkt zu Azure.Microsoft.com, um sich anzumelden, oder Sie erhalten ein Test-oder kostenpflichtiges Abonnement für Microsoft Azure, das von Ihrer kostenlosen Version für Microsoft 365 getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="4dc65-120">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free one for Microsoft 365.</span></span> 
  
<span data-ttu-id="4dc65-121">Mit dem kostenlosen Abonnement können Sie mit lokalen Verzeichnissen synchronisieren, einmaliges Anmelden einrichten und mit vielen Software als Dienstanwendungen wie Salesforce, Dropbox und vieles mehr synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="4dc65-121">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox and many more.</span></span>
  
<span data-ttu-id="4dc65-122">Wenn Sie erweiterte Active Directory-Domänendienste (AD DS) Funktionalität, bidirektionale Synchronisierung und andere Verwaltungsfunktionen wünschen, können Sie Ihr kostenloses Abonnement auf ein kostenpflichtiges Premium-Abonnement upgraden.</span><span class="sxs-lookup"><span data-stu-id="4dc65-122">If you want enhanced Active Directory Domain Services (AD DS) functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="4dc65-123">Ausführliche Informationen finden Sie unter [Azure Active Directory Editions](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="4dc65-123">For details see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="4dc65-124">Weitere Informationen zu Microsoft 365 und Azure AD finden Sie unter [Understanding Microsoft 365 Identity and Azure Active Directory](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="4dc65-124">For more information about Microsoft 365 and Azure AD, see [Understanding Microsoft 365 Identity and Azure Active Directory](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="4dc65-125">Erweitern der Funktionen Ihres Microsoft 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="4dc65-125">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="4dc65-126">**Feature**</span><span class="sxs-lookup"><span data-stu-id="4dc65-126">**Feature**</span></span>|<span data-ttu-id="4dc65-127">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4dc65-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4dc65-128">Integrierte apps</span><span class="sxs-lookup"><span data-stu-id="4dc65-128">Integrated apps</span></span>  <br/> |<span data-ttu-id="4dc65-129">Sie können einzelnen apps Zugriff auf Ihre Microsoft 365-Daten wie e-Mail, Kalender, Kontakte, Benutzer, Gruppen, Dateien und Ordner gewähren.</span><span class="sxs-lookup"><span data-stu-id="4dc65-129">You can grant individual apps access to your Microsoft 365 data, like mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="4dc65-130">Sie können diese apps auch auf globaler Administratorebene autorisieren und Sie für Ihr gesamtes Unternehmen zur Verfügung stellen, indem Sie die apps in Azure AD registrieren.</span><span class="sxs-lookup"><span data-stu-id="4dc65-130">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="4dc65-131">Ausführliche Informationen finden Sie unter [integrierte apps und Azure AD für Microsoft 365-Administratoren](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).</span><span class="sxs-lookup"><span data-stu-id="4dc65-131">For details see [Integrated Apps and Azure AD for Microsoft 365 administrators](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).</span></span>  <br/> <span data-ttu-id="4dc65-132">Siehe auch [einmaliges Anmelden bei Anwendungen](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="4dc65-132">Also see [single sign-on to applications](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="4dc65-133">PowerApps</span><span class="sxs-lookup"><span data-stu-id="4dc65-133">PowerApps</span></span>  <br/> | <span data-ttu-id="4dc65-134">Power apps sind fokussierte Apps für mobile Geräte, die mit Ihren vorhandenen Datenquellen wie SharePoint-Listen und anderen Daten-apps verbunden werden können.</span><span class="sxs-lookup"><span data-stu-id="4dc65-134">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists, and other data apps.</span></span> <span data-ttu-id="4dc65-135">Weitere Informationen finden Sie unter [Erstellen eines PowerApp für eine Liste auf SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) -und [PowerApps-Seite](https://powerapps.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="4dc65-135">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
<span data-ttu-id="4dc65-136">Weitere Informationen finden Sie unter [integrierte apps und Azure AD für Microsoft 365-Administratoren](integrated-apps-and-azure-ads.md) und [Azure AD Anwendungskatalog und einmaliges Anmelden](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="4dc65-136">Learn more at [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md) and [Azure AD application gallery and single-sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="see-also"></a><span data-ttu-id="4dc65-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4dc65-137">See also</span></span>

[<span data-ttu-id="4dc65-138">Übersicht zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4dc65-138">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
