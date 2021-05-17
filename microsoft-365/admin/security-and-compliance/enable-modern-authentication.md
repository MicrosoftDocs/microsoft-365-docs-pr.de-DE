---
title: Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Erfahren Sie, wie Sie Registrierungsschlüssel festlegen, um die moderne Authentifizierung für Geräte zu aktivieren, auf denen Microsoft Office 2013 installiert ist.
ms.openlocfilehash: f803cf9a30be63e71ef3c4293d0d1ba5b2355e75
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580834"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="a5085-103">Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten</span><span class="sxs-lookup"><span data-stu-id="a5085-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="a5085-104">[] Wenn Sie moderne Authentifizierung bei Windows-Geräten aktivieren möchten, auf denen Office 2013 installiert ist, müssen Sie spezielle Registrierungsschlüssel festlegen.</span><span class="sxs-lookup"><span data-stu-id="a5085-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="a5085-105">Aktivieren von moderner Authentifizierung bei Office 2013-Clients</span><span class="sxs-lookup"><span data-stu-id="a5085-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="a5085-106">Die moderne Authentifizierung ist für Office 2016-Clients bereits aktiviert, daher müssen Sie für Office 2016 keine Registrierungsschlüssel festlegen.</span><span class="sxs-lookup"><span data-stu-id="a5085-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="a5085-p101">Um moderne Authentifizierung bei Geräten unter Windows (beispielsweise auf Laptops und Tablets) zu aktivieren, auf denen Microsoft Office 2013 installiert ist, müssen Sie die nachstehenden Registrierungsschlüssel festlegen. Die Schlüssel müssen auf jedem Gerät festgelegt werden, das Sie für moderne Authentifizierung aktivieren möchten:</span><span class="sxs-lookup"><span data-stu-id="a5085-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="a5085-109">**Registrierungsschlüssel**</span><span class="sxs-lookup"><span data-stu-id="a5085-109">**Registry key**</span></span>|<span data-ttu-id="a5085-110">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a5085-110">**Type**</span></span>|<span data-ttu-id="a5085-111">**Wert**</span><span class="sxs-lookup"><span data-stu-id="a5085-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="a5085-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="a5085-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="a5085-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a5085-113">REG_DWORD</span></span>  |<span data-ttu-id="a5085-114">1</span><span class="sxs-lookup"><span data-stu-id="a5085-114">1</span></span>  |
|<span data-ttu-id="a5085-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="a5085-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="a5085-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a5085-116">REG_DWORD</span></span> |<span data-ttu-id="a5085-117">1</span><span class="sxs-lookup"><span data-stu-id="a5085-117">1</span></span> |
   
<span data-ttu-id="a5085-118">Nachdem Sie die Registrierungsschlüssel festgelegt haben, können Sie Office 2013-Geräte-Apps so festlegen, dass die mehrstufige Authentifizierung [(MFA)](set-up-multi-factor-authentication.md) mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5085-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="a5085-p102">Wenn Sie aktuell bei einer der Client-Apps angemeldet sind, müssen Sie sich abmelden und wieder anmelden, damit die Änderung wirksam wird. Andernfalls werden die MRU- und Roamingeinstellungen erst wieder verfügbar, wenn die ADAL-Identität eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="a5085-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="a5085-121">Deaktivieren von moderner Authentifizierung auf Geräten</span><span class="sxs-lookup"><span data-stu-id="a5085-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="a5085-122">Wenn Sie moderne Authentifizierung auf einem Gerät deaktivieren möchten, legen Sie dort die folgenden Registrierungsschlüssel fest:</span><span class="sxs-lookup"><span data-stu-id="a5085-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="a5085-123">**Registrierungsschlüssel**</span><span class="sxs-lookup"><span data-stu-id="a5085-123">**Registry key**</span></span>|<span data-ttu-id="a5085-124">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a5085-124">**Type**</span></span>|<span data-ttu-id="a5085-125">**Wert**</span><span class="sxs-lookup"><span data-stu-id="a5085-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="a5085-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="a5085-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="a5085-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a5085-127">REG_DWORD</span></span>|<span data-ttu-id="a5085-128">0</span><span class="sxs-lookup"><span data-stu-id="a5085-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="a5085-129">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="a5085-129">Related articles</span></span>
[<span data-ttu-id="a5085-130">Anmelden bei Office 2013 mit einer zweiten Überprüfungsmethode</span><span class="sxs-lookup"><span data-stu-id="a5085-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[<span data-ttu-id="a5085-131">Outlook Eingabeaufforderungen zum Kennwort und verwendet keine moderne Authentifizierung, um eine Verbindung mit Office 365</span><span class="sxs-lookup"><span data-stu-id="a5085-131">Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365</span></span>](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)

