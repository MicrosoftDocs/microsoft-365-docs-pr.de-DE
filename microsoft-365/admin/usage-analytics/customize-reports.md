---
title: Individuelles Anpassen der Berichte in Microsoft 365-Nutzungsanalysen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
ms.openlocfilehash: 0ef2364c82318dfea93e8df4e64d53a66caa8d74
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580774"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Individuelles Anpassen der Berichte in Microsoft 365-Nutzungsanalysen

Microsoft 365 Verwendungsanalyse bietet ein Dashboard in Power BI, das Einblicke in die Einführung und Verwendung von Microsoft 365. Das Dashboard bildet lediglich einen Ausgangspunkt für die Interaktion mit den Nutzungsdaten. Die Berichte lassen sich zur Gewinnung stärker personalisierter Einblicke anpassen.
  
Ferner können Sie den Power BI-Desktop verwenden, um Ihre Berichte weiter anzupassen, indem Sie sie mit anderen Datenquellen verbinden, um umfassendere Einblicke in Ihr Unternehmen zu erhalten.
  
## <a name="customizing-reports-in-the-browser"></a>Anpassen von Berichten im Browser

Die beiden folgenden Beispiele zeigen, wie Sie vorhandene visuelle Elemente ändern und neue visuelle Elemente erstellen.
  
### <a name="modify-an-existing-visual"></a>Ändern eines vorhandenen visuellen Elements

In diesem Beispiel wird gezeigt, wie Sie die Registerkarte **Aktivierung** innerhalb des Berichts zur **Aktivierung/Lizenzierung** ändern. 
  
1. Wählen Sie **im Aktivierungs-/Lizenzierungsbericht** die Registerkarte **Aktivierung** aus.
    
