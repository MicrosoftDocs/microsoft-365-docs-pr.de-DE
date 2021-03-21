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
description: Dieser Artikel kann Ihnen helfen, Probleme mit der Office 365-Leistung zu beheben und sogar einige der häufigsten Probleme zu beheben.
ms.openlocfilehash: 588a19e86d903a7ab709a7f0d0131da6e2a77f47
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928236"
---
# <a name="performance-troubleshooting-plan-for-office-365"></a>Behandlung von Leistungsproblemen – Plan für Office 365

Müssen Sie wissen, welche Schritte unternommen werden müssen, um Verzögerungen, Hänge und Leistungsverzögerungen zwischen SharePoint Online, OneDrive for Business, Exchange Online oder Skype for Business Online und Ihrem Clientcomputer zu identifizieren und zu beheben? Bevor Sie den Support aufrufen, können Sie in diesem Artikel Probleme mit der Office 365-Leistung beheben und sogar einige der häufigsten Probleme beheben.

Dieser Artikel ist eigentlich ein Beispielaktionsplan, mit dem Sie wertvolle Daten zu Ihrem Leistungsproblem erfassen können. Einige wichtige Probleme sind auch in diesem Artikel enthalten.

Wenn Sie mit der Netzwerkleistung neu sind und einen langfristigen Plan zur Überwachung der Leistung zwischen Ihren Clientcomputern und Office 365 erstellen möchten, sehen Sie sich [Office 365](performance-tuning-using-baselines-and-history.md)Performance Tuning and Troubleshooting – Admin und IT Pro an.

## <a name="sample-performance-troubleshooting-action-plan"></a>Beispiel für einen Aktionsplan zur Problembehandlung bei der Leistungsbehandlung

Dieser Aktionsplan enthält zwei Teile: Vorbereitungsphase und Protokollierungsphase. Wenn Sie derzeit ein Leistungsproblem haben und datensammlungen müssen, können Sie sofort mit der Verwendung dieses Plans beginnen.

### <a name="prepare-the-client-computer"></a>Vorbereiten des Clientcomputers

