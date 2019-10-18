---
title: Informationen zu AutoPilot-Profileinstellungen
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Mithilfe von Autopilot-Profilen können Sie steuern, wie Windows auf Benutzergeräten installiert wird. Die Profile enthalten standardmäßige und optionale Einstellungen wie Skip Cortana Installation.
ms.openlocfilehash: eb0d9a95c796909d024db1d061aaeace7d07ed1b
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574576"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="b880a-104">Informationen zu AutoPilot-Profileinstellungen</span><span class="sxs-lookup"><span data-stu-id="b880a-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="b880a-105">Autopilot-Profileinstellungen</span><span class="sxs-lookup"><span data-stu-id="b880a-105">AutoPilot profile settings</span></span>

<span data-ttu-id="b880a-106">Sie können steuern, wie Windows auf Benutzergeräten mithilfe der Autopilot-Profile installiert wird.</span><span class="sxs-lookup"><span data-stu-id="b880a-106">You can control how Windows gets installed on user devices by using the AutoPilot profiles.</span></span> <span data-ttu-id="b880a-107">Die Profile enthalten die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="b880a-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="b880a-108">**Autopilot-Standardfeatures (erforderlich), die automatisch festgelegt werden:**</span><span class="sxs-lookup"><span data-stu-id="b880a-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="b880a-109">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="b880a-109">**Setting**</span></span>|<span data-ttu-id="b880a-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b880a-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b880a-111">Cortana-, OneDrive- und OEM-Registrierung überspringen</span><span class="sxs-lookup"><span data-stu-id="b880a-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="b880a-112">Überspringt die Installation von Consumer-apps wie Cortana und persönliche OneDrive.</span><span class="sxs-lookup"><span data-stu-id="b880a-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="b880a-113">Der Geräte Benutzer kann diese später installieren, solange er ein lokaler Administrator auf dem Gerät ist.</span><span class="sxs-lookup"><span data-stu-id="b880a-113">The device user can install these later as long as he or she is a local admin on the device.</span></span> <span data-ttu-id="b880a-114">Die ursprüngliche Herstellerregistrierung wird übersprungen, da das Gerät von Microsoft 365 Business verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="b880a-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="b880a-115">Anmeldeumgebung mit dem Branding Ihres Unternehmens</span><span class="sxs-lookup"><span data-stu-id="b880a-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="b880a-116">Wenn Ihr Unternehmen das [Branding Ihres Unternehmens zu Office 365 Anmeldeseite hinzufügen](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)hat, erhält der Geräte Benutzer diese Erfahrung beim anmelden.</span><span class="sxs-lookup"><span data-stu-id="b880a-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="b880a-117">Automatische MDM-Registrierung mit konfigurierten AAD-Konten</span><span class="sxs-lookup"><span data-stu-id="b880a-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="b880a-118">Die Benutzeridentität wird von Azure Active Directory verwaltet, und die Benutzer melden sich mit ihren Microsoft 365 Business-Anmeldeinformationen bei Windows und Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="b880a-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="b880a-119">**Optionale Einstellungen:**</span><span class="sxs-lookup"><span data-stu-id="b880a-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="b880a-120">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="b880a-120">**Setting**</span></span>|<span data-ttu-id="b880a-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b880a-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b880a-122">Datenschutzeinstellungen überspringen (standardmäßig deaktiviert)</span><span class="sxs-lookup"><span data-stu-id="b880a-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="b880a-123">Wenn diese Option auf **Ein** festgelegt wurde, wird dem Gerätebenutzer bei der Erstanmeldung der Lizenzvertrag für das Gerät und Windows nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b880a-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="b880a-124">Nicht zulassen, dass der Benutzer der lokale Administrator wird</span><span class="sxs-lookup"><span data-stu-id="b880a-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="b880a-125">Wenn diese Option auf **Ein** festgelegt wurde, kann der Gerätebenutzer keine persönlichen Apps, z. B. Cortana, installieren.    </span><span class="sxs-lookup"><span data-stu-id="b880a-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
