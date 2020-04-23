---
title: Schützen von SharePoint Online-Dateien mit Azure Information Protection
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Zusammenfassung: Verwenden Sie Azure Information Protection zum Schützen von Dateien auf einer streng vertraulichen SharePoint Online-Teamwebsite.'
ms.openlocfilehash: 1c704689518da14bcabb56e81830b8456ebd2951
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632190"
---
# <a name="protect-sharepoint-online-files-with-azure-information-protection"></a><span data-ttu-id="ddbb2-103">Schützen von SharePoint Online-Dateien mit Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="ddbb2-103">Protect SharePoint Online files with Azure Information Protection</span></span>

>[!Note]
><span data-ttu-id="ddbb2-104">Die aktuelle Lösung für Dateien auf einer hochgradig vertraulichen SharePoint Online-Teamwebsite verwendet Microsoft 365-Vertraulichkeitsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-104">The current solution for files in a highly confidential SharePoint Online team site uses Microsoft 365 sensitivity labels.</span></span> <span data-ttu-id="ddbb2-105">Weitere Einzelheiten finden Sie in [diesem Artikel](protect-sharepoint-online-files-with-sensitivity-label.md).</span><span class="sxs-lookup"><span data-stu-id="ddbb2-105">Please see [this article](protect-sharepoint-online-files-with-sensitivity-label.md) for the details.</span></span>
>

<span data-ttu-id="ddbb2-p102">Konfigurieren Sie anhand der Schritte in diesem Artikel Azure Information Protection, um eine Verschlüsselung und Berechtigungen für Dateien bereitzustellen. Die Dateien können zu einer SharePoint-Bibliothek hinzugefügt werden, die für die Schutzebene „streng vertraulich“ konfiguriert wurde. Sie können eine Datei auch direkt über die Website öffnen und den Azure Information Protection-Client verwenden, um eine Verschlüsselung hinzuzufügen. Der Verschlüsselungs- und Berechtigungsschutz einer Datei bleibt auch dann bestehen, wenn die Datei von der Website heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-p102">Use the steps in this article to configure Azure Information Protection to provide encryption and permissions for files. These files can be added to a SharePoint library configured for highly confidential protection. Or, you can open a file directly from the site and use the Azure Information Protection client to add encryption. The encryption and permissions protection travels with a file even when it is downloaded from the site.</span></span> 

<span data-ttu-id="ddbb2-p103">Diese Schritte sind Teil einer umfangreicheren Lösung zur Konfiguration eines Schutzes streng vertraulicher Daten für SharePoint-Websites und die Dateien innerhalb dieser Websites. Weitere Informationen finden Sie unter [Sichern von SharePoint Online-Websites und -Dateien](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="ddbb2-p103">These steps are part of a larger solution for configuring highly confidential protection for SharePoint sites and the files within these sites. For more information, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span> 

<span data-ttu-id="ddbb2-112">Die Verwendung von Azure Information Protection für Dateien in SharePoint Online wird nicht für alle Benutzer empfohlen, sie ist jedoch eine Option für Kunden, die für eine Teilmenge von Dateien diese Ebene des Schutzes benötigen.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-112">Using Azure Information Protection for files in SharePoint Online is not recommended for all customers, but is an option for customers who need this level of protection for a subset of files.</span></span>

<span data-ttu-id="ddbb2-113">Einige wichtige Hinweise zu dieser Lösung:</span><span class="sxs-lookup"><span data-stu-id="ddbb2-113">Some important notes about this solution:</span></span>
- <span data-ttu-id="ddbb2-p104">Wenn Azure Information Protection-Verschlüsselung auf in Office 365 gespeicherte Dateien angewendet wird, kann der Dienst den Inhalt dieser Dateien nicht verarbeiten. Gemeinsame Dokumenterstellung, eDiscovery, Suche, Delve und andere Features für die Zusammenarbeit funktionieren nicht. DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) können nur auf die Metadaten (einschließlich Microsoft 365-Bezeichnungen) angewendet werden, aber nicht auf den Inhalt dieser Dateien (z. B. Kreditkartennummern in Dateien).</span><span class="sxs-lookup"><span data-stu-id="ddbb2-p104">When Azure Information Protection encryption is applied to files stored in Office 365, the service cannot process the contents of these files. Co-authoring, eDiscovery, search, Delve, and other collaborative features do not work. Data Loss Prevention (DLP) policies can only work with the metadata (including Microsoft 365 labels) but not the contents of these files (such as credit card numbers within files).</span></span>

