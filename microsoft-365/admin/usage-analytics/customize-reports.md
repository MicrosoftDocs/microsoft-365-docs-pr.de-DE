---
title: Individuelles Anpassen der Berichte in Microsoft 365-Nutzungsanalysen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Erfahren Sie, wie Sie Berichte im Browser und in Power BI Desktop anpassen können.
ms.openlocfilehash: 121a9be4a83570b7fcf358c48bf558d3bc7c1131
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402930"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="77d3c-103">Individuelles Anpassen der Berichte in Microsoft 365-Nutzungsanalysen</span><span class="sxs-lookup"><span data-stu-id="77d3c-103">Customize the reports in Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="77d3c-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="77d3c-104">The admin center is changing.</span></span> <span data-ttu-id="77d3c-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="77d3c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="77d3c-106">Microsoft 365 Usage Analytics bietet ein Dashboard in Power BI, das Einblicke in die Einführung und Verwendung von Microsoft 365 durch Benutzer bietet.</span><span class="sxs-lookup"><span data-stu-id="77d3c-106">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="77d3c-107">Das Dashboard bildet lediglich einen Ausgangspunkt für die Interaktion mit den Nutzungsdaten.</span><span class="sxs-lookup"><span data-stu-id="77d3c-107">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="77d3c-108">Die Berichte lassen sich zur Gewinnung stärker personalisierter Einblicke anpassen.</span><span class="sxs-lookup"><span data-stu-id="77d3c-108">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="77d3c-109">Ferner können Sie den Power BI-Desktop verwenden, um Ihre Berichte weiter anzupassen, indem Sie sie mit anderen Datenquellen verbinden, um umfassendere Einblicke in Ihr Unternehmen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="77d3c-109">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="77d3c-110">Anpassen von Berichten im Browser</span><span class="sxs-lookup"><span data-stu-id="77d3c-110">Customizing reports in the browser</span></span>

<span data-ttu-id="77d3c-111">Die beiden folgenden Beispiele zeigen, wie Sie vorhandene visuelle Elemente ändern und neue visuelle Elemente erstellen.</span><span class="sxs-lookup"><span data-stu-id="77d3c-111">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="77d3c-112">Ändern eines vorhandenen visuellen Elements</span><span class="sxs-lookup"><span data-stu-id="77d3c-112">Modify an existing visual</span></span>

<span data-ttu-id="77d3c-113">In diesem Beispiel wird gezeigt, wie Sie die Registerkarte **Aktivierung** innerhalb des Berichts zur **Aktivierung/Lizenzierung** ändern.</span><span class="sxs-lookup"><span data-stu-id="77d3c-113">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="77d3c-114">Klicken Sie im Bericht **Aktivierung/Lizenzierung** auf die Registerkarte **Aktivierung**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-114">Within the **Activation/Licensing** report, click on the **Activation** tab.</span></span>
    
