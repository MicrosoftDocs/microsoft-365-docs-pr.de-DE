---
title: Schritt-für-Schritt-Stapel zum Schutz vor Bedrohungen in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
description: Folgen Sie dem Pfad einer eingehenden Nachricht über den Bedrohungsfilterstapel in Microsoft Defender für Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e892ebe04887527cf57e4ea44f67c4aaa775b228
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683295"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a>Schrittweiser Bedrohungsschutz in Microsoft Defender für Office 365

Der Microsoft Defender für Office 365- oder Filterstapel kann wie in diesem Artikel in vier Phasen aufgeschlüsselt werden. Im Allgemeinen durchläuft eingehende E-Mails alle diese Phasen vor der Zustellung, aber der tatsächliche Pfad der E-Mail unterliegt der Defender for Office 365 Organisation.

> [!TIP]
> Bleiben Sie bis zum Ende dieses  Artikels dran, um eine einheitliche Grafik aller 4 Phasen von Defender for Office 365 zu finden!

## <a name="phase-1---edge-protection"></a>Phase 1 – Edge protection

Leider sind Edgeblöcke, die *einmal* kritisch waren, jetzt relativ einfach für schlechte Akteure zu überwinden. Im Laufe der Zeit wird hier weniger Datenverkehr blockiert, aber er bleibt ein wichtiger Teil des Stapels.  

Edgeblöcke sind so konzipiert, dass sie automatisch sind. Bei falsch positivem Ergebnis werden Die Absender benachrichtigt und informiert, wie sie ihr Problem beheben können. Connectors von vertrauenswürdigen Partnern mit eingeschränkter Zuverlässigkeit können beim Onboarding neuer Endpunkte die Lieferfähigkeit sicherstellen oder temporäre Außerkraftsetzungen setzen.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="Phase 1 der Filterung in Defender for Office 365 ist Edge Protection.":::

1. **Die Netzwerkdrosselung** schützt Office 365 und Kunden vor Denial of Service (DOS)-Angriffen, indem die Anzahl der Nachrichten begrenzt wird, die von einer bestimmten Gruppe von Infrastruktur übermittelt werden können.

2. **Durch die IP-Reputation und -Einschränkung** werden Nachrichten blockiert, die von bekannten ungültigen Verbindungs-IP-Adressen gesendet werden. Wenn eine bestimmte IP in kurzer Zeit viele Nachrichten sendet, werden sie gedrosselt.

3. **Die Domänen reputation** blockiert alle Nachrichten, die von einer bekannten ungültigen Domäne gesendet werden.

4. **Verzeichnisbasierte Edgefilterblöcke** versuchen, die Verzeichnisinformationen einer Organisation über SMTP zu erhalten.

5. **Die Backscattererkennung** verhindert, dass eine Organisation über ungültige Unzustellungsberichte (Non-Delivery Reports, NDRs) angegriffen wird.

6. **Die erweiterte Filterung für Connectors** behält Authentifizierungsinformationen bei, auch wenn der Datenverkehr ein anderes Gerät durchläuft, bevor Office 365. Dadurch wird die Filterstapelgenauigkeit verbessert, einschließlich heuristischem Clustering, Antis spoofing und Antiphishingmodellen für maschinelles Lernen, auch wenn es sich um komplexe oder hybride Routingszenarien handelt.

## <a name="phase-2---sender-intelligence"></a>Phase 2 – Sender Intelligence

Features in der Absenderintelligenz sind entscheidend für das Abfangen von Spam, Massen, Identitätswechsel und nicht autorisierte Spoofnachrichten und berücksichtigen auch die Phisherkennung. Die meisten dieser Features sind einzeln konfigurierbar.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="Phase 2 der Filterung in MDO ist Sender Intelligence.":::

1. **Erkennungsauslöser** und Warnungen zur Erkennung von Kontokompromissen werden ausgelöst, wenn ein Konto ein anomales Verhalten hat, das mit der Kompromissbereitschaft konsistent ist. In einigen Fällen wird das Benutzerkonto blockiert und daran gehindert, weitere E-Mail-Nachrichten zu senden, bis das Problem vom Sicherheitsteam einer Organisation behoben wurde.

2. **Die** E-Mail-Authentifizierung umfasst sowohl vom Kunden konfigurierte Methoden als auch Methoden, die in der Cloud eingerichtet wurden, um sicherzustellen, dass Absender autorisierte, authentifizierte E-Mail-Absender sind. Diese Methoden wehren sich gegen Spoofing.
    - **SPF** kann E-Mails basierend auf DNS-TXT-Einträgen ablehnen, die IP-Adressen und Server auflisten, die E-Mails im Namen der Organisation senden dürfen.
    - **DKIM bietet** eine verschlüsselte Signatur, die den Absender authentifiziert.
    - **Mit DMARC** können Administratoren SPF und DKIM nach Bedarf in ihrer Domäne markieren und die Ausrichtung zwischen den Ergebnissen dieser beiden Technologien erzwingen.
    - **ARC** ist nicht kundenkonfiguriert, baut aber auf DMARC auf, um mit der Weiterleitung in Mailinglisten zu arbeiten und gleichzeitig eine Authentifizierungskette zu erfassen.

