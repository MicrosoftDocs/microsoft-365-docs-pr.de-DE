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
audience: Admin
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574607"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="e777a-104">Voraussetzungen für Gastkonten</span><span class="sxs-lookup"><span data-stu-id="e777a-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="e777a-105">Microsoft Managed Desktop erfordert die folgenden Einstellungen in Ihrer Azure AD-Organisation für den Gastkontozugriff.</span><span class="sxs-lookup"><span data-stu-id="e777a-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="e777a-106">Sie können diese Einstellungen im [Azure-Portal unter](https://portal.azure.com) **Externe Identitäten /Externe Zusammenarbeit anpassen:**</span><span class="sxs-lookup"><span data-stu-id="e777a-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration**:</span></span>

-   <span data-ttu-id="e777a-107">**Administratoren und Benutzer in der Gast einladenden Rolle können auf** Ja festlegen **einladen**</span><span class="sxs-lookup"><span data-stu-id="e777a-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="e777a-108">Wählen **Sie für Einschränkungen für** die Zusammenarbeit eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="e777a-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="e777a-109">Wenn Sie Einladungen an eine Beliebige Domäne **(einschließlich)** zulassen auswählen, ist keine andere Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e777a-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="e777a-110">Wenn Sie **Einladungen an** die angegebenen Domänen verweigern auswählen, stellen Sie sicher, dass Microsoft.com nicht in den Zieldomänen aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="e777a-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="e777a-111">Wenn Sie Einladungen nur für die angegebenen **Domänen zulassen (am** restriktivsten) auswählen, stellen Sie sicher, dass Microsoft.com in den Zieldomänen aufgeführt ist. </span><span class="sxs-lookup"><span data-stu-id="e777a-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="e777a-112">Wenn Sie Einschränkungen festlegen, die mit diesen Einstellungen interagieren, müssen Sie die Azure Active Directory **Modern Workplace Service Accounts ausschließen.**</span><span class="sxs-lookup"><span data-stu-id="e777a-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="e777a-113">Wenn Sie beispielsweise über eine Richtlinie für bedingten Zugriff verfügen, die verhindert, dass Gastkonten auf das Intune-Portal zugreifen, schließen Sie die Gruppe **Moderne Arbeitsplatzdienstkonten** aus dieser Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="e777a-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="e777a-114">Schritte für die ersten Schritte</span><span class="sxs-lookup"><span data-stu-id="e777a-114">Steps to get ready</span></span>

1. <span data-ttu-id="e777a-115">Überprüfen [Sie die Voraussetzungen für Microsoft Managed Desktop](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="e777a-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="e777a-116">Verwenden [Sie Die Bereitschaftsbewertungstools](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="e777a-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="e777a-117">[Voraussetzungen für Gastkonten](guest-accounts.md) (Dieser Artikel)</span><span class="sxs-lookup"><span data-stu-id="e777a-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="e777a-118">Netzwerkkonfiguration für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="e777a-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="e777a-119">Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="e777a-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="e777a-120">Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="e777a-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="e777a-121">Anwendungen in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="e777a-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="e777a-122">Voraussetzungen von zugeordneten Laufwerken für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="e777a-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="e777a-123">Voraussetzungen von Druckressourcen für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="e777a-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)