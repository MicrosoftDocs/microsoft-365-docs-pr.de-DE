---
title: Erstellen eines B2B-Extranets mit verwalteten Gästen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Erfahren Sie, wie Sie eine B2B-Extranetwebsite oder ein Team mit verwalteten Gästen aus einer Partnerorganisation erstellen.
ms.openlocfilehash: f9b8d9326f302233ed85c9d168fdf6f343dc6cbf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904756"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="d590d-103">Erstellen eines B2B-Extranets mit verwalteten Gästen</span><span class="sxs-lookup"><span data-stu-id="d590d-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="d590d-104">Sie können Azure Active Directory [Berechtigungsverwaltung](/azure/active-directory/governance/entitlement-management-overview) verwenden, um ein B2B-Extranet für die Zusammenarbeit mit einer Partnerorganisation zu erstellen, die Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d590d-104">You can use [Azure Active Directory Entitlement Management](/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="d590d-105">Auf diese Weise können sich Benutzer selbst für die Extranetwebsite oder das Extranetteam registrieren und über einen Genehmigungsworkflow Zugriff erhalten.</span><span class="sxs-lookup"><span data-stu-id="d590d-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="d590d-106">Mit dieser Methode der Freigabe von Ressourcen für die Zusammenarbeit kann die Partnerorganisation dazu beitragen, die Gäste am Ende zu warten und zu genehmigen, die Belastung Für Ihre IT-Abteilung zu reduzieren und denjenigen, die mit der Zusammenarbeitsvereinbarung vertraut sind, die Verwaltung des Benutzerzugriffs zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d590d-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="d590d-107">In diesem Artikel werden die Schritte zum Erstellen eines Ressourcenpakets (in diesem Fall einer Website oder eines Teams) erläutert, das Sie über ein Self-Service-Zugriffsregistrierungsmodell für eine Partnerorganisation freigeben können.</span><span class="sxs-lookup"><span data-stu-id="d590d-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="d590d-108">Erstellen Sie vor Beginn die Website oder das Team, die Sie für die Partnerorganisation freigeben möchten, und aktivieren Sie sie für die Gastfreigabe.</span><span class="sxs-lookup"><span data-stu-id="d590d-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="d590d-109">Weitere [Informationen finden Sie unter Zusammenarbeiten](collaborate-in-site.md) mit Gästen in einer Website oder Zusammenarbeit mit Gästen [in](collaborate-as-team.md) einem Team.</span><span class="sxs-lookup"><span data-stu-id="d590d-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="d590d-110">Es wird außerdem [](create-secure-guest-sharing-environment.md) empfohlen, dass Sie erstellen eine sichere Umgebung für die Gastfreigabe für Informationen zu Sicherheits- und Compliancefeatures, die Sie verwenden können, um Ihre Steuerungsrichtlinien bei der Zusammenarbeit mit Gästen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="d590d-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="d590d-111">Lizenzanforderungen</span><span class="sxs-lookup"><span data-stu-id="d590d-111">License requirements</span></span>

<span data-ttu-id="d590d-112">Die Verwendung dieses Features erfordert eine Azure AD Premium P2-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="d590d-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="d590d-113">Spezielle Clouds wie Azure Deutschland und Azure China 21Vianet stehen derzeit nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d590d-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="d590d-114">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="d590d-114">Video demonstration</span></span>

<span data-ttu-id="d590d-115">In diesem Video werden die in diesem Artikel behandelten Verfahren veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d590d-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="d590d-116">Verbinden der Partnerorganisation</span><span class="sxs-lookup"><span data-stu-id="d590d-116">Connect the partner organization</span></span>