- Suchen Sie einen Clientcomputer, der das Leistungsproblem reproduzieren kann. Dieser Computer wird während der Problembehandlung verwendet.
- Notieren Sie sich die Schritte, die das Leistungsproblem verursachen, damit Sie zum Testen bereit sind.
- Installieren von Tools zum Sammeln und Aufzeichnen von Informationen:
  - Installieren [Sie Netmon 3.4 (oder](https://www.microsoft.com/download/details.aspx?id=4865) verwenden Sie ein entsprechendes Netzwerkablaufverfolgungstool).
  - Installieren Sie die kostenlose Basic Edition von [HTTPWatch](https://www.httpwatch.com/download/) (oder verwenden Sie ein entsprechendes Tool zur Netzwerkablaufverfolgung).
  - Verwenden Sie eine Bildschirmaufzeichnung, oder führen Sie die Steps Recorder (PSR.exe) aus, die mit Windows Vista und höher kommt, um eine Aufzeichnung der Schritte zu erhalten, die Sie während der Tests ausführen.

### <a name="log-the-performance-issue"></a>Protokollieren des Leistungsproblems

- Schließen Sie alle außerirdischen Internetbrowser.
- Starten Sie die Schrittaufzeichnung oder eine andere Bildschirmaufzeichnung.
- Starten Sie Ihre Netmon-Erfassung (oder das Netzwerkablaufverfolgungstool).
- Löschen Sie den DNS-Cache auf dem Clientcomputer über die Befehlszeile, indem Sie ipconfig /flushdns eingeben.
- Starten Sie eine neue Browsersitzung, und aktivieren Sie HTTPWatch.
- Optional: Wenn Sie Exchange Online testen, führen Sie das Exchange Client Performance Analyzer-Tool in der Office 365-Verwaltungskonsole aus.
- Reproduzieren Sie die genauen Schritte, die das Leistungsproblem verursachen.
- Beenden Sie die Ablaufverfolgung Ihres Netmon oder eines anderen Tools.
- Führen Sie an der Befehlszeile eine Ablaufverfolgungsroute zu Ihrem Office 365-Abonnement aus, indem Sie den folgenden Befehl eingeben und dann die EINGABETASTE drücken:

  ``` cmd
  tracert <subscriptionname>.onmicrosoft.com
  ```

- Beenden Sie die Schrittaufzeichnung, und speichern Sie das Video. Achten Sie darauf, das Datum und die Uhrzeit der Aufnahme und ob eine gute oder schlechte Leistung gezeigt wird.
- Speichern Sie die Ablaufverfolgungsdateien. Achten Sie auch hier darauf, datums- und uhrzeitgemäß zu erfassen und zu prüfen, ob eine gute oder eine schlechte Leistung gezeigt wird.

Wenn Sie nicht mit der Ausführung der in diesem Artikel erwähnten Tools vertraut sind, machen Sie sich keine Sorgen, da wir diese Schritte als Nächstes bereitstellen. Wenn Sie diese Art der Netzwerkerfassung gewohnt sind, können Sie mit [How to collect baselines](performance-tuning-using-baselines-and-history.md#how-to-collect-baselines)(Sammeln von Basiswerten) überspringen, in dem das Filtern und Lesen der Protokolle beschrieben wird.

### <a name="flush-the-dns-cache-first"></a>Löschen des DNS-Caches zuerst

Warum? Wenn Sie den DNS-Cache leeren, starten Sie die Tests mit einem neuen Schiefer. Durch Löschen des Caches können Sie den Inhalt des DNS-Resolvers auf die neuesten Einträge zurücksetzen. Denken Sie daran, dass durch eine Leerung keine EINTRÄGE der HOSTs-Datei entfernt werden. Wenn Sie HOST-Dateieinträge umfassend verwenden, sollten Sie diese Einträge in eine Datei in einem anderen Verzeichnis kopieren und dann die HOST-Datei leeren.

#### <a name="flush-your-dns-resolver-cache"></a>Leeren des DNS-Resolvercaches

1. Öffnen Sie die Eingabeaufforderung **(start** \> **Run** \> **cmd** oder **Windows key** \> **cmd**).
2. Geben Sie den folgenden Befehl ein, und drücken Sie die EINGABETASTE:

    ``` cmd
    ipconfig /flushdns
    ```

## <a name="netmon"></a>Netmon

Das Netzwerküberwachungstool von Microsoft ([Netmon](https://www.microsoft.com/download/details.aspx?id=4865)) analysiert Pakete, d. h. Datenverkehr, der zwischen Computern in Netzwerken verläuft. Mithilfe von Netmon können Sie Datenverkehr mit Office 365 erfassen, anzeigen und lesen, dazwischenliegende Geräte identifizieren, wichtige Einstellungen auf der Netzwerkhardware überprüfen, nach verworfenen Paketen suchen und den Datenverkehr zwischen Computern in Ihrem Unternehmensnetzwerk und Office 365 verfolgen. Da der tatsächliche Textkörper des Datenverkehrs verschlüsselt ist, d. h. er (wird über SSL/TLS über Port 443 übertragen), können Sie die gesendeten Dateien nicht lesen. Stattdessen erhalten Sie eine ungefilterte Ablaufverfolgung des Pfads, den das Paket einnimmt, mit dem Sie das Problemverhalten nachverfolgen können.

Stellen Sie sicher, dass Sie derzeit keinen Filter anwenden. Führen Sie stattdessen die Schritte durch, und demonstrieren Sie das Problem, bevor Sie die Ablaufverfolgung beenden und speichern.

Öffnen Sie nach der Installation von Netmon 3.4 das Tool, und ergreifen Sie die folgenden Schritte:

### <a name="take-a-netmon-trace-and-reproduce-the-issue"></a>Nehmen Sie eine Netmon-Ablaufverfolgung vor, und reproduzieren Sie das Problem.

1. Starten Sie Netmon 3.4.
Die Startseite enthält drei  Bereiche: **Zuletzt** erfasste Erfassungen, **Netzwerke** auswählen und erste Schritte mit Microsoft Network **Monitor 3.4. Hinweis**. Im Bereich Netzwerke auswählen erhalten Sie außerdem eine Liste der Standardnetzwerke, aus denen Sie erfassen können. Stellen Sie sicher, dass hier Netzwerkkarten ausgewählt sind.

2. Klicken **Sie oben** auf der Startseite auf Neue **Aufnahme.** Dadurch wird neben der Registerkarte Startseite eine **neue** Registerkarte mit dem Namen **Capture 1 hinzufügt.**
![Die Benutzeroberfläche von Netmon mit den Hervorgehobenen Schaltflächen Neue Erfassung, Start und Beenden.](../media/d4527d84-62ec-4301-82d5-e0166ff71f20.PNG)

3. Klicken Sie auf der Symbolleiste auf **Start,** um eine einfache Aufnahme zu erstellen.

4. Reproduzieren Sie die Schritte, die ein Leistungsproblem stellen.

5. Klicken **Sie auf Datei** \> **speichern** unter \> **beenden.** Denken Sie daran, Datum und Uhrzeit mit der Zeitzone zu geben und zu erwähnen, ob sie eine schlechte oder gute Leistung zeigt.

## <a name="httpwatch"></a>HTTPWatch

[HTTPWatch](https://www.httpwatch.com/download/) ist kostenpflichtig und eine kostenlose Edition. Die kostenlose Basic Edition deckt alles ab, was Sie für diesen Test benötigen. HTTPWatch überwacht den Netzwerkdatenverkehr und die Ladezeit der Seite direkt aus dem Browserfenster. HTTPWatch ist ein Plug-In in Internet Explorer, das die Leistung grafisch beschreibt. Die Analyse kann in HTTPWatch Studio gespeichert und angezeigt werden.

> [!NOTE]
> Wenn Sie einen anderen Browser wie Firefox, Google Chrome oder httpWatch in Internet Explorer nicht installieren können, öffnen Sie ein neues Browserfenster, und drücken Sie F12 auf der Tastatur. Das Popup des Entwicklertools sollte unten im Browser angezeigt werden. Wenn Sie Opera verwenden, drücken Sie STRG+UMSCHALT+I für Web Inspector, klicken Sie dann auf die Registerkarte Netzwerk, und führen Sie die unten beschriebenen Tests aus.  Die Informationen unterscheiden sich geringfügig, die Ladezeiten werden jedoch weiterhin in Millisekunden angezeigt. > HTTPWatch ist auch bei Problemen mit den Ladezeiten von SharePoint Online-Seiten sehr hilfreich.

### <a name="run-httpwatch-and-reproduce-the-issue"></a>Ausführen von HTTPWatch und Reproduzieren des Problems

HTTPWatch ist ein Browser-Plug-In, daher ist das Verfügbar machen des Tools im Browser etwas anders für jede Version von Internet Explorer. In der Regel finden Sie HTTPWatch unter der Befehlsleiste im Internet Explorer-Browser. Wenn das HTTPWatch-Plug-In in Ihrem Browserfenster nicht angezeigt wird, überprüfen  Sie die Version Ihres Browsers, indem Sie auf Hilfe zu klicken, oder klicken Sie in späteren Versionen von Internet Explorer auf das Zahnradsymbol und \> Auf **Internet Explorer**. Klicken Sie zum Starten der **Befehlsleiste** in Internet Explorer mit der rechten Maustaste auf die Menüleiste, und klicken Sie auf **Befehlsleiste**.

In der Vergangenheit wurde HTTPWatch sowohl den Befehlen als auch den Explorerleisten zugeordnet, wenn Sie also nach der Installation das Symbol (auch nach dem Neustart) nicht sofort sehen, überprüfen Sie **Extras** und Die Symbolleisten für das Symbol. Denken Sie daran, dass Symbolleisten angepasst werden können und Ihnen Optionen hinzugefügt werden können.

![Die Befehlssymbolleiste von Internet Explorer, auf der das SYMBOL HTTPWatch angezeigt wird.](../media/198590b0-d7b1-4bff-a6ad-e4ec3a1e83df.png)

1. Starten Sie HTTPWatch in einem Internet Explorer-Browserfenster. Es wird am unteren Rand dieses Fensters an den Browser angedockt angezeigt. Klicken Sie **auf Datensatz**.

2. Reproduzieren Sie die genauen Schritte im Leistungsproblem. Klicken Sie **in** HTTPWatch auf die Schaltfläche Beenden.

3. **Speichern** Sie httpWatch oder **Send by Email**. Denken Sie daran, die Datei so zu benennen, dass sie Datums- und Uhrzeitinformationen sowie einen Hinweis darauf enthält, ob Ihre Uhr eine Demonstration von guter oder schlechter Leistung enthält.

![HTTPWatch zeigt die Registerkarte Netzwerk für eine Seitenlast der Office 365-Homepage an.](../media/021a2c64-d581-49fd-adf4-4c364f589d75.PNG)

Dieser Screenshot ist aus der Professional-Version von HTTPWatch. Sie können Ablaufverfolgungen in der Standardversion auf einem Computer mit einer Professional-Version öffnen und dort lesen. Zusätzliche Informationen können von der Ablaufverfolgung über diese Methode zur Verfügung stehen.

## <a name="problem-steps-recorder"></a>Aufzeichnung von Problemschritten

Steps Recorder oder PSR.exe ermöglicht es Ihnen, Probleme zu protokollieren, während sie auftreten. Es ist ein sehr nützliches Tool und sehr einfach zu führen.

### <a name="run-problem-steps-recorder-psrexe-to-record-your-work"></a>Ausführen der Fehlerschrittaufzeichnung (PSR.exe) zum Aufzeichnen Ihrer Arbeit

1. Verwenden Sie **entweder start** run typePSR.exeOK , oder klicken Sie auf den \>  \>  \>  **Windows** \> Key-PSR.exeund drücken Sie dann die  \> EINGABETASTE.

2. Wenn das kleine PSR.exe angezeigt wird, klicken Sie auf **Datensatz starten,** und reproduzieren Sie die Schritte, die das Leistungsproblem reproduzieren. Sie können Kommentare nach Bedarf hinzufügen, indem Sie auf **Kommentare hinzufügen klicken.**

3. Klicken **Sie auf Datensatz beenden,** wenn Sie die Schritte abgeschlossen haben. Wenn das Leistungsproblem ein Seitenrendering ist, warten Sie, bis die Seite gerendert wird, bevor Sie die Aufzeichnung beenden.

4. Klicken Sie auf **Speichern**.

![Ein Screenshot der Steps Recorder oder PSR.exe.](../media/8542b0aa-a3ff-4718-8dc4-43f5521c6c34.PNG)

Datum und Uhrzeit werden für Sie aufgezeichnet. Dadurch wird Ihre PSR mit Ihrer Netmon-Ablaufverfolgung und HTTPWatch in der Zeit verknüpft und hilft bei der präzisen Problembehandlung. Das Datum und die Uhrzeit im PSR-Eintrag können beispielsweise zeigen, dass eine Minute zwischen der Anmeldung und dem Browsen der URL und dem teilweisen Rendern der Administratorwebsite vergangen ist.

## <a name="read-your-traces"></a>Lesen Der Ablaufverfolgungen

Es ist nicht möglich, alles zur Problembehandlung bei Netzwerk und Leistung zu vermitteln, die jemand über einen Artikel wissen müsste. Eine gute Leistung benötigt Erfahrung und Kenntnisse darüber, wie Ihr Netzwerk funktioniert und in der Regel funktioniert. Es ist jedoch möglich, eine Liste der wichtigsten Probleme zu runden und zu zeigen, wie Tools es Ihnen erleichtern können, die häufigsten Probleme zu beseitigen.

Wenn Sie Die Netzwerkverfolgungen für Ihre Office 365-Websites lesen möchten, gibt es keinen besseren Lehrer, als regelmäßig Nachverfolgungen von Seitenlasten zu erstellen und Erfahrungen beim Lesen zu sammeln. Wenn Sie beispielsweise eine Chance haben, laden Sie einen Office 365-Dienst, und verfolgen Sie den Prozess. Filtern Sie die Ablaufverfolgung nach DNS-Datenverkehr, oder durchsuchen Sie frameData nach dem Namen des Diensts, den Sie durchsucht haben. Überprüfen Sie die Ablaufverfolgung, um eine Vorstellung von den Schritten zu erhalten, die beim Laden des Diensts auftreten. Dies hilft Ihnen, zu erfahren, wie normale Seitenlast aussehen sollte, und bei der Problembehandlung, insbesondere bei der Leistung, kann der Vergleich von guten mit schlechten Ablaufverfolgungen Ihnen viel beibringen.

Netmon verwendet Microsoft Intellisense im Feld Anzeigefilter. IntelliSense oder intelligente Codevervollständigung ist dieser Trick, bei dem Sie einen Zeitraum eingeben und alle verfügbaren Optionen in einem Dropdownauswahlfeld angezeigt werden. Wenn Sie sich beispielsweise Sorgen über die SKALIERUNG von TCP-Fenstern machen, können Sie auf diese Weise den Weg zu einem Filter (z.  `.protocol.tcp.window < 100` B. ) finden.

![Screenshot von Netmon, der zeigt, dass das Feld Anzeigefilter intellisense verwendet.](../media/75a56c11-9a60-47ee-a100-aabdfb1ba10f.PNG)

Netmon-Ablaufverfolgungen können viel Datenverkehr in sich haben. Wenn Sie keine Erfahrung mit dem Lesen haben, ist es wahrscheinlich, dass Sie beim ersten Öffnen der Ablaufverfolgung überfordert sind. Als Erstes müssen Sie das Signal vom Hintergrundrauschen in der Ablaufverfolgung trennen. Sie haben mit Office 365 getestet, und das ist der Datenverkehr, den Sie sehen möchten. Wenn Sie es gewohnt sind, durch Ablaufverfolgungen zu navigieren, benötigen Sie diese Liste möglicherweise nicht.

Der Datenverkehr zwischen Ihrem Client und Office 365 wird über TLS übertragen, was bedeutet, dass der Datenverkehrskörper verschlüsselt wird und in einer generischen Netmon-Ablaufverfolgung nicht lesbar ist. Ihre Leistungsanalyse muss die Besonderheiten der Informationen im Paket nicht kennen. Sie ist jedoch sehr an Paketkopfzeilen und den informationen interessiert, die sie enthalten.

### <a name="tips-to-get-a-good-trace"></a>Tipps zum Erhalten einer guten Ablaufverfolgung

- Kennen Sie den Wert der IPv4- oder IPv6-Adresse Ihres Clientcomputers. Sie können dies über die Eingabeaufforderung erhalten, indem Sie **IPConfig eingeben** und dann die EINGABETASTE drücken. Wenn Sie diese Adresse kennen, können Sie auf einen Blick erkennen, ob der Datenverkehr in der Ablaufverfolgung ihren Clientcomputer direkt umfasst. Wenn ein bekannter Proxy vorkommt, pingen Sie ihn, und erhalten Sie auch seine IP-Adresse.

- Leeren Sie den DNS-Resolvercache, und schließen Sie nach Möglichkeit alle Browser mit Ausnahme des Browsers, in dem Sie die Tests ausführen. Wenn Sie dazu nicht in der Lage sind, beispielsweise wenn die Unterstützung ein browserbasiertes Tool zum Anzeigen des Desktops Ihres Clientcomputers verwendet, können Sie die Ablaufverfolgung filtern.

- Suchen Sie in einer Gebucht-Ablaufverfolgung nach dem office 365-Dienst, den Sie verwenden. Wenn Sie Ihren Datenverkehr noch nie oder selten gesehen haben, ist dies ein hilfreicher Schritt, um das Leistungsproblem von anderen Netzwerkgeräuschen zu trennen. Es gibt verschiedene Möglichkeiten, dies zu tun. Direkt vor dem Test können Sie _Ping_ oder _PsPing_ für die URL des bestimmten Diensts verwenden ( oder `ping outlook.office365.com` , `psping -4 microsoft-my.sharepoint.com:443` z. B. ). Sie können diese Ping- oder PsPing-Datei auch ganz einfach in einer Netmon-Ablaufverfolgung (nach dem Prozessnamen) finden. Dies gibt Ihnen einen Ort, an dem Sie mit der Suche beginnen können.

Wenn Sie zum Zeitpunkt des Problems nur die Netmon-Ablaufverfolgung verwenden, ist dies auch in Ordnung. Verwenden Sie einen Filter wie oder, um sich zu `ContainsBin(FrameData, ASCII, "office")` `ContainsBin(FrameData, ASCII, "outlook")` orientieren. Sie können Ihre Framenummer aus der Ablaufverfolgungsdatei aufzeichnen. Möglicherweise möchten Sie auch den Bildlauf im _Bereich Framezusammenfassung_ ganz nach rechts durchführen und nach der Spalte Unterhaltungs-ID suchen. Für die ID dieser bestimmten Unterhaltung ist eine Zahl angegeben, die Sie später auch isoliert aufzeichnen und betrachten können. Denken Sie daran, diesen Filter zu entfernen, bevor Sie eine andere Filterung anwenden.

> [!TIP]
> Netmon verfügt über viele hilfreiche integrierte Filter. Probieren Sie **die Schaltfläche** Ladenfilter oben im _Filterbereich Anzeigen_ aus.

![Suchen Sie Ihre IP mithilfe von PSPing an der Befehlszeile auf dem Clientcomputer.](../media/4c43ac67-e28e-4536-842d-7add7aa28847.PNG)

![Netmon-Ablaufverfolgung vom Client, der denselben PSPing-Befehl über den Filter TCP zeigt. Flags.Syn == 1.](../media/0ae7ef7d-e003-4d01-a006-dc49bd1fcef2.PNG)

Machen Sie sich mit Ihrem Datenverkehr vertraut, und erfahren Sie, wie Sie die benötigten Informationen finden. Erfahren Sie beispielsweise, welches Paket in der Ablaufverfolgung den ersten Verweis auf den von Ihnen verwendeten Office 365-Dienst (z. B. "Outlook") enthält.

Nehmen wir Office 365 Outlook Online als Beispiel, beginnt der Datenverkehr wie folgt:

- DNS Standard Query and DNS Response for outlook.office365.com with matching QueryIDs. Es ist wichtig, den Zeitabstand für diese Umdrehung zu beachten, sowie an der Stelle, an der das globale Office 365-DNS die Anforderung zur Namensauflösung sendet. Idealerweise möglichst lokal und nicht auf halbem Weg auf der ganzen Welt.

- Eine HTTP GET-Anforderung, deren Statusbericht dauerhaft verschoben wurde (301)

- RWS-Datenverkehr einschließlich RWS Connect-Anforderungen und Connect-Antworten. (Dies ist Remote Winsock, die eine Verbindung für Sie herstellen.)

- Eine TCP-SYN- und TCP-SYN/ACK-Unterhaltung. Viele der Einstellungen in dieser Unterhaltung haben Auswirkungen auf Ihre Leistung.

- Dann eine Reihe von TLS:TLS-Datenverkehr, in dem der TLS-Handshake und die TLS-Zertifikatunterhaltungen stattfinden. (Denken Sie daran, dass die Daten über SSL/TLS verschlüsselt sind.)

Alle Teile des Datenverkehrs sind wichtig und verbunden, aber kleine Teile der Ablaufverfolgung enthalten Informationen, die im Hinblick auf die Leistungsbehandlung besonders wichtig sind, daher konzentrieren wir uns auf diese Bereiche. Da wir bei Microsoft genügend Office 365-Leistungsproblembehandlung durchgeführt haben, um eine Top-Ten-Liste häufiger Probleme zu kompilieren, konzentrieren wir uns auf diese Probleme und die Verwendung der Tools, die wir als Nächstes zum Rooten dieser Probleme verwenden müssen.

Wenn Sie sie noch nicht alle installiert haben, werden in der folgenden Matrix mehrere Tools verwendet. Wo möglich. Links zu den Installationspunkten werden bereitgestellt. Die Liste enthält gängige Tools für die Netzwerkablaufverfolgung wie [Netmon](https://www.microsoft.com/download/details.aspx?id=4865) und [Wireshark,](https://www.wireshark.org/)aber verwenden Sie jedes Ablaufverfolgungstool, mit dem Sie sich wohl fühlen und in dem Sie gewohnt sind, Netzwerkdatenverkehr zu filtern. Beachten Sie beim Testen:

- *Schließen Sie Ihre Browser, und testen*  Sie, ob nur ein Browser ausgeführt wird – Dadurch wird der gesamt erfasste Datenverkehr reduziert. Dies sorgt für eine weniger ausgelaste Ablaufverfolgung.
- *Leeren Des DNS-Resolvercaches*  auf dem Clientcomputer – Dies gibt Ihnen einen sauberen Schiefer, wenn Sie mit der Aufnahme beginnen, um eine sauberere Ablaufverfolgung zu erhalten.

## <a name="common-issues"></a>Häufig auftretende Probleme

Einige häufige Probleme, die möglicherweise auftreten und wie Sie sie in Ihrer Netzwerkverfolgung finden.

### <a name="tcp-windows-scaling"></a>TCP Windows Scaling

Gefunden in der SYN - SYN/ACK. Ältere oder veraltete Hardware nutzt möglicherweise nicht die TCP-Windows-Skalierung.  Ohne die richtigen TCP-Fensterskalierungseinstellungen füllt sich der standardmäßige 16-Bit-Puffer in TCP-Headern in Millisekunden.  Der Datenverkehr kann erst dann gesendet werden, wenn der Client eine Bestätigung erhält, dass die ursprünglichen Daten empfangen wurden, was zu Verzögerungen führt.

#### <a name="tools"></a>Tools

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Suchen nach

Suchen Sie nach dem SYN - SYN/ACK-Datenverkehr in Ihrer Netzwerkverfolgung.  Verwenden Sie in Netmon einen Filter wie  `tcp.flags.syn == 1` . Dieser Filter ist in Wireshark identisch.

![Filtern Sie in Netmon oder Wireshark nach Syn-Paketen für beide Tools: TCP. Flags.Syn == 1.](../media/4b9a12a1-c915-43c8-ac2f-a679d0435a29.PNG)

Beachten Sie, dass es für jede SYN eine Quellportnummer (SrcPort) gibt, die im Zielport (DstPort) der zugehörigen Bestätigung (SYN/ACK) übereinstimmen.

Um den Windows Scaling-Wert zu sehen, der von Ihrer Netzwerkverbindung verwendet wird, erweitern Sie zuerst die SYN und dann die zugehörige SYN/ACK.

![Grafik, die zeigt, wie SrcPort mit DstPort in einer Ablaufverfolgung übereinstimmen, um das Zeitdelta zu erhalten.](../media/6a4ca573-0253-4fbd-93e8-92821ee1c351.png)

### <a name="tcp-idle-time-settings"></a>TCP-Einstellungen für die Leerlaufzeit

In der Vergangenheit sind die meisten Umkreisnetzwerke für vorübergehende Verbindungen konfiguriert, d. h. leerlaufverbindungen werden in der Regel beendet. Tcp-Sitzungen im Leerlauf können von Proxys und Firewalls mit mehr als 100 bis 300 Sekunden beendet werden. Dies ist für Outlook Online problematisch, da es langfristige Verbindungen erstellt und verwendet, unabhängig davon, ob sie sich im Leerlauf befinden oder nicht.

Wenn Verbindungen durch Proxy- oder Firewallgeräte beendet werden, wird der Client nicht informiert, und ein Versuch, Outlook Online zu verwenden, bedeutet, dass ein Clientcomputer wiederholt versucht, die Verbindung wiederzubeleben, bevor eine neue hergestellt wird. Möglicherweise werden beim Laden der Seite Hänge im Produkt, Aufforderungen oder eine langsame Leistung angezeigt.

#### <a name="tools"></a>Tools

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Suchen nach

Sehen Sie sich in Netmon das Feld Zeitoffset für einen Roundtrip an. Ein Roundtrip ist die Zeit zwischen dem Senden einer Anforderung an den Server und dem Empfangen einer Antwort zurück. Überprüfen Sie zwischen dem Client und dem Ausgangspunkt (z. B. Client –- \> Proxy) oder client to Office 365 (Client -- \> Office 365). Dies ist in vielen Pakettypen zu sehen.

Als Beispiel kann der Filter in Netmon wie  `.Protocol.IPv4.Address == 10.102.14.112 AND .Protocol.IPv4.Address == 10.201.114.12` aussehen, oder, in Wireshark,  `ip.addr == 10.102.14.112 &amp;&amp; ip.addr == 10.201.114.12` .

> [!TIP]
> Sie wissen nicht, ob die IP-Adresse in Ihrer Ablaufverfolgung zu Ihrem DNS-Server gehört? Versuchen Sie, es an der Befehlszeile nach oben zu suchen. Klicken **Sie auf Ausführen** starten, und geben Sie \>  \> **cmd** ein, oder drücken Sie die **Windows-TASTE,** \> und geben Sie **cmd ein.** Geben Sie an der Eingabeaufforderung  `nslookup <the IP address from the network trace>` ein. Verwenden Sie zum Testen nslookup für die IP-Adresse Ihres eigenen Computers. > Eine Liste der Microsoft-IP-Bereiche finden Sie unter [Office 365-URLs und IP-Adressbereiche](./urls-and-ip-address-ranges.md).

Wenn ein Problem auftritt, erwarten Sie, dass lange Zeitoffsets angezeigt werden, in diesem Fall (Outlook Online), insbesondere in TLS:TLS-Paketen, die den Übergang von Anwendungsdaten anzeigen (z. B. in Netmon finden Sie Anwendungsdatenpakete über  `.Protocol.TLS AND Description == "TLS:TLS Rec Layer-1 SSL Application Data"` ). In der Sitzung sollte ein reibungsloser Verlauf in der Sitzung zu sehen sein. Wenn beim Aktualisieren von Outlook Online lange Verzögerungen angezeigt werden, kann dies durch einen hohen Grad an Zurücksetzungen verursacht werden.

### <a name="latencyround-trip-time"></a>Wartezeit/Roundtripzeit

Latenz ist ein Maß, das sich je nach vielen Variablen, z. B. dem Upgrade alternder Geräte, dem Hinzufügen einer großen Anzahl von Benutzern zu einem Netzwerk und dem Prozentsatz der Gesamtbandbreite, die von anderen Aufgaben in einer Netzwerkverbindung verbraucht wird, erheblich ändern kann.

Bandbreitenrechner für Office 365 sind auf dieser Seite Netzwerkplanung und Leistungsoptimierung [für Office 365](network-planning-and-performance.md) verfügbar.

Müssen Sie die Geschwindigkeit Ihrer Verbindung oder die Bandbreite Ihrer Internetdienstanbieterverbindung messen? Testen Sie diese Website (oder Websites wie diese): [Speedtest Official Site](https://www.speedtest.net/), oder fragen Sie Ihre bevorzugte Suchmaschine nach dem **Ausdrucksgeschwindigkeitstest ab.**

#### <a name="tools"></a>Tools

- Ping
- PsPing
- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Suchen nach

Zum Nachverfolgen der Latenz in einer Ablaufverfolgung profitieren Sie davon, dass Sie die CLIENTcomputer-IP-Adresse und die IP-Adresse des DNS-Servers in Office 365 aufgezeichnet haben. Dies dient der einfacheren Ablaufverfolgungsfilterung. Wenn Sie eine Verbindung über einen Proxy herstellen, benötigen Sie die CLIENTcomputer-IP-Adresse, die Proxy-/Ausgangs-IP-Adresse und die Office 365-DNS-IP-Adresse, um die Arbeit zu vereinfachen.

Eine ping-Anforderung, die an outlook.office365.com gesendet wird, gibt den Namen des Datencenters an, das die Anforderung empfängt, auch wenn  *ping*  möglicherweise keine Verbindung herstellen kann, um die aufeinanderfolgenden ICMP-Pakete der Marke zu senden. Wenn Sie PsPing (ein kostenloses Tool zum Herunterladen) und den Port (443) und vielleicht IPv4 (-4) verwenden, erhalten Sie eine durchschnittliche Roundtripzeit für gesendete Pakete. Dies funktioniert für andere URLs in den Office 365-Diensten, z. B. `psping -4 yourSite.sharepoint.com:443` . In der Tat können Sie eine Reihe von Pings angeben, um ein größeres Beispiel für Ihren Durchschnitt zu erhalten, versuchen Sie es wie `psping -4 -n 20 yourSite-my.sharepoint.com:443` .

> [!NOTE]
> PsPing sendet keine ICMP-Pakete. Es pingt mit TCP-Paketen über einen bestimmten Port, sodass Sie einen beliebigen Port verwenden können, den Sie kennen, um geöffnet zu sein. In Office 365, das SSL/TLS verwendet, versuchen Sie, Port :443 an Ihre PsPing anfügen.

![Screenshot, der eine Pingauflösungs-outlook.office365.com und ein PSPing mit der 443-Gruppe zeigt, aber auch eine durchschnittliche RTT von 6,5 ms meldet.](../media/c64339f2-2c96-45b8-b168-c2a060430266.PNG)

Wenn Sie die Office 365-Seite mit langsamer Leistung geladen haben, während Sie eine Netzwerkverfolgung ausführen, sollten Sie eine Netmon- oder Wireshark-Ablaufverfolgung nach `DNS` filtern. Dies ist einer der IPs, die wir suchen.

Hier sind die Schritte, die Sie ausführen müssen, um Ihr Netmon zu filtern, um die IP-Adresse zu erhalten (und einen Blick auf die DNS-Latenz zu werfen). In diesem Beispiel outlook.office365.com verwendet, kann aber auch die URL eines SharePoint Online-Mandanten (z. B. hithere.sharepoint.com) verwendet werden.

1. Pingen Sie die URL, und noten Sie in den Ergebnissen den Namen und die IP-Adresse des DNS-Servers, `ping outlook.office365.com` an den die Pinganforderung gesendet wurde.
2. Netzwerkverfolgung, die die Seite öffnet, oder die Aktion, die das Leistungsproblem verursacht, oder, wenn eine hohe Latenz auf dem Ping auftritt, selbst, netzwerkverfolgung.
3. Öffnen Sie die Ablaufverfolgung in Netmon, und filtern Sie nach DNS (dieser Filter funktioniert auch in Wireshark, ist jedoch auf die Kleinschreibung `-- dns` sensibel). Da Sie den Namen des DNS-Servers aus Ihrem Ping kennen, können Sie in Netmon auch schneller filtern: , das in Wireshark dns und frame so aussieht, enthält `DNS AND ContainsBin(FrameData, ASCII, "namnorthwest")` "namnorthwest".<br/>Öffnen Sie das Antwortpaket, und klicken Sie im Fenster Netmon **Frame Details** auf **DNS,** um weitere Informationen zu erhalten. In den DNS-Informationen finden Sie die IP-Adresse des DNS-Servers, an den die Anforderung in Office 365 gesendet wurde. Sie benötigen diese IP-Adresse für den nächsten Schritt (das PsPing-Tool). Entfernen Sie den Filter, klicken Sie mit der rechten Maustaste auf die DNS-Antwort in Netmon (**Frame Summary** Find Conversations DNS ), um die \>  \> DNS-Abfrage und -Antwort nebeneinander zu sehen.
4. Notieren Sie sich in Netmon auch die Spalte Zeitversatz zwischen der DNS-Anforderung und der Antwort. Im nächsten Schritt ist das einfach zu installierende und zu verwendende [PsPing-Tool](/sysinternals/downloads/psping) sehr praktisch, sowohl weil ICMP häufig in Firewalls blockiert wird, als auch weil PsPing die Latenz in Millisekunden elegant verfolgt. PsPing schließt eine TCP-Verbindung mit einer Adresse und einem Port ab (in unserem Fall offener Port 443).
5. Installieren Sie PsPing.
6. Öffnen Sie eine Eingabeaufforderung (Cmd vom Typ Start ausführen \> \> oder Windows Key-Typ cmd), und ändern Sie das Verzeichnis in das Verzeichnis, in dem Sie PsPing installiert haben, um \> den Befehl PsPing auszuführen. In meinen Beispielen sehen Sie, dass ich einen Ordner "Perf" im Stammverzeichnis von C erstellt habe. Sie können dies auch für den schnellen Zugriff tun.
7. Geben Sie den Befehl ein, damit Sie PsPing für die IP-Adresse des Office 365-DNS-Servers aus Ihrer früheren Netmon-Ablaufverfolgung erstellen, einschließlich der Portnummer, z. B. `psping -n 20 132.245.24.82:445` . Dadurch erhalten Sie eine Sampling von 20 Pings und die durchschnittliche Wartezeit, wenn PsPing beendet wird.

Wenn Sie über einen Proxyserver zu Office 365 gehen, sind die Schritte etwas anders. Sie würden zunächst PsPing an Ihren Proxyserver senden, um einen durchschnittlichen Latenzwert in Millisekunden zu proxy/egress und back zu erhalten, und dann entweder PsPing auf dem Proxy oder auf einem Computer mit einer direkten Internetverbindung ausführen, um den fehlenden Wert (den zu Office 365 und zurück) zu erhalten.

Wenn Sie PsPing über den Proxy ausführen möchten, haben Sie zwei Millisekundenwerte: Clientcomputer zu Proxyserver oder Ausgangspunkt und Proxyserver für Office 365. Und Sie sind fertig! Nun, aufzeichnungswerte, sowieso.

Wenn Sie PsPing auf einem anderen Clientcomputer ausführen, der über eine direkte Verbindung mit dem Internet verfügt, d. h. ohne Proxy, haben Sie zwei Millisekundenwerte: Clientcomputer zu Proxyserver oder -ausgangspunkt und Clientcomputer zu Office 365. Subtrahieren Sie in diesem Fall den Wert des Clientcomputers an den Proxyserver oder den Ausgangspunkt von dem Wert des Clientcomputers zu Office 365, und Sie verfügen über die RTT-Nummern vom Clientcomputer zum Proxyserver oder -ausgangspunkt und von Proxyserver oder Ausgangspunkt auf Office 365.

Wenn Sie jedoch einen Clientcomputer am betroffenen Standort finden können, der direkt verbunden ist, oder den Proxy umgeht, können Sie sehen, ob das Problem dort zu Beginn reproduziert wird, und anschließend testen, ob es verwendet wird.

Latenz, wie in einer Netmon-Ablaufverfolgung zu sehen, können diese zusätzlichen Millisekunden addiert werden, wenn in einer bestimmten Sitzung genügend davon verfügbar ist.

![Allgemeine Latenz in Netmon, bei der die Netmon-Standardspalte Zeitdelta der Framezusammenfassung hinzugefügt wurde.](../media/7ad17380-8527-4bc2-9b9b-6310cf19ba6b.PNG)

> [!NOTE]
> Ihre IP-Adresse kann sich von den hier gezeigten IPs unterscheiden, z. B. gibt Ihr Ping etwas mehr wie 157.56.0.0/16 oder einen ähnlichen Bereich zurück. Eine Liste der von Office 365 verwendeten Bereiche finden Sie unter [Office 365-URLs und IP-Adressbereiche.](./urls-and-ip-address-ranges.md)

Denken Sie daran, alle Knoten zu erweitern (hier ist oben eine Schaltfläche vorhanden), wenn Sie beispielsweise nach 132.245 suchen möchten.

### <a name="proxy-authentication"></a>Proxyauthentifizierung

Dies gilt nur für Sie, wenn Sie einen Proxyserver verwenden. Andern falls nicht, können Sie diese Schritte überspringen. Bei ordnungsgemäßer Arbeit sollte die Proxyauthentifizierung konsistent in Millisekunden stattfinden. In Spitzenzeiten (z. B.) sollte keine zeitweise schlechte Leistung angezeigt werden.

Wenn die Proxyauthentifizierung aktiviert ist, müssen Sie jedes Mal, wenn Sie eine neue TCP-Verbindung mit Office 365 herstellen, um Informationen zu erhalten, einen Authentifizierungsprozess hinter den Kulissen bestehen. Wenn Sie beispielsweise von Kalender zu E-Mail in Outlook Online wechseln, authentifizieren Sie sich. Und wenn auf einer Seite Medien oder Daten von mehreren Websites oder Speicherorten angezeigt werden, authentifizieren Sie sich in SharePoint Online für jede unterschiedliche TCP-Verbindung, die zum Rendern der Daten erforderlich ist.

In Outlook Online können bei jedem Wechsel zwischen Kalender und Postfach langsame Ladezeiten oder langsame Seitenlasten in SharePoint Online angezeigt werden. Es gibt jedoch andere Symptome, die hier nicht aufgeführt sind.

Die Proxyauthentifizierung ist eine Einstellung auf dem ausziehende Proxyserver. Wenn es zu einem Leistungsproblem mit Office 365 kommt, müssen Sie sich an Ihr Netzwerkteam wenden.

#### <a name="tools"></a>Tools

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Suchen nach

Die Proxyauthentifizierung erfolgt immer dann, wenn eine neue TCP-Sitzung gesponnen werden muss, in der Regel zum Anfordern von Dateien oder Informationen vom Server oder zum Liefern von Informationen. Es kann z. B. eine Proxyauthentifizierung für HTTP GET- oder HTTP-POST-Anforderungen sein. Wenn Sie die Frames anzeigen möchten, in denen Sie Anforderungen in Ihrer Ablaufverfolgung authentifizieren möchten, fügen Sie netmon die Spalte "NTLMSSP Summary" hinzu, und filtern Sie nach  `.property.NTLMSSPSummary` . Um zu sehen, wie lange die Authentifizierung dauern soll, fügen Sie die Spalte Zeitdelta hinzu.

So fügen Sie Netmon eine Spalte hinzu:

1. Klicken Sie mit der rechten Maustaste auf eine Spalte, z. B. **Beschreibung**.
2. Klicken **Sie auf Spalten auswählen.**
3. Suchen _Sie die NTLMSSP-Zusammenfassung_ und _das Zeitdelta_ in der Liste, und klicken Sie auf **Hinzufügen**.
4. Verschieben Sie die neuen Spalten vor oder hinter der _Spalte Beschreibung,_ damit Sie sie nebeneinander lesen können.
5. Klicken Sie auf **OK**.

Auch wenn Sie die Spalte nicht hinzufügen, funktioniert der Netmon-Filter. Die Problembehandlung ist jedoch viel einfacher, wenn Sie sehen, in welcher Phase der Authentifizierung Sie sich begnnen.

Wenn Sie nach Instanzen der Proxyauthentifizierung suchen, sollten Sie unbedingt alle Frames untersuchen, in denen eine NTLM-Herausforderung vorhanden ist oder eine Authentifizierungsnachricht vorhanden ist. Klicken Sie bei Bedarf mit der rechten Maustaste auf das bestimmte Teil des Datenverkehrs, und suchen Sie \> Unterhaltungen TCP. Beachten Sie die Zeitdelta-Werte in diesen Unterhaltungen.

![Netmon-Ablaufverfolgung mit Proxyauthentifizierung, gefiltert nach Unterhaltung.](../media/b640f176-0a52-4bbb-972e-60fb3d6aece2.PNG)

Eine Verzögerung von vier Sekunden bei der Proxyauthentifizierung, wie in Wireshark zu sehen. Das **Zeitdelta aus der** vorherigen angezeigten Framespalte wurde durch Klicken mit der rechten Maustaste auf das Feld mit demselben Namen in den Framedetails und durch Auswählen von Hinzufügen als Spalte vorgenommen.  <br/> ![In Wireshark kann die Spalte "Zeitdelta vom vorherigen angezeigten Frame" durch Klicken mit der rechten Maustaste auf das Feld mit demselben Namen in den Framedetails und durch Auswählen von Hinzufügen als Spalte vorgenommen werden.](../media/f5b7bde4-8067-4ee0-bc7f-e9062ce1ba6f.PNG)

### <a name="dns-performance"></a>DNS-Leistung

Die Namensauflösung funktioniert am besten und am schnellsten, wenn sie so nah wie möglich am Land des Kunden stattfindet.

Wenn die DNS-Namensauflösung übersee erfolgt, kann sie Seitenlasten Sekunden hinzufügen. Idealerweise erfolgt die Namensauflösung in unter 100 ms. Andern falls nicht, sollten Sie weitere Untersuchungen anfingen.

> [!TIP]
> Sie sind nicht sicher, wie die Clientkonnektivität in Office 365 funktioniert? Sehen Sie sich hier das Dokument Clientverbindungsreferenz [an.](/previous-versions//dn741250(v=technet.10))

#### <a name="tools"></a>Tools

- Netmon
- Wireshark
- PsPing

#### <a name="what-to-look-for"></a>Suchen nach

Die Analyse der DNS-Leistung ist in der Regel ein weiterer Auftrag für eine Netzwerkverfolgung. PsPing ist jedoch auch hilfreich bei der Entscheidung in oder aus einer möglichen Ursache.

DER DNS-Datenverkehr basiert auf TCP- und UDP-Anforderungen und Antworten sind deutlich mit einer ID gekennzeichnet, die dabei hilft, eine bestimmte Anforderung mit ihrer spezifischen Antwort zu erfüllen. Der DNS-Datenverkehr wird angezeigt, wenn beispielsweise SharePoint Online einen Netzwerknamen oder eine URL auf einer Webseite verwendet. Als Faustregel wird der größte Teil dieses Datenverkehrs, mit Ausnahme der Übertragung von Zonen, über UDP ausgeführt.

In Netmon und Wireshark ist der grundlegendste Filter, mit dem Sie den DNS-Datenverkehr betrachten können, einfach `dns` . Achten Sie beim Angeben des Filters darauf, Klein klein zu verwenden. Denken Sie daran, den DNS-Resolvercache zu leeren, bevor Sie beginnen, das Problem auf Dem Clientcomputer zu reproduzieren. Wenn Sie beispielsweise eine langsame SharePoint Online-Seitenlast für die Startseite haben, sollten Sie alle Browser schließen, einen neuen Browser öffnen, die Ablaufverfolgung starten, den DNS-Resolvercache leeren und zu Ihrer SharePoint Online-Website navigieren. Nachdem die gesamte Seite aufgelöst wurde, sollten Sie die Ablaufverfolgung beenden und speichern.

![Ein grundlegender Filter für DNS in Netmon ist DNS.](../media/1bebc118-ca13-45f3-803f-ab73e7af401d.png)

Sie möchten hier den Zeitversatz betrachten. Und es kann hilfreich sein, netmon die **Spalte Zeitdelta** hinzuzufügen, die Sie ausführen können, indem Sie die folgenden Schritte ausführen:

1. Klicken Sie mit der rechten Maustaste auf eine Spalte, z. B. **Beschreibung**.
2. Klicken **Sie auf Spalten auswählen.**
3. Suchen _Sie zeitdelta_ in der Liste, und klicken Sie auf **Hinzufügen**.
4. Verschieben Sie die neue Spalte vor oder hinter der _Spalte Beschreibung,_ damit Sie sie nebeneinander lesen können.
5. Klicken Sie auf **OK**.

Wenn Sie eine interessante Abfrage finden, sollten Sie sie isolieren, indem Sie im Bereich Framedetails mit der rechten Maustaste auf diese Abfrage klicken, und wählen **Sie Unterhaltungen** \> **SUCHEN DNS aus.** Beachten Sie, dass der Bereich Netzwerkunterhaltungen direkt zu der bestimmten Unterhaltung im Protokoll des UDP-Datenverkehrs springt.

![Eine nach DNS gefilterte Netmon-Ablaufverfolgung der Outlook Online-Last und die Verwendung von Unterhaltungen suchen und DANN DNS zum Einen der Ergebnisse.](../media/763cf20e-7b48-4a37-9449-c9978cfe118b.PNG)

In Wireshark können Sie eine Spalte für die DNS-Zeit erstellen. Nehmen Sie ihre Ablaufverfolgung (oder öffnen Sie eine Ablaufverfolgung) in Wireshark, und filtern Sie nach `dns` , oder, hilfreicher,  `dns.time` . Klicken Sie auf eine beliebige DNS-Abfrage, und erweitern Sie im Bereich  `Domain Name System (response)` details. Sie sehen ein Feld für einen bestimmten Zeitraum (z. B. `[Time: 0.001111100 seconds]` . Klicken Sie dieses Mal mit der rechten Maustaste, und wählen **Sie Als Spalte übernehmen aus.** Dadurch erhalten Sie eine **Zeitspalte** für eine schnellere Sortierung Ihrer Ablaufverfolgung. Klicken Sie auf die neue Spalte, um nach absteigenden Werten zu sortieren, um zu sehen, welcher DNS-Aufruf am längsten aufgelöst wurde.

[Ein Durchsuchen von SharePoint Online, gefiltert in Wireshark nach (Kleinbuchstaben) dns.time, mit der Zeit aus den Details, die in eine Spalte und sortiert aufsteigend gemacht werden.](../media/1439dcc2-12ff-4ee2-9ef3-1484cf79c384.PNG)

Wenn Sie eine weitere Untersuchung der DNS-Auflösungszeit unternehmen möchten, versuchen Sie es mit einem PsPing für den DNS-Port, der von TCP verwendet wird (z. B.  `psping <IP address of DNS server>:53` ) . Wird weiterhin ein Leistungsproblem auftritt? In diesem Fall handelt es sich bei dem Problem wahrscheinlicher um ein umfassenderes Netzwerkproblem als um ein Problem mit einer bestimmten DNS-Anwendung, die Sie zur Lösung des Problems treffen. Es ist auch erwähnenswert, dass ein Ping an outlook.office365.com Ihnen sagt, wo die DNS-Namensauflösung für Outlook Online stattfindet (z. B. outlook-namnorthwest.office365.com).

Wenn das Problem DNS-spezifisch zu sein scheint, ist es möglicherweise erforderlich, sich mit Ihrer IT-Abteilung in Verbindung zu setzen, um sich die DNS-Konfigurationen und DNS-Weiterleitungen zu erschauen, um dieses Problem weiter zu untersuchen.

### <a name="proxy-scalability"></a>Proxyskalierbarkeit

Dienste wie Outlook Online in Office 365 gewähren Clients mehrere langfristige Verbindungen. Daher kann jeder Benutzer mehr Verbindungen verwenden, die eine längere Lebensdauer erfordern.

#### <a name="tools"></a>Tools

Mathematik

#### <a name="what-to-look-for"></a>Suchen nach

Es gibt kein spezifisches Tool zur Netzwerkverfolgung oder Problembehandlung. Stattdessen basiert sie auf Bandbreitenberechnungen, die Einschränkungen und andere Variablen enthalten.

### <a name="tcp-max-segment-size"></a>MAXIMALE TCP-Segmentgröße

Gefunden in der SYN - SYN/ACK.  Überprüfen Sie bei dieser Überprüfung alle Leistungsnetzwerkverfolgungen, die Sie verwendet haben, um sicherzustellen, dass TCP-Pakete so konfiguriert sind, dass sie die maximal mögliche Datenmenge übertragen.

Ziel ist es, einen MSS von 1460 Byte für die Übertragung von Daten zu sehen. Wenn Sie sich hinter einem Proxy befinden oder eine NAT verwenden, denken Sie daran, diesen Test vom Client zum Proxy/Ausstieg/NAT und von proxy/egress/NAT zu Office 365 für optimale Ergebnisse zu führen! Dies sind unterschiedliche TCP-Sitzungen.

#### <a name="tools"></a>Tools

Netmon

#### <a name="what-to-look-for"></a>Suchen nach

TCP Max Segment Size (MSS) ist ein weiterer Parameter des dreihändigen Handshakes in Ihrer Netzwerkverfolgung, d. h., Sie finden die benötigten Daten im SYN -SYN/ACK-Paket. MSS ist eigentlich recht einfach zu sehen.

Öffnen Sie jede Leistungsnetzwerkverfolgung, die Sie haben, und finden Sie die Verbindung, auf die Sie gespannt sind, oder die das Leistungsproblem veranschaulicht.

> [!NOTE]
> Wenn Sie eine Ablaufverfolgung suchen und den für Ihre Unterhaltung relevanten Datenverkehr finden müssen, filtern Sie nach der IP des Clients, der IP des Proxyservers oder des Ausgangspunkts oder beides. Direkt gehend müssen Sie die URL pingen, die Sie auf die IP-Adresse von Office 365 in der Ablaufverfolgung testen, und nach ihr filtern.

Sehen Sie sich die Ablaufverfolgung aus zweiter Hand an? Versuchen Sie, Filter zu verwenden, um sich zu orientieren. Führen Sie in Netmon eine Suche basierend auf der URL aus, z. B. , notieren Sie sich `Containsbin(framedata, ascii, "sphybridExample")` die Framenummer.

Verwenden Sie in Wireshark etwa  `frame contains "sphybridExample"` . Wenn Sie feststellen, dass Remote Winsock (RWS)-Datenverkehr gefunden wurde (er kann als [PSH, ACK] in Wireshark angezeigt werden), denken Sie daran, dass die RWS-Verbindungen kurz vor relevanter SYN - SYN/ACKs angezeigt werden können, wie zuvor erläutert.

An diesem Punkt können Sie die Framenummer aufzeichnen, den Filter ablegen und im Fenster Netzwerkunterhaltungen in Netmon auf Den ganzen Datenverkehr klicken, um die nächste SYN anzuzeigen. 

Wichtig: Wenn Sie zum Zeitpunkt der Ablaufverfolgung keine DER IP-Adressinformationen erhalten haben, erhalten Sie bei der Suche nach Ihrer URL in der Ablaufverfolgung (z. B. Teil von) DIE IP-Adressen, nach der gefiltert werden `sphybridExample-my.sharepoint.com` soll.

Suchen Sie die Verbindung in der Ablaufverfolgung, die Sie sehen möchten. Dazu können Sie entweder die Ablaufverfolgung prüfen, nach IP-Adressen filtern oder bestimmte Unterhaltungs-IDs im Fenster Netzwerkunterhaltungen in Netmon auswählen. Nachdem Sie das SYN-Paket gefunden haben, erweitern Sie tcp (in Netmon) oder Transmission Control Protocol (in Wireshark) im Bereich Framedetails. Erweitern Sie TCP-Optionen und MaxSegmentSize. Suchen Sie den zugehörigen SYN-ACK-Frame, und erweitern Sie TCP-Optionen und MaxSegmentSize. Der kleinere der beiden Werte ist Die maximale Segmentgröße. In dieser Abbildung verwende ich die integrierte Spalte in Netmon namens TCP Troubleshoot.

![Netzwerkverfolgung, die in Netmon mithilfe der integrierten Spalten gefiltert wurde.](../media/e073df13-71f8-497a-83b4-bb9f70bd9833.PNG)

Die integrierte Spalte befindet sich oben im **Bereich Framedetails.** (Klicken Sie erneut auf Spalten, und wählen Sie dann Zeitzone aus, um zur Normalansicht **zurück zu wechseln.)** 

![Hier finden Sie die Dropdownliste Spalten für die OPTION TCP-Problembehandlung (oben in der Framezusammenfassung).](../media/64fd4baa-a872-4f07-b959-752d7d37fd62.PNG)

Hier ist eine gefilterte Ablaufverfolgung in Wireshark. Es gibt einen Filter, der für den MSS-Wert ( ) spezifisch `tcp.options.mss` ist. Die Frames eines SYN-, SYN/ACK- und ACK-Handshakes sind am unteren Rand des Wireshark-Äquivalents mit Framedetails verknüpft (frame 47 ACK, links to 46 SYN/ACK, links to 43 SYN), um diese Art von Arbeit zu vereinfachen.

![Ablaufverfolgung, die in Wireshark nach tcp.options.mss für maximale Segmentgröße (Max Segment Size, MSS) gefiltert wurde.](../media/51e278db-801b-48bc-9b68-87cf92f03fd6.PNG)

Wenn Sie selektive **Bestätigung** überprüfen müssen (nächstes Thema in dieser Matrix), schließen Sie Ihre Ablaufverfolgung nicht!

### <a name="selective-acknowledgment"></a>Selektive Bestätigung

Gefunden in der SYN - SYN/ACK. Muss sowohl in SYN als auch in SYN/ACK als zulässig gemeldet werden. Die selektive Bestätigung (SELECTIVE Acknowledgement, SACK) ermöglicht eine reibungslosere Erneute Übertragung von Daten, wenn ein Paket oder ein Paket fehlt. Geräte können dieses Feature deaktivieren, was zu Leistungsproblemen führen kann.

Wenn Sie sich hinter einem Proxy befinden oder eine NAT verwenden, denken Sie daran, diesen Test vom Client zum Proxy/Ausstieg/NAT und von proxy/egress/NAT zu Office 365 für optimale Ergebnisse zu führen! Dies sind unterschiedliche TCP-Sitzungen.

#### <a name="tools"></a>Tools

Netmon

#### <a name="what-to-look-for"></a>Suchen nach

Die selektive Bestätigung (SACK) ist ein weiterer Parameter im SYN-SYN/ACK-Handshake. Sie können Ihre Ablaufverfolgung auf unterschiedliche Weise nach SYN - SYN/ACK filtern.

Suchen Sie die Verbindung in der Ablaufverfolgung, die Sie sehen möchten, indem Sie entweder die Ablaufverfolgung durchsuchen, nach IP-Adressen filtern oder mithilfe des Fensters Netzwerkunterhaltungen in Netmon auf eine Unterhaltungs-ID klicken. Nachdem Sie das SYN-Paket gefunden haben, erweitern Sie TCP in Netmon oder Das Übertragungssteuerungsprotokoll in Wireshark im Abschnitt Framedetails. Erweitern Sie TCP-Optionen und dann SACK. Suchen Sie den zugehörigen SYN-ACK-Frame, und erweitern Sie tcp-Optionen und das zugehörige FELD SACK. Stellen Sie sicher, dass SACK sowohl in SYN als auch in SYN/ACK zulässig ist. Hier sind DIE SACK-Werte, die sowohl in Netmon als auch in Wireshark angezeigt werden.

![Selektive Bestätigung (SACK) in Netmon als Ergebnis von tcp.flags.syn == 1.](../media/216f556f-5031-4ed2-b066-a0d9b3251fa2.PNG)

![SACK wie in Wireshark mit dem Filter tcp.flags.syn == 1.](../media/0a6e26e5-43dc-403b-adc9-3349a55f4e4b.PNG)

### <a name="dns-geolocation"></a>DNS-Geolocation

Wo in der Welt versucht Office 365, Ihre DNS-Aufrufe zu beheben, wirkt sich ihre Verbindungsgeschwindigkeit aus.

In Outlook Online wird nach Abschluss der ersten DNS-Suche der Speicherort dieses DNS verwendet, um eine Verbindung mit dem nächstgelegenen Datencenter herzustellen. Sie werden mit einem Outlook Online-CAS-Server verbunden, der das Backbonenetzwerk verwendet, um eine Verbindung mit dem Rechenzentrum herzustellen, in dem Ihre Daten gespeichert sind. Dies ist schneller.

Beim Zugriff auf SharePoint Online wird ein Benutzer, der ins Ausland reist, an sein aktives Datencenter geleitet – das ist der DC, dessen Standort auf der Home-Base des SPO-Mandanten basiert (also ein dC in den USA, wenn der Benutzer usa-basiert ist).

Lync Online verfügt über aktive Knoten in mehreren dC gleichzeitig. Wenn Anforderungen für Lync-Onlineinstanzen gesendet werden, bestimmt Microsofts DNS, woher die Anforderung in der Welt stammt, und gibt IP-Adressen vom nächstgelegenen regionalen DC zurück, in dem Lync Online aktiv ist.

> [!TIP]
> Benötigen Sie weitere Informationen dazu, wie Clients eine Verbindung mit Office 365 herstellen? Sehen Sie sich den [Referenzartikel "Clientkonnektivität"](/previous-versions//dn741250(v=technet.10)) (und die hilfreichen Grafiken) an.

#### <a name="tools"></a>Tools

- Ping
- PsPing

#### <a name="what-to-look-for"></a>Suchen nach

Anforderungen für die Namensauflösung von den DNS-Servern des Clients an die DNS-Server von Microsoft sollten in den meisten Fällen dazu führen, dass Microsoft DNS die IP-Adresse eines regionalen Rechenzentrums (DC) zurücksen. Was bedeutet dies für Sie? Wenn Sich Ihre Zentrale in Bengal, Indien, befindet, Sie jedoch in den Vereinigten Staaten unterwegs sind, sollten Die DNS-Server von Microsoft, wenn Ihr Browser eine Anforderung für Outlook Online stellt, Ihnen DIE IP-Adressen an Rechenzentren in den Vereinigten Staaten - ein regionales Datencenter - übersennen. Wenn E-Mails von Outlook benötigt werden, werden diese Daten über das schnelle Backbonenetzwerk von Microsoft zwischen den Rechenzentren gesendet.

DNS funktioniert am schnellsten, wenn die Namensauflösung so nah wie möglich am Benutzerspeicherort erfolgt. Wenn Sie in Europa sind, möchten Sie zu einem Microsoft DNS in Europa wechseln und (idealerweise) ein Rechenzentrum in Europa verwenden. Die Leistung eines Clients in Europa, der zu DNS und einem Datencenter in Amerika geht, wird langsamer sein.

Führen Sie das Ping-Tool outlook.office365.com, um zu bestimmen, wo in der Welt Ihre DNS-Anforderung geroutet wird. Wenn Sie sich in Europa befinden, sollten Sie eine Antwort von so etwas wie outlook-emeawest.office365.com. Erwarten Sie in Amerika so etwas wie outlook-namnorthwest.office365.com.

Öffnen Sie die Eingabeaufforderung auf dem Clientcomputer (über cmd start \> run oder windows key type \> \> cmd). Geben Sie ping-outlook.office365.com ein, und drücken Sie die EINGABETASTE. Denken Sie daran, -4 anzugeben, wenn Sie angeben möchten, dass ein Ping über IPv4 ausgeführt werden soll. Möglicherweise erhalten Sie keine Antwort von den ICMP-Paketen, sie sollten jedoch den Namen des DNS sehen, an das die Anforderung geroutet wurde. Wenn Sie die Latenznummern für diese Verbindung sehen möchten, versuchen Sie, PsPing an die IP-Adresse des Servers zu senden, der durch ping zurückgegeben wird.

![Ping von outlook.office365.com, der die Auflösung in outlook-namnorthwest zeigt.](../media/06c944d5-6159-43ec-aa31-757770695e8b.PNG)

![PsPing an die ip-Adresse, die vom Ping-to-Outlook.office365.com durchschnittliche Wartezeit von 28 Millisekunden angezeigt wird.](../media/f2b25a75-1a87-4479-b8a7-fa4375683507.PNG)

### <a name="office-365-application-troubleshooting"></a>Problembehandlung bei Office 365-Anwendungen

#### <a name="tools"></a>Tools

- Netmon
- HTTPWatch
- F12-Konsole im Browser

In diesem netzwerkspezifischen Artikel werden tools, die in der anwendungsspezifischen Problembehandlung verwendet werden, nicht behandelt. Sie finden jedoch Ressourcen, die *Sie auf dieser* [Seite verwenden können.](https://support.office.com/article/Network-planning-and-performance-tuning-for-Office-365-e5f1228c-da3c-4654-bf16-d163daee8848)

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Häufig gestellte Fragen zu Office 365-Endpunkten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)