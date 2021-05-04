---
title: Exportieren eines Berichts für die Inhaltssuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
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
description: Anstatt die tatsächlichen Ergebnisse einer Inhaltssuche im Security & Compliance Center in Office 365 zu exportieren, können Sie einen Suchergebnisseinbericht exportieren. Der Bericht enthält eine Zusammenfassung der Suchergebnisse und ein Dokument mit detaillierten Informationen zu jedem element, das exportiert werden würde.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fec6e441458ad7429067a1314a7aec3824aff11a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760153"
---
# <a name="export-a-content-search-report"></a>Exportieren eines Berichts für die Inhaltssuche

Anstatt den vollständigen Satz von Suchergebnissen aus einer Inhaltssuche im Security & Compliance Center (und aus einer Inhaltssuche, die einem eDiscovery-Fall zugeordnet ist) zu exportieren, können Sie dieselben Berichte exportieren, die beim Exportieren von Suchergebnissen generiert werden.
  
Wenn Sie einen Bericht exportieren, wird er in einen Ordner heruntergeladen, der denselben Namen wie die Inhaltssuche hat, der jedoch mit *_ReportsOnly.* Wenn die Inhaltssuche beispielsweise den Namen  *ContosoCase0815* hat, wird der Bericht in einen Ordner mit dem Namen *ContosoCase0815_ReportsOnly*. Eine Liste der Dokumente, die im Bericht enthalten sind, finden Sie unter [What's included in the report](#whats-included-in-the-report).

## <a name="assign-roles-and-check-system-requirements"></a>Zuweisen von Rollen und Überprüfen von Systemanforderungen

- Zum Exportieren eines Inhaltssuchberichts muss Ihnen die Verwaltungsrolle Compliancesuche im Security & Compliance Center zugewiesen werden. Diese Rolle wird standardmäßig den integrierten Rollengruppen eDiscovery Manager und Organization Management zugewiesen. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).

- Wenn Sie einen Bericht exportieren, werden die Daten vorübergehend in einem eindeutigen Azure Storage in der Microsoft Cloud gespeichert, bevor sie auf Ihren lokalen Computer heruntergeladen werden. Stellen Sie sicher, dass Ihre Organisation eine Verbindung mit dem Endpunkt in Azure herstellen kann, der **\* .blob.core.windows.net** ist (der Platzhalter stellt einen eindeutigen Bezeichner für Ihren Export dar). Die Suchergebnisse werden zwei Wochen nach der Azure Storage aus dem Bereich gelöscht.

- Der Computer, den Sie zum Exportieren der Suchergebnisse verwenden, muss die folgenden Voraussetzungen erfüllen:

  - Neueste Version von Windows (32-Bit- oder 64-Bit-Version)

  - Microsoft .NET Framework 4.7

- Sie müssen einen der folgenden unterstützten Browser verwenden, um das eDiscovery Export Tool<sup>1 ausführen zu können:</sup>

  - Microsoft Edge <sup>2</sup>

    ODER

  - Microsoft Internet Explorer 10 und höher

  > [!NOTE]
  > <sup>1</sup> Microsoft stellt keine Erweiterungen oder Add-Ons von Drittanbietern für ClickOnce her. Das Exportieren von Suchergebnissen mithilfe eines nicht unterstützten Browsers mit Drittanbietererweiterungen oder -add-ons wird nicht unterstützt.<br/>
  > <sup>2</sup> Als Ergebnis der letzten Änderungen an Microsoft Edge ist ClickOnce unterstützung standardmäßig nicht mehr aktiviert. Anweisungen zum Aktivieren ClickOnce in Edge finden Sie unter [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).

- Wenn die geschätzte Gesamtgröße der von einer Inhaltssuche zurückgegebenen Ergebnisse 2 TB überschreitet, schlägt das Exportieren des Berichts fehl. Um den Bericht erfolgreich zu exportieren, versuchen Sie, den Bereich zu einenten, und führen Sie die Suche erneut aus, sodass die geschätzte Größe der Ergebnisse kleiner als 2 TB ist.

- Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run. Weitere Informationen zu Exportbeschränkungen finden Sie [unter Exportieren von Inhaltssuchergebnissen](export-search-results.md#export-limits).

## <a name="generate-and-download-a-content-search-report"></a>Generieren und Herunterladen eines Inhaltssuchberichts

Die Schritte zum Generieren und Herunterladen eines Inhaltssuchberichts ähneln dem tatsächlichen Exportieren von Suchergebnissen.
  
## <a name="step-1-generate-the-report-for-export"></a>Schritt 1: Generieren des Berichts für den Export

Der erste Schritt besteht in der Vorbereitung des Berichts für das Herunterladen auf Ihren Computer, der exportiert wird. Wenn Sie den Bericht erstellen, werden die Berichtsdokumente in einen Azure Storage in der Microsoft Cloud hochgeladen.
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an.
    
3. Klicken Sie im linken Bereich des Security & Compliance Center auf **Inhaltssuche** \> **durchsuchen.**
    
4. Wählen Sie **auf der Seite Inhaltssuche** eine Suche aus. 
    
5. Klicken Sie im Detailbereich unter **Bericht auf einen Computer** exportieren auf Bericht **generieren**.
    
    > [!NOTE]
    > Wenn die Suchergebnisse älter als 7 Tage sind, werden Sie aufgefordert, die Suchergebnisse zu aktualisieren. Brechen Sie in diesem Fall  den Export ab, klicken Sie im Detailbereich für die ausgewählte Suche auf Suchergebnisse aktualisieren, und starten Sie den Berichtsexport erneut, nachdem die Ergebnisse aktualisiert wurden. 
  
6. Wählen Sie **auf der Seite** Bericht exportieren unter Diese Elemente **aus** der Suche hinzufügen eine der folgenden Optionen aus:
    
    - Nur indizierte Elemente exportieren
    
    - Indizierte und nicht indizierte Elemente exportieren
    
    - Nur nicht indizierte Elemente exportieren
    
    Weitere Informationen zu nicht indizierten Elementen finden Sie unter [Teilweise indizierte Elemente in der Inhaltssuche](partially-indexed-items-in-content-search.md).
    
7. Wählen Sie, ob Suchstatistiken für alle Versionen von Dokumenten SharePoint werden. Diese Option wird nur angezeigt, wenn die Inhaltsquellen der Suche SharePoint oder OneDrive for Business enthalten.
    
8. Klicken Sie **auf Bericht generieren**.
    
    Der Suchergebnissetbericht wird zum Herunterladen vorbereitet, d. h. die Berichtsdokumente werden in den Azure Storage in der Microsoft Cloud hochgeladen. Wenn der Bericht zum Herunterladen bereit ist, wird der **Link Bericht** herunterladen unter **Bericht auf** einen Computer exportieren im Detailbereich angezeigt. 
    
> [!NOTE]
> Sie können auch einen Bericht für eine Inhaltssuche exportieren, die einem eDiscovery-Fall zugeordnet ist. Wechseln Sie dazu zu **eDiscovery** \> **eDiscovery,** wählen Sie einen Fall aus, und klicken Sie auf **Bearbeiten** ![ (Symbol). ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) Wählen Sie **auf der Seite** Suchen eine  Suche aus, und klicken Sie dann auf Suchergebnisse exportieren Symbol ![ Bericht ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **exportieren**. 
  
## <a name="step-2-download-the-report"></a>Schritt 2: Herunterladen des Berichts

Im nächsten Schritt laden Sie den Bericht aus dem Azure Storage auf Ihren lokalen Computer herunter.
  
1. Klicken Sie im Detailbereich für die Suche, für die Sie den Bericht generiert haben, unter **Bericht auf** einen Computer exportieren auf **Bericht herunterladen.**
    
    Die **Seite Bericht herunterladen** wird angezeigt und enthält die folgenden Informationen zu dem Bericht, der auf Ihren Computer heruntergeladen wird. 
    
    - Die Anzahl der Elemente, die heruntergeladen werden.
    
    - Die geschätzte Gesamtgröße der Elemente, die heruntergeladen werden.
    
    - Gibt an, ob indiziert oder nicht indiziert exportiert wird. Nicht indizierte Elemente sind Elemente, die ein erkanntes Format haben, verschlüsselt sind oder aus anderen Gründen nicht indiziert wurden.
    
    - Gibt an, SharePoint Versionen von Dokumenten heruntergeladen werden.
    
    - Der Status des Berichtsexportprozesses. Sie können mit dem Herunterladen des Berichts beginnen, auch wenn die Vorbereitung des Berichts noch nicht abgeschlossen ist.
    
2. Klicken Sie unter **Schlüssel exportieren** auf **In Zwischenablage kopieren**. Sie verwenden diesen Schlüssel in Schritt 5, um den Bericht herunterzuladen.
    
    > [!IMPORTANT]
    > Da jeder benutzer das eDiscovery-Export-Tool installieren und starten kann und diesen Schlüssel dann zum Herunterladen des Suchberichts verwenden kann, sollten Sie Vorkehrungen treffen, um diesen Schlüssel so zu schützen, wie Sie Kennwörter oder andere sicherheitsrelevante Informationen schützen würden. 
  
3. Klicken **Sie auf Bericht herunterladen**.
    
4. Wenn Sie aufgefordert werden, das **eDiscovery-Exporttool zu** installieren, klicken Sie auf **Installieren**.
    
5. Fügen Sie im **eDiscovery-Exporttool** den Export-Schlüssel, den Sie in Schritt 2 kopiert haben, in das entsprechende Feld ein.
    
6. Klicken **Sie auf Durchsuchen,** um den Speicherort anzugeben, an dem Sie den Bericht herunterladen möchten. 
    
7. Klicken Sie zum Herunterladen der Suchergebnisse auf Ihren Computer auf **Starten**. 
    
    Das **eDiscovery-Exporttool** zeigt Statusinformationen zum Exportvorgang an, einschließlich einer Schätzung der Anzahl (und Größe) der verbleibenden Elemente, die heruntergeladen werden sollen. Wenn der Exportvorgang abgeschlossen ist, können Sie auf die Dateien am Speicherort zugreifen, an dem sie heruntergeladen wurden. 
    
> [!NOTE]
> Sie können den Bericht für eine Inhaltssuche herunterladen, die einem eDiscovery-Fall zugeordnet ist. Wechseln Sie dazu zu **eDiscovery** \> **eDiscovery,** wählen Sie einen Fall aus, und klicken Sie auf **Bearbeiten** ![ (Symbol). ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) Wählen Sie **auf der** Seite Exporte einen  Berichtsexport aus, und klicken Sie dann im Detailbereich auf Bericht herunterladen. 
  
## <a name="whats-included-in-the-report"></a>Was im Bericht enthalten ist

Wenn Sie einen Bericht über die Ergebnisse einer Inhaltssuche generieren und exportieren, werden die folgenden Dokumente heruntergeladen:
  
- **Exportzusammenfassung:** Ein Excel, das eine Zusammenfassung des Exports enthält. Dazu gehören Informationen wie die Anzahl der durchsuchten Inhaltsquellen, die Anzahl der Suchergebnisse aus den einzelnen Inhaltsspeicherorten, die geschätzte Anzahl der Elemente, die tatsächliche Anzahl der exportierten Elemente und die geschätzte und tatsächliche Größe der exportierten Elemente. 
    
    > [!NOTE]
    > Wenn Sie beim Exportieren des Berichts nicht indizierte Elemente enthalten, wird die Anzahl der nicht indizierten Elemente in der Gesamtanzahl der geschätzten Suchergebnisse und in der Gesamtzahl der heruntergeladenen Suchergebnisse (wenn Sie die Suchergebnisse exportieren sollten) enthalten, die im Bericht "Zusammenfassung exportieren" aufgeführt sind. Anders ausgedrückt: Die Gesamtanzahl der heruntergeladenen Elemente entspricht der Gesamtzahl der geschätzten Ergebnisse und der Gesamtzahl der nicht indizierten Elemente. 
  
- **Manifest:** Eine Manifestdatei (im XML-Format), die Informationen zu jedem Element enthält, das in den Suchergebnissen enthalten ist. 
    
- **Ergebnisse:** Ein Excel, das eine Zeile mit Informationen zu jedem indizierten Element enthält, das mit den Suchergebnissen exportiert würde. Für E-Mails enthält das Ergebnisprotokoll Informationen zu jeder Nachricht, einschließlich: 
    
  - Der Speicherort der Nachricht im Quellpostfach (einschließlich der Angabe, ob die Nachricht sich im primären oder im Archivpostfach befindet).
    
  - Das Datum, an dem die Nachricht gesendet oder empfangen wurde.
    
  - Die Betreffzeile der Nachricht.
    
  - Absender und Empfänger der Nachricht.
    
    Für Dokumente von SharePoint und OneDrive for Business enthält das Ergebnisprotokoll Informationen zu jedem Dokument, einschließlich:
    
  - Die URL für das Dokument.
    
  - Die URL für die Websitesammlung, in der sich das Dokument befindet.
    
  - Das Datum, an dem das Dokument zuletzt geändert wurde.
    
  - Der Name des Dokuments (das sich in der Spalte Betreff im Ergebnisprotokoll befindet).
    
    > [!NOTE]
    > Die Anzahl der Zeilen im **Ergebnisbericht** sollte gleich der Gesamtzahl der Suchergebnisse minus der Gesamtzahl der im Bericht **Nicht indizierte Elemente aufgeführten Elemente** sein. 
  
- **Nicht indizierte Elemente:** Ein Excel, das Informationen zu nicht indizierten Elementen enthält, die in den Suchergebnissen enthalten sind. Wenn Sie beim Generieren des Suchergebnissesberichts keine nicht indizierten Elemente verwenden, wird dieser Bericht weiterhin heruntergeladen, ist jedoch leer.
