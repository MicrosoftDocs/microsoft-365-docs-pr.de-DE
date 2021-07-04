---
title: Microsoft Defender für Endpunkt-APIs mit Power BI
ms.reviewer: ''
description: Erstellen Sie einen Power Business Intelligence (BI)-Bericht über Microsoft Defender für Endpunkt-APIs.
keywords: APIs, unterstützte APIs, Power BI, Berichte
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 23d9d61644b4c9adad69a5e467e49ca2b1d92413
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290231"
---
# <a name="create-custom-reports-using-power-bi"></a><span data-ttu-id="2370b-104">Erstellen von benutzerdefinierten Berichten mit Power BI</span><span class="sxs-lookup"><span data-stu-id="2370b-104">Create custom reports using Power BI</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2370b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2370b-105">**Applies to:**</span></span>
- [<span data-ttu-id="2370b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2370b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2370b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2370b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="2370b-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="2370b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2370b-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="2370b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="2370b-110">In diesem Abschnitt erfahren Sie, wie Sie einen Power BI Bericht über Defender für Endpunkt-APIs erstellen.</span><span class="sxs-lookup"><span data-stu-id="2370b-110">In this section you will learn create a Power BI report on top of Defender for Endpoint APIs.</span></span>

<span data-ttu-id="2370b-111">Im ersten Beispiel wird veranschaulicht, wie Power BI mit der API für die erweiterte Suche verbunden werden, und im zweiten Beispiel wird eine Verbindung mit unseren OData-APIs wie Computeraktionen oder Warnungen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2370b-111">The first example demonstrates how to connect Power BI to Advanced Hunting API and the second example demonstrates a connection to our OData APIs, such as Machine Actions or Alerts.</span></span>

## <a name="connect-power-bi-to-advanced-hunting-api"></a><span data-ttu-id="2370b-112">Verbinden Power BI zur API für die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="2370b-112">Connect Power BI to Advanced Hunting API</span></span>

- <span data-ttu-id="2370b-113">Öffnen von Microsoft Power BI</span><span class="sxs-lookup"><span data-stu-id="2370b-113">Open Microsoft Power BI</span></span>

- <span data-ttu-id="2370b-114">Klicken Sie auf  >  **"Leere Daten abrufen"**</span><span class="sxs-lookup"><span data-stu-id="2370b-114">Click **Get Data** > **Blank Query**</span></span>

  ![Abbildung des Erstellens einer leeren Abfrage](images/power-bi-create-blank-query.png)

- <span data-ttu-id="2370b-116">Klicken Sie auf **"Erweiterter Editor"**</span><span class="sxs-lookup"><span data-stu-id="2370b-116">Click **Advanced Editor**</span></span>

  ![Abbildung des geöffneten erweiterten Editors](images/power-bi-open-advanced-editor.png)

- <span data-ttu-id="2370b-118">Kopieren Sie die folgende Datei, und fügen Sie sie in den Editor ein:</span><span class="sxs-lookup"><span data-stu-id="2370b-118">Copy the below and paste it in the editor:</span></span>

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

- <span data-ttu-id="2370b-119">Klicken Sie auf **"Fertig".**</span><span class="sxs-lookup"><span data-stu-id="2370b-119">Click **Done**</span></span>

- <span data-ttu-id="2370b-120">Klicken Sie auf **"Anmeldeinformationen bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="2370b-120">Click **Edit Credentials**</span></span>

    ![Abbildung der Bearbeitungsanmeldeinformationen0](images/power-bi-edit-credentials.png)

- <span data-ttu-id="2370b-122">Organisationskonto   >  **anmelden** auswählen</span><span class="sxs-lookup"><span data-stu-id="2370b-122">Select **Organizational account** > **Sign in**</span></span>

    ![Abbildung der Festgelegten Anmeldeinformationen1](images/power-bi-set-credentials-organizational.png)

- <span data-ttu-id="2370b-124">Geben Sie Ihre Anmeldeinformationen ein, und warten Sie, bis Sie angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="2370b-124">Enter your credentials and wait to be signed in</span></span>

- <span data-ttu-id="2370b-125">Klicken Sie auf **Verbinden**</span><span class="sxs-lookup"><span data-stu-id="2370b-125">Click **Connect**</span></span>

    ![Abbildung der festgelegten Anmeldeinformationen2](images/power-bi-set-credentials-organizational-cont.png)

- <span data-ttu-id="2370b-127">Jetzt werden die Ergebnisse Ihrer Abfrage als Tabelle angezeigt, und Sie können mit der Erstellung von Visualisierungen beginnen.</span><span class="sxs-lookup"><span data-stu-id="2370b-127">Now the results of your query will appear as table and you can start build visualizations on top of it!</span></span>

- <span data-ttu-id="2370b-128">Sie können diese Tabelle duplizieren, umbenennen und die Abfrage "Erweiterte Suche" darin bearbeiten, um alle gewünschten Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2370b-128">You can duplicate this table, rename it and edit the Advanced Hunting query inside to get any data you would like.</span></span>

## <a name="connect-power-bi-to-odata-apis"></a><span data-ttu-id="2370b-129">Verbinden Power BI zu OData-APIs</span><span class="sxs-lookup"><span data-stu-id="2370b-129">Connect Power BI to OData APIs</span></span>

- <span data-ttu-id="2370b-130">Der einzige Unterschied zum obigen Beispiel ist die Abfrage innerhalb des Editors.</span><span class="sxs-lookup"><span data-stu-id="2370b-130">The only difference from the above example is the query inside the editor.</span></span>

- <span data-ttu-id="2370b-131">Kopieren Sie die folgende Datei, und fügen Sie sie in den Editor ein, um alle **Computeraktionen** aus Ihrer Organisation abzurufen:</span><span class="sxs-lookup"><span data-stu-id="2370b-131">Copy the below and paste it in the editor to pull all **Machine Actions** from your organization:</span></span>

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source
```

- <span data-ttu-id="2370b-132">Sie können dies auch für **Warnungen** und **Computer** tun.</span><span class="sxs-lookup"><span data-stu-id="2370b-132">You can do the same for **Alerts** and **Machines**.</span></span>
- <span data-ttu-id="2370b-133">Sie können auch OData-Abfragen für Abfragefilter verwenden. Weitere Informationen finden Sie unter [Verwenden von OData-Abfragen](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="2370b-133">You also can use OData queries for queries filters, see [Using OData Queries](exposed-apis-odata-samples.md)</span></span>

## <a name="power-bi-dashboard-samples-in-github"></a><span data-ttu-id="2370b-134">Power BI-Dashboardbeispiele in GitHub</span><span class="sxs-lookup"><span data-stu-id="2370b-134">Power BI dashboard samples in GitHub</span></span>

<span data-ttu-id="2370b-135">Weitere Informationen finden Sie in den [Power BI Berichtsvorlagen.](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)</span><span class="sxs-lookup"><span data-stu-id="2370b-135">For more information see the [Power BI report templates](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).</span></span>

## <a name="sample-reports"></a><span data-ttu-id="2370b-136">Beispielberichte</span><span class="sxs-lookup"><span data-stu-id="2370b-136">Sample reports</span></span>

<span data-ttu-id="2370b-137">Sehen Sie sich die Microsoft Defender für Endpunkt-Power BI Berichtsbeispiele an.</span><span class="sxs-lookup"><span data-stu-id="2370b-137">View the Microsoft Defender for Endpoint Power BI report samples.</span></span> <span data-ttu-id="2370b-138">Weitere Informationen finden Sie unter [Durchsuchen von Codebeispielen.](/samples/browse/?products=mdatp)</span><span class="sxs-lookup"><span data-stu-id="2370b-138">For more information, see [Browse code samples](/samples/browse/?products=mdatp).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2370b-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2370b-139">Related topics</span></span>

- [<span data-ttu-id="2370b-140">Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="2370b-140">Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="2370b-141">Erweiterte Bedrohungssuche-API</span><span class="sxs-lookup"><span data-stu-id="2370b-141">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="2370b-142">Verwenden von OData-Abfragen</span><span class="sxs-lookup"><span data-stu-id="2370b-142">Using OData Queries</span></span>](exposed-apis-odata-samples.md)
