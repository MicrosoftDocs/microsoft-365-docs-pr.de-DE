---
title: Informationen zu AutoPilot-Profileinstellungen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot Profile können Sie steuern, wie Windows auf Geräten der Benutzer installiert wird. Die Profile enthalten Standard und optionale Einstellungen wie Cortana-Installation zu überspringen.
ms.openlocfilehash: f114d1d446fae9924eb8bd8844341201deaf5299
ms.sourcegitcommit: 25fec94d85afcd4dca585fd6ebce5d364ebe41c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "25607960"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="2a854-104">Informationen zu AutoPilot-Profileinstellungen</span><span class="sxs-lookup"><span data-stu-id="2a854-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="2a854-105">AutoPilot-Profileinstellungen</span><span class="sxs-lookup"><span data-stu-id="2a854-105">AutoPilot profile settings</span></span>

<span data-ttu-id="2a854-p102">Sie können steuern, wie Windows auf Geräten der Benutzer mithilfe der AutoPilot Profile installiert wird. Die Profile enthalten die folgenden Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="2a854-p102">You can control how Windows gets installed on user devices by using the AutoPilot profiles. The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="2a854-108">**AutoPilot-Standardfeatures (erforderlich), die automatisch festgelegt werden:**</span><span class="sxs-lookup"><span data-stu-id="2a854-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="2a854-109">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="2a854-109">**Setting**</span></span>|<span data-ttu-id="2a854-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2a854-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a854-111">Cortana-, OneDrive- und OEM-Registrierung überspringen</span><span class="sxs-lookup"><span data-stu-id="2a854-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="2a854-p103">Überspringt die Installation der Consumer apps wie Cortana und persönliche OneDrive. Benutzer des Geräts kann diese später installieren, solange er ein lokaler Administrator auf dem Gerät ist. Die ursprünglichen Hersteller Registrierung wird übersprungen, da das Gerät von Microsoft 365 Business verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="2a854-p103">Skips the installation of consumer apps like Cortana and personal OneDrive. The device user can install these later as long as he or she is a local admin on the device. The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="2a854-115">Anmeldeumgebung mit dem Branding Ihres Unternehmens</span><span class="sxs-lookup"><span data-stu-id="2a854-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="2a854-116">Wenn Ihr Unternehmen eine [Hinzufügen Ihres Unternehmens branding zu Office 365 Anmeldeseite](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)hat, erhalten Benutzer des Geräts dieser Erfahrungen bei der Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="2a854-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="2a854-117">Automatische MDM-Registrierung mit konfigurierten AAD-Konten</span><span class="sxs-lookup"><span data-stu-id="2a854-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="2a854-118">Die Benutzeridentität wird von Azure Active Directory verwaltet, und die Benutzer melden sich mit ihren Microsoft 365 Business-Anmeldeinformationen bei Windows und Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="2a854-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="2a854-119">**Optionale Einstellungen:**</span><span class="sxs-lookup"><span data-stu-id="2a854-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="2a854-120">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="2a854-120">**Setting**</span></span>|<span data-ttu-id="2a854-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2a854-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a854-122">Datenschutzeinstellungen überspringen (standardmäßig deaktiviert)</span><span class="sxs-lookup"><span data-stu-id="2a854-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="2a854-123">Wenn diese Option auf **Ein** festgelegt wurde, wird dem Gerätebenutzer bei der Erstanmeldung der Lizenzvertrag für das Gerät und Windows nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2a854-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="2a854-124">Nicht zulassen, dass der Benutzer der lokale Administrator wird</span><span class="sxs-lookup"><span data-stu-id="2a854-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="2a854-125">Wenn diese Option auf **Ein** festgelegt wurde, kann der Gerätebenutzer keine persönlichen Apps, z. B. Cortana, installieren.  </span><span class="sxs-lookup"><span data-stu-id="2a854-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
