---
title: Benennungsrichtlinie für Office 365-Gruppen
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Erfahren Sie, wie eine Benennungsrichtlinie für Office 365-Gruppen erstellt wird.
ms.openlocfilehash: 11e2907462d325e4ad421914ae5a0deb5013e695
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352716"
---
# <a name="office-365-groups-naming-policy"></a><span data-ttu-id="41663-103">Benennungsrichtlinie für Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="41663-103">Office 365 Groups naming policy</span></span>

<span data-ttu-id="41663-104">Mithilfe der Gruppenbenennungsrichtlinie können Sie eine konsistente Benennungsstrategie für Gruppen erzwingen, die von Benutzern in Ihrer Organisation erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="41663-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="41663-105">Eine Benennungsrichtlinie kann Ihnen und Ihren Benutzern bei der Identifizierung der Funktion der Gruppe, der Mitgliedschaft, der geografischen Region oder der Person helfen, die die Gruppe erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="41663-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="41663-106">Die Benennungsrichtlinie kann auch hilfreich beim Kategorisieren von Gruppen im Adressbuch sein.</span><span class="sxs-lookup"><span data-stu-id="41663-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="41663-107">Mithilfe der Richtlinie können Sie bestimmte Wörter in Gruppennamen und -aliasen blockieren.</span><span class="sxs-lookup"><span data-stu-id="41663-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="41663-108">Die Benennungsrichtlinie wird übergreifend auf Gruppen angewendet, die in allen Workloads (wie Outlook, Microsoft Teams, SharePoint, Planner, Yammer usw.) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="41663-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc).</span></span> <span data-ttu-id="41663-109">Sie wird sowohl auf den Gruppennamen als auch auf den Gruppenalias angewendet.</span><span class="sxs-lookup"><span data-stu-id="41663-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="41663-110">Außerdem wird sie angewendet, wenn ein Benutzer eine Gruppe erstellt und wenn ein Gruppenname oder -alias bei einer bestehenden Gruppe bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="41663-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="41663-111">Die Benennungsrichtlinie für Office 365-Gruppen gilt nur für Office 365-Gruppen.</span><span class="sxs-lookup"><span data-stu-id="41663-111">An Office 365 group naming policy only applies to Office 365 Groups.</span></span> <span data-ttu-id="41663-112">Sie gilt nicht für in Exchange Online erstellte Verteilergruppen.</span><span class="sxs-lookup"><span data-stu-id="41663-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="41663-113">Informationen zum Erstellen einer Benennungsrichtlinie für Verteilergruppen finden Sie unter [Erstellen einer Namensrichtlinie für Verteilergruppen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="41663-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="41663-114">Die Gruppenbenennungsrichtlinie besteht aus den folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="41663-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="41663-p104">**Präfix-Suffix-Benennungsrichtlinie**: Sie können Präfixe oder Suffixe verwenden, um die Benennungskonvention von Gruppen zu\_definieren\_(Beispiel\_: "GRP US My Group Engineering"). Bei den Präfixen/Suffixen kann es sich entweder um feste Zeichenfolgen oder Benutzerattribute wie [Department] handeln, die basierend auf dem Benutzer ersetzt werden, der die Gruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="41663-p104">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "GRP\_US\_My Group\_Engineering"). The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="41663-p105">**Benutzerdefinierte blockierte Wörter**: Sie können eine Gruppe blockierter Wörter für Ihre Organisation hochladen, die in von Benutzern erstellten Gruppen blockiert würde. (Beispiel: "CEO, Abrechnung, HR").</span><span class="sxs-lookup"><span data-stu-id="41663-p105">**Custom Blocked Words**: You can upload a set of blocked words specific to their organization that would be blocked in groups created by users. (For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="41663-119">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="41663-119">Licensing requirements</span></span>

<span data-ttu-id="41663-120">Die Verwendung der Azure AD-Benennungsrichtlinie für Office 365-Gruppen setzt voraus, dass Sie über eine Azure Active Directory Premium P1-Lizenz oder eine Azure AD Basic EDU-Lizenz für jeden eindeutigen Benutzer (einschließlich Gäste) verfügen, der Mitglied einer oder mehrerer Office 365-Gruppen ist.</span><span class="sxs-lookup"><span data-stu-id="41663-120">Using Azure AD naming policy for Office 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Office 365 groups.</span></span>
<span data-ttu-id="41663-121">Dies gilt auch für den Administrator, der die Benennungsrichtlinie für Gruppen erstellt.</span><span class="sxs-lookup"><span data-stu-id="41663-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="41663-122">Präfix Suffix-Benennungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="41663-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="41663-123">Bei Präfixen und Suffixen kann es sich entweder um feste Zeichenfolgen oder um Benutzerattribute handeln.</span><span class="sxs-lookup"><span data-stu-id="41663-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="41663-124">Feste Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="41663-124">Fixed strings</span></span>

<span data-ttu-id="41663-p107">Sie können kurze Zeichenfolgen verwenden, mit denen Sie Gruppen in der GAL und im linken Navigationsbereich der Gruppen Arbeitsauslastungen unterscheiden können. Einige der gängigen Präfix Suffixe sind Schlüsselwörter wie "GRP\_Name", "\#Name", "\_Name".</span><span class="sxs-lookup"><span data-stu-id="41663-p107">You can use short strings that can help you differentiate groups in the GAL and Left nav of the group workloads. Some of the common prefixes suffixes are Keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="41663-127">Attribute</span><span class="sxs-lookup"><span data-stu-id="41663-127">Attributes</span></span>

<span data-ttu-id="41663-128">Sie können Attribute verwenden, anhand derer Sie feststellen können, wer eine Gruppe erstellt hat, z. B. "[Abteilung]", und wo sie erstellt wurde "[Land]".</span><span class="sxs-lookup"><span data-stu-id="41663-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="41663-129">**Beispiele**</span><span class="sxs-lookup"><span data-stu-id="41663-129">**Examples**</span></span>|<span data-ttu-id="41663-130">Richtlinie = "GRP [Gruppenname] [Abteilung]"</span><span class="sxs-lookup"><span data-stu-id="41663-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="41663-131">Abteilung des Benutzers = Entwicklung</span><span class="sxs-lookup"><span data-stu-id="41663-131">User's department = Engineering</span></span>|
||<span data-ttu-id="41663-132">Erstellter Gruppenname = "GRP Meine Gruppe Entwicklung"</span><span class="sxs-lookup"><span data-stu-id="41663-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="41663-133">Die unterstützten Azure Active Directory (Azure AD)-Attribute sind [Abteilung], [Firma], [Büro], [Bundesland/Kanton], [Land/Region], [Position]</span><span class="sxs-lookup"><span data-stu-id="41663-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], [Title]</span></span>

