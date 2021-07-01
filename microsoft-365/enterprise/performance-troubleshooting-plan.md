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
description: Dieser Artikel kann Ihnen helfen, Office 365 Leistungsprobleme zu beheben und sogar einige der häufigsten Probleme zu beheben.
ms.openlocfilehash: 6ef459d6469881c71ea7d1da3a32eb42eb3ead6b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229935"
---
# <a name="performance-troubleshooting-plan-for-office-365"></a>Behandlung von Leistungsproblemen – Plan für Office 365

Müssen Sie die erforderlichen Schritte kennen, um Verzögerungen, Blockaden und langsame Leistung zwischen SharePoint Online, OneDrive for Business, Exchange Online oder Skype for Business Online und Ihrem Clientcomputer zu erkennen und zu beheben? Bevor Sie den Support anrufen, können Sie in diesem Artikel Office 365 Leistungsprobleme beheben und sogar einige der häufigsten Probleme beheben.

Dieser Artikel ist eigentlich ein Beispielaktionsplan, mit dem Sie wertvolle Daten zu Ihrem Leistungsproblem erfassen können, während dies geschieht. Einige der wichtigsten Probleme sind auch in diesem Artikel enthalten.

Wenn Sie noch keine Informationen zur Netzwerkleistung haben und einen langfristigen Plan zur Überwachung der Leistung zwischen Ihren Clientcomputern und Office 365 erstellen möchten, werfen Sie einen Blick auf [Office 365 Leistungsoptimierung und Problembehandlung – Administrator- und IT-Pro.](performance-tuning-using-baselines-and-history.md)

## <a name="sample-performance-troubleshooting-action-plan"></a>Beispielaktionsplan zur Problembehandlung bei der Leistung

Dieser Aktionsplan enthält zwei Teile: eine Vorbereitungsphase und eine Protokollierungsphase. Wenn sie gerade ein Leistungsproblem haben und die Datensammlung durchführen müssen, können Sie sofort mit der Verwendung dieses Plans beginnen.

### <a name="prepare-the-client-computer"></a>Vorbereiten des Clientcomputers

