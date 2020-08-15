---
title: Verwenden des Seiten Diagnosetools für SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/03/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPO160
- MOE150
- BSA160
f1.keywords:
- NOCSH
description: Verwenden Sie das Seiten Diagnosetool für SharePoint, um SharePoint Online modernen Portal-und klassischen Veröffentlichungsseiten anhand einer vordefinierten Reihe von Leistungskriterien zu analysieren.
ms.openlocfilehash: 2598f2a8c7801a762133c93761d2910a220dc194
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695979"
---
# <a name="use-the-page-diagnostics-for-sharepoint-tool"></a>Verwenden der Seite Diagnostics für SharePoint-Tool

In diesem Artikel wird beschrieben, wie Sie mit dem **Tool Page Diagnostics for SharePoint** SharePoint Online modernen und klassischen Website Seiten anhand einer vordefinierten Reihe von Leistungskriterien analysieren.

Das Page Diagnostics für SharePoint-Tool kann installiert werden für:

- **Microsoft Edge** [(Edge-Erweiterung)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)
- **Chrome** [(Chrome-Erweiterung)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)

>[!TIP]
>Version **2.0.0** und höher umfasst neben klassischen Website Seiten auch Unterstützung für moderne Seiten. Wenn Sie sich nicht sicher sind, welche Version des Tools Sie verwenden, können Sie den Link **Info** oder die Ellipsen (...) auswählen, um Ihre Version zu überprüfen. **Aktualisieren Sie immer auf die neueste Version, wenn Sie** das Tool verwenden.