- <span data-ttu-id="41663-p108">Nicht unterstützte Benutzerattribute werden als feste Zeichenfolgen angesehen. Z. B. "[Postleitzahl]"</span><span class="sxs-lookup"><span data-stu-id="41663-p108">Unsupported user attributes are considered as fixed strings. E.g. "[postalCode]"</span></span>

- <span data-ttu-id="41663-137">Erweiterungsattribute und benutzerdefinierte Attribute werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41663-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="41663-138">Es empfiehlt sich, Attribute mit ausgefüllten Werten für alle Benutzer in Ihrer Organisation zu verwenden und Attribute mit längeren Werten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="41663-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="41663-139">Worauf Sie achten sollten</span><span class="sxs-lookup"><span data-stu-id="41663-139">Things to look out for</span></span>

- <span data-ttu-id="41663-140">Während der Erstellung der Richtlinie ist die Gesamtlänge der Zeichenfolgen für Präfixe und Suffixe auf 53 Zeichen eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="41663-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="41663-p109">Präfixe und Suffixe können Sonderzeichen enthalten, die in Gruppennamen und Gruppenaliasen unterstützt werden. Wenn die Präfixe und Suffixe Sonderzeichen enthalten, die im Gruppenalias nicht zulässig sind, werden diese entfernt und die Präfixe und Suffixe dann auf den Gruppenalias angewendet. In diesem Fall würden sich also die auf den Gruppennamen angewendeten Präfixe und Suffixe von den auf den Gruppennamen angewendeten unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="41663-p109">Prefixes and suffixes can contain special characters supported in group name and group alias. When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are removed and applied to the group alias. So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="41663-144">Wenn Sie jammern Office 365 verbundene Gruppen verwenden, vermeiden Sie die Verwendung der folgenden Zeichen in ihrer Benennungs \#Richtlinie \[: \]@ \<,, \>,, und.</span><span class="sxs-lookup"><span data-stu-id="41663-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="41663-145">Wenn die Benennungsrichtlinie eines dieser Zeichen enthält, können normale Yammer-Benutzer keine Gruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="41663-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="41663-146">Benutzerdefinierte blockierte Wörter</span><span class="sxs-lookup"><span data-stu-id="41663-146">Custom blocked words</span></span>

