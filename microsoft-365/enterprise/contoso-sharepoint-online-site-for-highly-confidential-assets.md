---
title: SharePoint-Website für hoch vertrauliche digitale Objekte der Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Zusammenfassung: wie Contoso eine SharePoint-Website für hochregulierte Daten zur einfacheren Zusammenarbeit zwischen den Forschungsteams implementiert hat.'
ms.openlocfilehash: ce813407c0f4c6f7b68aa997bf5e54b86a24ff2d
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672711"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="e63f1-103">SharePoint-Website für hoch vertrauliche digitale Objekte der Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="e63f1-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

<span data-ttu-id="e63f1-104">Die wertvollsten Ressourcen von Contoso sind das geistige Eigentum in Form von Geschäftsgeheimnissen wie proprietäre Fertigungstechniken und Designspezifikationen für Produkte, die sich in der Entwicklung befinden.</span><span class="sxs-lookup"><span data-stu-id="e63f1-104">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="e63f1-105">Diese Objekte wurden in digitaler Form gespeichert und ursprünglich als Dateien auf einer SharePoint Server 2016-Website gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e63f1-105">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="e63f1-106">Bei der Bereitstellung von Microsoft 365 Enterprise durch Contoso wollten Sie Ihre lokalen digitalen Ressourcen für einen einfacheren Zugriff und eine offenere Zusammenarbeit zwischen den Forschungsteams in Paris, Moskau, New York, Beijing und Bangalore umstellen.</span><span class="sxs-lookup"><span data-stu-id="e63f1-106">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="e63f1-107">Aufgrund Ihrer sensiblen Natur muss der Zugriff auf diese Dateien jedoch wie folgt erfolgen:</span><span class="sxs-lookup"><span data-stu-id="e63f1-107">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="e63f1-108">Beschränkt auf die Gruppe von Personen, denen der Zugriff gewährt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e63f1-108">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="e63f1-109">Durch eine DLP-Richtlinie (Data Loss Prevention) geschützt, um zu verhindern, dass Benutzer Sie außerhalb der Website verteilen.</span><span class="sxs-lookup"><span data-stu-id="e63f1-109">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="e63f1-110">Verschlüsselt und mit Berechtigungen geschützt, um zu verhindern, dass unbefugte Benutzer auf Ihre Inhalte zugreifen, auch wenn Sie außerhalb der Website verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="e63f1-110">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="e63f1-111">Sicherheits-und SharePoint-Administratoren in der IT-Abteilung von Contoso haben sich für die Verwendung einer [SharePoint-Website für hochregulierte Daten](teams-sharepoint-online-sites-highly-regulated-data.md)entschieden.</span><span class="sxs-lookup"><span data-stu-id="e63f1-111">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="e63f1-112">Contoso hat diese Schritte zum Erstellen und Sichern von SharePoint-Teamwebsites für Ihre Forschungsteams verwendet.</span><span class="sxs-lookup"><span data-stu-id="e63f1-112">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="e63f1-113">Schritt 1: Erstellen einer privaten SharePoint-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="e63f1-113">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="e63f1-114">Um den Zugriff auf die SharePoint-Website zu schützen, hat Contoso die [empfohlenen SharePoint-Zugriffsrichtlinien](sharepoint-file-access-policies.md)konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e63f1-114">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="e63f1-115">Als nächstes kompilierte Contoso IT-Administratoren eine Liste der Benutzerkonten für die Forscher in ihren Büros in Paris, Moskau, New York, Beijing und Bangalore.</span><span class="sxs-lookup"><span data-stu-id="e63f1-115">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="e63f1-116">Anschließend hat ein IT-Administrator von Contoso eine neue private Teamwebsite mit dem Namen **Research** erstellt und alle Benutzerkonten für die Forscher hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e63f1-116">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="e63f1-117">Anschließend wurden zusätzliche Berechtigungseinstellungen für die Website konfiguriert, um zu verhindern, dass Forscher Zugriff auf die Website freigeben, und um zu verhindern, dass nicht-Forscher Zugriff auf die Website anfordern.</span><span class="sxs-lookup"><span data-stu-id="e63f1-117">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="e63f1-118">Schritt 2: Konfigurieren der Website für eine restriktive DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e63f1-118">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="e63f1-119">Zunächst wendeten Contoso-Administratoren die vorhandene **streng vertrauliche** Office 365 Aufbewahrungs Bezeichnung auf den Ordner "Dokumente" der **Forschungs** Website an.</span><span class="sxs-lookup"><span data-stu-id="e63f1-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="e63f1-120">Als nächstes haben Sie eine neue Office 365 DLP-Richtlinie mit dem Namen " **Forschung** " erstellt:</span><span class="sxs-lookup"><span data-stu-id="e63f1-120">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="e63f1-121">Verwendet die Office 365 Aufbewahrungs Bezeichnung mit **hoher Vertraulichkeit** .</span><span class="sxs-lookup"><span data-stu-id="e63f1-121">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="e63f1-122">Blockiert Benutzer, wenn Sie versuchen, ein digitales Objekt auf der **Forschungs** Website außerhalb von Contoso freizugeben.</span><span class="sxs-lookup"><span data-stu-id="e63f1-122">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="e63f1-123">Informationen zu den Konfigurationsdetails finden Sie unter [Schützen von SharePoint-Dateien mit Aufbewahrungs Bezeichnungen und DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="e63f1-123">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="e63f1-124">Schritt 4: Erstellen einer sublabelgruppe für Office 365 Sensitivität für die Website</span><span class="sxs-lookup"><span data-stu-id="e63f1-124">Step 4: Created an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="e63f1-125">Contoso-Administratoren haben eine neue unter Bezeichnung für Office 365 Sensitivität namens " **Research Teams** of the **streng Confidential** Label" erstellt, die:</span><span class="sxs-lookup"><span data-stu-id="e63f1-125">Contoso admins created a new Office 365 sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="e63f1-126">Verschlüsselung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e63f1-126">Requires encryption.</span></span>
- <span data-ttu-id="e63f1-127">Erlaubt gemeinsame Author-Berechtigungen für die Gruppe " **Research** Office 365".</span><span class="sxs-lookup"><span data-stu-id="e63f1-127">Allows Co-Author permissions for the **Research** Office 365 group</span></span>
- <span data-ttu-id="e63f1-128">Gilt für die Gruppe " **Research** Office 365"</span><span class="sxs-lookup"><span data-stu-id="e63f1-128">Applies to the **Research** Office 365 group</span></span>

<span data-ttu-id="e63f1-129">Hier ist die resultierende Konfiguration der **Forschungs** Teamwebsite für streng vertrauliche Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="e63f1-129">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![Die resultierende Konfiguration der Forschungsteam Website für streng vertrauliche Ressourcen](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="e63f1-131">Dateien in Ordnern der **Forschungs** Website sind geschützt durch:</span><span class="sxs-lookup"><span data-stu-id="e63f1-131">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="e63f1-132">Die Websiteberechtigungen, die nur den Zugriff auf Mitglieder der Gruppe " **Research** Office 365" ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e63f1-132">The site permissions, which only allow access to members of the **Research** Office 365 group.</span></span>
- <span data-ttu-id="e63f1-133">Die DLP-Richtlinie für **Forschung** , die die **streng vertrauliche** Aufbewahrungs Bezeichnung und Einstellungen verwendet, die verhindern, dass die Datei für externe Benutzer freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e63f1-133">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="e63f1-134">Die Sensitivitäts-Sublabel für **Forschungs Teams** mit Verschlüsselung und Berechtigungen, die mit der Datei transportiert werden, wenn Sie von der **Forschungs** Website verschoben oder kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="e63f1-134">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="e63f1-135">Hier ist ein Beispiel für eine Datei, die auf der **Forschungs** Website gespeichert ist, wobei die Sensitivitäts-unter Bezeichnung **Research Teams** zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e63f1-135">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![Die resultierende Konfiguration der Forschungsteam Website für streng vertrauliche Ressourcen](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="e63f1-137">Schritt 5: Migrieren der lokalen SharePoint-Forschungsdaten</span><span class="sxs-lookup"><span data-stu-id="e63f1-137">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="e63f1-138">Contoso-Administratoren haben alle lokalen Forschungs Dateien in der lokalen SharePoint Server 2016-Website in Ordner in der neuen **Research** -SharePoint-Website verschoben.</span><span class="sxs-lookup"><span data-stu-id="e63f1-138">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-6-trained-their-researchers"></a><span data-ttu-id="e63f1-139">Schritt 6: Ausbildung ihrer Forscher</span><span class="sxs-lookup"><span data-stu-id="e63f1-139">Step 6: Trained their researchers</span></span>

<span data-ttu-id="e63f1-140">Contoso-Sicherheitsmitarbeiter haben die Mitglieder der Gruppe " **Research** Office 365" in einem obligatorischen Kurs geschult, der Sie schrittweise durchlaufen hat:</span><span class="sxs-lookup"><span data-stu-id="e63f1-140">Contoso security staff trained the members of the **Research** Office 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="e63f1-141">So greifen Sie auf die neue **Forschungs** Website und die vorhandenen Dateien zu.</span><span class="sxs-lookup"><span data-stu-id="e63f1-141">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="e63f1-142">Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="e63f1-142">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="e63f1-143">Eine Demonstration der Art und Weise, **wie die DLP** -Richtlinie verhindert, dass Dateien extern freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e63f1-143">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="e63f1-144">Vorgehensweise Beschriften von Dateien mit der Sensitivitäts-unter Bezeichnung **Research Teams** .</span><span class="sxs-lookup"><span data-stu-id="e63f1-144">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="e63f1-145">Eine Demonstration der Art und Weise, wie die unter Bezeichnung " **Research Teams** " eine Datei schützt, auch wenn Sie von der Website durchgesickert ist.</span><span class="sxs-lookup"><span data-stu-id="e63f1-145">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="e63f1-146">Das Endergebnis ist eine sichere Umgebung, in der die Forscher über Contoso hinweg in einer sicheren Umgebung mit Dateien zusammenarbeiten können, die Forschungsinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e63f1-146">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="e63f1-147">Wenn ein Forschungsdokument mit der unter Bezeichnung " **Research Teams** " den **Forschungs** Standort verlässt, ist es verschlüsselt und nur für Mitglieder der Gruppe " **Research** Office 365" mit gültigen Anmeldeinformationen für das Benutzerkonto zugänglich.</span><span class="sxs-lookup"><span data-stu-id="e63f1-147">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Office 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="e63f1-148">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e63f1-148">Next step</span></span>

<span data-ttu-id="e63f1-149">[Bereitstellen](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="e63f1-149">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="e63f1-150">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="e63f1-150">See also</span></span>

<span data-ttu-id="e63f1-151">[Microsoft 365-Produktivitätsbibliothek](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="e63f1-151">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
