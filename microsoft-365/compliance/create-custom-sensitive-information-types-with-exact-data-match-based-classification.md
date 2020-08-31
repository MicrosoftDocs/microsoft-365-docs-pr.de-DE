---
title: Erstellen benutzerdefinierter vertraulicher Informationstypen mit genauer Datenübereinstimmung
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie benutzerdefinierte vertrauliche Informationstypen mit genauer Datenübereinstimmungsklassifizierung erstellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f4bbbe8726370297e9ef6317cd468789bb3b3bfe
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300433"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="4cf6e-103">Erstellen von benutzerdefinierten vertraulichen Informationstypen mit genauer Datenübereinstimmungsklassifizierung</span><span class="sxs-lookup"><span data-stu-id="4cf6e-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="4cf6e-104">[Benutzerdefinierte Typen vertraulicher Informationen](custom-sensitive-info-types.md) werden verwendet, um vertrauliche Elemente zu identifizieren, sodass Sie verhindern können, dass Sie versehentlich oder in unangemessener Weise geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="4cf6e-105">Sie können einen benutzerdefinierten Typ vertraulicher Informationen folgendermaßen definieren:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="4cf6e-106">Durch Muster</span><span class="sxs-lookup"><span data-stu-id="4cf6e-106">patterns</span></span>
- <span data-ttu-id="4cf6e-107">Durch den Nachweis von Schlüsselwörtern, z. B. *Mitarbeiter*, *Badge*oder *ID*</span><span class="sxs-lookup"><span data-stu-id="4cf6e-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="4cf6e-108">Ähnliche Zeichen als Nachweis in einem bestimmten Muster</span><span class="sxs-lookup"><span data-stu-id="4cf6e-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="4cf6e-109">Konfidenzniveaus</span><span class="sxs-lookup"><span data-stu-id="4cf6e-109">confidence levels</span></span>

 <span data-ttu-id="4cf6e-110">Solche benutzerdefinierten vertraulichen Informationstypen erfüllen die geschäftlichen Anforderungen vieler Organisationen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="4cf6e-111">Was aber, wenn Sie einen benutzerdefinierten vertraulichen Informationstyp nutzen möchten, der genaue Datenwerte verwendet, anstatt eines Typs, der Übereinstimmungen basierend auf generischen Mustern findet?</span><span class="sxs-lookup"><span data-stu-id="4cf6e-111">But what if you wanted a custom sensitive information type that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="4cf6e-112">Mit einer EDM-basierten Klassifizierung (Exact Data Match, genaue Datenübereinstimmung) können Sie einen benutzerdefinierten Informationstyp mit den folgenden Merkmalen erstellen:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="4cf6e-113">dynamisch und aktualisierbar</span><span class="sxs-lookup"><span data-stu-id="4cf6e-113">be dynamic and refreshable</span></span>
- <span data-ttu-id="4cf6e-114">skalierbarer</span><span class="sxs-lookup"><span data-stu-id="4cf6e-114">be more scalable</span></span>
- <span data-ttu-id="4cf6e-115">weniger falsch positive Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="4cf6e-115">result in fewer false-positives</span></span>
- <span data-ttu-id="4cf6e-116">arbeitet mit strukturierten vertraulichen Daten</span><span class="sxs-lookup"><span data-stu-id="4cf6e-116">work with structured sensitive data</span></span>
- <span data-ttu-id="4cf6e-117">behandelt vertrauliche Informationen sicherer</span><span class="sxs-lookup"><span data-stu-id="4cf6e-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="4cf6e-118">mit verschiedenen Microsoft Cloud Services verwendbar</span><span class="sxs-lookup"><span data-stu-id="4cf6e-118">be used with several Microsoft cloud services</span></span>

![EDM-basierte Klassifikation](../media/EDMClassification.png)

