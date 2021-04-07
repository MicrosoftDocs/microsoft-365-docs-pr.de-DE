---
title: Identitäts- und Gerätezugriffsrichtlinien zum Zulassen des B2B-Zugriffs für Gastbenutzer und externe Benutzer – Microsoft 365 for Enterprise | Microsoft Docs
description: Beschreibt die empfohlenen Richtlinien für bedingten Zugriff und verwandte Richtlinien zum Schutz des Zugriffs von Gästen und externen Benutzern.
ms.prod: m365-security
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
audience: Admin
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
ms.technology: mdo
ms.openlocfilehash: 0baefab441b17aa4a9527536cead181bae8f8948
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599995"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="474b0-103">Richtlinien zum Zulassen des Gastzugriffs und des externen B2B-Zugriffs durch B2B</span><span class="sxs-lookup"><span data-stu-id="474b0-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="474b0-104">In diesem Artikel wird die Anpassung der empfohlenen Geräte- und Identitätszugriffsrichtlinien erläutert, um Gästen und externen Benutzern, die über ein Azure Active Directory (Azure AD) Business-to-Business (B2B)-Konto verfügen, zugriff zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="474b0-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="474b0-105">Diese Anleitung baut auf den [allgemeinen Identitäts- und Gerätezugriffsrichtlinien auf.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="474b0-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="474b0-106">Diese Empfehlungen sind so konzipiert, dass sie auf die **Basisebene** des Schutzes angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="474b0-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="474b0-107">Sie können die Empfehlungen jedoch auch an Ihre spezifischen Anforderungen für den **vertraulichen** und streng **regulierten Schutz** anpassen.</span><span class="sxs-lookup"><span data-stu-id="474b0-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="474b0-108">Wenn Sie einen Pfad für B2B-Konten zur Authentifizierung bei Ihrem Azure AD-Mandanten bereitstellen, erhalten diese Konten keinen Zugriff auf Ihre gesamte Umgebung.</span><span class="sxs-lookup"><span data-stu-id="474b0-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="474b0-109">B2B-Benutzer und ihre Konten haben Zugriff auf Dienste und Ressourcen, z. B. Dateien, die ihnen von der Richtlinie für bedingten Zugriff zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="474b0-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="474b0-110">Aktualisieren der allgemeinen Richtlinien zum Zulassen und Schützen von Gästen und externem Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="474b0-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="474b0-111">Dieses Diagramm zeigt, welche Richtlinien zwischen den allgemeinen Identitäts- und Gerätezugriffsrichtlinien für B2B-Gast- und externen Benutzerzugriff hinzugefügt oder aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="474b0-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="474b0-112">[![Zusammenfassung der Richtlinienupdates zum Schutz des Gastzugriffs](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="474b0-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

<span data-ttu-id="474b0-113">In der folgenden Tabelle sind die Richtlinien aufgeführt, die Sie entweder erstellen und aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="474b0-113">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="474b0-114">Die allgemeinen Richtlinien verknüpfen mit den zugehörigen Konfigurationsanweisungen im Artikel [Allgemeine Identitäts- und Gerätezugriffsrichtlinien.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="474b0-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="474b0-115">Schutzebene</span><span class="sxs-lookup"><span data-stu-id="474b0-115">Protection level</span></span>|<span data-ttu-id="474b0-116">Richtlinien</span><span class="sxs-lookup"><span data-stu-id="474b0-116">Policies</span></span>|<span data-ttu-id="474b0-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="474b0-117">More information</span></span>|
|---|---|---|
|<span data-ttu-id="474b0-118">**Basisplan**</span><span class="sxs-lookup"><span data-stu-id="474b0-118">**Baseline**</span></span>|[<span data-ttu-id="474b0-119">MFA immer für Gäste und externe Benutzer benötigen</span><span class="sxs-lookup"><span data-stu-id="474b0-119">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="474b0-120">Erstellen Sie diese neue Richtlinie, und konfigurieren Sie:</span><span class="sxs-lookup"><span data-stu-id="474b0-120">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="474b0-121">Wählen **Sie für > Benutzer** und Gruppen > Include die Option Benutzer und Gruppen auswählen aus, und wählen Sie dann Alle gast- und externen Benutzer **aus.** </span><span class="sxs-lookup"><span data-stu-id="474b0-121">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="474b0-122">Lassen **Sie für > Bedingungen > Anmeldung** alle Optionen deaktiviert, um die mehrstufige Authentifizierung (MFA) immer zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="474b0-122">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="474b0-123">MFA erforderlich, wenn das Anmelderisiko *mittel oder* hoch *ist*</span><span class="sxs-lookup"><span data-stu-id="474b0-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="474b0-124">Ändern Sie diese Richtlinie, um Gäste und externe Benutzer auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="474b0-124">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="474b0-125">Kompatible PCs erforderlich</span><span class="sxs-lookup"><span data-stu-id="474b0-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="474b0-126">Ändern Sie diese Richtlinie, um Gäste und externe Benutzer auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="474b0-126">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="474b0-127">Um Gäste und externe Benutzer in Richtlinien für bedingten Zugriff ein- oder auszuschließen, aktivieren Sie für **Zuordnungen >** Benutzer und Gruppen > Include or **Exclude** alle Gast- und **externe Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="474b0-127">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![Bildschirmaufnahme von Steuerelementen für das Ausschließen von Gästen und externen Benutzern](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="474b0-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="474b0-129">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="474b0-130">Gast- und externer Benutzerzugriff mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="474b0-130">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="474b0-131">Microsoft Teams definiert die folgenden Benutzer:</span><span class="sxs-lookup"><span data-stu-id="474b0-131">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="474b0-132">**Der Gastzugriff** verwendet ein Azure AD B2B-Konto, das als Mitglied eines Teams hinzugefügt werden kann und Zugriff auf die Kommunikation und Ressourcen des Teams hat.</span><span class="sxs-lookup"><span data-stu-id="474b0-132">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="474b0-133">**Der externe Zugriff** ist für einen externen Benutzer ohne B2B-Konto.</span><span class="sxs-lookup"><span data-stu-id="474b0-133">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="474b0-134">Der externe Benutzerzugriff umfasst Einladungen, Anrufe, Chats und Besprechungen, umfasst jedoch keine Teammitgliedschaft und keinen Zugriff auf die Ressourcen des Teams.</span><span class="sxs-lookup"><span data-stu-id="474b0-134">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="474b0-135">Weitere Informationen finden Sie im [Vergleich zwischen Gästen und externem Benutzerzugriff für Teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="474b0-135">For more information, see the [comparison between guests and external user access for teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="474b0-136">Weitere Informationen zum Schützen von Identitäts- und Gerätezugriffsrichtlinien für Teams finden Sie unter Richtlinienempfehlungen zum Schützen von [Teams-Chats, -Gruppen und -Dateien.](teams-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="474b0-136">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="474b0-137">MFA immer für Gastbenutzer und externe Benutzer erforderlich</span><span class="sxs-lookup"><span data-stu-id="474b0-137">Require MFA always for guest and external users</span></span>

<span data-ttu-id="474b0-138">Diese Richtlinie fordert Gäste auf, sich für MFA in Ihrem Mandanten zu registrieren, unabhängig davon, ob sie für MFA in ihrem Home-Mandanten registriert sind.</span><span class="sxs-lookup"><span data-stu-id="474b0-138">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="474b0-139">Beim Zugriff auf Ressourcen in Ihrem Mandanten müssen Gäste und externe Benutzer MFA für jede Anforderung verwenden.</span><span class="sxs-lookup"><span data-stu-id="474b0-139">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="474b0-140">Ausschließen von Gästen und externen Benutzern von risikobasierten MFA</span><span class="sxs-lookup"><span data-stu-id="474b0-140">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="474b0-141">Organisationen können zwar risikobasierte Richtlinien für B2B-Benutzer mithilfe von Azure AD Identity Protection erzwingen, es gibt jedoch Einschränkungen bei der Implementierung von Azure AD Identity Protection für Benutzer der B2B-Zusammenarbeit in einem Ressourcenverzeichnis aufgrund ihrer identität, die im Heimverzeichnis vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="474b0-141">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="474b0-142">Aufgrund dieser Einschränkungen empfiehlt Microsoft, Gäste von risikobasierten MFA-Richtlinien auszuschließen und von diesen Benutzern die verwendung von MFA zu verlangen.</span><span class="sxs-lookup"><span data-stu-id="474b0-142">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="474b0-143">Weitere Informationen finden Sie unter [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="474b0-143">For more information, see [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="474b0-144">Ausschließen von Gästen und externen Benutzern von der Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="474b0-144">Excluding guests and external users from device management</span></span>

<span data-ttu-id="474b0-145">Nur eine Organisation kann ein Gerät verwalten.</span><span class="sxs-lookup"><span data-stu-id="474b0-145">Only one organization can manage a device.</span></span> <span data-ttu-id="474b0-146">Wenn Sie Gäste und externe Benutzer nicht von Richtlinien ausschließen, die Gerätekonformität erfordern, blockieren diese Richtlinien diese Benutzer.</span><span class="sxs-lookup"><span data-stu-id="474b0-146">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="474b0-147">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="474b0-147">Next step</span></span>

![Schritt 4: Richtlinien für Microsoft 365-Cloud-Apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="474b0-149">Konfigurieren von Richtlinien für bedingten Zugriff für:</span><span class="sxs-lookup"><span data-stu-id="474b0-149">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="474b0-150">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="474b0-150">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="474b0-151">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="474b0-151">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="474b0-152">SharePoint</span><span class="sxs-lookup"><span data-stu-id="474b0-152">SharePoint</span></span>](sharepoint-file-access-policies.md)