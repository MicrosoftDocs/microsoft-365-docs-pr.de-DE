---
title: Exportieren eines Berichts für die Inhaltssuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Anstatt die tatsächlichen Ergebnisse einer Inhaltssuche im Security & Compliance Center in Office 365 zu exportieren, können Sie einen Suchergebnisbericht exportieren. Der Bericht enthält eine Zusammenfassung der Suchergebnisse und ein Dokument mit detaillierten Informationen zu jedem Element, das exportiert werden würde.
ms.openlocfilehash: 6730a1c406e02de26cbef964e445cfad31c948ec
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074392"
---
# <a name="export-a-content-search-report"></a>Exportieren eines Berichts für die Inhaltssuche

Anstatt den vollständigen Satz von Suchergebnissen aus einer Inhaltssuche im Security & Compliance Center (und aus einer Inhaltssuche, die einem eDiscovery-Fall zugeordnet ist) zu exportieren, können Sie dieselben Berichte exportieren, die beim Exportieren der Suchergebnisse generiert werden.
  
Wenn Sie einen Bericht exportieren, wird er in einen Ordner mit dem gleichen Namen wie die Inhaltssuche heruntergeladen, dieser wird jedoch *_ReportsOnly*angefügt. Wenn die Inhaltssuche beispielsweise " *ContosoCase0815*" lautet, wird der Bericht in einen Ordner mit dem Namen " *ContosoCase0815_ReportsOnly*" heruntergeladen. Eine Liste der Dokumente, die im Bericht enthalten sind, finden Sie unter [What es included in the Report](#whats-included-in-the-report).

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Zum Exportieren eines Inhalts Suchberichts müssen Sie im Security & Compliance Center die Compliance Search-Verwaltungsrolle zugewiesen haben. Diese Rolle wird den integrierten eDiscovery-Manager-und Organisations Verwaltungsrollengruppen zugewiesen. Sie wird nicht standardmäßig der Rollengruppe "Organisationsverwaltung" zugewiesen. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).
    
- Wenn Sie einen Bericht exportieren, werden die Daten temporär in einem eindeutigen Azure-Speicherbereich in der Microsoft-Cloud gespeichert, bevor Sie auf Ihren lokalen Computer heruntergeladen werden. Stellen Sie sicher, dass Ihre Organisation eine Verbindung mit dem Endpunkt in Azure herstellen kann, also ** \*. BLOB.Core.Windows.net** (der Platzhalter stellt einen eindeutigen Bezeichner für den Export dar). Die Suchergebnis Daten werden zwei Wochen nach ihrer Erstellung aus dem Azure-Speicherbereich gelöscht. 
    
- Der Computer, den Sie zum Exportieren der Suchergebnisse verwenden, muss die folgenden Voraussetzungen erfüllen:
    
  - 32-Bit-oder 64-Bit-Versionen von Windows 7 und höheren Versionen
    
  - Microsoft .NET Framework 4,7
    
- Sie müssen einen der folgenden unterstützten Browser verwenden, um das eDiscovery-Export Tool<sup>1</sup>auszuführen:

  - Microsoft Edge <sup>2</sup>

    ODER

  - Microsoft Internet Explorer 10 und höhere Versionen

  > [!NOTE]
  > <sup>1</sup> Microsoft stellt keine Drittanbietererweiterungen oder Add-ons für ClickOnce-Anwendungen her. Das Exportieren von Suchergebnissen mit einem nicht unterstützten Browser mit Erweiterungen oder Add-ons von Drittanbietern wird nicht unterstützt.<br/>
  > <sup>2</sup> aufgrund der letzten Änderungen an Microsoft Edge ist die ClickOnce-Unterstützung standardmäßig nicht mehr aktiviert. Anweisungen zum Aktivieren der ClickOnce-Unterstützung in Edge finden Sie unter [Verwenden des Office 365 eDiscovery-Export Tools in Microsoft Edge](configure-edge-to-export-search-results.md).

- Wenn die geschätzte Gesamtgröße der Ergebnisse, die von einer Inhaltssuche zurückgegeben werden, 2 TB überschreitet, schlägt das Exportieren des Berichts fehl. Um den Bericht erfolgreich zu exportieren, versuchen Sie, den Bereich einzugrenzen, und führen Sie die Suche erneut aus, damit die geschätzte Größe der Ergebnisse weniger als 2 TB beträgt.