- <span data-ttu-id="ddbb2-p105">Bei dieser Lösung muss ein Benutzer eine Bezeichnung auswählen, die den Schutz von Azure Information Protection anwendet. Wenn Sie eine automatische Verschlüsselung benötigen und SharePoint die Dateien indizieren und überprüfen soll, sollten Sie die Verwaltung von Informationsrechten (Information Rights Management, IRM) in SharePoint Online in Betracht ziehen. Wenn Sie eine SharePoint-Bibliothek für IRM konfigurieren, werden die Dateien automatisch beim Herunterladen für die Bearbeitung verschlüsselt. Für SharePoint IRM gelten einige Einschränkungen, die Ihre Entscheidung beeinflussen könnten. Weitere Informationen finden Sie unter [Einrichten von Information Rights Management (IRM) im SharePoint Admin Center](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).</span><span class="sxs-lookup"><span data-stu-id="ddbb2-p105">This solution requires a user to select a label that applies the protection from Azure Information Protection. If you require automatic encryption and the ability for SharePoint to index and inspect the files, consider using Information Rights Management (IRM) in SharePoint Online. When you configure a SharePoint library for IRM, files are automatically encrypted when they are downloaded for editing.  SharePoint IRM includes limitations that might influence your decision. For more information, see [Set up Information Rights Management (IRM) in SharePoint admin center](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).</span></span>

## <a name="admin-setup"></a><span data-ttu-id="ddbb2-122">Einrichten eines Administrators</span><span class="sxs-lookup"><span data-stu-id="ddbb2-122">Admin setup</span></span>
<span data-ttu-id="ddbb2-123">Führen Sie zuerst die Anleitungen unter [Aktivieren von Azure RMS mit Microsoft 365 Admin Center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) für Ihr Microsoft 365-Abonnement aus.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-123">First, use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) for your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="ddbb2-124">Konfigurieren Sie anschließend Azure Information Protection mit einer neuen bereichsbezogenen Richtlinie und einer untergeordneten Bezeichnung mit dem Schutz und den Berechtigungen für die streng vertrauliche SharePoint Online-Teamwebsite.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-124">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions of your highly confidential SharePoint Online team site.</span></span>
  
1. <span data-ttu-id="ddbb2-125">Melden Sie sich beim Admin Center mit einem Konto an, das über die Rolle „Sicherheitsadministrator" oder Unternehmensadministrator" verfügt.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-125">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="ddbb2-126">Hilfe finden Sie unter [Where to sign in to Office 365 (Wo kann ich mich bei Office 365 anmelden?)](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="ddbb2-126">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="ddbb2-127">Wechseln Sie auf einer separaten Registerkarte im Browser zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="ddbb2-127">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
4. <span data-ttu-id="ddbb2-128">Geben Sie im Suchfeld die **Information** ein, klicken Sie dann auf **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-128">In the search box, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="ddbb2-129">Klicken Sie auf **Etiketten**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-129">Click **Labels**.</span></span>
    
6. <span data-ttu-id="ddbb2-130">Klicken Sie mit der rechten Maustaste auf die Bezeichnung **Streng vertraulich**, und klicken Sie dann auf **Unterbezeichnung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-130">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="ddbb2-131">Geben Sie unter **Name** einen Namen für die Unterbezeichnung und unter **Beschreibung** eine Beschreibung für die Unterbezeichnung ein.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-131">Type a name for the sub-label in **Name** and a description of the sub-label in **Description**.</span></span>
    
8. <span data-ttu-id="ddbb2-132">Klicken Sie unter **Berechtigungen für Dokumente und E-Mails mit dieser Bezeichnung festlegen** auf **Schützen**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-132">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="ddbb2-133">Klicken Sie im Abschnitt **Schutz** auf **Azure (Cloudschlüssel)**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-133">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="ddbb2-134">Klicken Sie auf dem Blatt **Schutz** unter **Schutzeinstellungen** auf **Berechtigungen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-134">On the **Protection** blade, under **Protection settings**, click **Add permissions**.</span></span>
    
