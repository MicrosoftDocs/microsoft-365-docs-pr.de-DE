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
ms.openlocfilehash: 699cea6aec6f11462aed0c08db98ca4620df519a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686559"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="c5f32-103">Erstellen von benutzerdefinierten vertraulichen Informationstypen mit genauer Datenübereinstimmungsklassifizierung</span><span class="sxs-lookup"><span data-stu-id="c5f32-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="c5f32-104">[Benutzerdefinierte vertrauliche Informationstypen](custom-sensitive-info-types.md) werden verwendet, um zu verhindern, dass vertrauliche Informationen versehentlich oder in unangemessener Weise freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c5f32-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="c5f32-105">Als Administrator können Sie das Security & Compliance Center oder PowerShell verwenden, um einen benutzerdefinierten Typ sensibler Informationen auf der Grundlage von Mustern, Beweisen (Schlüsselwörter wie  *Mitarbeitende*, *Ausweis*, *ID* usw.), Zeichennähe (wie nah Beweise an Zeichen in einem bestimmten Muster liegen) und Vertrauensstufen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="c5f32-105">As an administrator, you can use the Security & Compliance Center or PowerShell to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="c5f32-106">Solche benutzerdefinierten vertraulichen Informationstypen erfüllen die geschäftlichen Anforderungen vieler Organisationen.</span><span class="sxs-lookup"><span data-stu-id="c5f32-106">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="c5f32-107">Was aber, wenn Sie einen benutzerdefinierten vertraulichen Informationstyp nutzen möchten, der genaue Datenwerte verwendet, anstatt nur mit generischen Mustern übereinzustimmen?</span><span class="sxs-lookup"><span data-stu-id="c5f32-107">But what if you wanted a custom sensitive information type that uses exact data values, instead of matching only with generic patterns?</span></span> <span data-ttu-id="c5f32-108">Mit einer EDM-basierten Klassifizierung (genaue Datenübereinstimmung) können Sie einen benutzerdefinierten Informationstyp mit den folgenden Merkmalen erstellen:</span><span class="sxs-lookup"><span data-stu-id="c5f32-108">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="c5f32-109">dynamisch und aktualisierbar;</span><span class="sxs-lookup"><span data-stu-id="c5f32-109">be dynamic and refreshable;</span></span>
- <span data-ttu-id="c5f32-110">höhere Skalierbarkeit;</span><span class="sxs-lookup"><span data-stu-id="c5f32-110">be more scalable;</span></span>
- <span data-ttu-id="c5f32-111">weniger falsch positive Ergebnisse;</span><span class="sxs-lookup"><span data-stu-id="c5f32-111">result in fewer false-positives;</span></span>
- <span data-ttu-id="c5f32-112">Arbeiten mit strukturierten vertraulichen Daten;</span><span class="sxs-lookup"><span data-stu-id="c5f32-112">work with structured sensitive data;</span></span>
- <span data-ttu-id="c5f32-113">vertrauliche Informationen sicherer behandeln; </span><span class="sxs-lookup"><span data-stu-id="c5f32-113">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="c5f32-114">Verwendbarkeit mit mehreren Microsoft Cloud Services.</span><span class="sxs-lookup"><span data-stu-id="c5f32-114">be used with several Microsoft cloud services.</span></span>

![EDM-basierte Klassifikation](../media/EDMClassification.png)

<span data-ttu-id="c5f32-116">Die EDM-basierte Klassifikation ermöglicht es Ihnen, benutzerdefinierte vertrauliche Informationstypen zu erstellen, die sich auf genaue Werte in einer Datenbank mit vertraulichen Informationen beziehen.</span><span class="sxs-lookup"><span data-stu-id="c5f32-116">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="c5f32-117">Die Datenbank kann täglich oder wöchentlich aktualisiert werden und bis zu 100 Millionen Datenzeilen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c5f32-117">The database can be refreshed daily or weekly, and it can contain up to 100 million rows of data.</span></span> <span data-ttu-id="c5f32-118">Mitarbeiter, Patienten oder Kunden kommen und gehen und Datensätze ändern sich, aber Ihre benutzerdefinierten vertraulichen Informationstypen bleiben aktuell und anwendbar.</span><span class="sxs-lookup"><span data-stu-id="c5f32-118">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="c5f32-119">Darüber hinaus können Sie EDM-basierte Klassifikation mit Richtlinien verwenden, z. B. [Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md) (Data Loss Prevention, DLP) oder [Microsoft Cloud App Security-Dateirichtlinien](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="c5f32-119">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="c5f32-120">Microsoft 365 Information Protection unterstützt jetzt in der Vorschau Doppelbyte-Zeichensatz-Sprachen für:</span><span class="sxs-lookup"><span data-stu-id="c5f32-120">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="c5f32-121">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="c5f32-121">Chinese (simplified)</span></span>
> - <span data-ttu-id="c5f32-122">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="c5f32-122">Chinese (traditional)</span></span>
> - <span data-ttu-id="c5f32-123">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="c5f32-123">Korean</span></span>
> - <span data-ttu-id="c5f32-124">Japanisch</span><span class="sxs-lookup"><span data-stu-id="c5f32-124">Japanese</span></span>
> 
><span data-ttu-id="c5f32-125">Diese Vorschau ist nur in der kommerziellen Cloud verfügbar, und die Einführung ist beschränkt auf:</span><span class="sxs-lookup"><span data-stu-id="c5f32-125">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="c5f32-126">Japan</span><span class="sxs-lookup"><span data-stu-id="c5f32-126">Japan</span></span>
> - <span data-ttu-id="c5f32-127">Korea</span><span class="sxs-lookup"><span data-stu-id="c5f32-127">Korea</span></span>
> - <span data-ttu-id="c5f32-128">China</span><span class="sxs-lookup"><span data-stu-id="c5f32-128">China</span></span>
> - <span data-ttu-id="c5f32-129">Hongkong (SAR)</span><span class="sxs-lookup"><span data-stu-id="c5f32-129">Hong Kong</span></span>
> - <span data-ttu-id="c5f32-130">Macau (SAR)</span><span class="sxs-lookup"><span data-stu-id="c5f32-130">Macau</span></span>
> - <span data-ttu-id="c5f32-131">Taiwan</span><span class="sxs-lookup"><span data-stu-id="c5f32-131">Taiwan</span></span>
>
><span data-ttu-id="c5f32-132">Diese Unterstützung ist für vertrauliche Informationstypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c5f32-132">This support is available for sensitive information types.</span></span> <span data-ttu-id="c5f32-133">Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="c5f32-133">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="c5f32-134">Erforderliche Lizenzen und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c5f32-134">Required licenses and permissions</span></span>