- Das Exportieren von Inhalts Suchberichten gilt für die maximale Anzahl von Exporten, die gleichzeitig ausgeführt werden, und für die maximale Anzahl von Exporten, die ein einzelner Benutzer ausführen kann. Weitere Informationen zu Exportbeschränkungen finden Sie unter [Exportieren von Inhalts Suchergebnissen](export-search-results.md#export-limits).

## <a name="generate-and-download-a-content-search-report"></a>Generieren und Herunterladen eines Inhalts Suchberichts

Die Schritte zum Generieren und Herunterladen eines Inhalts Suchberichts ähneln dem tatsächlichen Exportieren von Suchergebnissen.
  
## <a name="step-1-generate-the-report-for-export"></a>Schritt 1: Generieren des Berichts für den Export

Der erste Schritt besteht darin, den Bericht für den Download auf Ihrem Computer vorzubereiten, der exportiert. Wenn Sie den Bericht anzeigen, werden die Berichtsdokumente in einen Azure-Speicherbereich in der Microsoft-Cloud hochgeladen.
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto bei Office 365 an.
    
3. Klicken Sie im linken Bereich des Security & Compliance Centers auf **Such** \> **Inhaltssuche**.
    
4. Wählen Sie auf der Seite **Inhaltssuche** eine Suche aus. 
    
5. Klicken Sie im Detailbereich unter **Bericht auf einen Computer exportieren**auf **Bericht generieren**.
    
    > [!NOTE]
    > Wenn die Suchergebnisse älter als 7 Tage sind, werden Sie aufgefordert, die Suchergebnisse zu aktualisieren. Wenn dies geschieht, brechen Sie den Export ab, klicken Sie im Detailbereich für die ausgewählte Suche auf **Suchergebnisse aktualisieren** , und starten Sie dann den Berichtsexport erneut, nachdem die Ergebnisse aktualisiert wurden. 
  
6. Wählen Sie auf der Seite **Bericht exportieren** unter **diese Elemente aus der Suche einschließen**eine der folgenden Optionen aus:
    
    - Nur indizierte Elemente exportieren
    
    - Indizierte und nicht indizierte Elemente exportieren
    
    - Nur nicht indizierte Elemente exportieren
    
    Weitere Informationen zu nicht indizierten Elementen finden Sie unter [teilweise indizierte Elemente in der Inhaltssuche](partially-indexed-items-in-content-search.md).
    
7. Wählen Sie aus, um Suchstatistiken für alle Versionen von SharePoint-Dokumenten einzubeziehen. Diese Option wird nur angezeigt, wenn die Inhaltsquellen der Suche SharePoint-oder OneDrive für Unternehmen-Websites enthalten.
    
8. Klicken Sie auf **Bericht generieren**.
    
    Der Bericht "Suchergebnisse" wird zum Herunterladen vorbereitet, was bedeutet, dass die Berichtsdokumente in den Azure-Speicherbereich in der Microsoft-Cloud hochgeladen werden. Wenn der Bericht zum Download bereit ist, wird der Link **Bericht herunterladen** unter **Bericht auf einem Computer exportieren** im Detailbereich angezeigt. 
    
> [!NOTE]
> Sie können auch einen Bericht für eine Inhaltssuche exportieren, die einem eDiscovery-Fall zugeordnet ist. Wechseln Sie dazu zu **eDiscovery** \> **eDiscovery**, wählen Sie einen Fall aus, und klicken Sie auf Bearbeitungs](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)Symbol **Bearbeiten** ![. Wählen Sie **auf der Seite suchen eine** Suche aus, **und klicken Sie** ![dann auf Export exportieren](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> Suchergebnisse Symbol **Exportieren eines Berichts**. 
  
## <a name="step-2-download-the-report"></a>Schritt 2: Herunterladen des Berichts

Der nächste Schritt besteht darin, den Bericht aus dem Azure-Speicherbereich auf Ihren lokalen Computer herunterzuladen.
  
1. Klicken Sie im Detailbereich für die Suche, für die Sie den Bericht erstellt haben, unter **Bericht auf Computer exportieren**auf **Bericht herunterladen**.
    
    Die Seite **Bericht herunterladen** wird angezeigt und enthält die folgenden Informationen zu dem Bericht, der auf Ihren Computer heruntergeladen wird. 
    
    - Die Anzahl der Elemente, die heruntergeladen werden.
    
    - Die geschätzte Gesamtgröße der Elemente, die heruntergeladen werden sollen.
    
    - Ob indiziert oder nicht indiziert exportiert wird. Nicht indizierte Elemente sind Elemente, die ein erkanntes Format aufweisen, verschlüsselt sind oder aus anderen Gründen nicht indiziert wurden.
    
    - Gibt an, ob Versionen von SharePoint-Dokumenten heruntergeladen werden.
    
    - Der Status des Berichtsexport Prozesses. Sie können auch dann mit dem Herunterladen des Berichts beginnen, wenn die Vorbereitung des Berichts nicht abgeschlossen ist.
    
2. Klicken Sie unter **Schlüssel exportieren** auf **In Zwischenablage kopieren**. Sie verwenden diesen Schlüssel in Schritt 5, um den Bericht herunterzuladen.
    
    > [!IMPORTANT]
    > Da jeder Benutzer das eDiscovery-Export Tool installieren und starten und dann den Suchbericht mit diesem Schlüssel herunterladen kann, müssen Sie Vorkehrungen treffen, um diesen Schlüssel so zu schützen, wie Sie Kennwörter oder andere sicherheitsrelevante Informationen schützen. 
  
3. Klicken Sie auf **Bericht herunterladen**.
    
4. Wenn Sie aufgefordert werden, das **eDiscovery-Export Tool von Microsoft Office 365**zu installieren, klicken Sie auf **Installieren**.
    
5. Fügen Sie im **eDiscovery-Exporttool** den Export-Schlüssel, den Sie in Schritt 2 kopiert haben, in das entsprechende Feld ein.
    
6. Klicken Sie auf **Durchsuchen** , um den Speicherort anzugeben, an dem Sie den Bericht herunterladen möchten. 
    
7. Klicken Sie zum Herunterladen der Suchergebnisse auf Ihren Computer auf **Starten**. 
    
    Im **eDiscovery-Export Tool** werden Statusinformationen zum Exportprozess angezeigt, einschließlich einer Schätzung der Zahl (und der Größe) der restlichen Elemente, die heruntergeladen werden sollen. Wenn der Exportvorgang abgeschlossen ist, können Sie auf die Dateien an dem Speicherort zugreifen, an dem Sie heruntergeladen wurden. 
    
> [!NOTE]
> Sie können den Bericht für eine Inhaltssuche herunterladen, die einem eDiscovery-Fall zugeordnet ist. Wechseln Sie dazu zu **eDiscovery** \> **eDiscovery**, wählen Sie einen Fall aus, und klicken Sie auf Bearbeitungs](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)Symbol **Bearbeiten** ![. Wählen Sie auf der Seite **Exports** einen Berichtsexport aus, und klicken Sie dann im Detailbereich auf **Bericht herunterladen** . 
  
## <a name="whats-included-in-the-report"></a>Was ist im Bericht enthalten?

Wenn Sie einen Bericht zu den Ergebnissen einer Inhaltssuche generieren und exportieren, werden die folgenden Dokumente heruntergeladen:
  
- **Export Zusammenfassung:** Ein Excel-Dokument, das eine Zusammenfassung des Exports enthält. Dazu gehören Informationen wie die Anzahl der durchsuchten Inhaltsquellen, die Anzahl der Suchergebnisse von jedem Inhaltsspeicherort, die geschätzte Anzahl von Elementen, die tatsächliche Anzahl der exportierten Elemente sowie die geschätzte und tatsächliche Größe von Elementen. , die exportiert werden sollen. 
    
    > [!NOTE]
    > Wenn Sie nicht indizierte Elemente beim Exportieren des Berichts einschließen, wird die Anzahl der nicht indizierten Elemente in der Gesamtzahl der geschätzten Suchergebnisse und in der Gesamtzahl der heruntergeladenen Suchergebnisse (wenn Sie die Suchergebnisse exportieren), die in der Liste Export Zusammenfassungsbericht. Mit anderen Worten: die Gesamtzahl der heruntergeladenen Elemente entspricht der Gesamtzahl der geschätzten Ergebnisse und der Gesamtzahl der nicht indizierten Elemente. 
  
- **Manifest:** Eine Manifestdatei (im XML-Format), die Informationen zu jedem Element enthält, das in den Suchergebnissen enthalten ist. 
    
- **Ergebnisse:** Ein Excel-Dokument, das eine Zeile mit Informationen zu jedem indizierten Element enthält, das mit den Suchergebnissen exportiert werden würde. Bei e-Mails enthält das Ergebnisprotokoll Informationen zu den einzelnen Nachrichten, einschließlich: 
    
  - Der Speicherort der Nachricht im Quellpostfach (einschließlich der Angabe, ob die Nachricht sich im primären oder im Archivpostfach befindet).
    
  - Das Datum, an dem die Nachricht gesendet oder empfangen wurde.
    
  - Die Betreffzeile der Nachricht.
    
  - Absender und Empfänger der Nachricht.
    
    Bei Dokumenten aus SharePoint-und OneDrive für Unternehmen-Websites enthält das Ergebnisprotokoll Informationen zu den einzelnen Dokumenten, einschließlich:
    
  - Die URL für das Dokument.
    
  - Die URL für die Websitesammlung, in der sich das Dokument befindet.
    
  - Das Datum, an dem das Dokument zuletzt geändert wurde.
    
  - Der Name des Dokuments (der sich in der Spalte Betreff im Ergebnisprotokoll befindet).
    
    > [!NOTE]
    > Die Anzahl der Zeilen im **Ergebnis** Bericht sollte der Gesamtzahl der Suchergebnisse minus der Gesamtzahl der im Bericht nicht **Indexierte Elemente** aufgeführten Elemente entsprechen. 
  
- Nicht **indizierte Elemente:** Ein Excel-Dokument, das Informationen zu nicht indizierten Elementen enthält, die in den Suchergebnissen enthalten sind. Wenn Sie nicht indizierte Elemente beim Generieren des Berichts "Suchergebnisse" einschließen, wird dieser Bericht weiterhin heruntergeladen, wird jedoch leer sein.
