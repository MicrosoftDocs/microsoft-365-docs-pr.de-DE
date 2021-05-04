---
title: Ändern Sie das Schema für die genaue Datenübereinstimmung, um eine konfigurierbare Übereinstimmung zu verwenden
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
description: Erfahren Sie, wie Sie ein EDM-Schema ändern, um eine konfigurierbare Übereinstimmung zu verwenden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7d470b986d4a94206935efb832deec7171f8e404
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114193"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a><span data-ttu-id="569b4-103">Ändern Sie das Schema für die genaue Datenübereinstimmung, um eine konfigurierbare Übereinstimmung zu verwenden</span><span class="sxs-lookup"><span data-stu-id="569b4-103">Modify Exact Data Match schema to use configurable match</span></span>

<span data-ttu-id="569b4-104">Mit der EDM-basierten Klassifizierung (Exact Data Match) können Sie benutzerdefinierte vertrauliche Informationstypen erstellen, die sich auf genaue Werte in einer Datenbank mit vertraulichen Informationen beziehen.</span><span class="sxs-lookup"><span data-stu-id="569b4-104">Exact Data Match (EDM) based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="569b4-105">Wenn Sie Varianten einer exakten Zeichenfolge zulassen müssen, können Sie mithilfe der *konfigurierbaren Übereinstimmung* Microsoft 365 anweisen, Groß- und Kleinschreibung und einige Trennzeichen zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="569b4-105">When you need to allow for variants of a exact string, you can use *configurable match* to tell Microsoft 365 to ignore case and some delimiters.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="569b4-106">Verwenden Sie dieses Verfahren, um ein vorhandenes EDM-Schema und eine vorhandene Datendatei zu ändern.</span><span class="sxs-lookup"><span data-stu-id="569b4-106">Use this procedure to modify an existing EDM schema and data file.</span></span>

1. <span data-ttu-id="569b4-107">Deinstallieren Sie die Datei **EdmUploadAgent.exe** von dem Computer, auf dem Sie eine Verbindung zu Microsoft 365 für das Hochladen von EDM-Schemas und Datendateien herstellen.</span><span class="sxs-lookup"><span data-stu-id="569b4-107">Uninstall the **EdmUploadAgent.exe** from the computer that you use to connect to Microsoft 365 for EDM schema and data file upload purposes.</span></span>

