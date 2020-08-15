---
title: Behandlung von Leistungsproblemen – Plan für Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 5/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c
ms.collection:
- M365-security-compliance
- Ent_O365
description: Dieser Artikel hilft Ihnen bei der Behebung von Office 365 Leistungsproblemen und bei der Behebung einiger der häufigsten Probleme.
ms.openlocfilehash: 9287e2649a2eb126d723e7436a9178be93087bc0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690564"
---
# <a name="performance-troubleshooting-plan-for-office-365"></a>Behandlung von Leistungsproblemen – Plan für Office 365

Müssen Sie die erforderlichen Schritte zum Identifizieren und Beheben von Verzögerungen, hängen und langsamer Leistung zwischen SharePoint Online, OneDrive für Unternehmen, Exchange Online oder Skype for Business Online und Ihrem Clientcomputer kennen? Vor dem Aufruf des Supports können Sie in diesem Artikel bei der Problembehandlung Office 365 Leistungsproblemen behilflich sein und sogar einige der am häufigsten auftretenden Probleme beheben.
  
Dieser Artikel ist eigentlich ein Beispiel Aktionsplan, den Sie verwenden können, um wertvolle Daten zu Ihrem Leistungsproblem zu erfassen, während dies geschieht. Einige der wichtigsten Probleme sind auch in diesem Artikel enthalten.

Wenn Sie noch nicht mehr mit der Netzwerkleistung zu tun haben und einen langfristigen Plan zum Überwachen der Leistung zwischen ihren Clientcomputern und Office 365 erstellen möchten, sehen Sie sich [Office 365 Leistungsoptimierung und Problembehandlung – admin und IT-Experten](performance-tuning-using-baselines-and-history.md)an.
  
## <a name="sample-performance-troubleshooting-action-plan"></a>Beispiel für eine Leistungsproblembehandlung-Aktionsplan

Dieser Aktionsplan enthält zwei Teile; eine Vorbereitungsphase und eine Protokollierungs Phase. Wenn Sie im Moment ein Leistungsproblem haben und Datensammlung durchführen müssen, können Sie diesen Plan sofort verwenden.
  
### <a name="prepare-the-client-computer"></a>Vorbereiten des Clientcomputers
  