3. **Spoof intelligence** ist in der Lage, diejenigen zu filtern, die "spoof" (d. h. diejenigen, die E-Mails im Auftrag eines anderen Kontos senden oder die Weiterleitung für eine Mailingliste) von böswilligen Absendern, die organisatorische oder bekannte externe Domänen imitieren. Es trennt legitime "im Auftrag von" E-Mails von Absendern, die spoofen, um Spam- und Phishingnachrichten zu senden.

    **Organisationsinterne Spoofintelligenz** erkennt und blockiert Spoofversuche aus einer Domäne innerhalb der Organisation.

4. **Domänenübergreifende Spoofintelligenz** erkennt und blockiert Spoofversuche aus einer Domäne außerhalb der Organisation.

5. **Mit der Massenfilterung** können Administratoren eine Massenvertrauensstufe (Bulk Confidence Level, BCL) konfigurieren, die angibt, ob die Nachricht von einem Massensender gesendet wurde. Administratoren können den Massenschieberegler in der Antispamrichtlinie verwenden, um zu entscheiden, welche Ebene von Massen-E-Mails als Spam behandelt werden soll.

6. **Die Postfachintelligenz** lernt aus standardmäßigen Benutzer-E-Mail-Verhaltensweisen. Es nutzt das Kommunikationsdiagramm eines Benutzers, um zu erkennen, wann ein Absender nur eine Person zu sein scheint, mit der der Benutzer normalerweise kommuniziert, aber tatsächlich bösartig ist. Diese Methode erkennt identitätswechsel.

7. **Der Identitätswechsel der Postfachintelligenz** aktiviert oder deaktiviert erweiterte Identitätswechselergebnisse basierend auf der individuellen Absenderzuordnung jedes Benutzers. Wenn diese Funktion aktiviert ist, hilft dieses Feature, den Identitätswechsel zu identifizieren.

8. **Der Benutzerwechsel ermöglicht** es einem Administrator, eine Liste von Zielen mit hohem Wert zu erstellen, die wahrscheinlich als Identitätswechsel bezeichnet werden. Wenn eine E-Mail eintrifft, bei der der Absender nur den gleichen Namen und dieselbe Adresse wie das geschützte Konto mit hohem Wert zu haben scheint, wird die E-Mail markiert oder markiert. (Beispiel: *trα cye@contoso.com* für *tracye@contoso.com*).

9. **Der Domänenwechsel erkennt** Domänen, die der Domäne des Empfängers ähnlich sind und versuchen, wie eine interne Domäne aussahen. Dieser Identitätswechsel ist beispielsweise *tracye@liw α re.com* für *tracye@litware.com*.

## <a name="phase-3---content-filtering"></a>Phase 3 – Inhaltsfilterung

In dieser Phase beginnt der Filterstapel mit der Verarbeitung der spezifischen Inhalte der E-Mail, einschließlich der Hyperlinks und Anlagen.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="Phase 3 der Filterung in MDO ist Inhaltsfilterung.":::

1. **Transportregeln** (auch als Nachrichtenflussregeln oder Exchange Transportregeln bezeichnet) ermöglichen einem Administrator, eine vielzahl von Aktionen zu ergreifen, wenn für eine Nachricht ein ebenso breites Spektrum von Bedingungen erfüllt ist. Alle Nachrichten, die durch Ihre Organisation fließen, werden anhand der aktivierten Nachrichtenflussregeln/-transportregeln ausgewertet.

2. **Microsoft Defender Antivirus** und zwei *Antivirenmodule von* Drittanbietern werden verwendet, um alle bekannten Schadsoftware in Anlagen zu erkennen.

3. Die Antivirenmodule (AV) werden auch zum True-Type aller  Anlagen verwendet, sodass type blocking alle Anlagen der vom Administrator angegebenen Typen blockieren kann.

4. Wenn Microsoft Defender for Office 365 eine bösartige Anlage erkennt, werden der Dateihash und ein Hash seiner aktiven Inhalte der Exchange Online Protection (EOP) hinzugefügt. **Das Blockieren der** Anlagenverwenkung blockiert diese Datei über alle Office 365 und auf Endpunkten über MSAV-Cloudaufrufe.

5. **Heuristisches Clustering** kann anhand von Übermittlungshuristiken feststellen, dass eine Datei verdächtig ist. Wenn eine verdächtige Anlage gefunden wird, wird die gesamte Kampagne angehalten, und die Datei wird sandkasteniert. Wenn die Datei als schädlich festgestellt wird, wird die gesamte Kampagne blockiert.

6. **Computerlernmodelle** wirken sich auf die Kopfzeile, den Textkörper und die URLs einer Nachricht aus, um Phishingversuche zu erkennen.

7. Microsoft verwendet eine Bestimmung der Reputation aus dem URL-Sandkasten sowie die URL-Reputation von Drittanbieterfeeds im **Blockieren** der URL-Reputation, um alle Nachrichten mit einer bekannten schädlichen URL zu blockieren.

