---
title: Anforderungen für Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Rufen Sie für verwaltete Dienstanbieter (Managed Service Providers, MSPs) eine Liste der Anforderungen für die Verwendung von Microsoft 365 Lighthouse ab.
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395188"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a><span data-ttu-id="6b78f-103">Anforderungen für Microsoft 365 Lighthouse</span><span class="sxs-lookup"><span data-stu-id="6b78f-103">Requirements for Microsoft 365 Lighthouse</span></span>

> [!NOTE]
> <span data-ttu-id="6b78f-104">Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nur für Partner verfügbar, die die in diesem Artikel aufgeführten Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="6b78f-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the requirements listed in this article.</span></span> <span data-ttu-id="6b78f-105">Wenn Ihre Organisation nicht über Microsoft 365 Lighthouse verfügt, lesen Sie ["Registrieren für Microsoft 365 Lighthouse".](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="6b78f-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="6b78f-106">Microsoft 365 Lighthouse ist ein Verwaltungsportal, das Managed Service Providers (MSPs) dabei unterstützt, Geräte, Daten und Benutzer für SMB-Kunden (Small- und Medium-Business) im großen Maßstab zu sichern und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="6b78f-106">Microsoft 365 Lighthouse is an admin portal that helps Managed Service Providers (MSPs) secure and manage devices, data, and users at scale for small- and medium-sized business (SMB) customers.</span></span>  

<span data-ttu-id="6b78f-107">MSPs müssen für das programm Cloud Solution Provider (CSP) als indirekter Händler oder Partner für direkte Rechnungen registriert sein, um Microsoft 365 Lighthouse verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="6b78f-107">MSPs must be enrolled in the Cloud Solution Provider (CSP) program as an Indirect Reseller or Direct Bill partner to use Microsoft 365 Lighthouse.</span></span>  

<span data-ttu-id="6b78f-108">Darüber hinaus muss sich jeder MSP-Kundenmandant für Microsoft 365 Lighthouse qualifizieren, indem er die folgenden Anforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="6b78f-108">In addition, each MSP customer tenant must qualify for Microsoft 365 Lighthouse by meeting the following requirements:</span></span> 
 
- <span data-ttu-id="6b78f-109">Delegierte Administratorrechte (Delegated Admin Privileges, DAP) für den MSP</span><span class="sxs-lookup"><span data-stu-id="6b78f-109">Delegated Admin Privileges (DAP) for the MSP</span></span> 
- <span data-ttu-id="6b78f-110">Mindestens eine Microsoft 365 Business Premium-Lizenz</span><span class="sxs-lookup"><span data-stu-id="6b78f-110">At least one Microsoft 365 Business Premium license</span></span> 
- <span data-ttu-id="6b78f-111">Weniger als 500 lizenzierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="6b78f-111">Fewer than 500 licensed users</span></span>  

## <a name="requirements-for-enablingdevice-management"></a><span data-ttu-id="6b78f-112">Anforderungen für die Aktivierung der Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="6b78f-112">Requirements for enabling device management</span></span>   

<span data-ttu-id="6b78f-113">Um Kundenmandantengeräte auf den Geräteverwaltungsseiten anzuzeigen, muss ein MSP Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="6b78f-113">To view customer tenant devices on the device management pages, a MSP must:</span></span>    

- <span data-ttu-id="6b78f-114">Registrieren Sie alle Kundengeräte in Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="6b78f-114">Enroll all customer devices in Microsoft Endpoint Manager (MEM).</span></span><span data-ttu-id="6b78f-115">Weitere Informationen finden Sie unter [Registrieren von Geräten in Microsoft Intune.](/mem/intune/enrollment/)</span><span class="sxs-lookup"><span data-stu-id="6b78f-115"> For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>
- <span data-ttu-id="6b78f-116">Weisen Sie allen Kundengeräten Compliancerichtlinien zu.</span><span class="sxs-lookup"><span data-stu-id="6b78f-116">Assign compliance policies to all customer devices.</span></span><span data-ttu-id="6b78f-117">Weitere Informationen finden Sie unter [Erstellen einer Compliancerichtlinie in Microsoft Intune.](/mem/intune/protect/create-compliance-policy)</span><span class="sxs-lookup"><span data-stu-id="6b78f-117"> For more information, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span> 

## <a name="requirements-for-enabling-usermanagement"></a><span data-ttu-id="6b78f-118">Anforderungen für die Aktivierung der Benutzerverwaltung</span><span class="sxs-lookup"><span data-stu-id="6b78f-118">Requirements for enabling user management</span></span> 

