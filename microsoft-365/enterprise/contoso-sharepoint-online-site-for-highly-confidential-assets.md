---
title: SharePoint Online-Website für hoch vertrauliche digitale Objekte der Contoso Corporation
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
description: 'Zusammenfassung: wie Contoso eine SharePoint Online-Website für hochregulierte Daten implementiert hat, um die Zusammenarbeit zwischen ihren Forschungsteams zu vereinfachen.'
ms.openlocfilehash: 99599829658e5dc46c8adebfe59f5c6d09b165de
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072780"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="f9ab8-103">SharePoint Online-Website für hoch vertrauliche digitale Objekte der Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="f9ab8-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="f9ab8-104">**Zusammenfassung:** Wie Contoso eine SharePoint Online-Website für hochregulierte Daten implementiert hat, um die Zusammenarbeit zwischen ihren Forschungsteams zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="f9ab8-105">Die wertvollsten Ressourcen von Contoso sind Ihr geistiges Eigentum in Form von Geschäftsgeheimnisse, wie proprietäre Herstellungsverfahren und Designspezifikationen für Produkte, die sich in der Entwicklung befinden.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="f9ab8-106">Diese Objekte sind in digitaler Form, die ursprünglich als Dateien auf einer SharePoint Server 2016-Website gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-106">These assets are in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="f9ab8-107">Als Contoso Microsoft 365 Enterprise bereitgestellt hat, wollten Sie Ihre lokalen digitalen Ressourcen für einen einfacheren Zugriff und eine offenere Zusammenarbeit über Forschungsteams in Paris, Moskau, New York, Peking und Bangalore hinweg in die Cloud überführen.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="f9ab8-108">Aufgrund Ihrer sensiblen Art muss der Zugriff auf diese Dateien jedoch wie folgt erfolgen:</span><span class="sxs-lookup"><span data-stu-id="f9ab8-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="f9ab8-109">Beschränkt auf die Gruppe von Personen, die Sie anzeigen oder ändern dürfen, mit laufenden Berechtigungen für die Website, die nur von SharePoint-Administratoren verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="f9ab8-110">Protected with Data Loss Prevention (DLP), um zu verhindern, dass Benutzer Sie außerhalb der Website verteilen.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="f9ab8-111">Verschlüsselt und mit Zugriffssteuerungslisten geschützt, um zu verhindern, dass unbefugte Benutzer auf Ihre Inhalte zugreifen, auch wenn Sie außerhalb der Website verteilt sind.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="f9ab8-112">Sicherheit und SharePoint-Administratoren in der IT-Abteilung von Contoso haben sich entschieden, eine [SharePoint Online-Website für hochregulierte Daten](teams-sharepoint-online-sites-highly-regulated-data.md)zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="f9ab8-113">Contoso hat die folgenden Schritte zum Erstellen und Sichern einer SharePoint Online-Teamwebsite für Ihre Forschungsteams verwendet.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="f9ab8-114">Schritt 1: überprüfen und Überprüfen der Mitglieder von Forschungsteam Gruppen</span><span class="sxs-lookup"><span data-stu-id="f9ab8-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="f9ab8-115">Contoso-IT-Administratoren haben eine Überprüfungen der Gruppe von Sicherheitsgruppen für Ihre Forschungsteams durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-115">Contoso IT admins performed a review of the set of security groups for their research teams.</span></span> <span data-ttu-id="f9ab8-116">Sie haben alle Personen entfernt, die kein Forscher waren oder keinen Zugriff auf Forschungsobjekte benötigten.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-116">They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="f9ab8-117">Außerdem haben Sie die folgenden neuen Sicherheitsgruppen erstellt:</span><span class="sxs-lookup"><span data-stu-id="f9ab8-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="f9ab8-118">**Forschung-Administratoren**  Die Gruppe von SharePoint-Administratoren, die über vollständige Kontrolle über die Website verfügen, einschließlich der Möglichkeit, Berechtigungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="f9ab8-119">**Research-Mitglieder**  Die Gruppe von Sicherheitsgruppen für die Teams weltweit.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-119">**Research-Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="f9ab8-120">**Forschung – Betrachter**  Die Gruppe der Verwaltungs Benutzer, wie beispielsweise Führungskräfte in der Forschungsorganisation, die nur die Objekte auf der Website anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can only view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="f9ab8-121">Schritt 2: Erstellen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="f9ab8-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="f9ab8-122">Contoso SharePoint-Administratoren haben zunächst eine neue Teamwebsite mit dem Namen **Research**erstellt.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-122">Contoso SharePoint admins first created a new team site named **Research**.</span></span> <span data-ttu-id="f9ab8-123">Anschließend haben Sie Folgendes konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="f9ab8-123">They then configured:</span></span>

