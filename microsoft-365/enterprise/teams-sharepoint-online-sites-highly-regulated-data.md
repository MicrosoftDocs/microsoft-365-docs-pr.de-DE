---
title: SharePoint-Websites für streng regulierte Daten
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie eine sichere SharePoint-Teamwebsite zum Speichern Ihrer wertvollsten und vertraulichen Dateien.
ms.openlocfilehash: dc604870826075cee645dd466b82f908e1571339
ms.sourcegitcommit: e1ffb98ac8159d1dc814930fe388d3e37cbdc7e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2019
ms.locfileid: "37403182"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="d62bc-103">SharePoint-Websites für streng regulierte Daten</span><span class="sxs-lookup"><span data-stu-id="d62bc-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="d62bc-104">*Dieses Szenario gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d62bc-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d62bc-p101">Microsoft 365 Enterprise umfasst eine vollständige Suite cloudbasierter Dienste, damit Sie streng regulierte Daten in Dateien erstellen, speichern und schützen können. Dazu gehören folgende Daten:</span><span class="sxs-lookup"><span data-stu-id="d62bc-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="d62bc-107">Daten, die regionalen Vorschriften unterliegen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="d62bc-108">Die wertvollsten Daten für Ihre Organisation, z. B. Geschäftsgeheimnisse, Informationen zu Finanzen oder Personalwesen und die Organisationsstrategie.</span><span class="sxs-lookup"><span data-stu-id="d62bc-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="d62bc-109">Für ein cloudbasiertes Microsoft 365 Enterprise-Szenario, das diese Geschäftsanforderung erfüllt, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="d62bc-109">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="d62bc-110">Dateien (Dokumente, Folienstapel, Kalkulationstabellen usw.) in einer SharePoint-Teamwebsite speichern.</span><span class="sxs-lookup"><span data-stu-id="d62bc-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the Files tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="d62bc-111">Die Website sperren, um Folgendes zu verhindern:</span><span class="sxs-lookup"><span data-stu-id="d62bc-111">Lock down the site or team to prevent:</span></span>
  - <span data-ttu-id="d62bc-112">Zugriff für Benutzer, die nicht Mitglied der Office 365-Gruppe für die Website sind.</span><span class="sxs-lookup"><span data-stu-id="d62bc-112">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="d62bc-113">Dass Mitglieder der Website anderen Personen Zugriff gewähren.</span><span class="sxs-lookup"><span data-stu-id="d62bc-113">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="d62bc-114">Dass Nicht-Mitglieder der Website Zugriff auf die Website anfordern.</span><span class="sxs-lookup"><span data-stu-id="d62bc-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="d62bc-115">Konfigurieren Sie eine Office 365-Aufbewahrungsbezeichnung für Ihre SharePoint-Websites als Standardmethode, um Benutzer am Senden von Dateien an Ziele außerhalb der Organisation hindern.</span><span class="sxs-lookup"><span data-stu-id="d62bc-115">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="d62bc-116">Verschlüsseln Sie die besonders sensiblen Dateien der Website mit einer an die Dateien gebundenen Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="d62bc-116">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="d62bc-117">Fügen Sie den besonders sensiblen Dateien Berechtigungen hinzu, sodass zum Öffnen der Datei auch dann gültige Anmeldeinformationen eines Benutzerkontos mit Berechtigung erforderlich sind, wenn diese für Personen außerhalb der Website freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d62bc-117">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="d62bc-118">In der folgenden Tabelle sind die Anforderungen dieses Szenarios einem Feature von Microsoft 365 Enterprise zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d62bc-118">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="d62bc-119">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="d62bc-119">**Requirement**</span></span> | <span data-ttu-id="d62bc-120">**Microsoft 365 Enterprise-Feature**</span><span class="sxs-lookup"><span data-stu-id="d62bc-120">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="d62bc-121">Speichern von Dateien</span><span class="sxs-lookup"><span data-stu-id="d62bc-121">4. Store files online</span></span> | <span data-ttu-id="d62bc-122">SharePoint-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="d62bc-122">Isolated SharePoint Online team sites</span></span> |