<span data-ttu-id="d590d-117">Zum Einladen von Gästen aus einer Partnerorganisation müssen Sie die Domäne des Partners als verbundene Organisation in einer Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d590d-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="d590d-118">So fügen Sie eine verbundene Organisation hinzu</span><span class="sxs-lookup"><span data-stu-id="d590d-118">To add a connected organization</span></span>
1. <span data-ttu-id="d590d-119">Klicken [Azure Active Directory](https://aad.portal.azure.com)in diesem Link auf **Identitätsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="d590d-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="d590d-120">Klicken Sie **auf Verbundene Organisationen**.</span><span class="sxs-lookup"><span data-stu-id="d590d-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="d590d-121">Klicken Sie **auf Verbundene Organisation hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d590d-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="d590d-122">Geben Sie einen Namen und eine Beschreibung für die Organisation ein, und klicken Sie dann auf **Weiter: Verzeichnis + Domäne**.</span><span class="sxs-lookup"><span data-stu-id="d590d-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="d590d-123">Klicken **Sie auf Verzeichnis + Domäne hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="d590d-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="d590d-124">Geben Sie die Domäne für die Organisation ein, die Sie verbinden möchten, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d590d-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="d590d-125">Klicken **Verbinden**, und klicken Sie dann auf **Weiter: Sponsoren**.</span><span class="sxs-lookup"><span data-stu-id="d590d-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="d590d-126">Fügen Sie Personen aus Ihrer Organisation oder der Organisation hinzu, mit denen Sie eine Verbindung herstellen, mit der Sie den Zugriff für Gäste genehmigen möchten.</span><span class="sxs-lookup"><span data-stu-id="d590d-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="d590d-127">Klicken Sie auf **Weiter: Überprüfen + erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d590d-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="d590d-128">Überprüfen Sie die von Ihnen ausgewählten Einstellungen, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d590d-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Screenshot der Seite verbundene Organisationen in Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="d590d-130">Auswählen der ressourcen, die gemeinsam verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="d590d-130">Choose the resources to share</span></span>

<span data-ttu-id="d590d-131">Der erste Schritt bei der Auswahl von Ressourcen, die für eine Partnerorganisation verwendet werden sollen, besteht in der Erstellung eines Katalogs, der sie enthält.</span><span class="sxs-lookup"><span data-stu-id="d590d-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="d590d-132">So erstellen Sie einen Katalog</span><span class="sxs-lookup"><span data-stu-id="d590d-132">To create a catalog</span></span>
1. <span data-ttu-id="d590d-133">Klicken [Azure Active Directory](https://aad.portal.azure.com)in diesem Link auf **Identitätsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="d590d-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="d590d-134">Klicken Sie **auf Kataloge**.</span><span class="sxs-lookup"><span data-stu-id="d590d-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="d590d-135">Klicken Sie **auf Neuer Katalog**.</span><span class="sxs-lookup"><span data-stu-id="d590d-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="d590d-136">Geben Sie einen Namen und eine Beschreibung für den Katalog ein, und stellen Sie sicher, dass **Enabled** und **Enabled** für externe Benutzer beide auf Ja **festgelegt sind.**</span><span class="sxs-lookup"><span data-stu-id="d590d-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="d590d-137">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d590d-137">Click **Create**.</span></span>

   ![Screenshot der Katalogseite in Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

<span data-ttu-id="d590d-139">Nachdem der Katalog erstellt wurde, fügen Sie die SharePoint oder das Team hinzu, die Sie für die Partnerorganisation freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="d590d-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="d590d-140">So fügen Sie einem Katalog Ressourcen hinzu</span><span class="sxs-lookup"><span data-stu-id="d590d-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="d590d-141">Klicken Sie in Azure AD Identity Governance auf **Kataloge,** und klicken Sie dann auf den Katalog, in dem Sie Ressourcen hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="d590d-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="d590d-142">Klicken Sie **auf Ressourcen,** und klicken Sie dann **auf Ressourcen hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="d590d-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="d590d-143">Wählen Sie die Teams oder SharePoint aus, die Sie in Ihr Extranet hinzufügen möchten, und klicken Sie dann auf **Hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="d590d-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Screenshot der Katalogressourcenseite in Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="d590d-145">Nachdem Sie die Ressourcen definiert haben, die Sie freigeben möchten, besteht der nächste Schritt im Erstellen eines Zugriffspakets, das den Typ des Zugriffs definiert, dem Partnerbenutzer gewährt werden, und den Genehmigungsprozess für neue Partnerbenutzer, die Zugriff anfordern.</span><span class="sxs-lookup"><span data-stu-id="d590d-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="d590d-146">So erstellen Sie ein Zugriffspaket</span><span class="sxs-lookup"><span data-stu-id="d590d-146">To create an access package</span></span>
1. <span data-ttu-id="d590d-147">Klicken Sie in Azure AD Identity Governance auf **Kataloge,** und klicken Sie dann auf den Katalog, in dem Sie ein Zugriffspaket erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d590d-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="d590d-148">Klicken **Sie auf Access-Pakete,** und klicken Sie dann auf **Neues Zugriffspaket**.</span><span class="sxs-lookup"><span data-stu-id="d590d-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="d590d-149">Geben Sie einen Namen und eine Beschreibung für das Zugriffspaket ein, und klicken Sie dann auf **Weiter: Ressourcenrollen**.</span><span class="sxs-lookup"><span data-stu-id="d590d-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="d590d-150">Wählen Sie die Ressourcen aus dem Katalog aus, den Sie für Ihr Extranet verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d590d-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="d590d-151">Wählen Sie für jede Ressource in der Spalte **Rolle** die Benutzerrolle aus, die Sie den Gästen gewähren möchten, die das Extranet verwenden.</span><span class="sxs-lookup"><span data-stu-id="d590d-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="d590d-152">Klicken **Sie auf Weiter: Anforderungen**.</span><span class="sxs-lookup"><span data-stu-id="d590d-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="d590d-153">Wählen **Sie unter Benutzer, die Zugriff anfordern können,** die Option **Für Benutzer nicht in Ihrem Verzeichnis aus.**</span><span class="sxs-lookup"><span data-stu-id="d590d-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="d590d-154">Stellen Sie **sicher, dass die** Option Spezifische verbundene Organisationen ausgewählt ist, und klicken Sie dann auf Verzeichnisse **hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="d590d-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="d590d-155">Wählen Sie die verbundene Organisation aus, die Sie zuvor hinzugefügt haben, und klicken Sie dann auf **Auswählen.**</span><span class="sxs-lookup"><span data-stu-id="d590d-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="d590d-156">Wählen **Sie unter Genehmigung** die Option **Ja** für Genehmigung **erforderlich aus.**</span><span class="sxs-lookup"><span data-stu-id="d590d-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="d590d-157">Wählen **Sie unter Erster** Genehmiger einen der Sponsoren aus, den Sie zuvor hinzugefügt haben, oder wählen Sie einen bestimmten Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="d590d-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="d590d-158">Klicken **Sie auf Fallback hinzufügen,** und wählen Sie eine Fallback genehmigende Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="d590d-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="d590d-159">Wählen **Sie unter Aktivieren** die Option Ja **aus.**</span><span class="sxs-lookup"><span data-stu-id="d590d-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="d590d-160">Klicken **Sie auf Weiter: Lebenszyklus**.</span><span class="sxs-lookup"><span data-stu-id="d590d-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="d590d-161">Wählen Sie die Einstellungen für Ablauf- und Zugriffsüberprüfung aus, die Sie verwenden möchten, und klicken Sie dann auf **Weiter: Überprüfen + Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d590d-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="d590d-162">Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d590d-162">Review your settings, and then click **Create**.</span></span>

    ![Screenshot des Zugriffspaketbildschirms in Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

<span data-ttu-id="d590d-164">Wenn Sie eine Partnerschaft mit einer großen Organisation haben, sollten Sie das Zugriffspaket ausblenden.</span><span class="sxs-lookup"><span data-stu-id="d590d-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="d590d-165">Wenn das Paket ausgeblendet ist, wird den Benutzern in der Partnerorganisation das Paket im *Portal My Access nicht* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d590d-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="d590d-166">Stattdessen müssen sie einen direkten Link erhalten, um sich für das Paket zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="d590d-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="d590d-167">Das Ausblenden des Zugriffspakets kann die Anzahl unangemessener Zugriffsanforderungen verringern und auch dazu beitragen, dass verfügbare Zugriffspakete im Portal der Partnerorganisation organisiert bleiben.</span><span class="sxs-lookup"><span data-stu-id="d590d-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="d590d-168">So legen Sie ein Zugriffspaket auf ausgeblendet</span><span class="sxs-lookup"><span data-stu-id="d590d-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="d590d-169">Klicken Sie in Azure AD Identity Governance auf **Access-Pakete,** und klicken Sie dann auf Ihr Zugriffspaket.</span><span class="sxs-lookup"><span data-stu-id="d590d-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="d590d-170">Klicken Sie **auf der Seite** Übersicht auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d590d-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="d590d-171">Wählen **Sie unter Eigenschaften** die Option **Ja** für **Ausgeblendet** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d590d-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Screenshot eines Zugriffspaketeigenschaftenbildschirms für den Bearbeitungszugriff](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="d590d-173">Einladen von Partnerbenutzern</span><span class="sxs-lookup"><span data-stu-id="d590d-173">Invite partner users</span></span>

<span data-ttu-id="d590d-174">Wenn Sie das Zugriffspaket auf ausgeblendet festlegen, müssen Sie einen direkten Link zur Partnerorganisation senden, damit diese Zugriff auf Ihre Website oder Ihr Team anfordern kann.</span><span class="sxs-lookup"><span data-stu-id="d590d-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="d590d-175">So suchen Sie den Link zum Zugriffsportal</span><span class="sxs-lookup"><span data-stu-id="d590d-175">To find the access portal link</span></span>
1. <span data-ttu-id="d590d-176">Klicken Sie in Azure AD Identity Governance auf **Access-Pakete,** und klicken Sie dann auf Ihr Zugriffspaket.</span><span class="sxs-lookup"><span data-stu-id="d590d-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="d590d-177">Klicken Sie **auf der Seite** Übersicht für den Link Mein **Access-Portal** auf In zwischenablage kopieren. </span><span class="sxs-lookup"><span data-stu-id="d590d-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Screenshot der Zugriffspaketeigenschaften mit Zugriffsportallink](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="d590d-179">Nachdem Sie den Link kopiert haben, können Sie ihn für Ihren Kontakt in der Partnerorganisation freigeben und an die Benutzer im Team für die Zusammenarbeit senden.</span><span class="sxs-lookup"><span data-stu-id="d590d-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="d590d-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d590d-180">See Also</span></span>

[<span data-ttu-id="d590d-181">Erstellen einer sicheren Umgebung für die Gastfreigabe</span><span class="sxs-lookup"><span data-stu-id="d590d-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)