2. Geben Sie den Bearbeitungsmodus ein, indem Sie die Schaltfläche Bearbeiten oben über die Schaltfläche Weitere Seite in Power BI  ![ ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) auswählen. 
    
    ![Klicken Sie auf "Bericht bearbeiten" in der oberen rechten Navigationsleiste](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. Klicken Sie oben rechts auf **Diese Seite duplizieren.**
    
    ![Wählen Sie "Diese Seite duplizieren" aus](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. Wählen Sie unten rechts eines der Balkendiagramme aus, in denen die Anzahl der Benutzer angezeigt wird, die basierend auf dem Betriebssystem wie Android, iOS, Mac usw. aktiviert werden.
    
5. Wählen Sie **im Bereich Visualisierungen** auf der rechten Seite das **X** neben dem Visuellen aus, um Die Anzahl der **Macs** zu entfernen.

    ![Entfernen der Mac-Anzahl](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a>Erstellen eines neuen visuellen Elements

Im folgenden Beispiel sehen Sie, wie Sie ein neues visuelles Element zum Nachverfolgen neuer Yammer-Benutzer auf Monatsbasis erstellen.
  
1. Wechseln Sie **mit** dem linken Navigationsgerät zum Bericht Produktverwendung, und wählen Sie **die Registerkarte Yammer** aus.
    
2. Wechseln Sie in den Bearbeitungsmodus, indem Sie die Schaltfläche Weitere Seite ![ in Power BI und Bearbeiten ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) **auswählen.** 
    
3. Wählen Sie unten auf der Seite die Option ![Die Schaltfläche "Seite hinzufügen" in Power BI,](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) um eine neue Seite zu erstellen.
  
4. Wählen Sie **im Bereich Visualisierungen** rechts das **Diagramm** gestapelter Balken (oberste Zeile, zuerst von links).

    ![Balkendiagramm auswählen](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. Wählen Sie die untere rechte Seite dieser Visualisierung aus, und ziehen Sie sie, um sie größer zu machen.

6. Erweitern Sie im Bereich **Felder** auf der rechten Seite die Tabelle **Kalender**.

7. Ziehen Sie **MonthName** (Monatsname) in den Bereich "Felder", direkt unterhalb der Überschrift **Achse** im Bereich **Visualisierungen**.
 
    ![Monatsname ziehen](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. Erweitern Sie im Bereich **Felder** auf der rechten Seite die Tabelle **TenantProductUsage** (MandantProduktVerwendung).

9. Ziehen Sie **FirstTimeUsers** (ErstmaligeBenutzer) auf den Bereich "Felder", direkt unterhalb der Überschrift **Wert**.

10. Ziehen Sie **Product** (Produkt) auf den Bereich **Filter**, unmittelbar unter die Überschrift **Filter auf visueller Ebene**.

11. Aktivieren Sie im Bereich **Filtertyp**, der dann angezeigt wird, das Kontrollkästchen **Yammer**.

    ![Kontrollkästchen "Yammer" aktivieren](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. Wählen Sie direkt unterhalb der Liste der Visualisierungen das Symbol **Formatsymbol** ![ Format in Power BI Visualizaions ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) aus.

13. Erweitern Sie "Titel", und ändern Sie den Wert **Titeltext** in **Yammer-Erstbenutzer nach Monat**.
    
14. Ändern Sie den Wert für **Textgröße** auf **12**.
    
15. Ändern Sie den Titel der neuen Seite, indem Sie den Namen der Seite unten rechts bearbeiten.

16.  Um den Bericht zu speichern, klicken Sie oben auf **Leseansicht** und dann auf **Speichern**.
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a>Anpassen der Berichte in Power BI Desktop

Für die meisten Kunden wird das Ändern der Berichte und visuellen Diagrammelemente in Power BI Web ausreichend sein. Für manche kann jedoch Bedarf bestehen, diese Daten mit anderen Datenquellen zusammenzuführen, um tiefer gehende Einblicke im Kontext des eigenen Unternehmens zu erlangen. Zu diesem Zweck können in Power BI Desktop Berichte angepasst und zusätzliche Berichte generiert werden. Sie können [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) kostenlos herunterladen. 
  
### <a name="use-the-reporting-apis"></a>Verwenden der APIs zur Berichterstellung

Sie können zunächst eine direkte Verbindung mit den ODATA-Berichts-APIs herstellen, Microsoft 365 diese Berichte verwenden.
  
1. Navigieren Sie zu **Daten abrufen** \> **Sonstige** \> **ODATA-Feed** \> **Verbinden**.
    
2. Geben Sie im Fenster URL "https:// <i></i> \<tenantid\> reports.office.com/pbi/v1.0/" ein.
    
    **HINWEIS:** Die APIs zur Berichterstellung befinden sich in einer Vorschauphase und unterliegen bis zum Beginn der Produktion noch Änderungen. 
  
    ![OData-Feed-URL für Power BI Desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. Geben Sie Microsoft 365 (Organisation oder Schule)-Administratoranmeldeinformationen ein, um sich bei Microsoft 365 zu authentifizieren, wenn Sie dazu aufgefordert werden.
    
    Weitere Informationen [dazu,](usage-analytics.md#faq) wer auf die App-Berichte der Microsoft 365 Adoptionsvorlage zugreifen darf, finden Sie in den häufig gestellten Fragen. 
    
4. Sobald die Verbindung autorisiert ist, wird das Navigationsfenster mit den für Verbindungen verfügbaren Datasets angezeigt.
    
    Wählen Sie alle aus, und wählen **Sie Laden aus.**
    
    Dadurch werden die Daten in Ihre Power BI Desktop-Instanz heruntergeladen. Speichern Sie diese Datei. Anschließend können Sie mit dem Erstellen der benötigten Berichte beginnen.
    
    ![In der Berichts-API verfügbare ODATA-Werte](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a>Verwenden der Vorlage für die Microsoft 365-Nutzungsanalyse

Sie können ferner die Power BI-Vorlagendatei, die den Berichten der Microsoft 365-Nutzungsanalyse entspricht, als Ausgangspunkt für die Datenverbindung verwenden. Der Vorteil bei der Verwendung der PBIT-Datei besteht darin, dass die Verbindungszeichenfolge darin bereits eingerichtet ist. Ferner können Sie über die vom Basisschema zurückgegebenen Daten hinaus alle erstellten benutzerdefinierten Measures nutzen und weiter auf ihnen aufbauen.
  
Sie können die Power BI-Vorlagendatei aus dem [Microsoft Download Center herunterladen.](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit) Nachdem Sie die Power BI-Vorlagendatei heruntergeladen haben, führen Sie die folgenden Schritte aus, um zu beginnen:
  
1. Öffnen Sie die PBIT-Datei.
    
2. Geben Sie im Dialogfeld den Wert für Ihre Mandanten-ID ein.
    
    ![Geben Sie die Mandanten-ID ein, um die pbit-Datei zu öffnen](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. Geben Sie Ihre Administratoranmeldeinformationen ein, um sich bei Microsoft 365 zu authentifizieren, wenn Sie dazu aufgefordert werden.
    
     Weitere Informationen zu den Personen, denen der Zugriff auf die Berichte der Microsoft 365-Nutzungsanalyse gestattet ist. 
    
    Nach der Autorisierung werden die Daten in der Power BI-Datei aktualisiert.
    
    Das Laden der Daten kann einige Zeit in Anspruch nehmen. Nach dem Abschluss können Sie die Datei als PBIX-Datei speichern und mit dem Anpassen der Berichte fortfahren oder eine zusätzliche Datenquelle in den Bericht einbringen.
    
4. Informationen zu den Grundlagen der Berichtsgenerierung, zu ihrer Veröffentlichung im Power BI-Dienst und zum Teilen mit Ihrer Organisation finden Sie in der Dokumentation [Erste Schritte mit Power BI](/power-bi/fundamentals/desktop-getting-started). Das Beschreiten dieses Wegs zum Anpassen und Teilen macht möglicherweise zusätzliche Power BI-Lizenzen erforderlich. Details dazu finden Sie im Power BI-[Lizenzierungsleitfaden](https://go.microsoft.com/fwlink/p/?linkid=849803). 
