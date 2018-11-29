---
title: SharePoint Online-Website für streng vertraulich digitale Objekte der Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: 'Zusammenfassung: Wie für eine SharePoint Online-Website von Contoso stark implementiert teams regulierte Daten für einfachere Zusammenarbeit zwischen den Research.'
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868150"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="9d73f-103">SharePoint Online-Website für streng vertraulich digitale Objekte der Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="9d73f-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="9d73f-104">**Zusammenfassung:** Contoso hat wie eine SharePoint Online-Website für stark regulierten Daten für einfachere Zusammenarbeit zwischen den Teams Research implementiert.</span><span class="sxs-lookup"><span data-stu-id="9d73f-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="9d73f-p101">Wichtigsten Ressourcen von Contoso sind dessen Rechte an geistigem Eigentum in Form von Geschäftsgeheimnissen wie proprietäre Fertigung Techniken, und Entwerfen Spezifikationen von Produkten, die bei der Entwicklung sind. Diese Objekte sind in digitaler Form, die ursprünglich als Dateien auf einer SharePoint Server 2016-Website gespeichert. Bei Contoso Microsoft 365 Enterprise bereitgestellt haben, sollte damit ihre lokale digitaler Objekte in die Cloud für leichteren Zugriff und anfälliger für die Zusammenarbeit über Research Teams in Paris, Moskau, New York, Peking und Bangalore umzustellen.</span><span class="sxs-lookup"><span data-stu-id="9d73f-p101">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development. These assets are in digital form, originally stored as files on a SharePoint Server 2016 site. When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="9d73f-108">Aufgrund der sensiblen Daten, muss jedoch Zugriff auf diese Dateien werden:</span><span class="sxs-lookup"><span data-stu-id="9d73f-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="9d73f-109">Klicken Sie auf die Gruppe von Personen, die berechtigt sind, anzeigen oder ändern, mit dem laufenden Berechtigungen für die Website nur von SharePoint-Administratoren verwaltet beschränkt.</span><span class="sxs-lookup"><span data-stu-id="9d73f-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="9d73f-110">Geschützte mit Data Loss Prevention (DLP) verhindert, dass Benutzer außerhalb der Website verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="9d73f-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="9d73f-111">Verschlüsselte und geschützt mit Access Zugriffssteuerungslisten zu verhindern, dass der nicht autorisierte Benutzer den Zugriff auf ihre Inhalte, auch wenn sie außerhalb des Standorts verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="9d73f-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="9d73f-112">Sicherheit und SharePoint-Administratoren in Contoso des IT-Abteilung entschieden, eine [SharePoint Online-Website für stark regulierter Daten](teams-sharepoint-online-sites-highly-regulated-data.md)zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d73f-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="9d73f-113">Contoso verwendet diese Schritte zum Erstellen und Sichern eine SharePoint Online Teamwebsites für ihre Research-Teams.</span><span class="sxs-lookup"><span data-stu-id="9d73f-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="9d73f-114">Schritt 1: Überprüft und die Mitglieder einer Gruppe von Research Team überprüft</span><span class="sxs-lookup"><span data-stu-id="9d73f-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="9d73f-p102">Contoso-IT-Administratoren einen Überblick über den Satz von Sicherheitsgruppen für ihre Teams Research ausgeführt. Diese entfernt Personen war keine Interviewer oder nicht benötigen Zugriff auf Research-Objekte.</span><span class="sxs-lookup"><span data-stu-id="9d73f-p102">Contoso IT admins performed a review of the set of security groups for their research teams. They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="9d73f-117">Sie auch und diese neue Sicherheitsgruppen erstellt:</span><span class="sxs-lookup"><span data-stu-id="9d73f-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="9d73f-118">**Research-Admins**  Der Satz von SharePoint-Administratoren, die vollständige Kontrolle über die Website, einschließlich der Möglichkeit zum Ändern der Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="9d73f-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="9d73f-119">**Research-Member**  Der Satz von Sicherheitsgruppen für die Research Teams auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="9d73f-119">**Research Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="9d73f-120">**Research-Viewer**  Der Satz von Management-Benutzer, wie die Führungskräfte in der Organisation Research, die die Anlagen auf der Website anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="9d73f-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="9d73f-121">Schritt 2: Erstellt eine isolierte SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="9d73f-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="9d73f-p103">**Namens Contoso SharePoint-Administratoren, die zuerst erstellt eine neue Teamwebsite.** Diese dann konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="9d73f-p103">Contoso SharePoint admins first created a new team site named **Research**. They then configured:</span></span>

