---
title: Identitäts-und Gerätezugriffs Richtlinien für das Zulassen von Gast-und externem B2B-Zugriff – Microsoft 365 für Unternehmen | Microsoft-Dokumente
description: Beschreibt den empfohlenen bedingten Zugriff und verwandte Richtlinien zum Schützen des Zugriffs von Gast-und externen Benutzern.
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
ms.openlocfilehash: 55a84fa8ba31cfd4f981f2820811b541ae340a27
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357623"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="301fb-103">Richtlinien für das Zulassen von Gast-und externen B2B-Zugriff</span><span class="sxs-lookup"><span data-stu-id="301fb-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="301fb-104">In diesem Artikel wird beschrieben, wie Sie die empfohlenen allgemeinen Identitäts-und Gerätezugriffs Richtlinien anpassen können, um den Zugriff für Gast-und externe Benutzer zuzulassen, die über ein Business-to-Business-Konto (B2B) von Azure Active Directory (Azure AD) verfügen.</span><span class="sxs-lookup"><span data-stu-id="301fb-104">This article describes how to adjust the recommended common identity and device access policies to allow access for guest and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="301fb-105">Dieser Leitfaden basiert auf den [allgemeinen Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="301fb-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="301fb-106">Diese Empfehlungen sind darauf ausgelegt, auf die **grundlegende** Schutzebene anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="301fb-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="301fb-107">Sie können jedoch auch die Empfehlungen basierend auf der Granularität Ihrer Anforderungen für **sensiblen** und **streng reglementierten** Schutz anpassen.</span><span class="sxs-lookup"><span data-stu-id="301fb-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="301fb-108">Durch die Bereitstellungeines Pfads für B2B-Konten zur Authentifizierung bei Ihrem Azure AD Mandanten erhalten diese Konten keinen Zugriff auf Ihre gesamte Umgebung.</span><span class="sxs-lookup"><span data-stu-id="301fb-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="301fb-109">B2B-Benutzer und ihre Konten haben nur Zugriff auf Ressourcen, die für Sie (beispielsweise Dateien) innerhalb der in bedingten Zugriffsrichtlinien gewährten Dienste freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="301fb-109">B2B users and their accounts only have access to resources that are shared with them (such as files) within the services granted in Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="301fb-110">Aktualisieren der allgemeinen Richtlinien zum zulassen und schützen von Gast und externem Zugriff</span><span class="sxs-lookup"><span data-stu-id="301fb-110">Updating the common policies to allow and protect guest and external access</span></span>

<span data-ttu-id="301fb-111">Um Gast-und externen Zugriff mit Azure AD B2B-Konten zu schützen, zeigt das folgende Diagramm, welche Richtlinien hinzugefügt oder von den allgemeinen Richtlinien für Identitäts-und Geräte Zugriff aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="301fb-111">To protect guest and external access with Azure AD B2B accounts, the following diagram illustrates which policies to add or update from the the common identity and device access policies.</span></span>

<span data-ttu-id="301fb-112">[![Zusammenfassung der Richtlinienupdates zum Schützen des Gastzugriffs](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="301fb-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="301fb-113">Anzeigen einer größeren Version dieses Bilds</span><span class="sxs-lookup"><span data-stu-id="301fb-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="301fb-114">In der folgenden Tabelle sind die Richtlinien aufgeführt, die Sie entweder erstellen und aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="301fb-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="301fb-115">Die allgemeinen Richtlinien verweisen auf die zugehörigen Konfigurationsanweisungen im Artikel [Allgemeine Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="301fb-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="301fb-116">Schutzebene</span><span class="sxs-lookup"><span data-stu-id="301fb-116">Protection level</span></span>|<span data-ttu-id="301fb-117">Richtlinien</span><span class="sxs-lookup"><span data-stu-id="301fb-117">Policies</span></span>|<span data-ttu-id="301fb-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="301fb-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="301fb-119">**Basisplan**</span><span class="sxs-lookup"><span data-stu-id="301fb-119">**Baseline**</span></span>|[<span data-ttu-id="301fb-120">MFA immer für Gast und externe Benutzer erforderlich</span><span class="sxs-lookup"><span data-stu-id="301fb-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="301fb-121">Erstellen Sie diese neue Richtlinie, und konfigurieren Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="301fb-121">Create this new policy and configure:</span></span> <ul><li> <span data-ttu-id="301fb-122">Wählen Sie für **Zuordnungen > Benutzer und Gruppen > einschließen** die **Option Benutzer und Gruppen auswählen** aus, und wählen Sie dann **alle Gast-und externen Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="301fb-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span> </li><li> <span data-ttu-id="301fb-123">Lassen Sie für **Zuordnungen > Bedingungen > Anmeldung** die Option Alle Optionen deaktiviert, damit die mehrstufige Authentifizierung (MFA) immer erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="301fb-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li>|
||[<span data-ttu-id="301fb-124">MFA erforderlich, wenn das Anmelde Risiko *Mittel* groß oder *hoch* ist</span><span class="sxs-lookup"><span data-stu-id="301fb-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="301fb-125">Ändern Sie diese Richtlinie, um Gast-und externe Benutzer auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="301fb-125">Modify this policy to exclude guest and external users.</span></span>|
||[<span data-ttu-id="301fb-126">Kompatible PCs erforderlich</span><span class="sxs-lookup"><span data-stu-id="301fb-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="301fb-127">Ändern Sie diese Richtlinie, um Gast-und externe Benutzer auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="301fb-127">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="301fb-128">Wenn Sie Gast-und externe Benutzer in Richtlinien für den bedingten Zugriff einbeziehen oder ausschließen möchten, überprüfen Sie für **Zuordnungen > Benutzer und Gruppen, die > einschließen** oder **ausschließen**, **alle Gast-und externen Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="301fb-128">To include or exclude guest and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![Bildschirmaufzeichnung von Steuerelementen zum Ausschließen von Gast-und externen Benutzern](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="301fb-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="301fb-130">More information</span></span>

### <a name="guest-and-external-access-with-microsoft-teams"></a><span data-ttu-id="301fb-131">Gast-und externer Zugriff mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="301fb-131">Guest and external access with Microsoft Teams</span></span>

<span data-ttu-id="301fb-132">Microsoft Teams definiert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="301fb-132">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="301fb-133">**Gastzugriff** verwendet ein Azure AD B2B-Konto, das als Mitglied eines Teams hinzugefügt werden kann und über alle Berechtigungen für den Zugriff auf die Kommunikation und die Ressourcen des Teams verfügt.</span><span class="sxs-lookup"><span data-stu-id="301fb-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have all permissioned access to the communications and resources of the team.</span></span>

- <span data-ttu-id="301fb-134">**Externer Zugriff** ist für einen externen Benutzer, der über kein B2B-Konto verfügt.</span><span class="sxs-lookup"><span data-stu-id="301fb-134">**External access** is for an external user that does not have a B2B account.</span></span> <span data-ttu-id="301fb-135">Externer Zugriff kann Einladungen und Teilnahme an anrufen, Chats und Besprechungen umfassen, umfasst jedoch nicht die Teammitgliedschaft und den Zugriff auf die Ressourcen des Teams.</span><span class="sxs-lookup"><span data-stu-id="301fb-135">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="301fb-136">Weitere Informationen finden Sie unter [Vergleich zwischen Gast und externem Zugriff für Teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="301fb-136">For more information, see the [comparison between guest and external access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="301fb-137">Richtlinien für den bedingten Zugriff gelten nur für Gastzugriff in Microsoft Teams, da ein entsprechendes Azure AD B2B-Konto vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="301fb-137">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<span data-ttu-id="301fb-138">Weitere Informationen zum Sichern von Identitäts-und Gerätezugriffs Richtlinien für Teams finden Sie unter [Richtlinien Empfehlungen für das Sichern von teamchats, Gruppen und Dateien](teams-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="301fb-138">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access policies for Teams.</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="301fb-139">MFA immer für Gast und externe Benutzer erforderlich</span><span class="sxs-lookup"><span data-stu-id="301fb-139">Require MFA always for guest and external users</span></span>

<span data-ttu-id="301fb-140">Diese Richtlinie fordert Gäste auf, sich für MFA in Ihrem Mandanten zu registrieren, unabhängig davon, ob Sie für MFA in Ihrem Wohnsitz Mandanten registriert sind.</span><span class="sxs-lookup"><span data-stu-id="301fb-140">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="301fb-141">Beim Zugriff auf Ressourcen in Ihrem Mandanten müssen Gast-und externe Benutzer MFA für jede Anforderung verwenden.</span><span class="sxs-lookup"><span data-stu-id="301fb-141">When accessing resources in your tenant, guest and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="301fb-142">Ausschließen von Gast-und externen Benutzern aus risikobasierter MFA</span><span class="sxs-lookup"><span data-stu-id="301fb-142">Excluding guest and external users from risk-based MFA</span></span>

<span data-ttu-id="301fb-143">Während Organisationen risikobasierte Richtlinien für B2B-Benutzer mithilfe Azure AD Identitätsschutzes erzwingen können, gibt es Einschränkungen bei der Implementierung von Azure AD Identity Protection für Benutzer der B2B-Zusammenarbeit in einem Ressourcenverzeichnis, da ihre Identität in Ihrem Basisverzeichnis vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="301fb-143">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="301fb-144">Aufgrund dieser Einschränkungen empfiehlt Microsoft, Gastbenutzer von risikobasierten MFA-Richtlinien auszuschließen, und diese Benutzer müssen immer MFA verwenden.</span><span class="sxs-lookup"><span data-stu-id="301fb-144">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="301fb-145">Weitere Informationen finden Sie unter [Einschränkungen des Identitätsschutzes für Benutzer in der B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="301fb-145">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="301fb-146">Ausschließen von Gast-und externen Benutzern aus der Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="301fb-146">Excluding guest and external users from device management</span></span>

<span data-ttu-id="301fb-147">Nur eine Organisation kann ein Gerät verwalten.</span><span class="sxs-lookup"><span data-stu-id="301fb-147">Only one organization can manage a device.</span></span> <span data-ttu-id="301fb-148">Wenn Sie Gast-und externe Benutzer nicht von Richtlinien ausschließen, die die Gerätekompatibilität erfordern, werden diese Benutzer durch diese Richtlinien blockiert.</span><span class="sxs-lookup"><span data-stu-id="301fb-148">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="301fb-149">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="301fb-149">Next step</span></span>

![Schritt 4: Richtlinien für Microsoft 365 Cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="301fb-151">Konfigurieren von Richtlinien für bedingten Zugriff für:</span><span class="sxs-lookup"><span data-stu-id="301fb-151">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="301fb-152">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="301fb-152">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="301fb-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="301fb-153">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="301fb-154">SharePoint</span><span class="sxs-lookup"><span data-stu-id="301fb-154">SharePoint</span></span>](sharepoint-file-access-policies.md)