<span data-ttu-id="41663-147">Sie können eine durch Trennzeichen getrennte Liste der blockierten Wörter eingeben, die in Gruppennamen und -aliasen blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="41663-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="41663-148">Die Überprüfung von blockierten Wörtern wird für den eingegebenen Gruppennamen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="41663-148">The blocked words check is done on the user entered group name.</span></span> <span data-ttu-id="41663-149">Wenn der Benutzer also "darnit" eingibt und\_"prefix" die Benennungsrichtlinie\_ist, schlägt "prefix darnit" fehl.</span><span class="sxs-lookup"><span data-stu-id="41663-149">So if user enters 'darnit' and 'Prefix\_' is the naming policy, 'Prefix\_darnit' will fail.</span></span>

<span data-ttu-id="41663-150">Es erfolgt keine Suche nach Teilzeichenfolgen, d. h. es muss eine genaue Übereinstimmung zwischen dem vom Benutzer eingegebenen Namen und den benutzerdefinierten blockierten Wörtern bestehen, um eine Ablehnung auszulösen.</span><span class="sxs-lookup"><span data-stu-id="41663-150">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="41663-151">Es erfolgt keine Suche nach Teilzeichenfolgen, sodass Benutzer ein Wort wie 'Klarschiff' verwenden können, obwohl 'Arsch' ein blockiertes Wort ist.</span><span class="sxs-lookup"><span data-stu-id="41663-151">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="41663-152">**Dinge, die Sie beachten**sollten:</span><span class="sxs-lookup"><span data-stu-id="41663-152">**Things to look out for**:</span></span>

- <span data-ttu-id="41663-153">Bei blockierten Wörtern wird die Groß-/Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="41663-153">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="41663-154">Wenn ein Benutzer ein blockiertes Wort eingibt, zeigt der Gruppenclient eine Fehlermeldung mit dem gesperrten Wort an.</span><span class="sxs-lookup"><span data-stu-id="41663-154">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="41663-155">Es bestehen keine Zeichenbeschränkungen für die verwendeten blockierten Wörter.</span><span class="sxs-lookup"><span data-stu-id="41663-155">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="41663-156">Es können maximal 5.000 Wörter als blockierte Wörter festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="41663-156">There is an upper limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="41663-157">Außerkraftsetzung durch Administratoren</span><span class="sxs-lookup"><span data-stu-id="41663-157">Admin override</span></span>

<span data-ttu-id="41663-p113">Ausgewählte Administratoren sind übergreifend über alle Workloads und Endpunkte von diesen Richtlinien ausgenommen, sodass sie Gruppen mit den blockierten Wörtern und Benennungskonventionen nach eigenen Wünschen erstellen können. Es folgt eine Liste der Administratorrollen, die von der Gruppenbenennungsrichtlinie ausgenommen sind.</span><span class="sxs-lookup"><span data-stu-id="41663-p113">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions. The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="41663-160">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="41663-160">Global admin</span></span>

- <span data-ttu-id="41663-161">Partnersupport der Ebene 1</span><span class="sxs-lookup"><span data-stu-id="41663-161">Partner Tier 1 Support</span></span>

- <span data-ttu-id="41663-162">Partnersupport der Ebene 2</span><span class="sxs-lookup"><span data-stu-id="41663-162">Partner Tier 2 Support</span></span>

- <span data-ttu-id="41663-163">Administrator für Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="41663-163">User account admin</span></span>

- <span data-ttu-id="41663-164">Verzeichnisautoren</span><span class="sxs-lookup"><span data-stu-id="41663-164">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="41663-165">Vorgehensweise zum Einrichten der Benennungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="41663-165">How to set up the naming policy</span></span>