Das Tool "Seitendiagnose für SharePoint" ist eine Browsererweiterung für den neuen Microsoft Edge (https://www.microsoft.com/edge) und Chrome, mit denen Sie SharePoint Online-Seiten sowohl in modernen Portal- als auch in klassischen Veröffentlichungs-Websites analysieren können. Dieses Tool funktioniert nur für SharePoint Online und kann nicht auf einer SharePoint-System Seite verwendet werden.

Das Tool generiert einen Bericht für jede analysierte Seite, die zeigt, wie die Seite mit einem vordefinierten Satz von Regeln ausgeführt wird, und zeigt ausführliche Informationen an, wenn Ergebnisse für einen Test außerhalb des Basiswerts liegen. SharePoint Online Administratoren und Designer können das Tool verwenden, um Leistungsprobleme zu beheben und sicherzustellen, dass neue Seiten vor der Veröffentlichung optimiert werden.

Das Seiten Diagnosetool dient ausschließlich zum Analysieren von SharePoint-Website Seiten und nicht von System Seiten wie *AllItems. aspx* oder *SharePoint. aspx*. Wenn Sie versuchen, das Tool auf einer System Seite oder einer anderen Seite ohne Website auszuführen, erhalten Sie eine Fehlermeldung, in der Sie darauf hingewiesen werden, dass das Tool für diese Art von Seite nicht ausgeführt werden kann.

![Muss auf einer SharePoint-Seite ausgeführt werden](../media/page-diagnostics-for-spo/pagediag-Error-StartPage.png)

Dies ist kein Fehler im Tool, da es keinen Wert für die Bewertung von Bibliotheken oder System Seiten gibt. Navigieren Sie zu einer SharePoint-Website Seite, um das Tool zu verwenden. Wenn dieser Fehler auf einer SharePoint-Seite auftritt, überprüfen Sie die Gestaltungsvorlage, um sicherzustellen, dass die SharePoint-Metatags nicht entfernt wurden.

Um Feedback zu dem Tool zu erhalten, wählen Sie die Auslassungspunkte in der oberen rechten Ecke des Tools aus, und wählen Sie dann [Feedback geben](https://go.microsoft.com/fwlink/?linkid=874109)aus.

![Feedback geben](../media/page-diagnostics-for-spo/pagediag-feedback.png)
  
## <a name="install-the-page-diagnostics-for-sharepoint-tool"></a>Installieren der Seite Diagnostics für SharePoint-Tool

Das Installationsverfahren in diesem Abschnitt ist sowohl für die Chrome-als auch für die Microsoft-Edge-Browser funktionsfähig.

> [!IMPORTANT]
> Microsoft liest keine Daten oder Seiteninhalte, die vom Seiten Diagnosetool für SharePoint analysiert werden, und wir erfassen keine persönlichen Informationen, Website-oder Download Informationen. Die einzigen identifizierbaren Informationen, die von dem Tool bei Microsoft protokolliert werden, sind der Name des Mandanten, die Anzahl der fehlerhaften Regeln und das Datum und die Uhrzeit, zu der das Tool ausgeführt wurde. Diese Informationen werden von Microsoft verwendet, um moderne Portal-und Veröffentlichungs Nutzungstrends und Allgemeine Leistungsprobleme besser zu verstehen.

1. Installieren Sie die Seite Diagnostics für SharePoint-Tool für **Microsoft Edge** [(Edge Extension)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji) oder **Chrome** [(Chrome Extension)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi). Lesen Sie die Datenschutzrichtlinie für Benutzer, die auf der Seite Beschreibung im Store bereitgestellt wird. Wenn Sie das Tool Ihrem Browser hinzufügen, wird der folgende Berechtigungshinweis angezeigt.

    ![Erweiterungs Berechtigungen](../media/page-diagnostics-for-spo/pagediag-add-to-edge.png)

    Dieser Hinweis ist vorhanden, da eine Seite Inhalte von Speicherorten außerhalb von SharePoint abhängig von den Webparts und Anpassungen auf der Seite enthalten kann. Dies bedeutet, dass das Tool die Anforderungen und Antworten liest, wenn auf die Schaltfläche Start geklickt wird und nur für die aktive SharePoint-Registerkarte, auf der das Tool läuft. Diese Informationen werden lokal vom Webbrowser erfasst und stehen Ihnen über die Schaltfläche in **JSON exportieren** oder in **har exportieren** auf der Registerkarte _Netzwerkablaufverfolgung_ des Tools zur Verfügung. **die Informationen werden nicht an Microsoft gesendet oder von Microsoft erfasst.** (Das Tool respektiert die Datenschutzrichtlinie von Microsoft, die [hier](https://go.microsoft.com/fwlink/p/?linkid=857875)zugänglich ist.)

    Die Berechtigung zum _Verwalten Ihrer Downloads_ umfasst die Verwendung der Funktion " **Export in JSON** " des Tools. Beachten Sie die Datenschutzrichtlinien Ihres Unternehmens, bevor Sie die JSON-Datei außerhalb Ihrer Organisation freigeben, da die Ergebnisse URLs enthalten und als PII (personenbezogene Informationen) klassifiziert werden können.
1. Wenn Sie das Tool im Inkognito-oder InPrivate-Modus verwenden möchten, befolgen Sie das Verfahren für Ihren Browser:
    1. Navigieren Sie in Microsoft Edge zu **Erweiterungen** , oder geben Sie _Edge://Extensions_ in die URL-Leiste ein, und wählen Sie **Details** für die Erweiterung aus. Aktivieren Sie in den Erweiterungseinstellungen das Kontrollkästchen **in InPrivate zulassen**.
    1. Navigieren Sie in Chrome zu **Erweiterungen** , oder geben Sie _Chrome://Extensions_ in die URL-Leiste ein, und wählen Sie **Details** für die Erweiterung aus. Wählen Sie in den Erweiterungseinstellungen den Schieberegler für **Allow in Incognito**aus.
1. Navigieren Sie zur Seite SharePoint-Website auf SharePoint Online, die Sie überprüfen möchten. Wir haben für "verzögertes Laden" von Elementen auf Seiten zugelassen; Daher wird das Tool nicht automatisch angehalten (Dies ist beabsichtigt, um alle Szenarien für die Seitenauslastung aufzunehmen). Wählen Sie **Beenden**aus, um die Sammlung zu beenden. Stellen Sie sicher, dass die seitenladevorgang abgeschlossen ist, bevor Sie die Datensammlung beenden, oder Sie werden nur eine partielle Ablaufverfolgung erfassen.
1. Klicken Sie auf die Symbolleistenschaltfläche der Erweiterung. ![Seiten Diagnose für SharePoint-Logo](../media/page-diagnostics-for-spo/pagediag-icon32.png) zum Laden des Tools wird das folgende Erweiterungs-Popupfenster angezeigt:

    ![Popup für Seiten Diagnosetool](../media/page-diagnostics-for-spo/pagediag-Landing.png)

Wählen Sie **Start** aus, um mit dem Sammeln von Daten zur Analyse zu beginnen.

## <a name="what-youll-see-in-the-page-diagnostics-for-sharepoint-tool"></a>Was Sie im Seiten Diagnosetool für SharePoint sehen

1. Klicken Sie in der oberen rechten Ecke des Tools auf die Ellipsen (...), um die folgenden Links zu finden:
   1. Der Link **zusätzliche Ressourcen** enthält allgemeine Anleitungen und Details zum Tool, einschließlich eines Links zu diesem Artikel.
   1. Der Link **Feedback geben** enthält einen Link zur _Benutzer sprach Website für SharePoint-Websites und-Zusammenarbeit_ .
   1. Der **Info** -Link enthält die aktuell installierte Version des Tools und einen direkten Link zum Drittanbieter-Hinweis des Tools.  
1. Die **Korrelations-ID, SPRequestDuration, SPIISLatency**, **Seitenladezeit**und **URL** -Details sind Informationszwecken und können für einige Zwecke verwendet werden.

    ![Details zur Seiten Diagnose](../media/page-diagnostics-for-spo/pagediag-details.PNG)

   - **CorrelationId** ist ein wichtiges Element beim Arbeiten mit dem Microsoft-Support, da es Ihnen ermöglicht, zusätzliche Diagnosedaten für die jeweilige Seite zu sammeln.
   - **SPRequestDuration** ist die Zeit, die SharePoint zum Verarbeiten der Seite genommen hat. Strukturelle Navigation, große Bilder, viele API-Aufrufe können alle zu längeren Zeiträumen beitragen.
   - **SPIISLatency** ist die Zeit in Millisekunden, die für SharePoint Online Beginn des Ladens der Seite übernommen wurde. Dieser Wert enthält nicht die Zeit, die für die Antwort der Webanwendung benötigt wird.
   - Bei der **Seitenladezeit** handelt es sich um die Gesamtzeit, die von der Seite von der Zeit der Anforderung bis zu dem Zeitpunkt, an dem die Antwort empfangen und im Browser gerendert wurde, aufgezeichnet wurde. Dieser Wert wird durch eine Vielzahl von Faktoren beeinflusst, einschließlich der Netzwerkwartezeit, der Leistung des Computers und der Zeit, die der Browser zum Laden der Seite benötigt.
   - Die **Seiten-URL** (Uniform Resource Locator) ist die Webadresse der aktuellen Seite.

1. Auf der Registerkarte [**Diagnosetests**](#how-to-use-the-diagnostic-tests-tab) werden die Analyseergebnisse in drei Kategorien angezeigt. **Keine Aktion erforderlich**, **Verbesserungsmöglichkeiten** und **Aufmerksamkeit erforderlich**. Jedes Testergebnis wird durch ein Element in einer dieser Kategorien dargestellt, wie in der folgenden Tabelle beschrieben:

    |Kategorie  |Farbe  |Beschreibung  |
    |---------|---------|---------|
    |**Aufmerksamkeit erforderlich** |Rot |Das Test Ergebnis liegt außerhalb des Basiswerts und wirkt sich auf die Seitenleistung aus. Behebung der Anleitungen für die Korrektur.|
    |**Verbesserungsmöglichkeiten** |Gelb |Das Test Ergebnis liegt außerhalb des Basiswerts und kann zu Leistungsproblemen beitragen. Es können Test spezifische Kriterien angewendet werden.|
    |**Keine Aktion erforderlich** |Grün |Das Testergebnis liegt innerhalb des Basiswerts des Tests.|

    ![Seiten Diagnose](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

1. Auf der Registerkarte [**Netzwerkablaufverfolgung**](#how-to-use-the-network-trace-tab) finden Sie Details zu Seiten Erstellungsanforderungen und-Antworten.

## <a name="how-to-use-the-diagnostic-tests-tab"></a>Verwenden der Registerkarte "Diagnosetests"

Wenn Sie eine moderne SharePoint-Portalseite oder eine klassische Veröffentlichungssite Seite mit dem Seiten Diagnosetool für SharePoint analysieren, werden Ergebnisse mit vordefinierten Regeln analysiert, die Ergebnisse mit Basis Planwerten vergleichen und auf der Registerkarte **Diagnosetests** angezeigt werden. Regeln für bestimmte Tests können je nachdem, wie sich bestimmte Leistungsmerkmale zwischen den beiden unterscheiden, unterschiedliche Basiswerte für moderne Portal-und

Test Ergebnisse, die in den Kategorien **Verbesserungsmöglichkeiten** oder **Aufmerksamkeit erforderlich** angezeigt werden, zeigen Bereiche an, die anhand empfohlener Methoden überprüft werden sollten, und können ausgewählt werden, um zusätzliche Informationen zum Ergebnis anzuzeigen. Details zu jedem Element enthalten einen Link _Weitere Informationen_ , der Sie direkt zu den entsprechenden Anleitungen im Zusammenhang mit dem Test führt. Test Ergebnisse, die in der Kategorie **keine Aktion erforderlich** angezeigt werden, geben die Einhaltung der relevanten Regel an und zeigen bei der Auswahl keine zusätzlichen Details an.

In den Informationen auf der Registerkarte Diagnosetests wird nicht erläutert, wie Seiten entworfen werden, sondern es werden Faktoren hervorgehoben, die sich möglicherweise auf die Seitenleistung auswirken. Einige Seiten Funktionen und Anpassungen haben einen unvermeidbaren Einfluss auf die Seitenleistung und sollten für mögliche Korrekturen oder Auslassungen auf der Seite überprüft werden, wenn die Auswirkungen erheblich sind.

Rote oder gelbe Ergebnisse geben möglicherweise auch Webparts an, die Daten zu häufig aktualisieren. Beispielsweise werden Unternehmensnachrichten nicht jede Sekunde aktualisiert, aber benutzerdefinierte Webparts werden häufig so erstellt, dass die neuesten Nachrichten jede Sekunde abgerufen werden, anstatt zwischen Speicherungs Elementen zu implementieren, die die Gesamtbenutzer Oberfläche verbessern könnten. Beachten Sie beim Einschließen von Webparts auf einer Seite, dass häufig einfache Möglichkeiten zur Verringerung ihrer Leistungseinbußen auftreten, indem Sie den Wert der einzelnen verfügbaren Parameter bewerten, um sicherzustellen, dass Sie für den beabsichtigten Zweck ordnungsgemäß festgelegt werden.

>[!NOTE]
>Klassische Teamwebsites, für die das Veröffentlichungsfeature nicht aktiviert ist, können CDNs nicht verwenden. Wenn Sie das Tool auf diesen Websites ausführen, wird erwartet, dass der CDN-Test fehlschlägt und ignoriert werden kann, aber alle verbleibenden Tests sind anwendbar. Die zusätzliche Funktionalität des SharePoint-Veröffentlichungsfeatures kann die Seitenladezeiten verbessern, daher sollte es nicht aktiviert werden, um die CDN-Funktionalität zu ermöglichen.

>[!IMPORTANT]
>Testregeln werden regelmäßig hinzugefügt und aktualisiert, daher finden Sie in der aktuellen Version des Tools ausführliche Informationen zu aktuellen Regeln und spezifischen Informationen, die in Testergebnissen enthalten sind. Sie können die Version überprüfen, indem Sie Ihre Erweiterungen verwalten, und die Erweiterung wird Ihnen mitteilen, ob ein Update verfügbar ist.

## <a name="how-to-use-the-network-trace-tab"></a>Verwenden der Registerkarte "Netzwerkablaufverfolgung"

Die Registerkarte **Netzwerkablaufverfolgung** enthält detaillierte Informationen zu beiden Anforderungen zum Erstellen der Seite und den von SharePoint empfangenen Antworten.

1. **Suchen Sie nach Element Ladezeiten, die als rot gekennzeichnet**sind. Jede Anforderung und Antwort ist farblich codiert, um ihre Auswirkungen auf die Gesamtleistung der Seite mit den folgenden Latenz Metriken anzugeben:
    - Grün: \< 500M
    - Gelb: 500-1000ms
    - Rot: \> 1000ms

    ![Netzwerkablaufverfolgung](../media/page-diagnostics-for-spo/pagediag-networktrace-red.png)

    Im oben gezeigten Bild bezieht sich das rote Element auf die Standardseite. Es wird immer rot angezeigt, es sei denn, die Seite wird in \< 1000ms (weniger als 1 Sekunde) geladen.

2. **Laden der Test Element Zeiten**. In einigen Fällen wird kein Zeit-oder Farbindikator angezeigt, da die Elemente bereits vom Browser zwischengespeichert wurden. Um dies ordnungsgemäß zu testen, öffnen Sie die Seite, leeren Sie den Browsercache, und klicken Sie dann auf **starten** , um eine "kalte" Seitenlast zu erzwingen und eine echte Reflektion der anfänglichen Seitenlast zu sein. Dies sollte dann mit der "warmen" Seiten Lade verglichen werden, da dies auch dazu beiträgt, zu ermitteln, welche Elemente auf der Seite zwischengespeichert werden.

3. **Freigeben relevanter Details für andere Personen, die bei der Untersuchung von Problemen behilflich sein können** Um die im Tool bereitgestellten Details oder Informationen für Ihre Entwickler oder eine Person mit technischem Support freizugeben, klicken Sie auf in **JSON exportieren** (siehe Abbildung oben). Damit können Sie die Ergebnisse herunterladen, die mit einem JSON-Dateiviewer angezeigt werden.

    Wenn Sie sich für die Verwendung des Vorschau-Features für den *Export in Har* entschieden haben, wird der Exporttyp als **Export in Har**angezeigt.

    ![Netzwerkablaufverfolgung](../media/page-diagnostics-for-spo/pagediag-NetworkTraceHAR.PNG)

> [!IMPORTANT]
> Diese Ergebnisse enthalten URLs, die als PII klassifiziert werden können (personenbezogene Informationen). Stellen Sie sicher, dass Sie die Richtlinien Ihrer Organisation befolgen, bevor Sie diese Informationen verteilen.

## <a name="engaging-with-microsoft-support"></a>Einbindung des Microsoft-Supports

Wir haben ein **Feature von Microsoft Support Level** aufgenommen, das nur beim direkten Arbeiten an einem Supportfall verwendet werden sollte. Die Verwendung dieses Features bietet keinen Nutzen für Sie, wenn es ohne Support Team Engagement verwendet wird, und kann die Leistung der Seite deutlich langsamer machen. Es gibt keine zusätzlichen Informationen bei Verwendung dieses Features im Tool, da die zusätzlichen Informationen zur Protokollierung im Dienst hinzugefügt werden.

Es wird keine Änderung angezeigt, außer dass Sie benachrichtigt werden, dass Sie sie aktiviert haben, und die Leistung Ihrer Seite wird während der Aktivierung deutlich um 2-3-mal weniger Leistung verringert. Er ist nur für die jeweilige Seite und die aktive Sitzung relevant. Aus diesem Grund sollte diese sparsam und nur dann verwendet werden, wenn Sie aktiv mit dem Support beschäftigt sind.

### <a name="to-enable-the-microsoft-support-level-feature"></a>So aktivieren Sie das Feature "Microsoft Support Level"

1. Öffnen Sie das Tool Seite Diagnostics für SharePoint.
2. Drücken Sie auf der Tastatur **ALT-UMSCHALT-L**. Dadurch wird das Kontrollkästchen **Support Protokollierung aktivieren** angezeigt.
3. Aktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **starten** , um die Seite neu zu laden und die ausführliche Protokollierung zu generieren.

    ![Support Option aktiviert](../media/page-diagnostics-for-spo/pagediag-support.png)
  
    Notieren Sie sich die CorrelationId (oben im Tool angezeigt), und stellen Sie Sie Ihrem Supportmitarbeiter zur Verfügung, damit Sie zusätzliche Informationen zur Diagnosesitzung sammeln können.

## <a name="related-topics"></a>Verwandte Themen

[Optimieren der Leistung von SharePoint Online](tune-sharepoint-online-performance.md)

[Optimieren der Leistung von Office 365](tune-microsoft-365-performance.md)

[Leistung in der modernen SharePoint-Oberfläche](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Netzwerke für die Inhaltsübermittlung](content-delivery-networks.md)

[Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-microsoft-365-cdn-with-spo.md)