- <span data-ttu-id="9d73f-124">Die Berechtigungsstufe Vollzugriff auf die Research Besitzer SharePoint-Gruppe verwenden, die die Sicherheitsgruppe **"Research-Admins"** als Mitglied aufweist</span><span class="sxs-lookup"><span data-stu-id="9d73f-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="9d73f-125">Die Berechtigungsstufe bearbeiten die Research Mitglieder SharePoint-Gruppe verwenden, die die Sicherheitsgruppe **Research Mitglieder** als Mitglied aufweist</span><span class="sxs-lookup"><span data-stu-id="9d73f-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="9d73f-126">Die Berechtigungsstufe lesen, um die Research Besucher von SharePoint-Gruppe verwenden, die als Mitglied die **Research-Viewer** -Sicherheitsgruppe verfügt</span><span class="sxs-lookup"><span data-stu-id="9d73f-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="9d73f-127">Hier sind die resultierenden SharePoint-Berechtigungsstufen, SharePoint-Gruppen und deren Member.</span><span class="sxs-lookup"><span data-stu-id="9d73f-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="9d73f-128">Im nächsten Schritt konfiguriert sie zusätzliche Einschränkungen für die Website.</span><span class="sxs-lookup"><span data-stu-id="9d73f-128">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="9d73f-129">Die Konfigurationsdetails finden Sie unter [Bereitstellen einer isolierten SharePoint Online-Teamwebsite](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span><span class="sxs-lookup"><span data-stu-id="9d73f-129">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a><span data-ttu-id="9d73f-130">Schritt 3: Konfiguriert die Website für eine eingeschränkte Office 365 Bezeichnung DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="9d73f-130">Step 3: Configured the site for a restrictive Office 365 label DLP policy</span></span>

<span data-ttu-id="9d73f-131">"Contoso Admins" wird zuerst die Bezeichnung des **Streng vertraulich** Office 365 zu der Website **Research** angewendet.</span><span class="sxs-lookup"><span data-stu-id="9d73f-131">First, Contoso admins applied the **Highly Confidential** Office 365 label to the **Research** site.</span></span>

<span data-ttu-id="9d73f-132">Erstellt im nächsten Schritt eine neue Office 365 DLP-Richtlinie mit dem Namen **Research** , die:</span><span class="sxs-lookup"><span data-stu-id="9d73f-132">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="9d73f-133">Verwendet die **Streng vertraulich** Office 365-Beschriftung.</span><span class="sxs-lookup"><span data-stu-id="9d73f-133">Uses the **Highly Confidential** Office 365 label.</span></span> 
- <span data-ttu-id="9d73f-134">Wird auf der Website **Research** angewendet.</span><span class="sxs-lookup"><span data-stu-id="9d73f-134">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="9d73f-135">Verhindert, dass Benutzer Dokumente freigeben.</span><span class="sxs-lookup"><span data-stu-id="9d73f-135">Prevents users from sharing documents.</span></span>

<span data-ttu-id="9d73f-136">Die Konfigurationsdetails finden Sie unter [Schützen von SharePoint Online-Dateien mit Office 365 Etiketten und DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="9d73f-136">For the configuration details, see [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="9d73f-137">Schritt 4: Erstellt eine untergeordnete Azure Information Protection Beschriftung für die Website</span><span class="sxs-lookup"><span data-stu-id="9d73f-137">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="9d73f-138">"Contoso Admins" erstellt eine neue Azure Information Protection untergeordnete Beschriftung mit dem Namen **Research** der standardmäßigen **Streng vertraulich** Beschriftung in einer bereichsbezogenen Richtlinie, die:</span><span class="sxs-lookup"><span data-stu-id="9d73f-138">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="9d73f-139">Verschlüsselung ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9d73f-139">Requires encryption.</span></span>
- <span data-ttu-id="9d73f-140">Ermöglicht den Vollzugriff durch ein Mitglied der Sicherheitsgruppe **Research Mitglieder** .</span><span class="sxs-lookup"><span data-stu-id="9d73f-140">Allows full access by members of the **Research Members** security group.</span></span>
- <span data-ttu-id="9d73f-141">Ermöglicht den Lesezugriff durch ein Mitglied der Sicherheitsgruppe **Research Leser von Berichten** .</span><span class="sxs-lookup"><span data-stu-id="9d73f-141">Allows read access by members of the **Research Viewers** security group.</span></span>

<span data-ttu-id="9d73f-142">Im nächsten Schritt bereitgestellt sie Azure Information Protection-Client für die Geräte der Teammitglieder Research.</span><span class="sxs-lookup"><span data-stu-id="9d73f-142">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="9d73f-143">Die Konfigurationsdetails finden Sie unter [Schützen von SharePoint Online-Dateien mit Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="9d73f-143">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="9d73f-144">Hier ist die resultierende Konfiguration der Website **Research** für streng vertraulich Objekte.</span><span class="sxs-lookup"><span data-stu-id="9d73f-144">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="9d73f-145">Schritt 5: Migriert Research lokale SharePoint-Daten</span><span class="sxs-lookup"><span data-stu-id="9d73f-145">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="9d73f-146">"Contoso Admins" verschoben, dass alle von der lokalen Dateien in der lokalen SharePoint Server 2016 Website in Ordnern in die neue **Research** SharePoint Online-Website Recherchieren.</span><span class="sxs-lookup"><span data-stu-id="9d73f-146">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="9d73f-147">Schritt 6: Geschulte ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="9d73f-147">Step 6: Trained their users</span></span> 

<span data-ttu-id="9d73f-148">Contoso Sicherheit Mitarbeiter geschult die Research Teams ein obligatorisch Kurs, der über diese schrittweise durchlaufen:</span><span class="sxs-lookup"><span data-stu-id="9d73f-148">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="9d73f-149">Wie Sie auf die neue **Research** SharePoint Online-Website und die vorhandenen Dateien zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9d73f-149">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="9d73f-150">Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="9d73f-150">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="9d73f-151">Veranschaulicht die Erstellung blockiert die DLP-Richtlinie Dateien extern freigegeben.</span><span class="sxs-lookup"><span data-stu-id="9d73f-151">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="9d73f-152">Wie Sie mit der Azure Information Protection Client Research-Dateien mit der untergeordneten **Research** Bezeichnung bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="9d73f-152">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="9d73f-153">Veranschaulicht die Erstellung schützt **Research** untergeordnete Beschriftung eine Datei, auch wenn es von der Website offengelegt werden.</span><span class="sxs-lookup"><span data-stu-id="9d73f-153">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="9d73f-154">Das Ergebnis ist eine sichere Umgebung, in der die Forscher in der gesamten Organisation in einer sicheren Umgebung zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="9d73f-154">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="9d73f-155">Wenn ein Research-Dokument mit der untergeordneten **Research** Bezeichnung aus der Website **Research** offengelegt werden, ist es verschlüsselte und können nur Mitglieder der Sicherheitsgruppen **Research Elemente** und **Research Leser von Berichten** mit gültigen Anmeldeinformationen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9d73f-155">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research Members** and **Research Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="9d73f-156">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="9d73f-156">Next step</span></span>

<span data-ttu-id="9d73f-157">[Bereitstellen](deploy-microsoft-365-enterprise.md) von Microsoft 365 Enterprise in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9d73f-157">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

