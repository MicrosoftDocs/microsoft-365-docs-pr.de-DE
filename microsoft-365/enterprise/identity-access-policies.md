---
title: Allgemeine Identität und Gerät Zugriffsrichtlinien - Microsoft 365 Enterprise | Microsoft-Dokumente
description: Beschreibt die Richtlinien für Empfehlungen von Microsoft zur Anwendung von Identitäts- und Gerätezugriffsrichtlinien und -konfigurationen
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ab8454c27cd57b6bd5cc8df6e1526ee2950ac998
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868194"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="718d6-103">Allgemeine Identitäts- und Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="718d6-103">Common identity and device access policies</span></span>
<span data-ttu-id="718d6-104">Dieser Artikel beschreibt die allgemeine empfohlene Richtlinien für den sicheren Zugriff, um cloud-Dienste, einschließlich lokalen Applikationen mit Azure AD-Anwendungsproxy veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="718d6-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="718d6-p101">Diese Anleitung wird erläutert, wie die empfohlenen Richtlinien in einer neu bereitgestellte Umgebung bereitstellen. Diese Richtlinien in einer separaten Testlabor einrichten, können Sie verstehen und die empfohlenen Richtlinien vor die Einführung auf Ihren Umgebungen Vorproduktion und Produktion staging bewerten. Die neu bereitgestellte Umgebung ist möglicherweise nur-Cloud- oder Hybrid.</span><span class="sxs-lookup"><span data-stu-id="718d6-p101">This guidance discusses how to deploy the recommended policies in a newly-provisioned environment. Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your preproduction and production environments. Your newly provisioned environment may be cloud-only or hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="718d6-108">Richtlinie festlegen</span><span class="sxs-lookup"><span data-stu-id="718d6-108">Policy set</span></span> 

<span data-ttu-id="718d6-p102">Das folgende Diagramm veranschaulicht den empfohlenen Satz von Richtlinien. Es zeigt, welche Tier Schutzebenen jede Richtlinie gilt für und gibt an, ob die Richtlinien gelten für PCs oder Telefonen und Tablets oder beiden Kategorien von Geräten. Es gibt an, wobei diese Richtlinien konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="718d6-p102">The following diagram illustrates the recommended set of policies. It shows which tier of protections each policy applies to and whether the policies apply to PCs or phones and tablets, or both categories of devices. It also indicates where these policies are configured.</span></span>

