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
ms.openlocfilehash: dea641072983163c6fbbcc5888d5ee6ea91f6990
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408314"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a>Ändern Sie das Schema für die genaue Datenübereinstimmung, um eine konfigurierbare Übereinstimmung zu verwenden

Mit der EDM-basierten Klassifizierung (Exact Data Match) können Sie benutzerdefinierte vertrauliche Informationstypen erstellen, die sich auf genaue Werte in einer Datenbank mit vertraulichen Informationen beziehen. Wenn Sie Varianten einer exakten Zeichenfolge zulassen müssen, können Sie mithilfe der *konfigurierbaren Übereinstimmung* Microsoft 365 anweisen, Groß- und Kleinschreibung und einige Trennzeichen zu ignorieren. 

> [!IMPORTANT]
> Verwenden Sie dieses Verfahren, um ein vorhandenes EDM-Schema und eine vorhandene Datendatei zu ändern.

1. Deinstallieren Sie die Datei **EdmUploadAgent.exe** von dem Computer, auf dem Sie eine Verbindung zu Microsoft 365 für das Hochladen von EDM-Schemas und Datendateien herstellen.

2. Laden Sie die entsprechende Datei **EdmUploadAgent.exe** für Ihr Abonnement über die folgenden Links herunter:
    - [Handel + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) – die meisten gewerblichen Kunden sollten dies verwenden
    - [GCC-Hoch](https://go.microsoft.com/fwlink/?linkid=2137521) – Dies ist speziell für Cloud-Abonnenten mit hoher Sicherheit in der Regierung
    - [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) – Dies ist speziell für Cloud-Kunden des US-Verteidigungsministeriums

3. Autorisieren Sie den EDM-Upload-Agenten, öffnen Sie das Eingabeaufforderungsfenster (als Administrator) und führen Sie den folgenden Befehl aus:

   `EdmUploadAgent.exe /Authorize`

4. Wenn Sie keine aktuelle Kopie des vorhandenen Schemas haben, müssen Sie eine Kopie des vorhandenen Schemas herunterladen. Führen Sie den folgenden Befehl aus:

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. Passen Sie das Schema so an, dass jede Spalte "caseInsensitive" und / oder "ignoreDelimiters" verwendet.  Der Standardwert für "caseInsensitive" ist "false" und für "ignoreDelimiters" eine leere Zeichenfolge. 

> [!NOTE]
> Der zugrunde liegende benutzerdefinierte vertrauliche Informationstyp oder der integrierte vertrauliche Informationstyp, der zum Erkennen des allgemeinen RegEx-Musters verwendet wird, muss die Erkennung der mit ignorierten Begrenzern aufgelisteten Variationseingaben unterstützen. Beispielsweise kann der in der US-Sozialversicherungsnummer (SSN) integrierte Informationstyp Abweichungen in den Daten erkennen, die Bindestriche, Leerzeichen oder fehlende Leerzeichen zwischen den gruppierten Nummern enthalten, aus denen die SSN besteht. Daher sind die einzigen Trennzeichen, die relevant sind, um sie in die ignorierten Begrenzer von EDM für SSN-Daten aufzunehmen: Bindestrich und Leerzeichen.

Hier ist ein Beispielschema, das eine Übereinstimmung ohne Berücksichtigung der Groß- und Kleinschreibung simuliert, indem die zusätzlichen Spalten erstellt werden, die zum Erkennen von Abweichungen zwischen Groß- und Kleinschreibung in den sensiblen Daten erforderlich sind.

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

Im obigen Beispiel werden die Variationen der ursprünglichen Spalte `PolicyNumber` nicht mehr benötigt, wenn beide `caseInsensitive` und `ignoredDelimiters` hinzugefügt werden.

Verwenden Sie die Flags `caseInsensitive` und `ignoredDelimiters`, um dieses Schema so zu aktualisieren, dass EDM konfigurierbare Übereinstimmungen verwendet.  So sieht das aus:

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

Das Banner `ignoredDelimiters` unterstützt alle nicht alphanumerischen Zeichen. Hier einige Beispiele:
- \.
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

Das Banner `ignoredDelimiters` ist nicht vorhanden:
- Zeichen 0-9
- A-Z
- a-z
- \"
- \,

6. Informationen zum Herstellen der Verbindung zu Security & Compliance Center PowerShell finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).

> [!NOTE]
> Wenn Ihre Organisation [Kundenschlüssel für Microsoft 365 auf Mandantenebene (öffentliche Vorschau)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview) eingerichtet hat, wird bei der genauen Datenübereinstimmung automatisch dessen Verschlüsselungsfunktionalität verwendet. Dies ist nur für Mandanten mit E5-Lizenz in der kommerziellen Cloud verfügbar.

7. Aktualisieren Sie Ihr Schema, indem Sie diese Cmdlets einzeln ausführen:

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. Aktualisieren Sie gegebenenfalls die Datendatei, um sie an die neue Schemaversion anzupassen

> [!TIP]
> Optional können Sie vor dem Hochladen eine Validierung für Ihre CSV-Datei ausführen, indem Sie Folgendes ausführen:
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
>Weitere Informationen zu allen von EdmUploadAgent.exe> unterstützten Parametern erhalten Sie
>
> `EdmUploadAgent.exe /?`

9. Öffnen Sie das Eingabeaufforderungsfenster (als Administrator) und führen Sie den folgenden Befehl aus, um Ihre vertraulichen Daten zu hashen und hochzuladen:

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a>Verwandte Artikel

- [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).
- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
- [Benutzerdefinierte vertrauliche Informationstypen](./sensitive-information-type-learn-about.md)
- [Überblick über DLP-Richtlinien](data-loss-prevention-policies.md)
- [Microsoft Cloud App Security](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)