11. <span data-ttu-id="ddbb2-135">Klicken Sie auf dem Blatt **Berechtigungen hinzufügen** unter **Benutzer und Gruppen angeben** auf **Verzeichnis durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-135">On the **Add permissions** blade, under **Specify users and groups**, click **Browse directory**.</span></span>
    
12. <span data-ttu-id="ddbb2-136">Wählen Sie im Bereich **AAD-Benutzer und -Gruppen** die Websitemitglieder-Zugriffsgruppe für Ihre streng vertrauliche SharePoint Online-Teamwebsite aus, und klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-136">On the **AAD Users and Groups** pane, select the site members access group for your highly sensitive SharePoint Online team site, and then click **Select**.</span></span>
    
13. <span data-ttu-id="ddbb2-137">Klicken Sie unter **Aus voreingestellten Berechtigungen wählen oder Benutzerdefiniert festlegen** auf **Benutzerdefiniert**, und aktivieren Sie dann die Kontrollkästchen **Rechte anzeigen**, **Inhalt bearbeiten**, \*\* Speichern\*\*, **Antworten** und **Allen antworten**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-137">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="ddbb2-138">Klicken Sie zweimal auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-138">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="ddbb2-139">Klicken Sie auf dem Blatt **Untergeordnete Bezeichnung** auf **Speichern** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-139">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="ddbb2-140">Klicken Sie auf dem Blatt **Azure Information Protection** auf **Richtlinien > + Neue Richtlinie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-140">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="ddbb2-141">Geben Sie unter **Richtlinienname** einen Namen für die neue Richtlinie und unter **Beschreibung** eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-141">Type a name for the new policy in **Policy name** and a description in **Description**.</span></span>
    
18. <span data-ttu-id="ddbb2-142">Klicken Sie auf **Auswählen, welche Benutzer oder Gruppen diese Richtlinie erhalten > Benutzer/Gruppen**, und wählen Sie dann die Websitemitglieder-Zugriffsgruppe für Ihre streng vertrauliche SharePoint Online-Teamwebsite aus.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-142">Click **Select which users or groups get this policy > User/Groups**, and then select the site members access group for your highly sensitive SharePoint Online team site.</span></span>
    
19. <span data-ttu-id="ddbb2-143">Klicken Sie auf **Auswählen > OK**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-143">Click **Select > OK**.</span></span>

20. <span data-ttu-id="ddbb2-p107">Klicken Sie auf **Bezeichnungen hinzufügen oder entfernen**. Klicken Sie im Bereich **Richtlinie: Bezeichnungen hinzufügen oder entfernen** auf den Namen Ihrer neuen Unterbezeichnung und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-p107">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click the name of your new sub-label, and then click **OK**.</span></span>   

21. <span data-ttu-id="ddbb2-146">Klicken Sie auf **Speichern** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-146">Click **Save**, and then click **OK**.</span></span>
 
## <a name="client-setup"></a><span data-ttu-id="ddbb2-147">Einrichten eines Clients</span><span class="sxs-lookup"><span data-stu-id="ddbb2-147">Client setup</span></span>
<span data-ttu-id="ddbb2-148">Sie können jetzt damit beginnen, Dokumente zu erstellen und diese mit Azure Information Protection und der neuen Bezeichnung zu schützen.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-148">You are now ready to begin creating documents and protecting them with Azure Information Protection and your new label.</span></span>
  
<span data-ttu-id="ddbb2-p108">Sie müssen den [Azure Information Protection-Client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) auf Ihrem Gerät oder Ihrem Windows-Computer installieren. Sie können ein Skript erstellen und die Installation automatisieren, oder Benutzer können den Client manuell installieren. Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="ddbb2-p108">You must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on your device or Windows-based computer. You can script and automate the installation, or users can install the client manually. See the following resources:</span></span>
  
- [<span data-ttu-id="ddbb2-152">Die Clientseite von Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="ddbb2-152">The client side of Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/rms-client/use-client)
    