- <span data-ttu-id="f9ab8-124">Die Berechtigungsstufe "Vollzugriff" für die Verwendung der SharePoint-Gruppe "Research Owners" mit der Sicherheitsgruppe " **Research-Admins** " als Mitglied</span><span class="sxs-lookup"><span data-stu-id="f9ab8-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="f9ab8-125">Die Berechtigungsstufe "Bearbeiten" für die Verwendung der SharePoint-Gruppe "Research Members" mit der Sicherheitsgruppe " **Forschungs Mitglieder** " als Mitglied</span><span class="sxs-lookup"><span data-stu-id="f9ab8-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="f9ab8-126">Die Lese Berechtigungsstufe zum Verwenden der SharePoint-Gruppe "Research Visitors" mit der Sicherheitsgruppe " **Research-Viewers** " als Mitglied</span><span class="sxs-lookup"><span data-stu-id="f9ab8-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="f9ab8-127">Hier sind die resultierenden SharePoint-Berechtigungsstufen, SharePoint-Gruppen und ihre Mitglieder.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="f9ab8-128">Als nächstes haben Sie zusätzliche Einschränkungen für die Website konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-128">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="f9ab8-129">Die Konfigurationsdetails finden Sie unter [Deploy an isolated SharePoint Online Team Site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span><span class="sxs-lookup"><span data-stu-id="f9ab8-129">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="f9ab8-130">Schritt 3: Konfigurieren der Website für eine restriktive DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f9ab8-130">Step 3: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="f9ab8-131">Zunächst wendeten Contoso-Administratoren die **streng vertrauliche** Office 365-Aufbewahrungs Bezeichnung auf die **Forschungs** Website an.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-131">First, Contoso admins applied the **Highly Confidential** Office 365 retention label to the **Research** site.</span></span>

<span data-ttu-id="f9ab8-132">Als nächstes haben Sie eine neue Office 365 DLP-Richtlinie namens " **Forschung** " erstellt, die:</span><span class="sxs-lookup"><span data-stu-id="f9ab8-132">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="f9ab8-133">Verwendet die **vertrauliche** Office 365-Aufbewahrungs Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-133">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="f9ab8-134">Wird auf die **Forschungs** Website angewendet.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-134">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="f9ab8-135">Blockiert Benutzer, wenn Sie versuchen, ein digitales Objekt auf der **Forschungs** Website außerhalb von Contoso freizugeben.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-135">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="f9ab8-136">Die Konfigurationsdetails finden Sie unter [Schützen von SharePoint Online-Dateien mit Aufbewahrungs Bezeichnungen und DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="f9ab8-136">For the configuration details, see [Protect SharePoint Online files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="f9ab8-137">Schritt 4: Erstellen einer Azure Information Protection-unter Bezeichnung für die Website</span><span class="sxs-lookup"><span data-stu-id="f9ab8-137">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="f9ab8-138">Contoso-Administratoren haben eine neue Azure Information Protection-unter Bezeichnung mit dem Namen **Research** der standardmäßigen, **streng vertraulichen** Bezeichnung in einer bereichsbezogenen Richtlinie erstellt, die:</span><span class="sxs-lookup"><span data-stu-id="f9ab8-138">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="f9ab8-139">Verschlüsselung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-139">Requires encryption.</span></span>
- <span data-ttu-id="f9ab8-140">Ermöglicht den vollständigen Zugriff durch Mitglieder der Sicherheitsgruppe " **Research-Members** ".</span><span class="sxs-lookup"><span data-stu-id="f9ab8-140">Allows full access by members of the **Research-Members** security group.</span></span>
- <span data-ttu-id="f9ab8-141">Ermöglicht den Lesezugriff durch Mitglieder der Sicherheitsgruppe " **Research-Viewers** ".</span><span class="sxs-lookup"><span data-stu-id="f9ab8-141">Allows read access by members of the **Research-Viewers** security group.</span></span>

<span data-ttu-id="f9ab8-142">Als nächstes haben Sie den Azure Information Protection-Client für die Geräte von Mitgliedern des Forschungsteams bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-142">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="f9ab8-143">Die Konfigurationsdetails finden Sie unter [Schützen von SharePoint Online-Dateien mit Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="f9ab8-143">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="f9ab8-144">Hier ist die resultierende Konfiguration der **Forschungs** Website für hoch vertrauliche Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-144">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="f9ab8-145">Dateien in Ordnern der **Recherche** Website werden geschützt durch:</span><span class="sxs-lookup"><span data-stu-id="f9ab8-145">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="f9ab8-146">Die \*\*\*\* unter Bezeichnung Azure Information Protection, die Verschlüsselung und permssions für jede Datei anwendet, die mit der Datei reist, wenn Sie von der **Recherche** Website verschoben oder kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-146">The **Research** Azure Information Protection sublabel, which applies encryption and permssions to each file that travel with the file when it is moved or copied from the **Research** site.</span></span>
- <span data-ttu-id="f9ab8-147">Die \*\*\*\* DLP-Richtlinie "Recherchieren" verwendet die **hochsensible** Aufbewahrungs Bezeichnung und Einstellungen, die verhindern, dass die Datei für externe Benutzer freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-147">The **Research** DLP policy, which uses the **Highly Sensitive** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="f9ab8-148">Die Gruppe von Websiteberechtigungen, die nur den Mitgliedern der Sicherheitsgruppen für \*\*\*\* Recherche-und Forschungs \*\*\*\* Benutzer sowie der Verwaltung von Mitgliedern der Sicherheitsgruppe "Recherche- **Administratoren** " den Zugriff ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-148">The set of site permissions, which only allow access to members of the **Research-Members** and **Research-Viewers** security groups and administration by members of the **Research-Admins** security group.</span></span>

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="f9ab8-149">Schritt 5: Migrieren der lokalen SharePoint-Forschungsdaten</span><span class="sxs-lookup"><span data-stu-id="f9ab8-149">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="f9ab8-150">Contoso-Administratoren haben alle lokalen Recherche Dateien in der lokalen SharePoint Server 2016-Website in Ordner in der neuen **Research** SharePoint Online-Website verschoben.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-150">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="f9ab8-151">Schritt 6: Schulung der Benutzer</span><span class="sxs-lookup"><span data-stu-id="f9ab8-151">Step 6: Trained their users</span></span> 

<span data-ttu-id="f9ab8-152">Das Sicherheitsteam von Contoso hat die Forschungsteams in einem obligatorischen Kurs geschult, der Sie durchlaufen hat:</span><span class="sxs-lookup"><span data-stu-id="f9ab8-152">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="f9ab8-153">Zugriff auf die neue **Research** SharePoint Online-Website und die vorhandenen Dateien</span><span class="sxs-lookup"><span data-stu-id="f9ab8-153">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="f9ab8-154">Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-154">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="f9ab8-155">Ein Beispiel dafür, wie die DLP-Richtlinie verhindert, dass Dateien extern freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-155">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="f9ab8-156">Verwenden des Azure Information Protection-Clients zum Beschriften von Recherche Dateien mit der **Recherche** -unter Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-156">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="f9ab8-157">Eine Demonstration, wie die untergeordnete Bezeichnung " **Research** " eine Datei schützt, auch wenn Sie von der Website geleckt wird.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-157">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="f9ab8-158">Das Endergebnis ist eine sichere Umgebung, in der die Forscher innerhalb der gesamten Organisation in einer sicheren Umgebung zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-158">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="f9ab8-159">Wenn ein Forschungsdokument mit der unter Bezeichnung **Recherche** aus der **Forschungs** Website ausgelaufen ist, wird es verschlüsselt und kann nur Mitgliedern der Sicherheitsgruppen "Research- **Members** " und " **Research-Viewers** " mit gültigen Anmeldeinformationen zugänglich gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-159">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research-Members** and **Research-Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="f9ab8-160">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f9ab8-160">Next step</span></span>

<span data-ttu-id="f9ab8-161">[Bereitstellen](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="f9ab8-161">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

