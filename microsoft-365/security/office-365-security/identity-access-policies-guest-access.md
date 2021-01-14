---
title: Identitäts- und Gerätezugriffsrichtlinien zum Zulassen des Gast- und externen Benutzerzugriffs auf B2B - Microsoft 365 Enterprise | Microsoft Docs
description: Beschreibt die empfohlenen Richtlinien für bedingten Zugriff und verwandte Richtlinien zum Schutz des Zugriffs von Gästen und externen Benutzern.
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 4ee6cb93e5c943d704950e28ba4dc70a246429a6
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845076"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="66164-103">Richtlinien zum Zulassen des Gastzugriffs und des externen B2B-Benutzerzugriffs</span><span class="sxs-lookup"><span data-stu-id="66164-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="66164-104">In diesem Artikel wird das Anpassen der empfohlenen Geräte- und Identitätszugriffsrichtlinien erläutert, um Den Zugriff für Gäste und externe Benutzer zu ermöglichen, die über ein Azure Active Directory (Azure AD) Business-to-Business (B2B)-Konto verfügen.</span><span class="sxs-lookup"><span data-stu-id="66164-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="66164-105">Diese Anleitung basiert auf den [allgemeinen Identitäts- und Gerätezugriffsrichtlinien.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="66164-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="66164-106">Diese Empfehlungen gelten für die **grundlegende** Schutzebene.</span><span class="sxs-lookup"><span data-stu-id="66164-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="66164-107">Sie können die Empfehlungen jedoch auch basierend auf Ihren spezifischen Anforderungen für den Schutz **vertraulicher** und **streng regulierter Daten** anpassen.</span><span class="sxs-lookup"><span data-stu-id="66164-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="66164-108">Wenn Sie einen Pfad für B2B-Konten zur Authentifizierung bei Ihrem Azure AD-Mandanten bereitstellen, erhalten diese Konten keinen Zugriff auf Ihre gesamte Umgebung.</span><span class="sxs-lookup"><span data-stu-id="66164-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="66164-109">Benutzer von B2B und deren Konten haben Zugriff auf Dienste und Ressourcen, z. B. Dateien, die durch die Richtlinie für bedingten Zugriff für sie freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="66164-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="66164-110">Aktualisieren der allgemeinen Richtlinien zum Zulassen und Schützen von Gästen und externem Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="66164-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="66164-111">Dieses Diagramm zeigt, welche Richtlinien zwischen den allgemeinen Identitäts- und Gerätezugriffsrichtlinien für den B2B-Gast- und externen Benutzerzugriff hinzugefügt oder aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="66164-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="66164-112">[![Zusammenfassung der Richtlinienupdates zum Schutz des Gastzugriffs](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="66164-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="66164-113">Sehen Sie sich eine größere Version dieses Bilds an.</span><span class="sxs-lookup"><span data-stu-id="66164-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="66164-114">In der folgenden Tabelle sind die Richtlinien aufgeführt, die Sie entweder erstellen und aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="66164-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="66164-115">Die allgemeinen Richtlinien sind mit den zugehörigen Konfigurationsanweisungen im Artikel ["Allgemeine Identitäts- und Gerätezugriffsrichtlinien"](identity-access-policies.md) verknüpft.</span><span class="sxs-lookup"><span data-stu-id="66164-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="66164-116">Schutzebene</span><span class="sxs-lookup"><span data-stu-id="66164-116">Protection level</span></span>|<span data-ttu-id="66164-117">Richtlinien</span><span class="sxs-lookup"><span data-stu-id="66164-117">Policies</span></span>|<span data-ttu-id="66164-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66164-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="66164-119">**Basisplan**</span><span class="sxs-lookup"><span data-stu-id="66164-119">**Baseline**</span></span>|[<span data-ttu-id="66164-120">MFA immer für Gäste und externe Benutzer erforderlich</span><span class="sxs-lookup"><span data-stu-id="66164-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="66164-121">Erstellen Sie diese neue Richtlinie, und konfigurieren Sie:</span><span class="sxs-lookup"><span data-stu-id="66164-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="66164-122">For **Assignments > Users and groups > Include**, choose Select users and **groups,** and then select All guest and external **users**.</span><span class="sxs-lookup"><span data-stu-id="66164-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="66164-123">Lassen **Sie für > A0**> A0 alle Optionen deaktiviert, um die mehrstufige Authentifizierung (MFA) immer zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="66164-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="66164-124">MFA erforderlich, wenn das Anmelderisiko *mittel oder* hoch *ist*</span><span class="sxs-lookup"><span data-stu-id="66164-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="66164-125">Ändern Sie diese Richtlinie, um Gäste und externe Benutzer auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="66164-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="66164-126">Kompatible PCs erforderlich</span><span class="sxs-lookup"><span data-stu-id="66164-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="66164-127">Ändern Sie diese Richtlinie, um Gäste und externe Benutzer auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="66164-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="66164-128">Wenn Sie Gäste und externe Benutzer in Richtlinien für bedingten Zugriff ein- oder ausschließen möchten, aktivieren Sie für Aufgaben > Benutzer und Gruppen **> Ein-** oder Ausschließen alle Gastbenutzer und **externen Benutzer.**</span><span class="sxs-lookup"><span data-stu-id="66164-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![Bildschirmaufnahme von Steuerelementen für das Ausschließen von Gästen und externen Benutzern](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="66164-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66164-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="66164-131">Zugriff auf Gäste und externe Benutzer mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66164-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="66164-132">Microsoft Teams definiert die folgenden Benutzer:</span><span class="sxs-lookup"><span data-stu-id="66164-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="66164-133">**Gastzugriff** verwendet ein Azure AD B2B-Konto, das als Mitglied eines Teams hinzugefügt werden kann und Zugriff auf die Kommunikation und die Ressourcen des Teams hat.</span><span class="sxs-lookup"><span data-stu-id="66164-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="66164-134">**Der externe** Zugriff ist für einen externen Benutzer ohne ein B2B-Konto.</span><span class="sxs-lookup"><span data-stu-id="66164-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="66164-135">Der Zugriff durch externe Benutzer umfasst Einladungen, Anrufe, Chats und Besprechungen, umfasst jedoch keine Teammitgliedschaft und keinen Zugriff auf die Ressourcen des Teams.</span><span class="sxs-lookup"><span data-stu-id="66164-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="66164-136">Weitere Informationen finden Sie im Vergleich zwischen Gästen und [externem Benutzerzugriff für Teams.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="66164-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="66164-137">Weitere Informationen zum Sichern von Identitäts- und Gerätezugriffsrichtlinien für Teams finden Sie unter Richtlinienempfehlungen zum Sichern von [Teams-Chats,](teams-access-policies.md)-Gruppen und -Dateien.</span><span class="sxs-lookup"><span data-stu-id="66164-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="66164-138">MFA immer für Gastbenutzer und externe Benutzer erforderlich</span><span class="sxs-lookup"><span data-stu-id="66164-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="66164-139">Diese Richtlinie fordert Gäste auf, sich für MFA in Ihrem Mandanten zu registrieren, unabhängig davon, ob sie für MFA in ihrem Home-Mandanten registriert sind.</span><span class="sxs-lookup"><span data-stu-id="66164-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="66164-140">Beim Zugriff auf Ressourcen in Ihrem Mandanten müssen Gäste und externe Benutzer MFA für jede Anforderung verwenden.</span><span class="sxs-lookup"><span data-stu-id="66164-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="66164-141">Ausschließen von Gästen und externen Benutzern von risikobasierten MFA</span><span class="sxs-lookup"><span data-stu-id="66164-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="66164-142">Während Organisationen risikobasierte Richtlinien für B2B-Benutzer mithilfe von Azure AD Identity Protection erzwingen können, gibt es aufgrund ihrer in ihrem Startverzeichnis vorhandenen Identität Einschränkungen bei der Implementierung von Azure AD Identity Protection für Benutzer der B2B-Zusammenarbeit in einem Ressourcenverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="66164-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="66164-143">Aufgrund dieser Einschränkungen empfiehlt Microsoft, Gäste von risikobasierten Richtlinien für MFA auszuschließen und von diesen Benutzern die Verwendung von MFA zu verlangen.</span><span class="sxs-lookup"><span data-stu-id="66164-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="66164-144">Weitere Informationen finden Sie unter ["Einschränkungen des Identitätsschutzes für Benutzer der B2B-Zusammenarbeit".](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)</span><span class="sxs-lookup"><span data-stu-id="66164-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="66164-145">Ausschließen von Gästen und externen Benutzern aus der Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="66164-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="66164-146">Nur eine Organisation kann ein Gerät verwalten.</span><span class="sxs-lookup"><span data-stu-id="66164-146">Only one organization can manage a device.</span></span> <span data-ttu-id="66164-147">Wenn Sie Gäste und externe Benutzer nicht von Richtlinien ausschließen, die Gerätekonformität erfordern, blockieren diese Richtlinien diese Benutzer.</span><span class="sxs-lookup"><span data-stu-id="66164-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="66164-148">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="66164-148">Next step</span></span>

![Schritt 4: Richtlinien für Microsoft 365-Cloud-Apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="66164-150">Konfigurieren Sie Richtlinien für bedingten Zugriff für:</span><span class="sxs-lookup"><span data-stu-id="66164-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="66164-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66164-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="66164-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="66164-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="66164-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="66164-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