- [<span data-ttu-id="ddbb2-153">Installieren des Azure Information Protection-Clients</span><span class="sxs-lookup"><span data-stu-id="ddbb2-153">Installing the Azure Information Protection client</span></span>](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
    
- [<span data-ttu-id="ddbb2-154">Downloadseite für die manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="ddbb2-154">Download page for manual installation</span></span>](https://www.microsoft.com/download/details.aspx?id=53018)
    
<span data-ttu-id="ddbb2-p109">Nach der Installation führen Ihre Benutzer eine Office-Anwendung (z. B. Microsoft Word) aus und melden sich von dort aus mit Ihrem Microsoft 365-Konto an. Die neue Symbolleiste **Information Protection** ermöglicht es Benutzern, die neue Bezeichnung auszuwählen. Stellen Sie sicher, dass Ihre Benutzer die SharePoint Online-Teamwebsite kennen und wissen, welche Bezeichnung sie verwenden müssen, um ihre streng vertraulichen Dateien zu schützen.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-p109">Once installed, your users run and then sign-in from an Office application (such as Microsoft Word) with their Microsoft 365 account. A new **Information Protection** bar allows users to select the new label. Make sure that your users know the SharePoint Online team site and which label to use, to protect their highly confidential files.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ddbb2-158">Wenn Sie über mehrere streng vertrauliche SharePoint Online-Teamwebsites verfügen, müssen Sie anhand der oben aufgeführten Einstellungen mehrere bereichsbezogene Azure Information Protection-Richtlinien mit Unterbezeichnungen erstellen, wobei die Berechtigungen für jede Unterbezeichnung auf die Websitemitglieder-Zugriffsgruppe einer bestimmten SharePoint Online-Teamwebsite festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-158">If you have multiple highly sensitive SharePoint Online team sites, you should create multiple Azure Information Protection scoped policies with sub-labels with the above settings, with the permissions for each sub-label set to the site members access group of a specific SharePoint Online team site.</span></span> 
  
## <a name="adding-permissions-for-external-users"></a><span data-ttu-id="ddbb2-159">Hinzufügen von Berechtigungen für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="ddbb2-159">Adding permissions for external users</span></span>
<span data-ttu-id="ddbb2-p110">Es gibt zwei Möglichkeiten, wie Sie externen Benutzern Zugriff auf Dateien gewähren können, die mit Azure Information Protection geschützt sind. In beiden Fällen benötigen die externen Benutzer ein Azure AD-Konto. Wenn externe Benutzer kein Mitglied einer Organisation sind, die Azure Active Directory verwendet, können sie auf dieser Registrierungsseite ein Azure AD-Konto als Einzelperson beantragen: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span><span class="sxs-lookup"><span data-stu-id="ddbb2-p110">There are two ways you can grant external users access to files protected with Azure Information Protection. In both cases, external users must have an Azure AD account. If external users aren't members of an organization that uses Azure AD, they can obtain an Azure AD account as an individual by using this signup page: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span></span>

 - <span data-ttu-id="ddbb2-163">Hinzufügen von externen Benutzern zu einer Azure AD-Gruppe, die zum Konfigurieren des Schutzes für eine Bezeichnung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-163">Add external users to an Azure AD group that is used to configure protection for a label.</span></span> <span data-ttu-id="ddbb2-164">Sie müssen zuerst das Konto als B2B-Benutzer in Ihrem Verzeichnis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-164">You'll need to first add the account as a B2B user in your directory.</span></span> <span data-ttu-id="ddbb2-165">Das [Zwischenspeichern einer Gruppenmitgliedschaft durch Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection) kann einige Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-165">It can take a couple of hours for [group membership caching by Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection).</span></span>  
 - <span data-ttu-id="ddbb2-p112">Direktes Hinzufügen von externen Benutzern zum Bezeichnungsschutz. Sie können alle Benutzer aus einer Organisation (z. B. „Fabrikam.com“), eine Azure AD-Gruppe (z. B. eine Finanzgruppe innerhalb einer Organisation) oder einen Benutzer hinzufügen. Sie können beispielsweise ein externes Team von Aufsichtsbeamten zum Schutz für eine Bezeichnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-p112">Add external users directly to the label protection. You can add all users from an organization (e.g. Fabrikam.com), an Azure AD group (such as a finance group within an organization), or user. For example, you can add an external team of regulators to the protection for a label.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddbb2-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddbb2-169">See Also</span></span>

[<span data-ttu-id="ddbb2-170">Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützigen Organisationen und andere agile Organisationen</span><span class="sxs-lookup"><span data-stu-id="ddbb2-170">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="ddbb2-171">Cloudakzeptanz und Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="ddbb2-171">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