- Suchen Sie einen Clientcomputer, der das Leistungsproblem reproduzieren kann. Dieser Computer wird während der Problembehandlung verwendet.
- Notieren Sie sich die Schritte, die das Leistungsproblem verursachen, damit Sie zum Testen bereit sind.
- Installieren Sie Tools zum Sammeln und Aufzeichnen von Informationen:
  - Installieren Sie [Netmon 3.4](https://www.microsoft.com/download/details.aspx?id=4865) (oder verwenden Sie ein entsprechendes Netzwerkablaufverfolgungstool).
  - Installieren Sie die kostenlose Basic Edition von [HTTPWatch](https://www.httpwatch.com/download/) (oder verwenden Sie ein entsprechendes Netzwerkablaufverfolgungstool).
  - Verwenden Sie eine Bildschirmaufzeichnung, oder führen Sie den Steps Recorder (PSR.exe) aus, der in Windows Vista und höher enthalten ist, um einen Überblick über die Schritte zu behalten, die Sie während des Tests ausführen.

### <a name="log-the-performance-issue"></a>Protokollieren des Leistungsproblems

- Schließen Sie alle fremden Internetbrowser.
- Starten Sie den Steps Recorder oder eine andere Bildschirmaufzeichnung.
- Starten Sie Die Netmon-Erfassung (oder das Netzwerkablaufverfolgungstool).
- Löschen Sie den DNS-Cache auf dem Clientcomputer über die Befehlszeile, indem Sie "ipconfig/flushdns" eingeben.
- Starten Sie eine neue Browsersitzung, und aktivieren Sie HTTPWatch.
- Optional: Wenn Sie Exchange Online testen, führen Sie das Tool Exchange Client Performance Analyzer in der Office 365 Admin-Konsole aus.
- Reproduzieren Sie die genauen Schritte, die das Leistungsproblem verursachen.
- Beenden Sie die Ablaufverfolgung Ihres Netmon oder eines anderen Tools.
- Führen Sie an der Befehlszeile eine Ablaufverfolgungsroute zu Ihrem Office 365-Abonnement aus, indem Sie den folgenden Befehl eingeben und dann die EINGABETASTE drücken:

  ``` cmd
  tracert <subscriptionname>.onmicrosoft.com
  ```

- Beenden Sie den Steps Recorder, und speichern Sie das Video. Achten Sie darauf, das Datum und die Uhrzeit der Aufnahme einzuschließen und anzugeben, ob sie eine gute oder schlechte Leistung zeigt.
- Speichern Sie die Ablaufverfolgungsdateien. Achten Sie erneut darauf, das Datum und die Uhrzeit der Aufnahme einzuschließen und anzugeben, ob sie eine gute oder schlechte Leistung zeigt.

Wenn Sie nicht mit der Ausführung der in diesem Artikel erwähnten Tools vertraut sind, machen Sie sich keine Sorgen, da wir diese Schritte als Nächstes bereitstellen. Wenn Sie diese Art der Netzwerkerfassung gewohnt sind, können Sie mit dem Sammeln von [Basisplänen](performance-tuning-using-baselines-and-history.md#how-to-collect-baselines)übergehen, in dem das Filtern und Lesen der Protokolle beschrieben wird.

### <a name="flush-the-dns-cache-first"></a>Leeren des DNS-Caches zuerst

Warum? Indem Sie den DNS-Cache leeren, starten Sie Ihre Tests mit einem sauberen Schiefer. Durch Löschen des Caches wird der Inhalt des DNS-Resolvers auf die aktuellsten Einträge zurückgesetzt. Denken Sie daran, dass beim Leeren keine HOSTs-Dateieinträge entfernt werden. Wenn Sie HOST-Dateieinträge umfassend verwenden, sollten Sie diese Einträge in eine Datei in einem anderen Verzeichnis kopieren und dann die HOST-Datei leeren.

#### <a name="flush-your-dns-resolver-cache"></a>Leeren des DNS-Resolvercaches

1. Öffnen Sie die Eingabeaufforderung (start  \> **Run** \> **cmd** oder **Windows key** \> **cmd**).
2. Geben Sie den folgenden Befehl ein, und drücken Sie die EINGABETASTE:

    ``` cmd
    ipconfig /flushdns
    ```

## <a name="netmon"></a>Netmon

Das Netzwerküberwachungstool[(Netmon)](https://www.microsoft.com/download/details.aspx?id=4865)von Microsoft analysiert Pakete, d. h. Datenverkehr, der zwischen Computern in Netzwerken übergibt. Durch die Verwendung von Netmon zum Nachverfolgen von Datenverkehr mit Office 365 können Sie Paketheader erfassen, anzeigen und lesen, zwischengeschaltete Geräte identifizieren, wichtige Einstellungen auf der Netzwerkhardware überprüfen, nach verworfenen Paketen suchen und den Datenverkehrsfluss zwischen Computern in Ihrem Unternehmensnetzwerk und Office 365 verfolgen. Da der tatsächliche Text des Datenverkehrs verschlüsselt ist, d. h., er (wird über SSL/TLS an Port 443 übertragen), können Sie die gesendeten Dateien nicht lesen. Stattdessen erhalten Sie eine ungefilterte Ablaufverfolgung des Pfads, den das Paket einnimmt, was Ihnen dabei helfen kann, das Problemverhalten nachzuverfolgen.

Stellen Sie sicher, dass Sie derzeit keinen Filter anwenden. Führen Sie stattdessen die Schritte aus, und demonstrieren Sie das Problem, bevor Sie die Ablaufverfolgung beenden und speichern.

Öffnen Sie nach der Installation von Netmon 3.4 das Tool, und führen Sie die folgenden Schritte aus:

### <a name="take-a-netmon-trace-and-reproduce-the-issue"></a>Erstellen einer Netmon-Ablaufverfolgung und Reproduzieren des Problems

1. Starten Sie Netmon 3.4.
Es gibt drei Bereiche auf der **Startseite:** **Zuletzt verwendete Erfassungen,** **Ausgewählte Netzwerke** und erste Schritte mit Microsoft Network **Monitor 3.4. Beachten Sie**. Im Bereich "Netzwerke auswählen" erhalten Sie auch eine Liste der Standardnetzwerke, aus denen Sie erfassen können. Stellen Sie sicher, dass hier Netzwerkkarten ausgewählt sind.

2. Klicken Sie oben auf der **Startseite** auf **"Neue Erfassung".** Dadurch wird eine neue Registerkarte neben der Registerkarte **"Startseite"** mit dem Namen **"Capture 1"** hinzugefügt.
![Die Benutzeroberfläche von Netmon, auf der die Schaltflächen "Neue Erfassung", "Start" und "Beenden" hervorgehoben sind.](../media/d4527d84-62ec-4301-82d5-e0166ff71f20.PNG)

3. Klicken Sie auf der Symbolleiste auf **"Start",** um eine einfache Aufnahme zu erstellen.

4. Reproduzieren Sie die Schritte, die ein Leistungsproblem darstellen.

5. Klicken  Sie auf \> **"Datei** speichern \> **unter** beenden". Denken Sie daran, Datum und Uhrzeit mit der Zeitzone anzugeben und zu erwähnen, ob dies eine schlechte oder gute Leistung zeigt.

## <a name="httpwatch"></a>HTTPWatch

[HTTPWatch](https://www.httpwatch.com/download/) wird in Rechnung gestellt, und es wird eine kostenlose Edition bereitgestellt. Die kostenlose Basic Edition deckt alles ab, was Sie für diesen Test benötigen. HTTPWatch überwacht den Netzwerkdatenverkehr und die Seitenladezeit direkt im Browserfenster. HTTPWatch ist ein Plug-In in Internet Explorer, das die Leistung grafisch beschreibt. Die Analyse kann in HTTPWatch Studio gespeichert und angezeigt werden.

> [!NOTE]
> Wenn Sie einen anderen Browser verwenden, z. B. Firefox, Google Chrome, oder wenn Sie HTTPWatch nicht in Internet Explorer installieren können, öffnen Sie ein neues Browserfenster, und drücken Sie F12 auf Ihrer Tastatur. Das Entwicklertool sollte unten im Browser angezeigt werden. Wenn Sie Opera verwenden, drücken Sie STRG+UMSCHALT+I für den Webinspektor, klicken Sie dann auf die Registerkarte **"Netzwerk",** und schließen Sie die unten beschriebenen Tests ab. Die Informationen unterscheiden sich geringfügig, die Ladezeiten werden jedoch weiterhin in Millisekunden angezeigt. > HTTPWatch ist auch bei Problemen mit SharePoint Ladezeiten von Onlineseiten sehr hilfreich.

### <a name="run-httpwatch-and-reproduce-the-issue"></a>Ausführen von HTTPWatch und Reproduzieren des Problems

HTTPWatch ist ein Browser-Plug-In, sodass das Verfügbarmachen des Tools im Browser für jede Version von Internet Explorer etwas anders ist. In der Regel finden Sie HTTPWatch unter der Befehlsleiste im Internet Explorer-Browser. Wenn das HTTPWatch-Plug-In in Ihrem Browserfenster nicht angezeigt wird, überprüfen Sie die Version Ihres Browsers, indem Sie auf **Hilfe** zu \> oder in späteren Versionen von Internet Explorer auf das Zahnradsymbol und über **Internet Explorer** klicken. Klicken Sie zum Starten der **Befehlsleiste** mit der rechten Maustaste auf die Menüleiste in Internet Explorer, und klicken Sie auf **"Befehlsleiste".**

In der Vergangenheit war HTTPWatch sowohl den Befehlen als auch den Explorer-Leisten zugeordnet. Wenn das Symbol (auch nach dem Neustart) nach der Installation nicht sofort angezeigt wird, überprüfen Sie die **Tools** und die Symbolleisten für das Symbol. Denken Sie daran, dass Symbolleisten angepasst und Optionen hinzugefügt werden können.

![Befehlssymbolleiste von Internet Explorer, auf der das HTTPWatch-Symbol angezeigt wird.](../media/198590b0-d7b1-4bff-a6ad-e4ec3a1e83df.png)

1. Starten Sie HTTPWatch in einem Internet Explorer-Browserfenster. Er wird unten in diesem Fenster an den Browser angedockt angezeigt. Klicken Sie auf **"Aufzeichnen".**

2. Reproduzieren Sie die genauen Schritte, die für das Leistungsproblem erforderlich sind. Klicken Sie in HTTPWatch auf die Schaltfläche **"Beenden".**

3. **Speichern Sie** httpWatch oder **Senden per E-Mail**. Denken Sie daran, die Datei so zu benennen, dass sie Datums- und Uhrzeitinformationen und einen Hinweis darauf enthält, ob Ihre Überwachung eine Demonstration der guten oder schlechten Leistung enthält.

![HTTPWatch mit der Registerkarte "Netzwerk" für eine Seitenauslastung der Office 365 Startseite.](../media/021a2c64-d581-49fd-adf4-4c364f589d75.PNG)

Dieser Screenshot stammt aus der Professional-Version von HTTPWatch. Sie können Ablaufverfolgungen in der Standardversion auf einem Computer mit einer Professional-Version öffnen und dort lesen. Zusätzliche Informationen können über die Ablaufverfolgung über diese Methode verfügbar sein.

## <a name="problem-steps-recorder"></a>Problemschrittaufzeichnung

Mit der Schrittaufzeichnung (PSR.exe) können Sie Probleme aufzeichnen, sobald sie auftreten. Es ist ein sehr nützliches Tool und sehr einfach auszuführen.

### <a name="run-problem-steps-recorder-psrexe-to-record-your-work"></a>Ausführen des Problemschritt-Recorders (PSR.exe) zum Aufzeichnen Ihrer Arbeit

1. Verwenden  Sie entweder den \> **Startausführungstyp** \> **PSR.exe** \> **OK,** oder klicken Sie auf den **Windows Tastentyp** PSR.exe, und drücken Sie dann die \>  \> EINGABETASTE.

2. Wenn das kleine PSR.exe Fenster angezeigt wird, klicken Sie auf **"Datensatz starten",** und reproduzieren Sie die Schritte, die das Leistungsproblem reproduzieren. Sie können Kommentare nach Bedarf hinzufügen, indem Sie auf **"Kommentare hinzufügen"** klicken.

3. Klicken Sie auf **"Datensatz beenden",** wenn Sie die Schritte abgeschlossen haben. Wenn es sich bei dem Leistungsproblem um ein Seitenrendering handelt, warten Sie, bis die Seite gerendert wird, bevor Sie die Aufzeichnung beenden.

4. Klicken Sie auf **Speichern**.

![Screenshot des Steps Recorder oder PSR.exe.](../media/8542b0aa-a3ff-4718-8dc4-43f5521c6c34.PNG)

Datum und Uhrzeit werden für Sie aufgezeichnet. Dadurch wird Ihre PSR rechtzeitig mit Ihrer Netmon-Ablaufverfolgung und HTTPWatch verknüpft und hilft bei der präzisen Problembehandlung. Das Datum und die Uhrzeit im PSR-Datensatz können anzeigen, dass eine Minute zwischen der Anmeldung und dem Browsen der URL und dem teilweisen Rendern der Administratorwebsite vergangen ist, z. B.

## <a name="read-your-traces"></a>Lesen Ihrer Ablaufverfolgungen

Es ist nicht möglich, alles über die Problembehandlung bei Netzwerk- und Leistungsproblemen zu vermitteln, die jemand über einen Artikel wissen müsste. Eine gute Leistung erfordert Erfahrung und Wissen darüber, wie Ihr Netzwerk funktioniert und in der Regel funktioniert. Es ist jedoch möglich, eine Liste der wichtigsten Probleme zu runden und zu zeigen, wie Tools es Ihnen erleichtern können, die häufigsten Probleme zu beseitigen.

Wenn Sie Fähigkeiten zum Lesen von Netzwerkablaufverfolgungen für Ihre Office 365 Websites erlernen möchten, gibt es keinen besseren Lehrer, als regelmäßig Ablaufverfolgungen von Seitenlasten zu erstellen und Erfahrungen mit dem Lesen dieser Websites zu sammeln. Wenn Sie beispielsweise eine Möglichkeit haben, laden Sie einen Office 365 Dienst, und verfolgen Sie den Prozess. Filtern Sie die Ablaufverfolgung auf DNS-Datenverkehr, oder durchsuchen Sie die FrameData nach dem Namen des diensts, den Sie durchsucht haben. Überprüfen Sie die Ablaufverfolgung, um eine Vorstellung der Schritte zu erhalten, die beim Laden des Diensts ausgeführt werden. Dies hilft Ihnen zu erfahren, wie das normale Laden der Seite aussehen sollte. Bei der Problembehandlung, insbesondere bei der Leistung, kann ihnen der Vergleich von guten und schlechten Ablaufverfolgungen sehr viel vermitteln.

Netmon verwendet Microsoft IntelliSense im Anzeigefilterfeld. IntelliSense oder intelligente Codevervollständigung ist dieser Trick, bei dem Sie einen Punkt eingeben und alle verfügbaren Optionen in einem Dropdown-Auswahlfeld angezeigt werden. Wenn Sie z. B. die TCP-Fensterskalierung nicht berücksichtigen, finden Sie auf diese Weise den Weg zu einem Filter (z.  `.protocol.tcp.window < 100` B. ) .

![Screenshot von Netmon, der zeigt, dass das Feld "Anzeigefilter" IntelliSense verwendet.](../media/75a56c11-9a60-47ee-a100-aabdfb1ba10f.PNG)

Netmon-Ablaufverfolgungen können viel Datenverkehr enthalten. Wenn Sie nicht damit vertraut sind, sie zu lesen, ist es wahrscheinlich überfordert, die Ablaufverfolgung beim ersten Mal zu öffnen. Zunächst müssen Sie das Signal vom Hintergrundrauschen in der Ablaufverfolgung trennen. Sie haben Office 365 getestet, und das ist der Datenverkehr, den Sie sehen möchten. Wenn Sie es gewohnt sind, durch Ablaufverfolgungen zu navigieren, benötigen Sie diese Liste möglicherweise nicht.

Der Datenverkehr zwischen Ihrem Client und Office 365 wird über TLS übertragen, was bedeutet, dass der Datenverkehrstext verschlüsselt und in einer generischen Netmon-Ablaufverfolgung nicht lesbar ist. Ihre Leistungsanalyse muss die Einzelheiten der Informationen im Paket nicht kennen. Es ist jedoch sehr an Paketheadern und den darin enthaltenen Informationen interessiert.

### <a name="tips-to-get-a-good-trace"></a>Tipps, um eine gute Ablaufverfolgung zu erhalten

- Kennen Sie den Wert der IPv4- oder IPv6-Adresse Ihres Clientcomputers. Sie können dies über die Eingabeaufforderung abrufen, indem Sie **"IPConfig"** eingeben und dann die EINGABETASTE drücken. Wenn Sie diese Adresse kennen, können Sie auf einen Blick feststellen, ob der Datenverkehr in der Ablaufverfolgung direkt Ihren Clientcomputer betrifft. Wenn ein bekannter Proxy vorhanden ist, pingen Sie ihn, und rufen Sie auch dessen IP-Adresse ab.

- Leeren Sie den DNS-Resolvercache, und schließen Sie nach Möglichkeit alle Browser mit Ausnahme des Browsers, in dem Sie Ihre Tests ausführen. Wenn Sie dies nicht tun können, z. B. wenn die Unterstützung browserbasierte Tools verwendet, um den Desktop Ihres Clientcomputers anzuzeigen, sollten Sie darauf vorbereitet sein, Ihre Ablaufverfolgung zu filtern.

- Suchen Sie in einer ausgelasteten Ablaufverfolgung den Office 365 Dienst, den Sie verwenden. Wenn Sie Ihren Datenverkehr noch nie oder selten gesehen haben, ist dies ein hilfreicher Schritt beim Trennen des Leistungsproblems von anderen Netzwerkgeräuschen. Es gibt einige Möglichkeiten, dies zu tun. Direkt vor dem Test können Sie _Ping_ oder _PsPing_ für die URL des bestimmten Diensts `ping outlook.office365.com` (oder `psping -4 microsoft-my.sharepoint.com:443` beispielsweise) verwenden. Sie können diese Ping- oder PsPing-Funktion auch ganz einfach in einer Netmon-Ablaufverfolgung (anhand ihres Prozessnamens) finden. Dies gibt Ihnen einen Ort, an dem Sie beginnen können, zu suchen.

Wenn Sie zum Zeitpunkt des Problems nur die Netmon-Ablaufverfolgung verwenden, ist dies ebenfalls in Ordnung. Um sich zu orientieren, verwenden Sie einen Filter wie `ContainsBin(FrameData, ASCII, "office")` oder `ContainsBin(FrameData, ASCII, "outlook")` . Sie können Ihre Framenummer aus der Ablaufverfolgungsdatei aufzeichnen. Sie können auch den Bereich _"Framezusammenfassung"_ ganz nach rechts scrollen und nach der Spalte "Unterhaltungs-ID" suchen. Es ist eine Zahl für die ID dieser bestimmten Unterhaltung angegeben, die Sie später auch in Isolation aufzeichnen und betrachten können. Denken Sie daran, diesen Filter zu entfernen, bevor Sie eine andere Filterung anwenden.

> [!TIP]
> Netmon verfügt über viele hilfreiche integrierte Filter. Probieren Sie die Schaltfläche **"Filter laden"** oben im _Anzeigefilterbereich_ aus.

![Suchen Sie Ihre IP mithilfe von PSPing in der Befehlszeile auf dem Clientcomputer.](../media/4c43ac67-e28e-4536-842d-7add7aa28847.PNG)

![Netmon trace from the client showing the same PSPing command through the filter TCP. Flags.Syn == 1.](../media/0ae7ef7d-e003-4d01-a006-dc49bd1fcef2.PNG)

Machen Sie sich mit Ihrem Datenverkehr vertraut und lernen Sie, die benötigten Informationen zu finden. Erfahren Sie beispielsweise, welches Paket in der Ablaufverfolgung den ersten Verweis auf den von Ihnen verwendeten Office 365 Dienst aufweist (z. B. "Outlook").

Wenn Sie Office 365 Outlook Online als Beispiel verwenden, beginnt der Datenverkehr ungefähr wie folgt:

- DNS-Standardabfrage und DNS-Antwort für outlook.office365.com mit übereinstimmenden QueryIDs. Es ist wichtig, den Zeitoffset für diese Änderung zu beachten und zu beachten, wo der Office 365 globale DNS die Anforderung zur Namensauflösung sendet. Idealerweise so lokal wie möglich, anstatt auf halber Welt.

- Eine HTTP GET-Anforderung, deren Statusbericht dauerhaft verschoben wurde (301)

- RWS Traffic including RWS Verbinden requests and Verbinden replies. (Remote Winsock stellt eine Verbindung für Sie bereit.)

- Eine TCP SYN- und TCP SYN/ACK-Unterhaltung. Viele der Einstellungen in dieser Unterhaltung wirken sich auf Ihre Leistung aus.

- Dann eine Reihe von TLS:TLS-Datenverkehr, in dem die TLS-Handshake- und TLS-Zertifikatunterhaltungen stattfinden. (Denken Sie daran, dass die Daten über SSL/TLS verschlüsselt sind.)

Alle Teile des Datenverkehrs sind wichtig und verbunden, aber kleine Teile der Ablaufverfolgung enthalten Informationen, die im Hinblick auf die Leistungsbehandlung besonders wichtig sind. Daher konzentrieren wir uns auf diese Bereiche. Da wir bei Microsoft genügend Office 365 Problembehandlung bei der Leistung durchgeführt haben, um eine Liste der top Ten allgemeiner Probleme zu erstellen, konzentrieren wir uns außerdem auf diese Probleme und wie wir die Tools verwenden können, die wir als Nächstes zur Lösung dieser Probleme benötigen.

Wenn Sie noch nicht alle installiert haben, werden in der folgenden Matrix mehrere Tools verwendet. Wo möglich. Links zu den Installationspunkten werden bereitgestellt. Die Liste enthält gängige Netzwerkablaufverfolgungstools wie [Netmon](https://www.microsoft.com/download/details.aspx?id=4865) und [Wireshark,](https://www.wireshark.org/)aber verwenden Sie alle Ablaufverfolgungstools, mit denen Sie vertraut sind und in denen Sie es gewohnt sind, Netzwerkdatenverkehr zu filtern. Beachten Sie beim Testen Folgendes:

- *Schließen Sie Ihre Browser, und testen*  Sie mit nur einem browser, der ausgeführt wird – dies reduziert den gesamt erfassten Datenverkehr. Es sorgt für eine weniger ausgelasteten Ablaufverfolgung.
- *Leeren Des DNS-Resolver-Caches auf dem Clientcomputer*  – Dadurch erhalten Sie beim Start der Erfassung eine fehlerfreie Lösung, um eine übersichtlichere Ablaufverfolgung zu erhalten.

## <a name="common-issues"></a>Häufig auftretende Probleme

Einige häufige Probleme, mit denen Sie möglicherweise konfrontiert sind, und wie Sie sie in Ihrer Netzwerkablaufverfolgung finden.

### <a name="tcp-windows-scaling"></a>TCP-Windows skalierung

Gefunden in syn - SYN/ACK. Ältere oder veraltete Hardware nutzt die TCP-Fensterskalierung möglicherweise nicht.  Ohne die richtigen TCP-Fensterskalierungseinstellungen füllt sich der standardmäßige 16-Bit-Puffer in TCP-Headern in Millisekunden.  Der Datenverkehr kann nicht weiter gesendet werden, bis der Client eine Bestätigung erhält, dass die ursprünglichen Daten empfangen wurden, was zu Verzögerungen führt.

#### <a name="tools"></a>Tools

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Wonach Sie suchen sollten

Suchen Sie nach dem SYN-SYN/ACK-Datenverkehr in Ihrer Netzwerkablaufverfolgung.  Verwenden Sie in Netmon einen Filter wie  `tcp.flags.syn == 1` . Dieser Filter ist in Wireshark identisch.

![Filtern Sie in Netmon oder Wireshark nach Syn-Paketen für beide Tools: TCP. Flags.Syn == 1.](../media/4b9a12a1-c915-43c8-ac2f-a679d0435a29.PNG)

Beachten Sie, dass für jede SYN eine Quellportnummer (SrcPort) vorhanden ist, die im Zielport (DstPort) der zugehörigen Bestätigung (SYN/ACK) übereinstimmt.

Um den Windows Skalierungswert anzuzeigen, der von Ihrer Netzwerkverbindung verwendet wird, erweitern Sie zuerst syn und dann die zugehörige SYN/ACK.

![Grafik, die zeigt, wie SrcPort mit DstPort in einer Ablaufverfolgung verglichen wird, um das Zeitdelta abzurufen.](../media/6a4ca573-0253-4fbd-93e8-92821ee1c351.png)

### <a name="tcp-idle-time-settings"></a>TCP-Leerlaufzeit Einstellungen

In der Vergangenheit sind die meisten Umkreisnetzwerke für vorübergehende Verbindungen konfiguriert, was bedeutet, dass Leerlaufverbindungen in der Regel beendet werden. Leerlauf-TCP-Sitzungen können von Proxys und Firewalls mit mehr als 100 bis 300 Sekunden beendet werden. Dies ist für Outlook Online problematisch, da langfristige Verbindungen erstellt und verwendet werden, unabhängig davon, ob sie im Leerlauf sind oder nicht.

Wenn Verbindungen von Proxy- oder Firewallgeräten beendet werden, wird der Client nicht informiert, und ein Versuch, Outlook Online zu verwenden, bedeutet, dass ein Clientcomputer wiederholt versucht, die Verbindung herzustellen, bevor eine neue hergestellt wird. Möglicherweise werden Hänger im Produkt, Eingabeaufforderungen oder eine langsame Leistung beim Laden der Seite angezeigt.

#### <a name="tools"></a>Tools

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Wonach Sie suchen sollten

Sehen Sie sich in Netmon das Feld Zeitversatz für einen Roundtrip an. Ein Roundtrip ist die Zeit zwischen dem Client, der eine Anforderung an den Server sendet, und dem Empfangen einer Antwort zurück. Überprüfen Sie zwischen dem Client und dem Ausgangspunkt (z. B. Client –- \> Proxy) oder der client to Office 365 (Client -- \> Office 365). Dies ist in vielen Pakettypen zu sehen.

Als Beispiel kann der Filter in Netmon wie folgt  `.Protocol.IPv4.Address == 10.102.14.112 AND .Protocol.IPv4.Address == 10.201.114.12` aussehen, oder, in Wireshark,  `ip.addr == 10.102.14.112 &amp;&amp; ip.addr == 10.201.114.12` .

> [!TIP]
> Sie wissen nicht, ob die IP-Adresse in Ihrer Ablaufverfolgung zu Ihrem DNS-Server gehört? Versuchen Sie, es in der Befehlszeile nach oben zu suchen. Klicken Sie auf **"Start** \> **ausführen",** \> und geben Sie **"cmd"** ein, oder drücken **Sie Windows Taste,** und geben Sie \> **"cmd" ein.** Geben Sie an der Eingabeaufforderung  `nslookup <the IP address from the network trace>` . Verwenden Sie zum Testen nslookup für die IP-Adresse Ihres eigenen Computers. > Eine Liste der IP-Bereiche von Microsoft finden Sie unter [Office 365 URLs und IP-Adressbereiche.](./urls-and-ip-address-ranges.md)

Wenn ein Problem vorliegt, werden in diesem Fall (Outlook Online) lange Zeitoffsets angezeigt, insbesondere in TLS:TLS-Paketen, die die Übersicht der Anwendungsdaten anzeigen (z. B. in Netmon finden Sie Anwendungsdatenpakete über `.Protocol.TLS AND Description == "TLS:TLS Rec Layer-1 SSL Application Data"` ). Sie sollten einen reibungslosen Verlauf während der gesamten Sitzung sehen. Wenn beim Aktualisieren Ihrer Outlook Online lange Verzögerungen auftreten, kann dies durch ein hohes Maß an Zurücksetzungen verursacht werden.

### <a name="latencyround-trip-time"></a>Latenz-/Roundtripzeit

Die Latenz ist ein Maß, das sich je nach vielen Variablen stark ändern kann, z. B. beim Upgrade von Geräten, beim Hinzufügen einer großen Anzahl von Benutzern zu einem Netzwerk und dem Prozentsatz der Gesamtbandbreite, die von anderen Aufgaben in einer Netzwerkverbindung verbraucht wird.

Auf dieser Seite für die [Netzwerkplanung und Leistungsoptimierung](network-planning-and-performance.md) für Office 365 stehen Bandbreitenrechner für Office 365 zur Verfügung.

Müssen Sie die Geschwindigkeit Ihrer Verbindung oder die Bandbreite Ihrer ISP-Verbindung messen? Probieren Sie diese Website (oder Websites wie diese) aus: [Speedtest Offizielle Website,](https://www.speedtest.net/)oder fragen Sie Ihre bevorzugte Suchmaschine nach dem Test der **Ausdrucksgeschwindigkeit** ab.

#### <a name="tools"></a>Tools

- Pingen
- PsPing
- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Wonach Sie suchen sollten

Um die Latenz in einer Ablaufverfolgung nachzuverfolgen, profitieren Sie davon, dass Sie die IP-Adresse des Clientcomputers und die IP-Adresse des DNS-Servers in Office 365 aufgezeichnet haben. Dies dient der einfacheren Ablaufverfolgungsfilterung. Wenn Sie eine Verbindung über einen Proxy herstellen, benötigen Sie ihre Clientcomputer-IP-Adresse, die Proxy-/Egress-IP-Adresse und die Office 365 DNS-IP-Adresse, um die Arbeit zu vereinfachen.

Eine an outlook.office365.com gesendete Pinganforderung teilt Ihnen den Namen des Datencenters mit, das die Anforderung empfängt, auch wenn Ping  *möglicherweise*  keine Verbindung herstellen kann, um die aufeinanderfolgenden ICMP-Pakete der Marke zu senden. Wenn Sie PsPing (ein kostenloses Downloadtool) und den Port (443) und möglicherweise IPv4 (-4) verwenden, erhalten Sie eine durchschnittliche Roundtripzeit für gesendete Pakete. Dies funktioniert für andere URLs in den Office 365-Diensten, `psping -4 yourSite.sharepoint.com:443` z. B. . Tatsächlich können Sie eine Reihe von Pings angeben, um ein größeres Beispiel für Ihren Durchschnitt zu erhalten. Versuchen Sie es in etwa wie `psping -4 -n 20 yourSite-my.sharepoint.com:443` .

> [!NOTE]
> PsPing sendet keine ICMP-Pakete. Es pingt mit TCP-Paketen über einen bestimmten Port, sodass Sie jedes beliebige verwenden können, von dem Sie wissen, dass es geöffnet ist. Versuchen Sie in Office 365, das SSL/TLS verwendet, Port :443 an Ihr PsPing anzufügen.

![Screenshot, der einen Ping zeigt, der outlook.office365.com auflöst, und einen PSPing, bei dem 443 den gleichen Vorgang ausführt, aber auch einen durchschnittlichen RTT-Wert von 6,5 ms meldet.](../media/c64339f2-2c96-45b8-b168-c2a060430266.PNG)

Wenn Sie die langsam ausgeführte Office 365 Seite während einer Netzwerkablaufverfolgung geladen haben, sollten Sie eine Netmon- oder Wireshark-Ablaufverfolgung nach `DNS` filtern. Dies ist einer der IPs, nach dem wir suchen.

Hier sind die Schritte, die Sie ausführen müssen, um Ihren Netmon so zu filtern, dass die IP-Adresse abgerufen wird (und sehen Sie sich die DNS-Latenz an). In diesem Beispiel wird outlook.office365.com verwendet, aber möglicherweise auch die URL eines SharePoint Onlinemandanten (z. B. hithere.sharepoint.com).

1. Pingen Sie die `ping outlook.office365.com` URL, und noten Sie in den Ergebnissen den Namen und die IP-Adresse des DNS-Servers auf, an den die Pinganforderung gesendet wurde.
2. Die Netzwerkablaufverfolgung öffnet die Seite oder führt die Aktion aus, die ihnen das Leistungsproblem zur Verfügung stellt, oder, wenn eine hohe Latenz beim Pingen auftritt, selbst die Netzwerkablaufverfolgung.
3. Öffnen Sie die Ablaufverfolgung in Netmon, und filtern Sie nach DNS (dieser Filter funktioniert auch in Wireshark, ist jedoch groß- und kleinschreibungsaufwendig). `-- dns` Da Sie den Namen des DNS-Servers aus Ihrem Ping kennen, können Sie auch in Netmon wie folgt schneller filtern: `DNS AND ContainsBin(FrameData, ASCII, "namnorthwest")` , was in Wireshark dns und Frame wie folgt aussieht, enthält "namnorthwest".<br/>Öffnen Sie das Antwortpaket, und klicken Sie im Fenster **"Framedetails** für Netmon" auf **DNS,** um weitere Informationen zu erhalten. In den DNS-Informationen finden Sie die IP-Adresse des DNS-Servers, an den die Anforderung gesendet wurde, in Office 365. Sie benötigen diese IP-Adresse für den nächsten Schritt (das PsPing-Tool). Entfernen Sie den Filter, klicken Sie mit der rechten Maustaste auf die DNS-Antwort in Netmon (**Frame Summary** \> **Find Conversations** \> **DNS**), um die DNS-Abfrage und -Antwort nebeneinander anzuzeigen.
4. Beachten Sie in Netmon auch die Zeitoffsetspalte zwischen der DNS-Anforderung und der Antwort. Im nächsten Schritt ist das einfach zu installierende und zu verwendende [PsPing-Tool](/sysinternals/downloads/psping) sehr praktisch, sowohl weil ICMP häufig für Firewalls blockiert wird als auch weil PsPing die Latenz in Millisekunden elegant verfolgt. PsPing schließt eine TCP-Verbindung mit einer Adresse und einem Port ab (in unserem Fall geöffneter Port 443).
5. Installieren Sie PsPing.
6. Öffnen Sie eine Eingabeaufforderung \> \> (Startausführungstyp cmd oder Windows \> Schlüsseltyp cmd), und ändern Sie das Verzeichnis in das Verzeichnis, in dem Sie PsPing installiert haben, um den PsPing-Befehl auszuführen. In meinen Beispielen kann ich sehen, wie ich einen "Perf"-Ordner im Stammverzeichnis von C erstellt habe. Sie können dies auch für den Schnellzugriff tun.
7. Geben Sie den Befehl ein, damit Sie Ihr PsPing für die IP-Adresse des Office 365 DNS-Servers aus Ihrer früheren Netmon-Ablaufverfolgung vornehmen, einschließlich der Portnummer, z. `psping -n 20 132.245.24.82:445` B. . Dadurch erhalten Sie ein Sampling von 20 Pings und die durchschnittliche Latenz beim Beenden von PsPing.

Wenn Sie über einen Proxyserver Office 365, sind die Schritte etwas anders. Sie würden zuerst PsPing an Ihren Proxyserver weiterleiten, um einen durchschnittlichen Latenzwert in Millisekunden zum Proxy/Ausgang und zurück zu erhalten, und dann entweder PsPing auf dem Proxy oder auf einem Computer mit einer direkten Internetverbindung ausführen, um den fehlenden Wert zu erhalten (den wert zum Office 365 und zurück).

Wenn Sie PsPing über den Proxy ausführen möchten, haben Sie zwei Millisekundenwerte: Clientcomputer zu Proxyserver oder Ausgangspunkt und Proxyserver für Office 365. Und Sie sind fertig! Nun, aufzeichnungswerte, trotzdem.

Wenn Sie PsPing auf einem anderen Clientcomputer ausführen, der eine direkte Verbindung mit dem Internet hat, d. h. ohne Proxy, haben Sie zwei Millisekundenwerte: Clientcomputer zum Proxyserver oder Ausgangspunkt und Clientcomputer für Office 365. Subtrahieren Sie in diesem Fall den Wert des Clientcomputers an den Proxyserver oder Ausgangspunkt vom Wert des Clientcomputers in Office 365, und Sie erhalten die RTT-Nummern von Ihrem Clientcomputer zum Proxyserver oder Ausgangspunkt und vom Proxyserver oder Ausgangspunkt zu Office 365.

Wenn Sie jedoch einen Clientcomputer an dem betroffenen Speicherort finden können, der direkt verbunden ist, oder den Proxy umgehen, können Sie auswählen, ob sich das Problem dort zunächst reproduzieren lässt, und danach testen, ob es verwendet wird.

Latenz, wie in einer Netmon-Ablaufverfolgung dargestellt, können diese zusätzlichen Millisekunden addieren, wenn sie in einer bestimmten Sitzung ausreichend sind.

![Allgemeine Latenz in Netmon, wobei der Framezusammenfassung die Standardmäßige Time Delta-Spalte "Netmon" hinzugefügt wird.](../media/7ad17380-8527-4bc2-9b9b-6310cf19ba6b.PNG)

> [!NOTE]
> Ihre IP-Adresse kann sich von den hier gezeigten IP-Adressen unterscheiden, z. B. kann Ihr Ping ungefähr 157.56.0.0/16 oder einen ähnlichen Bereich zurückgeben. Eine Liste der von Office 365 verwendeten Bereiche finden Sie [unter Office 365 URLs und IP-Adressbereiche.](./urls-and-ip-address-ranges.md)

Denken Sie daran, alle Knoten (oben ist dafür eine Schaltfläche vorhanden) zu erweitern, wenn Sie z. B. nach 132.245 suchen möchten.

### <a name="proxy-authentication"></a>Proxyauthentifizierung

Dies gilt nur für Sie, wenn Sie einen Proxyserver durchlaufen. Andernfalls können Sie diese Schritte überspringen. Bei ordnungsgemäßer Funktionsweise sollte die Proxyauthentifizierung konsistent in Millisekunden erfolgen. Es sollte keine zeitweise schlechte Leistung während spitzen Nutzungszeiten (z. B. ) angezeigt werden.

Wenn die Proxyauthentifizierung aktiviert ist, müssen Sie jedes Mal, wenn Sie eine neue TCP-Verbindung zu Office 365 herstellen, um Informationen abzurufen, einen Authentifizierungsprozess hinter den Kulissen durchlaufen. Wenn Sie beispielsweise in Outlook Online von Kalender zu E-Mail wechseln, authentifizieren Sie sich. Und wenn auf einer Seite auf SharePoint Online Medien oder Daten von mehreren Standorten oder Standorten angezeigt werden, authentifizieren Sie sich für jede unterschiedliche TCP-Verbindung, die zum Rendern der Daten erforderlich ist.

In Outlook Online kann es zu langsamen Ladezeiten führen, wenn Sie zwischen Kalender und Postfach wechseln, oder langsames Laden der Seite in SharePoint Online. Es gibt jedoch andere Symptome, die hier nicht aufgeführt sind.

Die Proxyauthentifizierung ist eine Einstellung auf ihrem Ausgehend-Proxyserver. Wenn dies zu einem Leistungsproblem mit Office 365 führt, wenden Sie sich an Ihr Netzwerkteam.

#### <a name="tools"></a>Tools

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Wonach Sie suchen sollten

Die Proxyauthentifizierung findet immer dann statt, wenn eine neue TCP-Sitzung gesponnen werden muss, in der Regel, um Dateien oder Informationen vom Server anzufordern oder um Informationen bereitzustellen. Möglicherweise sehen Sie die Proxyauthentifizierung bei HTTP GET- oder HTTP POST-Anforderungen. Wenn Sie die Frames sehen möchten, in denen Sie Anforderungen in Ihrer Ablaufverfolgung authentifizieren, fügen Sie die Spalte "NTLMSSP-Zusammenfassung" zu Netmon hinzu, und filtern Sie nach  `.property.NTLMSSPSummary` . Um zu sehen, wie lange die Authentifizierung dauert, fügen Sie die Spalte "Time Delta" hinzu.

So fügen Sie Netmon eine Spalte hinzu:

1. Klicken Sie mit der rechten Maustaste auf eine Spalte **wie** Beschreibung.
2. Klicken Sie auf **"Spalten auswählen".**
3. Suchen Sie _NTLMSSP Summary_ and _Time Delta_ in der Liste, und klicken Sie auf **Hinzufügen**.
4. Verschieben Sie die neuen Spalten vor oder hinter die Spalte Beschreibung , damit Sie sie nebeneinander lesen können. 
5. Klicken Sie auf **OK**.

Auch wenn Sie die Spalte nicht hinzufügen, funktioniert der Netmon-Filter. Die Problembehandlung ist jedoch viel einfacher, wenn Sie sehen können, in welcher Phase der Authentifizierung Sie sich befinden.

Wenn Sie nach Instanzen der Proxyauthentifizierung suchen, sollten Sie alle Frames untersuchen, in denen eine NTLM-Abfrage vorhanden ist oder eine Authentifizierungsnachricht vorhanden ist. Klicken Sie bei Bedarf mit der rechten Maustaste auf den bestimmten Datenverkehr, und suchen Sie unterhaltungen \> tcp. Beachten Sie die Time Delta-Werte in diesen Unterhaltungen.

![Netmon-Ablaufverfolgung mit Proxyauthentifizierung, gefiltert nach Unterhaltung.](../media/b640f176-0a52-4bbb-972e-60fb3d6aece2.PNG)

Eine Verzögerung von vier Sekunden bei der Proxyauthentifizierung wie in Wireshark. Das **Zeitdelta aus der vorherigen angezeigten Framespalte** wurde erstellt, indem sie mit der rechten Maustaste auf das Feld mit demselben Namen in den Framedetails klickt und "Als Spalte hinzufügen" auswählt.  <br/> ![In Wireshark kann die Spalte "Time delta from previous displayed frame" erstellt werden, indem Sie mit der rechten Maustaste auf das Feld mit demselben Namen in den Framedetails klicken und "Als Spalte hinzufügen" auswählen.](../media/f5b7bde4-8067-4ee0-bc7f-e9062ce1ba6f.PNG)

### <a name="dns-performance"></a>DNS-Leistung

Die Namensauflösung funktioniert am besten und am schnellsten, wenn sie so nah wie möglich im Land des Kunden erfolgt.

Wenn die DNS-Namensauflösung erfolgt, kann das Laden der Seite Sekunden hinzufügen. Im Idealfall erfolgt die Namensauflösung in weniger als 100 ms. Wenn dies nicht der Fall ist, sollten Sie weitere Untersuchungen durchführen.

> [!TIP]
> Sie sind nicht sicher, wie die Clientkonnektivität in Office 365 funktioniert? Sehen Sie sich hier das Referenzdokument zur Clientkonnektivität [an.](/previous-versions//dn741250(v=technet.10))

#### <a name="tools"></a>Tools

- Netmon
- Wireshark
- PsPing

#### <a name="what-to-look-for"></a>Wonach Sie suchen sollten

Die Analyse der DNS-Leistung ist in der Regel ein weiterer Auftrag für eine Netzwerkablaufverfolgung. PsPing ist jedoch auch hilfreich, wenn es um eine mögliche Ursache geht.

DNS-Datenverkehr basiert auf TCP- und UDP-Anforderungen, und Antworten sind eindeutig mit einer ID gekennzeichnet, die dabei hilft, eine bestimmte Anforderung mit ihrer spezifischen Antwort zuzuordnen. Dns-Datenverkehr wird angezeigt, wenn z. B. SharePoint Online einen Netzwerknamen oder eine URL auf einer Webseite verwendet. Als Faustregel gilt, dass der Großteil dieses Datenverkehrs, außer beim Übertragen von Zonen, über UDP ausgeführt wird.

In Netmon und Wireshark ist der einfachste Filter, mit dem Sie dns-Datenverkehr betrachten können, einfach `dns` . Achten Sie darauf, bei der Angabe des Filters Kleinbuchstaben zu verwenden. Denken Sie daran, den DNS-Resolver-Cache zu leeren, bevor Sie mit der Reproduzierten des Problems auf Ihrem Clientcomputer beginnen. Wenn Sie beispielsweise eine langsame SharePoint Laden der Onlineseite für die Startseite haben, sollten Sie alle Browser schließen, einen neuen Browser öffnen, die Ablaufverfolgung starten, ihren DNS-Resolvercache leeren und zu Ihrer SharePoint Online-Website navigieren. Nachdem die gesamte Seite aufgelöst wurde, sollten Sie die Ablaufverfolgung beenden und speichern.

![Ein einfacher Filter für DNS in Netmon ist DNS.](../media/1bebc118-ca13-45f3-803f-ab73e7af401d.png)

Hier möchten Sie sich den Zeitversatz ansehen. Außerdem kann es hilfreich sein, die **Time Delta-Spalte** zu Netmon hinzuzufügen, die Sie ausführen können, indem Sie die folgenden Schritte ausführen:

1. Klicken Sie mit der rechten Maustaste auf eine Spalte **wie** Beschreibung.
2. Klicken Sie auf **"Spalten auswählen".**
3. Suchen Sie _Zeitdelta_ in der Liste, und klicken Sie auf **"Hinzufügen".**
4. Verschieben Sie die neue Spalte vor oder hinter die Spalte Beschreibung , damit Sie sie nebeneinander lesen können. 
5. Klicken Sie auf **OK**.

Wenn Sie eine interessante Abfrage finden, sollten Sie sie isolieren, indem Sie im Framedetailseel mit der rechten Maustaste auf diese Abfrage klicken und **"Dns für Unterhaltungen** suchen" \> auswählen. Beachten Sie, dass der Bereich "Netzwerkunterhaltungen" im Protokoll des UDP-Datenverkehrs direkt zu der jeweiligen Unterhaltung springt.

![Eine Netmon-Ablaufverfolgung von Outlook nach DNS gefilterten Online-Ladevorgang, und verwenden Sie dann "Unterhaltungen suchen", um die Ergebnisse einzugrenzen.](../media/763cf20e-7b48-4a37-9449-c9978cfe118b.PNG)

In Wireshark können Sie eine Spalte für DNS-Zeit erstellen. Nehmen Sie Ihre Ablaufverfolgung (oder öffnen Sie eine Ablaufverfolgung) in Wireshark, und filtern Sie nach `dns` oder, hilfreicher,  `dns.time` nach . Klicken Sie auf eine beliebige DNS-Abfrage, und erweitern Sie im Bereich mit den Details die  `Domain Name System (response)` Details. Es wird ein Feld für die Zeit angezeigt `[Time: 0.001111100 seconds]` (z. B. . Klicken Sie dieses Mal mit der rechten Maustaste, und wählen Sie **"Als Spalte übernehmen"** aus. Dadurch erhalten Sie eine **Zeitspalte** für eine schnellere Sortierung Ihrer Ablaufverfolgung. Klicken Sie auf die neue Spalte, um nach absteigenden Werten zu sortieren, um zu sehen, welcher DNS-Aufruf am längsten aufgelöst wurde.

[Eine Suche nach SharePoint Online, gefiltert in Wireshark nach (Kleinbuchstaben) dns.time, wobei die Zeit aus den Details in eine Spalte umgewandelt und aufsteigend sortiert wird.](../media/1439dcc2-12ff-4ee2-9ef3-1484cf79c384.PNG)

Wenn Sie die DNS-Auflösungszeit genauer untersuchen möchten, versuchen Sie es mit einem PsPing für den von TCP verwendeten DNS-Port (z.  `psping <IP address of DNS server>:53` B. ). Sehen Sie weiterhin ein Leistungsproblem? Wenn Sie dies tun, ist das Problem wahrscheinlich ein größeres Netzwerkproblem als ein Problem mit einer bestimmten DNS-Anwendung, auf die Sie sich zur Lösung des Problems drücken. Es ist auch noch einmal zu erwähnen, dass ein Ping an outlook.office365.com Ihnen mitteilen wird, wo die DNS-Namensauflösung für Outlook Online stattfindet (z. B. outlook-namnorthwest.office365.com).

Wenn das Problem DNS-spezifisch ist, kann es erforderlich sein, sich an Ihre IT-Abteilung zu wenden, um sich dns-Konfigurationen und DNS-Weiterleitungen anzusehen, um dieses Problem weiter zu untersuchen.

### <a name="proxy-scalability"></a>Proxyskalierbarkeit

Dienste wie Outlook Online in Office 365 Clients mehrere langfristige Verbindungen gewähren. Daher kann jeder Benutzer mehr Verbindungen verwenden, die eine längere Lebensdauer erfordern.

#### <a name="tools"></a>Tools

Mathematik

#### <a name="what-to-look-for"></a>Wonach Sie suchen sollten

Es gibt kein spezielles Netzwerkablaufverfolgungs- oder Problembehandlungstool. Stattdessen basiert sie auf Bandbreitenberechnungen, die einschränkungen und anderen Variablen gegeben sind.

### <a name="tcp-max-segment-size"></a>TCP Max Segment Size

Gefunden in syn - SYN/ACK.  Führen Sie diese Überprüfung in einer Leistungsnetzwerkablaufverfolgung durch, die Sie durchgeführt haben, um sicherzustellen, dass TCP-Pakete so konfiguriert sind, dass die maximale Datenmenge möglich ist.

Ziel ist es, einen MSS von 1460 Bytes für die Übertragung von Daten zu sehen. Wenn Sie sich hinter einem Proxy befinden oder eine NAT verwenden, denken Sie daran, diesen Test vom Client zum Proxy/Egress/NAT und von Proxy/Ausgang/NAT zu Office 365 auszuführen, um optimale Ergebnisse zu erzielen! Dies sind unterschiedliche TCP-Sitzungen.

#### <a name="tools"></a>Tools

Netmon

#### <a name="what-to-look-for"></a>Wonach Sie suchen sollten

TCP Max Segment Size (MSS) ist ein weiterer Parameter des Drei-Wege-Handshake in Ihrer Netzwerkablaufverfolgung, d. h., Sie finden die benötigten Daten im SYN-SYN/ACK-Paket. MSS ist eigentlich ziemlich einfach zu sehen.

Öffnen Sie eine leistungsnetzwerkablaufverfolgung, die Sie haben, und suchen Sie die Verbindung, die Sie interessiert, oder die das Leistungsproblem veranschaulicht.

> [!NOTE]
> Wenn Sie sich eine Ablaufverfolgung ansehen und den für Ihre Unterhaltung relevanten Datenverkehr suchen müssen, filtern Sie nach der IP des Clients, der IP des Proxyservers, des Ausgangspunkts oder nach beiden. Wenn Sie direkt gehen, müssen Sie die URL, die Sie auf die IP-Adresse von Office 365 in der Ablaufverfolgung testen, pingen und nach ihr filtern.

Sehen Sie sich die Ablaufverfolgung aus zweiter Hand an? Versuchen Sie, Filter zu verwenden, um sich selbst zu orientieren. Führen Sie in Netmon eine Suche basierend auf der URL aus, z. `Containsbin(framedata, ascii, "sphybridExample")` B. notieren Sie sich die Framenummer.

Verwenden Sie in Wireshark etwas wie  `frame contains "sphybridExample"` . Wenn Sie feststellen, dass Sie Remote Winsock (RWS)-Datenverkehr gefunden haben (er kann als [PSH, ACK] in Wireshark angezeigt werden), denken Sie daran, dass RWS-Verbindungen kurz vor relevanten SYN - SYN/ACKs angezeigt werden können, wie zuvor erläutert.

An diesem Punkt können Sie die Framenummer aufzeichnen, den Filter ablegen und im Fenster "Netzwerkunterhaltungen" in Netmon auf **"Gesamter Datenverkehr"** klicken, um die nächste SYN anzuzeigen.

Wichtig: Wenn Sie zum Zeitpunkt der Ablaufverfolgung keine IP-Adressinformationen erhalten haben, erhalten Sie beim Suchen Ihrer URL in der Ablaufverfolgung (z. B. Teil `sphybridExample-my.sharepoint.com` von) IP-Adressen, nach denen gefiltert werden soll.

Suchen Sie die Verbindung in der Ablaufverfolgung, die Sie sehen möchten. Dazu können Sie entweder die Ablaufverfolgung überprüfen, nach IP-Adressen filtern oder bestimmte Unterhaltungs-IDs im Fenster "Netzwerkunterhaltungen" in Netmon auswählen. Sobald Sie das SYN-Paket gefunden haben, erweitern Sie TCP (in Netmon) oder das Transmission Control Protocol (in Wireshark) im Bereich "Framedetails". Erweitern Sie TCP-Optionen und MaxSegmentSize. Suchen Sie den zugehörigen SYN-ACK-Frame, und erweitern Sie TCP-Optionen und MaxSegmentSize. Der kleinere der beiden Werte ist die maximale Segmentgröße. In dieser Abbildung verwende ich die integrierte Spalte in Netmon mit dem Namen TCP-Problembehandlung.

![Die Netzwerkablaufverfolgung wird in Netmon mithilfe der integrierten Spalten gefiltert.](../media/e073df13-71f8-497a-83b4-bb9f70bd9833.PNG)

Die integrierte Spalte befindet sich oben im **Bereich "Framedetails".** (Um zur Normalansicht zurückzukehren, klicken Sie erneut auf **Spalten,** und wählen Sie dann **Zeitzone** aus.)

![Hier finden Sie die Dropdownliste "Spalten" für die TCP-Problembehandlungsoption (oben in der Framezusammenfassung).](../media/64fd4baa-a872-4f07-b959-752d7d37fd62.PNG)

Hier ist eine gefilterte Ablaufverfolgung in Wireshark. Es gibt einen für den MSS-Wert spezifischen Filter ( `tcp.options.mss` ). Die Frames eines SYN-, SYN/ACK- und ACK-Handshakes sind unten im Wireshark-Äquivalent zu Framedetails verknüpft (frame 47 ACK, Links zu 46 SYN/ACK, Links zu 43 SYN), um diese Art von Arbeit zu vereinfachen.

![Ablaufverfolgung, gefiltert in Wireshark nach tcp.options.mss für Max Segment Size (MSS).](../media/51e278db-801b-48bc-9b68-87cf92f03fd6.PNG)

Wenn Sie die **selektive Bestätigung** überprüfen müssen (nächstes Thema in dieser Matrix), schließen Sie Ihre Ablaufverfolgung nicht!

### <a name="selective-acknowledgment"></a>Selektive Bestätigung

Gefunden in syn - SYN/ACK. Muss sowohl in SYN als auch in SYN/ACK als zulässig gemeldet werden. Die selektive Bestätigung (Selective Acknowledgment, SACK) ermöglicht eine reibungslosere erneute Übertragung von Daten, wenn ein Paket oder ein Paket fehlt. Geräte können dieses Feature deaktivieren, was zu Leistungsproblemen führen kann.

Wenn Sie sich hinter einem Proxy befinden oder eine NAT verwenden, denken Sie daran, diesen Test vom Client zum Proxy/Egress/NAT und von Proxy/Ausgang/NAT zu Office 365 auszuführen, um optimale Ergebnisse zu erzielen! Dies sind unterschiedliche TCP-Sitzungen.

#### <a name="tools"></a>Tools

Netmon

#### <a name="what-to-look-for"></a>Wonach Sie suchen sollten

Die selektive Bestätigung (Selective Acknowledgment, SACK) ist ein weiterer Parameter im SYN-SYN/ACK-Handshake. Sie können Ihre Ablaufverfolgung auf verschiedene Arten nach SYN - SYN/ACK filtern.

Suchen Sie die Verbindung in der Ablaufverfolgung, die Sie sehen möchten, indem Sie entweder die Ablaufverfolgung überprüfen, nach IP-Adressen filtern oder mithilfe des Fensters "Netzwerkunterhaltungen" in Netmon auf eine Unterhaltungs-ID klicken. Sobald Sie das SYN-Paket gefunden haben, erweitern Sie TCP in Netmon oder das Transmission Control Protocol in Wireshark im Abschnitt "Framedetails". Erweitern Sie die TCP-Optionen und dann SACK. Suchen Sie den zugehörigen SYN-ACK-Frame, und erweitern Sie die TCP-Optionen und das zugehörige SACK-Feld. Stellen Sie sicher, dass SACK sowohl in SYN als auch in SYN/ACK zulässig ist. Hier sind SACK-Werte wie in Netmon und Wireshark zu sehen.

![Selektive Bestätigung (SACK) in Netmon als Ergebnis von tcp.flags.syn == 1.](../media/216f556f-5031-4ed2-b066-a0d9b3251fa2.PNG)

![SACK wie in Wireshark mit dem Filter tcp.flags.syn == 1.](../media/0a6e26e5-43dc-403b-adc9-3349a55f4e4b.PNG)

### <a name="dns-geolocation"></a>DNS-Geolocation

Wo in der Welt Office 365 versucht, Ihren DNS-Anruf aufzulösen, wirkt sich auf Ihre Verbindungsgeschwindigkeit aus.

In Outlook Online wird nach Abschluss der ersten DNS-Suche der Speicherort dieses DNS verwendet, um eine Verbindung mit Ihrem nächstgelegenen Rechenzentrum herzustellen. Sie werden mit einem Outlook Online CAS-Server verbunden, der das Backbone-Netzwerk verwendet, um eine Verbindung mit dem Rechenzentrum (dC) herzustellen, in dem Ihre Daten gespeichert sind. Dies ist schneller.

Beim Zugriff auf SharePoint Online wird ein Benutzer, der auf Reisen ist, in sein aktives Rechenzentrum geleitet – dC, dessen Standort auf der Startseite des SPO-Mandanten basiert (dC also in den USA, wenn der Benutzer in den USA ansässig ist).

Lync Online verfügt über aktive Knoten in mehreren dC gleichzeitig. Wenn Anforderungen für Lync-Onlineinstanzen gesendet werden, bestimmt das DNS von Microsoft, woher die Anforderung weltweit stammt, und gibt IP-Adressen vom nächstgelegenen regionalen DC zurück, in dem Lync Online aktiv ist.

> [!TIP]
> Benötigen Sie mehr darüber, wie Clients eine Verbindung mit Office 365 herstellen? Werfen Sie einen Blick auf den Referenzartikel zur [Clientkonnektivität](/previous-versions//dn741250(v=technet.10)) (und die hilfreichen Grafiken).

#### <a name="tools"></a>Tools

- Pingen
- PsPing

#### <a name="what-to-look-for"></a>Wonach Sie suchen sollten

Anforderungen für die Namensauflösung von den DNS-Servern des Clients an die DNS-Server von Microsoft sollten in den meisten Fällen dazu führen, dass Microsoft DNS die IP-Adresse eines regionalen Rechenzentrums (dC) zurückgibt. Was bedeutet dies für Sie? Wenn Sich Ihre Zentrale in Dermans, Indien, befindet, Sie jedoch in die Vereinigten Staaten reisen, sollten Die DNS-Server von Microsoft, wenn Ihr Browser eine Anforderung für Outlook Online stellt, Ihnen IP-Adressen an Rechenzentren in den VEREINIGTEn Staaten übergeben – ein regionales Rechenzentrum. Wenn E-Mails von Outlook benötigt werden, werden diese Daten über das schnelle Backbone-Netzwerk von Microsoft zwischen den Rechenzentren übermittelt.

DNS funktioniert am schnellsten, wenn die Namensauflösung so nah wie möglich am Standort des Benutzers erfolgt. Wenn Sie sich in Europa befinden, möchten Sie zu einem Microsoft-DNS in Europa wechseln und sich (im Idealfall) mit einem Rechenzentrum in Europa befassen. Die Leistung eines Clients in Europa, der zu DNS und einem Rechenzentrum in Amerika wechselt, wird langsamer sein.

Führen Sie das Ping-Tool für outlook.office365.com aus, um zu bestimmen, wohin Ihre DNS-Anforderung weltweit weitergeleitet wird. Wenn Sie sich in Europa befinden, sollte eine Antwort von etwa outlook-emeawest.office365.com angezeigt werden. Erwarten Sie in Amerika etwa outlook-namnorthwest.office365.com.

Öffnen Sie die Eingabeaufforderung auf dem Clientcomputer (über start \> Run \> cmd oder Windows \> Schlüsseltyp cmd). Geben Sie Ping outlook.office365.com ein, und drücken Sie die EINGABETASTE. Denken Sie daran, "-4" anzugeben, wenn Sie einen Ping über IPv4 angeben möchten. Möglicherweise erhalten Sie keine Antwort von den ICMP-Paketen, aber Sie sollten den Namen des DNS sehen, an den die Anforderung weitergeleitet wurde. Wenn Sie die Latenznummern für diese Verbindung anzeigen möchten, versuchen Sie PsPing an die IP-Adresse des Servers, der von Ping zurückgegeben wird.

![Pingen von outlook.office365.com mit Auflösung in outlook-namnorthwest.](../media/06c944d5-6159-43ec-aa31-757770695e8b.PNG)

![PSPing an die IP-Adresse, die vom Ping an outlook.office365.com mit einer durchschnittlichen Latenz von 28 Millisekunden zurückgegeben wird.](../media/f2b25a75-1a87-4479-b8a7-fa4375683507.PNG)

### <a name="office-365-application-troubleshooting"></a>Office 365 Anwendungsproblembehandlung

#### <a name="tools"></a>Tools

- Netmon
- HTTPWatch
- F12-Konsole im Browser

In diesem netzwerkspezifischen Artikel werden keine Tools behandelt, die bei der anwendungsspezifischen Problembehandlung verwendet werden. Auf [dieser Seite](https://support.office.com/article/Network-planning-and-performance-tuning-for-Office-365-e5f1228c-da3c-4654-bf16-d163daee8848)finden Sie jedoch Ressourcen, die Sie verwenden *können.*

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Häufig gestellte Fragen zu Office 365-Endpunkten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)