2. <span data-ttu-id="569b4-108">Laden Sie die entsprechende Datei **EdmUploadAgent.exe** für Ihr Abonnement über die folgenden Links herunter:</span><span class="sxs-lookup"><span data-stu-id="569b4-108">Download the appropriate **EdmUploadAgent.exe** file for your subscription using the links below:</span></span>
    - <span data-ttu-id="569b4-109">[Handel + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) – die meisten gewerblichen Kunden sollten dies verwenden</span><span class="sxs-lookup"><span data-stu-id="569b4-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
    - <span data-ttu-id="569b4-110">[GCC-Hoch](https://go.microsoft.com/fwlink/?linkid=2137521) – Dies ist speziell für Cloud-Abonnenten mit hoher Sicherheit in der Regierung</span><span class="sxs-lookup"><span data-stu-id="569b4-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
    - <span data-ttu-id="569b4-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) – Dies ist speziell für Cloud-Kunden des US-Verteidigungsministeriums</span><span class="sxs-lookup"><span data-stu-id="569b4-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

3. <span data-ttu-id="569b4-112">Autorisieren Sie den EDM-Upload-Agenten, öffnen Sie das Eingabeaufforderungsfenster (als Administrator) und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="569b4-112">Authorize the EDM Upload Agent, open Command Prompt window (as an administrator) and run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="569b4-113">Wenn Sie keine aktuelle Kopie des vorhandenen Schemas haben, müssen Sie eine Kopie des vorhandenen Schemas herunterladen. Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="569b4-113">If you don't have a current copy of the existing schema, you'll need to download a copy of the existing schema, run this command:</span></span>

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. <span data-ttu-id="569b4-114">Passen Sie das Schema so an, dass jede Spalte "caseInsensitive" und / oder "ignoreDelimiters" verwendet.</span><span class="sxs-lookup"><span data-stu-id="569b4-114">Customize the schema so each column utilizes “caseInsensitive” and / or “ignoredDelimiters”.</span></span>  <span data-ttu-id="569b4-115">Der Standardwert für "caseInsensitive" ist "false" und für "ignoreDelimiters" eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="569b4-115">The default value for “caseInsensitive” is “false” and for “ignoredDelimiters”, it is an empty string.</span></span> 

> [!NOTE]
> <span data-ttu-id="569b4-116">Der zugrunde liegende benutzerdefinierte vertrauliche Informationstyp oder der integrierte vertrauliche Informationstyp, der zum Erkennen des allgemeinen RegEx-Musters verwendet wird, muss die Erkennung der mit ignorierten Begrenzern aufgelisteten Variationseingaben unterstützen.</span><span class="sxs-lookup"><span data-stu-id="569b4-116">The underlying custom sensitive information type or built in sensitive information type used to detect the general regex pattern must support detection of the variations inputs listed with ignoredDelimiters.</span></span> <span data-ttu-id="569b4-117">Beispielsweise kann der in der US-Sozialversicherungsnummer (SSN) integrierte Informationstyp Abweichungen in den Daten erkennen, die Bindestriche, Leerzeichen oder fehlende Leerzeichen zwischen den gruppierten Nummern enthalten, aus denen die SSN besteht.</span><span class="sxs-lookup"><span data-stu-id="569b4-117">For example, the built in U.S. social security number (SSN) sensitive information type can detect variations in the data that include dashes, spaces, or lack of spaces between the grouped numbers that make up the SSN.</span></span> <span data-ttu-id="569b4-118">Daher sind die einzigen Trennzeichen, die relevant sind, um sie in die ignorierten Begrenzer von EDM für SSN-Daten aufzunehmen: Bindestrich und Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="569b4-118">As a result, the only delimiters that are relevant to include in EDM’s ignoredDelimiters for SSN data are: dash and space.</span></span>

<span data-ttu-id="569b4-119">Hier ist ein Beispielschema, das eine Übereinstimmung ohne Berücksichtigung der Groß- und Kleinschreibung simuliert, indem die zusätzlichen Spalten erstellt werden, die zum Erkennen von Abweichungen zwischen Groß- und Kleinschreibung in den sensiblen Daten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="569b4-119">Here is a sample schema that simulates case insensitive match by creating the extra columns needed to recognize case variations in the sensitive data.</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="569b4-120">Im obigen Beispiel werden die Variationen der ursprünglichen Spalte `PolicyNumber` nicht mehr benötigt, wenn beide `caseInsensitive` und `ignoredDelimiters` hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="569b4-120">In the above example, the variations of the original `PolicyNumber` column will no longer be needed if both `caseInsensitive` and `ignoredDelimiters` are added.</span></span>

<span data-ttu-id="569b4-121">Verwenden Sie die Flags `caseInsensitive` und `ignoredDelimiters`, um dieses Schema so zu aktualisieren, dass EDM konfigurierbare Übereinstimmungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="569b4-121">To update this schema so that EDM uses configurable match use the `caseInsensitive` and `ignoredDelimiters` flags.</span></span>  <span data-ttu-id="569b4-122">So sieht das aus:</span><span class="sxs-lookup"><span data-stu-id="569b4-122">Here's how that looks:</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="569b4-123">Das Banner `ignoredDelimiters` unterstützt alle nicht alphanumerischen Zeichen. Hier einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="569b4-123">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="569b4-124">\.</span><span class="sxs-lookup"><span data-stu-id="569b4-124">\.</span></span>
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

<span data-ttu-id="569b4-125">Das Banner `ignoredDelimiters` ist nicht vorhanden:</span><span class="sxs-lookup"><span data-stu-id="569b4-125">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="569b4-126">Zeichen 0-9</span><span class="sxs-lookup"><span data-stu-id="569b4-126">characters 0-9</span></span>
- <span data-ttu-id="569b4-127">A-Z</span><span class="sxs-lookup"><span data-stu-id="569b4-127">A-Z</span></span>
- <span data-ttu-id="569b4-128">a-z</span><span class="sxs-lookup"><span data-stu-id="569b4-128">a-z</span></span>
- \"
- \,

6. <span data-ttu-id="569b4-129">Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="569b4-129">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="569b4-130">Wenn Ihre Organisation [Kundenschlüssel für Microsoft 365 auf Mandantenebene (öffentliche Vorschau)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview) eingerichtet hat, wird bei der genauen Datenübereinstimmung automatisch dessen Verschlüsselungsfunktionalität verwendet.</span><span class="sxs-lookup"><span data-stu-id="569b4-130">If your organization has set up [Customer Key for Microsoft 365 at the tenant level (public preview)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="569b4-131">Dies ist nur für Mandanten mit E5-Lizenz in der kommerziellen Cloud verfügbar.</span><span class="sxs-lookup"><span data-stu-id="569b4-131">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

7. <span data-ttu-id="569b4-132">Aktualisieren Sie Ihr Schema, indem Sie diese Cmdlets einzeln ausführen:</span><span class="sxs-lookup"><span data-stu-id="569b4-132">Update your schema by running these cmdlets one at a time:</span></span>

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. <span data-ttu-id="569b4-133">Aktualisieren Sie gegebenenfalls die Datendatei, um sie an die neue Schemaversion anzupassen</span><span class="sxs-lookup"><span data-stu-id="569b4-133">If necessary, update the data file to match the new schema version</span></span>

> [!TIP]
> <span data-ttu-id="569b4-134">Optional können Sie vor dem Hochladen eine Validierung für Ihre CSV-Datei ausführen, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="569b4-134">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
><span data-ttu-id="569b4-135">Weitere Informationen zu allen von EdmUploadAgent.exe> unterstützten Parametern erhalten Sie</span><span class="sxs-lookup"><span data-stu-id="569b4-135">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

9. <span data-ttu-id="569b4-136">Öffnen Sie das Eingabeaufforderungsfenster (als Administrator) und führen Sie den folgenden Befehl aus, um Ihre vertraulichen Daten zu hashen und hochzuladen:</span><span class="sxs-lookup"><span data-stu-id="569b4-136">Open Command Prompt window (as an administrator) and run the following command to hash and upload your sensitive data:</span></span>

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a><span data-ttu-id="569b4-137">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="569b4-137">Related articles</span></span>

- <span data-ttu-id="569b4-138">[Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="569b4-138">[Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span></span>
- [<span data-ttu-id="569b4-139">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="569b4-139">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="569b4-140">Benutzerdefinierte vertrauliche Informationstypen</span><span class="sxs-lookup"><span data-stu-id="569b4-140">Custom sensitive information types</span></span>](./sensitive-information-type-learn-about.md)
- [<span data-ttu-id="569b4-141">Informationen zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="569b4-141">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="569b4-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="569b4-142">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="569b4-143">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="569b4-143">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)