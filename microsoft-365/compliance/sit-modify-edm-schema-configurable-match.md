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
ms.openlocfilehash: 2211e4d99d97fcce241a5f4c3ea7c9d8122ca9d7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656801"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a><span data-ttu-id="bfd3c-103">Ändern Sie das Schema für die genaue Datenübereinstimmung, um eine konfigurierbare Übereinstimmung zu verwenden</span><span class="sxs-lookup"><span data-stu-id="bfd3c-103">Modify Exact Data Match schema to use configurable match</span></span>

<span data-ttu-id="bfd3c-104">Mit der EDM-basierten Klassifizierung (Exact Data Match) können Sie benutzerdefinierte vertrauliche Informationstypen erstellen, die sich auf genaue Werte in einer Datenbank mit vertraulichen Informationen beziehen.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-104">Exact Data Match (EDM) based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="bfd3c-105">Wenn Sie Varianten einer exakten Zeichenfolge zulassen müssen, können Sie mithilfe der *konfigurierbaren Übereinstimmung* Microsoft 365 anweisen, Groß- und Kleinschreibung und einige Trennzeichen zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-105">When you need to allow for variants of a exact string, you can use *configurable match* to tell Microsoft 365 to ignore case and some delimiters.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="bfd3c-106">Verwenden Sie dieses Verfahren, um ein vorhandenes EDM-Schema und eine vorhandene Datendatei zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-106">Use this procedure to modify an existing EDM schema and data file.</span></span>

1. <span data-ttu-id="bfd3c-107">Deinstallieren Sie die Datei **EdmUploadAgent.exe** von dem Computer, auf dem Sie eine Verbindung zu Microsoft 365 für das Hochladen von EDM-Schemas und Datendateien herstellen.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-107">Uninstall the **EdmUploadAgent.exe** from the computer that you use to connect to Microsoft 365 for EDM schema and data file upload purposes.</span></span>

