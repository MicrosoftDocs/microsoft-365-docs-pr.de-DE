---
title: SharePoint Online Website für hoch vertrauliche digitale Objekte der Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Zusammenfassung: wie Contoso eine SharePoint Online Website für hochregulierte Daten implementiert, um die Zusammenarbeit zwischen den Forschungsteams zu vereinfachen.'
ms.openlocfilehash: 6c61d02c802a77afeb93a58b59114741c6630f9e
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369526"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="ab06d-103">SharePoint Online Website für hoch vertrauliche digitale Objekte der Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="ab06d-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="ab06d-104">**Zusammenfassung:** Wie Contoso eine SharePoint Online Website für hochregulierte Daten implementiert, um die Zusammenarbeit zwischen den Forschungsteams zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="ab06d-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="ab06d-105">Die wertvollsten Ressourcen von Contoso sind das geistige Eigentum in Form von Geschäftsgeheimnissen wie proprietäre Fertigungstechniken und Designspezifikationen für Produkte, die sich in der Entwicklung befinden.</span><span class="sxs-lookup"><span data-stu-id="ab06d-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="ab06d-106">Diese Objekte befinden sich in digitaler Form, werden ursprünglich als Dateien auf einer SharePoint Server 2016-Website gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ab06d-106">These assets are in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="ab06d-107">Bei der Bereitstellung von Microsoft 365 Enterprise durch Contoso wollten Sie Ihre lokalen digitalen Ressourcen für einen einfacheren Zugriff und eine offenere Zusammenarbeit zwischen den Forschungsteams in Paris, Moskau, New York, Beijing und Bangalore umstellen.</span><span class="sxs-lookup"><span data-stu-id="ab06d-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="ab06d-108">Aufgrund Ihrer sensiblen Natur muss der Zugriff auf diese Dateien jedoch wie folgt erfolgen:</span><span class="sxs-lookup"><span data-stu-id="ab06d-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="ab06d-109">Beschränkt auf die Gruppe von Personen, die Sie anzeigen oder ändern dürfen, mit laufenden Berechtigungen für die Website, die nur von SharePoint-Administratoren verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="ab06d-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="ab06d-110">Geschützt durch Datenverlust Verhinderung (DLP), um zu verhindern, dass Benutzer Sie außerhalb der Website verteilen.</span><span class="sxs-lookup"><span data-stu-id="ab06d-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="ab06d-111">Verschlüsselt und mit Zugriffssteuerungslisten geschützt, um zu verhindern, dass unbefugte Benutzer auf Ihre Inhalte zugreifen, auch wenn Sie außerhalb der Website verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="ab06d-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="ab06d-112">Sicherheits-und SharePoint-Administratoren in der IT-Abteilung von Contoso haben beschlossen, eine [SharePoint Online Website für hochregulierte Daten](teams-sharepoint-online-sites-highly-regulated-data.md)zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab06d-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="ab06d-113">Contoso hat diese Schritte zum Erstellen und Sichern einer SharePoint Online Teamwebsites für Ihre Forschungsteams verwendet.</span><span class="sxs-lookup"><span data-stu-id="ab06d-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="ab06d-114">Schritt 1: überprüfen und Überprüfen der Mitglieder der Gruppe "Forschungsteams"</span><span class="sxs-lookup"><span data-stu-id="ab06d-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="ab06d-115">Contoso IT-Administratoren haben eine Überprüfung der Gruppe von Sicherheitsgruppen für Ihre Forschungsteams durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="ab06d-115">Contoso IT admins performed a review of the set of security groups for their research teams.</span></span> <span data-ttu-id="ab06d-116">Sie haben alle Personen entfernt, die kein Forscher waren oder keinen Zugriff auf Forschungsressourcen benötigten.</span><span class="sxs-lookup"><span data-stu-id="ab06d-116">They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="ab06d-117">Außerdem wurden diese neuen Sicherheitsgruppen erstellt:</span><span class="sxs-lookup"><span data-stu-id="ab06d-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="ab06d-118">**Forschung-Administratoren**  Die Gruppe von SharePoint-Administratoren, die Vollzugriff auf die Website haben, einschließlich der Fähigkeit, Berechtigungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ab06d-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="ab06d-119">**Forschung-Mitglieder**  Die Gruppe von Sicherheitsgruppen für die Forschungsteams auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="ab06d-119">**Research-Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="ab06d-120">**Forschung-Betrachter**  Die Gruppe von Verwaltungs Benutzern wie Führungskräfte in der Forschungsorganisation, die nur die Objekte auf der Website anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="ab06d-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can only view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="ab06d-121">Schritt 2: Erstellen einer isolierten SharePoint Online Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="ab06d-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="ab06d-122">Contoso SharePoint-Administratoren haben zuerst eine neue Teamwebsite mit dem Namen **Research**erstellt.</span><span class="sxs-lookup"><span data-stu-id="ab06d-122">Contoso SharePoint admins first created a new team site named **Research**.</span></span> <span data-ttu-id="ab06d-123">Anschließend wurde Folgendes konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="ab06d-123">They then configured:</span></span>

- <span data-ttu-id="ab06d-124">Die Berechtigungsstufe "Vollzugriff" zur Verwendung der SharePoint-Gruppe "Research Owners" mit der Sicherheitsgruppe " **Research-Admins** " als Mitglied</span><span class="sxs-lookup"><span data-stu-id="ab06d-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="ab06d-125">Die Berechtigungsstufe "Bearbeiten" zur Verwendung der SharePoint-Gruppe "Forschungs Mitglieder" mit der Sicherheitsgruppe " **Forschungs Mitglieder** " als Mitglied</span><span class="sxs-lookup"><span data-stu-id="ab06d-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="ab06d-126">Die Berechtigungsstufe "lesen" zur Verwendung der SharePoint-Gruppe "Research Visitors" mit der Sicherheitsgruppe " **Research-Viewers** " als Mitglied</span><span class="sxs-lookup"><span data-stu-id="ab06d-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="ab06d-127">Im folgenden finden Sie die resultierenden SharePoint-Berechtigungsstufen, SharePoint-Gruppen und ihre Mitglieder.</span><span class="sxs-lookup"><span data-stu-id="ab06d-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![SharePoint-Berechtigungsstufen, SharePoint-Gruppen und ihre Mitglieder](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="ab06d-129">Als nächstes haben Sie zusätzliche Einschränkungen für die Website konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ab06d-129">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="ab06d-130">Informationen zu den Konfigurationsdetails finden Sie unter [Deploy an isolated SharePoint Online Team Site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span><span class="sxs-lookup"><span data-stu-id="ab06d-130">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="ab06d-131">Schritt 3: Konfigurieren der Website für eine restriktive DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ab06d-131">Step 3: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="ab06d-132">Zunächst wendeten Contoso-Administratoren die **streng vertrauliche** Office 365 Aufbewahrungs Bezeichnung für die **Forschungs** Website an.</span><span class="sxs-lookup"><span data-stu-id="ab06d-132">First, Contoso admins applied the **Highly Confidential** Office 365 retention label to the **Research** site.</span></span>

<span data-ttu-id="ab06d-133">Als nächstes haben Sie eine neue Office 365 DLP-Richtlinie mit dem Namen " **Forschung** " erstellt:</span><span class="sxs-lookup"><span data-stu-id="ab06d-133">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="ab06d-134">Verwendet die Office 365 Aufbewahrungs Bezeichnung mit **hoher Vertraulichkeit** .</span><span class="sxs-lookup"><span data-stu-id="ab06d-134">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="ab06d-135">Auf die **Forschungs** Website angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab06d-135">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="ab06d-136">Blockiert Benutzer, wenn Sie versuchen, ein digitales Objekt auf der **Forschungs** Website außerhalb von Contoso freizugeben.</span><span class="sxs-lookup"><span data-stu-id="ab06d-136">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="ab06d-137">Informationen zu den Konfigurationsdetails finden Sie unter [Protect SharePoint Online files with Retention Labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="ab06d-137">For the configuration details, see [Protect SharePoint Online files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="ab06d-138">Schritt 4: Erstellen einer Azure Information Protection-unter Bezeichnung für die Website</span><span class="sxs-lookup"><span data-stu-id="ab06d-138">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="ab06d-139">Contoso-Administratoren haben eine neue unter Bezeichnung für Azure Information Protection mit dem Namen **Research** of the Standard Label **highly Confidential** in einer bereichsbezogenen Richtlinie erstellt, die Folgendes umfasst:</span><span class="sxs-lookup"><span data-stu-id="ab06d-139">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="ab06d-140">Verschlüsselung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ab06d-140">Requires encryption.</span></span>
- <span data-ttu-id="ab06d-141">Ermöglicht den vollständigen Zugriff durch Mitglieder der Sicherheitsgruppe " **Research-Members** ".</span><span class="sxs-lookup"><span data-stu-id="ab06d-141">Allows full access by members of the **Research-Members** security group.</span></span>
- <span data-ttu-id="ab06d-142">Ermöglicht Lesezugriff durch Mitglieder der Sicherheitsgruppe " **Research-Viewers** ".</span><span class="sxs-lookup"><span data-stu-id="ab06d-142">Allows read access by members of the **Research-Viewers** security group.</span></span>

<span data-ttu-id="ab06d-143">Als nächstes haben Sie den Azure Information Protection-Client für die Geräte der Mitglieder des Forschungsteams bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ab06d-143">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="ab06d-144">Informationen zu den Konfigurationsdetails finden Sie unter [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="ab06d-144">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="ab06d-145">Hier ist die resultierende Konfiguration der **Forschungs** Website für streng vertrauliche Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="ab06d-145">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![Die resultierende Konfiguration des \* \* Research \* \*-Standorts für hoch vertrauliche Ressourcen](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="ab06d-147">Dateien in Ordnern der **Forschungs** Website sind geschützt durch:</span><span class="sxs-lookup"><span data-stu-id="ab06d-147">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="ab06d-148">Die unter Bezeichnung Azure Information Protection für **Forschung** , die Verschlüsselung und permssions auf jede Datei anwendet, die mit der Datei reist, wenn Sie von der **Forschungs** Website verschoben oder kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="ab06d-148">The **Research** Azure Information Protection sublabel, which applies encryption and permssions to each file that travel with the file when it is moved or copied from the **Research** site.</span></span>
- <span data-ttu-id="ab06d-149">Die DLP-Richtlinie für **Forschung** , die die **streng vertrauliche** Aufbewahrungs Bezeichnung und Einstellungen verwendet, die verhindern, dass die Datei für externe Benutzer freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ab06d-149">The **Research** DLP policy, which uses the **Highly Sensitive** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="ab06d-150">Die Gruppe von Websiteberechtigungen, die nur Mitgliedern der Sicherheitsgruppe " **Research-Admins** " den Zugriff auf die Mitglieder der Sicherheitsgruppen "Research- **Members** " und " **Research-Viewers** " und "Verwaltung" ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ab06d-150">The set of site permissions, which only allow access to members of the **Research-Members** and **Research-Viewers** security groups and administration by members of the **Research-Admins** security group.</span></span>

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="ab06d-151">Schritt 5: Migrieren der lokalen SharePoint-Forschungsdaten</span><span class="sxs-lookup"><span data-stu-id="ab06d-151">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="ab06d-152">Contoso-Administratoren haben alle lokalen Forschungs Dateien in der lokalen SharePoint Server 2016-Website in Ordner auf der neuen **Research** SharePoint Online-Website verschoben.</span><span class="sxs-lookup"><span data-stu-id="ab06d-152">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="ab06d-153">Schritt 6: Schulung der Benutzer</span><span class="sxs-lookup"><span data-stu-id="ab06d-153">Step 6: Trained their users</span></span> 

<span data-ttu-id="ab06d-154">Mitarbeiter von Contoso Security haben die Forschungsteams in einem obligatorischen Kurs ausgebildet, der Sie durchschritten hat:</span><span class="sxs-lookup"><span data-stu-id="ab06d-154">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="ab06d-155">So greifen Sie auf die neue **Research** SharePoint Online-Website und Ihre vorhandenen Dateien zu.</span><span class="sxs-lookup"><span data-stu-id="ab06d-155">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="ab06d-156">Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="ab06d-156">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="ab06d-157">Ein Beispiel dafür, wie die DLP-Richtlinie verhindert, dass Dateien extern freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ab06d-157">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="ab06d-158">Verwenden des Azure Information Protection-Clients zum Beschriften von Recherche Dateien mit der unter Bezeichnung " **Research** ".</span><span class="sxs-lookup"><span data-stu-id="ab06d-158">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="ab06d-159">Eine Demonstration der Art und Weise, wie die **Forschungs** -unter Bezeichnung eine Datei schützt, auch wenn Sie von der Website durchgesickert ist.</span><span class="sxs-lookup"><span data-stu-id="ab06d-159">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="ab06d-160">Das Endergebnis ist eine sichere Umgebung, in der die Forscher innerhalb der Organisation in einer sicheren Umgebung zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="ab06d-160">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="ab06d-161">Wenn ein Forschungsdokument mit dem **Recherche** -unter Label von der **Forschungs** Website durchgesickert ist, ist es verschlüsselt und nur für Mitglieder der Sicherheitsgruppen " **Research-Members** " und " **Research-Viewers** " mit gültigen Anmeldeinformationen zugänglich.</span><span class="sxs-lookup"><span data-stu-id="ab06d-161">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research-Members** and **Research-Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="ab06d-162">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ab06d-162">Next step</span></span>

<span data-ttu-id="ab06d-163">[Bereitstellen](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="ab06d-163">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