<span data-ttu-id="6b78f-119">Damit Kundendaten in Berichten auf Benutzerverwaltungsseiten angezeigt werden können, einschließlich riskanter Benutzer, mehrstufiger Authentifizierung und Kennwortzurücksetzung, müssen Kundenmandanten Über Lizenzen für Azure Active Directory Premium P1 oder höher verfügen.</span><span class="sxs-lookup"><span data-stu-id="6b78f-119">For customer data to show up in reports on user management pages, including Risky users, Multifactor authentication, and Password reset, customer tenants must have licenses for Azure Active Directory Premium P1 or later.</span></span> <span data-ttu-id="6b78f-120">Azure AD Premium P1 ist in Microsoft 365 Business Premium enthalten.</span><span class="sxs-lookup"><span data-stu-id="6b78f-120">Azure AD Premium P1 is included with Microsoft 365 Business Premium.</span></span>   

## <a name="requirements-for-enablingthreat-management"></a><span data-ttu-id="6b78f-121">Anforderungen für die Aktivierung des Bedrohungsmanagements</span><span class="sxs-lookup"><span data-stu-id="6b78f-121">Requirements for enabling threat management</span></span> 

<span data-ttu-id="6b78f-122">Um Kundenmandantengeräte und Bedrohungen auf den Seiten für das Bedrohungsmanagement anzuzeigen, müssen Sie alle Kundenmandantengeräte in Microsoft Endpoint Manager (MEM) registrieren und diese schützen, indem Sie Microsoft Defender Antivirus ausführen.</span><span class="sxs-lookup"><span data-stu-id="6b78f-122">To view customer tenant devices and threats on the threat management pages, you must enroll all customer tenant devices in Microsoft Endpoint Manager (MEM) and protect them by running Microsoft Defender Antivirus.</span></span>  

<span data-ttu-id="6b78f-123">Weitere Informationen finden Sie unter [Registrieren von Geräten in Microsoft Intune.](/mem/intune/enrollment/)</span><span class="sxs-lookup"><span data-stu-id="6b78f-123">For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>  

<span data-ttu-id="6b78f-124">Microsoft Defender Antivirus ist Teil des Windows Betriebssystems und auf Geräten mit Windows 10 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6b78f-124">Microsoft Defender Antivirus is part of the Windows operating system and is enabled by default on devices running Windows 10.</span></span>  

> [!NOTE] 
> <span data-ttu-id="6b78f-125">Wenn Sie eine Antivirenlösung verwenden, die nicht von Microsoft stammt und nicht Microsoft Defender Antivirus, wird Microsoft Defender Antivirus automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6b78f-125">If you're using a non-Microsoft antivirus solution and not Microsoft Defender Antivirus, Microsoft Defender Antivirus is disabled automatically.</span></span> <span data-ttu-id="6b78f-126">Wenn Sie die Antivirenlösung deinstallieren, die nicht von Microsoft stammt, wird Microsoft Defender Antivirus automatisch aktiviert, um Ihre Windows Geräte vor Bedrohungen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="6b78f-126">When you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus is activated automatically to protect your Windows devices from threats.</span></span>    

## <a name="related-content"></a><span data-ttu-id="6b78f-127">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="6b78f-127">Related content</span></span>   

<span data-ttu-id="6b78f-128">[Konfigurieren Microsoft 365 Lighthouse Portalsicherheit](m365-lighthouse-configure-portal-security.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6b78f-128">[Configure Microsoft 365 Lighthouse portal security](m365-lighthouse-configure-portal-security.md) (article)</span></span>\
<span data-ttu-id="6b78f-129">[Übersicht über Microsoft 365 Lighthouse Gerätekompatibilität](m365-lighthouse-device-compliance-page-overview.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6b78f-129">[Microsoft 365 Lighthouse Device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="6b78f-130">[Übersicht über die Seite "Microsoft 365 Lighthouse Benutzer"](m365-lighthouse-users-page-overview.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6b78f-130">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="6b78f-131">[Übersicht über Microsoft 365 Lighthouse Seite "Bedrohungsmanagement"](m365-lighthouse-threat-management-page-overview.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6b78f-131">[Microsoft 365 Lighthouse Threat management page overview](m365-lighthouse-threat-management-page-overview.md) (article)</span></span>\
<span data-ttu-id="6b78f-132">[häufig gestellte Fragen](m365-lighthouse-faq.yml)   zu Microsoft 365 Lighthouse (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6b78f-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>