<span data-ttu-id="4cf6e-120">Die EDM-basierte Klassifikation ermöglicht es Ihnen, benutzerdefinierte vertrauliche Informationstypen zu erstellen, die sich auf genaue Werte in einer Datenbank mit vertraulichen Informationen beziehen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="4cf6e-121">Die Datenbank kann täglich aktualisiert werden und bis zu 100 Millionen Datenzeilen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="4cf6e-122">Mitarbeiter, Patienten oder Kunden kommen und gehen und Datensätze ändern sich, aber Ihre benutzerdefinierten vertraulichen Informationstypen bleiben aktuell und anwendbar.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="4cf6e-123">Darüber hinaus können Sie EDM-basierte Klassifikation mit Richtlinien verwenden, z. B. [Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md) (Data Loss Prevention, DLP) oder [Microsoft Cloud App Security-Dateirichtlinien](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="4cf6e-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="4cf6e-124">Microsoft 365 Information Protection unterstützt jetzt in der Vorschau Doppelbyte-Zeichensatz-Sprachen für:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-124">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="4cf6e-125">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="4cf6e-126">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="4cf6e-127">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="4cf6e-127">Korean</span></span>
> - <span data-ttu-id="4cf6e-128">Japanisch</span><span class="sxs-lookup"><span data-stu-id="4cf6e-128">Japanese</span></span>
> 
><span data-ttu-id="4cf6e-129">Diese Vorschau ist nur in der kommerziellen Cloud verfügbar, und die Einführung ist beschränkt auf:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-129">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="4cf6e-130">Japan</span><span class="sxs-lookup"><span data-stu-id="4cf6e-130">Japan</span></span>
> - <span data-ttu-id="4cf6e-131">Korea</span><span class="sxs-lookup"><span data-stu-id="4cf6e-131">Korea</span></span>
> - <span data-ttu-id="4cf6e-132">China</span><span class="sxs-lookup"><span data-stu-id="4cf6e-132">China</span></span>
> - <span data-ttu-id="4cf6e-133">Hongkong (SAR)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-133">Hong Kong</span></span>
> - <span data-ttu-id="4cf6e-134">Macau (SAR)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-134">Macau</span></span>
> - <span data-ttu-id="4cf6e-135">Taiwan</span><span class="sxs-lookup"><span data-stu-id="4cf6e-135">Taiwan</span></span>
>
><span data-ttu-id="4cf6e-136">Diese Unterstützung ist für vertrauliche Informationstypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-136">This support is available for sensitive information types.</span></span> <span data-ttu-id="4cf6e-137">Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="4cf6e-137">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="4cf6e-138">Erforderliche Lizenzen und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-138">Required licenses and permissions</span></span>

<span data-ttu-id="4cf6e-139">Sie müssen ein globaler, Compliance- oder Exchange Online-Administrator sein, um die in diesem Artikel beschriebenen Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-139">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="4cf6e-140">Weitere Informationen über DLP-Berechtigungen finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="4cf6e-140">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="4cf6e-141">Die EDM-basierte Klassifizierung ist in diesen Abonnements enthalten.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-141">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="4cf6e-142">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4cf6e-142">Office 365 E5</span></span>
- <span data-ttu-id="4cf6e-143">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4cf6e-143">Microsoft 365 E5</span></span>
- <span data-ttu-id="4cf6e-144">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="4cf6e-144">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="4cf6e-145">Microsoft E5/ A5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="4cf6e-145">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="4cf6e-146">Portal Links für Ihr Abonnement</span><span class="sxs-lookup"><span data-stu-id="4cf6e-146">Portal links for your subscription</span></span>


|<span data-ttu-id="4cf6e-147">Portal</span><span class="sxs-lookup"><span data-stu-id="4cf6e-147">Portal</span></span>  |<span data-ttu-id="4cf6e-148">Weltweit/GCC</span><span class="sxs-lookup"><span data-stu-id="4cf6e-148">World Wide/GCC</span></span>  |<span data-ttu-id="4cf6e-149">GCC – hoch</span><span class="sxs-lookup"><span data-stu-id="4cf6e-149">GCC-High</span></span>  |<span data-ttu-id="4cf6e-150">DOD</span><span class="sxs-lookup"><span data-stu-id="4cf6e-150">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="4cf6e-151">Office SCC</span><span class="sxs-lookup"><span data-stu-id="4cf6e-151">Office SCC</span></span>     |  <span data-ttu-id="4cf6e-152">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="4cf6e-152">protection.office.com</span></span>       |<span data-ttu-id="4cf6e-153">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="4cf6e-153">scc.office365.us</span></span>         |<span data-ttu-id="4cf6e-154">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="4cf6e-154">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="4cf6e-155">Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="4cf6e-155">Microsoft 365 Security center</span></span>     |<span data-ttu-id="4cf6e-156">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4cf6e-156">security.microsoft.com</span></span>         |<span data-ttu-id="4cf6e-157">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="4cf6e-157">security.microsoft.us</span></span>         |<span data-ttu-id="4cf6e-158">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="4cf6e-158">security.apps.mil</span></span>|
|<span data-ttu-id="4cf6e-159">Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="4cf6e-159">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="4cf6e-160">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4cf6e-160">compliance.microsoft.com</span></span>         |<span data-ttu-id="4cf6e-161">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="4cf6e-161">compliance.microsoft.us</span></span>         |<span data-ttu-id="4cf6e-162">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="4cf6e-162">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="4cf6e-163">Der Workflow auf einen Blick</span><span class="sxs-lookup"><span data-stu-id="4cf6e-163">The work flow at a glance</span></span>

|<span data-ttu-id="4cf6e-164">Phase</span><span class="sxs-lookup"><span data-stu-id="4cf6e-164">Phase</span></span>  |<span data-ttu-id="4cf6e-165">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-165">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="4cf6e-166">Teil 1: Einrichten der EDM-basierten Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="4cf6e-166">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="4cf6e-167">(je nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-167">(As needed)</span></span><br/><span data-ttu-id="4cf6e-168">- [Bearbeiten des Datenbankschemas](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-168">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="4cf6e-169">- [Entfernen des Schemas](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-169">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="4cf6e-170">– Lesezugriff auf vertrauliche Daten</span><span class="sxs-lookup"><span data-stu-id="4cf6e-170">- Read access to the sensitive data</span></span><br/><span data-ttu-id="4cf6e-171">– Datenbankschema im XML-Format (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-171">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="4cf6e-172">– Regelpaket im XML-Format (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-172">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="4cf6e-173">– Administratorberechtigungen für das Security & Compliance Center (mithilfe von PowerShell)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-173">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="4cf6e-174">Teil 2: Hashen und Hochladen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="4cf6e-174">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="4cf6e-175">(je nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-175">(As needed)</span></span><br/>[<span data-ttu-id="4cf6e-176">Aktualisieren der Daten</span><span class="sxs-lookup"><span data-stu-id="4cf6e-176">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="4cf6e-177">– Benutzerdefinierte Sicherheitsgruppe und Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="4cf6e-177">- Custom security group and user account</span></span><br/><span data-ttu-id="4cf6e-178">– Lokaler Administratorzugriff auf den Computer mit dem EDM-Upload-Agent</span><span class="sxs-lookup"><span data-stu-id="4cf6e-178">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="4cf6e-179">– Lesezugriff auf vertrauliche Daten</span><span class="sxs-lookup"><span data-stu-id="4cf6e-179">- Read access to the sensitive data</span></span><br/><span data-ttu-id="4cf6e-180">– Prozess und Zeitplan für die Datenaktualisierung</span><span class="sxs-lookup"><span data-stu-id="4cf6e-180">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="4cf6e-181">Teil 3: Verwenden der EDM-basierten Klassifizierung mit Ihren Microsoft Cloud Services</span><span class="sxs-lookup"><span data-stu-id="4cf6e-181">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="4cf6e-182">– Microsoft 365-Abonnement mit DLP</span><span class="sxs-lookup"><span data-stu-id="4cf6e-182">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="4cf6e-183">– EDM-basiertes Klassifizierungsfeature aktiviert</span><span class="sxs-lookup"><span data-stu-id="4cf6e-183">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="4cf6e-184">Teil 1: Einrichten der EDM-basierten Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="4cf6e-184">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="4cf6e-185">Das Einrichten und Konfigurieren der EDM-basierten Klassifizierung umfasst:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-185">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="4cf6e-186">Speichern vertraulicher Daten im CSV-Format</span><span class="sxs-lookup"><span data-stu-id="4cf6e-186">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="4cf6e-187">Definieren Ihres Datenbankschemas für vertrauliche Informationen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-187">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="4cf6e-188">Erstellen eines Regelpakets</span><span class="sxs-lookup"><span data-stu-id="4cf6e-188">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="4cf6e-189">Speichern vertraulicher Daten im CSV-Format</span><span class="sxs-lookup"><span data-stu-id="4cf6e-189">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="4cf6e-190">Identifizieren Sie die vertraulichen Informationen, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-190">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="4cf6e-191">Exportieren Sie die Daten in eine App, wie z. B. Microsoft Excel, und speichern Sie die Datei im CSV-Format.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-191">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="4cf6e-192">Die Datendatei kann maximal Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-192">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="4cf6e-193">bis zu 100 Millionen Zeilen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="4cf6e-193">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="4cf6e-194">bis zu 32 Spalten (Felder) pro Datenquelle</span><span class="sxs-lookup"><span data-stu-id="4cf6e-194">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="4cf6e-195">bis zu 5 als durchsuchbar markierte Spalten (Felder)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-195">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="4cf6e-196">Strukturieren Sie die vertraulichen Daten in der CSV-Datei so, dass die erste Zeile die Namen der für die EDM-basierte Klassifizierung verwendeten Felder enthält.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-196">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="4cf6e-197">Möglicherweise gibt es in Ihrer CSV-Datei Feldnamen, wie z. B. "SSN", "Geburtsdatum", "Vorname" oder "Nachname".</span><span class="sxs-lookup"><span data-stu-id="4cf6e-197">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="4cf6e-198">Die Namen der Spaltenüberschriften dürfen keine Leerzeichen oder Unterstriche enthalten.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-198">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="4cf6e-199">Die CSV-Datei, die wir in diesem Artikel verwenden, trägt beispielsweise den Namen  *PatientRecords.csv*, und hat u. a. die Spalten  *PatientID*, *MRN*, *LastName*, *FirstName* und  *SSN*.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-199">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="4cf6e-200">Definieren des Schemas für Ihre Datenbank mit vertraulichen Informationen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-200">Define the schema for your database of sensitive information</span></span>

3. <span data-ttu-id="4cf6e-201">Definieren Sie das Schema für die Datenbank mit vertraulichen Informationen im XML-Format (ähnlich wie in unserem Beispiel unten).</span><span class="sxs-lookup"><span data-stu-id="4cf6e-201">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="4cf6e-202">Nennen Sie diese Schemadatei **edm.xml**, und konfigurieren Sie sie so, dass es für jede Spalte in der Datenbank eine Zeile mit der folgenden Syntax gibt:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-202">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="4cf6e-203">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-203">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="4cf6e-204">Verwenden Sie Spaltennamen für *Field name*-Werte.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-204">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="4cf6e-205">Verwenden Sie *searchable="true* für maximal 5 Felder, die durchsuchbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-205">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="4cf6e-206">Mindestens ein Feld muss durchsuchbar sein.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-206">At least one field must be searchable.</span></span>

      <span data-ttu-id="4cf6e-207">Im folgenden Beispiel definiert die XML-Datei das Schema für eine Datenbank mit Patientendatensätzen, wobei fünf Felder als durchsuchbar angegeben werden: *PatientID*, *MRN*, *SSN*, *Phone* und *DOB*.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-207">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="4cf6e-208">(Sie können das Beispiel kopieren, ändern und verwenden.)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-208">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

4. <span data-ttu-id="4cf6e-209">Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="4cf6e-209">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="4cf6e-210">Führen Sie die folgenden Cmdlets nacheinander aus, um das Datenbankschema hochzuladen:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-210">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="4cf6e-211">Sie werden zu folgenden Bestätigungen aufgefordert:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-211">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="4cf6e-212">Bestätigen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-212">Confirm</span></span>
      >
      > <span data-ttu-id="4cf6e-213">Möchten Sie diese Aktion wirklich ausführen?</span><span class="sxs-lookup"><span data-stu-id="4cf6e-213">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="4cf6e-214">Das neue EDM-Schema für den Datenspeicher „patientrecords“ wird importiert.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-214">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="4cf6e-215">\[J\] Ja \[A\] Ja für alle \[N\] Nein \[L\] Nein für alle \[?\] Hilfe (Standard ist "J"):</span><span class="sxs-lookup"><span data-stu-id="4cf6e-215">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="4cf6e-216">Wenn Sie möchten, dass Ihre Änderungen ohne Bestätigung durchgeführt werden, verwenden Sie in Schritt 5 stattdessen das folgende Cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="4cf6e-216">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="4cf6e-217">Es kann zwischen 10–60 Minuten dauern, bis das EDMSchema durch Ergänzungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-217">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="4cf6e-218">Das Update muss abgeschlossen sein, bevor Sie Schritte ausführen, die die Zusätze verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-218">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="4cf6e-219">Einrichten eines Regelpakets</span><span class="sxs-lookup"><span data-stu-id="4cf6e-219">Set up a rule package</span></span>

1. <span data-ttu-id="4cf6e-220">Erstellen Sie ein Regelpaket im XML-Format (mit Unicode-Codierung), ähnlich wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-220">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="4cf6e-221">(Sie können das Beispiel kopieren, ändern und verwenden.)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-221">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="4cf6e-222">Vergewissern Sie sich beim Einrichten des Regelpakets, dass Sie die CSV-Datei und die **edm.xml**-Datei korrekt referenzieren.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-222">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="4cf6e-223">Sie können das Beispiel kopieren, ändern und verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-223">You can copy, modify, and use our example.</span></span> <span data-ttu-id="4cf6e-224">In dieser XML-Beispieldatei müssen die folgenden Felder so angepasst werden, dass Sie Ihren vertraulichen EDM-Typ erstellen:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-224">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="4cf6e-225">**RulePack id und ExactMatch id**: Verwenden Sie [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6), um eine GUID zu generieren.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-225">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="4cf6e-226">**Datenspeicher**: Dieses Feld gibt den zu verwendenden EDM-Nachschlage-Datenspeicher an.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-226">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="4cf6e-227">Sie geben einen Datenquellennamen eines konfigurierten EDM-Schemas an.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-227">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="4cf6e-228">**idMatch**: Dieses Feld verweist auf das primäre Element für EDM.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-228">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="4cf6e-229">Stimmt überein mit: gibt das Feld an, das in der exakten Suche verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-229">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="4cf6e-230">Sie geben den Namen eines durchsuchbaren Felds im EDM-Schema für den Datenspeicher an.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-230">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="4cf6e-231">Klassifizierung: Dieses Feld gibt die Übereinstimmung für den vertraulichen Typ an, der EDM-Nachschlagevorgänge auslöst.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-231">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="4cf6e-232">Sie können den Namen oder die GUID einer vorhandenen integrierten oder benutzerdefinierten Klassifizierung angeben.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-232">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="4cf6e-233">**Übereinstimmung:** Dieses Feld verweist auf zusätzliche Nachweise, die sich in der Nähe von "idMatch" befinden.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-233">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="4cf6e-234">Stimmt überein mit: Sie geben einen Feldnamen im EDM-Schema für den Datenspeicher an.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-234">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="4cf6e-235">**Ressource:** In diesem Abschnitt werden der Name und die Beschreibung für den vertraulichen Typ in mehreren Sprachversionen angegeben.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-235">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="4cf6e-236">idRef: Sie geben die GUID für die ExactMatch-ID an.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-236">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="4cf6e-237">Name und Beschreibungen: nach Bedarf anpassen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-237">Name & descriptions: customize as required.</span></span>

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

1. <span data-ttu-id="4cf6e-238">Laden Sie das Regelpaket hoch, indem Sie nacheinander die folgenden PowerShell-Cmdlets ausführen:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-238">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="4cf6e-239">Sie haben die EDM-basierte Klassifizierung nun eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-239">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="4cf6e-240">Der nächste Schritt ist das Hashen vertraulicher Daten, gefolgt vom Hochladen der Hashes für die Indizierung.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-240">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="4cf6e-241">Wie Sie im vorherigen Verfahren erfahren haben, wurden im PatientRecords-Schema fünf Felder als durchsuchbar definiert: *PatientID*, *MRN*, *SSN*, *Phone* und *DOB*.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-241">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="4cf6e-242">Unser Beispiel für ein Regelpaket enthält diese Felder und verweist auf die Datenbankschemadatei (**edm.xml**), mit einem  *ExactMatch* -Element pro durchsuchbarem Feld.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-242">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="4cf6e-243">Sehen Sie sich das folgende ExactMatch-Element an:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-243">Consider the following ExactMatch item:</span></span>

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

<span data-ttu-id="4cf6e-244">Beachten Sie in diesem Beispiel Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-244">In this example, note that:</span></span>

- <span data-ttu-id="4cf6e-245">Der dataStore-Name verweist auf die zuvor erstellte CSV-Datei: **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-245">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="4cf6e-246">Der idMatch-Wert verweist auf ein durchsuchbares Feld, das in der Datenbankschema-Datei aufgelistet ist: **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-246">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="4cf6e-247">Der classification-Wert verweist auf einen vorhandenen oder benutzerdefinierten vertraulichen Informationstyp: **classification = "US-Sozialversicherungsnummer (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-247">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="4cf6e-248">(In diesem Fall wird der vorhandene vertrauliche Informationstyp "US-Sozialversicherungsnummer" verwendet.)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-248">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="4cf6e-249">Es kann zwischen 10–60 Minuten dauern, bis das EDMSchema durch Ergänzungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-249">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="4cf6e-250">Das Update muss abgeschlossen sein, bevor Sie Schritte ausführen, die die Zusätze verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-250">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="4cf6e-251">Bearbeiten des Schemas für die EDM-basierte Klassifikation</span><span class="sxs-lookup"><span data-stu-id="4cf6e-251">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="4cf6e-252">Wenn Sie Änderungen an Ihrer **edm.xml**-Datei vornehmen und z. B. ändern möchten, welche Felder für die EDM-basierte Klassifikation verwendet werden, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-252">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="4cf6e-253">Bearbeiten Sie Ihre **edm.xml**-Datei (die Datei, die im Abschnitt [Definieren des Schemas](#define-the-schema-for-your-database-of-sensitive-information) in diesem Artikel behandelt wird).</span><span class="sxs-lookup"><span data-stu-id="4cf6e-253">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="4cf6e-254">Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="4cf6e-254">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="4cf6e-255">Führen Sie die folgenden Cmdlets nacheinander aus, um Ihr Datenbankschema zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-255">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="4cf6e-256">Sie werden zu folgenden Bestätigungen aufgefordert:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-256">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="4cf6e-257">Bestätigen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-257">Confirm</span></span>
      >
      > <span data-ttu-id="4cf6e-258">Möchten Sie diese Aktion wirklich ausführen?</span><span class="sxs-lookup"><span data-stu-id="4cf6e-258">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="4cf6e-259">Das EDM-Schema für den Datenspeicher „patientrecords“ wird aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-259">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="4cf6e-260">\[J\] Ja \[A\] Ja für alle \[N\] Nein \[L\] Nein für alle \[?\] Hilfe (Standard ist "J"):</span><span class="sxs-lookup"><span data-stu-id="4cf6e-260">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="4cf6e-261">Wenn Sie möchten, dass Ihre Änderungen ohne Bestätigung durchgeführt werden, verwenden Sie in Schritt 3 stattdessen das folgende Cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="4cf6e-261">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="4cf6e-262">Es kann zwischen 10–60 Minuten dauern, bis das EDMSchema durch Ergänzungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-262">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="4cf6e-263">Das Update muss abgeschlossen sein, bevor Sie Schritte ausführen, die die Zusätze verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-263">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="4cf6e-264">Entfernen des Schemas für die EDM-basierte Klassifikation</span><span class="sxs-lookup"><span data-stu-id="4cf6e-264">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="4cf6e-265">(Nach Bedarf) Wenn Sie das Schema entfernen möchten, das Sie für die EDM-basierte Klassifizierung verwenden, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-265">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="4cf6e-266">Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="4cf6e-266">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="4cf6e-267">Führen Sie die folgenden PowerShell-Cmdlets aus, und ersetzen Sie dabei den Datenspeichernamen "patient records" durch den Namen, den Sie entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-267">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="4cf6e-268">Sie werden zum Bestätigen aufgefordert:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-268">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="4cf6e-269">Bestätigen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-269">Confirm</span></span>
      >
      > <span data-ttu-id="4cf6e-270">Möchten Sie diese Aktion wirklich ausführen?</span><span class="sxs-lookup"><span data-stu-id="4cf6e-270">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="4cf6e-271">Das EDM-Schema für den Datenspeicher „patientrecords“ wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-271">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="4cf6e-272">\[J\] Ja \[A\] Ja für alle \[N\] Nein \[L\] Nein für alle \[?\] Hilfe (Standard ist "J"):</span><span class="sxs-lookup"><span data-stu-id="4cf6e-272">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="4cf6e-273">Wenn Sie möchten, dass Ihre Änderungen ohne Bestätigung durchgeführt werden, verwenden Sie in Schritt 2 stattdessen das folgende Cmdlet: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="4cf6e-273">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>


<!-- salt notes
need two salting procedures, one for onestep from the externally facing and another for two step, on an internal machine then the upload from the external machine

- create A  folder put the edmupload agent and, csv and salt file there, run all processes there
- 
- stuff you need to have first: DataStoreName, /DataFile name (csv file)  /Hashlocation

- salt can be randomly generated by Microsoft or can be provided by the customer. If provided by the customer it must follow  format of 64 character, and can contain only letters or 0-9 characters.  Use a website to generate a valid salt value.
 
- can run EDMuploadagent.exe from PS or Windows cmd window . tested on Windows Server 2016 or Windows 10 and dot net version 4.6.2

when defiuning the schema file the searchable fields must be either an out of box SIT or custom SIT, only 5 fields )column headings) can be searchable

1. From outbound access device from the cmd prompt run EdmUploadAgent.exe /Authorize -  
2. data store schema must have already been uploaded
3.  create hash first then do upload
4. EdmUploadAgent.exe /CreateHash /DataFile (where the data file is ) E:\emd\test\data\schema32_1000000,csv /HashLocation  (where to store it) E:\edm\tat\hash this makes the salt file and the hash file as output
5. next is upload EdmUploadAgent.exe /UploadHash /DataStoreName (found in the Schema file DataSore name="FOO" /HashFile (path to hash file locaztion and file name /HashLocation path to hash)  for example
1.EdmUploadAgent/exe /UploadHash /DataStoreName schema321 /HashFile E:\edm\test\hash\schema32_10000000.EdmHash /HashLocation E:\edm\test\hash  -this one  uses MSFT generated salt, so no need to provide

Salt is an optional parameter so if yo uwant to use a custom salt add /salt and the salt value if salt file not copied to the outbound machine 

OR copy both files hash and salt to the same directory and the commmand will get both


OR do it in single step hash, salt ulopad

!! once they download the updated upload agent they will always have SALT, there is no going back.


all in one step: EdmUploadAgent.exe /UploadData /DataStoreName schema321 /DataFile E:\edm\test\data\schema32_10000.csv /HashLocation E:\edm\test\hash

tshooting/check status cmd



Once it gets to completed the admin can start using it in the custom SIT

they have to get their own custom SALT

just copy SALT over in a secure fashion










1.
6.
7.
1.  


 -->

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="4cf6e-274">Teil 2: Hashvorgang durchführen und vertrauliche Daten hochladen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-274">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="4cf6e-275">In dieser Phase richten Sie eine benutzerdefinierte Sicherheitsgruppe, ein Benutzerkonto und das Tool EDM-Upload-Agent ein.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-275">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="4cf6e-276">Dann verwenden Sie das Tool, um für die vertraulichen Daten mit Salt-Wert einen Hashvorgang durchzuführen und sie hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-276">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="4cf6e-277">Der Hashvorgang und das Hochlande können mit einem einzigen Computer durchgeführt werden. Sie können aber auch den Hashvorgang vom Upload trennen, um größere Sicherheit zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-277">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="4cf6e-278">Wenn Sie den Hashvorgang und das Hochladen von einem Computer aus durchführen möchten, muss dieser eine direkte Verbindung zu Ihrem Microsoft 365-Mandanten herstellen können.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-278">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="4cf6e-279">Dies setzt voraus, dass für den Hashvorgang die vertraulichen Datendateien im Klartext auf diesem Computer bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-279">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="4cf6e-280">Wenn Sie Ihre vertrauliche Datendatei im Klartext nicht verfügbar machen möchten, können Sie den Hashvorgang auf einem Computer an einem sicheren Ort durchführen, und dann die Hashdatei und die Saltdatei auf einen Computer kopieren, der für das Hochladen eine direkte Verbindung mit Ihrem Microsoft 365-Mandanten herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-280">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="4cf6e-281">In diesem Szenario benötigen Sie das den EDM-Upload-Agenten auf beiden Computern.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-281">In this scenario, you will need the EDMUploadAgent on both computers.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="4cf6e-282">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-282">Prerequisites</span></span>

- <span data-ttu-id="4cf6e-283">Ein Microsoft 365-Geschäfts-, Schul- oder Unikonto, das der **EDM-\_DataUploaders**-Sicherheitsgruppe hinzugefügt wird</span><span class="sxs-lookup"><span data-stu-id="4cf6e-283">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="4cf6e-284">Einen Computer mit Windows 10 oder Windows Server 2016 mit .NET Version 4.6.2, um den EDM-Upload-Agenten auszuführen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-284">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="4cf6e-285">Ein Verzeichnis auf dem für das Hochladen verwendeten Computer für den:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-285">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="4cf6e-286">EDM-Upload-Agenten</span><span class="sxs-lookup"><span data-stu-id="4cf6e-286">EDMUploadAgent</span></span>
    - <span data-ttu-id="4cf6e-287">Ihre vertrauliche Elementdatei im CSV-Format (in unseren Beispielen **"PatientRecords.csv"**)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-287">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="4cf6e-288">sowie die Output-Hash- und-Saltdateien</span><span class="sxs-lookup"><span data-stu-id="4cf6e-288">and the output hash and salt files</span></span>
    - <span data-ttu-id="4cf6e-289">Den Namen des Datenspeichers aus der Datei **EDM.xml** (in diesem Beispiel `PatientRecords`)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-289">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="4cf6e-290">Einrichten der Sicherheitsgruppe und des Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="4cf6e-290">Set up the security group and user account</span></span>

1. <span data-ttu-id="4cf6e-291">Als globaler Administrator gehen Sie über den entsprechenden [Link für Ihr Abonnement](#portal-links-for-your-subscription) zum Verwaltungszentrum und  [erstellen Sie eine Sicherheitsgruppe](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) namens **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-291">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="4cf6e-292">Fügen Sie einen oder mehrere Benutzer zur **EDM\_DataUploaders**-Sicherheitsgruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-292">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="4cf6e-293">(Diese Benutzer verwalten die Datenbank mit vertraulichen Informationen.)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-293">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="4cf6e-294">Hash und Upload von einem Computer</span><span class="sxs-lookup"><span data-stu-id="4cf6e-294">Hash and upload from one computer</span></span>

<span data-ttu-id="4cf6e-295">Dieser Computer muss direkten Zugriff auf Ihren Microsoft 365-Mandanten haben.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-295">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="4cf6e-296">Bevor Sie mit diesem Verfahren beginnen, stellen Sie sicher, dass Sie Mitglied der  **EDM\_DataUploaders** -Sicherheitsgruppe sind.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-296">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="4cf6e-297">Links zum EDM-Upload-Agenten nach Abonnementtyp</span><span class="sxs-lookup"><span data-stu-id="4cf6e-297">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="4cf6e-298">Handel und GCC</span><span class="sxs-lookup"><span data-stu-id="4cf6e-298">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="4cf6e-299">GCC – hoch</span><span class="sxs-lookup"><span data-stu-id="4cf6e-299">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="4cf6e-300">DoD</span><span class="sxs-lookup"><span data-stu-id="4cf6e-300">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="4cf6e-301">Erstellen Sie ein Arbeitsverzeichnis für das den EDM-Upload-Agenten.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-301">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="4cf6e-302">Das kann beispielsweise das Verzeichnis **C:\EDM\Data** sein.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-302">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="4cf6e-303">Platzieren Sie dort die Datei **PatientRecords.csv"**.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-303">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="4cf6e-304">Laden Sie den für Ihr Abonnement geeigneten [EDM-Upload-Agenten](#links-to-edm-upload-agent-by-subscription-type) herunter und installieren Sie ihn in das im ersten Schritt erstellte Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-304">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

> [!NOTE]
> <span data-ttu-id="4cf6e-305">Der EDM-Upload-Agent unter den oben aufgeführten Links wurde aktualisiert, um automatisch einen Saltwert zu den Hashdaten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-305">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="4cf6e-306">Alternativ können Sie auch ihren eigenen Saltwert angeben.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-306">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="4cf6e-307">Sobald Sie diese Version verwendet haben, können Sie die vorherige Version des EDM-Upload-Agenten nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-307">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
>
> <span data-ttu-id="4cf6e-308">Sie können Daten mit dem EDM-Upload-Agenten nur zwei Mal pro Tag in einen bestimmten Datenspeicherort hochladen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-308">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

> [!TIP]
> <span data-ttu-id="4cf6e-309">Um eine Liste der unterstützten Befehlsparameter zu erhalten, führen Sie den Agenten ohne Argumente aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-309">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="4cf6e-310">Zum Beispiel "EdmUploadAgent.exe".</span><span class="sxs-lookup"><span data-stu-id="4cf6e-310">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="4cf6e-311">Autorisieren Sie den EDM-Upload-Agenten Öffnen Sie dafür die Eingabeaufforderung (als Administrator), wechseln Sie ins Verzeichnis **C:\EDM\Data** und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-311">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="4cf6e-312">Melden Sie sich mit Ihrem Microsoft 365-Geschäfts-, Schul- oder Unikonto an, das der Sicherheitsgruppe „EDM_DataUploaders“hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-312">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="4cf6e-313">Ihre Mandanteninformationen werden aus dem Benutzerkonto extrahiert, um die Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-313">Your tenant information is extracted from the user account to make the connection.</span></span>

4. <span data-ttu-id="4cf6e-314">Um den Hashvorgang durchzuführen die vertraulichen Daten hochzuladen, führen Sie den folgenden Befehl in der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-314">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="4cf6e-315">Beispiel: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="4cf6e-315">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="4cf6e-316">Dadurch wird dem Hashwert automatisch ein zufällig generierter Saltwert hinzugefügt, um die Sicherheit zu vergrößern.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-316">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="4cf6e-317">Wenn Sie optional einen eigenen Saltwert verwenden möchten, fügen Sie dem Befehl **/Salt <saltvalue>** hinzu.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-317">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="4cf6e-318">Dieser Wert muss 64 Zeichen umfassen und darf nur die Zeichen a-z und die Ziffern 0-9 enthalten.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-318">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="4cf6e-319">Überprüfen Sie den Uploadstatus, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-319">Check the upload status by running this command:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

<span data-ttu-id="4cf6e-320">Beispiel: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="4cf6e-320">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

<span data-ttu-id="4cf6e-321">Suchen Sie nach dem Status in **ProcessingInProgress**.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-321">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="4cf6e-322">Überprüfen Sie den Status alle paar Minuten, bis er sich zu **Abgeschlossen** geändert hat.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-322">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="4cf6e-323">Sobald der Status „Abgeschlossen“ angezeigt wird, können Sie die EDM-Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-323">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="4cf6e-324">Trennen von Hash und Upload</span><span class="sxs-lookup"><span data-stu-id="4cf6e-324">Separate Hash and upload</span></span>

<span data-ttu-id="4cf6e-325">Führen Sie den Hashvorgang auf einem Computer in einer sicheren Umgebung aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-325">Perform the hash on a computer in a secure environment.</span></span>

1. <span data-ttu-id="4cf6e-326">Führen Sie in den Eingabeaufforderungsfenstern den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-326">Run the following command in Command Prompt windows:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="4cf6e-327">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-327">For example:</span></span>

> <span data-ttu-id="4cf6e-328">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="4cf6e-328">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="4cf6e-329">Dadurch wird eine Hashdatei und eine Saltdatei mit diesen Erweiterungen ausgegeben, wenn Sie die Option **/Salt <saltvalue>** nicht angegeben haben:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-329">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
- <span data-ttu-id="4cf6e-330">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="4cf6e-330">.EdmHash</span></span>
- <span data-ttu-id="4cf6e-331">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="4cf6e-331">.EdmSalt</span></span>

2. <span data-ttu-id="4cf6e-332">Kopieren Sie diese Dateien auf sichere Weise auf den Computer, den Sie verwenden, um Ihre CSV-Datei mit den vertraulichen Elementen (PatientRecords) in ihren-Mandanten hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-332">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

<span data-ttu-id="4cf6e-333">Führen Sie zum Hochladen gehashter Daten den folgenden Befehl in der Windows-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-333">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="4cf6e-334">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-334">For example:</span></span>

> <span data-ttu-id="4cf6e-335">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="4cf6e-335">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="4cf6e-336">Führen Sie zur Überprüfung, ob Ihre vertraulichen Daten hochgeladen wurden, den folgenden Befehl in der Windows-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-336">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="4cf6e-337">Sie sehen eine Liste der Datenspeicher und wann sie zuletzt aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-337">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="4cf6e-338">Wenn Sie alle Daten sehen möchten, die in einen bestimmten Store hochgeladen wurden, führen Sie den folgenden Befehl in einer Windows-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-338">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="4cf6e-339">Fahren Sie mit dem Einrichten des Prozesses und des Zeitplans für das [Aktualisieren der Datenbank für vertrauliche Informationen](#refreshing-your-sensitive-information-database) fort.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-339">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="4cf6e-340">Sie können nun die EDM-basierte Klassifikation mit Ihren Microsoft Cloud Services verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-340">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="4cf6e-341">Sie können beispielsweise [eine DLP-Richtlinie mithilfe der EDM-basierten Klassifizierung einrichten](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="4cf6e-341">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="4cf6e-342">Aktualisieren der Datenbank für vertrauliche Informationen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-342">Refreshing your sensitive information database</span></span>

<span data-ttu-id="4cf6e-343">Sie können Ihre Datenbank für vertrauliche Informationen täglich aktualisieren, und das EDM-Upload-Tool kann die vertraulichen Daten neu indizieren und dann die indizierten Daten erneut hochladen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-343">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="4cf6e-344">Ermitteln Sie den Vorgang und die Häufigkeit (täglich oder wöchentlich) zum Aktualisieren der Datenbank mit vertraulichen Informationen.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-344">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="4cf6e-345">Exportieren Sie die vertraulichen Daten erneut in eine App, wie z. B. Microsoft Excel, und speichern Sie die Datei im CSV-Format.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-345">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="4cf6e-346">Behalten Sie den Dateinamen und den Speicherort bei, den Sie beim Ausführen der unter  [Hashen und Hochladen vertraulicher Daten](#part-2-hash-and-upload-the-sensitive-data) beschriebenen Schritte verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-346">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="4cf6e-347">Wenn es keine Änderungen an der Struktur (Feldnamen) der CSV-Datei gibt, müssen Sie auch keine an der Datenbankschemadatei vornehmen, wenn Sie die Daten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-347">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="4cf6e-348">Wenn Sie jedoch Änderungen vornehmen müssen, stellen Sie sicher, dass Sie das Datenbankschema und Ihr Regelpaket entsprechend bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-348">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="4cf6e-349">Mithilfe des  [Aufgabenplaners](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page)  können Sie die Schritte 2 und 3 im Verfahren [Hashen und Hochladen vertraulicher Daten](#part-2-hash-and-upload-the-sensitive-data)  automatisieren.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-349">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="4cf6e-350">Sie können Aufgaben mithilfe verschiedener Methoden planen:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-350">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="4cf6e-351">Methode</span><span class="sxs-lookup"><span data-stu-id="4cf6e-351">Method</span></span>             | <span data-ttu-id="4cf6e-352">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="4cf6e-352">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="4cf6e-353">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4cf6e-353">Windows PowerShell</span></span>     | <span data-ttu-id="4cf6e-354">Siehe die Dokumentation [Aufgabenplanung](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) und das [PowerShell-Beispielskript](#example-powershell-script-for-task-scheduler) in diesem Artikel</span><span class="sxs-lookup"><span data-stu-id="4cf6e-354">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="4cf6e-355">Aufgabenplaner-API</span><span class="sxs-lookup"><span data-stu-id="4cf6e-355">Task Scheduler API</span></span>     | <span data-ttu-id="4cf6e-356">Lesen Sie die Dokumentation [Aufgabenplanung](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-356">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="4cf6e-357">Windows-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="4cf6e-357">Windows user interface</span></span> | <span data-ttu-id="4cf6e-358">Klicken Sie in Windows auf **Start**, und geben Sie „Aufgabenplanung“ ein.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-358">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="4cf6e-359">Klicken Sie dann in der Ergebnisliste mit der rechten Maustaste auf **Aufgabenplanung** und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-359">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="4cf6e-360">„PowerShell-Beispielskript“ für „Aufgabenplanung“</span><span class="sxs-lookup"><span data-stu-id="4cf6e-360">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="4cf6e-361">Dieser Abschnitt enthält ein Beispiel für ein PowerShell-Skript, mit dem Sie Ihre Aufgaben zum Hashen von Daten und Hochladen gehashter Daten planen können:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-361">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="4cf6e-362">So planen Sie das Hashen und Hochladen in einem kombinierten Schritt</span><span class="sxs-lookup"><span data-stu-id="4cf6e-362">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="4cf6e-363">So planen Sie das Hashen und Hochladen als separate Schritte</span><span class="sxs-lookup"><span data-stu-id="4cf6e-363">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="4cf6e-364">Teil 3: Verwenden der EDM-basierten Klassifizierung mit Ihren Microsoft Cloud Services</span><span class="sxs-lookup"><span data-stu-id="4cf6e-364">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="4cf6e-365">Diese Speicherorte sind unterstützte Typen vertraulicher EDM-Informationen:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-365">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="4cf6e-366">DLP für Exchange Online (E-Mail)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-366">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="4cf6e-367">OneDrive for Business (Dateien)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-367">OneDrive for Business (files)</span></span>
- <span data-ttu-id="4cf6e-368">Microsoft Teams (Unterhaltungen)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-368">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="4cf6e-369">DLP für SharePoint (Dateien)</span><span class="sxs-lookup"><span data-stu-id="4cf6e-369">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="4cf6e-370">DLP-Richtlinien für Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4cf6e-370">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="4cf6e-371">Vertrauliche EDM-Informationstypen für die folgenden Szenarien sind derzeit in der Entwicklung, aber noch nicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="4cf6e-371">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="4cf6e-372">automatische Klassifizierung von Vertraulichkeits- und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-372">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="4cf6e-373">Erstellen einer DLP-Richtlinie mit EDM</span><span class="sxs-lookup"><span data-stu-id="4cf6e-373">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="4cf6e-374">Gehen Sie zum Security & Compliance Center, indem Sie den entsprechenden [Link für Ihr Abonnement](#portal-links-for-your-subscription) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-374">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="4cf6e-375">Klicken Sie auf die **Richtlinie** \> **zur Verhinderung von Datenverlust**.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-375">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="4cf6e-376">Wählen Sie **Richtlinie erstellen** \> **Benutzerdefiniert** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-376">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="4cf6e-377">Geben Sie auf der Registerkarte **Richtlinie benennen** einen Namen und eine Beschreibung ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-377">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="4cf6e-378">Wählen Sie auf der Registerkarte **Speicherorte auswählen**  **Bestimmte Speicherorte auswählen** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-378">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="4cf6e-379">Wählen Sie in der Spalte **Status**  **Exchange-E-Mail, OneDrive-Konten, Teams-Chat und Kanalnachricht** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-379">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="4cf6e-380">Wählen Sie auf der Registerkarte **Richtlinieneinstellungen**  **Erweiterte Einstellungen verwenden** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-380">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="4cf6e-381">Wählen Sie **+ Neue Regel** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-381">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="4cf6e-382">Geben Sie im Abschnitt **Name** einen Namen und eine Beschreibung für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-382">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="4cf6e-383">Wählen Sie im Abschnitt **Bedingungen** in der Liste **+ Bedingung hinzufügen**  **Inhalt enthält vertraulichen Typ** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-383">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![Inhalt enthält sensible Informationstypen](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="4cf6e-385">Suchen Sie den vertraulichen Informationstyp, den Sie beim Einrichten Ihres Regelpakets erstellt haben, und wählen Sie dann **+ Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-385">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="4cf6e-386">Wählen Sie dann **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-386">Then choose **Done**.</span></span>

12. <span data-ttu-id="4cf6e-387">Wählen Sie Optionen für die Regel aus, wie z. B. **Benutzerbenachrichtigungen**, **Außerkraftsetzungen durch Benutzer**, **Schadensberichte** usw., und dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-387">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="4cf6e-388">Überprüfen Sie auf der Registerkarte **Richtlinieneinstellungen** Ihre Regeln und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-388">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="4cf6e-389">Geben Sie an, ob Sie die Richtlinie sofort aktivieren, testen oder deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-389">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="4cf6e-390">Wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-390">Then choose **Next**.</span></span>

15. <span data-ttu-id="4cf6e-391">Überprüfen Sie auf der Registerkarte **Überprüfen Sie Ihre Einstellungen** Ihre Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-391">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="4cf6e-392">Nehmen Sie alle nötigen Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-392">Make any needed changes.</span></span> <span data-ttu-id="4cf6e-393">Wenn Sie fertig sind, wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-393">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="4cf6e-394">Es kann ungefähr eine Stunde dauern, bis Ihre neue DLP-Richtlinie im Rechenzentrum erscheint.</span><span class="sxs-lookup"><span data-stu-id="4cf6e-394">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4cf6e-395">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="4cf6e-395">Related articles</span></span>

- [<span data-ttu-id="4cf6e-396">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-396">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="4cf6e-397">Benutzerdefinierte vertrauliche Informationstypen</span><span class="sxs-lookup"><span data-stu-id="4cf6e-397">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="4cf6e-398">Überblick über DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4cf6e-398">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="4cf6e-399">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4cf6e-399">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="4cf6e-400">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="4cf6e-400">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema?view=exchange-ps)