| <span data-ttu-id="d62bc-123">Sperren der Website</span><span class="sxs-lookup"><span data-stu-id="d62bc-123">Lock down the site</span></span> | <span data-ttu-id="d62bc-124">Azure Active Directory (Azure AD)-Gruppen und SharePoint-Teamwebsiteberechtigungen</span><span class="sxs-lookup"><span data-stu-id="d62bc-124">Azure Active Directory (Azure AD) groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="d62bc-125">Zuordnen von Bezeichnungen zu den Dateien der Website</span><span class="sxs-lookup"><span data-stu-id="d62bc-125">Label the digital assets of the site</span></span> | <span data-ttu-id="d62bc-126">Office 365-Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="d62bc-126">Office 365 retention labels</span></span> |
| <span data-ttu-id="d62bc-127">Verhindern, dass Benutzer Dateien außerhalb der Organisation senden</span><span class="sxs-lookup"><span data-stu-id="d62bc-127">Block users when sending files outside the organization</span></span> | <span data-ttu-id="d62bc-128">Richtlinien zur Verhinderung von Datenverlust in Office 365</span><span class="sxs-lookup"><span data-stu-id="d62bc-128">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="d62bc-129">Verschlüsseln aller Dateien der Website</span><span class="sxs-lookup"><span data-stu-id="d62bc-129">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="d62bc-130">Office 365-Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="d62bc-130">Office 365 sensitivity sublabels</span></span> |
| <span data-ttu-id="d62bc-131">Hinzufügen von Berechtigungen zu den Dateien der Website</span><span class="sxs-lookup"><span data-stu-id="d62bc-131">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="d62bc-132">Office 365-Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="d62bc-132">Office 365 sensitivity sublabels</span></span> |
|||

<span data-ttu-id="d62bc-133">Hier sehen Sie die Konfiguration für eine sichere SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="d62bc-133">Here is the configuration for a SharePoint Online site.</span></span>

