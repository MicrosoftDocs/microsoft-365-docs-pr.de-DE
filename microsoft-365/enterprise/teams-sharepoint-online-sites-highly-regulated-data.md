---
title: SharePoint-Websites für streng regulierte Daten
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie eine sichere SharePoint-Teamwebsite zum Speichern Ihrer wertvollsten und vertraulichen Dateien.
ms.openlocfilehash: f8ccda85256e1f590f80a9302897e2950c59d154
ms.sourcegitcommit: 0ceb79a633f7004e82b80e69b6f7a7329ccec7ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699745"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="06dac-103">SharePoint-Websites für streng regulierte Daten</span><span class="sxs-lookup"><span data-stu-id="06dac-103">SharePoint sites for highly regulated data</span></span>

<span data-ttu-id="06dac-104">*Dieses Szenario gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="06dac-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="06dac-p101">Microsoft 365 Enterprise umfasst eine vollständige Suite cloudbasierter Dienste, damit Sie streng regulierte Daten in Dateien erstellen, speichern, schützen und verwalten können. Dazu gehören folgende Daten:</span><span class="sxs-lookup"><span data-stu-id="06dac-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, secure, and manage your highly regulated data stored in files. This includes data that is:</span></span>

- <span data-ttu-id="06dac-107">Daten, die regionalen Vorschriften unterliegen.</span><span class="sxs-lookup"><span data-stu-id="06dac-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="06dac-108">Die wertvollsten Daten für Ihre Organisation, z. B. Geschäftsgeheimnisse, Informationen zu Finanzen oder Personalwesen und die Organisationsstrategie.</span><span class="sxs-lookup"><span data-stu-id="06dac-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