<span data-ttu-id="41663-166">So richten Sie eine Benennungsrichtlinie ein:</span><span class="sxs-lookup"><span data-stu-id="41663-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="41663-167">Klicken Sie in [Azure Active Directory](https://aad.portal.azure.com) unter **Verwalten** auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="41663-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="41663-168">Klicken Sie unter **Einstellungen** auf **Benennungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="41663-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="41663-169">Wählen Sie die Registerkarte **Gruppenbenennungsrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="41663-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="41663-170">Wählen Sie unter **Aktuelle Richtlinie** aus, ob ein Präfix oder ein Suffix oder beides benötigt wird, und aktivieren Sie die entsprechenden Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="41663-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="41663-171">Wählen Sie zwischen **Attribut** und **Zeichenfolge** für jede Zeile aus, und geben Sie dann das Attribut oder die Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="41663-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="41663-172">Wenn Sie die benötigten Präfixe und Suffixe hinzugefügt haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="41663-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Screenshot der Einstellungen für Benennungsrichtlinien für Gruppen in Azure Active Directory](../../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a><span data-ttu-id="41663-174">Benutzererfahrung der Benennungsrichtlinien in den einzelnen Office 365-Apps</span><span class="sxs-lookup"><span data-stu-id="41663-174">Naming policy experiences across Office 365 apps</span></span>

<span data-ttu-id="41663-p114">Die Office 365-Apps wurden aktualisiert, um eine Vorschau des Benennungsrichtlinien-Gruppennamens (mit Präfixen und Suffixen) anzuzeigen, wenn der Benutzer den Gruppennamen und den Alias eingibt. Wenn Benutzer blockierte Wörter eingeben, wird eine Fehlermeldung angezeigt, sodass sie die blockierten Wörter entfernen können.</span><span class="sxs-lookup"><span data-stu-id="41663-p114">The Office 365 apps have been updated to show a preview of the naming policy group name (with prefixes and suffixes) when the user types in the group name and alias. When the user enters blocked words, they'll see an error message so they can remove the blocked words.</span></span>

## <a name="outlook-on-the-web"></a><span data-ttu-id="41663-177">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="41663-177">Outlook on the web</span></span>

<span data-ttu-id="41663-p115">Outlook im Internet (früher bekannt als Outlook Web App oder OWA) zeigt den Benennungsrichtlinien ergänzten Namen an, wenn der Benutzer einen Gruppennamen oder Gruppen Alias eingibt. Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird in der Benutzeroberfläche eine Fehlermeldung zusammen mit dem blockierten Wort angezeigt, sodass der Benutzer es entfernen kann. Im folgenden sind die Snapshots für Outlook im Webbrowser dargestellt.</span><span class="sxs-lookup"><span data-stu-id="41663-p115">Outlook on the web (formerly known as Outlook Web App or OWA) shows the naming policy decorated name when the user types a group name or group alias. When an user enters a custom blocked word, an error message is shown in the UI along with the blocked word so that the user can remove it. Outlook on the web experience snapshots are shown below.</span></span>