![Allgemeine Richtlinien zum Konfigurieren des Zugriffs von Identität und Geräte](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="718d6-113">Der Rest dieses Artikels wird beschrieben, wie diese Richtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="718d6-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="718d6-p103">Verwenden die mehrstufige Authentifizierung wird empfohlen, vor der Geräte in Intune registrieren Assurance, die das Gerät im Besitz des gewünschten Benutzers ist. Sie müssen auch Geräte in Intune registrieren, bevor Kompatibilitätsrichtlinien Gerät erzwungen.</span><span class="sxs-lookup"><span data-stu-id="718d6-p103">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user. You must also enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="718d6-p104">So übergeben Sie die Zeit für diese Aufgaben, es wird empfohlen, die in dieser Tabelle aufgeführten Implementieren der Baseline-Richtlinien in der Reihenfolge. Mehrstufiger Authentifizierung das Richtlinien zum Schutz von vertraulichen und hochgradig regulierten können jedoch jederzeit implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="718d6-p104">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table. However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="718d6-118">Schutzebene</span><span class="sxs-lookup"><span data-stu-id="718d6-118">Protection level</span></span>|<span data-ttu-id="718d6-119">Policies</span><span class="sxs-lookup"><span data-stu-id="718d6-119">Policies</span></span>|<span data-ttu-id="718d6-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="718d6-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="718d6-121">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="718d6-121">**Baseline**</span></span>|[<span data-ttu-id="718d6-122">Erfordern Sie mehrstufiger Authentifizierung das, bei der Anmeldung Risiko *Mittel* oder *Hoch* ist</span><span class="sxs-lookup"><span data-stu-id="718d6-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="718d6-123">Blockierung von Clients, die moderne Authentifizierung nicht unterstützen</span><span class="sxs-lookup"><span data-stu-id="718d6-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="718d6-124">Clients, die nicht modernen Authentifizierung verwenden können bedingte Zugriffsregeln, umgehen, daher es wichtig ist, die Sie blockieren</span><span class="sxs-lookup"><span data-stu-id="718d6-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these</span></span>|
|        |[<span data-ttu-id="718d6-125">Hoch riskante Benutzer müssen Kennwort ändern.</span><span class="sxs-lookup"><span data-stu-id="718d6-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="718d6-126">Erzwingt, dass Benutzer ihr Kennwort ändern, bei der Anmeldung mit hohem Risiko Aktivität für ihr Konto festgestellt wird</span><span class="sxs-lookup"><span data-stu-id="718d6-126">Forces users to change their password when signing in if high-risk activity is detected for their account</span></span>|
|        |[<span data-ttu-id="718d6-127">Definieren von Richtlinien für die app-Schutz</span><span class="sxs-lookup"><span data-stu-id="718d6-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="718d6-128">Eine Richtlinie pro Plattform (iOS, Android, Windows).</span><span class="sxs-lookup"><span data-stu-id="718d6-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="718d6-129">Genehmigte apps erfordern</span><span class="sxs-lookup"><span data-stu-id="718d6-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="718d6-130">Erzwingt die mobile app Schutz für Mobiltelefone und tablets</span><span class="sxs-lookup"><span data-stu-id="718d6-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="718d6-131">Gerät Compliance-Richtlinien definieren</span><span class="sxs-lookup"><span data-stu-id="718d6-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="718d6-132">Eine Richtlinie für jede Plattform</span><span class="sxs-lookup"><span data-stu-id="718d6-132">One policy for each platform</span></span>|
|        |[<span data-ttu-id="718d6-133">Kompatible PCs erfordern</span><span class="sxs-lookup"><span data-stu-id="718d6-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="718d6-134">Erzwingt Intune Verwaltung von PCs</span><span class="sxs-lookup"><span data-stu-id="718d6-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="718d6-135">**Vertraulich**</span><span class="sxs-lookup"><span data-stu-id="718d6-135">**Sensitive**</span></span>|[<span data-ttu-id="718d6-136">Erfordern Sie mehrstufiger Authentifizierung das, bei der Anmeldung Risiko *Niedrig*, *Mittel* oder *Hoch* ist</span><span class="sxs-lookup"><span data-stu-id="718d6-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="718d6-137">Erfordern Sie kompatible PCs *und* mobile Geräten</span><span class="sxs-lookup"><span data-stu-id="718d6-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="718d6-138">Erzwingt Intune Management für PCs und Telefon-tablets</span><span class="sxs-lookup"><span data-stu-id="718d6-138">Enforces Intune management for PCs and phone/tablets</span></span>|
|<span data-ttu-id="718d6-139">**Streng geregelt**</span><span class="sxs-lookup"><span data-stu-id="718d6-139">**Highly regulated**</span></span>|[<span data-ttu-id="718d6-140">*Immer* erfordern mehrstufiger Authentifizierung das</span><span class="sxs-lookup"><span data-stu-id="718d6-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="718d6-141">Zuweisen von Richtlinien für Benutzer</span><span class="sxs-lookup"><span data-stu-id="718d6-141">Assigning policies to users</span></span>
<span data-ttu-id="718d6-p105">Identifizieren Sie vor dem Konfigurieren von Richtlinien, die Azure AD-Gruppen, die Sie für die einzelnen Ebenen des Schutzes verwenden. In der Regel gilt Baseline Schutz für alle Benutzer in der Organisation. Ein Benutzer, der für geplante und vertrauliche Protection enthalten ist müssen alle angewendeten geplante Richtlinien plus die vertraulichen Richtlinien. Schutz ist kumulativ und die restriktivste Richtlinie erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="718d6-p105">Before configuring policies, identify the Azure AD groups you are using for each tier of protection. Typically, baseline protection applies to everybody in the organization. A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies. Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="718d6-p106">Zum Erstellen einer Azure Active Directory-Gruppe für bedingten Zugriff Ausschluss wird eine empfohlen. Um alle Zugriffsregeln zur bedingten unter "Ausschließen" dieser Gruppe hinzuzufügen. Dadurch können Sie eine Methode, um den Zugriff für einen Benutzer bereitstellen, während Sie Access-Probleme zu beheben. Dies wird als eine Zwischenlösung nur empfohlen. Überwachen Sie diese Gruppe aus, damit die Änderungen, und achten Sie darauf, dass die Ausschlussgruppe nur wie vorgesehen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="718d6-p106">A recommended practice is to create an Azure AD group for conditional access exclusion. Add this group to all of your conditional access rules under "Exclude". This gives you a method to provide access to a user while you troubleshoot access issues. This is recommended as a temporary solution only. Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="718d6-151">Die folgende Abbildung enthält ein Beispiel von Benutzerrechten und Ausschlüsse.</span><span class="sxs-lookup"><span data-stu-id="718d6-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![Beispiel von Benutzerrechten und Ausschlüssen für mehrstufiger Authentifizierung das Regeln](../images/identity-access-policies-assignment.png)

<span data-ttu-id="718d6-p107">In der Abbildung ist das "oberen geheimen X Projektteam" eine bedingte Zugriffsrichtlinie zugewiesen, mehrstufiger Authentifizierung das *immer*müssen. Werden Sie zielgerichtete beim Anwenden von höherer Schutz auf Benutzer. Mitglieder dieser Projektteams müssen Sie zwei Arten der Authentifizierung jedes Mal, wenn sie Anmelden bereitstellen, auch wenn sie nicht sehr regulierter Inhalte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="718d6-p107">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*. Be judicious when applying higher levels of protection to users. Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly-regulated content.</span></span>  

<span data-ttu-id="718d6-p108">Alle Azure AD-Gruppen, die als Teil des diesen Empfehlungen erstellte müssen als Office 365-Gruppen erstellt werden. Dies ist insbesondere wichtig für die Bereitstellung von Azure Informationen Schutz (per), bei der Sicherung von Dokumenten in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="718d6-p108">All Azure AD groups created as part of these recommendations must be created as Office 365 groups. This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![Zum Erstellen von Gruppen für Office 365-Bildschirmaufnahme](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="718d6-159">Mehrstufiger Authentifizierung das basierend auf Risiko-Anmeldung erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="718d6-p109">Mehrstufiger Authentifizierung das werden müssen, zunächst mit dem eine Identität Protection mehrstufiger Authentifizierung das Registrierung Richtlinie Benutzer für mehrstufiger Authentifizierung das registrieren. Nachdem der Benutzer registriert sind, können Sie mehrstufiger Authentifizierung das für die Anmeldung erzwingen. Die [erforderliche Arbeit](identity-access-prerequisites.md) enthält, allen Benutzern mit mehrstufiger Authentifizierung das registrieren.</span><span class="sxs-lookup"><span data-stu-id="718d6-p109">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA. After users are registered you can enforce MFA for sign-in. The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="718d6-163">So erstellen Sie eine neue bedingte Zugriffsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="718d6-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="718d6-p110">Wechseln Sie zu der [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen. Nachdem Sie sich erfolgreich angemeldet haben, sehen Sie das Dashboard Azure.</span><span class="sxs-lookup"><span data-stu-id="718d6-p110">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="718d6-166">Wählen Sie im linken Menü **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="718d6-167">Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="718d6-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="718d6-168">Wählen Sie **Neue Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-168">Choose **New policy**.</span></span>

![Grundlegende Richtlinie für bedingten Zugriff](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="718d6-170">In den folgenden Tabellen werden die bedingten Zugriff Richtlinieneinstellungen für diese Richtlinie implementieren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="718d6-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="718d6-171">**Zuweisungen**</span><span class="sxs-lookup"><span data-stu-id="718d6-171">**Assignments**</span></span>

|<span data-ttu-id="718d6-172">Typ</span><span class="sxs-lookup"><span data-stu-id="718d6-172">Type</span></span>|<span data-ttu-id="718d6-173">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="718d6-173">Properties</span></span>|<span data-ttu-id="718d6-174">Werte</span><span class="sxs-lookup"><span data-stu-id="718d6-174">Values</span></span>|<span data-ttu-id="718d6-175">Hinweise</span><span class="sxs-lookup"><span data-stu-id="718d6-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="718d6-176">Benutzer und Gruppen</span><span class="sxs-lookup"><span data-stu-id="718d6-176">Users and groups</span></span>|<span data-ttu-id="718d6-177">Einschließen</span><span class="sxs-lookup"><span data-stu-id="718d6-177">Include</span></span>|<span data-ttu-id="718d6-178">Wählen Sie Benutzer und Gruppen aus: Wählen Sie eine spezifische Sicherheitsgruppe aus, die Zielbenutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="718d6-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="718d6-179">Beginnen Sie mit der Sicherheitsgruppe einschließlich Pilotbenutzer</span><span class="sxs-lookup"><span data-stu-id="718d6-179">Start with security group including pilot users</span></span>|
||<span data-ttu-id="718d6-180">Ausschließen</span><span class="sxs-lookup"><span data-stu-id="718d6-180">Exclude</span></span>|<span data-ttu-id="718d6-181">Ausnahmesicherheitsgruppe, Dienstkonten (App-Identitäten)</span><span class="sxs-lookup"><span data-stu-id="718d6-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="718d6-182">Die Mitgliedschaft bei Bedarf temporäre regelmäßig geändert</span><span class="sxs-lookup"><span data-stu-id="718d6-182">Membership modified on an as-needed temporary basis</span></span>|
|<span data-ttu-id="718d6-183">Cloud-Apps</span><span class="sxs-lookup"><span data-stu-id="718d6-183">Cloud apps</span></span>|<span data-ttu-id="718d6-184">Einschließen</span><span class="sxs-lookup"><span data-stu-id="718d6-184">Include</span></span>|<span data-ttu-id="718d6-p111">Wählen Sie die apps, die diese Regel angewendet werden soll. Wählen Sie zum Beispiel auf Office 365 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="718d6-p111">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="718d6-187">Bedingungen</span><span class="sxs-lookup"><span data-stu-id="718d6-187">Conditions</span></span>|<span data-ttu-id="718d6-188">Konfigurierte</span><span class="sxs-lookup"><span data-stu-id="718d6-188">Configured</span></span>|<span data-ttu-id="718d6-189">Ja</span><span class="sxs-lookup"><span data-stu-id="718d6-189">Yes</span></span>|<span data-ttu-id="718d6-190">Konfigurieren Sie speziell für Ihre Umgebung und Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="718d6-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="718d6-191">Anmelderisiko</span><span class="sxs-lookup"><span data-stu-id="718d6-191">Sign-in risk</span></span>|<span data-ttu-id="718d6-192">Risikostufe</span><span class="sxs-lookup"><span data-stu-id="718d6-192">Risk level</span></span>||<span data-ttu-id="718d6-193">Finden Sie unter der Anleitung in der folgenden Tabelle</span><span class="sxs-lookup"><span data-stu-id="718d6-193">See the guidance in the following table</span></span>|

<span data-ttu-id="718d6-194">**Anmelderisiko**</span><span class="sxs-lookup"><span data-stu-id="718d6-194">**Sign-in risk**</span></span>

<span data-ttu-id="718d6-195">Wenden Sie die Einstellungen, die basierend auf der Mail-Schutzstufe, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="718d6-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="718d6-196">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="718d6-196">Property</span></span>|<span data-ttu-id="718d6-197">Schutzebene</span><span class="sxs-lookup"><span data-stu-id="718d6-197">Level of protection</span></span>|<span data-ttu-id="718d6-198">Werte</span><span class="sxs-lookup"><span data-stu-id="718d6-198">Values</span></span>|<span data-ttu-id="718d6-199">Hinweise</span><span class="sxs-lookup"><span data-stu-id="718d6-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="718d6-200">Risikostufe</span><span class="sxs-lookup"><span data-stu-id="718d6-200">Risk level</span></span>|<span data-ttu-id="718d6-201">Baseline</span><span class="sxs-lookup"><span data-stu-id="718d6-201">Baseline</span></span>|<span data-ttu-id="718d6-202">Hoch, Mmittel</span><span class="sxs-lookup"><span data-stu-id="718d6-202">High, medium</span></span>|<span data-ttu-id="718d6-203">Aktivieren Sie beide</span><span class="sxs-lookup"><span data-stu-id="718d6-203">Check both</span></span>|
| |<span data-ttu-id="718d6-204">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="718d6-204">Sensitive</span></span>|<span data-ttu-id="718d6-205">Hoch, Mittel, Niedrig</span><span class="sxs-lookup"><span data-stu-id="718d6-205">High, medium, low</span></span>|<span data-ttu-id="718d6-206">Alle drei aktivieren</span><span class="sxs-lookup"><span data-stu-id="718d6-206">Check all three</span></span>|
| |<span data-ttu-id="718d6-207">Streng geregelt</span><span class="sxs-lookup"><span data-stu-id="718d6-207">Highly regulated</span></span>| |<span data-ttu-id="718d6-208">Lassen Sie alle Optionen deaktiviert, um immer mehrstufiger Authentifizierung das erzwingen</span><span class="sxs-lookup"><span data-stu-id="718d6-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="718d6-209">**Zugriffssteuerung**</span><span class="sxs-lookup"><span data-stu-id="718d6-209">**Access controls**</span></span>

|<span data-ttu-id="718d6-210">Typ</span><span class="sxs-lookup"><span data-stu-id="718d6-210">Type</span></span>|<span data-ttu-id="718d6-211">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="718d6-211">Properties</span></span>|<span data-ttu-id="718d6-212">Werte</span><span class="sxs-lookup"><span data-stu-id="718d6-212">Values</span></span>|<span data-ttu-id="718d6-213">Hinweise</span><span class="sxs-lookup"><span data-stu-id="718d6-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="718d6-214">Gewähren</span><span class="sxs-lookup"><span data-stu-id="718d6-214">Grant</span></span>|<span data-ttu-id="718d6-215">Gewähren von Zugriff</span><span class="sxs-lookup"><span data-stu-id="718d6-215">Grant access</span></span>|<span data-ttu-id="718d6-216">True</span><span class="sxs-lookup"><span data-stu-id="718d6-216">True</span></span>|<span data-ttu-id="718d6-217">Ausgewählt</span><span class="sxs-lookup"><span data-stu-id="718d6-217">Selected</span></span>|
||<span data-ttu-id="718d6-218">MFA erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-218">Require MFA</span></span>|<span data-ttu-id="718d6-219">True</span><span class="sxs-lookup"><span data-stu-id="718d6-219">True</span></span>|<span data-ttu-id="718d6-220">Check</span><span class="sxs-lookup"><span data-stu-id="718d6-220">Check</span></span>|
||<span data-ttu-id="718d6-221">Müssen Sie Gerät als kompatibel markiert werden</span><span class="sxs-lookup"><span data-stu-id="718d6-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="718d6-222">False</span><span class="sxs-lookup"><span data-stu-id="718d6-222">False</span></span>||
||<span data-ttu-id="718d6-223">Hybride Azure AD gehörenden Gerät erfordern</span><span class="sxs-lookup"><span data-stu-id="718d6-223">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="718d6-224">False</span><span class="sxs-lookup"><span data-stu-id="718d6-224">False</span></span>||
||<span data-ttu-id="718d6-225">Genehmigte Client-app erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-225">Require approved client app</span></span>|<span data-ttu-id="718d6-226">False</span><span class="sxs-lookup"><span data-stu-id="718d6-226">False</span></span>||
||<span data-ttu-id="718d6-227">Alle ausgewählten Steuerelemente erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-227">Require all the selected controls</span></span>|<span data-ttu-id="718d6-228">True</span><span class="sxs-lookup"><span data-stu-id="718d6-228">True</span></span>|<span data-ttu-id="718d6-229">Ausgewählt</span><span class="sxs-lookup"><span data-stu-id="718d6-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="718d6-p112">Achten Sie darauf, dass Sie diese Richtlinie aktivieren, indem Sie **auf**auswählen. Sollten Sie auch mithilfe des Tools [Was passiert, wenn](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) um die Richtlinie zu testen.</span><span class="sxs-lookup"><span data-stu-id="718d6-p112">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="718d6-232">Blockierung von Clients, die moderne Authentifizierung nicht unterstützen</span><span class="sxs-lookup"><span data-stu-id="718d6-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="718d6-p113">Wechseln Sie zu der [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen. Nachdem Sie sich erfolgreich angemeldet haben, sehen Sie das Dashboard Azure.</span><span class="sxs-lookup"><span data-stu-id="718d6-p113">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="718d6-235">Wählen Sie im linken Menü **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="718d6-236">Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="718d6-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="718d6-237">Wählen Sie **Neue Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-237">Choose **New policy**.</span></span>

<span data-ttu-id="718d6-238">In den folgenden Tabellen werden die bedingten Zugriff Richtlinieneinstellungen für diese Richtlinie implementieren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="718d6-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="718d6-239">**Zuweisungen**</span><span class="sxs-lookup"><span data-stu-id="718d6-239">**Assignments**</span></span>

|<span data-ttu-id="718d6-240">Typ</span><span class="sxs-lookup"><span data-stu-id="718d6-240">Type</span></span>|<span data-ttu-id="718d6-241">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="718d6-241">Properties</span></span>|<span data-ttu-id="718d6-242">Werte</span><span class="sxs-lookup"><span data-stu-id="718d6-242">Values</span></span>|<span data-ttu-id="718d6-243">Hinweise</span><span class="sxs-lookup"><span data-stu-id="718d6-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="718d6-244">Benutzer und Gruppen</span><span class="sxs-lookup"><span data-stu-id="718d6-244">Users and groups</span></span>|<span data-ttu-id="718d6-245">Einschließen</span><span class="sxs-lookup"><span data-stu-id="718d6-245">Include</span></span>|<span data-ttu-id="718d6-246">Wählen Sie Benutzer und Gruppen aus: Wählen Sie eine spezifische Sicherheitsgruppe aus, die Zielbenutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="718d6-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="718d6-247">Beginnen Sie mit der Sicherheitsgruppe einschließlich Pilotbenutzer</span><span class="sxs-lookup"><span data-stu-id="718d6-247">Start with security group including pilot users</span></span>|
||<span data-ttu-id="718d6-248">Ausschließen</span><span class="sxs-lookup"><span data-stu-id="718d6-248">Exclude</span></span>|<span data-ttu-id="718d6-249">Ausnahmesicherheitsgruppe, Dienstkonten (App-Identitäten)</span><span class="sxs-lookup"><span data-stu-id="718d6-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="718d6-250">Mitgliedschaft, die auf vorübergehender, bedarfsmäßiger Basis geändert wird</span><span class="sxs-lookup"><span data-stu-id="718d6-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="718d6-251">Cloud-Apps</span><span class="sxs-lookup"><span data-stu-id="718d6-251">Cloud apps</span></span>|<span data-ttu-id="718d6-252">Einschließen</span><span class="sxs-lookup"><span data-stu-id="718d6-252">Include</span></span>|<span data-ttu-id="718d6-p114">Wählen Sie die apps, die diese Regel angewendet werden soll. Wählen Sie zum Beispiel auf Office 365 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="718d6-p114">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="718d6-255">Bedingungen</span><span class="sxs-lookup"><span data-stu-id="718d6-255">Conditions</span></span>|<span data-ttu-id="718d6-256">Konfigurierte</span><span class="sxs-lookup"><span data-stu-id="718d6-256">Configured</span></span>|<span data-ttu-id="718d6-257">Ja</span><span class="sxs-lookup"><span data-stu-id="718d6-257">Yes</span></span>|<span data-ttu-id="718d6-258">Konfigurieren von Client-apps</span><span class="sxs-lookup"><span data-stu-id="718d6-258">Configure Client apps</span></span>|
|<span data-ttu-id="718d6-259">Client-apps</span><span class="sxs-lookup"><span data-stu-id="718d6-259">Client apps</span></span>|<span data-ttu-id="718d6-260">Konfigurierte</span><span class="sxs-lookup"><span data-stu-id="718d6-260">Configured</span></span>|<span data-ttu-id="718d6-261">Ja</span><span class="sxs-lookup"><span data-stu-id="718d6-261">Yes</span></span>|<span data-ttu-id="718d6-262">Mobile apps und Desktopclients, andere Clients (Wählen Sie beide)</span><span class="sxs-lookup"><span data-stu-id="718d6-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="718d6-263">**Zugriffssteuerung**</span><span class="sxs-lookup"><span data-stu-id="718d6-263">**Access controls**</span></span>

|<span data-ttu-id="718d6-264">Typ</span><span class="sxs-lookup"><span data-stu-id="718d6-264">Type</span></span>|<span data-ttu-id="718d6-265">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="718d6-265">Properties</span></span>|<span data-ttu-id="718d6-266">Werte</span><span class="sxs-lookup"><span data-stu-id="718d6-266">Values</span></span>|<span data-ttu-id="718d6-267">Hinweise</span><span class="sxs-lookup"><span data-stu-id="718d6-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="718d6-268">Gewähren</span><span class="sxs-lookup"><span data-stu-id="718d6-268">Grant</span></span>|<span data-ttu-id="718d6-269">Zugriff blockieren</span><span class="sxs-lookup"><span data-stu-id="718d6-269">Block access</span></span>|<span data-ttu-id="718d6-270">True</span><span class="sxs-lookup"><span data-stu-id="718d6-270">True</span></span>|<span data-ttu-id="718d6-271">Ausgewählt</span><span class="sxs-lookup"><span data-stu-id="718d6-271">Selected</span></span>|
||<span data-ttu-id="718d6-272">MFA erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-272">Require MFA</span></span>|<span data-ttu-id="718d6-273">False</span><span class="sxs-lookup"><span data-stu-id="718d6-273">False</span></span>||
||<span data-ttu-id="718d6-274">Müssen Sie Gerät als kompatibel markiert werden</span><span class="sxs-lookup"><span data-stu-id="718d6-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="718d6-275">False</span><span class="sxs-lookup"><span data-stu-id="718d6-275">False</span></span>||
||<span data-ttu-id="718d6-276">Hybride Azure AD gehörenden Gerät erfordern</span><span class="sxs-lookup"><span data-stu-id="718d6-276">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="718d6-277">False</span><span class="sxs-lookup"><span data-stu-id="718d6-277">False</span></span>||
||<span data-ttu-id="718d6-278">Genehmigte Client-app erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-278">Require approved client app</span></span>|<span data-ttu-id="718d6-279">False</span><span class="sxs-lookup"><span data-stu-id="718d6-279">False</span></span>||
||<span data-ttu-id="718d6-280">Alle ausgewählten Steuerelemente erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-280">Require all the selected controls</span></span>|<span data-ttu-id="718d6-281">True</span><span class="sxs-lookup"><span data-stu-id="718d6-281">True</span></span>|<span data-ttu-id="718d6-282">Ausgewählt</span><span class="sxs-lookup"><span data-stu-id="718d6-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="718d6-p115">Achten Sie darauf, dass Sie diese Richtlinie aktivieren, indem Sie **auf**auswählen. Sollten Sie auch mithilfe des Tools [Was passiert, wenn](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) um die Richtlinie zu testen.</span><span class="sxs-lookup"><span data-stu-id="718d6-p115">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="718d6-285">Hoch riskante Benutzer müssen Kennwort ändern.</span><span class="sxs-lookup"><span data-stu-id="718d6-285">High risk users must change password</span></span>
<span data-ttu-id="718d6-286">Um sicherzustellen, dass alle mit hohem Risiko kompromittierten Benutzerkonten werden gezwungen, beim Anmelden bei eine Änderung des Kennworts ausgeführt, müssen Sie die folgende Richtlinie anwenden.</span><span class="sxs-lookup"><span data-stu-id="718d6-286">To ensure that all high-risk users' compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="718d6-287">Melden Sie sich bei der [Microsoft Azure-Portal (http://portal.azure.com) ](http://portal.azure.com/) mit Ihren Administratoranmeldeinformationen, und navigieren Sie zu **Azure AD-Schutz > Risiko Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="718d6-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="718d6-288">**Zuweisungen**</span><span class="sxs-lookup"><span data-stu-id="718d6-288">**Assignments**</span></span>

|<span data-ttu-id="718d6-289">Typ</span><span class="sxs-lookup"><span data-stu-id="718d6-289">Type</span></span>|<span data-ttu-id="718d6-290">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="718d6-290">Properties</span></span>|<span data-ttu-id="718d6-291">Werte</span><span class="sxs-lookup"><span data-stu-id="718d6-291">Values</span></span>|<span data-ttu-id="718d6-292">Hinweise</span><span class="sxs-lookup"><span data-stu-id="718d6-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="718d6-293">Users</span><span class="sxs-lookup"><span data-stu-id="718d6-293">Users</span></span>|<span data-ttu-id="718d6-294">Einschließen</span><span class="sxs-lookup"><span data-stu-id="718d6-294">Include</span></span>|<span data-ttu-id="718d6-295">Alle Benutzer</span><span class="sxs-lookup"><span data-stu-id="718d6-295">All users</span></span>|<span data-ttu-id="718d6-296">Ausgewählt</span><span class="sxs-lookup"><span data-stu-id="718d6-296">Selected</span></span>|
||<span data-ttu-id="718d6-297">Ausschließen</span><span class="sxs-lookup"><span data-stu-id="718d6-297">Exclude</span></span>|<span data-ttu-id="718d6-298">Keine</span><span class="sxs-lookup"><span data-stu-id="718d6-298">None</span></span>||
|<span data-ttu-id="718d6-299">Bedingungen</span><span class="sxs-lookup"><span data-stu-id="718d6-299">Conditions</span></span>|<span data-ttu-id="718d6-300">Benutzerrisiko</span><span class="sxs-lookup"><span data-stu-id="718d6-300">User risk</span></span>|<span data-ttu-id="718d6-301">Hoch</span><span class="sxs-lookup"><span data-stu-id="718d6-301">High</span></span>|<span data-ttu-id="718d6-302">Ausgewählt</span><span class="sxs-lookup"><span data-stu-id="718d6-302">Selected</span></span>|

<span data-ttu-id="718d6-303">**Steuerelemente**</span><span class="sxs-lookup"><span data-stu-id="718d6-303">**Controls**</span></span>

| <span data-ttu-id="718d6-304">Typ</span><span class="sxs-lookup"><span data-stu-id="718d6-304">Type</span></span> | <span data-ttu-id="718d6-305">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="718d6-305">Properties</span></span> | <span data-ttu-id="718d6-306">Werte</span><span class="sxs-lookup"><span data-stu-id="718d6-306">Values</span></span>                  | <span data-ttu-id="718d6-307">Hinweise</span><span class="sxs-lookup"><span data-stu-id="718d6-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="718d6-308">Zugriff</span><span class="sxs-lookup"><span data-stu-id="718d6-308">Access</span></span>     | <span data-ttu-id="718d6-309">Zugriff zulassen</span><span class="sxs-lookup"><span data-stu-id="718d6-309">Allow access</span></span>            | <span data-ttu-id="718d6-310">True</span><span class="sxs-lookup"><span data-stu-id="718d6-310">True</span></span>  |
|      | <span data-ttu-id="718d6-311">Zugriff</span><span class="sxs-lookup"><span data-stu-id="718d6-311">Access</span></span>     | <span data-ttu-id="718d6-312">Kennwortänderung erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-312">Require password change</span></span> | <span data-ttu-id="718d6-313">True</span><span class="sxs-lookup"><span data-stu-id="718d6-313">True</span></span>  |

<span data-ttu-id="718d6-314">**Überprüfen:** nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="718d6-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="718d6-p116">Achten Sie darauf, dass Sie diese Richtlinie aktivieren, indem Sie **auf**auswählen. Berücksichtigen Sie auch mit dem Tool [Was passiert, wenn](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) die Richtlinie testen</span><span class="sxs-lookup"><span data-stu-id="718d6-p116">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="718d6-317">Definieren von Richtlinien für die app-Schutz</span><span class="sxs-lookup"><span data-stu-id="718d6-317">Define app protection policies</span></span>
<span data-ttu-id="718d6-p117">App-Richtlinien definieren, welche apps zulässig sind, und die Aktionen, die sie mit Ihrer Organisation Daten ausführen können. Erstellen Sie Intune app Protection-Richtlinien aus der Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="718d6-p117">App protection policies define which apps are allowed and the actions they can take with your organization's data. Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="718d6-320">Erstellen Sie eine Richtlinie für jede Plattform:</span><span class="sxs-lookup"><span data-stu-id="718d6-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="718d6-321">iOS</span><span class="sxs-lookup"><span data-stu-id="718d6-321">iOS</span></span>
- <span data-ttu-id="718d6-322">Android</span><span class="sxs-lookup"><span data-stu-id="718d6-322">Android</span></span>
- <span data-ttu-id="718d6-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="718d6-323">Windows 10</span></span>

<span data-ttu-id="718d6-p118">Um eine neue app-Schutz-Richtlinie zu erstellen, melden Sie sich an das Microsoft Azure-Portal mit Ihren Anmeldeinformationen verwalten, und navigieren Sie zu **mobiler apps > Richtlinien für die App Protection**. Wählen Sie **eine Richtlinie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="718d6-p118">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**. Choose **Add a policy**.</span></span>

<span data-ttu-id="718d6-p119">Es gibt leichte Unterschiede in der app-Schutz Richtlinienoptionen zwischen iOS und Android. Die unter Richtlinie bezieht sich speziell auf Android. Verwenden Sie dies als Leitfaden für die anderen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="718d6-p119">There are slight differences in the app protection policy options between iOS and Android. The below policy is specifically for Android. Use this as a guide for your other policies.</span></span>

<span data-ttu-id="718d6-329">Die empfohlene Liste apps umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="718d6-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="718d6-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="718d6-330">PowerPoint</span></span>
- <span data-ttu-id="718d6-331">Excel</span><span class="sxs-lookup"><span data-stu-id="718d6-331">Excel</span></span>
- <span data-ttu-id="718d6-332">Word</span><span class="sxs-lookup"><span data-stu-id="718d6-332">Word</span></span>
- <span data-ttu-id="718d6-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="718d6-333">Microsoft Teams</span></span>
- <span data-ttu-id="718d6-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="718d6-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="718d6-335">Microsoft Visio Viewer</span><span class="sxs-lookup"><span data-stu-id="718d6-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="718d6-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="718d6-336">OneDrive</span></span>
- <span data-ttu-id="718d6-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="718d6-337">OneNote</span></span>
- <span data-ttu-id="718d6-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="718d6-338">Outlook</span></span>

<span data-ttu-id="718d6-339">In den folgenden Tabellen werden die empfohlenen Einstellungen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="718d6-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="718d6-340">Typ</span><span class="sxs-lookup"><span data-stu-id="718d6-340">Type</span></span>|<span data-ttu-id="718d6-341">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="718d6-341">Properties</span></span>|<span data-ttu-id="718d6-342">Werte</span><span class="sxs-lookup"><span data-stu-id="718d6-342">Values</span></span>|<span data-ttu-id="718d6-343">Hinweise</span><span class="sxs-lookup"><span data-stu-id="718d6-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="718d6-344">Datenverschiebung</span><span class="sxs-lookup"><span data-stu-id="718d6-344">Data relocation</span></span>|<span data-ttu-id="718d6-345">Android-Sicherungen verhindern</span><span class="sxs-lookup"><span data-stu-id="718d6-345">Prevent Android backup</span></span>|<span data-ttu-id="718d6-346">Ja</span><span class="sxs-lookup"><span data-stu-id="718d6-346">Yes</span></span>|<span data-ttu-id="718d6-347">Auf iOS wird dies insbesondere iTunes und iCloud aufrufen.</span><span class="sxs-lookup"><span data-stu-id="718d6-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="718d6-348">App Übertragung von Daten an andere Apps erlauben</span><span class="sxs-lookup"><span data-stu-id="718d6-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="718d6-349">Richtlinienverwaltete Apps</span><span class="sxs-lookup"><span data-stu-id="718d6-349">Policy managed apps</span></span>||
||<span data-ttu-id="718d6-350">Zulassen, dass die App Daten von anderen Apps empfängt</span><span class="sxs-lookup"><span data-stu-id="718d6-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="718d6-351">Richtlinienverwaltete Apps</span><span class="sxs-lookup"><span data-stu-id="718d6-351">Policy managed apps</span></span>||
||<span data-ttu-id="718d6-352">"Speichern unter" verhindern</span><span class="sxs-lookup"><span data-stu-id="718d6-352">Prevent "Save As"</span></span>|<span data-ttu-id="718d6-353">Ja</span><span class="sxs-lookup"><span data-stu-id="718d6-353">Yes</span></span>||
||<span data-ttu-id="718d6-354">Speicherdienste zum Speichern von Unternehmensdaten auswählen</span><span class="sxs-lookup"><span data-stu-id="718d6-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="718d6-355">OneDrive für Unternehmen, SharePoint</span><span class="sxs-lookup"><span data-stu-id="718d6-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="718d6-356">Ausschneiden, Kopieren und Einfügen mit anderen Apps einschränken</span><span class="sxs-lookup"><span data-stu-id="718d6-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="718d6-357">Richtlinie verwaltet apps mit Einfügen in</span><span class="sxs-lookup"><span data-stu-id="718d6-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="718d6-358">Anzeige von Webinhalten auf den Managed Browser beschränken</span><span class="sxs-lookup"><span data-stu-id="718d6-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="718d6-359">Nein</span><span class="sxs-lookup"><span data-stu-id="718d6-359">No</span></span>||
||<span data-ttu-id="718d6-360">App-Daten verschlüsseln</span><span class="sxs-lookup"><span data-stu-id="718d6-360">Encrypt app data</span></span>|<span data-ttu-id="718d6-361">Ja</span><span class="sxs-lookup"><span data-stu-id="718d6-361">Yes</span></span>|<span data-ttu-id="718d6-362">Wählen Sie bei iOS diese Option aus: Wenn das Gerät gesperrt ist.</span><span class="sxs-lookup"><span data-stu-id="718d6-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="718d6-363">Deaktivieren der app-Verschlüsselung beim Gerät aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="718d6-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="718d6-364">Ja</span><span class="sxs-lookup"><span data-stu-id="718d6-364">Yes</span></span>|<span data-ttu-id="718d6-365">Deaktivieren Sie diese Einstellung, um doppelte Verschlüsselung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="718d6-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="718d6-366">Kontaktsynchronisierung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="718d6-366">Disable contacts sync</span></span>|<span data-ttu-id="718d6-367">Nein</span><span class="sxs-lookup"><span data-stu-id="718d6-367">No</span></span>||
||<span data-ttu-id="718d6-368">Deaktivieren von ausdrucken</span><span class="sxs-lookup"><span data-stu-id="718d6-368">Disable printing</span></span>|<span data-ttu-id="718d6-369">Nein</span><span class="sxs-lookup"><span data-stu-id="718d6-369">No</span></span>||
|<span data-ttu-id="718d6-370">Zugriff</span><span class="sxs-lookup"><span data-stu-id="718d6-370">Access</span></span>|<span data-ttu-id="718d6-371">PIN für Zugriff anfordern</span><span class="sxs-lookup"><span data-stu-id="718d6-371">Require PIN for access</span></span>|<span data-ttu-id="718d6-372">Ja</span><span class="sxs-lookup"><span data-stu-id="718d6-372">Yes</span></span>||
||<span data-ttu-id="718d6-373">Wählen Sie</span><span class="sxs-lookup"><span data-stu-id="718d6-373">Select Type</span></span>|<span data-ttu-id="718d6-374">Numerische</span><span class="sxs-lookup"><span data-stu-id="718d6-374">Numeric</span></span>||
||<span data-ttu-id="718d6-375">Einfache PIN zulassen</span><span class="sxs-lookup"><span data-stu-id="718d6-375">Allow simple PIN</span></span>|<span data-ttu-id="718d6-376">Nein</span><span class="sxs-lookup"><span data-stu-id="718d6-376">No</span></span>||
||<span data-ttu-id="718d6-377">PIN-Länge</span><span class="sxs-lookup"><span data-stu-id="718d6-377">PIN length</span></span>|<span data-ttu-id="718d6-378">6</span><span class="sxs-lookup"><span data-stu-id="718d6-378">6</span></span>||
||<span data-ttu-id="718d6-379">Fingerabdruck anstelle von PIN zulassen</span><span class="sxs-lookup"><span data-stu-id="718d6-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="718d6-380">Ja</span><span class="sxs-lookup"><span data-stu-id="718d6-380">Yes</span></span>||
||<span data-ttu-id="718d6-381">Deaktivieren der app PIN, Geräte-ID verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="718d6-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="718d6-382">Ja</span><span class="sxs-lookup"><span data-stu-id="718d6-382">Yes</span></span>||
||<span data-ttu-id="718d6-383">Erfordern des Unternehmensanmeldeinformationen für access</span><span class="sxs-lookup"><span data-stu-id="718d6-383">Require corporate credentials for access</span></span>|<span data-ttu-id="718d6-384">Nein</span><span class="sxs-lookup"><span data-stu-id="718d6-384">No</span></span>||
||<span data-ttu-id="718d6-385">Erneutes Überprüfen der Zugriffsanforderung nach (Minuten)</span><span class="sxs-lookup"><span data-stu-id="718d6-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="718d6-386">30</span><span class="sxs-lookup"><span data-stu-id="718d6-386">30</span></span>||
||<span data-ttu-id="718d6-387">Bildschirmaufnahme und Android-Assistenten blockieren</span><span class="sxs-lookup"><span data-stu-id="718d6-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="718d6-388">Nein</span><span class="sxs-lookup"><span data-stu-id="718d6-388">No</span></span>|<span data-ttu-id="718d6-389">Bei iOS ist diese Option nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="718d6-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="718d6-390">Anmeldung sicherheitsanforderungen</span><span class="sxs-lookup"><span data-stu-id="718d6-390">Sign-in security requirements</span></span>|<span data-ttu-id="718d6-391">Max-PIN versucht</span><span class="sxs-lookup"><span data-stu-id="718d6-391">Max PIN attempts</span></span>|<span data-ttu-id="718d6-392">5</span><span class="sxs-lookup"><span data-stu-id="718d6-392">5</span></span>|<span data-ttu-id="718d6-393">Pin zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="718d6-393">Reset Pin</span></span>|
||<span data-ttu-id="718d6-394">Offline-Toleranzperiode</span><span class="sxs-lookup"><span data-stu-id="718d6-394">Offline grace period</span></span>|<span data-ttu-id="718d6-395">720</span><span class="sxs-lookup"><span data-stu-id="718d6-395">720</span></span>|<span data-ttu-id="718d6-396">Zugriff blockieren</span><span class="sxs-lookup"><span data-stu-id="718d6-396">Block access</span></span>|
||<span data-ttu-id="718d6-397">Offline-Intervall (in Tagen), bevor App-Daten zurückgesetzt werden</span><span class="sxs-lookup"><span data-stu-id="718d6-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="718d6-398">90</span><span class="sxs-lookup"><span data-stu-id="718d6-398">90</span></span>|<span data-ttu-id="718d6-399">Daten löschen</span><span class="sxs-lookup"><span data-stu-id="718d6-399">Wipe data</span></span>|
||<span data-ttu-id="718d6-400">Jailbroken/Stamm Geräte</span><span class="sxs-lookup"><span data-stu-id="718d6-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="718d6-401">Daten löschen</span><span class="sxs-lookup"><span data-stu-id="718d6-401">Wipe data</span></span>|

<span data-ttu-id="718d6-p120">Nach Abschluss des Vorgangs, denken Sie daran, wählen Sie "Erstellen". Wiederholen Sie die oben genannten Schritte aus, und Ersetzen Sie die ausgewählte Plattform (Dropdown) durch iOS. Dies erstellt zwei Richtlinien für die app daher, nach dem Erstellen der Richtlinie dann Zuweisen von Gruppen für die Richtlinie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="718d6-p120">When complete, remember to select "Create". Repeat the above steps and replace the selected platform (dropdown) with iOS. This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="718d6-405">Zum Bearbeiten der Richtlinien und diese Richtlinien Benutzern zuweisen, finden Sie unter [Erstellen und Zuweisen von Richtlinien für die app Schutz](https://docs.microsoft.com/intune/app-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="718d6-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="718d6-406">Genehmigte apps erfordern</span><span class="sxs-lookup"><span data-stu-id="718d6-406">Require approved apps</span></span>
<span data-ttu-id="718d6-407">Genehmigte apps erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="718d6-407">To require approved apps:</span></span>

1. <span data-ttu-id="718d6-p121">Wechseln Sie zu der [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen. Nachdem Sie sich erfolgreich angemeldet haben, sehen Sie das Dashboard Azure.</span><span class="sxs-lookup"><span data-stu-id="718d6-p121">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="718d6-410">Wählen Sie im linken Menü **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="718d6-411">Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="718d6-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="718d6-412">Wählen Sie **Neue Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="718d6-413">Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="718d6-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="718d6-414">Klicken Sie auf **Cloud-Apps**.</span><span class="sxs-lookup"><span data-stu-id="718d6-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="718d6-p122">Wählen Sie **apps auswählen**, wählen Sie die gewünschten apps aus der Liste der **Cloud-apps** . Wählen Sie beispielsweise Office 365 Exchange Online. Die Option **auswählen** und **durchgeführt**.</span><span class="sxs-lookup"><span data-stu-id="718d6-p122">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="718d6-418">Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-418">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="718d6-p123">Wählen Sie **Zugriff gewähren**, wählen Sie **Client-app genehmigt erforderlich**. Wählen Sie für mehrere Steuerelemente **die ausgewählten Steuerelemente erforderlich**, und klicken Sie dann **auf auswählen**.</span><span class="sxs-lookup"><span data-stu-id="718d6-p123">Choose **Grant access**, select **Require approved client app**. For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="718d6-421">Wählen Sie **Create** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-421">Choose **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="718d6-422">Definieren von Richtlinien für die Geräte-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="718d6-422">Define device-compliance policies</span></span>

<span data-ttu-id="718d6-p124">Gerät-Kompatibilitätsrichtlinien definieren die Anforderungen, denen Geräte einhalten müssen, um als kompatibel markiert werden. Erstellen Sie Intune Gerät Kompatibilitätsrichtlinien im Azure-Portal aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-p124">Device-compliance policies define the requirements that devices must adhere to in order to be marked as compliant. Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="718d6-425">Erstellen Sie eine Richtlinie für jede Plattform:</span><span class="sxs-lookup"><span data-stu-id="718d6-425">Create a policy for each platform:</span></span>
- <span data-ttu-id="718d6-426">Android</span><span class="sxs-lookup"><span data-stu-id="718d6-426">Android</span></span>
- <span data-ttu-id="718d6-427">Android enterprise</span><span class="sxs-lookup"><span data-stu-id="718d6-427">Android enterprise</span></span>
- <span data-ttu-id="718d6-428">iOS</span><span class="sxs-lookup"><span data-stu-id="718d6-428">iOS</span></span>
- <span data-ttu-id="718d6-429">Mac OS</span><span class="sxs-lookup"><span data-stu-id="718d6-429">macOS</span></span>
- <span data-ttu-id="718d6-430">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="718d6-430">Windows Phone 8.1</span></span>
- <span data-ttu-id="718d6-431">Windows 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="718d6-431">Windows 8.1 and later</span></span>
- <span data-ttu-id="718d6-432">Windows 10 und höher</span><span class="sxs-lookup"><span data-stu-id="718d6-432">Windows 10 and later</span></span>

<span data-ttu-id="718d6-p125">Um Gerät Kompatibilitätsrichtlinien erstellen, melden Sie sich an das Microsoft Azure-Portal mit Ihren Anmeldeinformationen verwalten, und navigieren Sie zu **Intune > Gerät Compliance**. Wählen Sie **Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="718d6-p125">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**. Select **Create policy**.</span></span>

<span data-ttu-id="718d6-435">Die folgenden Einstellungen sind für Windows 10 empfohlen.</span><span class="sxs-lookup"><span data-stu-id="718d6-435">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="718d6-436">**Device-Status: Windows Health Bescheinigung Service-Regeln**</span><span class="sxs-lookup"><span data-stu-id="718d6-436">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="718d6-437">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="718d6-437">Properties</span></span>|<span data-ttu-id="718d6-438">Werte</span><span class="sxs-lookup"><span data-stu-id="718d6-438">Values</span></span>|<span data-ttu-id="718d6-439">Hinweise</span><span class="sxs-lookup"><span data-stu-id="718d6-439">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="718d6-440">BitLocker erfordern</span><span class="sxs-lookup"><span data-stu-id="718d6-440">Require BitLocker</span></span>|<span data-ttu-id="718d6-441">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-441">Require</span></span>||
|<span data-ttu-id="718d6-442">Erfordern Sie Secure Boot auf dem Gerät aktiviert werden soll</span><span class="sxs-lookup"><span data-stu-id="718d6-442">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="718d6-443">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-443">Require</span></span>||
|<span data-ttu-id="718d6-444">Benötigen Sie die Integrität des Codes</span><span class="sxs-lookup"><span data-stu-id="718d6-444">Require code integrity</span></span>|<span data-ttu-id="718d6-445">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-445">Require</span></span>||


<span data-ttu-id="718d6-446">**Geräteeigenschaften**</span><span class="sxs-lookup"><span data-stu-id="718d6-446">**Device properties**</span></span>

|<span data-ttu-id="718d6-447">Typ</span><span class="sxs-lookup"><span data-stu-id="718d6-447">Type</span></span>|<span data-ttu-id="718d6-448">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="718d6-448">Properties</span></span>|<span data-ttu-id="718d6-449">Werte</span><span class="sxs-lookup"><span data-stu-id="718d6-449">Values</span></span>|<span data-ttu-id="718d6-450">Hinweise</span><span class="sxs-lookup"><span data-stu-id="718d6-450">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="718d6-451">Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="718d6-451">Operating system version</span></span>|<span data-ttu-id="718d6-452">Alle</span><span class="sxs-lookup"><span data-stu-id="718d6-452">All</span></span>|<span data-ttu-id="718d6-453">Nicht konfiguriert</span><span class="sxs-lookup"><span data-stu-id="718d6-453">Not configured</span></span>||

<span data-ttu-id="718d6-p126">Für alle, die die oben beschriebenen Richtlinien zu berücksichtigenden bereitgestellt, müssen sie Benutzergruppen Ziel sein. Hierzu können Sie die Richtlinie zu erstellen (Speichern) oder höher, indem Sie die **Bereitstellung verwalten** im Abschnitt **Richtlinie** (derselben Ebene wie hinzufügen) auswählen.</span><span class="sxs-lookup"><span data-stu-id="718d6-p126">For all the above policies to be considered deployed, they must be targeted at user groups. You can do this by creating the policy (on Save) or later by selecting **Manage Deployment** in the **Policy** section (same level as Add).</span></span>

<span data-ttu-id="718d6-456">**Systemsicherheit**</span><span class="sxs-lookup"><span data-stu-id="718d6-456">**System security**</span></span>

|<span data-ttu-id="718d6-457">Typ</span><span class="sxs-lookup"><span data-stu-id="718d6-457">Type</span></span>|<span data-ttu-id="718d6-458">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="718d6-458">Properties</span></span>|<span data-ttu-id="718d6-459">Werte</span><span class="sxs-lookup"><span data-stu-id="718d6-459">Values</span></span>|<span data-ttu-id="718d6-460">Hinweise</span><span class="sxs-lookup"><span data-stu-id="718d6-460">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="718d6-461">Password</span><span class="sxs-lookup"><span data-stu-id="718d6-461">Password</span></span>|<span data-ttu-id="718d6-462">Anfordern eines Kennworts zum Entsperren von mobiler Geräten</span><span class="sxs-lookup"><span data-stu-id="718d6-462">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="718d6-463">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-463">Require</span></span>||
||<span data-ttu-id="718d6-464">Einfache Kennwörter</span><span class="sxs-lookup"><span data-stu-id="718d6-464">Simple passwords</span></span>|<span data-ttu-id="718d6-465">Blockieren</span><span class="sxs-lookup"><span data-stu-id="718d6-465">Block</span></span>||
||<span data-ttu-id="718d6-466">Kennworttyp</span><span class="sxs-lookup"><span data-stu-id="718d6-466">Password type</span></span>|<span data-ttu-id="718d6-467">Gerät Standard</span><span class="sxs-lookup"><span data-stu-id="718d6-467">Device default</span></span>||
||<span data-ttu-id="718d6-468">Minimale Kennwortlänge</span><span class="sxs-lookup"><span data-stu-id="718d6-468">Minimum password length</span></span>|<span data-ttu-id="718d6-469">6</span><span class="sxs-lookup"><span data-stu-id="718d6-469">6</span></span>||
||<span data-ttu-id="718d6-470">Maximale Minuten Inaktivität bevor Kennwort erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="718d6-470">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="718d6-471">15 </span><span class="sxs-lookup"><span data-stu-id="718d6-471">15</span></span>|<span data-ttu-id="718d6-p127">Diese Einstellung wird für Android Versionen 4.0 und höher unterstützt oder KNOX 4.0 und höher. Für iOS-Geräte wird es für iOS 8.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="718d6-p127">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above. For iOS devices, it’s supported for iOS 8.0 and above</span></span>|
||<span data-ttu-id="718d6-474">Kennwortablauf (Tage)</span><span class="sxs-lookup"><span data-stu-id="718d6-474">Password expiration (days)</span></span>|<span data-ttu-id="718d6-475">41</span><span class="sxs-lookup"><span data-stu-id="718d6-475">41</span></span>||
||<span data-ttu-id="718d6-476">Anzahl der vorherigen Kennwörter, Wiederverwendung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="718d6-476">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="718d6-477">5</span><span class="sxs-lookup"><span data-stu-id="718d6-477">5</span></span>||
||<span data-ttu-id="718d6-478">Kennwort ist erforderlich, wenn Gerät aus Leerlauf (Mobile und Holographic) zurückgibt</span><span class="sxs-lookup"><span data-stu-id="718d6-478">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="718d6-479">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-479">Require</span></span>|<span data-ttu-id="718d6-480">Für Windows 10 und höher</span><span class="sxs-lookup"><span data-stu-id="718d6-480">Available for Windows 10 and later</span></span>|
|<span data-ttu-id="718d6-481">Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="718d6-481">Encryption</span></span>|<span data-ttu-id="718d6-482">Verschlüsselung von Datenspeicher auf Gerät</span><span class="sxs-lookup"><span data-stu-id="718d6-482">Encryption of data storage on device</span></span>|<span data-ttu-id="718d6-483">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-483">Require</span></span>||
|<span data-ttu-id="718d6-484">Sicherheit von Geräten</span><span class="sxs-lookup"><span data-stu-id="718d6-484">Device Security</span></span>|<span data-ttu-id="718d6-485">Firewall</span><span class="sxs-lookup"><span data-stu-id="718d6-485">Firewall</span></span>|<span data-ttu-id="718d6-486">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-486">Require</span></span>||
||<span data-ttu-id="718d6-487">Antivirus</span><span class="sxs-lookup"><span data-stu-id="718d6-487">Antivirus</span></span>|<span data-ttu-id="718d6-488">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-488">Require</span></span>||
||<span data-ttu-id="718d6-489">AntiSpyware</span><span class="sxs-lookup"><span data-stu-id="718d6-489">Antispyware</span></span>|<span data-ttu-id="718d6-490">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-490">Require</span></span>|<span data-ttu-id="718d6-491">Diese Einstellung erfordert eine Anti-Schutz-Lösung mit dem Windows-Sicherheitscenter registriert</span><span class="sxs-lookup"><span data-stu-id="718d6-491">This setting requires an Anti-Spyware solution registered with Windows Security Center</span></span>|
|<span data-ttu-id="718d6-492">Defender</span><span class="sxs-lookup"><span data-stu-id="718d6-492">Defender</span></span>|<span data-ttu-id="718d6-493">Windows-Defender-Modul</span><span class="sxs-lookup"><span data-stu-id="718d6-493">Windows Defender Antimalware</span></span>|<span data-ttu-id="718d6-494">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-494">Require</span></span>||
||<span data-ttu-id="718d6-495">Windows Defender Modul Mindestversion</span><span class="sxs-lookup"><span data-stu-id="718d6-495">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="718d6-p128">Nur unterstützt für Windows 10 Desktop. Microsoft empfiehlt Versionen nicht mehr als fünf hinter aus der aktuellsten version</span><span class="sxs-lookup"><span data-stu-id="718d6-p128">Only supported for Windows 10 desktop. Microsoft recommends versions no more than five behind from the most recent version</span></span>|
||<span data-ttu-id="718d6-498">Windows Defender Modul Signatur auf dem aktuellen Stand</span><span class="sxs-lookup"><span data-stu-id="718d6-498">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="718d6-499">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-499">Require</span></span>||
||<span data-ttu-id="718d6-500">„Echtzeitschutz“</span><span class="sxs-lookup"><span data-stu-id="718d6-500">Real-time protection</span></span>|<span data-ttu-id="718d6-501">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="718d6-501">Require</span></span>|<span data-ttu-id="718d6-502">Nur unterstützt für Windows 10 Desktop.</span><span class="sxs-lookup"><span data-stu-id="718d6-502">Only supported for Windows 10 desktop</span></span>|

<span data-ttu-id="718d6-503">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="718d6-503">**Windows Defender ATP**</span></span>

|<span data-ttu-id="718d6-504">Typ</span><span class="sxs-lookup"><span data-stu-id="718d6-504">Type</span></span>|<span data-ttu-id="718d6-505">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="718d6-505">Properties</span></span>|<span data-ttu-id="718d6-506">Werte</span><span class="sxs-lookup"><span data-stu-id="718d6-506">Values</span></span>|<span data-ttu-id="718d6-507">Hinweise</span><span class="sxs-lookup"><span data-stu-id="718d6-507">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="718d6-508">Windows Defender erweiterte Bedrohung-Schutzregeln</span><span class="sxs-lookup"><span data-stu-id="718d6-508">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="718d6-509">Erfordern Sie das Gerät an oder unter der Computer Risiko Score möglicherweise</span><span class="sxs-lookup"><span data-stu-id="718d6-509">Require the device to be at or under the machine-risk score</span></span>|<span data-ttu-id="718d6-510">Mittel</span><span class="sxs-lookup"><span data-stu-id="718d6-510">Medium</span></span>||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="718d6-511">Erfordern Sie kompatible PCs (aber nicht kompatible Telefonen und Tablets)</span><span class="sxs-lookup"><span data-stu-id="718d6-511">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="718d6-p129">Bevor Sie kompatible PCs erforderlich, um eine Richtlinie hinzufügen, unbedingt Geräte für die Verwaltung in Intune registrieren. Verwenden die mehrstufige Authentifizierung wird empfohlen, vor der Geräte in Intune registrieren Assurance, die das Gerät im Besitz des gewünschten Benutzers ist.</span><span class="sxs-lookup"><span data-stu-id="718d6-p129">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune. Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="718d6-514">Kompatible PCs erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="718d6-514">To require compliant PCs:</span></span>

1. <span data-ttu-id="718d6-p130">Wechseln Sie zu der [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen. Nachdem Sie sich erfolgreich angemeldet haben, sehen Sie das Dashboard Azure.</span><span class="sxs-lookup"><span data-stu-id="718d6-p130">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="718d6-517">Wählen Sie im linken Menü **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-517">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="718d6-518">Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="718d6-518">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="718d6-519">Wählen Sie **Neue Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-519">Choose **New policy**.</span></span>

5. <span data-ttu-id="718d6-520">Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="718d6-520">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="718d6-521">Klicken Sie auf **Cloud-Apps**.</span><span class="sxs-lookup"><span data-stu-id="718d6-521">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="718d6-p131">Wählen Sie **apps auswählen**, wählen Sie die gewünschten apps aus der Liste der **Cloud-apps** . Wählen Sie beispielsweise Office 365 Exchange Online. Die Option **auswählen** und **durchgeführt**.</span><span class="sxs-lookup"><span data-stu-id="718d6-p131">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="718d6-p132">Wählen kompatible erforderlich, um PCs, aber nicht kompatible Telefonen und Tablets, **Bedingungen** und **Geräteplattformen**. Wählen Sie **Geräteplattformen** auf aus, und wählen Sie **Windows** und **Mac OS**.</span><span class="sxs-lookup"><span data-stu-id="718d6-p132">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**. Choose **Select device platforms** and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="718d6-527">Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-527">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="718d6-p133">Wählen Sie **Zugriff gewähren**, wählen Sie **erforderlich Gerät als kompatibel markiert werden**. Wählen Sie für mehrere Steuerelemente **alle ausgewählten Steuerelemente erforderlich**, und klicken Sie dann **auf auswählen**.</span><span class="sxs-lookup"><span data-stu-id="718d6-p133">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="718d6-530">Wählen Sie **Create** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-530">Choose **Create**.</span></span>

<span data-ttu-id="718d6-p134">Wenn Ihr Ziel ist es, kompatible PCs *und* mobilen Geräten müssen, wählen Sie Plattformen nicht. Erzwingt die Kompatibilität für alle Geräte.</span><span class="sxs-lookup"><span data-stu-id="718d6-p134">If your objective is to require compliant PCs *and* mobile devices, do not select platforms. This enforces compliance for all devices.</span></span> 

## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="718d6-533">Erfordern Sie kompatible PCs *und* mobile Geräten</span><span class="sxs-lookup"><span data-stu-id="718d6-533">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="718d6-534">So erzwingen Sie Compliance für alle Geräte:</span><span class="sxs-lookup"><span data-stu-id="718d6-534">To require compliance for all devices:</span></span>

1. <span data-ttu-id="718d6-p135">Wechseln Sie zu der [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen. Nachdem Sie sich erfolgreich angemeldet haben, sehen Sie das Dashboard Azure.</span><span class="sxs-lookup"><span data-stu-id="718d6-p135">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="718d6-537">Wählen Sie im linken Menü **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-537">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="718d6-538">Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="718d6-538">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="718d6-539">Wählen Sie **Neue Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-539">Choose **New policy**.</span></span>

5. <span data-ttu-id="718d6-540">Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="718d6-540">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="718d6-541">Klicken Sie auf **Cloud-Apps**.</span><span class="sxs-lookup"><span data-stu-id="718d6-541">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="718d6-p136">Wählen Sie **apps auswählen**, wählen Sie die gewünschten apps aus der Liste der **Cloud-apps** . Wählen Sie beispielsweise Office 365 Exchange Online. Die Option **auswählen** und **durchgeführt**.</span><span class="sxs-lookup"><span data-stu-id="718d6-p136">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="718d6-545">Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-545">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="718d6-p137">Wählen Sie **Zugriff gewähren**, wählen Sie **erforderlich Gerät als kompatibel markiert werden**. Wählen Sie für mehrere Steuerelemente **alle ausgewählten Steuerelemente erforderlich**, und klicken Sie dann **auf auswählen**.</span><span class="sxs-lookup"><span data-stu-id="718d6-p137">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="718d6-548">Wählen Sie **Create** aus.</span><span class="sxs-lookup"><span data-stu-id="718d6-548">Choose **Create**.</span></span>

<span data-ttu-id="718d6-p138">Wenn Sie diese Richtlinie zu erstellen, wählen Sie Plattformen nicht. Dies erzwingt kompatible Geräte.</span><span class="sxs-lookup"><span data-stu-id="718d6-p138">When creating this policy, do not select platforms. This enforces compliant devices.</span></span>




<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a><span data-ttu-id="718d6-551">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="718d6-551">Next steps</span></span>

[<span data-ttu-id="718d6-552">Weitere Informationen zu Richtlinienempfehlungen zum Schutz von E-Mails</span><span class="sxs-lookup"><span data-stu-id="718d6-552">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
