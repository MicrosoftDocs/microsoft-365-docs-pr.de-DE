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
description: In diesem Artikel erfahren Sie, wie Sie eine Liste blockierter URLs für Ihre Organisation mit Office 365 Advanced Threat Protection einrichten. Die gesperrten URLs gelten für e-Mail-Nachrichten und Office-Dokumente gemäß ihren ATP-Richtlinien für sichere Links.
ms.openlocfilehash: ff8709a8bf0f8afc27ace2b3977be975f42c33a5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638404"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="20662-104">Einrichten einer benutzerdefinierten Liste blockierter URLs mithilfe von ATP-Sicherheits Links</span><span class="sxs-lookup"><span data-stu-id="20662-104">Set up a custom blocked URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20662-105">Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="20662-105">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="20662-106">Wenn Sie ein Privatbenutzer sind, der nach Informationen zu sicheren Links in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="20662-106">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="20662-107">Mit [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kann Ihre Organisation eine benutzerdefinierte Liste der blockierten Websiteadressen (URLs) haben.</span><span class="sxs-lookup"><span data-stu-id="20662-107">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="20662-108">Wenn eine URL blockiert wird, werden Personen, die auf Links zur gesperrten URL klicken, zu einer [Warnungsseite](atp-safe-links-warning-pages.md) geleitet, die dem folgenden Bild ähnelt:</span><span class="sxs-lookup"><span data-stu-id="20662-108">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![Diese Website ist blockiert](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="20662-110">Die Liste Blockierte URLs wird vom Microsoft 365 for Business-Sicherheitsteam Ihrer Organisation definiert, und diese Liste gilt für alle Benutzer in der Organisation, die von Office 365 Richtlinien für ATP-sichere Links abgedeckt werden.</span><span class="sxs-lookup"><span data-stu-id="20662-110">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="20662-111">In diesem Artikel erfahren Sie, wie Sie die Liste der benutzerdefinierten blockierten URLs Ihrer Organisation für [ATP-sichere Links in Office 365](atp-safe-links.md)einrichten.</span><span class="sxs-lookup"><span data-stu-id="20662-111">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="20662-112">Anzeigen oder Bearbeiten einer benutzerdefinierten Liste blockierter URLs</span><span class="sxs-lookup"><span data-stu-id="20662-112">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="20662-113">[Für ATP-sichere Links in Office 365](atp-safe-links.md) werden mehrere Listen verwendet, einschließlich der Liste der benutzerdefinierten blockierten URLs in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="20662-113">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="20662-114">Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie die benutzerdefinierte Liste Ihrer Organisation einrichten.</span><span class="sxs-lookup"><span data-stu-id="20662-114">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="20662-115">Hierzu bearbeiten Sie die Standardrichtlinie für sichere Links in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="20662-115">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="20662-116">Um ATP-Richtlinien zu bearbeiten oder zu definieren, müssen Sie einer der in der folgenden Tabelle beschriebenen Rollen zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="20662-116">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="20662-117">Rolle</span><span class="sxs-lookup"><span data-stu-id="20662-117">Role</span></span>  |<span data-ttu-id="20662-118">Wo/wie zugewiesen</span><span class="sxs-lookup"><span data-stu-id="20662-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="20662-119">globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="20662-119">global administrator</span></span> |<span data-ttu-id="20662-120">Die Person, die sich zum Kauf von Microsoft 365 anmeldet, ist standardmäßig ein globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="20662-120">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="20662-121">(Weitere Informationen finden Sie unter [Informationen zu Microsoft 365-Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .)</span><span class="sxs-lookup"><span data-stu-id="20662-121">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="20662-122">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="20662-122">Security Administrator</span></span> |<span data-ttu-id="20662-123">Azure Active Directory Admin Center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="20662-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="20662-124">Exchange Online-Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="20662-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="20662-125">Exchange Admin Center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="20662-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="20662-126">oder</span><span class="sxs-lookup"><span data-stu-id="20662-126">or</span></span> <br>  <span data-ttu-id="20662-127">PowerShell-Cmdlets (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="20662-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span> |

> [!TIP]
> <span data-ttu-id="20662-128">Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="20662-128">To learn more about roles and permissions, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="20662-129">So zeigen Sie eine benutzerdefinierte Liste blockierter URLs an oder bearbeiten Sie</span><span class="sxs-lookup"><span data-stu-id="20662-129">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="20662-130">Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="20662-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="20662-131">Wählen Sie im linken Navigationsbereich unter **Threat Management**die Option **Richtlinien** \> **sichere Links**aus.</span><span class="sxs-lookup"><span data-stu-id="20662-131">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="20662-132">Wählen Sie in den **Richtlinien für den Abschnitt gesamte Organisation** die Option **Standard**aus, und klicken Sie dann auf **Bearbeiten** (die Schaltfläche Bearbeiten ähnelt einem Bleistift).</span><span class="sxs-lookup"><span data-stu-id="20662-132">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="20662-133">![Klicken Sie auf Bearbeiten, um die Standardrichtlinie für den Schutz von sicheren Links zu bearbeiten.](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="20662-133">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="20662-134">Auf diese Weise können Sie die Liste der blockierten URLs anzeigen.</span><span class="sxs-lookup"><span data-stu-id="20662-134">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="20662-135">Auf den ersten sind hier möglicherweise keine URLs aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="20662-135">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="20662-136">![Liste der blockierten URLs in der Standardrichtlinie für sichere Links](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="20662-136">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="20662-137">Aktivieren Sie das Kontrollkästchen **gültige URL eingeben** , geben Sie eine URL ein, und klicken Sie dann**+** auf das Pluszeichen ().</span><span class="sxs-lookup"><span data-stu-id="20662-137">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="20662-138">Wenn Sie das Hinzufügen von URLs abgeschlossen haben, wählen Sie in der unteren rechten Ecke des Bildschirms **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="20662-138">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="20662-139">Einige Dinge, die Sie beachten sollten</span><span class="sxs-lookup"><span data-stu-id="20662-139">A few things to keep in mind</span></span>

<span data-ttu-id="20662-140">Achten Sie beim Hinzufügen von URLs zu Ihrer Liste darauf, Folgendes zu beachten:</span><span class="sxs-lookup"><span data-stu-id="20662-140">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="20662-141">Fügen Sie am Ende der URL keinen **/** Schrägstrich () ein.</span><span class="sxs-lookup"><span data-stu-id="20662-141">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="20662-142">Geben Sie beispielsweise anstatt Eingabe `https://www.contoso.com/`ein ein `https://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="20662-142">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>
    
- <span data-ttu-id="20662-143">Sie können eine nur-Domänen-URL angeben ( `contoso.com` wie `tailspintoys.com`oder).</span><span class="sxs-lookup"><span data-stu-id="20662-143">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="20662-144">Dadurch wird das Klicken auf eine URL blockiert, die die Domäne enthält.</span><span class="sxs-lookup"><span data-stu-id="20662-144">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="20662-145">Sie können eine Unterdomäne (like `toys.contoso.com*`) angeben, ohne eine vollständige Domäne ( `contoso.com`like) zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="20662-145">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="20662-146">Dadurch wird das Klicken auf eine URL blockiert, die die Unterdomäne enthält, es werden jedoch keine Klicks auf eine URL blockiert, die die vollständige Domäne enthält.</span><span class="sxs-lookup"><span data-stu-id="20662-146">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="20662-147">Sie können bis zu drei Platzhalter Sternchen (\*) pro URL hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="20662-147">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="20662-148">In der folgenden Tabelle sind einige Beispiele aufgeführt, die Sie eingeben können und welche Auswirkungen diese Einträge haben.</span><span class="sxs-lookup"><span data-stu-id="20662-148">The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="20662-149">**Beispieleintrag**</span><span class="sxs-lookup"><span data-stu-id="20662-149">**Example Entry**</span></span>|<span data-ttu-id="20662-150">**Funktionsweise**</span><span class="sxs-lookup"><span data-stu-id="20662-150">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="20662-151">`contoso.com` oder `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="20662-151">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="20662-152">Blockiert die Domäne, Unterdomänen und Pfade, wie `https://www.contoso.com`, und `https://sub.contoso.com``https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="20662-152">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>  <br/> |
|`https://contoso.com/a`  <br/> |<span data-ttu-id="20662-153">Blockiert eine Website `https://contoso.com/a` , jedoch keine weiteren untergeordneten Pfade wie`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="20662-153">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>  <br/> |
|`https://contoso.com/a*`  <br/> |<span data-ttu-id="20662-154">Blockiert eine Website `https://contoso.com/a` und weitere untergeordnete Pfade wie`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="20662-154">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>  <br/> |
|`https://toys.contoso.com*`  <br/> |<span data-ttu-id="20662-155">Blockiert eine Unterdomäne ("Toys" in diesem Fall), aber Sie können Klicks auf andere Domänen- `https://contoso.com` URLs `https://home.contoso.com`(wie oder) zulassen.</span><span class="sxs-lookup"><span data-stu-id="20662-155">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="20662-156">Vorgehensweise definieren von Ausnahmen für bestimmte Benutzer in einer Organisation</span><span class="sxs-lookup"><span data-stu-id="20662-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="20662-157">Wenn Sie möchten, dass bestimmte Gruppen URLs anzeigen können, die möglicherweise für andere Personen blockiert wurden, können Sie eine Richtlinie für ATP-sichere Links angeben, die für bestimmte Empfänger gilt.</span><span class="sxs-lookup"><span data-stu-id="20662-157">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="20662-158">Weitere Informationen finden Sie unter [Einrichten einer benutzerdefinierten Liste "URLs nicht umschreiben" unter Verwendung von ATP-Safe-Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="20662-158">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