![Die SharePoint-Websites für ein Szenario mit stark regulierten Daten](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="d62bc-135">Dieses Szenario erfordert, dass Sie Folgendes bereits bereitgestellt haben:</span><span class="sxs-lookup"><span data-stu-id="d62bc-135">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="d62bc-136">Die Phase [Identität](identity-infrastructure.md) und die Schritte 1 und 2 der Phase [Informationsschutz](infoprotect-infrastructure.md) der Foundation-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="d62bc-136">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="d62bc-137">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="d62bc-137">SharePoint</span></span>

<span data-ttu-id="d62bc-138">Die folgenden Phasen führen Sie schrittweise durch den Entwurf, die Konfiguration und das Fördern der Einführung für SharePoint-Websites für streng regulierte Daten.</span><span class="sxs-lookup"><span data-stu-id="d62bc-138">The following phases step you through designing, configuring, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="d62bc-139">Um zu erfahren, wie die Contoso Corporation, ein fiktives, aber repräsentatives multinationales Unternehmen, eine SharePoint-Website für seine Forschungsteams entwickelt hat, sehen Sie sich die folgende [Beispielkonfiguration](contoso-sharepoint-online-site-for-highly-confidential-assets.md) an.</span><span class="sxs-lookup"><span data-stu-id="d62bc-139">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="d62bc-140">Voraussetzungen für den Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="d62bc-140">Identity and device access prerequisites</span></span>

<span data-ttu-id="d62bc-141">Um den Zugriff auf die SharePoint-Website zu schützen, stellen Sie sicher, dass Sie [Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md) und die [empfohlenen SharePoint-Zugriffsrichtlinien](sharepoint-file-access-policies.md) konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="d62bc-141">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="d62bc-142">Phase 1: Entwurf</span><span class="sxs-lookup"><span data-stu-id="d62bc-142">Phase 1: Design</span></span>

<span data-ttu-id="d62bc-143">Wenn Sie eine SharePoint-Website für stark regulierte Daten erstellen möchten, müssen Sie zuerst deren Zweck bestimmen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-143">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="d62bc-144">So benötigt die Abteilung "Forschung und Entwicklung" eines Fertigungsunternehmens beispielsweise eine SharePoint-Website zum Speichern der aktuellen Designspezifikationen für bestehende Produkte und einen Ort für die Zusammenarbeit an neuen Produkten.</span><span class="sxs-lookup"><span data-stu-id="d62bc-144">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span> <span data-ttu-id="d62bc-145">Nur Mitglieder der Abteilung "Forschung und Entwicklung" und ausgewählte Führungskräfte dürfen auf die Website zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-145">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="d62bc-146">Dieser Zweck unterstützt die Ermittlung wichtiger Konfigurationselemente, z. B.:</span><span class="sxs-lookup"><span data-stu-id="d62bc-146">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="d62bc-147">Die Office 365-Aufbewahrungsbezeichnung, die dem Dokumententeil der Website zugewiesen werden soll, und DLP-Richtlinien für die Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="d62bc-147">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="d62bc-148">Die Einstellungen einer Office 365-Vertraulichkeitsunterbezeichnung, die Benutzer auf streng vertrauliche Dateien anwenden, die auf der Website gespeichert sind</span><span class="sxs-lookup"><span data-stu-id="d62bc-148">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="d62bc-149">Nach der Ermittlung werden diese Einstellungen zur Konfiguration der Website in Phase 2 verwendet.</span><span class="sxs-lookup"><span data-stu-id="d62bc-149">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="d62bc-150">Schritt 1: Office 365-Aufbewahrungsbezeichnungen und DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d62bc-150">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="d62bc-151">Wenn Office 365-Aufbewahrungsbezeichnungen auf den Dokumententeil einer SharePoint-Teamwebsite angewendet werden, bieten diese eine Standardmethode zum Klassifizieren aller Dateien, die auf der Website gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="d62bc-151">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="d62bc-152">Für SharePoint-Websites für streng regulierte Daten müssen Sie ermitteln, welche Office 365-Aufbewahrungsbezeichnung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d62bc-152">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="d62bc-153">Die Entwurfsaspekte für Office 365-Bezeichnungen finden Sie unter [Office 365-Klassifizierung und -Bezeichnungen](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="d62bc-153">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="d62bc-p103">Um vertrauliche Informationen zu schützen und ihre versehentliche oder absichtliche Veröffentlichung zu verhindern, verwenden Sie die DLP-Richtlinien. Weitere Informationen finden Sie in dieser [Übersicht](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="d62bc-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="d62bc-156">Für SharePoint-Websites müssen Sie eine DLP-Richtlinie für die Office 365-Aufbewahrungsbezeichnung konfigurieren, die der Website zugewiesen ist, um zu verhindern, dass Benutzer Dateien für externe Benutzer freigeben.</span><span class="sxs-lookup"><span data-stu-id="d62bc-156">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="d62bc-157">Schritt 2: Ihre Office 365-Vertraulichkeitsunterbezeichnung</span><span class="sxs-lookup"><span data-stu-id="d62bc-157">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="d62bc-158">Um für Ihre besonders sensiblen Dateien Verschlüsselung und eine Reihe von Berechtigungen bereitzustellen, müssen Benutzer eine Office 365-Vertraulichkeitsunterbezeichnung anwenden.</span><span class="sxs-lookup"><span data-stu-id="d62bc-158">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity sublabel.</span></span>

<span data-ttu-id="d62bc-159">Eine Unterbezeichnung ist einer vorhandenen Bezeichnung untergeordnet.</span><span class="sxs-lookup"><span data-stu-id="d62bc-159">A sublabel exists under an existing label.</span></span> <span data-ttu-id="d62bc-160">Sie können z. B. unter der Bezeichnung "Hochgradig reguliert" eine Unterbezeichnung "Forschung und Entwicklung" erstellen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-160">For example, you can create a Research & Development sublabel under the Highly Regulated label.</span></span> <span data-ttu-id="d62bc-161">Bei SharePoint-Websites für stark regulierte Daten konfigurieren Sie die Berechtigungen so, dass eine Datei, an die die Unterbezeichnung angefügt ist, nur von Websitemitgliedern geöffnet und geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d62bc-161">For SharePoint sites for highly regulated data, you configure the permissions so that only site members can open and change the file to which the sublabel is attached.</span></span>

<span data-ttu-id="d62bc-162">Die Einstellungen der angewendeten Unterbezeichnung sind an die Datei gebunden.</span><span class="sxs-lookup"><span data-stu-id="d62bc-162">The settings of the applied sublabel travel with the file.</span></span> <span data-ttu-id="d62bc-163">Auch wenn eine Datei die Website verlässt, kann sie nur von authentifizierten Benutzerkonten mit entsprechenden Berechtigungen geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="d62bc-163">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>


### <a name="design-results"></a><span data-ttu-id="d62bc-164">Entwurfsergebnisse</span><span class="sxs-lookup"><span data-stu-id="d62bc-164">Design results</span></span>

<span data-ttu-id="d62bc-165">Sie haben Folgendes bestimmt:</span><span class="sxs-lookup"><span data-stu-id="d62bc-165">You have determined the following:</span></span>

- <span data-ttu-id="d62bc-166">Die entsprechende Office 365 Aufbewahrungsbezeichnung und die DLP-Richtlinie, die dieser Bezeichnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="d62bc-166">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="d62bc-167">Die Einstellungen der Office 365-Unterbezeichnung, die Verschlüsselung und Berechtigungen umfassen</span><span class="sxs-lookup"><span data-stu-id="d62bc-167">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="d62bc-168">Phase 2: Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="d62bc-168">Phase 2: Configure</span></span>

<span data-ttu-id="d62bc-169">In dieser Phase implementieren Sie die in Phase 1 ermittelten Einstellungen, um eine SharePoint-Website für streng regulierte Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-169">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="d62bc-170">Schritt 1: Erstellen einer privaten SharePoint-Teamwebsite mit Besitzern und Mitgliedern der entsprechenden Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="d62bc-170">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="d62bc-171">Folgen Sie [diesen Anweisungen]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8), um eine private SharePoint-Teamwebsite zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-171">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="d62bc-172">Schritt 2: Konfigurieren zusätzlicher Berechtigungseinstellungen für die SharePoint-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="d62bc-172">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="d62bc-173">Konfigurieren Sie diese Berechtigungseinstellungen auf der SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="d62bc-173">From the SharePoint site, configure these permission settings.</span></span>

1.  <span data-ttu-id="d62bc-174">Klicken Sie in der Symbolleiste auf das Symbol „Einstellungen“ und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-174">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="d62bc-175">Klicken Sie im Bereich **Websiteberechtigungen** auf **Erweiterte Berechtigungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
3.  <span data-ttu-id="d62bc-176">Klicken Sie auf der neuen Registerkarte **Berechtigungen** in Ihrem Browser auf **Einstellungen für Zugriffsrechteanforderungen**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-176">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
4.  <span data-ttu-id="d62bc-177">Deaktivieren Sie im Dialogfeld **Einstellungen für Zugriffsrechteanforderungen** die Optionen **Mitgliedern das Freigeben der Website sowie einzelner Dateien und Ordner erlauben** und **Zugriffsanforderungen zulassen** (sodass alle drei Kontrollkästchen deaktiviert sind), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-177">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

<span data-ttu-id="d62bc-178">Bei diesen Einstellungen ist die Möglichkeit, dass Websitegruppenmitglieder die Website mit anderen Mitgliedern oder Nichtmitgliedern teilen, um den Zugriff auf die Website anzufordern, deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d62bc-178">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="d62bc-179">Schritt 3: Konfigurieren der Website für eine Office 365-Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="d62bc-179">Step 2: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="d62bc-180">Verwenden Sie die Anweisungen unter [Schützen von SharePoint-Dateien mit Office 365-Bezeichnungen und Verhindern von Datenverlust](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp), um Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="d62bc-180">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="d62bc-181">Erstellen und Veröffentlichen einer Aufbewahrungsbezeichnung für stark regulierte Daten (sofern erforderlich).</span><span class="sxs-lookup"><span data-stu-id="d62bc-181">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="d62bc-182">Konfigurieren der Website für die in Schritt 1 erstellte Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="d62bc-182">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="d62bc-183">Erstellen einer DLP-Richtlinie für stark regulierte Daten, die die in Schritt 2 erstellte Aufbewahrungsbezeichnung verwendet und Benutzer am Senden von Dateien an Ziele außerhalb der Organisation hindert</span><span class="sxs-lookup"><span data-stu-id="d62bc-183">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="d62bc-184">Schritt 4: Erstellen einer Office 365-Vertraulichkeitsunterbezeichnung für die Website</span><span class="sxs-lookup"><span data-stu-id="d62bc-184">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="d62bc-185">Im Gegensatz zu einer Vertraulichkeitsbezeichnung für streng regulierte Daten, die von jedem auf eine beliebige Datei angewendet werden kann, benötigt eine sichere Website eine eigene Unterbezeichnung, damit für Dateien, denen diese Unterbezeichnung zugeordnet ist, Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="d62bc-185">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="d62bc-186">Die Dateien werden verschlüsselt, und die Verschlüsselung ist an die Dateien gebunden.</span><span class="sxs-lookup"><span data-stu-id="d62bc-186">Are encrypted and the encryption travels with the file.</span></span>
-   <span data-ttu-id="d62bc-187">Die Dateien enthalten benutzerdefinierte Berechtigungen, sodass sie nur von Mitgliedern der Websitegruppe geöffnet werden können.</span><span class="sxs-lookup"><span data-stu-id="d62bc-187">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="d62bc-188">Um diese zusätzliche Sicherheitsstufe für die auf der Website gespeicherten Dateien zu erreichen, müssen Sie eine neue Vertraulichkeitsbezeichnung konfigurieren, bei der es sich um eine Unterbezeichnung der allgemeinen Bezeichnung für stark regulierten Dateien handelt.</span><span class="sxs-lookup"><span data-stu-id="d62bc-188">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="d62bc-189">Diese wird nur Gruppenmitgliedern der Website in der Liste der Unterbezeichnungen für die Bezeichnung "Hochgradig reguliert" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d62bc-189">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="d62bc-190">Verwenden Sie die [hier](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) aufgeführten Anweisungen, um eine Unterbezeichnungen der verwendeten Bezeichnung für stark regulierte Dateien mit den folgenden Einstellungen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="d62bc-190">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="d62bc-191">Zur einfachen Zuordnung der Unterbezeichnung zu einer Datei enthält der Name der Unterbezeichnung den Namen der Website.</span><span class="sxs-lookup"><span data-stu-id="d62bc-191">The name of the sublabel contains the name of the site for easy association when assign the sublabel to a file.</span></span>
- <span data-ttu-id="d62bc-192">Die Verschlüsselung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d62bc-192">Encryption is enabled.</span></span>
- <span data-ttu-id="d62bc-193">Die Websitegruppe verfügt über Berechtigungen für die gemeinsame Dokumenterstellung.</span><span class="sxs-lookup"><span data-stu-id="d62bc-193">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="d62bc-194">Konfigurationsergebnisse</span><span class="sxs-lookup"><span data-stu-id="d62bc-194">Configuration results</span></span>

<span data-ttu-id="d62bc-195">Sie haben Folgendes konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="d62bc-195">You have configured the following:</span></span>

- <span data-ttu-id="d62bc-196">Restriktivere Berechtigungseinstellungen auf der SharePoint-Website</span><span class="sxs-lookup"><span data-stu-id="d62bc-196">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="d62bc-197">Eine Office 365-Aufbewahrungsbezeichnung, die dem Dokumententeil der SharePoint-Website zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="d62bc-197">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="d62bc-198">Eine DLP-Richtlinie für die Office 365-Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="d62bc-198">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="d62bc-199">Eine Office 365-Vertraulichkeitsunterbezeichnung, die Benutzer auf die auf der Website gespeicherten besonders sensiblen Dateien anwenden können. Die Vertraulichkeitsunterbezeichnung verschlüsselt die Datei und erlaubt nur Mitgliedern der Teamwebsitegruppe den Zugriff für die gemeinsame Dokumenterstellung</span><span class="sxs-lookup"><span data-stu-id="d62bc-199">An Office 365 sensitivity sublabel that users can apply to the most sensitive files stored in the site that encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="d62bc-200">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d62bc-200">Here is the resulting configuration.</span></span>

![Die SharePoint-Websites für ein Szenario mit stark regulierten Daten](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)


<span data-ttu-id="d62bc-202">In diesem Beispiel hat ein Benutzer die Vertraulichkeitsunterbezeichnung auf eine auf der Website gespeicherte Datei angewendet.</span><span class="sxs-lookup"><span data-stu-id="d62bc-202">Here is an example of a user that has applied the sensitivity sublabel to a file stored in the site.</span></span>

![Die SharePoint-Websites für ein Szenario mit stark regulierten Daten](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="d62bc-204">Phase 3: Fördern der Benutzerakzeptanz</span><span class="sxs-lookup"><span data-stu-id="d62bc-204">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="d62bc-205">Eine SharePoint-Website für stark regulierte Daten kann diese Daten nur schützen, wenn Sie konsequent für die Speicherung und den Zugriff auf vertrauliche Dateien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d62bc-205">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> <span data-ttu-id="d62bc-206">Dies ist die schwierigste Phase, da sie davon abhängt, dass Benutzer ihre Gewohnheiten und Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="d62bc-206">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="d62bc-207">Beispielsweise müssen Angestellte, die vertrauliche Dateien bisher auf USB-Laufwerken oder auf persönlichen cloudbasierten Speicherlösungen gespeichert hatten, diese nun ausschließlich in einer SharePoint-Website für streng regulierte Daten speichern.</span><span class="sxs-lookup"><span data-stu-id="d62bc-207">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="d62bc-208">Schritt 1: Schulen der Benutzer</span><span class="sxs-lookup"><span data-stu-id="d62bc-208">Step 1: Train your users</span></span>

<span data-ttu-id="d62bc-209">Schulen Sie nach Abschluss der Konfiguration die Gruppe von Benutzern, die Mitglied der Websitezugriffsgruppen sind:</span><span class="sxs-lookup"><span data-stu-id="d62bc-209">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="d62bc-210">Vermitteln Sie ihnen, wie wichtig es ist, die neue Website zu verwenden, um wertvolle Dateien zu schützen, und welche Auswirkungen ein Verlust streng regulierter Daten hat, z. B. rechtliche Konsequenzen, Bußgelder oder Verlust des Wettbewerbsvorteils.</span><span class="sxs-lookup"><span data-stu-id="d62bc-210">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="d62bc-211">Erläutern Sie, wie auf die Website und ihre Dateien zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="d62bc-211">How to access the site and its assets.</span></span>
- <span data-ttu-id="d62bc-212">Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="d62bc-212">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="d62bc-213">Veranschaulichen Sie, wie durch die DLP-Richtlinie verhindert wird, dass Dateien extern freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d62bc-213">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="d62bc-214">Erklären Sie, wie die besonders sensiblen Dateien mit der Unterbezeichnung für die Website gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="d62bc-214">How to label the most sensitive files with the sublabel for the site.</span></span>
- <span data-ttu-id="d62bc-215">Veranschaulichen Sie, wie die Unterbezeichnung eine Datei schützt, auch wenn die Website verlässt.</span><span class="sxs-lookup"><span data-stu-id="d62bc-215">How the sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="d62bc-216">Diese Schulung sollte praktische Übungen umfassen, damit die Benutzer diese Vorgänge und deren Ergebnisse ausprobieren können.</span><span class="sxs-lookup"><span data-stu-id="d62bc-216">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="d62bc-217">Schritt 2: Durchführen regelmäßiger Verwendungs- und Dateiprüfungen</span><span class="sxs-lookup"><span data-stu-id="d62bc-217">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="d62bc-218">In den Wochen nach der Schulung kann der SharePoint-Administrator für die SharePoint-Website Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="d62bc-218">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="d62bc-219">Die Verwendung für die Website analysieren und dies mit den Erwartungen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-219">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="d62bc-220">Sicherstellen, dass streng vertrauliche Dateien korrekt mit der Vertraulichkeitsbezeichnung gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="d62bc-220">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

<span data-ttu-id="d62bc-221">Ihre Benutzer bei Bedarf erneut schulen.</span><span class="sxs-lookup"><span data-stu-id="d62bc-221">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="d62bc-222">Ergebnisse der Benutzerakzeptanz</span><span class="sxs-lookup"><span data-stu-id="d62bc-222">User adoption results</span></span>

<span data-ttu-id="d62bc-223">Stark regulierte Dateien werden ausschließlich auf SharePoint-Websites für stark regulierte Daten gespeichert, und die besonders sensiblen Dateien weisen die Vertraulichkeitsunterbezeichnung für die Website auf.</span><span class="sxs-lookup"><span data-stu-id="d62bc-223">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="d62bc-224">Bereitstellen von Microsoft 365 Enterprise für die Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="d62bc-224">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d62bc-225">Die Contoso Corporation ist ein fiktiver, aber repräsentativer globaler Mischkonzern im Bereich Fertigung mit Hauptsitz in Paris.</span><span class="sxs-lookup"><span data-stu-id="d62bc-225">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="d62bc-226">Erfahren Sie, wie Contoso die Einführung einer [sicheren SharePoint-Website](contoso-sharepoint-online-site-for-highly-confidential-assets.md) für seine Forschungsteams in Paris, Moskau, New York, Peking (Beijing) und Bengaluru (Bangalore) konzipiert, konfiguriert und dann vorangetrieben hat.</span><span class="sxs-lookup"><span data-stu-id="d62bc-226">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="d62bc-227">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d62bc-227">See also</span></span>

[<span data-ttu-id="d62bc-228">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="d62bc-228">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d62bc-229">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="d62bc-229">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