![Nebeneinander angeordnete Ansicht von Gruppenbenennungsrichtlinien in Office 365-Gruppen](../../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a><span data-ttu-id="41663-182">Outlook Desktop</span><span class="sxs-lookup"><span data-stu-id="41663-182">Outlook Desktop</span></span>

<span data-ttu-id="41663-183">In Outlook Desktop erstellte Gruppen sind mit der Benennungsrichtlinie kompatibel.</span><span class="sxs-lookup"><span data-stu-id="41663-183">Groups created in Outlook desktop are compliant with naming policy.</span></span> <span data-ttu-id="41663-184">Die Outlook Desktop-App zeigt derzeit noch keine Vorschau der Benennungsrichtlinie an und gibt Fehler aufgrund benutzerdefinierter blockierter Wörter nicht zurück, wenn der Benutzer den Gruppennamen eingibt.</span><span class="sxs-lookup"><span data-stu-id="41663-184">Outlook desktop app doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span> <span data-ttu-id="41663-185">Allerdings wird die Benennungsrichtlinie beim Auswählen von Erstellen/Bearbeiten automatisch angewendet, und Benutzern werden Fehler angezeigt, wenn sich im Gruppennamen oder Alias benutzerdefinierte blockierte Wörter befinden.</span><span class="sxs-lookup"><span data-stu-id="41663-185">However, naming policy will be automatically applied on selecting create/edit and users will be presented with errors if there are custom blocked words in the group name or alias.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="41663-186">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="41663-186">Microsoft Teams</span></span>

<span data-ttu-id="41663-p117">Wenn der Benutzer einen Teamnamen eingibt, zeigt Microsoft Teams den von der Benennungsrichtlinie ergänzten Namen an. Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird eine Fehlermeldung zusammen mit dem blockierten Wort angezeigt, sodass der Benutzer es entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="41663-p117">Microsoft Teams shows the naming policy decorated name when the user types a team name. When a user enters a custom blocked word, an error message is shown along with the blocked word so that the user can remove it.</span></span>

![Gruppenbenennungsrichtlinie in Microsoft Teams, blockiertes Beispiel](../../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a><span data-ttu-id="41663-190">SharePoint</span><span class="sxs-lookup"><span data-stu-id="41663-190">SharePoint</span></span>

<span data-ttu-id="41663-191">SharePoint zeigt den Namen gemäß der Benennungsrichtlinie an, wenn der Benutzer einen Websitenamen oder eine Gruppen-E-Mail-Adresse eingibt.</span><span class="sxs-lookup"><span data-stu-id="41663-191">SharePoint shows the naming policy name when the user types a site name or group email address.</span></span> <span data-ttu-id="41663-192">Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird eine Fehlermeldung zusammen mit dem blockierten Wort angezeigt, sodass der Benutzer es entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="41663-192">When an user enters a custom blocked word, an error message is shown, along with the blocked word so that the user can remove it.</span></span>

![Gruppenbenennungsrichtlinie – Blockierter Name einer SharePoint-Website](../../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a><span data-ttu-id="41663-194">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="41663-194">Microsoft Stream</span></span>

<span data-ttu-id="41663-p119">Microsoft Stream zeigt den gemäß der Benennungsrichtlinie ergänzten Namen an, wenn der Benutzer einen Gruppennamen oder einen Gruppen-E-Mail-Alias eingibt. Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird eine Fehlermeldung mit dem blockierten Wort angezeigt, sodass der Benutzer es entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="41663-p119">Microsoft Stream shows the naming policy decorated name when the user types a group name or group email alias. When an user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Gruppenbenennungsrichtlinie, blockiertes Beispiel für Microsoft Stream](../../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a><span data-ttu-id="41663-198">Outlook iOS- und Android-App</span><span class="sxs-lookup"><span data-stu-id="41663-198">Outlook iOS and Android App</span></span>

<span data-ttu-id="41663-199">In Outlook-Apps erstellte Gruppen sind mit der Benennungsrichtlinie kompatibel.</span><span class="sxs-lookup"><span data-stu-id="41663-199">Groups created in Outlook apps are compliant with naming policy.</span></span> <span data-ttu-id="41663-200">Outlook Mobile zeigt bei der Eingabe des Gruppennamens eine Vorschau des durch die Benennungsrichtlinie erzwungenen Namens an.</span><span class="sxs-lookup"><span data-stu-id="41663-200">Outlook mobile shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="41663-201">Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird beim Erstellen der Gruppe eine Fehlermeldung angezeigt, sodass der Benutzer das blockierte Wort entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="41663-201">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="planner"></a><span data-ttu-id="41663-202">Planner</span><span class="sxs-lookup"><span data-stu-id="41663-202">Planner</span></span>

<span data-ttu-id="41663-203">Planer ist mit den Benennungsrichtlinien kompatibel.</span><span class="sxs-lookup"><span data-stu-id="41663-203">Planner is compliant with naming policy.</span></span> <span data-ttu-id="41663-204">Planner zeigt bei der Eingabe des Plannamens eine Vorschau des durch die Benennungsrichtlinie erzwungenen Namens an.</span><span class="sxs-lookup"><span data-stu-id="41663-204">Planner shows the naming policy preview when entering the Plan name.</span></span> <span data-ttu-id="41663-205">Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird beim Erstellen des Plans eine Fehlermeldung angezeigt, sodass der Benutzer das blockierte Wort entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="41663-205">When a user enters a custom blocked word, an error message is shown on creating the plan, so the user can remove the blocked word.</span></span>

![Gruppenbenennungsrichtlinie – "Neuen Plan erstellen", blockiertes Beispiel](../../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a><span data-ttu-id="41663-207">Dynamics 365 for Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="41663-207">Dynamics 365 for Customer Engagement</span></span>

<span data-ttu-id="41663-208">Dynamics 365 for Customer Engagement ist mit der Benennungsrichtlinie konform.</span><span class="sxs-lookup"><span data-stu-id="41663-208">Dynamics 365 for Customer Engagement is compliant with naming policy.</span></span> <span data-ttu-id="41663-209">Dynamics 365 zeigt den durch die Benennungsrichtlinie ergänzten Namen an, wenn der Benutzer einen Gruppennamen oder den E-Mail-Alias einer Gruppe eingibt.</span><span class="sxs-lookup"><span data-stu-id="41663-209">Dynamics 365 shows the naming policy decorated name when the user types a group name or group email alias.</span></span> <span data-ttu-id="41663-210">Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird eine Fehlermeldung mit dem blockierten Wort angezeigt, damit der Benutzer es entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="41663-210">When the user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Dynamics 365](../../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a><span data-ttu-id="41663-212">School Data Sync (SDS)</span><span class="sxs-lookup"><span data-stu-id="41663-212">School Data Sync (SDS)</span></span>

<span data-ttu-id="41663-p123">Mithilfe von SDS erstellte Gruppen sind mit der Benennungsrichtlinie kompatibel, die Benennungsrichtlinie wird aber nicht automatisch angewendet. SDS-Administratoren müssen die Präfixe und Suffixe an die Namen von Klassen anhängen, für die Gruppen erstellt werden müssen, und sie dann auf SDS hochladen. Andernfalls tritt beim Erstellen/Bearbeiten von Gruppen ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="41663-p123">Groups created through SDS comply with naming policy, but the naming policy isn't applied automatically. SDS administrators have to append the prefixes and suffixes to class names for which groups need to be created and then upload to SDS. Groups creation/edit would fail otherwise.</span></span>

## <a name="outlook-customer-manager-ocm"></a><span data-ttu-id="41663-216">Outlook Customer Manager (OCM)</span><span class="sxs-lookup"><span data-stu-id="41663-216">Outlook Customer Manager (OCM)</span></span>

<span data-ttu-id="41663-217">Outlook Customer Manager ist mit der Benennungsrichtlinie konform.</span><span class="sxs-lookup"><span data-stu-id="41663-217">Outlook Customer Manager is compliant with naming policy.</span></span> <span data-ttu-id="41663-218">Die Benennungsrichtlinie wird automatisch auf die in Outlook Customer Manager erstellte Gruppe angewendet.</span><span class="sxs-lookup"><span data-stu-id="41663-218">The naming policy gets automatically applied to the group created in Outlook Customer Manager.</span></span> <span data-ttu-id="41663-219">Wenn eines der Wörter in "Gesamtes Vertriebsteam" als benutzerdefiniertes blockiertes Wort definiert ist, wird die Gruppenerstellung in OCM blockiert.</span><span class="sxs-lookup"><span data-stu-id="41663-219">If any of the words within "All Sales Team" is defined as a custom blocked word, the group creation in OCM will be blocked.</span></span> <span data-ttu-id="41663-220">Der Benutzer kann die OCM-Gruppe nicht erstellen und wird für die Nutzung der OCM-App blockiert.</span><span class="sxs-lookup"><span data-stu-id="41663-220">The user will not be able to create the OCM group and will be blocked from using the OCM app."</span></span>

## <a name="classroom-app"></a><span data-ttu-id="41663-221">Classroom-App</span><span class="sxs-lookup"><span data-stu-id="41663-221">Classroom App</span></span>

<span data-ttu-id="41663-p125">In der Classroom-App erstellte Gruppen sind mit der Benennungsrichtlinie kompatibel, aber die Benennungsrichtlinie wird nicht automatisch angewendet, und beim Eingeben eines Classroom-Gruppennamens wird den Benutzern keine Vorschau der Benennungsrichtlinie angezeigt. Daher müssen Benutzer den um Präfixe und Suffixe ergänzten Gruppennamen eingeben. Andernfalls treten beim Erstellen oder Bearbeiten der Classroom-Gruppe Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="41663-p125">Groups created in classroom app comply with naming policy, but the naming policy isn't applied automatically, and the naming policy preview isn't shown to the users while entering a classroom group name. So users would have to enter the decorated classroom group name with prefixes and suffixes. Otherwise the classroom group create or edit will fail with errors.</span></span>

## <a name="power-bi"></a><span data-ttu-id="41663-225">Power BI</span><span class="sxs-lookup"><span data-stu-id="41663-225">Power BI</span></span>

<span data-ttu-id="41663-226">In Power BI-Arbeitsbereichen erstellte Gruppen sind mit der Benennungsrichtlinie kompatibel, die Benennungsrichtlinie wird aber nicht automatisch angewendet.</span><span class="sxs-lookup"><span data-stu-id="41663-226">Groups created in Power BI workspaces comply with the naming policy, but the naming policy isn't applied automatically.</span></span> <span data-ttu-id="41663-227">Und die Vorschau der Benennungsrichtlinie wird Benutzern nicht angezeigt, wenn Sie einen Power BI-Arbeitsbereichsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="41663-227">And, the naming policy preview isn't shown to users when they enter a Power BI workspace name.</span></span>

<span data-ttu-id="41663-228">Der empfohlene Name – mit der angewendeten Benennungsrichtlinie – wird in den Fehlerdetails unter Erstellen oder Bearbeiten von Arbeitsbereichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="41663-228">The recommended name - with the naming policy applied - is shown in the error details on create or edit workspaces.</span></span> <span data-ttu-id="41663-229">Benutzer müssen dann den ergänzten Arbeitsbereichsnamen mit Präfixen und Suffixen eingeben.</span><span class="sxs-lookup"><span data-stu-id="41663-229">This means users have to enter the decorated workspace name with prefixes and suffixes.</span></span> <span data-ttu-id="41663-230">Andernfalls treten beim Erstellen oder Bearbeiten des Arbeitsbereichs Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="41663-230">Otherwise the workspace create or edit will fail with errors.</span></span>

## <a name="yammer"></a><span data-ttu-id="41663-231">Yammer</span><span class="sxs-lookup"><span data-stu-id="41663-231">Yammer</span></span>

<span data-ttu-id="41663-232">Wenn ein Benutzer, der sich mit seinem Azure Active Directory-Konto bei Yammer angemeldet hat, eine Gruppe erstellt oder einen Gruppennamen bearbeitet, entspricht der Gruppenname der Benennungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="41663-232">When a user signed in to Yammer with their Azure Active Directory account creates a group or edits a group name, the group name will comply with naming policy.</span></span> <span data-ttu-id="41663-233">Dies gilt sowohl für mit Office 365 verbundene Gruppen als auch für alle anderen Yammer-Gruppen.</span><span class="sxs-lookup"><span data-stu-id="41663-233">This applies both to Office 365 connected groups and all other Yammer groups.</span></span>

<span data-ttu-id="41663-234">Wenn eine mit Office 365 verbundene Gruppe erstellt wurde, bevor die Benennungsrichtlinie vorhanden war, entspricht der Gruppenname nicht automatisch den Benennungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="41663-234">If an Office 365 connected group was created before the naming policy is in place, the group name will not automatically follow the naming policies.</span></span> <span data-ttu-id="41663-235">Wenn ein Benutzer den Gruppennamen bearbeitet, wird er aufgefordert, das Präfix und das Suffix hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="41663-235">When a user edits the group name, they will be prompted to add the prefix and suffix.</span></span>

<span data-ttu-id="41663-236">Wenn die Benennungsrichtlinie Zeichen enthält, die nicht in Yammer-Gruppennamen enthalten sein dürfen, können nur Administratoren eine verbundene Gruppe in Yammer erstellen.</span><span class="sxs-lookup"><span data-stu-id="41663-236">If the naming policy includes characters that can't be in Yammer group names, only admins will be able to create a connected group in Yammer.</span></span>

## <a name="staffhub"></a><span data-ttu-id="41663-237">StaffHub</span><span class="sxs-lookup"><span data-stu-id="41663-237">StaffHub</span></span>

<span data-ttu-id="41663-238">StaffHub-Teams unterliegen nicht der Benennungsrichtlinie, die zugrunde liegende Office 365-Gruppe jedoch schon.</span><span class="sxs-lookup"><span data-stu-id="41663-238">StaffHub teams do not follow the naming policy, but the underlying Office 365 group does.</span></span> <span data-ttu-id="41663-239">Der StaffHub-Teamname wendet die Präfixe und Suffixe nicht an und wird nicht auf benutzerdefinierte blockierte Wörter überprüft.</span><span class="sxs-lookup"><span data-stu-id="41663-239">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="41663-240">StaffHub wendet die Präfixe und Suffixe allerdings auf die zugrunde liegende Office 365-Gruppe an und entfernt dort ggf. blockierte Wörter.</span><span class="sxs-lookup"><span data-stu-id="41663-240">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Office 365 group.</span></span>

## <a name="exchange-powershell"></a><span data-ttu-id="41663-241">Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="41663-241">Exchange PowerShell</span></span>

<span data-ttu-id="41663-p131">Exchange-PowerShell-Cmdlets sind mit der Benennungsrichtlinie kompatibel. Benutzern werden entsprechende Fehlermeldungen mit Vorschlägen für Präfixe und Suffixe und benutzerdefinierte blockierte Wörter angezeigt, wenn die Benennungskonvention in Gruppennamen und Gruppenaliasen nicht befolgt wird.</span><span class="sxs-lookup"><span data-stu-id="41663-p131">Exchange PowerShell cmdlets are compliant with naming policy. Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="azure-active-directory-powershell-cmdlets"></a><span data-ttu-id="41663-244">Azure Active Directory PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="41663-244">Azure Active Directory PowerShell cmdlets</span></span>

<span data-ttu-id="41663-245">Azure Active Directory PowerShell-Cmdlets sind mit der Benennungsrichtlinie konform.</span><span class="sxs-lookup"><span data-stu-id="41663-245">Azure Active Directory PowerShell cmdlets are compliant with naming policy.</span></span> <span data-ttu-id="41663-246">Benutzern werden entsprechende Fehlermeldungen mit Vorschlägen für Präfixe und Suffixe und benutzerdefinierte blockierte Wörter angezeigt, wenn die Benennungskonvention in Gruppennamen und Gruppenaliasen nicht befolgt wird.</span><span class="sxs-lookup"><span data-stu-id="41663-246">Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="exchange-admin-center"></a><span data-ttu-id="41663-247">Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="41663-247">Exchange admin center</span></span>

<span data-ttu-id="41663-248">Das Exchange Admin Center (EAC) ist mit der Benennungsrichtlinie kompatibel.</span><span class="sxs-lookup"><span data-stu-id="41663-248">The Exchange admin center (EAC) is compliant with naming policy.</span></span> <span data-ttu-id="41663-249">Beim Erstellen oder Bearbeiten von Aktionen werden Benutzern entsprechende Fehlermeldungen mit Vorschlägen für Präfixe und Suffixe und benutzerdefinierte blockierte Wörter angezeigt, wenn die Benennungskonvention in Gruppennamen und Gruppenaliasen nicht befolgt wird.</span><span class="sxs-lookup"><span data-stu-id="41663-249">On create or edit actions, users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="microsoft-365-admin-center"></a><span data-ttu-id="41663-250">Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="41663-250">Microsoft 365 admin center</span></span>

<span data-ttu-id="41663-251">Das Microsoft 365 Admin Center ist mit den Benennungsrichtlinien kompatibel.</span><span class="sxs-lookup"><span data-stu-id="41663-251">The Microsoft 365 admin center is compliant with naming policy.</span></span> <span data-ttu-id="41663-252">Beim Erstellen oder Bearbeiten von Aktionen wird die Benennungsrichtlinie automatisch angewendet.</span><span class="sxs-lookup"><span data-stu-id="41663-252">On create or edit actions, naming policy will automatically get applied.</span></span> <span data-ttu-id="41663-253">Benutzer erhalten entsprechende Fehler, wenn sie benutzerdefinierte blockierte Wörter eingeben.</span><span class="sxs-lookup"><span data-stu-id="41663-253">Users will get appropriate errors when they enter custom blocked words.</span></span> <span data-ttu-id="41663-254">Das Microsoft 365 Admin Center zeigt derzeit noch keine Vorschau der Benennungsrichtlinie an und gibt die Fehler aufgrund benutzerdefinierter blockierter Wörter nicht zurück, wenn der Benutzer den Gruppennamen eingibt.</span><span class="sxs-lookup"><span data-stu-id="41663-254">The Microsoft 365 admin center doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span>

## <a name="azure-active-directory-portal"></a><span data-ttu-id="41663-255">Azure Active Directory-Portal</span><span class="sxs-lookup"><span data-stu-id="41663-255">Azure Active Directory portal</span></span>

<span data-ttu-id="41663-256">Das Azure Active Directory-Portal ist mit der Benennungsrichtlinie konform.</span><span class="sxs-lookup"><span data-stu-id="41663-256">The Azure Active Directory portal is compliant with naming policy.</span></span> <span data-ttu-id="41663-257">Das Azure Active Directory-Portal zeigt bei der Eingabe des Gruppennamens eine Vorschau des durch die Benennungsrichtlinie erzwungenen Namens an.</span><span class="sxs-lookup"><span data-stu-id="41663-257">Azure Active Directory portal shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="41663-258">Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird beim Erstellen der Gruppe eine Fehlermeldung angezeigt, sodass der Benutzer das blockierte Wort entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="41663-258">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="41663-259">Weitere Artikel zur Benennungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="41663-259">More articles on naming policy</span></span>

[<span data-ttu-id="41663-260">Erzwingen einer Benennungsrichtlinie für Office 365-Gruppen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="41663-260">Enforce a naming policy for Office 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="41663-261">Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen</span><span class="sxs-lookup"><span data-stu-id="41663-261">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