2. <span data-ttu-id="77d3c-115">Wechseln Sie in den Bearbeitungsmodus, indem Sie oben auf die Schaltfläche **Bearbeiten** der Schaltfläche ![Die Schaltfläche "Seite hinzufügen" in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="77d3c-115">Enter the edit mode by clicking the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Klicken Sie auf "Bericht bearbeiten" in der oberen rechten Navigationsleiste](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="77d3c-117">Klicken Sie oben rechts auf **Diese Seite duplizieren**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-117">On the top right, click **Duplicate this page**.</span></span>
    
    ![Wählen Sie "Diese Seite duplizieren" aus](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="77d3c-119">Klicken Sie unten rechts auf eines der Balkendiagramme, in dem die Anzahl der Benutzer angezeigt wird, die basierend auf Betriebssystemen wie Android, iOS, Mac usw. eine Aktivierung vornehmen.</span><span class="sxs-lookup"><span data-stu-id="77d3c-119">In the bottom right, click on any of the bar charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="77d3c-120">Klicken Sie im Bereich **Visualisierungen** auf der rechten Seite, um die **Mac-Anzahl** aus dem visuellen Element zu entfernen, auf das **X** daneben.</span><span class="sxs-lookup"><span data-stu-id="77d3c-120">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, click on the **X** next to it.</span></span>

    ![Entfernen der Mac-Anzahl](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="77d3c-122">Erstellen eines neuen visuellen Elements</span><span class="sxs-lookup"><span data-stu-id="77d3c-122">Create a new visual</span></span>

<span data-ttu-id="77d3c-123">Im folgenden Beispiel sehen Sie, wie Sie ein neues visuelles Element zum Nachverfolgen neuer Yammer-Benutzer auf Monatsbasis erstellen.</span><span class="sxs-lookup"><span data-stu-id="77d3c-123">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="77d3c-124">Wechseln Sie mit der linken Navigationsleiste zum Bericht **Produktnutzung**, und klicken Sie auf die Registerkarte **Yammer**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-124">Go to the **Product Usage** report using the left nav and click on **Yammer** tab.</span></span>
    
2. <span data-ttu-id="77d3c-125">Wechseln Sie in den Bearbeitungsmodus, indem Sie auf ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png)Die Schaltfläche "Seite hinzufügen" in Power BI![ und **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="77d3c-125">Switch to edit mode by clicking on ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="77d3c-126">Klicken Sie am unteren Rand der Seite auf </span><span class="sxs-lookup"><span data-stu-id="77d3c-126">At the bottom of the page, click on</span></span> ![Die Schaltfläche "Seite hinzufügen" in Power BI,](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="77d3c-128">um eine neue Seite zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="77d3c-128">to create a new page.</span></span>
  
4. <span data-ttu-id="77d3c-129">Klicken Sie im Bereich **Visualisierungen** auf der rechten Seite auf **Gestapeltes Balkendiagramm** (obere Zeile, erstes Element von links).</span><span class="sxs-lookup"><span data-stu-id="77d3c-129">In the **Visualizations** area to the right, click the **Stacked bar chart** (top row, first from left).</span></span>

    ![Balkendiagramm auswählen](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="77d3c-131">Klicken Sie auf die untere rechte Ecke dieser Visualisierung, und ziehen Sie, um sie zu vergrößern.</span><span class="sxs-lookup"><span data-stu-id="77d3c-131">Click the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="77d3c-132">Erweitern Sie im Bereich **Felder** auf der rechten Seite die Tabelle **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-132">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="77d3c-133">Ziehen Sie **MonthName** (Monatsname) in den Bereich "Felder", direkt unterhalb der Überschrift **Achse** im Bereich **Visualisierungen**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-133">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Monatsname ziehen](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="77d3c-135">Erweitern Sie im Bereich **Felder** auf der rechten Seite die Tabelle **TenantProductUsage** (MandantProduktVerwendung).</span><span class="sxs-lookup"><span data-stu-id="77d3c-135">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="77d3c-136">Ziehen Sie **FirstTimeUsers** (ErstmaligeBenutzer) auf den Bereich "Felder", direkt unterhalb der Überschrift **Wert**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-136">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="77d3c-137">Ziehen Sie **Product** (Produkt) auf den Bereich **Filter**, unmittelbar unter die Überschrift **Filter auf visueller Ebene**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-137">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="77d3c-138">Aktivieren Sie im Bereich **Filtertyp**, der dann angezeigt wird, das Kontrollkästchen **Yammer**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-138">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Kontrollkästchen "Yammer" aktivieren](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="77d3c-140">Klicken Sie unmittelbar unterhalb der Liste der Visualisierungen auf das Symbol **Format** ![Symbol "Format" in Power BI-Visualisierungen](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span><span class="sxs-lookup"><span data-stu-id="77d3c-140">Just below the list of visualizations, click the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="77d3c-141">Erweitern Sie "Titel", und ändern Sie den Wert **Titeltext** in **Yammer-Erstbenutzer nach Monat**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-141">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="77d3c-142">Ändern Sie den Wert für **Textgröße** auf **12**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-142">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="77d3c-143">Ändern Sie den Titel der neuen Seite, indem Sie den Namen der Seite unten rechts bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="77d3c-143">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="77d3c-144">Um den Bericht zu speichern, klicken Sie oben auf **Leseansicht** und dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-144">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="77d3c-145">Anpassen der Berichte in Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="77d3c-145">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="77d3c-p103">Für die meisten Kunden wird das Ändern der Berichte und visuellen Diagrammelemente in Power BI Web ausreichend sein. Für manche kann jedoch Bedarf bestehen, diese Daten mit anderen Datenquellen zusammenzuführen, um tiefer gehende Einblicke im Kontext des eigenen Unternehmens zu erlangen. Zu diesem Zweck können in Power BI Desktop Berichte angepasst und zusätzliche Berichte generiert werden. Sie können [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) kostenlos herunterladen.</span><span class="sxs-lookup"><span data-stu-id="77d3c-p103">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="77d3c-149">Verwenden der APIs zur Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="77d3c-149">Use the reporting APIs</span></span>

<span data-ttu-id="77d3c-150">Sie können zunächst eine direkte Verbindung mit den ODATA-Berichts-APIs von Microsoft 365 herstellen, mit denen diese Berichte versorgt werden.</span><span class="sxs-lookup"><span data-stu-id="77d3c-150">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="77d3c-151">Navigieren Sie zu **Daten abrufen** \> **Sonstige** \> **ODATA-Feed** \> **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-151">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="77d3c-152">Geben Sie im Fenster URL "https:// <i></i> Reports.Office.com/PBI/v1.0/ \<tenantid\> " ein.</span><span class="sxs-lookup"><span data-stu-id="77d3c-152">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="77d3c-153">**HINWEIS:** Die APIs zur Berichterstellung befinden sich in einer Vorschauphase und unterliegen bis zum Beginn der Produktion noch Änderungen.</span><span class="sxs-lookup"><span data-stu-id="77d3c-153">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData-Feed-URL für Power BI Desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="77d3c-155">Geben Sie Ihre Microsoft 365 (Organization oder School) Administratoranmeldeinformationen zur Authentifizierung bei Microsoft 365 ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="77d3c-155">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="77d3c-156">In den [FAQ](usage-analytics.md#faq) finden Sie weitere Informationen darüber, wer auf die Microsoft 365 Adoptions Vorlagen-APP-Berichte zugreifen darf.</span><span class="sxs-lookup"><span data-stu-id="77d3c-156">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="77d3c-157">Sobald die Verbindung autorisiert ist, wird das Navigationsfenster mit den für Verbindungen verfügbaren Datasets angezeigt.</span><span class="sxs-lookup"><span data-stu-id="77d3c-157">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="77d3c-158">Wählen Sie alle aus, und klicken Sie auf **Laden**.</span><span class="sxs-lookup"><span data-stu-id="77d3c-158">Select all and click on **Load**.</span></span>
    
    <span data-ttu-id="77d3c-p104">Dadurch werden die Daten in Ihre Power BI Desktop-Instanz heruntergeladen. Speichern Sie diese Datei. Anschließend können Sie mit dem Erstellen der benötigten Berichte beginnen.</span><span class="sxs-lookup"><span data-stu-id="77d3c-p104">This will download the data into your Power BI Desktop. Save this file and then you can start creating the reports you need.</span></span>
    
    ![In der Berichts-API verfügbare ODATA-Werte](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="77d3c-162">Verwenden der Vorlage für die Microsoft 365-Nutzungsanalyse</span><span class="sxs-lookup"><span data-stu-id="77d3c-162">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="77d3c-163">Sie können ferner die Power BI-Vorlagendatei, die den Berichten der Microsoft 365-Nutzungsanalyse entspricht, als Ausgangspunkt für die Datenverbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="77d3c-163">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="77d3c-164">Der Vorteil bei der Verwendung der PBIT-Datei besteht darin, dass die Verbindungszeichenfolge darin bereits eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="77d3c-164">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="77d3c-165">Ferner können Sie über die vom Basisschema zurückgegebenen Daten hinaus alle erstellten benutzerdefinierten Measures nutzen und weiter auf ihnen aufbauen.</span><span class="sxs-lookup"><span data-stu-id="77d3c-165">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="77d3c-166">Sie können die Power BI-Vorlagendatei im Microsoft [Download Center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="77d3c-166">You can download the Power BI template file from the Microsoft download center from the [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="77d3c-167">Führen Sie nach dem Herunterladen der Power BI-Vorlagendatei diese Schritte zum Einstieg aus:</span><span class="sxs-lookup"><span data-stu-id="77d3c-167">After you have downloaded the Power BI template file follow these steps to get started:</span></span>
  
1. <span data-ttu-id="77d3c-168">Öffnen Sie die PBIT-Datei.</span><span class="sxs-lookup"><span data-stu-id="77d3c-168">Open the pbit file.</span></span>
    
2. <span data-ttu-id="77d3c-169">Geben Sie im Dialogfeld den Wert für Ihre Mandanten-ID ein.</span><span class="sxs-lookup"><span data-stu-id="77d3c-169">Enter your tenant id value in the dialog.</span></span>
    
    ![Geben Sie die Mandanten-ID ein, um die pbit-Datei zu öffnen](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="77d3c-171">Geben Sie Ihre Administratoranmeldeinformationen für die Authentifizierung bei Microsoft 365 ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="77d3c-171">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="77d3c-172">Weitere Informationen zu den Personen, denen der Zugriff auf die Berichte der Microsoft 365-Nutzungsanalyse gestattet ist.</span><span class="sxs-lookup"><span data-stu-id="77d3c-172">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="77d3c-173">Nach der Autorisierung werden die Daten in der Power BI-Datei aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="77d3c-173">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="77d3c-174">Das Laden der Daten kann einige Zeit in Anspruch nehmen. Nach dem Abschluss können Sie die Datei als PBIX-Datei speichern und mit dem Anpassen der Berichte fortfahren oder eine zusätzliche Datenquelle in den Bericht einbringen.</span><span class="sxs-lookup"><span data-stu-id="77d3c-174">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="77d3c-p107">Informationen zu den Grundlagen der Berichtsgenerierung, zu ihrer Veröffentlichung im Power BI-Dienst und zum Teilen mit Ihrer Organisation finden Sie in der Dokumentation [Erste Schritte mit Power BI](https://go.microsoft.com/fwlink/?linkid=849802). Das Beschreiten dieses Wegs zum Anpassen und Teilen macht möglicherweise zusätzliche Power BI-Lizenzen erforderlich. Details dazu finden Sie im Power BI-[Lizenzierungsleitfaden](https://go.microsoft.com/fwlink/p/?linkid=849803).</span><span class="sxs-lookup"><span data-stu-id="77d3c-p107">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