- Suchen Sie einen Clientcomputer, der das Leistungsproblem reproduzieren kann. Dieser Computer wird im Verlauf der Problembehandlung verwendet.
- Notieren Sie sich die Schritte, die dazu führen, dass das Leistungsproblem auftritt, damit Sie bereit sind, wenn es Zeit zum Testen kommt.
- Installieren von Tools zum Sammeln und Aufzeichnen von Informationen:
  - Installieren Sie [Netmon 3,4](https://www.microsoft.com/download/details.aspx?id=4865) (oder verwenden Sie ein entsprechendes Netzwerk Ablaufverfolgungstool).
  - Installieren Sie die ﻿kostenlose Basic Edition von [HTTPWatch](https://www.httpwatch.com/download/) (oder verwenden Sie ein äquivalentes Netzwerk Ablaufverfolgungstool).
  - Verwenden Sie eine Bildschirmaufzeichnung, oder führen Sie die mit Windows Vista und höher bereitgestellten Schritte Recorder (PSR.exe) aus, um die Schritte zu protokollieren, die Sie während der Tests durchführen.

### <a name="log-the-performance-issue"></a>Protokollieren des Leistungsproblems
  
- Schließen Sie alle fremden Internet Browser.
- Starten Sie die Aufzeichnung der Schritte oder eine andere Bildschirmaufzeichnung.
- Starten Sie die NetMon-Erfassung (oder das Netzwerk Ablaufverfolgungstool).
- Löschen Sie den DNS-Cache auf dem Clientcomputer von der Befehlszeile aus, indem Sie ipconfig/flushdns ein. eingeben.
- Starten Sie eine neue Browsersitzung, und aktivieren Sie HTTPWatch.
- Optional: Wenn Sie Exchange Online testen, führen Sie das Tool Exchange Client Performance Analyzer in der Office 365-Verwaltungskonsole aus.
- Reproduzieren Sie die genauen Schritte, die das Leistungsproblem verursachen.
- Beenden Sie die NetMon-oder die Ablaufverfolgung anderer Tools.
- Führen Sie an der Befehlszeile eine Ablauf Verfolgungs Route zu Ihrem Office 365 Abonnement aus, indem Sie den folgenden Befehl eingeben und dann die EINGABETASTE drücken:

  ``` cmd
  tracert <subscriptionname>.onmicrosoft.com
  ```

- Beenden Sie die Aufzeichnung der Schritte und speichern Sie das Video. Achten Sie darauf, dass Sie das Datum und die Uhrzeit der Erfassung einschließen und ob Sie eine gute oder schlechte Leistung veranschaulichen.
- Speichern Sie die Ablaufverfolgungsdateien. Achten Sie darauf, dass Sie das Datum und die Uhrzeit der Erfassung einschließen und ob die Leistung gut oder schlecht dargestellt wird.

Wenn Sie mit dem Ausführen der in diesem Artikel erwähnten Tools nicht vertraut sind, machen Sie sich keine Sorgen, da wir diese Schritte als nächstes bereitstellen. Wenn Sie diese Art von Netzwerkerfassung gewohnt sind, können Sie mit dem [Sammeln von Baselines](performance-tuning-using-baselines-and-history.md#how-to-collect-baselines)fortfahren, in dem die Filterung und das Lesen der Protokolle beschrieben werden.
  
### <a name="flush-the-dns-cache-first"></a>Leeren des DNS-Caches zuerst

Warum? Durch das Leeren des DNS-Caches starten Sie Ihre Tests mit einem sauberen Schiefer. Wenn Sie den Cache leeren, setzen Sie den DNS-Resolver-Inhalt auf die aktuellsten Einträge zurück. Beachten Sie, dass durch einen Flush keine HOSTs-Dateieinträge entfernt werden. Wenn Sie Host Dateieinträge ausgiebig verwenden, sollten Sie diese Einträge in eine Datei in einem anderen Verzeichnis kopieren und dann die Hostdatei leeren.
  
#### <a name="flush-your-dns-resolver-cache"></a>Leeren des DNS-Auflösungs Caches
  
1. Öffnen Sie die Eingabeaufforderung, ( **starten** Sie entweder \> **Run** \> **cmd** oder **Windows Key** \> **cmd**).
2. Geben Sie den folgenden Befehl ein, und drücken Sie die EINGABETASTE:

    ``` cmd
    ipconfig /flushdns
    ```

## <a name="netmon"></a>NetMon

Das netzwerküberwachungstool ([netmon](https://www.microsoft.com/download/details.aspx?id=4865)) von Microsoft analysiert Pakete, also Datenverkehr, der zwischen Computern in Netzwerken verläuft. Durch die Verwendung von Netmon zum Verfolgen des Datenverkehrs mit Office 365 können Sie Paket Kopfzeilen erfassen, anzeigen und lesen, eingreifende Geräte identifizieren, wichtige Einstellungen für die Netzwerkhardware überprüfen, nach verworfenen Paketen suchen und den Datenverkehr zwischen Computern in Ihrem Unternehmensnetzwerk und Office 365 verfolgen. Da der tatsächliche Text des Datenverkehrs verschlüsselt ist, d. (er reist an Port 443 über SSL/TLS, können die gesendeten Dateien nicht gelesen werden. Stattdessen erhalten Sie eine ungefilterte Ablaufverfolgung des Pfads, den das Paket ausführt, was Ihnen helfen kann, das Problemverhalten nachzuverfolgen.
  
Stellen Sie sicher, dass Sie zu diesem Zeitpunkt keinen Filter anwenden. Führen Sie stattdessen die Schritte aus, und demonstrieren Sie das Problem, bevor Sie die Ablaufverfolgung beenden und speichern.
  
Öffnen Sie nach der Installation von Netmon 3,4 das Tool, und führen Sie die folgenden Schritte aus:
  
### <a name="take-a-netmon-trace-and-reproduce-the-issue"></a>Übernehmen einer Netmon-Ablaufverfolgung und reproduzieren des Problems
  
1. Starten Sie Netmon 3,4.
Auf der **Start** Seite gibt es drei Bereiche: **zuletzt erfasste**Elemente, **Netzwerke auswählen**und **Erste Schritte mit Microsoft Network Monitor 3,4. Hinweis**. Im Bereich Netzwerke auswählen erhalten Sie außerdem eine Liste der Standardnetzwerke, aus denen Sie erfasst werden können. Stellen Sie sicher, dass hier Netzwerkkarten ausgewählt sind.

2. Klicken Sie oben auf der **Start** Seite auf **neue Erfassung** . Dadurch wird eine neue Registerkarte neben der Registerkarte **Start** Seite mit dem Namen **Capture 1**hinzugefügt.
![Die NetMon-Benutzeroberfläche mit den neuen Schaltflächen Capture, Start und Stop wurde hervorgehoben.](../media/d4527d84-62ec-4301-82d5-e0166ff71f20.PNG)

3. Um eine einfache Erfassung durchführen zu können, klicken Sie auf der Symbolleiste auf **starten** .

4. Reproduzieren Sie die Schritte, die ein Leistungsproblem darstellen.

5. Klicken **Stop** Sie auf \> **Datei** \> **Speichern**unter beenden. Denken Sie daran, das Datum und die Uhrzeit mit der Zeitzone zu versehen und anzugeben, ob eine schlechte oder eine gute Leistung gezeigt wird.

## <a name="httpwatch"></a>HTTPWatch

[HTTPWatch](https://www.httpwatch.com/download/) kommt in Rechnung und eine ﻿kostenlose Edition. Die ﻿kostenlose Basic Edition umfasst alles, was Sie für diesen Test benötigen. HTTPWatch überwacht den Netzwerkdatenverkehr und die Ladezeit der Seite direkt in Ihrem Browserfenster. HTTPWatch ist ein Plug-in für Internet Explorer, das die Leistung grafisch beschreibt. Die Analyse kann in HTTPWatch Studio gespeichert und angezeigt werden.
  
> [!NOTE]
> Wenn Sie einen anderen Browser wie Firefox oder Google Chrome verwenden oder HTTPWatch nicht in Internet Explorer installieren können, öffnen Sie ein neues Browserfenster, und drücken Sie F12 auf Ihrer Tastatur. Das Entwickler Tool sollte unten in Ihrem Browser angezeigt werden. Wenn Sie Opera verwenden, drücken Sie STRG + UMSCHALT + I für den webinspektor, klicken Sie dann auf die Registerkarte **Netzwerk** , und führen Sie die unten beschriebenen Tests aus. Die Informationen werden geringfügig unterschiedlich sein, aber Ladezeiten werden weiterhin in Millisekunden angezeigt. > HTTPWatch ist auch für Probleme mit SharePoint Online Seitenladezeiten sehr nützlich.
  
### <a name="run-httpwatch-and-reproduce-the-issue"></a>Ausführen von HTTPWatch und reproduzieren des Problems
  
HTTPWatch ist ein Browser-Plug-in, sodass das verfügbar machen des Tools im Browser für jede Version von Internet Explorer geringfügig abweicht. In der Regel können Sie HTTPWatch unter der Befehlsleiste im Internet Explorer Browser suchen. Wenn das HTTPWatch-Plug-in nicht in Ihrem Browserfenster angezeigt wird, überprüfen Sie die Version Ihres Browsers, indem Sie auf **Hilfe** \> **über**oder in höheren Versionen von Internet Explorer klicken, auf das Zahnradsymbol und **Internet Explorer**. Klicken Sie zum Starten der **Befehls** Leiste mit der rechten Maustaste in Internet Explorer auf die Menüleiste, und klicken Sie dann auf **Befehlsleiste**.

In der Vergangenheit wurde HTTPWatch sowohl den Befehlen als auch den Explorer-Balken zugeordnet, sodass Sie nach der Installation, wenn Sie nicht sofort das Symbol (auch nach dem Neustart) überprüfen, **Tools**und die Symbolleisten für das Symbol sehen. Denken Sie daran, dass Symbolleisten angepasst werden können und Optionen hinzugefügt werden können.

![Internet Explorer Befehls Symbolleiste mit dem HTTPWatch-Symbol angezeigt.](../media/198590b0-d7b1-4bff-a6ad-e4ec3a1e83df.png)
  
1. Starten Sie HTTPWatch in einem Internet Explorer Browserfenster. Sie wird am unteren Rand des Fensters an den Browser angedockt angezeigt. Klicken Sie auf **Record**.

2. Reproduzieren Sie die genauen Schritte im Zusammenhang mit dem Leistungsproblem. Klicken Sie in HTTPWatch auf die Schaltfläche **Beenden** .

3. **Speichern** Sie das HTTPWatch oder senden Sie es **per e-Mail**. Denken Sie daran, die Datei so zu benennen, dass Sie Informationen zu Datum und Uhrzeit sowie einen Hinweis darauf enthält, ob Ihre Uhr eine Vorführung guter oder schlechter Leistung enthält.

![HTTPWatch zeigt die Registerkarte "Netzwerk" für eine Seitenlast der Office 365 Homepage an.](../media/021a2c64-d581-49fd-adf4-4c364f589d75.PNG)

Dieser Screenshot stammt aus der professionellen Version von HTTPWatch. Sie können Ablaufverfolgungen öffnen, die in der grundlegenden Version auf einem Computer mit einer professionellen Version entnommen wurden, und diese dort lesen. Über diese Methode sind möglicherweise zusätzliche Informationen aus der Ablaufverfolgung verfügbar.

## <a name="problem-steps-recorder"></a>Problem Aufzeichnung für Schritte

Mit den Schritten Recorder oder PSR.exe können Sie Probleme aufzeichnen, während Sie auftreten. Es handelt sich um ein sehr nützliches Tool, das sehr einfach ausgeführt werden kann.
  
### <a name="run-problem-steps-recorder-psrexe-to-record-your-work"></a>Ausführen des Problems "Recording Steps Recorder" (PSR.exe) zum Aufzeichnen Ihrer Arbeit
  
1. Verwenden Sie entweder **Start** \> **Lauftyp** \> **PSR.exe** \> **OK**, oder klicken Sie auf den **Windows-Schlüsseltyp** \> **PSR.exe** , \> und drücken Sie dann die EINGABETASTE.

2. Wenn das Fenster kleines PSR.exe angezeigt wird, klicken Sie auf **Datensatz starten** , und reproduzieren Sie die Schritte, die das Leistungsproblem reproduzieren. Sie können bei Bedarf Kommentare hinzufügen, indem Sie auf **Kommentare hinzufügen**klicken.

3. Klicken Sie auf **Record beenden** , wenn Sie die Schritte abgeschlossen haben. Wenn es sich bei dem Leistungsproblem um ein Seitenrendering handelt, warten Sie, bis die Seite gerendert wird, bevor Sie die Aufzeichnung beenden.

4. Klicken Sie auf **Speichern**.

![Ein Screenshot der Schritte Recorder oder PSR.exe.](../media/8542b0aa-a3ff-4718-8dc4-43f5521c6c34.PNG)
  
Das Datum und die Uhrzeit werden für Sie aufgezeichnet. Dadurch wird Ihr PSR mit ihrer Netmon-Ablaufverfolgung und HTTPWatch in der Zeit verknüpft und hilft bei der präzisen Problembehandlung. Das Datum und die Uhrzeit im PSR-Eintrag können zeigen, dass eine Minute zwischen der Anmeldung und dem Browsen der URL und dem partiellen Rendern der Administratorwebsite verging, beispielsweise.
  
## <a name="read-your-traces"></a>Lesen der Ablaufverfolgungen

Es ist nicht möglich, alles über die Netzwerk-und Leistungsfehler Behebung zu unterrichten, die jemand über einen Artikel wissen müsste. Bei der Leistungsfähigkeit wird die Erfahrung und die Funktionsweise des Netzwerks und in der Regel ausgeführt. Es ist jedoch möglich, eine Liste mit den wichtigsten Problemen zusammenzustellen und zu zeigen, wie Sie mit Tools das Beseitigen der häufigsten Probleme erleichtern können.
  
Wenn Sie wissen möchten, wie Sie Netzwerkablaufverfolgungen für Ihre Office 365-Websites lesen können, gibt es keinen besseren Lehrer als die regelmäßige Erstellung von Spuren von Seitenlasten und die Erfahrung beim Lesen. Wenn Sie beispielsweise eine Chance haben, laden Sie einen Office 365 Dienst, und verfolgen Sie den Prozess. Filtern Sie die Ablaufverfolgung für DNS-Datenverkehr, oder Durchsuchen Sie den FrameData nach dem Namen des Diensts, den Sie durchsucht haben. Überprüfen Sie die Ablaufverfolgung, um eine Vorstellung der Schritte zu erhalten, die beim Laden des Diensts auftreten. Auf diese Weise erfahren Sie, wie die normale Seitenauslastung aussehen sollte, und im Fall der Problembehandlung, insbesondere im Hinblick auf die Leistung, kann das Vergleichen von guten und schlechten Ablaufverfolgungen eine Menge Lehren.
  
NetMon verwendet Microsoft IntelliSense im Feld Anzeigefilter. IntelliSense oder die intelligente Codevervollständigung ist dieser Trick, bei dem Sie einen Punkt eingeben und alle verfügbaren Optionen in einem Dropdown-Auswahlfeld angezeigt werden. Wenn Sie beispielsweise über die TCP-Fensterskalierung besorgt sind, können Sie mit dieser Methode zu einem Filter (beispielsweise  `.protocol.tcp.window < 100` ) gelangen.
  
![Screenshot von Netmon, der zeigt, dass das Feld "Anzeige Filter" IntelliSense verwendet.](../media/75a56c11-9a60-47ee-a100-aabdfb1ba10f.PNG)
  
Netmon-Ablaufverfolgungen können viel Datenverkehr aufweisen. Wenn Sie keine Erfahrung mit dem Lesen haben, ist es wahrscheinlich, dass Sie überwältigt werden, wenn Sie das erste Mal die Ablaufverfolgung öffnen. Das erste, was Sie tun müssen, ist, dass das Signal vom Hintergrundrauschen in der Ablaufverfolgung getrennt wird. Sie haben mit Office 365 getestet, und das ist der Datenverkehr, den Sie sehen möchten. Wenn Sie zur Navigation durch Ablaufverfolgungen verwendet werden, benötigen Sie diese Liste möglicherweise nicht.
  
Der Datenverkehr zwischen dem Client und Office 365 erfolgt über TLS, was bedeutet, dass der Text des Datenverkehrs verschlüsselt und nicht in einer allgemeinen Netmon-Ablaufverfolgung lesbar ist. Bei der Leistungsanalyse müssen nicht die Besonderheiten der Informationen im Paket bekannt sein. Es ist jedoch sehr an Paket Kopfzeilen und den darin enthaltenen Informationen interessiert.
  
### <a name="tips-to-get-a-good-trace"></a>Tipps zum Abrufen einer guten Ablaufverfolgung
  
- Kennen Sie den Wert der IPv4-oder IPv6-Adresse Ihres Clientcomputers. Sie können dies über die Eingabeaufforderung abrufen, indem Sie **ipconfig** eingeben und dann die EINGABETASTE drücken. Wenn Sie diese Adresse kennen, können Sie auf einen Blick erfahren, ob der Datenverkehr in der Ablaufverfolgung Ihren Clientcomputer direkt einbezieht. Wenn es einen bekannten Proxy gibt, Pingen Sie ihn, und rufen Sie auch seine IP-Adresse ab.

- Leeren Sie den DNS-Auflösungscache, und schließen Sie, wenn möglich, alle Browser ab, mit Ausnahme derjenigen, in der Sie die Tests durchführen. Wenn Sie dies nicht tun können, beispielsweise wenn die Unterstützung ein browserbasiertes Tool zum Anzeigen des Desktops des Clientcomputers verwendet, müssen Sie Ihre Ablaufverfolgung filtern.

- Suchen Sie in einer aktiven Ablaufverfolgung nach dem Office 365 Dienst, den Sie verwenden. Wenn Sie den Datenverkehr noch nie oder selten gesehen haben, ist dies ein hilfreicher Schritt, um das Leistungsproblem von anderen Netzwerk Rauschen zu trennen. Es gibt einige Möglichkeiten, dies zu tun. Direkt vor dem Test können Sie _Ping_ oder _PsPing_ für die URL des jeweiligen Diensts verwenden (oder Beispiels `ping outlook.office365.com` `psping -4 microsoft-my.sharepoint.com:443` Weise). Sie können diesen Ping-oder PsPing auch ganz einfach in einer Netmon-Ablaufverfolgung (anhand des Prozess namens) finden. Das gibt Ihnen einen Platz, um mit der Suche zu beginnen.

Wenn Sie zum Zeitpunkt des Problems nur Netmon Tracing verwenden, ist das auch okay. Um sich selbst zu orientieren, verwenden Sie einen Filter wie `ContainsBin(FrameData, ASCII, "office")` oder `ContainsBin(FrameData, ASCII, "outlook")` . Sie können Ihre Framenummer aus der Ablaufverfolgungsdatei aufzeichnen. Möglicherweise möchten Sie auch den _Frame Zusammenfassungs_ Bereich ganz nach rechts scrollen und nach der Spalte Unterhaltungs-ID suchen. Es gibt eine Nummer, die für die ID dieser spezifischen Unterhaltung angezeigt wird, die Sie später auch isoliert aufzeichnen und sehen können. Denken Sie daran, diesen Filter zu entfernen, bevor Sie andere Filter anwenden.

> [!TIP]
> NetMon verfügt über viele hilfreiche integrierte Filter. Testen Sie die Schaltfläche " **Filter laden** " oben im Bereich " _Anzeige_ Filter".
  
![Suchen Sie Ihre IP mithilfe von PSPing in der Befehlszeile auf dem Clientcomputer.](../media/4c43ac67-e28e-4536-842d-7add7aa28847.PNG)
  
![NetMon-Ablaufverfolgung vom Client mit dem gleichen PSPing-Befehl über den TCP-Filter. Flags. SYN = = 1.](../media/0ae7ef7d-e003-4d01-a006-dc49bd1fcef2.PNG)
  
Machen Sie sich mit Ihrem Traffic vertraut, und erfahren Sie, wie Sie die benötigten Informationen finden. Beispielsweise erfahren Sie, wie Sie ermitteln, welches Paket in der Ablaufverfolgung den ersten Verweis auf den Office 365 Dienst verwendet, den Sie verwenden (wie "Outlook").

Wenn Office 365 Outlook Online als Beispiel angenommen wird, beginnt der Datenverkehr etwa wie folgt:
  
- DNS-Standard Abfrage und DNS-Antwort für Outlook.office365.com mit übereinstimmender QueryIDs. Es ist wichtig, dass Sie den Zeit Offset für diesen Turn-Around beachten, und wo in der Welt die Office 365 globale DNS die Anforderung zur Namensauflösung sendet. Idealerweise so lokal wie möglich statt auf der halben Welt.

- Eine HTTP GET-Anforderung, deren Statusbericht dauerhaft verschoben wurde (301)

- RWS-Datenverkehr einschließlich RWs Connect-Anforderungen und Connect-Antworten. (Dies ist eine Remote-WinSock, die eine Verbindung für Sie herstellen.)

- Eine TCP SYN-und TCP-SYN/ACK-Unterhaltung. Viele der Einstellungen in dieser Unterhaltung wirken sich auf Ihre Leistung aus.

- Dann eine Reihe von TLS: TLS-Datenverkehr, in dem die Unterhaltungen zwischen TLS-Handshake und TLS-Zertifikaten stattfinden. (Denken Sie daran, dass die Daten über SSL/TLS verschlüsselt sind.)

Alle Teile des Datenverkehrs sind wichtig und verbunden, aber kleine Teile der Ablaufverfolgung enthalten Informationen, die in Bezug auf die Leistungsproblembehandlung besonders wichtig sind, daher konzentrieren wir uns auf diese Bereiche. Da wir bei Microsoft genug Office 365 Leistungsproblembehandlung durchgeführt haben, um eine Liste der zehn häufigsten Probleme zu erstellen, konzentrieren wir uns auf diese Probleme und die Verwendung der Tools, die Sie als nächstes herausfinden müssen.
  
Wenn Sie Sie nicht alle Ready installiert haben, werden in der folgenden Matrix verschiedene Tools verwendet. Wo möglich. Links werden den Installations Punkten zur Verfügung gestellt. Die Liste enthält allgemeine Tools für die Netzwerkablaufverfolgung wie [netmon](https://www.microsoft.com/download/details.aspx?id=4865) und [wireshark](https://www.wireshark.org/), verwendet jedoch ein beliebiges Ablaufverfolgungstool, mit dem Sie sich vertraut machen und in dem Sie den Netzwerkdatenverkehr filtern können. Beachten Sie beim Testen Folgendes:
  
- *Schließen Sie Ihre Browser, und testen Sie mit nur einem Browser*  – dadurch wird der gesamte erfasste Datenverkehr reduziert. Es sorgt für eine wenig beschäftigte Ablaufverfolgung.
- *Leeren Sie den DNS-Auflösungscache auf dem Clientcomputer*  -dadurch erhalten Sie eine saubere schiefertafel, wenn Sie mit der Aufnahme beginnen, für eine sauberere Ablaufverfolgung.

## <a name="common-issues"></a>Häufig auftretende Probleme

Einige häufige Probleme, denen Sie ausgesetzt sein können, und deren Suche in ihrer Netzwerkablaufverfolgung.

### <a name="tcp-windows-scaling"></a>TCP-Windows-Skalierung

In der SYN-SYN/ACK gefunden. Legacy-oder Alterungs Hardware nutzt möglicherweise nicht die TCP-Windows-Skalierung.  Ohne ordnungsgemäße TCP-Windows-Skalierungseinstellungen wird der 16-Bit-Standardpuffer in TCP-Kopfzeilen in Millisekunden ausgefüllt.  Datenverkehr kann nicht weitergesendet werden, bis der Client eine Bestätigung erhält, dass die ursprünglichen Daten empfangen wurden, wodurch Verzögerungen auftreten.

#### <a name="tools"></a>Tools

- NetMon
- Wireshark

#### <a name="what-to-look-for"></a>Worauf Sie achten sollten

Suchen Sie in der Netzwerkablaufverfolgung nach dem SYN-SYN/ACK-Datenverkehr.  Verwenden Sie in Netmon einen Filter wie  `tcp.flags.syn == 1` . Dieser Filter ist in Wireshark identisch.  

![Filtern Sie in Netmon oder wireshark für SYN-Pakete für beide Tools: TCP. Flags. SYN = = 1.](../media/4b9a12a1-c915-43c8-ac2f-a679d0435a29.PNG)

Beachten Sie, dass für jede SYN eine Quellportnummer (SrcPort) vorhanden ist, die im Zielport (synport) der zugehörigen Bestätigung (SYN/ACK) übereinstimmt.

Um den von Ihrer Netzwerkverbindung verwendeten Skalierungswert für Windows anzuzeigen, erweitern Sie zunächst die SYN-und dann die zugehörige SYN/ACK.  

![Grafik, die zeigt, wie SrcPort mit synport in einer Ablaufverfolgung abgeglichen wird, um das Zeit Delta zu erhalten.](../media/6a4ca573-0253-4fbd-93e8-92821ee1c351.png)  

### <a name="tcp-idle-time-settings"></a>TCP-Leerlaufzeit Einstellungen

Historisch gesehen sind die meisten Umkreisnetzwerke für vorübergehende Verbindungen konfiguriert, was bedeutet, dass Leerlaufverbindungen im allgemeinen beendet werden. TCP-Sitzungen im Leerlauf können von Proxys und Firewalls mit mehr als 100 bis 300 Sekunden beendet werden. Dies ist für Outlook Online problematisch, da es langfristige Verbindungen erstellt und verwendet, unabhängig davon, ob Sie im Leerlauf sind oder nicht.  

Wenn Verbindungen von Proxy-oder Firewall-Geräten beendet werden, wird der Client nicht informiert, und ein Versuch, Outlook online zu verwenden, bedeutet, dass ein Clientcomputer wiederholt versucht, die Verbindung wiederherzustellen, bevor eine neue Verbindung hergestellt wird. Möglicherweise werden im Produkt, in den Ansagen oder bei langsamer Leistung beim Laden der Seite hängt angezeigt.

#### <a name="tools"></a>Tools

- NetMon
- Wireshark

#### <a name="what-to-look-for"></a>Worauf Sie achten sollten

Sehen Sie sich in Netmon das Feld Zeitabstand für einen Roundtrip an. Bei einem Roundtrip handelt es sich um die Zeit zwischen dem Client, der eine Anforderung an den Server sendet und eine Antwort zurück erhält. Überprüfen Sie zwischen dem Client und dem Ausgangswert (ex. Client-- \> Proxy) oder der Client Office 365 (Client-- \> Office 365). Sie können dies in vielen Arten von Paketen sehen.

Beispielsweise kann der Filter in Netmon wie  `.Protocol.IPv4.Address == 10.102.14.112 AND .Protocol.IPv4.Address == 10.201.114.12` , oder, in Wireshark, Aussehen  `ip.addr == 10.102.14.112 &amp;&amp; ip.addr == 10.201.114.12` .  

> [!TIP]
> Sie wissen nicht, ob die IP-Adresse in Ihrer Ablaufverfolgung zu Ihrem DNS-Server gehört? Versuchen Sie es nach oben an der Befehlszeile. Klicken Sie auf **Start** \> **Ausführen** \> , geben Sie **cmd**ein, oder drücken Sie die **Windows** \> -Taste, und geben Sie **cmd**ein. Geben Sie an der Eingabeaufforderung ein  `nslookup <the IP address from the network trace>` . Verwenden Sie zum Testen nslookup für die IP-Adresse Ihres Computers. > eine Liste der IP-Bereiche von Microsoft finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://technet.microsoft.com/library/hh373144.aspx).

Wenn ein Problem vorliegt, erwarten Sie, dass lange Zeitoffsets angezeigt werden, in diesem Fall (Outlook Online), insbesondere in TLS: TLS-Paketen, die den Durchgang von Anwendungsdaten anzeigen (beispielsweise können Sie in Netmon über Anwendungsdaten Pakete suchen  `.Protocol.TLS AND Description == "TLS:TLS Rec Layer-1 SSL Application Data"` ). Sie sollten einen reibungslosen Verlauf in der Zeit in der Sitzung sehen. Wenn beim Aktualisieren von Outlook Online lange Verzögerungen angezeigt werden, kann dies darauf zurückzuführen sein, dass ein hoher Grad an Zurücksetzen gesendet wird.

### <a name="latencyround-trip-time"></a>Wartezeit/Roundtrip-Zeit

Bei der Wartezeit handelt es sich um eine Maßnahme, die abhängig von vielen Variablen, einer solchen Aktualisierung von Alterungs Geräten, dem Hinzufügen einer großen Anzahl von Benutzern zu einem Netzwerk und dem prozentualen Anteil der Gesamtbandbreite, die von anderen Aufgaben in einer Netzwerkverbindung beansprucht wird, viel ändern kann.

Es gibt bandbreitenrechner für Office 365, die in dieser [Netzwerkplanung und Leistungsoptimierung für Office 365](network-planning-and-performance.md) Seite verfügbar sind.  

Sie müssen die Geschwindigkeit Ihrer Verbindung oder die Bandbreite ihrer ISP-Verbindung messen? Versuchen Sie diese Website (oder Websites wie Sie): [Speedtest Offizielle Website](https://www.speedtest.net/), oder Fragen Sie Ihre bevorzugten Suchmaschine für die Phrase **Speed Test**.

#### <a name="tools"></a>Tools

- Ping
- PsPing
- NetMon
- Wireshark

#### <a name="what-to-look-for"></a>Worauf Sie achten sollten

Um die Wartezeit in einer Ablaufverfolgung nachzuverfolgen, werden Sie davon profitieren, die IP-Adresse des Clientcomputers und die IP-Adresse des DNS-Servers in Office 365 aufgezeichnet zu haben. Dies dient dem Zweck der einfacheren Ablauf Verfolgungs Filterung. Wenn Sie über einen Proxy eine Verbindung herstellen, benötigen Sie die IP-Adresse Ihres Clientcomputers, die Proxy/Ausstieg-IP-Adresse und die Office 365 DNS-IP-Adresse, um die Arbeit zu vereinfachen.  

Bei einer an Outlook.office365.com gesendeten Ping-Anforderung wird Ihnen der Name des Datencenters mitgeteilt, das die Anforderung empfängt, auch wenn ping  *möglicherweise*  keine Verbindung herstellen kann, um die Marken aufeinander folgenden ICMP-Pakete zu senden. Wenn Sie PsPing (ein kostenloses Tool zum herunterladen) und den Port (443) und möglicherweise für die Verwendung von IPv4 (-4) verwenden, erhalten Sie eine durchschnittliche Roundtrip-Zeit für gesendete Pakete. Dies funktioniert für andere URLs in den Office 365 Diensten wie `psping -4 yourSite.sharepoint.com:443` . In der Tat können Sie eine Reihe von Pings angeben, um eine größere Stichprobe für Ihren Durchschnitt zu erhalten, versuchen Sie so etwas wie `psping -4 -n 20 yourSite-my.sharepoint.com:443` .  

> [!NOTE]
> PsPing sendet keine ICMP-Pakete. Es pingt mit TCP-Paketen über einen bestimmten Port, sodass Sie eine beliebige, die Sie kennen, verwenden können, um Sie zu öffnen. Versuchen Sie in Office 365, die SSL/TLS verwendet, Port: 443 an Ihren PsPing anzufügen.

![Screenshot, der ein Ping-Auflösen von Outlook.office365.com zeigt, und ein PSPing mit dem 443, das dasselbe tut, aber auch eine 6.5 ms average RTT meldet.](../media/c64339f2-2c96-45b8-b168-c2a060430266.PNG)

Wenn Sie beim Ausführen einer Netzwerkablaufverfolgung die Seite langsam ausgeführte Office 365 geladen haben, sollten Sie eine Netmon-oder wireshark-Ablaufverfolgung für Filtern `DNS` . Dies ist eines der IPS, nach dem wir suchen.  

Hier sind die Schritte, die Sie zum Filtern Ihrer Netmon ausführen müssen, um die IP-Adresse zu erhalten (und einen Blick auf die DNS-Wartezeit werfen). In diesem Beispiel wird Outlook.office365.com verwendet, es kann aber auch die URL eines SharePoint Online-Mandanten verwendet werden (beispielsweise HiThere.SharePoint.com).  

1. Pingen Sie die URL an, `ping outlook.office365.com` und notieren Sie in den Ergebnissen den Namen und die IP-Adresse des DNS-Servers, an den die Ping-Anforderung gesendet wurde.
2. Netzwerkablaufverfolgung zum Öffnen der Seite oder Ausführen der Aktion, die Ihnen das Leistungsproblem gibt, oder, wenn Sie eine hohe Wartezeit auf dem Ping-Wert selbst sehen, Netzwerkablaufverfolgung.
3. Öffnen Sie die Ablaufverfolgung in Netmon, und Filtern Sie nach DNS (dieser Filter funktioniert auch in Wireshark, ist jedoch für den Fall anfällig `-- dns` ). Da Sie den Namen des DNS-Servers aus Ihrem Ping-Signal kennen, können Sie auch in Netmon so schnell wie folgt filtern: `DNS AND ContainsBin(FrameData, ASCII, "namnorthwest")` , das in Wireshark DNS aussieht, und Frame enthält "namnorthwest".<br/>Öffnen Sie das Antwortpaket, und klicken Sie im Fenster Netmon- **Frame Details** auf zu erweiternde **DNS** , um weitere Informationen zu erhalten. In den DNS-Informationen finden Sie die IP-Adresse des DNS-Servers, an den die Anforderung ging, in Office 365. Sie benötigen diese IP-Adresse für den nächsten Schritt (das PsPing-Tool). Entfernen Sie den Filter, klicken Sie mit der rechten Maustaste auf die DNS-Antwort in Netmon (**Frame Summary** \> **Find Conversations** \> **DNS**), um die DNS-Abfrage und-Antwort nebeneinander anzuzeigen.
4. Beachten Sie in Netmon auch die Zeit Offset Spalte zwischen der DNS-Anforderung und der Antwort. Im nächsten Schritt ist das einfache installieren und Verwenden des [PsPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) -Tools sehr praktisch, da ICMP häufig in Firewalls blockiert wird und PsPing die Wartezeit in Millisekunden elegant verfolgt. PsPing schließt eine TCP-Verbindung mit einer Adresse und einem Port ab (in unserem Fall Open Port 443).
5. Installieren Sie PsPing.
6. Öffnen Sie eine Eingabeaufforderung (starten Sie \> \> den Typ cmd oder den Windows-Schlüsseltyp \> cmd), und wechseln Sie in das Verzeichnis, in dem Sie PsPing installiert haben, um den PsPing-Befehl auszuführen. In meinen Beispielen können Sie sehen, dass ich einen "Perf"-Ordner im Stamm von C erstellt habe. Sie können das gleiche für den Schnellzugriff ausführen.
7. Geben Sie den Befehl ein, damit Sie Ihre PsPing gegen die IP-Adresse des Office 365 DNS-Servers aus ihrer früheren Netmon-Ablaufverfolgung, einschließlich der Portnummer, wie `psping -n 20 132.245.24.82:445` . Auf diese Weise erhalten Sie eine Stichprobe von 20 Pings und die durchschnittliche Wartezeit beim Beenden von PsPing.

Wenn Sie über einen Proxy Server Office 365 werden, sind die Schritte etwas anders. Sie möchten zunächst Ihren Proxy Server PsPing, um einen durchschnittlichen Latenzwert in Millisekunden an Proxy/Ausstieg und zurück zu erhalten, und dann entweder PsPing auf dem Proxy oder auf einem Computer mit direkter Internet Verbindung ausführen, um den fehlenden Wert abzurufen (der an Office 365 und zurück).  

Wenn Sie PsPing über den Proxy ausführen möchten, haben Sie zwei Millisekunden: Client Computer mit Proxy Server oder Ausgangspunkte und Proxy Server für Office 365. Und Sie sind fertig! Nun, sowieso Aufzeichnungs Werte.  

Wenn Sie PsPing auf einem anderen Clientcomputer ausführen, der über eine direkte Verbindung mit dem Internet verfügt, also ohne Proxy, haben Sie zwei Millisekunden: Clientcomputer mit Proxy Server oder Ausgangsstelle und Clientcomputer für Office 365. In diesem Fall subtrahieren Sie den Wert des Clientcomputers mit dem Proxy Server oder dem Ausgangspunkte vom Wert des Clientcomputers zu Office 365, und Sie haben die RTT-Nummern von Ihrem Clientcomputer zum Proxy Server oder Ausgangsnummer und von Proxy Server oder Ausgangsstelle auf Office 365.

Wenn Sie jedoch einen Clientcomputer in dem betroffenen Standort finden können, der direkt verbunden ist, oder den Proxy umgeht, können Sie sich entscheiden, ob das Problem dort zunächst wiedergegeben wird, und anschließend mit diesem testen.

Latenz, wie in einer Netmon-Ablaufverfolgung zu sehen ist, können diese zusätzlichen Millisekunden addiert werden, wenn Sie in einer bestimmten Sitzung ausreichend vorhanden sind.  

![Allgemeine Wartezeit in Netmon, wobei die NetMon-Standardzeit Delta-Spalte zur Rahmen Zusammenfassung hinzugefügt wurde.](../media/7ad17380-8527-4bc2-9b9b-6310cf19ba6b.PNG)

> [!NOTE]
> Ihre IP-Adresse unterscheidet sich möglicherweise von den hier gezeigten IPS, beispielsweise kann Ihr Ping etwas mehr wie 157.56.0.0/16 oder einen ähnlichen Bereich zurückgeben. Eine Liste der von Office 365 verwendeten Bereiche finden Sie unter [Office 365 URLs und IP-Adressbereiche](https://technet.microsoft.com/library/hh373144.aspx).

Denken Sie daran, alle Knoten zu erweitern (dafür gibt es eine Schaltfläche oben), wenn Sie nach suchen möchten, beispielsweise 132,245.

### <a name="proxy-authentication"></a>Proxy Authentifizierung

Dies gilt nur für Sie, wenn Sie einen Proxy Server durchlaufen. Wenn dies nicht der Fall ist, können Sie diese Schritte überspringen. Bei ordnungsgemäßer Funktion sollte die Proxyauthentifizierung konsistent in Millisekunden erfolgen. Während Spitzennutzungszeiten (zum Beispiel) sollten Sie keine intermittierende schlechte Leistung sehen.  

Wenn die Proxy Authentifizierung eingeschaltet ist, müssen Sie jedes Mal, wenn Sie eine neue TCP-Verbindung mit Office 365 herstellen, um Informationen zu erhalten, einen Authentifizierungsprozess hinter den Kulissen durchlaufen. Wenn Sie beispielsweise von Kalender zu e-Mail in Outlook Online wechseln, authentifizieren Sie sich. Wenn in SharePoint Online auf einer Seite Medien oder Daten von mehreren Standorten oder Speicherorten angezeigt werden, authentifizieren Sie sich für jede unterschiedliche TCP-Verbindung, die erforderlich ist, um die Daten zu rendern.  

In Outlook Online treten möglicherweise langsame Ladezeiten auf, wenn Sie zwischen Kalender und Ihrem Postfach wechseln oder langsame Seitenlasten in SharePoint Online. Es gibt jedoch andere Symptome, die hier nicht aufgeführt sind.

Die Proxyauthentifizierung ist eine Einstellung auf Ihrem Ausstiegs Proxy Server. Wenn ein Leistungsproblem mit Office 365 auftritt, müssen Sie sich an Ihr Netzwerkteam wenden.  

#### <a name="tools"></a>Tools

- NetMon
- Wireshark

#### <a name="what-to-look-for"></a>Worauf Sie achten sollten

Die Proxy Authentifizierung findet immer dann statt, wenn eine neue TCP-Sitzung gesponnen werden muss, um Dateien oder Informationen vom Server anzufordern oder um Informationen zu liefern. Beispielsweise kann Proxyauthentifizierung bei HTTP GET-oder HTTP POST-Anforderungen angezeigt werden. Wenn Sie die Frames sehen möchten, in denen Sie Anforderungen in Ihrer Ablaufverfolgung authentifizieren, fügen Sie die Spalte "NTLMSSP Summary" zu Netmon und Filter for hinzu  `.property.NTLMSSPSummary` . Um zu sehen, wie lange die Authentifizierung dauert, fügen Sie die Zeit Delta-Spalte hinzu.

So fügen Sie Netmon eine Spalte hinzu:

1. Klicken Sie mit der rechten Maustaste auf eine Spalte wie **Description**.
2. Klicken Sie auf **Spalten auswählen**.
3. Suchen Sie in der Liste nach _NTLMSSP Summary_ and _time Delta_ , und klicken Sie auf **Hinzufügen**.
4. Verschiebt die neuen Spalten vor oder hinter der _Beschreibungs_ Spalte, sodass Sie sie nebeneinander lesen können.
5. Klicken Sie auf **OK**.

Auch wenn Sie die Spalte nicht hinzufügen, kann der Netmon-Filter verwendet werden. Die Problembehandlung wird jedoch viel einfacher, wenn Sie sehen können, in welcher Phase der Authentifizierung Sie sich befinden.

Achten Sie bei der Suche nach Instanzen der Proxy Authentifizierung darauf, dass Sie alle Frames untersuchen, bei denen eine NTLM-Herausforderung vorliegt, oder ob eine Authentifizierungsmeldung vorhanden ist. Klicken Sie bei Bedarf mit der rechten Maustaste auf den bestimmten Datenverkehr, und suchen Sie Unterhaltungen \> TCP. Beachten Sie die Time Delta-Werte in diesen Unterhaltungen.

![NetMon-Ablaufverfolgung mit Proxyauthentifizierung, gefiltert nach Unterhaltung.](../media/b640f176-0a52-4bbb-972e-60fb3d6aece2.PNG)

Eine Verzögerung von vier Sekunden bei der Proxyauthentifizierung, wie Sie in Wireshark angezeigt wird. Das **Zeit Delta von der vorherigen angezeigten Frame** Spalte wurde durch Klicken mit der rechten Maustaste auf das Feld mit dem gleichen Namen in den Details des Frames und Auswählen von als Spalte hinzufügen erstellt.  <br/> ![In Wireshark kann die Spalte "Zeit Delta von vorherigem angezeigten Frame" durch Klicken mit der rechten Maustaste auf das Feld mit dem gleichen Namen in den Details des Frames und Auswählen von "als Spalte hinzufügen" erfolgen.](../media/f5b7bde4-8067-4ee0-bc7f-e9062ce1ba6f.PNG)

### <a name="dns-performance"></a>DNS-Leistung

Die Namensauflösung funktioniert am besten und am schnellsten, wenn Sie so nah wie möglich am Land des Clients stattfindet.

Wenn die DNS-Namensauflösung in Übersee stattfindet, kann Sie Sekunden zu Seitenlasten hinzufügen. Im Idealfall erfolgt die Namensauflösung in unter 100M. Wenn dies nicht der Fall ist, sollten Sie weitere Untersuchungen durchführen.

> [!TIP]
> Sind Sie nicht sicher, wie die Client Konnektivität in Office 365 funktioniert? Sehen Sie sich das Referenzdokument zur Client Konnektivität [hier](https://technet.microsoft.com/library/dn741250.aspx)an.

#### <a name="tools"></a>Tools

- NetMon
- Wireshark
- PsPing

#### <a name="what-to-look-for"></a>Worauf Sie achten sollten

Die Analyse der DNS-Leistung ist in der Regel ein weiterer Auftrag für eine Netzwerkablaufverfolgung. PsPing ist jedoch auch hilfreich bei der Entscheidung in oder aus einer möglichen Ursache.

DNS-Datenverkehr basiert auf TCP-und UDP-Anforderungen und Antworten sind eindeutig mit einer ID gekennzeichnet, mit der eine bestimmte Anforderung mit der spezifischen Antwort abgeglichen werden kann. Wenn SharePoint Online beispielsweise einen Netzwerknamen oder eine URL auf einer Webseite verwendet, wird DNS-Datenverkehr angezeigt. Als Faustregel wird der Großteil dieses Datenverkehrs, außer beim Übertragen von Zonen, über UDP ausgeführt.

Sowohl in Netmon als auch in Wireshark ist der grundlegendste Filter, mit dem Sie den DNS-Datenverkehr betrachten können, einfach `dns` . Achten Sie darauf, bei der Angabe des Filters Kleinbuchstaben zu verwenden. Denken Sie daran, den DNS-Auflösungscache zu leeren, bevor Sie mit dem reproduzieren des Problems auf dem Clientcomputer beginnen. Wenn Sie beispielsweise eine langsame SharePoint Online Seitenlast für die Startseite haben, sollten Sie alle Browser schließen, einen neuen Browser öffnen, die Ablaufverfolgung starten, den DNS-Auflösungscache leeren und zu Ihrer SharePoint Online Website wechseln. Sobald die gesamte Seite aufgelöst wird, sollten Sie die Ablaufverfolgung beenden und speichern.

![Ein grundlegender Filter für DNS in Netmon ist DNS.](../media/1bebc118-ca13-45f3-803f-ab73e7af401d.png)

Sie möchten sich den Zeit Offset hier ansehen. Und es kann hilfreich sein, die **Zeit Delta** -Spalte zu Netmon hinzuzufügen, was Sie tun können, indem Sie die folgenden Schritte ausführen:

1. Klicken Sie mit der rechten Maustaste auf eine Spalte wie **Description**.
2. Klicken Sie auf **Spalten auswählen**.
3. Suchen Sie in der Liste nach _Zeit Delta_ , und klicken Sie auf **Hinzufügen**.
4. Positionieren Sie die neue Spalte vor oder hinter der Spalte _Description_ , sodass Sie sie nebeneinander lesen können.
5. Klicken Sie auf **OK**.

Wenn Sie eine Abfrage von Interesse finden, können Sie sie isolieren, indem Sie im Bereich "Frame Details" mit der rechten Maustaste auf diese Abfrage klicken und dann unter **Haltungen** \> **DNS**suchen auswählen. Beachten Sie, dass der Bereich "Netzwerk Unterhaltungen" im Protokoll des UDP-Datenverkehrs direkt zu der jeweiligen Unterhaltung springt.

![Eine Netmon-Ablaufverfolgung von Outlook Online-Laden, gefiltert nach DNS, und Verwenden von "Unterhaltungen suchen" und "DNS" zum Einschränken der Ergebnisse.](../media/763cf20e-7b48-4a37-9449-c9978cfe118b.PNG)

In Wireshark können Sie eine Spalte für die DNS-Zeit erstellen. Nehmen Sie Ihre Ablaufverfolgung (oder öffnen Sie eine Ablaufverfolgung) in Wireshark, und Filtern Sie nach `dns` , oder, hilfreicher,  `dns.time` . Klicken Sie auf eine beliebige DNS-Abfrage, und erweitern Sie im Bereich Details anzeigen die  `Domain Name System (response)` Details. Sie sehen ein Feld für die Zeit (beispielsweise `[Time: 0.001111100 seconds]` . Klicken Sie mit der rechten Maustaste auf dieses Mal, und wählen Sie **als Spalte anwenden**aus. Dadurch erhalten Sie eine **Zeit** Spalte für eine schnellere Sortierung Ihrer Ablaufverfolgung. Klicken Sie auf die neue Spalte, um nach absteigenden Werten zu sortieren, um zu sehen, welcher DNS-Anruf am längsten Auflösungsvorgang dauerte.

[Eine Durchsuchen von SharePoint Online gefiltert in Wireshark von (klein geschrieben) DNS. Time, wobei die Zeit aus den Details in eine Spalte und aufsteigend sortiert wird.](../media/1439dcc2-12ff-4ee2-9ef3-1484cf79c384.PNG)

Wenn Sie weitere Untersuchungen zur DNS-Auflösungszeit durchführen möchten, versuchen Sie es mit einem PsPing gegen den von TCP verwendeten DNS-Port (beispielsweise  `psping <IP address of DNS server>:53` ). Wird weiterhin ein Leistungsproblem angezeigt? Wenn Sie dies tun, ist das Problem eher ein größeres Netzwerkproblem als ein Problem mit der spezifischen DNS-Anwendung, auf die Sie die Lösung durchführen. Es ist auch erwähnenswert, dass ein Ping zu Outlook.office365.com Ihnen mitteilt, wo DNS-Namensauflösung für Outlook Online stattfindet (beispielsweise Outlook-namnorthwest.office365.com).

Wenn das Problem DNS-spezifisch aussieht, kann es erforderlich sein, sich an Ihre IT-Abteilung zu wenden, um DNS-Konfigurationen und DNS-Weiterleitungen zu prüfen, um dieses Problem weiter zu untersuchen.

### <a name="proxy-scalability"></a>Proxy Skalierbarkeit

Dienste wie Outlook online in Office 365 gewähren Clients mehrere lang Zeit Verbindungen. Daher kann jeder Benutzer mehr Verbindungen verwenden, die eine längere Lebensdauer erfordern.  

#### <a name="tools"></a>Tools

Mathematik  

#### <a name="what-to-look-for"></a>Worauf Sie achten sollten

Es gibt keine spezielle Netzwerkablaufverfolgung oder Problembehandlungstool. Stattdessen basiert es auf Bandbreiten Berechnungen, die Einschränkungen und anderen Variablen zugewiesen sind.  

### <a name="tcp-max-segment-size"></a>TCP-max-Segment Größe

In der SYN-SYN/ACK gefunden.  Überprüfen Sie in einer Leistungsnetzwerk Ablaufverfolgung, die Sie durchgeführt haben, um sicherzustellen, dass TCP-Pakete so konfiguriert sind, dass die maximale Datenmenge möglich ist.

Das Ziel besteht darin, eine MSS von 1460 Bytes für die Übertragung von Daten anzuzeigen. Wenn Sie sich hinter einem Proxy befinden oder eine NAT verwenden, denken Sie daran, diesen Test von Client zu Proxy/Ausstieg/NAT auszuführen, und von Proxy/Ausstieg/NAT zu Office 365, um optimale Ergebnisse zu erzielen! Dabei handelt es sich um unterschiedliche TCP-Sitzungen.

#### <a name="tools"></a>Tools

NetMon

#### <a name="what-to-look-for"></a>Worauf Sie achten sollten

TCP max Segment Size (MSS) ist ein weiterer Parameter des drei-Wege-Handshakes in ihrer Netzwerkablaufverfolgung, d. h., Sie finden die benötigten Daten im SYN-SYN/ACK-Paket. MSS ist eigentlich ziemlich einfach zu sehen.

Öffnen Sie eine Leistungsnetzwerk Ablaufverfolgung, die Sie haben, und suchen Sie nach der Verbindung, über die Sie neugierig sind, oder zeigen Sie das Leistungsproblem.

> [!NOTE]
> Wenn Sie eine Ablaufverfolgung suchen und den für Ihre Unterhaltung relevanten Datenverkehr ermitteln möchten, Filtern Sie die IP-Adresse des Clients oder die IP-Adresse des Proxyservers oder Ausgangs Points oder beides. Wenn Sie direkt wechseln, müssen Sie die URL, die Sie testen, auf die IP-Adresse von Office 365 in der Ablaufverfolgung pingen und nach ihr filtern.

Sehen Sie sich die Trace Second-Hand an? Verwenden Sie Filter, um sich selbst zu orientieren. Führen Sie in Netmon eine Suche basierend auf der URL aus, beispielsweise `Containsbin(framedata, ascii, "sphybridExample")` beachten Sie die Framenummer.

Verwenden Sie in Wireshark so etwas wie  `frame contains "sphybridExample"` . Wenn Sie feststellen, dass Sie den Remote-WinSock (RWS)-Datenverkehr gefunden haben (er kann als [PSH, ACK] in Wireshark angezeigt werden), denken Sie daran, dass die RWs-Verbindung kurz vor relevanten SYN-SYN/ACKs zu sehen ist, wie weiter oben beschrieben.

An dieser Stelle können Sie die Framenummer aufzeichnen, den Filter löschen und im Fenster Netzwerk Unterhaltungen in Netmon auf **gesamter Datenverkehr** klicken, um die nächste SYN-Ansicht anzuzeigen.

Wenn Sie zum Zeitpunkt der Ablaufverfolgung keine IP-Adressinformationen erhalten haben, erhalten Sie von der Suche nach Ihrer URL in der Ablaufverfolgung ( `sphybridExample-my.sharepoint.com` beispielsweise zum Beispiel) IP-Adressen, nach denen Sie filtern können.

Suchen Sie die Verbindung in der Ablaufverfolgung, die Sie sehen möchten. Dies ist möglich, indem Sie entweder die Ablaufverfolgung überprüfen, durch IP-Adressen filtern oder bestimmte Unterhaltungs-IDs mithilfe des Fensters Netzwerk Unterhaltungen in Netmon auswählen. Wenn Sie das SYN-Paket gefunden haben, erweitern Sie TCP (in NetMon) oder Transmission Control Protocol (in Wireshark) im Bereich Frame Details. Erweitern Sie TCP-Optionen und MaxSegmentSize. Suchen Sie den zugehörigen SYN-ACK-Frame, und erweitern Sie TCP-Optionen und MaxSegmentSize. Der kleinere der beiden Werte ist die maximale Segment Größe. In diesem Bild verwende ich die integrierte Spalte in Netmon, die als TCP-Problembehandlung bezeichnet wird.  

![Netzwerkablaufverfolgung in Netmon mithilfe der integrierten Spalten gefiltert.](../media/e073df13-71f8-497a-83b4-bb9f70bd9833.PNG)

Die integrierte Spalte befindet sich oben im Bereich " **Frame Details** ". (Um wieder zur Normalansicht zurückzukehren, klicken Sie erneut auf **Spalten** , und wählen Sie dann **Zeitzone**aus.)

![Hier finden Sie die Dropdownliste Spalten für die Option TCP-Problembehandlung (oberhalb der Rahmen Zusammenfassung).](../media/64fd4baa-a872-4f07-b959-752d7d37fd62.PNG)

Hier ist eine gefilterte Ablaufverfolgung in Wireshark. Es gibt einen spezifischen Filter für den MSS-Wert ( `tcp.options.mss` ). Die Frames eines SYN-, SYN/ACK-Handshakes werden am unteren Rand des Wireshark-Äquivalents mit Frame-Details verknüpft (also Frame 47 ACK, Links zu 46 SYN/ACK, Links zu 43 SYN), um diese Art von Arbeit zu vereinfachen.

![Trace gefiltert in Wireshark durch TCP. Options. MSS für maximale Segment Größe (MSS).](../media/51e278db-801b-48bc-9b68-87cf92f03fd6.PNG)

Wenn Sie die **selektive Bestätigung** (Nächstes Thema in dieser Matrix) überprüfen möchten, schließen Sie die Ablaufverfolgung nicht!

### <a name="selective-acknowledgment"></a>Selektive Bestätigung

In der SYN-SYN/ACK gefunden. Muss in SYN und SYN/ACK als zulässig gemeldet werden. Selective Quittierung (Sack) ermöglicht eine reibungslosere Weitergabe von Daten, wenn ein Paket oder Pakete fehlen. Geräte können dieses Feature deaktivieren, was zu Leistungsproblemen führen kann.

Wenn Sie sich hinter einem Proxy befinden oder eine NAT verwenden, denken Sie daran, diesen Test von Client zu Proxy/Ausstieg/NAT auszuführen, und von Proxy/Ausstieg/NAT zu Office 365, um optimale Ergebnisse zu erzielen! Dabei handelt es sich um unterschiedliche TCP-Sitzungen.

#### <a name="tools"></a>Tools

NetMon

#### <a name="what-to-look-for"></a>Worauf Sie achten sollten

Die selektive Bestätigung (Sack) ist ein weiterer Parameter im SYN-SYN/ACK-Handshake. Sie können die Ablaufverfolgung auf viele Arten auf SYN-SYN/ACK filtern.

Suchen Sie die Verbindung in der Ablaufverfolgung, die Sie anzeigen möchten, indem Sie die Ablaufverfolgung überprüfen, die Filterung nach IP-Adressen durchführen oder auf eine Unterhaltungs-ID im Fenster Netzwerk Unterhaltungen in Netmon klicken. Nachdem Sie das SYN-Paket gefunden haben, erweitern Sie im Abschnitt Frame Details den Knoten TCP in Netmon oder das Transmission Control Protocol in Wireshark. Erweitern Sie TCP-Optionen und dann Sack. Suchen Sie den zugehörigen SYN-ACK-Frame, und erweitern Sie TCP-Optionen und das zugehörige Feld Sack. Stellen Sie sicher, dass Sack in SYN und SYN/ACK zulässig ist. Hier sind Sack Werte, die in Netmon und wireshark angezeigt werden.

![Selektive Bestätigung (Sack) in Netmon als Ergebnis von TCP. Flags. SYN = = 1.](../media/216f556f-5031-4ed2-b066-a0d9b3251fa2.PNG)

![Sack wie in Wireshark mit dem Filter "TCP. Flags. SYN = = 1" gesehen.](../media/0a6e26e5-43dc-403b-adc9-3349a55f4e4b.PNG)

### <a name="dns-geolocation"></a>DNS-geolocation

Wo auf der Welt Office 365 versucht, Ihren DNS-Anruf zu lösen, hat Ihre Verbindungsgeschwindigkeit zur folgen.

In Outlook Online wird nach Abschluss der ersten DNS-Suche der Speicherort dieses DNS verwendet, um eine Verbindung mit Ihrem nächsten Datencenter herzustellen. Sie werden mit einem Outlook Online-CAS-Server verbunden, der das Backbone-Netzwerk zum Herstellen einer Verbindung mit dem Rechenzentrum (DC) verwendet, in dem Ihre Daten gespeichert werden. Dies ist schneller.

Wenn Sie auf SharePoint Online zugreifen, wird ein Benutzer, der ins Ausland reist, an sein aktives Rechenzentrum weitergeleitet, das ist der DC, dessen Standort auf dem Home-Base-Basis Wert Ihres SPO-Mandanten basiert (also ein DC in den USA, wenn der Benutzer wenn USA basiert).

Lync Online verfügt über aktive Knoten in mehr als einem DC gleichzeitig. Wenn Anforderungen für lync Online-Instanzen gesendet werden, bestimmt das DNS von Microsoft, wo in der Welt die Anforderung stammt, und gibt IP-Adressen aus dem nächstgelegenen regionalen DC zurück, in dem lync Online aktiv ist.

> [!TIP]
> Sie müssen mehr darüber wissen, wie Clients eine Verbindung mit Office 365 herstellen? Sehen Sie sich den Referenzartikel über die [Client Konnektivität](https://technet.microsoft.com/library/dn741250.aspx) (und seine hilfreichen Grafiken) an.

#### <a name="tools"></a>Tools

- Ping
- PsPing

#### <a name="what-to-look-for"></a>Worauf Sie achten sollten

Anforderungen für die Namensauflösung von den DNS-Servern des Clients zu den Microsoft-DNS-Servern sollten in den meisten Fällen dazu führen, dass Microsoft DNS die IP-Adresse eines regionalen Datencenters (DC) zurückgibt. Was bedeutet das für Sie? Wenn sich Ihr Hauptsitz in Bangalore, Indien befindet, aber Sie in den USA Reisen, wenn Ihr Browser eine Anforderung für Outlook Online stellt, sollten die Microsoft-DNS-Server Ihnen IP-Adressen an Rechenzentren in den Vereinigten Staaten übergeben – ein regionales Rechenzentrum. Wenn e-Mails aus Outlook benötigt werden, werden diese Daten durch das schnelle Backbone-Netzwerk von Microsoft zwischen den Rechenzentren Reisen.

DNS funktioniert am schnellsten, wenn die Namensauflösung so nah wie möglich am Speicherort des Benutzers erfolgt. Wenn Sie in Europa sind, möchten Sie zu einem Microsoft-DNS in Europa wechseln und (im Idealfall) mit einem Rechenzentrum in Europa umgehen. Die Leistung eines Clients in Europa, der zu DNS und einem Rechenzentrum in Amerika wechseln wird, ist langsamer.

Führen Sie das Ping-Tool gegen Outlook.office365.com aus, um zu bestimmen, an welcher Stelle in der Welt Ihre DNS-Anforderung weitergeleitet wird. Wenn Sie sich in Europa befinden, sollten Sie eine Antwort von so etwas wie Outlook-emeawest.office365.com sehen. In Nord-und Südamerika erwarten Sie so etwas wie Outlook-namnorthwest.office365.com.

Öffnen Sie die Eingabeaufforderung auf dem Clientcomputer (über Start \> Ausführen \> cmd oder Windows \> -Schlüsseltyp cmd). Geben Sie Ping Outlook.office365.com ein, und drücken Sie die EINGABETASTE. Denken Sie daran, um-4 anzugeben, wenn Sie den Ping über IPv4 angeben möchten. Es kann sein, dass Sie nicht über die ICMP-Pakete eine Antwort erhalten, aber Sie sollten den Namen des DNS sehen, an das die Anforderung weitergeleitet wurde. Wenn Sie die Latenz Nummern für diese Verbindung anzeigen möchten, versuchen Sie PsPing mit der IP-Adresse des Servers, der von Ping zurückgegeben wird.  

![Ping von Outlook.office365.com mit Auflösung in Outlook-namnorthwest.](../media/06c944d5-6159-43ec-aa31-757770695e8b.PNG)

![PSPing der vom Ping-Befehl an Outlook.office365.com zurückgegebenen IP-Adresse, die eine durchschnittliche Wartezeit von 28 Millisekunden anzeigt.](../media/f2b25a75-1a87-4479-b8a7-fa4375683507.PNG)

### <a name="office-365-application-troubleshooting"></a>Problembehandlung bei Office 365 Anwendungen

#### <a name="tools"></a>Tools

- NetMon
- HTTPWatch
- F12-Konsole im Browser

In diesem netzwerkspezifischen Artikel werden keine Tools behandelt, die in der anwendungsspezifischen Problembehandlung verwendet werden. Sie finden jedoch Ressourcen, [die Sie auf dieser Seite](https://support.office.com/article/Network-planning-and-performance-tuning-for-Office-365-e5f1228c-da3c-4654-bf16-d163daee8848)verwenden *können* .

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Häufig gestellte Fragen zu Office 365-Endpunkten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