<span data-ttu-id="c5f32-135">Sie müssen ein globaler, Compliance- oder Exchange Online-Administrator sein, um die in diesem Artikel beschriebenen Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c5f32-135">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="c5f32-136">Weitere Informationen über DLP-Berechtigungen finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="c5f32-136">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="c5f32-137">Die EDM-basierte Klassifizierung ist in diesen Abonnements enthalten.</span><span class="sxs-lookup"><span data-stu-id="c5f32-137">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="c5f32-138">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="c5f32-138">Office 365 E5</span></span>
- <span data-ttu-id="c5f32-139">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c5f32-139">Microsoft 365 E5</span></span>
- <span data-ttu-id="c5f32-140">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="c5f32-140">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="c5f32-141">Microsoft E5/ A5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="c5f32-141">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="c5f32-142">Portal Links für Ihr Abonnement</span><span class="sxs-lookup"><span data-stu-id="c5f32-142">Portal links for your subscription</span></span>


|<span data-ttu-id="c5f32-143">Portal</span><span class="sxs-lookup"><span data-stu-id="c5f32-143">Portal</span></span>  |<span data-ttu-id="c5f32-144">Weltweit/GCC</span><span class="sxs-lookup"><span data-stu-id="c5f32-144">World Wide/GCC</span></span>  |<span data-ttu-id="c5f32-145">GCC – hoch</span><span class="sxs-lookup"><span data-stu-id="c5f32-145">GCC-High</span></span>  |<span data-ttu-id="c5f32-146">DOD</span><span class="sxs-lookup"><span data-stu-id="c5f32-146">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="c5f32-147">Office SCC</span><span class="sxs-lookup"><span data-stu-id="c5f32-147">Office SCC</span></span>     |  <span data-ttu-id="c5f32-148">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="c5f32-148">protection.office.com</span></span>       |<span data-ttu-id="c5f32-149">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="c5f32-149">scc.office365.us</span></span>         |<span data-ttu-id="c5f32-150">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="c5f32-150">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="c5f32-151">Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="c5f32-151">Microsoft 365 Security center</span></span>     |<span data-ttu-id="c5f32-152">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c5f32-152">security.microsoft.com</span></span>         |<span data-ttu-id="c5f32-153">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="c5f32-153">security.microsoft.us</span></span>         |<span data-ttu-id="c5f32-154">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="c5f32-154">security.apps.mil</span></span>|
|<span data-ttu-id="c5f32-155">Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="c5f32-155">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="c5f32-156">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c5f32-156">compliance.microsoft.com</span></span>         |<span data-ttu-id="c5f32-157">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="c5f32-157">compliance.microsoft.us</span></span>         |<span data-ttu-id="c5f32-158">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="c5f32-158">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="c5f32-159">Der Workflow auf einen Blick</span><span class="sxs-lookup"><span data-stu-id="c5f32-159">The work flow at a glance</span></span>

