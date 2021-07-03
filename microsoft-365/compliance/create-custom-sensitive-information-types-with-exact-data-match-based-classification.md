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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie benutzerdefinierte vertrauliche Informationstypen mit genauer Datenübereinstimmungsklassifizierung erstellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17b9d9b1f551c62e42b2f5291f4d1fba8622f1ae
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287041"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="dff40-103">Erstellen von benutzerdefinierten vertraulichen Informationstypen mit genauer Datenübereinstimmungsklassifizierung</span><span class="sxs-lookup"><span data-stu-id="dff40-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="dff40-104">[Benutzerdefinierte Typen vertraulicher Informationen](sensitive-information-type-learn-about.md) werden verwendet, um vertrauliche Elemente zu identifizieren, sodass Sie verhindern können, dass Sie versehentlich oder in unangemessener Weise geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="dff40-104">[Custom sensitive information types](sensitive-information-type-learn-about.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="dff40-105">Sie definieren einen benutzerdefinierten vertraulichen Informationstyp (SIT) basierend auf:</span><span class="sxs-lookup"><span data-stu-id="dff40-105">You define a custom sensitive information type (SIT)based on:</span></span>

- <span data-ttu-id="dff40-106">Durch Muster</span><span class="sxs-lookup"><span data-stu-id="dff40-106">patterns</span></span>
- <span data-ttu-id="dff40-107">Durch den Nachweis von Schlüsselwörtern, z. B. *Mitarbeiter*,*Badge* oder *ID*</span><span class="sxs-lookup"><span data-stu-id="dff40-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="dff40-108">Ähnliche Zeichen als Nachweis in einem bestimmten Muster</span><span class="sxs-lookup"><span data-stu-id="dff40-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="dff40-109">Konfidenzniveaus</span><span class="sxs-lookup"><span data-stu-id="dff40-109">confidence levels</span></span>

 <span data-ttu-id="dff40-110">Solche benutzerdefinierten vertraulichen Informationstypen erfüllen die geschäftlichen Anforderungen vieler Organisationen.</span><span class="sxs-lookup"><span data-stu-id="dff40-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="dff40-111">Was aber, wenn Sie einen benutzerdefinierten vertraulichen Informationstyp (SIT) nutzen möchten, der genaue Datenwerte verwendet, anstatt eines Typs, der Übereinstimmungen basierend auf generischen Mustern findet?</span><span class="sxs-lookup"><span data-stu-id="dff40-111">But what if you wanted a custom sensitive information type (SIT) that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="dff40-112">Mit einer EDM-basierten Klassifizierung (Exact Data Match, genaue Datenübereinstimmung) können Sie einen benutzerdefinierten Informationstyp mit den folgenden Merkmalen erstellen:</span><span class="sxs-lookup"><span data-stu-id="dff40-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="dff40-113">dynamisch und leicht zu aktualisieren</span><span class="sxs-lookup"><span data-stu-id="dff40-113">be dynamic and easily refreshed</span></span>
- <span data-ttu-id="dff40-114">skalierbarer</span><span class="sxs-lookup"><span data-stu-id="dff40-114">be more scalable</span></span>
- <span data-ttu-id="dff40-115">weniger falsch positive Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="dff40-115">result in fewer false-positives</span></span>
- <span data-ttu-id="dff40-116">arbeitet mit strukturierten vertraulichen Daten</span><span class="sxs-lookup"><span data-stu-id="dff40-116">work with structured sensitive data</span></span>
- <span data-ttu-id="dff40-117">behandelt vertrauliche Informationen sicherer</span><span class="sxs-lookup"><span data-stu-id="dff40-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="dff40-118">mit verschiedenen Microsoft Cloud Services verwendbar</span><span class="sxs-lookup"><span data-stu-id="dff40-118">be used with several Microsoft cloud services</span></span>

![EDM-basierte Klassifikation](../media/EDMClassification.png)

<span data-ttu-id="dff40-120">Die EDM-basierte Klassifikation ermöglicht es Ihnen, benutzerdefinierte vertrauliche Informationstypen zu erstellen, die sich auf genaue Werte in einer Datenbank mit vertraulichen Informationen beziehen.</span><span class="sxs-lookup"><span data-stu-id="dff40-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="dff40-121">Die Datenbank kann täglich aktualisiert werden und bis zu 100 Millionen Datenzeilen enthalten.</span><span class="sxs-lookup"><span data-stu-id="dff40-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="dff40-122">Mitarbeiter, Patienten oder Kunden kommen und gehen und Datensätze ändern sich, aber Ihre benutzerdefinierten vertraulichen Informationstypen bleiben aktuell und anwendbar.</span><span class="sxs-lookup"><span data-stu-id="dff40-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="dff40-123">Darüber hinaus können Sie EDM-basierte Klassifikation mit Richtlinien verwenden, z. B. [Richtlinien zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md) oder [Microsoft Cloud App Security-Dateirichtlinien](/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="dff40-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](dlp-learn-about-dlp.md) or [Microsoft Cloud App Security file policies](/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="dff40-124">Microsoft 365 Information Protection unterstützt Sprachen mit Doppelbyte-Zeichensätzen für:</span><span class="sxs-lookup"><span data-stu-id="dff40-124">Microsoft 365 Information Protection supports double byte character set languages for:</span></span>
>
> - <span data-ttu-id="dff40-125">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="dff40-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="dff40-126">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="dff40-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="dff40-127">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="dff40-127">Korean</span></span>
> - <span data-ttu-id="dff40-128">Japanisch</span><span class="sxs-lookup"><span data-stu-id="dff40-128">Japanese</span></span>
>
> <span data-ttu-id="dff40-129">Diese Unterstützung ist für vertrauliche Informationstypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dff40-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="dff40-130">Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="dff40-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="dff40-131">Erforderliche Lizenzen und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="dff40-131">Required licenses and permissions</span></span>

<span data-ttu-id="dff40-132">Sie müssen ein globaler, Compliance- oder Exchange Online-Administrator sein, um die in diesem Artikel beschriebenen Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dff40-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="dff40-133">Weitere Informationen über DLP-Berechtigungen finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="dff40-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="dff40-134">Die EDM-basierte Klassifizierung ist in diesen Abonnements enthalten.</span><span class="sxs-lookup"><span data-stu-id="dff40-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="dff40-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="dff40-135">Office 365 E5</span></span>
- <span data-ttu-id="dff40-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dff40-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="dff40-137">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="dff40-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="dff40-138">Microsoft E5/ A5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="dff40-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="dff40-139">Portal Links für Ihr Abonnement</span><span class="sxs-lookup"><span data-stu-id="dff40-139">Portal links for your subscription</span></span>

|<span data-ttu-id="dff40-140">Portal</span><span class="sxs-lookup"><span data-stu-id="dff40-140">Portal</span></span>|<span data-ttu-id="dff40-141">Weltweit/GCC</span><span class="sxs-lookup"><span data-stu-id="dff40-141">World Wide/GCC</span></span>|<span data-ttu-id="dff40-142">GCC – hoch</span><span class="sxs-lookup"><span data-stu-id="dff40-142">GCC-High</span></span>|<span data-ttu-id="dff40-143">DOD</span><span class="sxs-lookup"><span data-stu-id="dff40-143">DOD</span></span>|
|---|---|---|---|
|<span data-ttu-id="dff40-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="dff40-144">Office SCC</span></span>|<span data-ttu-id="dff40-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="dff40-145">protection.office.com</span></span>|<span data-ttu-id="dff40-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="dff40-146">scc.office365.us</span></span>|<span data-ttu-id="dff40-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="dff40-147">scc.protection.apps.mil</span></span>|
|<span data-ttu-id="dff40-148">Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="dff40-148">Microsoft 365 Security center</span></span>|<span data-ttu-id="dff40-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dff40-149">security.microsoft.com</span></span>|<span data-ttu-id="dff40-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="dff40-150">security.microsoft.us</span></span>|<span data-ttu-id="dff40-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="dff40-151">security.apps.mil</span></span>|
|<span data-ttu-id="dff40-152">Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="dff40-152">Microsoft 365 Compliance center</span></span>|<span data-ttu-id="dff40-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dff40-153">compliance.microsoft.com</span></span>|<span data-ttu-id="dff40-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="dff40-154">compliance.microsoft.us</span></span>|<span data-ttu-id="dff40-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="dff40-155">compliance.apps.mil</span></span>|

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="dff40-156">Der Workflow auf einen Blick</span><span class="sxs-lookup"><span data-stu-id="dff40-156">The work flow at a glance</span></span>

|<span data-ttu-id="dff40-157">Phase</span><span class="sxs-lookup"><span data-stu-id="dff40-157">Phase</span></span>|<span data-ttu-id="dff40-158">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dff40-158">What's needed</span></span>|
|---|---|
|[<span data-ttu-id="dff40-159">Teil 1: Einrichten der EDM-basierten Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="dff40-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="dff40-160">(je nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="dff40-160">(As needed)</span></span><br/><span data-ttu-id="dff40-161">- [Bearbeiten des Datenbankschemas](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="dff40-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="dff40-162">- [Entfernen des Schemas](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="dff40-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span>|<span data-ttu-id="dff40-163">– Lesezugriff auf vertrauliche Daten</span><span class="sxs-lookup"><span data-stu-id="dff40-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="dff40-164">– Datenbankschema im XML-Format (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="dff40-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="dff40-165">– Regelpaket im XML-Format (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="dff40-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="dff40-166">– Administratorberechtigungen für das Security & Compliance Center (mithilfe von PowerShell)</span><span class="sxs-lookup"><span data-stu-id="dff40-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span>|
|[<span data-ttu-id="dff40-167">Teil 2: Hashen und Hochladen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="dff40-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="dff40-168">(je nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="dff40-168">(As needed)</span></span><br/>[<span data-ttu-id="dff40-169">Aktualisieren der Daten</span><span class="sxs-lookup"><span data-stu-id="dff40-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database)|<span data-ttu-id="dff40-170">– Benutzerdefinierte Sicherheitsgruppe und Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="dff40-170">- Custom security group and user account</span></span><br/><span data-ttu-id="dff40-171">– Lokaler Administratorzugriff auf den Computer mit dem EDM-Upload-Agent</span><span class="sxs-lookup"><span data-stu-id="dff40-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="dff40-172">– Lesezugriff auf vertrauliche Daten</span><span class="sxs-lookup"><span data-stu-id="dff40-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="dff40-173">– Prozess und Zeitplan für die Datenaktualisierung</span><span class="sxs-lookup"><span data-stu-id="dff40-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="dff40-174">Teil 3: Verwenden der EDM-basierten Klassifizierung mit Ihren Microsoft Cloud Services</span><span class="sxs-lookup"><span data-stu-id="dff40-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services)|<span data-ttu-id="dff40-175">– Microsoft 365-Abonnement mit DLP</span><span class="sxs-lookup"><span data-stu-id="dff40-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="dff40-176">– EDM-basiertes Klassifizierungsfeature aktiviert</span><span class="sxs-lookup"><span data-stu-id="dff40-176">- EDM-based classification feature enabled</span></span>|

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="dff40-177">Teil 1: Einrichten der EDM-basierten Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="dff40-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="dff40-178">Das Einrichten und Konfigurieren der EDM-basierten Klassifizierung umfasst:</span><span class="sxs-lookup"><span data-stu-id="dff40-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="dff40-179">Speichern vertraulicher Daten im .csv- oder TSV-Format</span><span class="sxs-lookup"><span data-stu-id="dff40-179">Saving sensitive data in .csv or .tsv format</span></span>](#save-sensitive-data-in-csv-or-tsv-format)
2. [<span data-ttu-id="dff40-180">Definieren Ihres Datenbankschemas für vertrauliche Informationen</span><span class="sxs-lookup"><span data-stu-id="dff40-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="dff40-181">Erstellen eines Regelpakets</span><span class="sxs-lookup"><span data-stu-id="dff40-181">Create a rule package</span></span>](#set-up-a-rule-package)

#### <a name="save-sensitive-data-in-csv-or-tsv-format"></a><span data-ttu-id="dff40-182">Speichern vertraulicher Daten im .csv- oder TSV-Format</span><span class="sxs-lookup"><span data-stu-id="dff40-182">Save sensitive data in .csv or .tsv format</span></span>

1. <span data-ttu-id="dff40-183">Identifizieren Sie die vertraulichen Informationen, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="dff40-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="dff40-184">Exportieren Sie die Daten in eine App, z. B. Microsoft Excel, und speichern Sie die Datei in einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="dff40-184">Export the data to an app, such as Microsoft Excel, and save the file in a text file.</span></span> <span data-ttu-id="dff40-185">Die Datei kann im format .csv (durch Trennzeichen getrennte Werte), TSV (durch Tabstopps getrennte Werte) oder im pipetrennten Format (|) gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="dff40-185">The file can be saved in .csv (comma-separated values), .tsv (tab-separated values), or pipe-separated (|) format.</span></span> <span data-ttu-id="dff40-186">Das TSV-Format wird in Fällen empfohlen, in denen Ihre Datenwerte Kommas enthalten können, z. B. Straßenadressen.</span><span class="sxs-lookup"><span data-stu-id="dff40-186">The .tsv format is recommended in cases where your data values may included commas, such as street addresses.</span></span>
<span data-ttu-id="dff40-187">Die Datendatei kann maximal Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="dff40-187">The data file can include a maximum of:</span></span>
   - <span data-ttu-id="dff40-188">bis zu 100 Millionen Zeilen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="dff40-188">Up to 100 million rows of sensitive data</span></span>
   - <span data-ttu-id="dff40-189">bis zu 32 Spalten (Felder) pro Datenquelle</span><span class="sxs-lookup"><span data-stu-id="dff40-189">Up to 32 columns (fields) per data source</span></span>
   - <span data-ttu-id="dff40-190">bis zu 5 als durchsuchbar markierte Spalten (Felder)</span><span class="sxs-lookup"><span data-stu-id="dff40-190">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="dff40-191">Strukturierung der vertraulichen Daten in der .csv- oder TSV-Datei so, dass die erste Zeile die Namen der Felder enthält, die für die EDM-basierte Klassifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dff40-191">Structure the sensitive data in the .csv or .tsv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="dff40-192">In Ihrer Datei haben Sie möglicherweise Feldnamen wie "ssn", "birthdate", "firstname", "lastname".</span><span class="sxs-lookup"><span data-stu-id="dff40-192">In your file you might have field names such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="dff40-193">Die Namen der Spaltenüberschriften dürfen keine Leerzeichen oder Unterstriche enthalten.</span><span class="sxs-lookup"><span data-stu-id="dff40-193">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="dff40-194">Die CSV-Datei, die wir in diesem Artikel verwenden, trägt beispielsweise den Namen *PatientRecords.csv* und hat u. a. die Spalten *PatientID*, *MRN*, *LastName*, *FirstName* und *SSN*.</span><span class="sxs-lookup"><span data-stu-id="dff40-194">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="dff40-195">Achten Sie auf das Format der Felder für die vertraulichen Daten.</span><span class="sxs-lookup"><span data-stu-id="dff40-195">Pay attention to the format of the sensitive data fields.</span></span> <span data-ttu-id="dff40-196">Insbesondere Felder, die Kommas in ihrem Inhalt enthalten können, z. B. eine Straßenadresse, die den Wert "Seattle,WA" enthält, werden bei der Analyse als zwei separate Felder analysiert, wenn das .csv Format ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="dff40-196">In particular, fields that may contain commas in their content, for example, a street address that contains the value "Seattle,WA" would be parsed as two separate fields when parsed if the .csv format is selected.</span></span> <span data-ttu-id="dff40-197">Um dies zu vermeiden, verwenden Sie das TSV-Format oder umgeben das Komma mit Werten in doppelte Anführungszeichen in der Tabelle mit vertraulichen Daten.</span><span class="sxs-lookup"><span data-stu-id="dff40-197">To avoid this, use the .tsv format or surrounded the comma containing values by double quotes in the sensitive data table.</span></span> <span data-ttu-id="dff40-198">Wenn Kommas, die Werte enthalten, auch Leerzeichen enthalten, müssen Sie eine benutzerdefinierte SIT erstellen, die dem entsprechenden Format entspricht.</span><span class="sxs-lookup"><span data-stu-id="dff40-198">If comma containing values also contain spaces, you need to create a custom SIT that matches the corresponding format.</span></span> <span data-ttu-id="dff40-199">Beispielsweise eine SIT, die zeichenfolgen mit mehreren Wörtern mit Kommas und Leerzeichen erkennt.</span><span class="sxs-lookup"><span data-stu-id="dff40-199">For example, a SIT that detects multi-word string with commas and spaces in it.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="dff40-200">Definieren des Schemas für Ihre Datenbank mit vertraulichen Informationen</span><span class="sxs-lookup"><span data-stu-id="dff40-200">Define the schema for your database of sensitive information</span></span>

<span data-ttu-id="dff40-201">Wenn Sie es aus geschäftlichen oder technischen Gründen vorziehen, PowerShell oder die Befehlszeile nicht zu verwenden, um Ihr Schema und EDM-Muster vertraulicher Informationstypen (Regelpaket) zu erstellen, können Sie den [Assistenten für das Exact Data Match (EDM)-Schema und vertrauliche Informationstypen](sit-edm-wizard.md) verwenden, um sie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dff40-201">If for business or technical reasons, you prefer not to use PowerShell or command line to create your schema and EDM sensitive info type pattern (rule package), you can use the [Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) to create them.</span></span> <span data-ttu-id="dff40-202">Wenn Sie mit dem Erstellen des Schemas und des EDM-vertraulicher-Informationstyp-Musters fertig sind, kehren Sie zurück, um alle Schritte abzuschließen, die erforderlich sind, um Ihren EDM-basierten vertraulicher Informationstyp für die Verwendung verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="dff40-202">When you are done creating the schema and EDM sensitive info type pattern, return to complete all the steps necessary to make your EDM based sensitive information type available for use.</span></span>

> [!NOTE]
> <span data-ttu-id="dff40-203">Der Assistent für die Exact Data Match Schema und vertraulicher Informationstyp ist nur für die World Wide- und GCC-Cloud verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dff40-203">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

1. <span data-ttu-id="dff40-204">Definieren Sie das Schema für die Datenbank mit vertraulichen Informationen im XML-Format (ähnlich wie in unserem Beispiel unten).</span><span class="sxs-lookup"><span data-stu-id="dff40-204">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="dff40-205">Nennen Sie diese Schemadatei **edm.xml** und konfigurieren Sie sie so, dass es für jede Spalte in der Datenbank eine Zeile mit der folgenden Syntax gibt:</span><span class="sxs-lookup"><span data-stu-id="dff40-205">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span>

      <span data-ttu-id="dff40-206">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="dff40-206">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="dff40-207">Verwenden Sie Spaltennamen für *Field name*-Werte.</span><span class="sxs-lookup"><span data-stu-id="dff40-207">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="dff40-208">Verwenden Sie *searchable="true“* für maximal 5 Felder, die durchsuchbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="dff40-208">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="dff40-209">Mindestens ein Feld muss durchsuchbar sein.</span><span class="sxs-lookup"><span data-stu-id="dff40-209">At least one field must be searchable.</span></span>

      <span data-ttu-id="dff40-210">Im folgenden Beispiel definiert die XML-Datei das Schema für eine Datenbank mit Patientendatensätzen, wobei fünf Felder als durchsuchbar angegeben werden: *PatientID*, *MRN*, *SSN*, *Phone* und *DOB*.</span><span class="sxs-lookup"><span data-stu-id="dff40-210">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="dff40-211">(Sie können das Beispiel kopieren, ändern und verwenden.)</span><span class="sxs-lookup"><span data-stu-id="dff40-211">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
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

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a><span data-ttu-id="dff40-212">Konfigurierbare Übereinstimmung unter Verwendung der Felder caseInsensitive und ignoredDelimiters</span><span class="sxs-lookup"><span data-stu-id="dff40-212">Configurable match using the caseInsensitive and ignoredDelimiters fields</span></span>

<span data-ttu-id="dff40-213">Das obige XML-Beispiel verwendet die Felder `caseInsensitive` und `ignoredDelimiters`.</span><span class="sxs-lookup"><span data-stu-id="dff40-213">The above XML sample makes use of the `caseInsensitive` and the `ignoredDelimiters` fields.</span></span>

<span data-ttu-id="dff40-214">Wenn Sie das Feld \***caseInsensitive** _ in Ihre Schemadefinition aufnehmen, das auf den Wert von `true` festgelegt ist, schließt EDM ein Element nicht aus, das auf Groß- und Kleinschreibung für das `PatientID` Feld basiert.</span><span class="sxs-lookup"><span data-stu-id="dff40-214">When you include the \***caseInsensitive** _ field set to the value of `true` in your schema definition, EDM will not exclude an item based on case differences for `PatientID` field.</span></span> <span data-ttu-id="dff40-215">EDM wird also sehen, dass `PatientID` _ *FOO-1234*\* und **fOo-1234** identisch sind.</span><span class="sxs-lookup"><span data-stu-id="dff40-215">So EDM will see, `PatientID` _ *FOO-1234*\* and **fOo-1234** as being identical.</span></span>

<span data-ttu-id="dff40-216">Wenn Sie das Feld **ignoredDelimiters** _ mit unterstützten Zeichen einfügen, ignoriert EDM diese Zeichen im `PatientID`.</span><span class="sxs-lookup"><span data-stu-id="dff40-216">When you include the \***ignoredDelimiters** _ field with supported characters,  EDM will ignore those characters in the `PatientID`.</span></span> <span data-ttu-id="dff40-217">EDM wird also sehen, dass `PatientID` _ *FOO-1234*\* und `PatientID` **FOO#1234** identisch sind.</span><span class="sxs-lookup"><span data-stu-id="dff40-217">So EDM will see, `PatientID` _ *FOO-1234*\* and `PatientID` **FOO#1234** as being identical.</span></span> <span data-ttu-id="dff40-218">Das Banner `ignoredDelimiters` unterstützt alle nicht alphanumerischen Zeichen. Hier einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="dff40-218">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>

- <span data-ttu-id="dff40-219">\.</span><span class="sxs-lookup"><span data-stu-id="dff40-219">\.</span></span>
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \;

<span data-ttu-id="dff40-220">Das Banner `ignoredDelimiters` ist nicht vorhanden:</span><span class="sxs-lookup"><span data-stu-id="dff40-220">The `ignoredDelimiters` flag doesn't support:</span></span>

- <span data-ttu-id="dff40-221">Zeichen 0-9</span><span class="sxs-lookup"><span data-stu-id="dff40-221">characters 0-9</span></span>
- <span data-ttu-id="dff40-222">A-Z</span><span class="sxs-lookup"><span data-stu-id="dff40-222">A-Z</span></span>
- <span data-ttu-id="dff40-223">a-z</span><span class="sxs-lookup"><span data-stu-id="dff40-223">a-z</span></span>
- \"
- \,

<span data-ttu-id="dff40-224">In diesem Beispiel, in dem beide, `caseInsensitive` und `ignoredDelimiters`, verwendet werden, sieht EDM **FOO-1234** und **fOo#1234** als identisch an und klassifiziert das Element als sensiblen Informationstyp für Patientenakten.</span><span class="sxs-lookup"><span data-stu-id="dff40-224">In this example, where both `caseInsensitive` and `ignoredDelimiters` are used, EDM would see **FOO-1234** and **fOo#1234** as  identical and classify the item as a patient record sensitive information type.</span></span>

1. <span data-ttu-id="dff40-225">Verbinden zur Security & Compliance Center PowerShell mithilfe der Verfahren in [Verbinden security & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="dff40-225">Connect to the Security & Compliance Center PowerShell using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="dff40-226">Führen Sie die folgenden Cmdlets nacheinander aus, um das Datenbankschema hochzuladen:</span><span class="sxs-lookup"><span data-stu-id="dff40-226">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="dff40-227">Sie werden zu folgenden Bestätigungen aufgefordert:</span><span class="sxs-lookup"><span data-stu-id="dff40-227">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="dff40-228">Bestätigen</span><span class="sxs-lookup"><span data-stu-id="dff40-228">Confirm</span></span>
      >
      > <span data-ttu-id="dff40-229">Möchten Sie diese Aktion wirklich ausführen?</span><span class="sxs-lookup"><span data-stu-id="dff40-229">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="dff40-230">Das neue EDM-Schema für den Datenspeicher „patientrecords“ wird importiert.</span><span class="sxs-lookup"><span data-stu-id="dff40-230">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="dff40-231">\[J\] Ja \[A\] Ja für alle \[N\] Nein \[L\] Nein für alle \[?\] Hilfe (Standard ist "J"):</span><span class="sxs-lookup"><span data-stu-id="dff40-231">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="dff40-232">Wenn Sie möchten, dass Ihre Änderungen ohne Bestätigung durchgeführt werden, verwenden Sie in Schritt 5 stattdessen das folgende Cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="dff40-232">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="dff40-233">Es kann zwischen 10–60 Minuten dauern, bis das EDMSchema durch Ergänzungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="dff40-233">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="dff40-234">Das Update muss abgeschlossen sein, bevor Sie Schritte ausführen, die die Zusätze verwenden.</span><span class="sxs-lookup"><span data-stu-id="dff40-234">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="dff40-235">Einrichten eines Regelpakets</span><span class="sxs-lookup"><span data-stu-id="dff40-235">Set up a rule package</span></span>

1. <span data-ttu-id="dff40-236">Erstellen Sie ein Regelpaket im XML-Format (mit Unicode-Codierung), ähnlich wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="dff40-236">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="dff40-237">(Sie können das Beispiel kopieren, ändern und verwenden.)</span><span class="sxs-lookup"><span data-stu-id="dff40-237">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="dff40-238">Wenn Sie das Regelpaket einrichten, stellen Sie sicher, dass Sie ordnungsgemäß auf die .csv- oder TSV-Datei und **edm.xml** Datei verweisen.</span><span class="sxs-lookup"><span data-stu-id="dff40-238">When you set up your rule package, make sure to correctly reference your .csv or .tsv file and **edm.xml** file.</span></span> <span data-ttu-id="dff40-239">Sie können das Beispiel kopieren, ändern und verwenden.</span><span class="sxs-lookup"><span data-stu-id="dff40-239">You can copy, modify, and use our example.</span></span> <span data-ttu-id="dff40-240">In dieser XML-Beispieldatei müssen die folgenden Felder so angepasst werden, dass Sie Ihren vertraulichen EDM-Typ erstellen:</span><span class="sxs-lookup"><span data-stu-id="dff40-240">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="dff40-241">**RulePack id und ExactMatch id**: Verwenden Sie [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid), um eine GUID zu generieren.</span><span class="sxs-lookup"><span data-stu-id="dff40-241">**RulePack id & ExactMatch id**: Use [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid) to generate a GUID.</span></span>

      - <span data-ttu-id="dff40-242">**Datenspeicher**: Dieses Feld gibt den zu verwendenden EDM-Nachschlage-Datenspeicher an.</span><span class="sxs-lookup"><span data-stu-id="dff40-242">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="dff40-243">Sie geben einen Datenquellennamen eines konfigurierten EDM-Schemas an.</span><span class="sxs-lookup"><span data-stu-id="dff40-243">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="dff40-244">**idMatch**: Dieses Feld verweist auf das primäre Element für EDM.</span><span class="sxs-lookup"><span data-stu-id="dff40-244">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="dff40-245">Stimmt überein mit: gibt das Feld an, das in der exakten Suche verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dff40-245">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="dff40-246">Sie geben den Namen eines durchsuchbaren Felds im EDM-Schema für den Datenspeicher an.</span><span class="sxs-lookup"><span data-stu-id="dff40-246">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="dff40-247">Klassifizierung: Dieses Feld gibt die Übereinstimmung für den vertraulichen Typ an, der EDM-Nachschlagevorgänge auslöst.</span><span class="sxs-lookup"><span data-stu-id="dff40-247">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="dff40-248">Sie können den Namen oder die GUID eines vorhandenen integrierten oder benutzerdefinierten vertraulichen Informationstyps angeben.</span><span class="sxs-lookup"><span data-stu-id="dff40-248">You can provide the Name or GUID of an existing built-in or custom sensitive information type.</span></span> <span data-ttu-id="dff40-249">Beachten Sie, dass auf alle Zeichenfolgen, die dem angegebenen vertraulichen Informationstyp entsprechen, ein Hash angewendet wird und sie mit jedem Eintrag in der Tabelle mit vertraulichen Informationen verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="dff40-249">Be aware that any string that matches the sensitive information type provided will be hashed and compared to every entry in the sensitive information table.</span></span> <span data-ttu-id="dff40-250">Um Leistungsprobleme zu vermeiden, sollten Sie bei Verwendung eines benutzerdefinierten vertraulichen Informationstyps als Klassifizierungselement in EDM keinen Inhaltstyp verwenden, der einem großen Prozentsatz des Inhalts entspricht (z. B. "beliebige Zahl" oder "beliebiges aus fünf Buchstaben bestehendes Wort"). Fügen Sie hierzu unterstützende Schlüsselwörter hinzu oder schließen Sie Formatierung in die Definition des benutzerdefinierten vertraulichen Klassifizierungsinformationstyps ein.</span><span class="sxs-lookup"><span data-stu-id="dff40-250">In order to avoid causing performance issues, if you use a custom sensitive information type as the Classification element in EDM, avoid using one that will match a large percentage of content (such as "any number" or "any five-letter word") by adding supporting keywords or including formatting in the definition of the custom classification sensitive information type.</span></span>

      - <span data-ttu-id="dff40-251">**Übereinstimmung:** Dieses Feld verweist auf zusätzliche Nachweise, die sich in der Nähe von "idMatch" befinden.</span><span class="sxs-lookup"><span data-stu-id="dff40-251">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="dff40-252">Stimmt überein mit: Sie geben einen Feldnamen im EDM-Schema für den Datenspeicher an.</span><span class="sxs-lookup"><span data-stu-id="dff40-252">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="dff40-253">**Ressource:** In diesem Abschnitt werden der Name und die Beschreibung für den vertraulichen Typ in mehreren Sprachversionen angegeben.</span><span class="sxs-lookup"><span data-stu-id="dff40-253">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="dff40-254">idRef: Sie geben die GUID für die ExactMatch-ID an.</span><span class="sxs-lookup"><span data-stu-id="dff40-254">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="dff40-255">Name und Beschreibungen: nach Bedarf anpassen.</span><span class="sxs-lookup"><span data-stu-id="dff40-255">Name & descriptions: customize as required.</span></span>

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

2. <span data-ttu-id="dff40-256">Laden Sie das Regelpaket hoch, indem Sie nacheinander die folgenden PowerShell-Cmdlets ausführen:</span><span class="sxs-lookup"><span data-stu-id="dff40-256">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="dff40-257">Sie haben die EDM-basierte Klassifizierung nun eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="dff40-257">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="dff40-258">Der nächste Schritt ist das Hashen vertraulicher Daten, gefolgt vom Hochladen der Hashes für die Indizierung.</span><span class="sxs-lookup"><span data-stu-id="dff40-258">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="dff40-259">Wie Sie im vorherigen Verfahren erfahren haben, wurden im PatientRecords-Schema fünf Felder als durchsuchbar definiert: *PatientID*, *MRN*, *SSN*, *Phone* und *DOB*.</span><span class="sxs-lookup"><span data-stu-id="dff40-259">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="dff40-260">In unserem Beispiel für ein Regelpaket sind diese Felder enthalten, und es wird auf die Datenbankschemadatei (**edm.xml**) verwiesen, wobei ein *ExactMatch*-Element pro durchsuchbarem Feld vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="dff40-260">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="dff40-261">Sehen Sie sich das folgende ExactMatch-Element an:</span><span class="sxs-lookup"><span data-stu-id="dff40-261">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="dff40-262">Beachten Sie in diesem Beispiel Folgendes:</span><span class="sxs-lookup"><span data-stu-id="dff40-262">In this example, note that:</span></span>

- <span data-ttu-id="dff40-263">Der dataStore-Name verweist auf die zuvor erstellte CSV-Datei: **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="dff40-263">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="dff40-264">Der idMatch-Wert verweist auf ein durchsuchbares Feld, das in der Datenbankschema-Datei aufgelistet ist: **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="dff40-264">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="dff40-265">Der classification-Wert verweist auf einen vorhandenen oder benutzerdefinierten vertraulichen Informationstyp: **classification = "US-Sozialversicherungsnummer (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="dff40-265">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="dff40-266">(In diesem Fall wird der vorhandene vertrauliche Informationstyp "US-Sozialversicherungsnummer" verwendet.)</span><span class="sxs-lookup"><span data-stu-id="dff40-266">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="dff40-267">Es kann zwischen 10–60 Minuten dauern, bis das EDMSchema durch Ergänzungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="dff40-267">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="dff40-268">Das Update muss abgeschlossen sein, bevor Sie Schritte ausführen, die die Zusätze verwenden.</span><span class="sxs-lookup"><span data-stu-id="dff40-268">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="dff40-269">Nachdem Sie das Regelpaket mit Ihrem EDM-Typ vertraulicher Informationen und Ihre Tabelle vertraulicher Daten importiert haben, können Sie Ihren neu erstellten Typ mit der Funktion **Testen** im EDM-Assistenten im Compliance Center testen.</span><span class="sxs-lookup"><span data-stu-id="dff40-269">After you have imported your rule package with your EDM sensitive info type and have imported your sensitive data table, you can test your newly created type by using the **Test** function in the EDM wizard in the compliance center.</span></span> <span data-ttu-id="dff40-270">Anweisungen zur Verwendung dieser Funktion finden Sie unter [Verwendung des Assistenten für das Schema exakter Datenübereinstimmung und für den Typ vertraulicher Informationen](sit-edm-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="dff40-270">See [Use the Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) for instructions on using this functionality.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="dff40-271">Bearbeiten des Schemas für die EDM-basierte Klassifikation</span><span class="sxs-lookup"><span data-stu-id="dff40-271">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="dff40-272">Wenn Sie Änderungen an Ihrer **edm.xml**-Datei vornehmen und z. B. ändern möchten, welche Felder für die EDM-basierte Klassifikation verwendet werden, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="dff40-272">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

> [!TIP]
> <span data-ttu-id="dff40-273">Sie können Ihr EDM-Schema und Ihre Datendatei ändern, um die **konfigurierbare Übereinstimmung zu nutzen**.</span><span class="sxs-lookup"><span data-stu-id="dff40-273">You can change your EDM schema and data file to take advantage of **configurable match**.</span></span> <span data-ttu-id="dff40-274">Bei der Konfiguration ignoriert EDM bei der Auswertung eines Elements Groß- und Kleinschreibung und einige Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="dff40-274">When configured, EDM will ignore case differences and some delimiters when it evaluates an item.</span></span> <span data-ttu-id="dff40-275">Dies erleichtert die Definition Ihres XML-Schemas und Ihrer vertraulichen Datendateien.</span><span class="sxs-lookup"><span data-stu-id="dff40-275">This makes defining your xml schema and your sensitive data files easier.</span></span> <span data-ttu-id="dff40-276">Weitere Informationen finden Sie unter [Ändern des Schemas für exakte Datenübereinstimmungen, um konfigurierbare Übereinstimmungen zu verwenden](sit-modify-edm-schema-configurable-match.md).</span><span class="sxs-lookup"><span data-stu-id="dff40-276">To learn more see, [Modify Exact Data Match schema to use configurable match](sit-modify-edm-schema-configurable-match.md).</span></span>

1. <span data-ttu-id="dff40-277">Bearbeiten Sie Ihre **edm.mxl**-Datei. (Dies ist die Datei, die im Abschnitt [Definieren des Schemas](#define-the-schema-for-your-database-of-sensitive-information) in diesem Artikel behandelt wird).</span><span class="sxs-lookup"><span data-stu-id="dff40-277">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="dff40-278">Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="dff40-278">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="dff40-279">Führen Sie die folgenden Cmdlets nacheinander aus, um Ihr Datenbankschema zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="dff40-279">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="dff40-280">Sie werden zu folgenden Bestätigungen aufgefordert:</span><span class="sxs-lookup"><span data-stu-id="dff40-280">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="dff40-281">Bestätigen</span><span class="sxs-lookup"><span data-stu-id="dff40-281">Confirm</span></span>
      >
      > <span data-ttu-id="dff40-282">Möchten Sie diese Aktion wirklich ausführen?</span><span class="sxs-lookup"><span data-stu-id="dff40-282">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="dff40-283">Das EDM-Schema für den Datenspeicher „patientrecords“ wird aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="dff40-283">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="dff40-284">\[J\] Ja \[A\] Ja für alle \[N\] Nein \[L\] Nein für alle \[?\] Hilfe (Standard ist "J"):</span><span class="sxs-lookup"><span data-stu-id="dff40-284">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="dff40-285">Wenn Sie möchten, dass Ihre Änderungen ohne Bestätigung durchgeführt werden, verwenden Sie in Schritt 3 stattdessen das folgende Cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="dff40-285">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="dff40-286">Es kann zwischen 10–60 Minuten dauern, bis das EDMSchema durch Ergänzungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="dff40-286">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="dff40-287">Das Update muss abgeschlossen sein, bevor Sie Schritte ausführen, die die Zusätze verwenden.</span><span class="sxs-lookup"><span data-stu-id="dff40-287">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="dff40-288">Entfernen des Schemas für die EDM-basierte Klassifikation</span><span class="sxs-lookup"><span data-stu-id="dff40-288">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="dff40-289">(Nach Bedarf) Wenn Sie das Schema entfernen möchten, das Sie für die EDM-basierte Klassifizierung verwenden, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="dff40-289">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="dff40-290">Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="dff40-290">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="dff40-291">Führen Sie die folgenden PowerShell-Cmdlets aus, und ersetzen Sie dabei den Datenspeichernamen "patient records" durch den Namen, den Sie entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="dff40-291">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="dff40-292">Sie werden zum Bestätigen aufgefordert:</span><span class="sxs-lookup"><span data-stu-id="dff40-292">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="dff40-293">Bestätigen</span><span class="sxs-lookup"><span data-stu-id="dff40-293">Confirm</span></span>
      >
      > <span data-ttu-id="dff40-294">Möchten Sie diese Aktion wirklich ausführen?</span><span class="sxs-lookup"><span data-stu-id="dff40-294">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="dff40-295">Das EDM-Schema für den Datenspeicher „patientrecords“ wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="dff40-295">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="dff40-296">\[J\] Ja \[A\] Ja für alle \[N\] Nein \[L\] Nein für alle \[?\] Hilfe (Standard ist "J"):</span><span class="sxs-lookup"><span data-stu-id="dff40-296">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="dff40-297">Wenn Sie möchten, dass Ihre Änderungen ohne Bestätigung durchgeführt werden, verwenden Sie in Schritt 2 stattdessen das folgende Cmdlet: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="dff40-297">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="dff40-298">Teil 2: Hashvorgang durchführen und vertrauliche Daten hochladen</span><span class="sxs-lookup"><span data-stu-id="dff40-298">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="dff40-299">In dieser Phase richten Sie eine benutzerdefinierte Sicherheitsgruppe, ein Benutzerkonto und das Tool EDM-Upload-Agent ein.</span><span class="sxs-lookup"><span data-stu-id="dff40-299">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="dff40-300">Dann verwenden Sie das Tool, um für die vertraulichen Daten mit Salt-Wert einen Hashvorgang durchzuführen und sie hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="dff40-300">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="dff40-301">Der Hashvorgang und das Hochlande können mit einem einzigen Computer durchgeführt werden. Sie können aber auch den Hashvorgang vom Upload trennen, um größere Sicherheit zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="dff40-301">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="dff40-302">Wenn Sie den Hashvorgang und das Hochladen von einem Computer aus durchführen möchten, muss dieser eine direkte Verbindung zu Ihrem Microsoft 365-Mandanten herstellen können.</span><span class="sxs-lookup"><span data-stu-id="dff40-302">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="dff40-303">Dies setzt voraus, dass für den Hashvorgang die vertraulichen Datendateien im Klartext auf diesem Computer bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="dff40-303">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="dff40-p129">Wenn Sie Ihre vertrauliche Datendatei im Klartext nicht verfügbar machen möchten, können Sie den Hashvorgang auf einem Computer an einem sicheren Ort durchführen, und dann die Hashdatei und die Saltdatei auf einen Computer kopieren, der für das Hochladen eine direkte Verbindung mit Ihrem Microsoft 365-Mandanten herstellen kann. In diesem Szenario benötigen Sie den EDMUploadAgent auf beiden Computern.</span><span class="sxs-lookup"><span data-stu-id="dff40-p129">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload. In this scenario, you will need the EDMUploadAgent on both computers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dff40-306">Wenn Sie den Assistenten für Exact Data Match Schema und vertraulicher Informationstyp verwendet haben, um Ihre Schema- und Musterdateien zu erstellen, ***müssen*** Sie das Schema für dieses Verfahren herunterladen.</span><span class="sxs-lookup"><span data-stu-id="dff40-306">If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, you ***must*** download the schema for this procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="dff40-307">Wenn Ihre Organisation [Den Kundenschlüssel für Microsoft 365 auf Mandantenebene](customer-key-overview.md)eingerichtet hat, nutzt die genaue Datenüberstimmung automatisch die Verschlüsselungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="dff40-307">If your organization has set up [Customer Key for Microsoft 365 at the tenant level](customer-key-overview.md), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="dff40-308">Dies ist nur für Mandanten mit E5-Lizenz in der kommerziellen Cloud verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dff40-308">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="dff40-309">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="dff40-309">Prerequisites</span></span>

- <span data-ttu-id="dff40-310">Ein Microsoft 365-Geschäfts-, Schul- oder Unikonto, das der **EDM-\_DataUploaders**-Sicherheitsgruppe hinzugefügt wird</span><span class="sxs-lookup"><span data-stu-id="dff40-310">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="dff40-311">Einen Computer mit Windows 10 oder Windows Server 2016 mit .NET Version 4.6.2, um den EDM-Upload-Agenten auszuführen</span><span class="sxs-lookup"><span data-stu-id="dff40-311">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="dff40-312">Ein Verzeichnis auf dem für das Hochladen verwendeten Computer für den:</span><span class="sxs-lookup"><span data-stu-id="dff40-312">a directory on your upload machine for the:</span></span>
  - <span data-ttu-id="dff40-313">EDM-Upload-Agenten</span><span class="sxs-lookup"><span data-stu-id="dff40-313">EDMUploadAgent</span></span>
  - <span data-ttu-id="dff40-314">Ihre Datei für vertrauliche Elemente im .csv- oder TSV-Format **PatientRecords.csv** in unseren Beispielen</span><span class="sxs-lookup"><span data-stu-id="dff40-314">your sensitive item file in .csv or .tsv format, **PatientRecords.csv** in our examples</span></span>
  - <span data-ttu-id="dff40-315">Die Ausgabehash- und Saltdateien</span><span class="sxs-lookup"><span data-stu-id="dff40-315">the output hash and salt files</span></span>
  - <span data-ttu-id="dff40-316">Den Namen des Datenspeichers aus der Datei **EDM.xml** (in diesem Beispiel `PatientRecords`)</span><span class="sxs-lookup"><span data-stu-id="dff40-316">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>
- <span data-ttu-id="dff40-317">Wenn Sie den Assistenten für das [Schema exakter Datenübereinstimmung und den vertraulichen Informationstyp](sit-edm-wizard.md) verwendet haben, ***müssen*** Sie ihn herunterladen.</span><span class="sxs-lookup"><span data-stu-id="dff40-317">If you used the [Exact Data Match schema and sensitive information type wizard](sit-edm-wizard.md) you ***must*** download it</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="dff40-318">Einrichten der Sicherheitsgruppe und des Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="dff40-318">Set up the security group and user account</span></span>

1. <span data-ttu-id="dff40-319">Als globaler Administrator gehen Sie über den entsprechenden [Link für Ihr Abonnement](#portal-links-for-your-subscription) zum Verwaltungszentrum und [erstellen Sie eine Sicherheitsgruppe](/office365/admin/email/create-edit-or-delete-a-security-group) namens **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="dff40-319">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](/office365/admin/email/create-edit-or-delete-a-security-group) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="dff40-320">Fügen Sie einen oder mehrere Benutzer zu der **EDM\_DataUploaders**-Sicherheitsgruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="dff40-320">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="dff40-321">(Diese Benutzer verwalten die Datenbank mit vertraulichen Informationen.)</span><span class="sxs-lookup"><span data-stu-id="dff40-321">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="dff40-322">Hash und Upload von einem Computer</span><span class="sxs-lookup"><span data-stu-id="dff40-322">Hash and upload from one computer</span></span>

<span data-ttu-id="dff40-323">Dieser Computer muss direkten Zugriff auf Ihren Microsoft 365-Mandanten haben.</span><span class="sxs-lookup"><span data-stu-id="dff40-323">This computer must have direct access to your Microsoft 365 tenant.</span></span>

> [!NOTE]
>
> <span data-ttu-id="dff40-324">Bevor Sie mit diesem Verfahren beginnen, stellen Sie sicher, dass Sie Mitglied der **EDM\_DataUploaders**-Sicherheitsgruppe sind.</span><span class="sxs-lookup"><span data-stu-id="dff40-324">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>
>
> <span data-ttu-id="dff40-325">Optional können Sie eine Überprüfung für Ihre .csv- oder TSV-Datei vor dem Hochladen ausführen, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="dff40-325">Optionally, you can run a validation against your .csv or .tsv file before uploading by running:</span></span>
>
> `EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
> <span data-ttu-id="dff40-326">Weitere Informationen zu allen von EdmUploadAgent.exe >unterstützten Parametern erhalten Sie</span><span class="sxs-lookup"><span data-stu-id="dff40-326">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="dff40-327">Links zum EDM-Upload-Agenten nach Abonnementtyp</span><span class="sxs-lookup"><span data-stu-id="dff40-327">Links to EDM upload agent by subscription type</span></span>

- <span data-ttu-id="dff40-328">[Handel + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) – die meisten gewerblichen Kunden sollten dies verwenden</span><span class="sxs-lookup"><span data-stu-id="dff40-328">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
- <span data-ttu-id="dff40-329">[GCC-Hoch](https://go.microsoft.com/fwlink/?linkid=2137521) – Dies ist speziell für Cloud-Abonnenten mit hoher Sicherheit in der Regierung</span><span class="sxs-lookup"><span data-stu-id="dff40-329">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
- <span data-ttu-id="dff40-330">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) – Dies ist speziell für Cloud-Kunden des US-Verteidigungsministeriums</span><span class="sxs-lookup"><span data-stu-id="dff40-330">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

1. <span data-ttu-id="dff40-331">Erstellen Sie ein Arbeitsverzeichnis für das den EDM-Upload-Agenten.</span><span class="sxs-lookup"><span data-stu-id="dff40-331">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="dff40-332">Das kann beispielsweise das Verzeichnis **C:\EDM\Data** sein.</span><span class="sxs-lookup"><span data-stu-id="dff40-332">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="dff40-333">Platzieren Sie dort die Datei **PatientRecords.csv"**.</span><span class="sxs-lookup"><span data-stu-id="dff40-333">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="dff40-334">Laden Sie den für Ihr Abonnement geeigneten [EDM-Upload-Agenten](#links-to-edm-upload-agent-by-subscription-type) herunter und installieren Sie ihn in das im ersten Schritt erstellte Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="dff40-334">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dff40-335">Der EDM-Upload-Agent unter den oben aufgeführten Links wurde aktualisiert, um automatisch einen Saltwert zu den Hashdaten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="dff40-335">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="dff40-336">Alternativ können Sie auch ihren eigenen Saltwert angeben.</span><span class="sxs-lookup"><span data-stu-id="dff40-336">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="dff40-337">Sobald Sie diese Version verwendet haben, können Sie die vorherige Version des EDM-Upload-Agenten nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="dff40-337">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
   >
   > <span data-ttu-id="dff40-338">Sie können Daten mit dem EDM-Upload-Agenten nur zwei Mal pro Tag in einen bestimmten Datenspeicherort hochladen.</span><span class="sxs-lookup"><span data-stu-id="dff40-338">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

   > [!TIP]
   > <span data-ttu-id="dff40-p134">Um eine Liste der unterstützten Befehlsparameter zu erhalten, führen Sie den Agenten ohne Argumente aus. Beispiel: "EdmUploadAgent.exe".</span><span class="sxs-lookup"><span data-stu-id="dff40-p134">To a get a list out of the supported command parameters, run the agent no arguments. For example 'EdmUploadAgent.exe'.</span></span>

3. <span data-ttu-id="dff40-341">Autorisieren Sie den EDM-Upload-Agenten Öffnen Sie dafür die Eingabeaufforderung (als Administrator), wechseln Sie ins Verzeichnis **C:\EDM\Data** und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dff40-341">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="dff40-342">Melden Sie sich mit Ihrem Microsoft 365-Geschäfts-, Schul- oder Unikonto an, das der Sicherheitsgruppe „EDM_DataUploaders“hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="dff40-342">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="dff40-343">Ihre Mandanteninformationen werden aus dem Benutzerkonto extrahiert, um die Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="dff40-343">Your tenant information is extracted from the user account to make the connection.</span></span>

   <span data-ttu-id="dff40-344">OPTIONAL: Wenn Sie den Assistenten für Exact Data Match Schema und vertraulicher Informationstyp verwendet haben, um Ihre Schema- und Musterdateien zu erstellen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster aus:</span><span class="sxs-lookup"><span data-stu-id="dff40-344">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

   ```dos
   EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
   ```

5. <span data-ttu-id="dff40-345">Um den Hashvorgang durchzuführen die vertraulichen Daten hochzuladen, führen Sie den folgenden Befehl in der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="dff40-345">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

   ```dos
   EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"]
   ```

   <span data-ttu-id="dff40-346">Beispiel: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="dff40-346">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="dff40-347">Das Standardformat für die Datei mit vertraulichen Daten ist durch Trennzeichen getrennte Werte.</span><span class="sxs-lookup"><span data-stu-id="dff40-347">The default format for the sensitive data file is comma-separated values.</span></span> <span data-ttu-id="dff40-348">Sie können eine durch Registerkarten getrennte Datei angeben, indem Sie die Option "{Tab}" mit dem Parameter "/ColumnSeparator" angeben, oder Sie können eine durch Pipe getrennte Datei angeben, indem Sie die Option "|" angeben.</span><span class="sxs-lookup"><span data-stu-id="dff40-348">You can specify a tab-separated file by indicating the "{Tab}" option with the /ColumnSeparator parameter, or you can specify a pipe-separated file by indicating the "|" option.</span></span>
   <span data-ttu-id="dff40-349">Dieser Befehl fügt automatisch einen zufällig generierten Saltwert zum Hash hinzu, um die Sicherheit zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="dff40-349">This command will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="dff40-350">Wenn Sie optional einen eigenen Saltwert verwenden möchten, fügen Sie dem Befehl **/Salt <saltvalue>** hinzu.</span><span class="sxs-lookup"><span data-stu-id="dff40-350">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="dff40-351">Dieser Wert muss 64 Zeichen umfassen und darf nur die Zeichen a-z und die Ziffern 0-9 enthalten.</span><span class="sxs-lookup"><span data-stu-id="dff40-351">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

6. <span data-ttu-id="dff40-352">Überprüfen Sie den Uploadstatus, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="dff40-352">Check the upload status by running this command:</span></span>

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>
   ```

   <span data-ttu-id="dff40-353">Beispiel: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="dff40-353">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

   <span data-ttu-id="dff40-354">Suchen Sie nach dem Status in **ProcessingInProgress**.</span><span class="sxs-lookup"><span data-stu-id="dff40-354">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="dff40-355">Überprüfen Sie den Status alle paar Minuten, bis er sich zu **Abgeschlossen** geändert hat.</span><span class="sxs-lookup"><span data-stu-id="dff40-355">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="dff40-356">Sobald der Status „Abgeschlossen“ angezeigt wird, können Sie die EDM-Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="dff40-356">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="dff40-357">Trennen von Hash und Upload</span><span class="sxs-lookup"><span data-stu-id="dff40-357">Separate Hash and upload</span></span>

<span data-ttu-id="dff40-358">Führen Sie den Hashvorgang auf einem Computer in einer sicheren Umgebung aus.</span><span class="sxs-lookup"><span data-stu-id="dff40-358">Perform the hash on a computer in a secure environment.</span></span>

<span data-ttu-id="dff40-359">OPTIONAL: Wenn Sie den Assistenten für Exact Data Match Schema und vertraulicher Informationstyp verwendet haben, um Ihre Schema- und Musterdateien zu erstellen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster aus:</span><span class="sxs-lookup"><span data-stu-id="dff40-359">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

```dos
EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
````

1. <span data-ttu-id="dff40-360">Führen Sie in den Eingabeaufforderungsfenstern den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dff40-360">Run the following command in Command Prompt windows:</span></span>

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file]
   ```

   <span data-ttu-id="dff40-361">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dff40-361">For example:</span></span>

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml
   ```

   <span data-ttu-id="dff40-362">Dadurch wird eine Hashdatei und eine Saltdatei mit diesen Erweiterungen ausgegeben, wenn Sie die Option **/Salt <saltvalue>** nicht angegeben haben:</span><span class="sxs-lookup"><span data-stu-id="dff40-362">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>

   - <span data-ttu-id="dff40-363">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="dff40-363">.EdmHash</span></span>
   - <span data-ttu-id="dff40-364">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="dff40-364">.EdmSalt</span></span>

2. <span data-ttu-id="dff40-365">Kopieren Sie diese Dateien auf sichere Weise auf den Computer, mit dem Sie Ihre vertraulichen Elemente .csv oder TSV-Datei (PatientRecords) in Ihren Mandanten hochladen.</span><span class="sxs-lookup"><span data-stu-id="dff40-365">Copy these files in a secure fashion to the computer you will use to upload your sensitive items .csv or .tsv file (PatientRecords) to your tenant.</span></span>

   <span data-ttu-id="dff40-366">Führen Sie zum Hochladen gehashter Daten den folgenden Befehl in der Windows-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="dff40-366">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>
   ```

   <span data-ttu-id="dff40-367">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dff40-367">For example:</span></span>

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**
   ```

   <span data-ttu-id="dff40-368">Führen Sie zur Überprüfung, ob Ihre vertraulichen Daten hochgeladen wurden, den folgenden Befehl in der Windows-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="dff40-368">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>

   ```dos
   EdmUploadAgent.exe /GetDataStore
   ```

   <span data-ttu-id="dff40-369">Sie sehen eine Liste der Datenspeicher und wann sie zuletzt aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="dff40-369">You'll see a list of data stores and when they were last updated.</span></span>

   <span data-ttu-id="dff40-370">Wenn Sie alle Daten sehen möchten, die in einen bestimmten Store hochgeladen wurden, führen Sie den folgenden Befehl in einer Windows-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="dff40-370">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>
   ```

   <span data-ttu-id="dff40-371">Fahren Sie mit dem Einrichten des Prozesses und des Zeitplans für [Aktualisieren der Datenbank für vertrauliche Informationen](#refreshing-your-sensitive-information-database) fort.</span><span class="sxs-lookup"><span data-stu-id="dff40-371">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="dff40-372">Sie können nun die EDM-basierte Klassifikation mit Ihren Microsoft Cloud Services verwenden.</span><span class="sxs-lookup"><span data-stu-id="dff40-372">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="dff40-373">Sie können beispielsweise [eine DLP-Richtlinie mithilfe der EDM-basierten Klassifizierung](#to-create-a-dlp-policy-with-edm) einrichten.</span><span class="sxs-lookup"><span data-stu-id="dff40-373">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="dff40-374">Aktualisieren der Datenbank für vertrauliche Informationen</span><span class="sxs-lookup"><span data-stu-id="dff40-374">Refreshing your sensitive information database</span></span>

<span data-ttu-id="dff40-375">Sie können Ihre Datenbank für vertrauliche Informationen täglich aktualisieren, und das EDM-Upload-Tool kann die vertraulichen Daten neu indizieren und dann die indizierten Daten erneut hochladen.</span><span class="sxs-lookup"><span data-stu-id="dff40-375">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="dff40-376">Ermitteln Sie den Vorgang und die Häufigkeit (täglich oder wöchentlich) zum Aktualisieren der Datenbank mit vertraulichen Informationen.</span><span class="sxs-lookup"><span data-stu-id="dff40-376">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="dff40-377">Exportieren Sie die vertraulichen Daten erneut in eine App, z. B. Microsoft Excel, und speichern Sie die Datei im .csv- oder TSV-Format.</span><span class="sxs-lookup"><span data-stu-id="dff40-377">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv or .tsv format.</span></span> <span data-ttu-id="dff40-378">Behalten Sie den Dateinamen und den Speicherort bei, den Sie beim Ausführen der unter [Hashen und Hochladen vertraulicher Daten](#part-2-hash-and-upload-the-sensitive-data) beschriebenen Schritte verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="dff40-378">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="dff40-379">Wenn keine Änderungen an der Struktur (Feldnamen) der .csv- oder TSV-Datei vorgenommen werden, müssen Sie beim Aktualisieren der Daten keine Änderungen an der Datenbankschemadatei vornehmen.</span><span class="sxs-lookup"><span data-stu-id="dff40-379">If there are no changes to the structure (field names) of the .csv or .tsv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="dff40-380">Wenn Sie jedoch Änderungen vornehmen müssen, stellen Sie sicher, dass Sie das Datenbankschema und Ihr Regelpaket entsprechend bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="dff40-380">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="dff40-381">Verwenden Sie die [Aufgabenplanung](/windows/desktop/TaskSchd/task-scheduler-start-page), um die Schritte 2 und 3 im Verfahren [Hashen und Hochladen vertraulicher Daten](#part-2-hash-and-upload-the-sensitive-data) zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="dff40-381">Use [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="dff40-382">Sie können Aufgaben mithilfe verschiedener Methoden planen:</span><span class="sxs-lookup"><span data-stu-id="dff40-382">You can schedule tasks using several methods:</span></span>

   |<span data-ttu-id="dff40-383">Methode</span><span class="sxs-lookup"><span data-stu-id="dff40-383">Method</span></span>|<span data-ttu-id="dff40-384">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="dff40-384">What to do</span></span>|
   |---|---|
   |<span data-ttu-id="dff40-385">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dff40-385">Windows PowerShell</span></span>|<span data-ttu-id="dff40-386">Siehe Dokumentation [Aufgabenplanung](/powershell/module/scheduledtasks/) und [Beispiel PowerShell-Skript](#example-powershell-script-for-task-scheduler) in diesem Artikel</span><span class="sxs-lookup"><span data-stu-id="dff40-386">See the [ScheduledTasks](/powershell/module/scheduledtasks/) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span>|
   |<span data-ttu-id="dff40-387">Aufgabenplaner-API</span><span class="sxs-lookup"><span data-stu-id="dff40-387">Task Scheduler API</span></span>|<span data-ttu-id="dff40-388">Siehe Dokumentation [Aufgabenplaner](/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="dff40-388">See the [Task Scheduler](/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>|
   |<span data-ttu-id="dff40-389">Windows-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="dff40-389">Windows user interface</span></span>|<span data-ttu-id="dff40-390">Klicken Sie in Windows auf **Start** und geben Sie „Aufgabenplanung“ ein.</span><span class="sxs-lookup"><span data-stu-id="dff40-390">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="dff40-391">Klicken Sie dann in der Ergebnisliste mit der rechten Maustaste auf **Aufgabenplaner** und wählen Sie **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="dff40-391">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>|

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="dff40-392">„PowerShell-Beispielskript“ für „Aufgabenplanung“</span><span class="sxs-lookup"><span data-stu-id="dff40-392">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="dff40-393">Dieser Abschnitt enthält ein Beispiel für ein PowerShell-Skript, mit dem Sie Ihre Aufgaben zum Hashen von Daten und Hochladen gehashter Daten planen können:</span><span class="sxs-lookup"><span data-stu-id="dff40-393">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="dff40-394">So planen Sie das Hashen und Hochladen in einem kombinierten Schritt</span><span class="sxs-lookup"><span data-stu-id="dff40-394">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="dff40-395">So planen Sie das Hashen und Hochladen als separate Schritte</span><span class="sxs-lookup"><span data-stu-id="dff40-395">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="dff40-396">Teil 3: Verwenden der EDM-basierten Klassifizierung mit Ihren Microsoft Cloud Services</span><span class="sxs-lookup"><span data-stu-id="dff40-396">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="dff40-397">Diese Speicherorte sind unterstützte Typen vertraulicher EDM-Informationen:</span><span class="sxs-lookup"><span data-stu-id="dff40-397">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="dff40-398">DLP für Exchange Online (E-Mail)</span><span class="sxs-lookup"><span data-stu-id="dff40-398">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="dff40-399">OneDrive for Business (Dateien)</span><span class="sxs-lookup"><span data-stu-id="dff40-399">OneDrive for Business (files)</span></span>
- <span data-ttu-id="dff40-400">Microsoft Teams (Unterhaltungen)</span><span class="sxs-lookup"><span data-stu-id="dff40-400">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="dff40-401">DLP für SharePoint (Dateien)</span><span class="sxs-lookup"><span data-stu-id="dff40-401">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="dff40-402">DLP-Richtlinien für Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="dff40-402">Microsoft Cloud App Security DLP policies</span></span>
- <span data-ttu-id="dff40-403">Serverseitige Richtlinien für automatische Bezeichnungen – für kommerzielle Cloudkunden und Government Cloud-Kunden verfügbar</span><span class="sxs-lookup"><span data-stu-id="dff40-403">Server-side auto-labeling policies - available for commercial cloud customers and government cloud customers</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="dff40-404">Erstellen einer DLP-Richtlinie mit EDM</span><span class="sxs-lookup"><span data-stu-id="dff40-404">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="dff40-405">Gehen Sie zum Security & Compliance Center, indem Sie den entsprechenden [Link für Ihr Abonnement](#portal-links-for-your-subscription) verwenden.</span><span class="sxs-lookup"><span data-stu-id="dff40-405">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="dff40-406">Wählen Sie **Verhinderung von Datenverlust** \> **Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="dff40-406">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="dff40-407">Wählen Sie **Richtlinie erstellen** \> **Benutzerdefiniert** \> **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dff40-407">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="dff40-408">Geben Sie auf der Registerkarte **Richtlinie benennen** einen Namen und eine Beschreibung ein und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dff40-408">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="dff40-409">Wählen Sie auf der Registerkarte **Speicherorte auswählen** **Bestimmte Speicherorte auswählen** und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dff40-409">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="dff40-410">Wählen Sie in der Spalte **Status** die Option **Exchange-E-Mail, OneDrive-Konten, Teams-Chat und Kanalnachricht** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="dff40-410">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message**, and then choose **Next**.</span></span>

7. <span data-ttu-id="dff40-411">Wählen Sie auf der Registerkarte **Richtlinieneinstellungen** **Erweiterte Einstellungen verwenden** und dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dff40-411">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="dff40-412">Wählen Sie **+ Neue Regel** aus.</span><span class="sxs-lookup"><span data-stu-id="dff40-412">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="dff40-413">Geben Sie im Abschnitt **Name** einen Namen und eine Beschreibung für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="dff40-413">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="dff40-414">Wählen Sie im Abschnitt **Bedingungen** in der Liste **+ Bedingung hinzufügen** **Inhalt enthält vertraulichen Typ**.</span><span class="sxs-lookup"><span data-stu-id="dff40-414">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![Inhalt enthält sensible Informationstypen](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="dff40-416">Suchen Sie den vertraulichen Informationstyp, den Sie beim Einrichten Ihres Regelpakets erstellt haben, und wählen Sie dann **+ Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dff40-416">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>
    <span data-ttu-id="dff40-417">Wählen Sie dann **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="dff40-417">Then choose **Done**.</span></span>

12. <span data-ttu-id="dff40-418">Wählen Sie Optionen für die Regel aus, wie z. B. **Benutzerbenachrichtigungen**, **Benutzeraußerkraftsetzungen**, **Schadensberichte** usw., und wählen Sie dann **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dff40-418">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="dff40-419">Überprüfen Sie auf der Registerkarte die **Richtlinieneinstellungen**, überprüfen Sie Ihre Regeln und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dff40-419">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="dff40-420">Geben Sie an, ob Sie die Richtlinie sofort aktivieren, sie testen oder deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="dff40-420">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="dff40-421">Wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="dff40-421">Then choose **Next**.</span></span>

15. <span data-ttu-id="dff40-422">Überprüfen Sie auf der Registerkarte **Überprüfen Sie Ihre Einstellungen** Ihre Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="dff40-422">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="dff40-423">Nehmen Sie alle erforderlichen Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="dff40-423">Make any needed changes.</span></span> <span data-ttu-id="dff40-424">Wenn Sie fertig sind, wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="dff40-424">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="dff40-425">Es kann ungefähr eine Stunde dauern, bis Ihre neue DLP-Richtlinie im Rechenzentrum erscheint.</span><span class="sxs-lookup"><span data-stu-id="dff40-425">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dff40-426">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="dff40-426">Related articles</span></span>

- [<span data-ttu-id="dff40-427">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="dff40-427">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="dff40-428">Informationen zu Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="dff40-428">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="dff40-429">Informationen zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="dff40-429">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="dff40-430">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dff40-430">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="dff40-431">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="dff40-431">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)
- [<span data-ttu-id="dff40-432">Ändern Sie das Schema für die genaue Datenübereinstimmung, um eine konfigurierbare Übereinstimmung zu verwenden</span><span class="sxs-lookup"><span data-stu-id="dff40-432">Modify Exact Data Match schema to use configurable match</span></span>](sit-modify-edm-schema-configurable-match.md)