8. **Inhaltshuristiken können** verdächtige Nachrichten basierend auf der Struktur und Worthäufigkeit im Textkörper der Nachricht mithilfe von Machine Learning-Modellen erkennen.

9. **Sichere Anlagen** sandkastent jede Anlage für Defender für Office 365 Kunden, indem dynamische Analysen verwendet werden, um nie zuvor gesehene Bedrohungen zu erkennen.

10. **Die Detonation** verknüpfter Inhalte behandelt jede URL, die mit einer Datei in einer E-Mail verknüpft ist, als Anlage und sandt die Datei zum Zeitpunkt der Zustellung asynchron in einen Sandkasten.

11. **Die URL-Detonation** erfolgt, wenn die vorgelagerte Antiphishingtechnologie eine Nachricht oder URL als verdächtig findet. Die URL-Detonation sandkastent die URLs in der Nachricht zum Zeitpunkt der Zustellung.

## <a name="phase-4---post-delivery-protection"></a>Phase 4 – Post-Delivery Protection

Die letzte Phase erfolgt nach der E-Mail- oder Dateizustellung, die auf E-Mails in verschiedenen Postfächern und Dateien und Links erfolgt, die in Clients wie Microsoft Teams.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="Phase 4 der Filterung in Defender for Office 365 ist Post-Delivery Protection.":::

1. **Sichere Links** ist Defender für Office 365 klickzeitschutz. Jede URL in jeder Nachricht wird so umschlossen, dass sie auf Microsoft Safe Links-Server verweist. Wenn auf eine URL geklickt wird, wird sie mit der neuesten Reputation überprüft, bevor der Benutzer zur Zielwebsite umgeleitet wird. Die URL wird asynchron sandkasteniert, um ihre Reputation zu aktualisieren.

2. **Zero-Hour Auto-Purge (ZAP)** für Phishing erkennt und neutralisiert schädliche Phishingnachrichten, die bereits an Exchange Online wurden.

3. **ZAP für Schadsoftware** erkennt und neutralisiert schadhaft schädliche Schadsoftwarenachrichten, die bereits an Exchange Online übermittelt wurden.

4. **ZAP für Phishing** erkennt und neutralisiert schädliche Spamnachrichten, die bereits an Exchange Online zugestellt wurden.

5. **Mit Kampagnenansichten** können Administratoren das Gesamtbild eines Angriffs schneller und vollständiger sehen als jedes Team ohne Automatisierung. Microsoft nutzt die enormen Mengen an Antiphishing-, Antispam- und Anti-Malware-Daten über den gesamten Dienst, um Kampagnen zu identifizieren, und ermöglicht Administratoren dann, sie von Anfang bis Ende zu untersuchen, einschließlich Zielen, Auswirkungen und Flüssen, die auch in einem herunterladbaren Kampagnen-Write-up verfügbar sind.

6. **Die Report Message-Add-Ins** ermöglichen Es Benutzern, falsch positive Ergebnisse (gute E-Mails, fälschlicherweise als "schlecht" *gekennzeichnet)* oder falsch negative (schlechte E-Mails, die als "gut" gekennzeichnet *sind)* einfach an Microsoft zur weiteren Analyse zu melden.

7. **Sichere Links für Office-Clients** bieten den gleichen Schutz für sichere Links , nativ, innerhalb von Office Clients wie Word, PowerPoint und Excel.

8. Der Schutz für **OneDrive, SharePoint** und Teams bietet den gleichen Schutz vor schädlichen Dateien, nativ, innerhalb von OneDrive, SharePoint und Microsoft Teams.

9. Wenn eine URL, die auf eine Datei verweist, nach der Zustellung ausgewählt wird, wird bei der **Detonation** verknüpfter Inhalte eine Warnseite angezeigt, bis der Sandkasten der Datei abgeschlossen ist und die URL als sicher eingestuft wird.

## <a name="the-filtering-stack-diagram"></a>Das Filterstapeldiagramm

Das endgültige Diagramm (wie bei allen Teilen des *Diagramms,* aus dem es erstellt wird) kann sich ändern, wenn das Produkt wächst und entwickelt wird. Markieren Sie diese Seite, und verwenden Sie die **Feedbackoption,** die Sie unten finden, wenn Sie nach Updates fragen müssen. Für Ihre Datensätze ist dies der Stapel mit allen Phasen in der Reihenfolge:

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="Alle Phasen der Filterung in MDO in der Reihenfolge 1 bis 4.":::

## <a name="more-information"></a>Weitere Informationen

Müssen Sie Microsoft Defender für Office 365 ***jetzt _?** einrichten? Verwenden Sie diesen Stapel, _now*, mit diesem Schritt [für](protect-against-threats.md) Schritt, um mit dem Schutz Ihrer Organisation zu beginnen.

*Besonderer Dank von MSFTTracyP und dem* Dokument schreibenden Team an Dennis Garruba für diesen Inhalt.