>[!Note]
> <span data-ttu-id="06dac-109">Ein ähnliches Szenario mit Microsoft Teams finden Sie [hier](secure-teams-highly-regulated-data-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="06dac-109">A similar scenario using Microsoft Teams is [here](secure-teams-highly-regulated-data-scenario.md).</span></span>
>

<span data-ttu-id="06dac-110">Für ein cloudbasiertes Microsoft 365 Enterprise-Szenario, das diese Geschäftsanforderung erfüllt, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="06dac-110">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="06dac-111">Dateien (Dokumente, Folienstapel, Kalkulationstabellen usw.) in einer SharePoint-Teamwebsite speichern.</span><span class="sxs-lookup"><span data-stu-id="06dac-111">Store files (documents, slide decks, spreadsheets, etc.) in a SharePoint team site.</span></span>
- <span data-ttu-id="06dac-112">Die Website sperren, um Folgendes zu verhindern:</span><span class="sxs-lookup"><span data-stu-id="06dac-112">Lock down the site to prevent:</span></span>
  - <span data-ttu-id="06dac-113">Zugriff für Benutzer, die nicht Mitglied der Office 365-Gruppe für die Website sind.</span><span class="sxs-lookup"><span data-stu-id="06dac-113">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="06dac-114">Dass Mitglieder der Website anderen Personen Zugriff gewähren.</span><span class="sxs-lookup"><span data-stu-id="06dac-114">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="06dac-115">Dass Nicht-Mitglieder der Website Zugriff auf die Website anfordern.</span><span class="sxs-lookup"><span data-stu-id="06dac-115">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="06dac-116">Konfigurieren Sie eine Office 365-Aufbewahrungsbezeichnung für Ihre SharePoint-Websites als Standardmethode, um Benutzer am Senden von Dateien an Ziele außerhalb der Organisation hindern.</span><span class="sxs-lookup"><span data-stu-id="06dac-116">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="06dac-117">Verschlüsseln Sie die besonders sensiblen Dateien der Website mit einer an die Dateien gebundenen Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="06dac-117">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="06dac-118">Fügen Sie den besonders sensiblen Dateien Berechtigungen hinzu, sodass zum Öffnen der Datei auch dann gültige Anmeldeinformationen eines Benutzerkontos mit Berechtigung erforderlich sind, wenn diese für Personen außerhalb der Website freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="06dac-118">Add permissions to the most sensitive files so that if even if they get shared outside of the site, opening the file still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="06dac-119">In der folgenden Tabelle sind die Anforderungen dieses Szenarios einem Feature von Microsoft 365 Enterprise zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="06dac-119">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="06dac-120">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="06dac-120">**Requirement**</span></span> | <span data-ttu-id="06dac-121">**Microsoft 365 Enterprise-Feature**</span><span class="sxs-lookup"><span data-stu-id="06dac-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="06dac-122">Speichern von Dateien</span><span class="sxs-lookup"><span data-stu-id="06dac-122">Store files</span></span> | <span data-ttu-id="06dac-123">SharePoint-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="06dac-123">SharePoint team sites</span></span> |
| <span data-ttu-id="06dac-124">Sperren der Website</span><span class="sxs-lookup"><span data-stu-id="06dac-124">Lock down the site</span></span> | <span data-ttu-id="06dac-125">Office 365-Gruppen und SharePoint-Teamwebsiteberechtigungen</span><span class="sxs-lookup"><span data-stu-id="06dac-125">Office 365 groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="06dac-126">Zuordnen von Bezeichnungen zu den Dateien der Website</span><span class="sxs-lookup"><span data-stu-id="06dac-126">Label the files of the site</span></span> | <span data-ttu-id="06dac-127">Office 365-Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="06dac-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="06dac-128">Verhindern, dass Benutzer Dateien außerhalb der Organisation senden</span><span class="sxs-lookup"><span data-stu-id="06dac-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="06dac-129">Richtlinien zur Verhinderung von Datenverlust in Office 365</span><span class="sxs-lookup"><span data-stu-id="06dac-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="06dac-130">Verschlüsseln aller Dateien der Website</span><span class="sxs-lookup"><span data-stu-id="06dac-130">Encrypt all of the files of the site</span></span> | <span data-ttu-id="06dac-131">Office 365-Vertraulichkeitsbezeichnungen oder -unterbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="06dac-131">Office 365 sensitivity labels or sublabels</span></span> |
| <span data-ttu-id="06dac-132">Hinzufügen von Berechtigungen zu den Dateien der Website</span><span class="sxs-lookup"><span data-stu-id="06dac-132">Add permissions to the files of the site</span></span> | <span data-ttu-id="06dac-133">Office 365-Vertraulichkeitsbezeichnungen oder -unterbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="06dac-133">Office 365 sensitivity labels or sublabels</span></span> |
|||

<span data-ttu-id="06dac-134">Hier sehen Sie eine Beispielkonfiguration für eine sichere SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="06dac-134">Here is an example configuration for a secure SharePoint site.</span></span>

![Die SharePoint-Websites für ein Szenario mit stark regulierten Daten](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="06dac-136">Dieses Szenario erfordert, dass Sie Folgendes bereits bereitgestellt haben:</span><span class="sxs-lookup"><span data-stu-id="06dac-136">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="06dac-137">Die Phase [Identität](identity-infrastructure.md) und die Schritte 1 und 2 der Phase [Informationsschutz](infoprotect-infrastructure.md) der Foundation-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="06dac-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="06dac-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="06dac-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span></span>

<span data-ttu-id="06dac-139">Die folgenden Phasen führen Sie schrittweise durch den Entwurf, die Konfiguration und das Fördern der Einführung für SharePoint-Websites für streng regulierte Daten.</span><span class="sxs-lookup"><span data-stu-id="06dac-139">The following phases step you through designing, configuring, and driving adoption for SharePoint sites for highly regulated data.</span></span>

<a name="poster"></a> <span data-ttu-id="06dac-140">Eine einseitige Zusammenfassung dieses Szenarios finden Sie auf dem [Poster für SharePoint-Websites für streng regulierte Daten](./media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span><span class="sxs-lookup"><span data-stu-id="06dac-140">For a 1-page summary of this scenario, see the [SharePoint sites for highly regulated data poster](./media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="06dac-141">[![SharePoint-Websites für streng regulierte Daten](./media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](./media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="06dac-141">[![SharePoint sites for highly regulated data poster](./media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](./media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="06dac-142">Sie können dieses Poster auch im [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)- oder [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx)-Format herunterladen und in den Formaten "Brief", "Legal" oder "Tabloid" (27,94 x 43,18 cm) ausdrucken.</span><span class="sxs-lookup"><span data-stu-id="06dac-142">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="06dac-143">Voraussetzungen für den Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="06dac-143">Identity and device access prerequisites</span></span>

<span data-ttu-id="06dac-144">Um den Zugriff auf die SharePoint-Website zu schützen, stellen Sie sicher, dass Sie [Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md) und die [empfohlenen SharePoint-Zugriffsrichtlinien](sharepoint-file-access-policies.md) konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="06dac-144">To protect access to the SharePoint site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="06dac-145">Phase 1: Entwurf</span><span class="sxs-lookup"><span data-stu-id="06dac-145">Phase 1: Design</span></span>

<span data-ttu-id="06dac-146">Wenn Sie eine SharePoint-Website für stark regulierte Daten erstellen möchten, müssen Sie zuerst deren Zweck bestimmen.</span><span class="sxs-lookup"><span data-stu-id="06dac-146">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="06dac-147">So benötigt die Abteilung "Forschung und Entwicklung" eines Fertigungsunternehmens beispielsweise eine SharePoint-Website zum Speichern der aktuellen Designspezifikationen für bestehende Produkte und einen Ort für die Zusammenarbeit an neuen Produkten.</span><span class="sxs-lookup"><span data-stu-id="06dac-147">For example, the research and development department of a manufacturing organization needs a SharePoint site to store current design specifications for existing products and a place to collaborate on new products.</span></span> <span data-ttu-id="06dac-148">Nur Mitglieder der Abteilung "Forschung und Entwicklung" und ausgewählte Führungskräfte dürfen auf die Website zugreifen.</span><span class="sxs-lookup"><span data-stu-id="06dac-148">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="06dac-149">Dieser Zweck unterstützt die Ermittlung wichtiger Konfigurationselemente, z. B.:</span><span class="sxs-lookup"><span data-stu-id="06dac-149">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="06dac-150">Die Office 365-Aufbewahrungsbezeichnung, die dem Dokumententeil der Website zugewiesen werden soll, und DLP-Richtlinien für die Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="06dac-150">The Office 365 retention label to assign to the Documents portion of the site and DLP policies for the label</span></span>
- <span data-ttu-id="06dac-151">Die Einstellungen einer Office 365-Vertraulichkeitsunterbezeichnung, die Benutzer auf streng vertrauliche Dateien anwenden, die auf der Website gespeichert sind</span><span class="sxs-lookup"><span data-stu-id="06dac-151">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="06dac-152">Nach der Ermittlung werden diese Einstellungen zur Konfiguration der Website in Phase 2 verwendet.</span><span class="sxs-lookup"><span data-stu-id="06dac-152">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="06dac-153">Schritt 1: Office 365-Aufbewahrungsbezeichnungen und DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="06dac-153">Step 1 Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="06dac-154">Wenn Office 365-Aufbewahrungsbezeichnungen auf den Dokumententeil einer SharePoint-Teamwebsite angewendet werden, bieten diese eine Standardmethode zum Klassifizieren aller Dateien, die auf der Website gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="06dac-154">When applied to the Documents portion of a SharePoint team site, Office 365 retention labels provide a default method of classifying all files stored on the site.</span></span>
 
<span data-ttu-id="06dac-155">Für SharePoint-Websites für streng regulierte Daten müssen Sie ermitteln, welche Office 365-Aufbewahrungsbezeichnung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="06dac-155">For SharePoint sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="06dac-156">Die Entwurfsaspekte für Office 365-Bezeichnungen finden Sie unter [Office 365-Klassifizierung und -Bezeichnungen](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="06dac-156">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="06dac-p103">Um vertrauliche Informationen zu schützen und ihre versehentliche oder absichtliche Veröffentlichung zu verhindern, verwenden Sie die DLP-Richtlinien. Weitere Informationen finden Sie in dieser [Übersicht](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="06dac-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="06dac-159">Für SharePoint-Websites müssen Sie eine DLP-Richtlinie für die Office 365-Aufbewahrungsbezeichnung konfigurieren, die der Website zugewiesen ist, um zu verhindern, dass Benutzer Dateien für externe Benutzer freigeben.</span><span class="sxs-lookup"><span data-stu-id="06dac-159">For SharePoint sites, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share files with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="06dac-160">Schritt 2: Ihre Office 365-Vertraulichkeitsunterbezeichnung</span><span class="sxs-lookup"><span data-stu-id="06dac-160">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="06dac-161">Um für Ihre besonders sensiblen Dateien Verschlüsselung und eine Reihe von Berechtigungen bereitzustellen, müssen Benutzer eine Office 365-Vertraulichkeitsbezeichnung oder -unterbezeichnung anwenden.</span><span class="sxs-lookup"><span data-stu-id="06dac-161">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity label or sublabel.</span></span> <span data-ttu-id="06dac-162">Eine Unterbezeichnung ist einer vorhandenen Bezeichnung untergeordnet.</span><span class="sxs-lookup"><span data-stu-id="06dac-162">A sublabel exists under an existing label.</span></span> 

<span data-ttu-id="06dac-163">Verwenden Sie eine Vertraulichkeitsbezeichnung, wenn Sie nur eine kleine Anzahl von Bezeichnungen für die globale Nutzung und für einzelne private Teams benötigen.</span><span class="sxs-lookup"><span data-stu-id="06dac-163">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="06dac-164">Verwenden Sie eine Vertraulichkeitsunterbezeichnung, wenn Sie über eine große Anzahl von Bezeichnungen verfügen oder Bezeichnungen für sichere Websites unter ihrer streng regulierten Bezeichnung organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="06dac-164">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for secure sites the under your highly regulated label.</span></span> 

<span data-ttu-id="06dac-165">Die Einstellungen der angewendeten Bezeichnung oder Unterbezeichnung sind an die Datei gebunden.</span><span class="sxs-lookup"><span data-stu-id="06dac-165">The settings of the applied label or sublabel travel with the file.</span></span> <span data-ttu-id="06dac-166">Auch wenn eine Datei die Website verlässt, kann sie nur von authentifizierten Benutzerkonten mit entsprechenden Berechtigungen geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="06dac-166">Even if it is leaked outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="06dac-167">Entwurfsergebnisse</span><span class="sxs-lookup"><span data-stu-id="06dac-167">Design results</span></span>

<span data-ttu-id="06dac-168">Sie haben Folgendes bestimmt:</span><span class="sxs-lookup"><span data-stu-id="06dac-168">You have determined the following:</span></span>

- <span data-ttu-id="06dac-169">Die entsprechende Office 365 Aufbewahrungsbezeichnung und die DLP-Richtlinie, die dieser Bezeichnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="06dac-169">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="06dac-170">Die Einstellungen der Office 365-Unterbezeichnung, die Verschlüsselung und Berechtigungen umfassen</span><span class="sxs-lookup"><span data-stu-id="06dac-170">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="06dac-171">Phase 2: Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="06dac-171">Phase 2: Configure</span></span>

<span data-ttu-id="06dac-172">In dieser Phase implementieren Sie die in Phase 1 ermittelten Einstellungen, um eine SharePoint-Website für streng regulierte Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="06dac-172">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="06dac-173">Schritt 1: Erstellen einer privaten SharePoint-Teamwebsite mit Besitzern und Mitgliedern der entsprechenden Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="06dac-173">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="06dac-174">Folgen Sie [diesen Anweisungen]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8), um eine private SharePoint-Teamwebsite zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="06dac-174">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="06dac-175">Schritt 2: Konfigurieren zusätzlicher Berechtigungseinstellungen für die SharePoint-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="06dac-175">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="06dac-176">Konfigurieren Sie diese Berechtigungseinstellungen auf der SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="06dac-176">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="06dac-177">Klicken Sie in der Symbolleiste auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="06dac-177">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="06dac-178">Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="06dac-178">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="06dac-179">Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus.</span><span class="sxs-lookup"><span data-stu-id="06dac-179">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="06dac-180">Deaktivieren Sie **Zugriffsanforderungen zulassen**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="06dac-180">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="06dac-181">Bei diesen Einstellungen ist die Möglichkeit, dass Websitegruppenmitglieder die Website mit anderen Mitgliedern oder Nichtmitgliedern teilen, um den Zugriff auf die Website anzufordern, deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="06dac-181">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="06dac-182">Schritt 3: Konfigurieren der Website für eine Office 365-Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="06dac-182">Step 3: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="06dac-183">Verwenden Sie die Anweisungen unter [Schützen von SharePoint-Dateien mit Office 365-Bezeichnungen und Verhindern von Datenverlust](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp), um Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="06dac-183">Use the instructions in [Protect SharePoint files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="06dac-184">Erstellen und Veröffentlichen einer Aufbewahrungsbezeichnung für stark regulierte Daten (sofern erforderlich).</span><span class="sxs-lookup"><span data-stu-id="06dac-184">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="06dac-185">Konfigurieren der Website für die in Schritt 1 erstellte Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="06dac-185">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="06dac-186">Erstellen einer DLP-Richtlinie für stark regulierte Daten, die die in Schritt 2 erstellte Aufbewahrungsbezeichnung verwendet und Benutzer am Senden von Dateien an Ziele außerhalb der Organisation hindert</span><span class="sxs-lookup"><span data-stu-id="06dac-186">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="06dac-187">Schritt 4: Erstellen einer Office 365-Vertraulichkeitsunterbezeichnung für die Website</span><span class="sxs-lookup"><span data-stu-id="06dac-187">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="06dac-188">Im Gegensatz zu einer Vertraulichkeitsbezeichnung für streng regulierte Daten, die von jedem auf eine beliebige Datei angewendet werden kann, benötigt eine sichere Website eine eigene Unterbezeichnung, damit für Dateien, denen diese Unterbezeichnung zugeordnet ist, Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="06dac-188">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="06dac-189">Die Dateien werden verschlüsselt, und die Verschlüsselung ist an die Dateien gebunden.</span><span class="sxs-lookup"><span data-stu-id="06dac-189">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="06dac-190">Die Dateien enthalten benutzerdefinierte Berechtigungen, sodass sie nur von Mitgliedern der Websitegruppe geöffnet werden können.</span><span class="sxs-lookup"><span data-stu-id="06dac-190">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="06dac-191">Um diese zusätzliche Sicherheitsstufe für die auf der Website gespeicherten Dateien zu erreichen, müssen Sie eine neue Vertraulichkeitsbezeichnung oder Unterbezeichnung der allgemeinen Bezeichnung für stark regulierte Dateien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="06dac-191">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label or a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="06dac-192">Diese wird nur Gruppenmitgliedern der Website in der Liste der Unterbezeichnungen für die Bezeichnung "Hochgradig reguliert" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06dac-192">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="06dac-193">Verwenden Sie die [hier](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) aufgeführten Anweisungen, um eine Bezeichnung oder Unterbezeichnung der verwendeten Bezeichnung für stark regulierte Dateien mit den folgenden Einstellungen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="06dac-193">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a label or a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="06dac-194">Zur einfachen Zuordnung der Bezeichnung oder Unterbezeichnung zu einer Datei enthält der Name der Bezeichnung oder Unterbezeichnung den Namen der Website.</span><span class="sxs-lookup"><span data-stu-id="06dac-194">The name of the label or sublabel contains the name of the site for easy association when assigning the label or sublabel to a file.</span></span>
- <span data-ttu-id="06dac-195">Die Verschlüsselung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="06dac-195">Encryption is enabled.</span></span>
- <span data-ttu-id="06dac-196">Die Websitegruppe verfügt über Berechtigungen für die gemeinsame Dokumenterstellung.</span><span class="sxs-lookup"><span data-stu-id="06dac-196">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="06dac-197">Konfigurationsergebnisse</span><span class="sxs-lookup"><span data-stu-id="06dac-197">Configuration results</span></span>

<span data-ttu-id="06dac-198">Sie haben Folgendes konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="06dac-198">You have configured the following:</span></span>

- <span data-ttu-id="06dac-199">Restriktivere Berechtigungseinstellungen auf der SharePoint-Website</span><span class="sxs-lookup"><span data-stu-id="06dac-199">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="06dac-200">Eine Office 365-Aufbewahrungsbezeichnung, die dem Dokumententeil der SharePoint-Website zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="06dac-200">An Office 365 retention label assigned to the Documents portion of the SharePoint site</span></span>
- <span data-ttu-id="06dac-201">Eine DLP-Richtlinie für die Office 365-Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="06dac-201">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="06dac-202">Eine Office 365-Vertraulichkeitsbezeichnung oder -unterbezeichnung, die Benutzer auf die auf der Website gespeicherten besonders sensiblen Dateien anwenden können. Die Vertraulichkeitsbezeichnung oder -unterbezeichnung verschlüsselt die Datei und erlaubt nur Mitgliedern der Teamwebsitegruppe den Zugriff für die gemeinsame Dokumenterstellung</span><span class="sxs-lookup"><span data-stu-id="06dac-202">An Office 365 sensitivity label or sublabel that users can apply to the most sensitive files stored in the site, which encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="06dac-203">Hier ist die resultierende Konfiguration, die eine Unterbezeichnung der Vertraulichkeitsbezeichnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="06dac-203">Here is the resulting configuration that uses a sublabel of the Highly regulated label.</span></span>

![Die SharePoint-Websites für ein Szenario mit stark regulierten Daten](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="06dac-205">In diesem Beispiel hat ein Benutzer die Unterbezeichnung auf eine auf der Website gespeicherte Datei angewendet.</span><span class="sxs-lookup"><span data-stu-id="06dac-205">Here is an example of a user that has applied the sublabel to a file stored in the site.</span></span>

![Die SharePoint-Websites für ein Szenario mit stark regulierten Daten](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="06dac-207">Phase 3: Fördern der Benutzerakzeptanz</span><span class="sxs-lookup"><span data-stu-id="06dac-207">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="06dac-208">Eine SharePoint-Website für stark regulierte Daten kann diese Daten nur schützen, wenn Sie konsequent für die Speicherung und den Zugriff auf vertrauliche Dateien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="06dac-208">A SharePoint site for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive files.</span></span> <span data-ttu-id="06dac-209">Dies ist die schwierigste Phase, da sie davon abhängt, dass Benutzer ihre Gewohnheiten und Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="06dac-209">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="06dac-210">Beispielsweise müssen Angestellte, die vertrauliche Dateien bisher auf USB-Laufwerken oder auf persönlichen cloudbasierten Speicherlösungen gespeichert hatten, diese nun ausschließlich in einer SharePoint-Website für streng regulierte Daten speichern.</span><span class="sxs-lookup"><span data-stu-id="06dac-210">For example, employees that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="06dac-211">Schritt 1: Schulen der Benutzer</span><span class="sxs-lookup"><span data-stu-id="06dac-211">Step 1: Train your users</span></span>

<span data-ttu-id="06dac-212">Schulen Sie nach Abschluss der Konfiguration die Gruppe von Benutzern, die Mitglied der Website sind:</span><span class="sxs-lookup"><span data-stu-id="06dac-212">After completing your configuration, train the set of users who are members of the site:</span></span>

- <span data-ttu-id="06dac-213">Vermitteln Sie ihnen, wie wichtig es ist, die neue Website zu verwenden, um wertvolle Dateien zu schützen, und welche Auswirkungen ein Verlust streng regulierter Daten hat, z. B. rechtliche Konsequenzen, Bußgelder oder Verlust des Wettbewerbsvorteils.</span><span class="sxs-lookup"><span data-stu-id="06dac-213">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="06dac-214">Erläutern Sie, wie auf die Website und ihre Dateien zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="06dac-214">How to access the site and its files.</span></span>
- <span data-ttu-id="06dac-215">Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="06dac-215">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="06dac-216">Veranschaulichen Sie, wie durch die DLP-Richtlinie verhindert wird, dass Dateien extern freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="06dac-216">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="06dac-217">Erklären Sie, wie die besonders sensiblen Dateien mit der Bezeichnung oder Unterbezeichnung für die Website gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="06dac-217">How to label the most sensitive files with the label or sublabel for the site.</span></span>
- <span data-ttu-id="06dac-218">Veranschaulichen Sie, wie die Bezeichnung oder Unterbezeichnung eine Datei schützt, auch wenn die Website verlässt.</span><span class="sxs-lookup"><span data-stu-id="06dac-218">How the label or sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="06dac-219">Diese Schulung sollte praktische Übungen umfassen, damit die Benutzer diese Vorgänge und deren Ergebnisse ausprobieren können.</span><span class="sxs-lookup"><span data-stu-id="06dac-219">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="06dac-220">Schritt 2: Durchführen regelmäßiger Verwendungs- und Dateiprüfungen</span><span class="sxs-lookup"><span data-stu-id="06dac-220">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="06dac-221">In den Wochen nach der Schulung kann der SharePoint-Administrator für die SharePoint-Website Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="06dac-221">In the weeks after training, the SharePoint administrator for the SharePoint site can:</span></span>

- <span data-ttu-id="06dac-222">Die Verwendung für die Website analysieren und dies mit den Erwartungen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="06dac-222">Analyze usage for the site and compare it with usage expectations.</span></span>
- <span data-ttu-id="06dac-223">Sicherstellen, dass streng vertrauliche Dateien korrekt mit der Vertraulichkeitsbezeichnung oder -unterbezeichnung gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="06dac-223">Verify that highly sensitive files have been properly labeled with the sensitivity label or sublabel.</span></span>

  <span data-ttu-id="06dac-224">Sie können sehen, welchen Dateien eine Bezeichnung zugeordnet ist, indem Sie einen Ordner in SharePoint anzeigen und über die Option **Spalten ein-/ausblenden** > **Spalte hinzufügen** die Spalte **Vertraulichkeit** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="06dac-224">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>


<span data-ttu-id="06dac-225">Ihre Benutzer bei Bedarf erneut schulen.</span><span class="sxs-lookup"><span data-stu-id="06dac-225">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="06dac-226">Ergebnisse der Benutzerakzeptanz</span><span class="sxs-lookup"><span data-stu-id="06dac-226">User adoption results</span></span>

<span data-ttu-id="06dac-227">Stark regulierte Dateien werden ausschließlich auf SharePoint-Websites für stark regulierte Daten gespeichert, und die besonders sensiblen Dateien weisen die Vertraulichkeitsbezeichnung oder -unterbezeichnung für die Website auf.</span><span class="sxs-lookup"><span data-stu-id="06dac-227">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity label or sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-used-a-sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="06dac-228">Verwendung einer SharePoint-Website für stark regulierte Daten in der Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="06dac-228">How the Contoso Corporation used a SharePoint site for highly regulated data</span></span>

<span data-ttu-id="06dac-229">Die Contoso Corporation ist ein fiktiver, aber repräsentativer globaler Mischkonzern.</span><span class="sxs-lookup"><span data-stu-id="06dac-229">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="06dac-230">Erfahren Sie, wie Contoso die Einführung einer [sicheren SharePoint-Website](contoso-sharepoint-online-site-for-highly-confidential-assets.md) für seine Forschungsteams in Paris, Moskau, New York, Peking (Beijing) und Bengaluru (Bangalore) konzipiert, konfiguriert und dann vorangetrieben hat.</span><span class="sxs-lookup"><span data-stu-id="06dac-230">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="06dac-231">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06dac-231">See also</span></span>

[<span data-ttu-id="06dac-232">Teams für streng regulierte Daten</span><span class="sxs-lookup"><span data-stu-id="06dac-232">Teams for highly regulated data</span></span>](secure-teams-highly-regulated-data-scenario.md)

[<span data-ttu-id="06dac-233">Microsoft 365 Enterprise-Arbeitslasten und -Szenarien</span><span class="sxs-lookup"><span data-stu-id="06dac-233">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="06dac-234">[Microsoft 365-Produktivitätsbibliothek](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="06dac-234">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="06dac-235">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="06dac-235">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
