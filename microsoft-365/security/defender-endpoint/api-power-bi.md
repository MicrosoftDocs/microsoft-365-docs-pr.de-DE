---
title: Verbindung von Microsoft Defender für Endpunkt-APIs Power BI
ms.reviewer: ''
description: Erstellen Sie einen Power Business Intelligence (BI)-Bericht über Microsoft Defender for Endpoint-APIs.
keywords: apis, supported apis, Power BI, reports
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7c99267d75c89b3484d207cd763131e4bcc91527
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935041"
---
# <a name="create-custom-reports-using-power-bi"></a>Erstellen benutzerdefinierter Berichte mithilfe Power BI

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

In diesem Abschnitt erfahren Sie, wie Sie Power BI defender for Endpoint-APIs erstellen.

Im ersten Beispiel wird veranschaulicht, wie Power BI mit der Advanced Hunting-API verbunden wird, und im zweiten Beispiel wird eine Verbindung mit unseren OData-APIs, z. B. Computeraktionen oder Warnungen, veranschaulicht.

## <a name="connect-power-bi-to-advanced-hunting-api"></a>Verbinden Power BI zu Advanced Hunting API

- Öffnen Sie Microsoft Power BI

- Klicken **Sie auf Daten leere Abfrage**  >  **erhalten**

    ![Abbildung des Erstellens einer leeren Abfrage](images/power-bi-create-blank-query.png)

- Klicken Sie **auf Erweiterter Editor**

    ![Abbildung des geöffneten erweiterten Editors](images/power-bi-open-advanced-editor.png)

- Kopieren Sie den folgenden Text, und fügen Sie ihn in den Editor ein:

```
    let 
        AdvancedHuntingQuery = "DeviceEvents | where ActionType contains 'Anti' | limit 20",

        HuntingUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries",

        Response = Json.Document(Web.Contents(HuntingUrl, [Query=[key=AdvancedHuntingQuery]])),

        TypeMap = #table(
            { "Type", "PowerBiType" },
            {
                { "Double",   Double.Type },
                { "Int64",    Int64.Type },
                { "Int32",    Int32.Type },
                { "Int16",    Int16.Type },
                { "UInt64",   Number.Type },
                { "UInt32",   Number.Type },
                { "UInt16",   Number.Type },
                { "Byte",     Byte.Type },
                { "Single",   Single.Type },
                { "Decimal",  Decimal.Type },
                { "TimeSpan", Duration.Type },
                { "DateTime", DateTimeZone.Type },
                { "String",   Text.Type },
                { "Boolean",  Logical.Type },
                { "SByte",    Logical.Type },
                { "Guid",     Text.Type }
            }),

        Schema = Table.FromRecords(Response[Schema]),
        TypedSchema = Table.Join(Table.SelectColumns(Schema, {"Name", "Type"}), {"Type"}, TypeMap , {"Type"}),
        Results = Response[Results],
        Rows = Table.FromRecords(Results, Schema[Name]),
        Table = Table.TransformColumnTypes(Rows, Table.ToList(TypedSchema, (c) => {c{0}, c{2}}))

    in Table

```

- Klicken Sie auf **Fertig**

- Klicken **Sie auf Anmeldeinformationen bearbeiten**

    ![Abbildung der Anmeldeinformationen bearbeiten0](images/power-bi-edit-credentials.png)

- Auswählen **des Organisationskontos**  >  **Anmelden**

    ![Abbildung der festgelegten Anmeldeinformationen1](images/power-bi-set-credentials-organizational.png)

- Geben Sie Ihre Anmeldeinformationen ein, und warten Sie, bis sie angemeldet sind

- Klicken Sie **Verbinden**

    ![Abbildung der festgelegten Anmeldeinformationen2](images/power-bi-set-credentials-organizational-cont.png)

- Jetzt werden die Ergebnisse Ihrer Abfrage als Tabelle angezeigt, und Sie können mit dem Erstellen von Visualisierungen beginnen.

- Sie können diese Tabelle duplizieren, umbenennen und die Erweiterte Suche bearbeiten, um beliebige Daten zu erhalten.

## <a name="connect-power-bi-to-odata-apis"></a>Verbinden Power BI zu OData-APIs

- Der einzige Unterschied zum obigen Beispiel ist die Abfrage innerhalb des Editors. 

- Kopieren Sie die folgende Datei, und fügen Sie sie in den Editor ein, um alle **Computeraktionen aus** Ihrer Organisation zu ziehen:

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- Sie können dasselbe für Warnungen **und** **Computer tun.**

- Sie können auch OData-Abfragen für Abfragenfilter verwenden. Weitere Informationen finden Sie unter [Using OData Queries](exposed-apis-odata-samples.md)


## <a name="power-bi-dashboard-samples-in-github"></a>Power BI Dashboardbeispiele in GitHub
Weitere Informationen finden Sie unter [Power BI Berichtsvorlagen](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).

## <a name="sample-reports"></a>Beispielberichte
Anzeigen der Microsoft Defender for Endpoint Power BI Berichtsbeispiele. Weitere Informationen finden Sie unter [Durchsuchen von Codebeispielen](https://docs.microsoft.com/samples/browse/?products=mdatp).


## <a name="related-topic"></a>Verwandtes Thema
- [Defender für Endpunkt-APIs](apis-intro.md)
- [Erweiterte Suche-API](run-advanced-query-api.md)
- [Verwenden von OData-Abfragen](exposed-apis-odata-samples.md)
