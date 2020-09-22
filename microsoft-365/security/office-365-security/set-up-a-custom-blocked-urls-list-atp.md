---
title: Einrichten einer benutzerdefinierten Liste blockierter URLs mithilfe von ATP-Sicherheits Links
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie eine Liste blockierter URLs für Ihre Organisation mit Office 365 Advanced Threat Protection einrichten.
ms.openlocfilehash: e153d5631c12d52564643477216b777cdbc49433
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201003"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="7a4f3-103">Einrichten einer benutzerdefinierten Liste blockierter URLs mithilfe von ATP-Sicherheits Links</span><span class="sxs-lookup"><span data-stu-id="7a4f3-103">Set up a custom blocked URLs list using ATP Safe Links</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="7a4f3-104">Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="7a4f3-105">Wenn Sie ein Privatbenutzer sind, der nach Informationen zu sicheren Links in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="7a4f3-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="7a4f3-106">Mit [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kann Ihre Organisation eine benutzerdefinierte Liste der blockierten Websiteadressen (URLs) haben.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="7a4f3-107">Wenn eine URL blockiert wird, werden Personen, die auf Links zur gesperrten URL klicken, zu einer [Warnungsseite](atp-safe-links-warning-pages.md) geleitet, die dem folgenden Bild ähnelt:</span><span class="sxs-lookup"><span data-stu-id="7a4f3-107">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span>

![Diese Website ist blockiert](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="7a4f3-109">Die Liste Blockierte URLs wird vom Microsoft 365 for Business-Sicherheitsteam Ihrer Organisation definiert, und diese Liste gilt für alle Benutzer in der Organisation, die von Office 365 Richtlinien für ATP-sichere Links abgedeckt werden.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-109">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span>

<span data-ttu-id="7a4f3-110">In diesem Artikel erfahren Sie, wie Sie die Liste der benutzerdefinierten blockierten URLs Ihrer Organisation für [ATP-sichere Links in Office 365](atp-safe-links.md)einrichten.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-110">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="7a4f3-111">Anzeigen oder Bearbeiten einer benutzerdefinierten Liste blockierter URLs</span><span class="sxs-lookup"><span data-stu-id="7a4f3-111">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="7a4f3-112">[Für ATP-sichere Links in Office 365](atp-safe-links.md) werden mehrere Listen verwendet, einschließlich der Liste der benutzerdefinierten blockierten URLs in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-112">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="7a4f3-113">Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie die benutzerdefinierte Liste Ihrer Organisation einrichten.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-113">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="7a4f3-114">Hierzu bearbeiten Sie die Standardrichtlinie für sichere Links in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-114">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="7a4f3-115">Um ATP-Richtlinien zu bearbeiten oder zu definieren, müssen Sie einer der in der folgenden Tabelle beschriebenen Rollen zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="7a4f3-115">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

****

|<span data-ttu-id="7a4f3-116">Rolle</span><span class="sxs-lookup"><span data-stu-id="7a4f3-116">Role</span></span>|<span data-ttu-id="7a4f3-117">Wo/wie zugewiesen</span><span class="sxs-lookup"><span data-stu-id="7a4f3-117">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="7a4f3-118">globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="7a4f3-118">global administrator</span></span>|<span data-ttu-id="7a4f3-119">Die Person, die sich zum Kauf von Microsoft 365 anmeldet, ist standardmäßig ein globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-119">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="7a4f3-120">(Weitere Informationen finden Sie unter [Informationen zu Microsoft 365-Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)</span><span class="sxs-lookup"><span data-stu-id="7a4f3-120">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="7a4f3-121">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="7a4f3-121">Security Administrator</span></span>|<span data-ttu-id="7a4f3-122">Azure Active Directory Admin Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="7a4f3-122">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="7a4f3-123">Exchange Online-Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="7a4f3-123">Exchange Online Organization Management</span></span>|<span data-ttu-id="7a4f3-124">Exchange Admin Center ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="7a4f3-124">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="7a4f3-125">oder</span><span class="sxs-lookup"><span data-stu-id="7a4f3-125">or</span></span> <br>  <span data-ttu-id="7a4f3-126">PowerShell-Cmdlets (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="7a4f3-126">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="7a4f3-127">Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7a4f3-127">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="7a4f3-128">So zeigen Sie eine benutzerdefinierte Liste blockierter URLs an oder bearbeiten Sie</span><span class="sxs-lookup"><span data-stu-id="7a4f3-128">To view or edit a custom blocked URLs list</span></span>

1. <span data-ttu-id="7a4f3-129">Wechseln Sie zu, [https://protection.office.com](https://protection.office.com) und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-129">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="7a4f3-130">Wählen Sie im linken Navigationsbereich unter **Threat Management**die Option **Richtlinien** \> **sichere Links**aus.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-130">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="7a4f3-131">Wählen Sie in den **Richtlinien für den Abschnitt gesamte Organisation** die Option **Standard**aus, und klicken Sie dann auf **Bearbeiten** (die Schaltfläche Bearbeiten ähnelt einem Bleistift).</span><span class="sxs-lookup"><span data-stu-id="7a4f3-131">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="7a4f3-132">![Klicken Sie auf Bearbeiten, um die Standardrichtlinie für den Schutz von sicheren Links zu bearbeiten.](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="7a4f3-132">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="7a4f3-133">Auf diese Weise können Sie die Liste der blockierten URLs anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-133">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="7a4f3-134">Auf den ersten sind hier möglicherweise keine URLs aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-134">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="7a4f3-135">![Liste der blockierten URLs in der Standardrichtlinie für sichere Links](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="7a4f3-135">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>

4. <span data-ttu-id="7a4f3-136">Aktivieren Sie das Kontrollkästchen **gültige URL eingeben** , geben Sie eine URL ein, und klicken Sie dann auf das Pluszeichen ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="7a4f3-136">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span>

5. <span data-ttu-id="7a4f3-137">Wenn Sie das Hinzufügen von URLs abgeschlossen haben, wählen Sie in der unteren rechten Ecke des Bildschirms **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="7a4f3-138">Einige Dinge, die Sie beachten sollten</span><span class="sxs-lookup"><span data-stu-id="7a4f3-138">A few things to keep in mind</span></span>

<span data-ttu-id="7a4f3-139">Achten Sie beim Hinzufügen von URLs zu Ihrer Liste darauf, Folgendes zu beachten:</span><span class="sxs-lookup"><span data-stu-id="7a4f3-139">While you add URLs to your list, keep the following points in mind:</span></span>

- <span data-ttu-id="7a4f3-140">Fügen Sie am Ende der URL keinen Schrägstrich ( **/** ) ein.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-140">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="7a4f3-141">Geben Sie beispielsweise anstatt Eingabe `https://www.contoso.com/` ein ein `https://www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="7a4f3-141">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>

- <span data-ttu-id="7a4f3-142">Sie können eine nur-Domänen-URL angeben (wie `contoso.com` oder `tailspintoys.com` ).</span><span class="sxs-lookup"><span data-stu-id="7a4f3-142">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="7a4f3-143">Dadurch wird das Klicken auf eine URL blockiert, die die Domäne enthält.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-143">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="7a4f3-144">Sie können eine Unterdomäne (like) angeben, `toys.contoso.com*` ohne eine vollständige Domäne (like) zu blockieren `contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="7a4f3-144">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="7a4f3-145">Dadurch wird das Klicken auf eine URL blockiert, die die Unterdomäne enthält, es werden jedoch keine Klicks auf eine URL blockiert, die die vollständige Domäne enthält.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-145">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>

- <span data-ttu-id="7a4f3-146">Sie können bis zu drei Platzhalter Sternchen ( \* ) pro URL hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-146">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="7a4f3-147">In der folgenden Tabelle sind einige Beispiele aufgeführt, die Sie eingeben können und welche Auswirkungen diese Einträge haben.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-147">The following table lists some examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="7a4f3-148">Beispieleintrag</span><span class="sxs-lookup"><span data-stu-id="7a4f3-148">Example Entry</span></span>|<span data-ttu-id="7a4f3-149">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="7a4f3-149">What It Does</span></span>|
|---|---|
|<span data-ttu-id="7a4f3-150">`contoso.com` oder `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="7a4f3-150">`contoso.com` or `*contoso.com*`</span></span>|<span data-ttu-id="7a4f3-151">Blockiert die Domäne, Unterdomänen und Pfade, wie `https://www.contoso.com` , `https://sub.contoso.com` und `https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="7a4f3-151">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="7a4f3-152">Blockiert eine Website, `https://contoso.com/a` jedoch keine weiteren untergeordneten Pfade wie `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="7a4f3-152">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="7a4f3-153">Blockiert eine Website `https://contoso.com/a` und weitere untergeordnete Pfade wie `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="7a4f3-153">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="7a4f3-154">Blockiert eine Unterdomäne ("Toys" in diesem Fall), aber Sie können Klicks auf andere Domänen-URLs (wie `https://contoso.com` oder `https://home.contoso.com` ) zulassen.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-154">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

> [!NOTE]
> <span data-ttu-id="7a4f3-155">Standardmäßig können Sie in der Liste gesperrter URLs nur 500-URLs in der Standardrichtlinie Office 365 ATP-Links hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-155">By default, you can only add 500 URLs to the blocked URL list in the Office 365 ATP Safe Links default policy.</span></span> <span data-ttu-id="7a4f3-156">Eine einzelne URL darf 128 Zeichen nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-156">An individual URL can't exceed 128 characters.</span></span> <span data-ttu-id="7a4f3-157">Die gesamte Liste blockierter URLs darf 10.000 Zeichen nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-157">The entire Blocked URL list can't exceed 10,000 characters.</span></span>

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="7a4f3-158">Vorgehensweise definieren von Ausnahmen für bestimmte Benutzer in einer Organisation</span><span class="sxs-lookup"><span data-stu-id="7a4f3-158">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="7a4f3-159">Wenn Sie möchten, dass bestimmte Gruppen URLs anzeigen können, die möglicherweise für andere Personen blockiert wurden, können Sie eine Richtlinie für ATP-sichere Links angeben, die für bestimmte Empfänger gilt.</span><span class="sxs-lookup"><span data-stu-id="7a4f3-159">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="7a4f3-160">Weitere Informationen finden Sie unter [Einrichten einer benutzerdefinierten Liste "URLs nicht umschreiben" unter Verwendung von ATP-Safe-Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="7a4f3-160">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
