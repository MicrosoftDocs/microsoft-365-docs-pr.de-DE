---
title: Microsoft 365 gruppenbenennungsrichtlinie
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Hier erfahren Sie, wie Sie eine Benennungsrichtlinie für Microsoft 365-Gruppen erstellen.
ms.openlocfilehash: 55faf5c61d577b35b34923efc7b65457fe46de29
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377605"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="6e662-103">Microsoft 365 gruppenbenennungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6e662-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="6e662-104">Sie können eine gruppenbenennungsrichtlinie verwenden, um eine konsistente Benennungsstrategie für Gruppen zu erzwingen, die von Benutzern in Ihrer Organisation erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6e662-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="6e662-105">Eine Benennungsrichtlinie kann Ihnen und Ihren Benutzern bei der Identifizierung der Funktion der Gruppe, der Mitgliedschaft, der geografischen Region oder der Person helfen, die die Gruppe erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="6e662-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="6e662-106">Die Benennungsrichtlinie kann auch hilfreich beim Kategorisieren von Gruppen im Adressbuch sein.</span><span class="sxs-lookup"><span data-stu-id="6e662-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="6e662-107">Mithilfe der Richtlinie können Sie bestimmte Wörter in Gruppennamen und -aliasen blockieren.</span><span class="sxs-lookup"><span data-stu-id="6e662-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="6e662-108">Die Benennungsrichtlinie wird auf Gruppen angewendet, die für alle Gruppen Arbeitsauslastungen erstellt werden (wie Outlook, Microsoft Teams, SharePoint, Planer, jammern usw.).</span><span class="sxs-lookup"><span data-stu-id="6e662-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="6e662-109">Sie wird sowohl auf den Gruppennamen als auch auf den Gruppenalias angewendet.</span><span class="sxs-lookup"><span data-stu-id="6e662-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="6e662-110">Außerdem wird sie angewendet, wenn ein Benutzer eine Gruppe erstellt und wenn ein Gruppenname oder -alias bei einer bestehenden Gruppe bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="6e662-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="6e662-111">Eine Microsoft 365-gruppenbenennungsrichtlinie gilt nur für Microsoft 365-Gruppen.</span><span class="sxs-lookup"><span data-stu-id="6e662-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="6e662-112">Sie gilt nicht für in Exchange Online erstellte Verteilergruppen.</span><span class="sxs-lookup"><span data-stu-id="6e662-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="6e662-113">Informationen zum Erstellen einer Benennungsrichtlinie für Verteilergruppen finden Sie unter [Erstellen einer Namensrichtlinie für Verteilergruppen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="6e662-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="6e662-114">Die Gruppenbenennungsrichtlinie besteht aus den folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="6e662-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="6e662-p104">**Präfix-Suffix-Benennungsrichtlinie**: Sie können Präfixe oder Suffixe verwenden, um die Benennungskonvention von Gruppen zu definieren (beispielsweise "US \_ My Group \_ Engineering"). Bei den Präfixen/Suffixen kann es sich entweder um feste Zeichenfolgen oder Benutzerattribute wie [Department] handeln, die basierend auf dem Benutzer ersetzt werden, der die Gruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="6e662-p104">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering"). The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="6e662-p105">**Benutzerdefinierte blockierte Wörter**: Sie können eine Gruppe blockierter Wörter für Ihre Organisation hochladen, die in von Benutzern erstellten Gruppen blockiert werden. (Beispiel: "CEO, Abrechnung, HR").</span><span class="sxs-lookup"><span data-stu-id="6e662-p105">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users. (For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="6e662-119">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6e662-119">Licensing requirements</span></span>

<span data-ttu-id="6e662-120">Wenn Sie Azure AD Benennungsrichtlinie für Microsoft 365-Gruppen verwenden, müssen Sie für jeden eindeutigen Benutzer (einschließlich Gäste), der Mitglied einer oder mehrerer Microsoft 365-Gruppen ist, eine Azure Active Directory Premium P1-Lizenz oder Azure AD Basic edu-Lizenz besitzen, jedoch nicht unbedingt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6e662-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="6e662-121">Dies ist auch für den Administrator erforderlich, der die Benennungsrichtlinie für Gruppen erstellt.</span><span class="sxs-lookup"><span data-stu-id="6e662-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="6e662-122">Präfix Suffix-Benennungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6e662-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="6e662-123">Bei Präfixen und Suffixen kann es sich entweder um feste Zeichenfolgen oder um Benutzerattribute handeln.</span><span class="sxs-lookup"><span data-stu-id="6e662-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="6e662-124">Feste Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="6e662-124">Fixed strings</span></span>

<span data-ttu-id="6e662-125">Sie können kurze Zeichenfolgen verwenden, mit denen Sie Gruppen in der GAL und der linken Navigation der Gruppen Arbeitsauslastungen unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="6e662-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="6e662-126">Einige der gängigen Präfix Suffixe sind Schlüsselwörter wie "GRP \_ Name", " \# Name", " \_ Name".</span><span class="sxs-lookup"><span data-stu-id="6e662-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="6e662-127">Attribute</span><span class="sxs-lookup"><span data-stu-id="6e662-127">Attributes</span></span>

<span data-ttu-id="6e662-128">Sie können Attribute verwenden, anhand derer Sie feststellen können, wer eine Gruppe erstellt hat, z. B. "[Abteilung]", und wo sie erstellt wurde "[Land]".</span><span class="sxs-lookup"><span data-stu-id="6e662-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="6e662-129">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="6e662-129">Examples:</span></span>

- <span data-ttu-id="6e662-130">Richtlinie = "GRP [Gruppenname] [Abteilung]"</span><span class="sxs-lookup"><span data-stu-id="6e662-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="6e662-131">Abteilung des Benutzers = Entwicklung</span><span class="sxs-lookup"><span data-stu-id="6e662-131">User's department = Engineering</span></span>
- <span data-ttu-id="6e662-132">Erstellter Gruppenname = "GRP Meine Gruppe Entwicklung"</span><span class="sxs-lookup"><span data-stu-id="6e662-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="6e662-133">Die unterstützten Azure Active Directory (Azure AD)-Attribute sind [Department], [Firma], [Office], [StateOrProvince], [CountryOrRegion] und [title].</span><span class="sxs-lookup"><span data-stu-id="6e662-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="6e662-134">Nicht unterstützte Benutzerattribute werden als feste Zeichenfolgen betrachtet, beispielsweise [PostalCode].</span><span class="sxs-lookup"><span data-stu-id="6e662-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="6e662-135">Erweiterungsattribute und benutzerdefinierte Attribute werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e662-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="6e662-136">Es empfiehlt sich, Attribute mit ausgefüllten Werten für alle Benutzer in Ihrer Organisation zu verwenden und Attribute mit längeren Werten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6e662-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="6e662-137">Worauf Sie achten sollten</span><span class="sxs-lookup"><span data-stu-id="6e662-137">Things to look out for</span></span>

- <span data-ttu-id="6e662-138">Während der Erstellung der Richtlinie ist die Gesamtlänge der Zeichenfolgen für Präfixe und Suffixe auf 53 Zeichen eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="6e662-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="6e662-139">Präfixe und Suffixe können Sonderzeichen enthalten, die in Gruppennamen und Gruppenaliasen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="6e662-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="6e662-140">Wenn die Präfixe und Suffixe Sonderzeichen enthalten, die im Gruppen Alias nicht zulässig sind, werden Sie nur auf den Gruppennamen angewendet.</span><span class="sxs-lookup"><span data-stu-id="6e662-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="6e662-141">In diesem Fall würden sich also die auf den Gruppennamen angewendeten Präfixe und Suffixe von den auf den Gruppennamen angewendeten unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="6e662-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6e662-142">Ein Punkt (.) oder ein Bindestrich (-) ist an beliebiger Stelle im Gruppennamen zulässig, außer am Anfang oder Ende des Namens.</span><span class="sxs-lookup"><span data-stu-id="6e662-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="6e662-143">Ein Unterstrich (_) ist an beliebiger Stelle im Gruppennamen zulässig, einschließlich am Anfang oder Ende des Namens.</span><span class="sxs-lookup"><span data-stu-id="6e662-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="6e662-144">Wenn Sie jammern Office 365 verbundene Gruppen verwenden, vermeiden Sie die Verwendung der folgenden Zeichen in ihrer Benennungsrichtlinie: @, \# , \[ , \] , \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="6e662-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="6e662-145">Wenn die Benennungsrichtlinie eines dieser Zeichen enthält, können normale Yammer-Benutzer keine Gruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e662-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="6e662-146">Verwenden Sie kurze Zeichenfolgen als Namenszusatz.</span><span class="sxs-lookup"><span data-stu-id="6e662-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="6e662-147">Verwenden Sie Attribute mit Werten.</span><span class="sxs-lookup"><span data-stu-id="6e662-147">Use attributes with values.</span></span>
> - <span data-ttu-id="6e662-148">Lassen Sie sich nicht zu kreativ sein, die gesamte Name-Länge hat maximal 264 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6e662-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="6e662-149">Laden Sie spezifische blockierte Wörter Ihrer Organisation hoch, um die Nutzung einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="6e662-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="6e662-150">Benutzerdefinierte blockierte Wörter</span><span class="sxs-lookup"><span data-stu-id="6e662-150">Custom blocked words</span></span>

<span data-ttu-id="6e662-151">Sie können eine durch Trennzeichen getrennte Liste der blockierten Wörter eingeben, die in Gruppennamen und -aliasen blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e662-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="6e662-152">Es erfolgt keine Suche nach Teilzeichenfolgen, d. h. es muss eine genaue Übereinstimmung zwischen dem vom Benutzer eingegebenen Namen und den benutzerdefinierten blockierten Wörtern bestehen, um eine Ablehnung auszulösen.</span><span class="sxs-lookup"><span data-stu-id="6e662-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="6e662-153">**Dinge, die Sie beachten**sollten:</span><span class="sxs-lookup"><span data-stu-id="6e662-153">**Things to look out for**:</span></span>

- <span data-ttu-id="6e662-154">Bei blockierten Wörtern wird die Groß-/Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="6e662-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="6e662-155">Wenn ein Benutzer ein blockiertes Wort eingibt, zeigt der Gruppenclient eine Fehlermeldung mit dem gesperrten Wort an.</span><span class="sxs-lookup"><span data-stu-id="6e662-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="6e662-156">Es bestehen keine Zeichenbeschränkungen für die verwendeten blockierten Wörter.</span><span class="sxs-lookup"><span data-stu-id="6e662-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="6e662-157">Es gibt ein Limit von 5000 Wörtern, die als blockierte Wörter festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="6e662-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="6e662-158">Außerkraftsetzung durch Administratoren</span><span class="sxs-lookup"><span data-stu-id="6e662-158">Admin override</span></span>

<span data-ttu-id="6e662-159">Einige Administratoren sind von diesen Richtlinien für alle Gruppen Arbeitslasten und-Endpunkte ausgenommen, sodass Sie Gruppen mit diesen blockierten Wörtern und mit Ihren gewünschten Benennungskonventionen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="6e662-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="6e662-160">Es folgt eine Liste der Administratorrollen, die von der Gruppenbenennungsrichtlinie ausgenommen sind.</span><span class="sxs-lookup"><span data-stu-id="6e662-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="6e662-161">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="6e662-161">Global admin</span></span>

- <span data-ttu-id="6e662-162">Partnersupport der Ebene 1</span><span class="sxs-lookup"><span data-stu-id="6e662-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="6e662-163">Partnersupport der Ebene 2</span><span class="sxs-lookup"><span data-stu-id="6e662-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="6e662-164">Administrator für Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="6e662-164">User account admin</span></span>

- <span data-ttu-id="6e662-165">Verzeichnisautoren</span><span class="sxs-lookup"><span data-stu-id="6e662-165">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="6e662-166">Vorgehensweise zum Einrichten der Benennungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6e662-166">How to set up the naming policy</span></span>

<span data-ttu-id="6e662-167">So richten Sie eine Benennungsrichtlinie ein:</span><span class="sxs-lookup"><span data-stu-id="6e662-167">To set up a naming policy:</span></span>

1. <span data-ttu-id="6e662-168">Klicken Sie in [Azure Active Directory](https://aad.portal.azure.com) unter **Verwalten** auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="6e662-168">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="6e662-169">Klicken Sie unter **Einstellungen** auf **Benennungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="6e662-169">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="6e662-170">Wählen Sie die Registerkarte **Gruppenbenennungsrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="6e662-170">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="6e662-171">Wählen Sie unter **Aktuelle Richtlinie** aus, ob ein Präfix oder ein Suffix oder beides benötigt wird, und aktivieren Sie die entsprechenden Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="6e662-171">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="6e662-172">Wählen Sie zwischen **Attribut** und **Zeichenfolge** für jede Zeile aus, und geben Sie dann das Attribut oder die Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="6e662-172">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="6e662-173">Wenn Sie die benötigten Präfixe und Suffixe hinzugefügt haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6e662-173">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Screenshot der Einstellungen für Benennungsrichtlinien für Gruppen in Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="6e662-175">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6e662-175">Related topics</span></span>

[<span data-ttu-id="6e662-176">Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen</span><span class="sxs-lookup"><span data-stu-id="6e662-176">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