2. <span data-ttu-id="bfd3c-108">Laden Sie die entsprechende Datei **EdmUploadAgent.exe** für Ihr Abonnement über die folgenden Links herunter:</span><span class="sxs-lookup"><span data-stu-id="bfd3c-108">Download the appropriate **EdmUploadAgent.exe** file for your subscription using the links below:</span></span>
    - <span data-ttu-id="bfd3c-109">[Handel + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) – die meisten gewerblichen Kunden sollten dies verwenden</span><span class="sxs-lookup"><span data-stu-id="bfd3c-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
    - <span data-ttu-id="bfd3c-110">[GCC-Hoch](https://go.microsoft.com/fwlink/?linkid=2137521) – Dies ist speziell für Cloud-Abonnenten mit hoher Sicherheit in der Regierung</span><span class="sxs-lookup"><span data-stu-id="bfd3c-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
    - <span data-ttu-id="bfd3c-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) – Dies ist speziell für Cloud-Kunden des US-Verteidigungsministeriums</span><span class="sxs-lookup"><span data-stu-id="bfd3c-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

3. <span data-ttu-id="bfd3c-112">Autorisieren Sie den EDM-Upload-Agenten, öffnen Sie das Eingabeaufforderungsfenster (als Administrator) und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bfd3c-112">Authorize the EDM Upload Agent, open Command Prompt window (as an administrator) and run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="bfd3c-113">Wenn Sie keine aktuelle Kopie des vorhandenen Schemas haben, müssen Sie eine Kopie des vorhandenen Schemas herunterladen. Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bfd3c-113">If you don't have a current copy of the existing schema, you'll need to download a copy of the existing schema, run this command:</span></span>

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. <span data-ttu-id="bfd3c-114">Passen Sie das Schema so an, dass jede Spalte "caseInsensitive" und / oder "ignoreDelimiters" verwendet.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-114">Customize the schema so each column utilizes “caseInsensitive” and / or “ignoredDelimiters”.</span></span>  <span data-ttu-id="bfd3c-115">Der Standardwert für "caseInsensitive" ist "false" und für "ignoreDelimiters" eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-115">The default value for “caseInsensitive” is “false” and for “ignoredDelimiters”, it is an empty string.</span></span> 

> [!NOTE]
> <span data-ttu-id="bfd3c-116">Der zugrunde liegende benutzerdefinierte vertrauliche Informationstyp oder der integrierte vertrauliche Informationstyp, der zum Erkennen des allgemeinen RegEx-Musters verwendet wird, muss die Erkennung der mit ignorierten Begrenzern aufgelisteten Variationseingaben unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-116">The underlying custom sensitive information type or built in sensitive information type used to detect the general regex pattern must support detection of the variations inputs listed with ignoredDelimiters.</span></span> <span data-ttu-id="bfd3c-117">Beispielsweise kann der in der US-Sozialversicherungsnummer (SSN) integrierte Informationstyp Abweichungen in den Daten erkennen, die Bindestriche, Leerzeichen oder fehlende Leerzeichen zwischen den gruppierten Nummern enthalten, aus denen die SSN besteht.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-117">For example, the built in U.S. social security number (SSN) sensitive information type can detect variations in the data that include dashes, spaces, or lack of spaces between the grouped numbers that make up the SSN.</span></span> <span data-ttu-id="bfd3c-118">Daher sind die einzigen Trennzeichen, die relevant sind, um sie in die ignorierten Begrenzer von EDM für SSN-Daten aufzunehmen: Bindestrich und Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-118">As a result, the only delimiters that are relevant to include in EDM’s ignoredDelimiters for SSN data are: dash and space.</span></span>

<span data-ttu-id="bfd3c-119">Hier ist ein Beispielschema, das eine Übereinstimmung ohne Berücksichtigung der Groß- und Kleinschreibung simuliert, indem die zusätzlichen Spalten erstellt werden, die zum Erkennen von Abweichungen zwischen Groß- und Kleinschreibung in den sensiblen Daten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-119">Here is a sample schema that simulates case insensitive match by creating the extra columns needed to recognize case variations in the sensitive data.</span></span>

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

<span data-ttu-id="bfd3c-120">Im obigen Beispiel werden die Variationen der ursprünglichen Spalte `PolicyNumber` nicht mehr benötigt, wenn beide `caseInsensitive` und `ignoredDelimiters` hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-120">In the above example, the variations of the original `PolicyNumber` column will no longer be needed if both `caseInsensitive` and `ignoredDelimiters` are added.</span></span>

<span data-ttu-id="bfd3c-121">Verwenden Sie die Flags `caseInsensitive` und `ignoredDelimiters`, um dieses Schema so zu aktualisieren, dass EDM konfigurierbare Übereinstimmungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-121">To update this schema so that EDM uses configurable match use the `caseInsensitive` and `ignoredDelimiters` flags.</span></span>  <span data-ttu-id="bfd3c-122">So sieht das aus:</span><span class="sxs-lookup"><span data-stu-id="bfd3c-122">Here's how that looks:</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="bfd3c-123">Das Banner `ignoredDelimiters` unterstützt alle nicht alphanumerischen Zeichen. Hier einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="bfd3c-123">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="bfd3c-124">\.</span><span class="sxs-lookup"><span data-stu-id="bfd3c-124">\.</span></span>
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

<span data-ttu-id="bfd3c-125">Das Banner `ignoredDelimiters` ist nicht vorhanden:</span><span class="sxs-lookup"><span data-stu-id="bfd3c-125">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="bfd3c-126">Zeichen 0-9</span><span class="sxs-lookup"><span data-stu-id="bfd3c-126">characters 0-9</span></span>
- <span data-ttu-id="bfd3c-127">A-Z</span><span class="sxs-lookup"><span data-stu-id="bfd3c-127">A-Z</span></span>
- <span data-ttu-id="bfd3c-128">a-z</span><span class="sxs-lookup"><span data-stu-id="bfd3c-128">a-z</span></span>
- \"
- \,

6. <span data-ttu-id="bfd3c-129">Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="bfd3c-129">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

7. <span data-ttu-id="bfd3c-130">Aktualisieren Sie Ihr Schema, indem Sie diese Cmdlets einzeln ausführen:</span><span class="sxs-lookup"><span data-stu-id="bfd3c-130">Update your schema by running these cmdlets one at a time:</span></span>

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. <span data-ttu-id="bfd3c-131">Aktualisieren Sie gegebenenfalls die Datendatei, um sie an die neue Schemaversion anzupassen</span><span class="sxs-lookup"><span data-stu-id="bfd3c-131">If necessary, update the data file to match the new schema version</span></span>

> [!TIP]
> <span data-ttu-id="bfd3c-132">Optional können Sie vor dem Hochladen eine Validierung für Ihre CSV-Datei ausführen, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="bfd3c-132">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
><span data-ttu-id="bfd3c-133">Weitere Informationen zu allen von EdmUploadAgent.exe> unterstützten Parametern erhalten Sie</span><span class="sxs-lookup"><span data-stu-id="bfd3c-133">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

9. <span data-ttu-id="bfd3c-134">Öffnen Sie das Eingabeaufforderungsfenster (als Administrator) und führen Sie den folgenden Befehl aus, um Ihre vertraulichen Daten zu hashen und hochzuladen:</span><span class="sxs-lookup"><span data-stu-id="bfd3c-134">Open Command Prompt window (as an administrator) and run the following command to hash and upload your sensitive data:</span></span>

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a><span data-ttu-id="bfd3c-135">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="bfd3c-135">Related articles</span></span>

- <span data-ttu-id="bfd3c-136">[Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="bfd3c-136">[Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span></span>
- [<span data-ttu-id="bfd3c-137">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="bfd3c-137">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="bfd3c-138">Benutzerdefinierte vertrauliche Informationstypen</span><span class="sxs-lookup"><span data-stu-id="bfd3c-138">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="bfd3c-139">Überblick über DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="bfd3c-139">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="bfd3c-140">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bfd3c-140">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="bfd3c-141">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="bfd3c-141">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema)