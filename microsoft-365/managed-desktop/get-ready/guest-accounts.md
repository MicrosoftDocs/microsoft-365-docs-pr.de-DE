---
title: Voraussetzungen für Gastkonten
description: Konfigurationsrichtlinien für Gastkonten und deren Anpassung
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073224"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="9edcd-104">Voraussetzungen für Gastkonten</span><span class="sxs-lookup"><span data-stu-id="9edcd-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="9edcd-105">Für Microsoft Managed Desktop sind die folgenden Einstellungen in ihrer Azure AD Organisation für den Zugriff auf Gastkonten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9edcd-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="9edcd-106">Sie können diese Einstellungen im Azure- [Portal](https://portal.azure.com) unter **externe Identitäten/externe Zusammenarbeit** anpassen:</span><span class="sxs-lookup"><span data-stu-id="9edcd-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration** :</span></span>

-   <span data-ttu-id="9edcd-107">**Administratoren und Benutzer in der Rolle "Gast Inviter" können die Einstellung "Ja" einladen** . **Yes**</span><span class="sxs-lookup"><span data-stu-id="9edcd-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="9edcd-108">Wählen Sie unter Einschränkungen für die **Zusammenarbeit** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="9edcd-108">For **Collaboration restrictions** , choose any of these options:</span></span>
    -   <span data-ttu-id="9edcd-109">Wenn Sie zulassen, dass **Einladungen an eine beliebige Domäne gesendet werden (am besten inklusive)** , ist keine andere Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9edcd-109">If you select **Allow invitations to be sent to any domain (most inclusive)** , no other configuration required.</span></span>
    -   <span data-ttu-id="9edcd-110">Wenn Sie **Einladungen zu den angegebenen Domänen verweigern** auswählen, stellen Sie sicher, dass Microsoft.com nicht in den Zieldomänen aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="9edcd-110">If you select **Deny invitations to the specified domains** , make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="9edcd-111">Wenn Sie **Einladungen nur für die angegebenen Domänen (am restriktivsten) zulassen** auswählen, stellen Sie sicher, dass Microsoft.com in den Zieldomänen aufgeführt *ist* .</span><span class="sxs-lookup"><span data-stu-id="9edcd-111">If you select **Allow invitations only to the specified domains (most restrictive)** , make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="9edcd-112">Wenn Sie Einschränkungen festlegen, die mit diesen Einstellungen interagieren, stellen Sie sicher, dass Sie die Azure-Active Directory **moderne Arbeitsplatz-Dienstkonten** ausschließen.</span><span class="sxs-lookup"><span data-stu-id="9edcd-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="9edcd-113">Wenn Sie beispielsweise über eine Richtlinie für den bedingten Zugriff verfügen, die verhindert, dass Gastkonten auf das InTune-Portal zugreifen können, schließen Sie die Gruppe **moderner Arbeitsplatz-Dienstkonten** aus dieser Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="9edcd-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