|<span data-ttu-id="c5f32-160">Phase</span><span class="sxs-lookup"><span data-stu-id="c5f32-160">Phase</span></span>  |<span data-ttu-id="c5f32-161">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c5f32-161">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="c5f32-162">Teil 1: Einrichten der EDM-basierten Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="c5f32-162">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="c5f32-163">(je nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="c5f32-163">(As needed)</span></span><br/><span data-ttu-id="c5f32-164">- [Bearbeiten des Datenbankschemas](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="c5f32-164">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="c5f32-165">- [Entfernen des Schemas](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="c5f32-165">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="c5f32-166">– Lesezugriff auf vertrauliche Daten</span><span class="sxs-lookup"><span data-stu-id="c5f32-166">- Read access to the sensitive data</span></span><br/><span data-ttu-id="c5f32-167">– Datenbankschema im XML-Format (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="c5f32-167">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="c5f32-168">– Regelpaket im XML-Format (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="c5f32-168">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="c5f32-169">– Administratorberechtigungen für das Security & Compliance Center (mithilfe von PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c5f32-169">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="c5f32-170">Teil 2: Hashen und Hochladen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="c5f32-170">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="c5f32-171">(je nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="c5f32-171">(As needed)</span></span><br/>[<span data-ttu-id="c5f32-172">Aktualisieren der Daten</span><span class="sxs-lookup"><span data-stu-id="c5f32-172">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="c5f32-173">– Benutzerdefinierte Sicherheitsgruppe und Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="c5f32-173">- Custom security group and user account</span></span><br/><span data-ttu-id="c5f32-174">– Lokaler Administratorzugriff auf den Computer mit dem EDM-Upload-Agent</span><span class="sxs-lookup"><span data-stu-id="c5f32-174">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="c5f32-175">– Lesezugriff auf vertrauliche Daten</span><span class="sxs-lookup"><span data-stu-id="c5f32-175">- Read access to the sensitive data</span></span><br/><span data-ttu-id="c5f32-176">– Prozess und Zeitplan für die Datenaktualisierung</span><span class="sxs-lookup"><span data-stu-id="c5f32-176">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="c5f32-177">Teil 3: Verwenden der EDM-basierten Klassifizierung mit Ihren Microsoft Cloud Services</span><span class="sxs-lookup"><span data-stu-id="c5f32-177">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="c5f32-178">– Microsoft 365-Abonnement mit DLP</span><span class="sxs-lookup"><span data-stu-id="c5f32-178">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="c5f32-179">– EDM-basiertes Klassifizierungsfeature aktiviert</span><span class="sxs-lookup"><span data-stu-id="c5f32-179">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="c5f32-180">Teil 1: Einrichten der EDM-basierten Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="c5f32-180">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="c5f32-181">Beim Einrichten und Konfigurieren der EDM-basierten Klassifizierung werden vertrauliche Daten im CSV-Format gespeichert, ein Schema für Ihre Datenbank mit vertraulichen Informationen definiert und ein Regelpaket erstellt. Anschließend werden das Schema und das Regelpaket hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="c5f32-181">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="c5f32-182">Definieren des Schemas für Ihre Datenbank mit vertraulichen Informationen</span><span class="sxs-lookup"><span data-stu-id="c5f32-182">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="c5f32-183">Identifizieren Sie die vertraulichen Informationen, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c5f32-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="c5f32-184">Exportieren Sie die Daten in eine App, wie z. B. Microsoft Excel, und speichern Sie die Datei im CSV-Format.</span><span class="sxs-lookup"><span data-stu-id="c5f32-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="c5f32-185">Die Datendatei kann maximal Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="c5f32-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="c5f32-186">bis zu 100 Millionen Zeilen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="c5f32-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="c5f32-187">bis zu 32 Spalten (Felder) pro Datenquelle</span><span class="sxs-lookup"><span data-stu-id="c5f32-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="c5f32-188">bis zu 5 als durchsuchbar markierte Spalten (Felder)</span><span class="sxs-lookup"><span data-stu-id="c5f32-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="c5f32-189">Strukturieren Sie die vertraulichen Daten in der CSV-Datei so, dass die erste Zeile die Namen der für die EDM-basierte Klassifizierung verwendeten Felder enthält.</span><span class="sxs-lookup"><span data-stu-id="c5f32-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="c5f32-190">Möglicherweise gibt es in Ihrer CSV-Datei Feldnamen, wie z. B. "SSN", "Geburtsdatum", "Vorname", "Nachname" usw.</span><span class="sxs-lookup"><span data-stu-id="c5f32-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="c5f32-191">Beachten Sie, dass Spaltenüberschriften keine Leerzeichen oder Unterstriche im Namen enthalten dürfen.</span><span class="sxs-lookup"><span data-stu-id="c5f32-191">Please note that column headers can't include spaces or underscores in their names.</span></span> <span data-ttu-id="c5f32-192">Im Beispiel nennen wir unsere CSV-Datei *PatientRecords.csv*, und die Spalten beinhalten *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*und mehr.</span><span class="sxs-lookup"><span data-stu-id="c5f32-192">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="c5f32-193">Definieren Sie das Schema für die Datenbank mit vertraulichen Informationen im XML-Format (ähnlich wie in unserem Beispiel unten).</span><span class="sxs-lookup"><span data-stu-id="c5f32-193">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="c5f32-194">Nennen Sie diese Schemadatei **edm.xml**, und konfigurieren Sie sie so, dass es für jede Spalte in der Datenbank eine Zeile mit der folgenden Syntax gibt:</span><span class="sxs-lookup"><span data-stu-id="c5f32-194">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="c5f32-195">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="c5f32-195">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="c5f32-196">Verwenden Sie Spaltennamen für *Field name*-Werte.</span><span class="sxs-lookup"><span data-stu-id="c5f32-196">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="c5f32-197">Verwenden Sie *searchable="true* für maximal 5 Felder, die durchsuchbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="c5f32-197">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="c5f32-198">Sie müssen mindestens ein Feld als durchsuchbar festlegen.</span><span class="sxs-lookup"><span data-stu-id="c5f32-198">You must designate a minimum of one field as searchable.</span></span>

      <span data-ttu-id="c5f32-199">Im folgenden Beispiel definiert die XML-Datei das Schema für eine Datenbank mit Patientendatensätzen, wobei fünf Felder als durchsuchbar angegeben werden: *PatientID*, *MRN*, *SSN*, *Phone* und *DOB*.</span><span class="sxs-lookup"><span data-stu-id="c5f32-199">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="c5f32-200">(Sie können das Beispiel kopieren, ändern und verwenden.)</span><span class="sxs-lookup"><span data-stu-id="c5f32-200">(You can copy, modify, and use our example.)</span></span>

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

4. <span data-ttu-id="c5f32-201">Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="c5f32-201">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="c5f32-202">Führen Sie die folgenden Cmdlets nacheinander aus, um das Datenbankschema hochzuladen:</span><span class="sxs-lookup"><span data-stu-id="c5f32-202">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="c5f32-203">Sie werden zu folgenden Bestätigungen aufgefordert:</span><span class="sxs-lookup"><span data-stu-id="c5f32-203">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="c5f32-204">Bestätigen</span><span class="sxs-lookup"><span data-stu-id="c5f32-204">Confirm</span></span>
      >
      > <span data-ttu-id="c5f32-205">Möchten Sie diese Aktion wirklich ausführen?</span><span class="sxs-lookup"><span data-stu-id="c5f32-205">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="c5f32-206">Das neue EDM-Schema für den Datenspeicher „patientrecords“ wird importiert.</span><span class="sxs-lookup"><span data-stu-id="c5f32-206">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="c5f32-207">\[J\] Ja \[A\] Ja für alle \[N\] Nein \[L\] Nein für alle \[?\] Hilfe (Standard ist "J"):</span><span class="sxs-lookup"><span data-stu-id="c5f32-207">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="c5f32-208">Wenn Sie möchten, dass Ihre Änderungen ohne Bestätigung durchgeführt werden, verwenden Sie in Schritt 5 stattdessen das folgende Cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="c5f32-208">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="c5f32-209">Es kann zwischen 10–60 Minuten dauern, bis das EDMSchema durch Ergänzungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="c5f32-209">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="c5f32-210">Das Update muss abgeschlossen sein, bevor Sie Schritte ausführen, die die Zusätze verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5f32-210">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="c5f32-211">Nachdem das Schema für Ihre Datenbank mit vertraulichen Informationen definiert wurde, besteht der nächste Schritt darin, ein Regelpaket einzurichten.</span><span class="sxs-lookup"><span data-stu-id="c5f32-211">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="c5f32-212">Fahren Sie mit dem Abschnitt [Einrichten eines Regelpakets](#set-up-a-rule-package) fort.</span><span class="sxs-lookup"><span data-stu-id="c5f32-212">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="c5f32-213">Bearbeiten des Schemas für die EDM-basierte Klassifikation</span><span class="sxs-lookup"><span data-stu-id="c5f32-213">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="c5f32-214">Wenn Sie Änderungen an Ihrer **edm.xml**-Datei vornehmen und z. B. ändern möchten, welche Felder für die EDM-basierte Klassifikation verwendet werden, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c5f32-214">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="c5f32-215">Bearbeiten Sie Ihre **edm.xml**-Datei (die Datei, die im Abschnitt [Definieren des Schemas](#define-the-schema-for-your-database-of-sensitive-information) in diesem Artikel behandelt wird).</span><span class="sxs-lookup"><span data-stu-id="c5f32-215">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="c5f32-216">Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="c5f32-216">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="c5f32-217">Führen Sie die folgenden Cmdlets nacheinander aus, um Ihr Datenbankschema zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="c5f32-217">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="c5f32-218">Sie werden zu folgenden Bestätigungen aufgefordert:</span><span class="sxs-lookup"><span data-stu-id="c5f32-218">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="c5f32-219">Bestätigen</span><span class="sxs-lookup"><span data-stu-id="c5f32-219">Confirm</span></span>
      >
      > <span data-ttu-id="c5f32-220">Möchten Sie diese Aktion wirklich ausführen?</span><span class="sxs-lookup"><span data-stu-id="c5f32-220">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="c5f32-221">Das EDM-Schema für den Datenspeicher „patientrecords“ wird aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c5f32-221">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="c5f32-222">\[J\] Ja \[A\] Ja für alle \[N\] Nein \[L\] Nein für alle \[?\] Hilfe (Standard ist "J"):</span><span class="sxs-lookup"><span data-stu-id="c5f32-222">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="c5f32-223">Wenn Sie möchten, dass Ihre Änderungen ohne Bestätigung durchgeführt werden, verwenden Sie in Schritt 3 stattdessen das folgende Cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="c5f32-223">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="c5f32-224">Es kann zwischen 10–60 Minuten dauern, bis das EDMSchema durch Ergänzungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="c5f32-224">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="c5f32-225">Das Update muss abgeschlossen sein, bevor Sie Schritte ausführen, die die Zusätze verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5f32-225">The update must complete before you execute steps that use the additions.</span></span>

## <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="c5f32-226">Entfernen des Schemas für die EDM-basierte Klassifikation</span><span class="sxs-lookup"><span data-stu-id="c5f32-226">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="c5f32-227">(Nach Bedarf) Wenn Sie das Schema entfernen möchten, das Sie für die EDM-basierte Klassifizierung verwenden, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="c5f32-227">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="c5f32-228">Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="c5f32-228">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="c5f32-229">Führen Sie die folgenden PowerShell-Cmdlets aus, und ersetzen Sie dabei den Datenspeichernamen "patientrecords" durch den Namen, den Sie entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="c5f32-229">Run the following PowerShell cmdlets, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="c5f32-230">Sie werden zu folgenden Bestätigungen aufgefordert:</span><span class="sxs-lookup"><span data-stu-id="c5f32-230">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="c5f32-231">Bestätigen</span><span class="sxs-lookup"><span data-stu-id="c5f32-231">Confirm</span></span>
      >
      > <span data-ttu-id="c5f32-232">Möchten Sie diese Aktion wirklich ausführen?</span><span class="sxs-lookup"><span data-stu-id="c5f32-232">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="c5f32-233">Das EDM-Schema für den Datenspeicher „patientrecords“ wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="c5f32-233">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="c5f32-234">\[J\] Ja \[A\] Ja für alle \[N\] Nein \[L\] Nein für alle \[?\] Hilfe (Standard ist "J"):</span><span class="sxs-lookup"><span data-stu-id="c5f32-234">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="c5f32-235">Wenn Sie möchten, dass Ihre Änderungen ohne Bestätigung durchgeführt werden, verwenden Sie in Schritt 2 stattdessen das folgende Cmdlet: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="c5f32-235">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="c5f32-236">Einrichten eines Regelpakets</span><span class="sxs-lookup"><span data-stu-id="c5f32-236">Set up a rule package</span></span>

1. <span data-ttu-id="c5f32-237">Erstellen Sie ein Regelpaket im XML-Format (mit Unicode-Codierung), ähnlich wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c5f32-237">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="c5f32-238">(Sie können das Beispiel kopieren, ändern und verwenden.)</span><span class="sxs-lookup"><span data-stu-id="c5f32-238">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="c5f32-239">Vergewissern Sie sich beim Einrichten des Regelpakets, dass Sie die CSV-Datei und die **edm.xml**-Datei korrekt referenzieren.</span><span class="sxs-lookup"><span data-stu-id="c5f32-239">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="c5f32-240">Sie können das Beispiel kopieren, ändern und verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5f32-240">You can copy, modify, and use our example.</span></span> <span data-ttu-id="c5f32-241">In dieser XML-Beispieldatei müssen die folgenden Felder so angepasst werden, dass Sie Ihren vertraulichen EDM-Typ erstellen:</span><span class="sxs-lookup"><span data-stu-id="c5f32-241">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="c5f32-242">**RulePack id und ExactMatch id**: Verwenden Sie [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6), um eine GUID zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c5f32-242">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="c5f32-243">**Datenspeicher**: Dieses Feld gibt den zu verwendenden EDM-Nachschlage-Datenspeicher an.</span><span class="sxs-lookup"><span data-stu-id="c5f32-243">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="c5f32-244">Sie geben einen Datenquellennamen eines konfigurierten EDM-Schemas an.</span><span class="sxs-lookup"><span data-stu-id="c5f32-244">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="c5f32-245">**idMatch**: Dieses Feld verweist auf das primäre Element für EDM.</span><span class="sxs-lookup"><span data-stu-id="c5f32-245">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="c5f32-246">Stimmt überein mit: gibt das Feld an, das in der exakten Suche verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5f32-246">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="c5f32-247">Sie geben den Namen eines durchsuchbaren Felds im EDM-Schema für den Datenspeicher an.</span><span class="sxs-lookup"><span data-stu-id="c5f32-247">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="c5f32-248">Klassifizierung: Dieses Feld gibt die Übereinstimmung für den vertraulichen Typ an, der EDM-Nachschlagevorgänge auslöst.</span><span class="sxs-lookup"><span data-stu-id="c5f32-248">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="c5f32-249">Sie können den Namen oder die GUID einer vorhandenen integrierten oder benutzerdefinierten Klassifizierung angeben.</span><span class="sxs-lookup"><span data-stu-id="c5f32-249">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="c5f32-250">**Übereinstimmung:** Dieses Feld verweist auf zusätzliche Nachweise, die sich in der Nähe von "idMatch" befinden.</span><span class="sxs-lookup"><span data-stu-id="c5f32-250">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="c5f32-251">Stimmt überein mit: Sie geben einen Feldnamen im EDM-Schema für den Datenspeicher an.</span><span class="sxs-lookup"><span data-stu-id="c5f32-251">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="c5f32-252">**Ressource:** In diesem Abschnitt werden der Name und die Beschreibung für den vertraulichen Typ in mehreren Sprachversionen angegeben.</span><span class="sxs-lookup"><span data-stu-id="c5f32-252">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="c5f32-253">idRef: Sie geben die GUID für die ExactMatch-ID an.</span><span class="sxs-lookup"><span data-stu-id="c5f32-253">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="c5f32-254">Name und Beschreibungen: nach Bedarf anpassen.</span><span class="sxs-lookup"><span data-stu-id="c5f32-254">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="c5f32-255">Laden Sie das Regelpaket hoch, indem Sie nacheinander die folgenden PowerShell-Cmdlets ausführen:</span><span class="sxs-lookup"><span data-stu-id="c5f32-255">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="c5f32-256">Sie haben die EDM-basierte Klassifizierung nun eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="c5f32-256">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="c5f32-257">Der nächste Schritt ist das Hashen vertraulicher Daten, gefolgt vom Hochladen der Hashes für die Indizierung.</span><span class="sxs-lookup"><span data-stu-id="c5f32-257">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="c5f32-258">Wie Sie im vorherigen Verfahren erfahren haben, wurden im PatientRecords-Schema fünf Felder als durchsuchbar definiert: *PatientID*, *MRN*, *SSN*, *Phone* und *DOB*.</span><span class="sxs-lookup"><span data-stu-id="c5f32-258">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="c5f32-259">Unser Beispiel für ein Regelpaket enthält diese Felder und verweist auf die Datenbankschemadatei (**edm.xml**), mit einem  *ExactMatch* -Element pro durchsuchbarem Feld.</span><span class="sxs-lookup"><span data-stu-id="c5f32-259">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="c5f32-260">Sehen Sie sich das folgende ExactMatch-Element an:</span><span class="sxs-lookup"><span data-stu-id="c5f32-260">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="c5f32-261">Beachten Sie in diesem Beispiel Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c5f32-261">In this example, note the following:</span></span>

- <span data-ttu-id="c5f32-262">Der dataStore-Name verweist auf die zuvor erstellte CSV-Datei: **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="c5f32-262">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="c5f32-263">Der idMatch-Wert verweist auf ein durchsuchbares Feld, das in der Datenbankschema-Datei aufgelistet ist: **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="c5f32-263">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="c5f32-264">Der classification-Wert verweist auf einen vorhandenen oder benutzerdefinierten vertraulichen Informationstyp: **classification = "US-Sozialversicherungsnummer (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="c5f32-264">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="c5f32-265">(In diesem Fall wird der vorhandene vertrauliche Informationstyp "US-Sozialversicherungsnummer" verwendet.)</span><span class="sxs-lookup"><span data-stu-id="c5f32-265">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="c5f32-266">Es kann zwischen 10–60 Minuten dauern, bis das EDMSchema durch Ergänzungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="c5f32-266">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="c5f32-267">Das Update muss abgeschlossen sein, bevor Sie Schritte ausführen, die die Zusätze verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5f32-267">The update must complete before you execute steps that use the additions.</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="c5f32-268">Teil 2: Hashen und Hochladen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="c5f32-268">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="c5f32-269">In dieser Phase richten Sie eine benutzerdefinierte Sicherheitsgruppe, ein Benutzerkonto und das Tool EDM-Upload-Agent ein.</span><span class="sxs-lookup"><span data-stu-id="c5f32-269">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="c5f32-270">Verwenden Sie dann das Tool zum Hashen vertraulicher Daten, und laden Sie die gehashten Daten hoch, damit sie indiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="c5f32-270">Then, you use the tool to hash the sensitive data, and upload the hashed data so it can be indexed.</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="c5f32-271">Einrichten der Sicherheitsgruppe und des Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="c5f32-271">Set up the security group and user account</span></span>

1. <span data-ttu-id="c5f32-272">Als globaler Administrator gehen Sie über den entsprechenden [Link für Ihr Abonnement](#portal-links-for-your-subscription) zum Verwaltungszentrum und  [erstellen Sie eine Sicherheitsgruppe](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) namens **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="c5f32-272">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="c5f32-273">Fügen Sie einen oder mehrere Benutzer zur **EDM\_DataUploaders**-Sicherheitsgruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="c5f32-273">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="c5f32-274">(Diese Benutzer verwalten die Datenbank mit vertraulichen Informationen.)</span><span class="sxs-lookup"><span data-stu-id="c5f32-274">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="c5f32-275">Stellen Sie sicher, dass jeder Benutzer, der die vertraulichen Daten verwaltet, ein lokaler Administrator auf dem Computer ist, der für den EDM-Upload-Agent verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c5f32-275">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

#### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="c5f32-276">Einrichten des EDM-Upload-Agenten</span><span class="sxs-lookup"><span data-stu-id="c5f32-276">Set up the EDM Upload Agent</span></span>

>[!NOTE]
> <span data-ttu-id="c5f32-277">Bevor Sie mit diesem Verfahren beginnen, stellen Sie sicher, dass Sie Mitglied der Sicherheitsgruppe **EDM\_DataUploaders** und lokaler Administrator auf Ihrem Computer sind.</span><span class="sxs-lookup"><span data-stu-id="c5f32-277">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group and a local admin on your machine.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="c5f32-278">Links zum EDM-Upload-Agenten nach Abonnementtyp</span><span class="sxs-lookup"><span data-stu-id="c5f32-278">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="c5f32-279">Handel und GCC</span><span class="sxs-lookup"><span data-stu-id="c5f32-279">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="c5f32-280">GCC – hoch</span><span class="sxs-lookup"><span data-stu-id="c5f32-280">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="c5f32-281">DoD</span><span class="sxs-lookup"><span data-stu-id="c5f32-281">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="c5f32-282">Laden Sie den für Ihr Abonnement geeigneten [EDM-Upload-Agent](#links-to-edm-upload-agent-by-subscription-type) herunter und installieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="c5f32-282">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription.</span></span> <span data-ttu-id="c5f32-283">Standardmäßig sollte der Installationsspeicherort  **C:\\Programmdateien\\Microsoft\\EdmUploadAgent** sein.</span><span class="sxs-lookup"><span data-stu-id="c5f32-283">By default, the installation location should be **C:\\Program Files\\Microsoft\\EdmUploadAgent**.</span></span>

   > [!TIP]
   > <span data-ttu-id="c5f32-284">Um eine Liste der unterstützten Befehlsparameter zu erhalten, führen Sie den Agenten ohne Argumente aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-284">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="c5f32-285">Zum Beispiel "EdmUploadAgent.exe".</span><span class="sxs-lookup"><span data-stu-id="c5f32-285">For example 'EdmUploadAgent.exe'.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c5f32-286">Sie können Daten mit dem EDMUploadAgent nur zwei Mal pro Tag in einen bestimmten Datenspeicherort hochladen.</span><span class="sxs-lookup"><span data-stu-id="c5f32-286">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

2. <span data-ttu-id="c5f32-287">Wenn Sie den EDM-Upload-Agenten autorisieren möchten, öffnen Sie die Windows-Eingabeaufforderung (als Administrator), und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c5f32-287">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="c5f32-288">Melden Sie sich mit Ihrem Arbeits- oder Schulkonto für Office 365 an, das der Sicherheitsgruppe EDM_DataUploaders hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="c5f32-288">Sign in with your work or school account for Office 365 that was added to the EDM_DataUploaders security group.</span></span>

<span data-ttu-id="c5f32-289">Im nächsten Schritt verwenden Sie den EDM-Upload-Agent zum Hashen vertraulicher Daten, gefolgt vom Hochladen der gehashten Daten.</span><span class="sxs-lookup"><span data-stu-id="c5f32-289">The next step is to use the EDM Upload Agent to hash the sensitive data, and then upload the hashed data.</span></span>

#### <a name="hash-and-upload-the-sensitive-data"></a><span data-ttu-id="c5f32-290">Hashen und Hochladen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="c5f32-290">Hash and upload the sensitive data</span></span>

<span data-ttu-id="c5f32-291">Speichern Sie die Datei mit den vertraulichen Daten (unser Beispiel ist wie erwähnt **PatientRecords.csv**) auf dem lokalen Laufwerk Ihres Computers.</span><span class="sxs-lookup"><span data-stu-id="c5f32-291">Save the sensitive data file (recall our example is **PatientRecords.csv**) to the local drive on the machine.</span></span> <span data-ttu-id="c5f32-292">(Die Beispieldatei  **PatientRecords.csv** wurde unter  **C:\\Edm\\Data** gespeichert.)</span><span class="sxs-lookup"><span data-stu-id="c5f32-292">(We saved our example **PatientRecords.csv** file to **C:\\Edm\\Data**.)</span></span>

<span data-ttu-id="c5f32-293">Führen Sie zum Hashen und Hochladen vertraulicher Daten den folgenden Befehl in der Windows-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="c5f32-293">To hash and upload the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="c5f32-294">Beispiel: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="c5f32-294">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="c5f32-295">Wenn Sie das Hashen vertraulicher Daten in einer isolierten Umgebung trennen und ausführen möchten, führen Sie die Schritte „Hashen“ und „Hochladen“ separat aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-295">To separate and execute the hashing of sensitive data in an isolated environment, execute the hashing and upload steps separately.</span></span>

<span data-ttu-id="c5f32-296">Führen Sie zum Hashen vertraulicher Daten den folgenden Befehl in der Windows-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="c5f32-296">To hash the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="c5f32-297">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c5f32-297">For example:</span></span>

> <span data-ttu-id="c5f32-298">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="c5f32-298">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="c5f32-299">Führen Sie zum Hochladen gehashter Daten den folgenden Befehl in der Windows-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="c5f32-299">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="c5f32-300">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c5f32-300">For example:</span></span>

> <span data-ttu-id="c5f32-301">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="c5f32-301">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="c5f32-302">Führen Sie zur Überprüfung, ob Ihre vertraulichen Daten hochgeladen wurden, den folgenden Befehl in der Windows-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="c5f32-302">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="c5f32-303">Sie sehen eine Liste der Datenspeicher und wann sie zuletzt aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c5f32-303">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="c5f32-304">Wenn Sie alle Daten sehen möchten, die in einen bestimmten Store hochgeladen wurden, führen Sie den folgenden Befehl in einer Windows-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="c5f32-304">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="c5f32-305">Fahren Sie mit dem Einrichten des Prozesses und des Zeitplans für das [Aktualisieren der Datenbank für vertrauliche Informationen](#refreshing-your-sensitive-information-database) fort.</span><span class="sxs-lookup"><span data-stu-id="c5f32-305">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="c5f32-306">Sie können nun die EDM-basierte Klassifikation mit Ihren Microsoft Cloud Services verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5f32-306">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="c5f32-307">Sie können beispielsweise [eine DLP-Richtlinie mithilfe der EDM-basierten Klassifizierung einrichten](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="c5f32-307">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="c5f32-308">Aktualisieren der Datenbank für vertrauliche Informationen</span><span class="sxs-lookup"><span data-stu-id="c5f32-308">Refreshing your sensitive information database</span></span>

<span data-ttu-id="c5f32-309">Sie können Ihre Datenbank für vertrauliche Informationen täglich oder wöchentlich aktualisieren, und das EDM-Upload-Tool kann die vertraulichen Daten erneut hashen und die gehashten Daten dann erneut hochladen.</span><span class="sxs-lookup"><span data-stu-id="c5f32-309">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can re-hash the sensitive data and then reupload the hashed data.</span></span>

1. <span data-ttu-id="c5f32-310">Ermitteln Sie den Vorgang und die Häufigkeit (täglich oder wöchentlich) zum Aktualisieren der Datenbank mit vertraulichen Informationen.</span><span class="sxs-lookup"><span data-stu-id="c5f32-310">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="c5f32-311">Exportieren Sie die vertraulichen Daten erneut in eine App, wie z. B. Microsoft Excel, und speichern Sie die Datei im CSV-Format.</span><span class="sxs-lookup"><span data-stu-id="c5f32-311">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="c5f32-312">Behalten Sie den Dateinamen und den Speicherort bei, den Sie beim Ausführen der unter  [Hashen und Hochladen vertraulicher Daten](#hash-and-upload-the-sensitive-data) beschriebenen Schritte verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="c5f32-312">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="c5f32-313">Wenn es keine Änderungen an der Struktur (Feldnamen) der CSV-Datei gibt, müssen Sie auch keine an der Datenbankschemadatei vornehmen, wenn Sie die Daten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c5f32-313">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="c5f32-314">Wenn Sie jedoch Änderungen vornehmen müssen, stellen Sie sicher, dass Sie das Datenbankschema und Ihr Regelpaket entsprechend bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c5f32-314">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="c5f32-315">Mithilfe des  [Aufgabenplaners](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page)  können Sie die Schritte 2 und 3 im Verfahren [Hashen und Hochladen vertraulicher Daten](#hash-and-upload-the-sensitive-data)  automatisieren.</span><span class="sxs-lookup"><span data-stu-id="c5f32-315">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="c5f32-316">Sie können Aufgaben mithilfe verschiedener Methoden planen:</span><span class="sxs-lookup"><span data-stu-id="c5f32-316">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="c5f32-317">Methode</span><span class="sxs-lookup"><span data-stu-id="c5f32-317">Method</span></span>             | <span data-ttu-id="c5f32-318">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="c5f32-318">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="c5f32-319">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5f32-319">Windows PowerShell</span></span>     | <span data-ttu-id="c5f32-320">Siehe die Dokumentation [Aufgabenplanung](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) und das [PowerShell-Beispielskript](#example-powershell-script-for-task-scheduler) in diesem Artikel</span><span class="sxs-lookup"><span data-stu-id="c5f32-320">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="c5f32-321">Aufgabenplaner-API</span><span class="sxs-lookup"><span data-stu-id="c5f32-321">Task Scheduler API</span></span>     | <span data-ttu-id="c5f32-322">Lesen Sie die Dokumentation [Aufgabenplanung](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="c5f32-322">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="c5f32-323">Windows-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="c5f32-323">Windows user interface</span></span> | <span data-ttu-id="c5f32-324">Klicken Sie in Windows auf **Start**, und geben Sie „Aufgabenplanung“ ein.</span><span class="sxs-lookup"><span data-stu-id="c5f32-324">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="c5f32-325">Klicken Sie dann in der Ergebnisliste mit der rechten Maustaste auf **Aufgabenplanung** und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-325">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="c5f32-326">„PowerShell-Beispielskript“ für „Aufgabenplanung“</span><span class="sxs-lookup"><span data-stu-id="c5f32-326">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="c5f32-327">Dieser Abschnitt enthält ein Beispiel für ein PowerShell-Skript, mit dem Sie Ihre Aufgaben zum Hashen von Daten und Hochladen gehashter Daten planen können:</span><span class="sxs-lookup"><span data-stu-id="c5f32-327">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="c5f32-328">So planen Sie das Hashen und Hochladen in einem kombinierten Schritt</span><span class="sxs-lookup"><span data-stu-id="c5f32-328">To schedule hashing and upload in a combined step</span></span>

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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="c5f32-329">So planen Sie das Hashen und Hochladen als separate Schritte</span><span class="sxs-lookup"><span data-stu-id="c5f32-329">To schedule hashing and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="c5f32-330">Teil 3: Verwenden der EDM-basierten Klassifizierung mit Ihren Microsoft Cloud Services</span><span class="sxs-lookup"><span data-stu-id="c5f32-330">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="c5f32-331">Diese Speicherorte sind unterstützte Typen vertraulicher EDM-Informationen:</span><span class="sxs-lookup"><span data-stu-id="c5f32-331">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="c5f32-332">DLP für Exchange Online (E-Mail)</span><span class="sxs-lookup"><span data-stu-id="c5f32-332">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="c5f32-333">OneDrive for Business (Dateien)</span><span class="sxs-lookup"><span data-stu-id="c5f32-333">OneDrive for Business (files)</span></span>
- <span data-ttu-id="c5f32-334">Microsoft Teams (Unterhaltungen)</span><span class="sxs-lookup"><span data-stu-id="c5f32-334">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="c5f32-335">DLP für SharePoint (Dateien)</span><span class="sxs-lookup"><span data-stu-id="c5f32-335">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="c5f32-336">DLP-Richtlinien für Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c5f32-336">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="c5f32-337">Vertrauliche EDM-Informationstypen für die folgenden Szenarien sind derzeit in der Entwicklung, aber noch nicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="c5f32-337">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="c5f32-338">automatische Klassifizierung von Vertraulichkeits- und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c5f32-338">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="c5f32-339">Erstellen einer DLP-Richtlinie mit EDM</span><span class="sxs-lookup"><span data-stu-id="c5f32-339">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="c5f32-340">Gehen Sie zum Security & Compliance Center, indem Sie den entsprechenden [Link für Ihr Abonnement](#portal-links-for-your-subscription) verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5f32-340">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="c5f32-341">Klicken Sie auf die **Richtlinie** \> **zur Verhinderung von Datenverlust**.</span><span class="sxs-lookup"><span data-stu-id="c5f32-341">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="c5f32-342">Wählen Sie **Richtlinie erstellen** \> **Benutzerdefiniert** \> **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-342">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="c5f32-343">Geben Sie auf der Registerkarte **Richtlinie benennen** einen Namen und eine Beschreibung ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-343">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="c5f32-344">Wählen Sie auf der Registerkarte **Speicherorte auswählen**  **Bestimmte Speicherorte auswählen** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-344">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="c5f32-345">Wählen Sie in der Spalte **Status**  **Exchange-E-Mail, OneDrive-Konten, Teams-Chat und Kanalnachricht** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-345">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="c5f32-346">Wählen Sie auf der Registerkarte **Richtlinieneinstellungen**  **Erweiterte Einstellungen verwenden** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-346">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="c5f32-347">Wählen Sie **+ Neue Regel** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-347">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="c5f32-348">Geben Sie im Abschnitt **Name** einen Namen und eine Beschreibung für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="c5f32-348">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="c5f32-349">Wählen Sie im Abschnitt **Bedingungen** in der Liste **+ Bedingung hinzufügen**  **Inhalt enthält vertraulichen Typ** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-349">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![Inhalt enthält sensible Informationstypen](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="c5f32-351">Suchen Sie den vertraulichen Informationstyp, den Sie beim Einrichten Ihres Regelpakets erstellt haben, und wählen Sie dann **+ Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-351">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="c5f32-352">Wählen Sie dann **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-352">Then choose **Done**.</span></span>

12. <span data-ttu-id="c5f32-353">Wählen Sie Optionen für die Regel aus, wie z. B. **Benutzerbenachrichtigungen**, **Außerkraftsetzungen durch Benutzer**, **Schadensberichte** usw., und dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-353">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="c5f32-354">Überprüfen Sie auf der Registerkarte **Richtlinieneinstellungen** Ihre Regeln und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-354">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="c5f32-355">Geben Sie an, ob Sie die Richtlinie sofort aktivieren, testen oder deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c5f32-355">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="c5f32-356">Wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-356">Then choose **Next**.</span></span>

15. <span data-ttu-id="c5f32-357">Überprüfen Sie auf der Registerkarte **Überprüfen Sie Ihre Einstellungen** Ihre Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="c5f32-357">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="c5f32-358">Nehmen Sie alle nötigen Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="c5f32-358">Make any needed changes.</span></span> <span data-ttu-id="c5f32-359">Wenn Sie fertig sind, wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f32-359">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="c5f32-360">Es kann ungefähr eine Stunde dauern, bis Ihre neue DLP-Richtlinie im Rechenzentrum erscheint.</span><span class="sxs-lookup"><span data-stu-id="c5f32-360">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c5f32-361">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="c5f32-361">Related articles</span></span>

- [<span data-ttu-id="c5f32-362">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="c5f32-362">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="c5f32-363">Benutzerdefinierte vertrauliche Informationstypen</span><span class="sxs-lookup"><span data-stu-id="c5f32-363">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="c5f32-364">Überblick über DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="c5f32-364">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="c5f32-365">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c5f32-365">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="c5f32-366">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="c5f32-366">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema?view=exchange-ps)

