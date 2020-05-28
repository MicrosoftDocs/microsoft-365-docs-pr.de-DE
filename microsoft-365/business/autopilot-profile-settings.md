---
title: Informationen zu AutoPilot-Profileinstellungen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Mithilfe von Autopilot-Profilen können Sie steuern, wie Windows auf Benutzergeräten installiert wird. Die Profile enthalten standardmäßige und optionale Einstellungen wie Skip Cortana Installation.
ms.openlocfilehash: 100de5e9548f901008d3ae154ac5a237ef265ffb
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401032"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="310c2-104">Informationen zu AutoPilot-Profileinstellungen</span><span class="sxs-lookup"><span data-stu-id="310c2-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="310c2-105">Autopilot-Profileinstellungen</span><span class="sxs-lookup"><span data-stu-id="310c2-105">AutoPilot profile settings</span></span>

<span data-ttu-id="310c2-106">Sie können Autopilot-Profile verwenden, um zu steuern, wie Windows auf Benutzergeräten installiert wird.</span><span class="sxs-lookup"><span data-stu-id="310c2-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="310c2-107">Die Profile enthalten die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="310c2-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="310c2-108">**Autopilot-Standardfeatures (erforderlich), die automatisch festgelegt werden:**</span><span class="sxs-lookup"><span data-stu-id="310c2-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="310c2-109">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="310c2-109">**Setting**</span></span>|<span data-ttu-id="310c2-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="310c2-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="310c2-111">Überspringen von Cortana, OneDrive und OEM-Registrierung</span><span class="sxs-lookup"><span data-stu-id="310c2-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="310c2-112">Überspringt die Installation von Consumer-apps wie Cortana und persönliche OneDrive.</span><span class="sxs-lookup"><span data-stu-id="310c2-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="310c2-113">Der Geräte Benutzer kann diese später installieren, solange der Benutzer ein lokaler Administrator auf dem Gerät ist.</span><span class="sxs-lookup"><span data-stu-id="310c2-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="310c2-114">Die ursprüngliche Herstellerregistrierung wird übersprungen, da das Gerät von Microsoft 365 Business Premium verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="310c2-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="310c2-115">Anmeldeumgebung mit dem Branding Ihres Unternehmens</span><span class="sxs-lookup"><span data-stu-id="310c2-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="310c2-116">Wenn Ihr Unternehmen ein [Branding Ihres Unternehmens zur Microsoft 365-Anmeldeseite hinzufügt](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), erhält der Geräte Benutzer diese Erfahrung beim anmelden.</span><span class="sxs-lookup"><span data-stu-id="310c2-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="310c2-117">Automatische MDM-Registrierung mit konfigurierten AAD-Konten</span><span class="sxs-lookup"><span data-stu-id="310c2-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="310c2-118">Die Benutzeridentität wird von Azure Active Directory verwaltet, und die Benutzer melden sich bei Windows und Microsoft 365 mit Ihren Microsoft 365 Business Premium-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="310c2-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="310c2-119">**Optionale Einstellungen:**</span><span class="sxs-lookup"><span data-stu-id="310c2-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="310c2-120">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="310c2-120">**Setting**</span></span>|<span data-ttu-id="310c2-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="310c2-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="310c2-122">Datenschutzeinstellungen überspringen (standardmäßig deaktiviert)</span><span class="sxs-lookup"><span data-stu-id="310c2-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="310c2-123">Wenn diese Option auf **Ein** festgelegt wurde, wird dem Gerätebenutzer bei der Erstanmeldung der Lizenzvertrag für das Gerät und Windows nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="310c2-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="310c2-124">Nicht zulassen, dass der Benutzer der lokale Administrator wird</span><span class="sxs-lookup"><span data-stu-id="310c2-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="310c2-125">Wenn diese Option auf **Ein** festgelegt wurde, kann der Gerätebenutzer keine persönlichen Apps, z. B. Cortana, installieren.    </span><span class="sxs-lookup"><span data-stu-id="310c2-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   
