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
description: Folgen Sie dem Pfad einer eingehenden Nachricht über den Stapel für die Bedrohungsfilterung in Microsoft Defender für Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1113d04cabdabe2925242cb18dde78daf9ef6e2c
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194805"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a>Schrittweiser Bedrohungsschutz in Microsoft Defender für Office 365

Der Schutz- oder Filterstapel von Microsoft Defender für Office 365 kann wie in diesem Artikel in vier Phasen unterteilt werden. Im Allgemeinen werden eingehende E-Mails alle diese Phasen vor der Zustellung durchlaufen, aber der tatsächliche Pfad, den E-Mails einnimmt, unterliegt dem Defender einer Organisation für Office 365 Konfiguration.

> [!TIP]
> Warten Sie bis zum Ende dieses Artikels auf eine *einheitliche* Grafik aller vier Phasen von Defender für Office 365 Schutz!

## <a name="phase-1---edge-protection"></a>Phase 1: Edgeschutz

Leider sind Edgeblöcke, die einmal *kritisch* waren, für schlechte Akteure relativ einfach zu bewältigen. Im Laufe der Zeit wird hier weniger Datenverkehr blockiert, aber es bleibt ein wichtiger Teil des Stapels.  

Edgeblöcke sind so konzipiert, dass sie automatisch ausgeführt werden. Bei falsch positiven Ergebnissen werden Absender benachrichtigt und angewiesen, wie sie ihr Problem beheben können. Connectors von vertrauenswürdigen Partnern mit eingeschränktem Ruf können die Bereitstellung sicherstellen, oder temporäre Außerkraftsetzungen können beim Onboarding neuer Endpunkte eingerichtet werden.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="Phase 1 der Filterung in Defender für Office 365 ist Edgeschutz.":::

1. **Die Netzwerkdrosselung** schützt Office 365 Infrastruktur und Kunden vor Denial of Service (DOS)-Angriffen, indem die Anzahl der Nachrichten begrenzt wird, die von einer bestimmten Gruppe von Infrastruktur übermittelt werden können.

2. **Die IP-Zuverlässigkeit und -Drosselung** blockiert, dass Nachrichten von bekannten ungültigen IP-Adressen gesendet werden. Wenn eine bestimmte IP viele Nachrichten in einem kurzen Zeitraum sendet, werden sie gedrosselt.

3. **Die Domänenreputation** blockiert alle Nachrichten, die von einer bekannten ungültigen Domäne gesendet werden.

4. **Die verzeichnisbasierte Edgefilterung** blockiert Versuche, die Verzeichnisinformationen einer Organisation über SMTP zu sammeln.

5. **Die Rückscatter-Erkennung** verhindert, dass eine Organisation durch ungültige Unzustellbarkeitsberichte (Non-Delivery Reports, NDRs) angegriffen wird.

6. **Die erweiterte Filterung für Connectors** behält Authentifizierungsinformationen bei, auch wenn datenverkehr über ein anderes Gerät fließt, bevor Office 365 erreicht wird. Dies verbessert die Filterstapelgenauigkeit, einschließlich heuristischem Clustering, Antispoofing und Antiphishing-Machine Learning-Modellen, auch in komplexen oder hybriden Routingszenarien.

## <a name="phase-2---sender-intelligence"></a>Phase 2: Sender Intelligence

Features in der Absenderintelligenz sind wichtig für den Abfangen von Spam, Massennachrichten, Identitätswechsel und nicht autorisierten Spoofingnachrichten sowie für die Phishing-Erkennung. Die meisten dieser Features sind einzeln konfigurierbar.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="Phase 2 der Filterung in Defender für Office 365 ist Sender Intelligence.":::

1. Die Erkennung von **Kontokompromittierungsauslösern** und Warnungen wird ausgelöst, wenn ein Konto ein anomales Verhalten aufweist, das mit einer Kompromittierung konsistent ist. In einigen Fällen wird das Benutzerkonto blockiert und daran gehindert, weitere E-Mail-Nachrichten zu senden, bis das Problem vom Sicherheitsteam einer Organisation behoben wurde.

2. **Die E-Mail-Authentifizierung** umfasst vom Kunden konfigurierte Methoden und Methoden, die in der Cloud eingerichtet sind, um sicherzustellen, dass Absender autorisierte, authentifizierte E-Mail-Absender sind. Diese Methoden widersetzen sich Spoofing.
    - **SPF** kann E-Mails basierend auf DNS-TXT-Einträgen ablehnen, die IP-Adressen und Server auflisten, die E-Mails im Auftrag der Organisation senden dürfen.
    - **DKIM** stellt eine verschlüsselte Signatur bereit, die den Absender authentifiziert.
    - **MIT DMARC** können Administratoren SPF und DKIM nach Bedarf in ihrer Domäne markieren und die Ausrichtung zwischen den Ergebnissen dieser beiden Technologien erzwingen.
    - **ARC** ist nicht vom Kunden konfiguriert, baut jedoch auf DMARC auf, um beim Aufzeichnen einer Authentifizierungskette mit der Weiterleitung in Adresslisten zu arbeiten.

3. **Die Spoofintelligenz** kann diejenigen filtern, die "Spoofing" (d. h. diejenigen, die E-Mails im Auftrag eines anderen Kontos senden oder für eine Mailingliste weiterleiten) von böswilligen Absendern filtern, die Organisations- oder bekannte externe Domänen imitieren. Es trennt seriöse "im Auftrag von" E-Mails von Absendern, die Spoofing ausführen, um Spam- und Phishingnachrichten zu übermitteln.

    **Organisationsinterne Spoofintelligenz** erkennt und blockiert Spoofingversuche aus einer Domäne innerhalb der Organisation.

4. **Die domänenübergreifende Spoofintelligenz** erkennt und blockiert Spoofingversuche von einer Domäne außerhalb der Organisation.

5. Mit der **Massenfilterung** können Administratoren eine BCL -Stufe (Bulk Confidence Level) konfigurieren, die angibt, ob die Nachricht von einem Massenabsender gesendet wurde. Administratoren können den Massenschieberegler in der Antispamrichtlinie verwenden, um zu entscheiden, welche Menge von Massen-E-Mails als Spam behandelt werden soll.

6. **Die Postfachintelligenz** lernt aus standardmäßigen E-Mail-Verhaltensweisen von Benutzern. Es nutzt das Kommunikationsdiagramm eines Benutzers, um zu erkennen, wann ein Absender nur jemand zu sein scheint, mit dem der Benutzer in der Regel kommuniziert, aber tatsächlich bösartig ist. Diese Methode erkennt den Identitätswechsel.

7. **Der Identitätswechsel der Postfachintelligenz** aktiviert oder deaktiviert erweiterte Identitätswechselergebnisse basierend auf der individuellen Absenderzuordnung jedes Benutzers. Wenn diese Funktion aktiviert ist, kann sie den Identitätswechsel identifizieren.

8. **Der Benutzeridentitätswechsel** ermöglicht es einem Administrator, eine Liste mit Zielen mit hohem Wert zu erstellen, die wahrscheinlich einen Identitätswechsel ausführen. Wenn eine E-Mail eintrifft, bei der der Absender nur denselben Namen und die gleiche Adresse wie das geschützte Konto mit hohem Wert zu haben scheint, wird die E-Mail markiert oder markiert. (z. *B. trα cye@contoso.com* für *tracye@contoso.com*).

9. **Der Domänenidentitätswechsel** erkennt Domänen, die der Domäne des Empfängers ähneln und versuchen, wie eine interne Domäne auszusehen. Dieser Identitätswechsel *tracye@liw α re.com* beispielsweise für *tracye@litware.com*.

## <a name="phase-3---content-filtering"></a>Phase 3 : Inhaltsfilterung

In dieser Phase beginnt der Filterstapel, den spezifischen Inhalt der E-Mail zu verarbeiten, einschließlich seiner Hyperlinks und Anlagen.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="Phase 3 der Filterung in MDO ist die Inhaltsfilterung.":::

1. **Transportregeln** (auch als Nachrichtenflussregeln oder Exchange Transportregeln bezeichnet) ermöglichen es einem Administrator, eine Vielzahl von Aktionen auszuführen, wenn eine ebenso breite Palette von Bedingungen für eine Nachricht erfüllt ist. Alle Nachrichten, die durch Ihre Organisation fließen, werden anhand der aktivierten Nachrichtenflussregeln/Transportregeln ausgewertet.

2. **Microsoft Defender Antivirus** und zwei Antivirenmodule von Drittanbietern werden verwendet, um alle bekannten *Schadsoftware* in Anlagen zu erkennen.

3. Die Antivirus-Engines (AV) werden auch verwendet, um alle Anlagen auf "true" zu setzen, sodass die **Typblockierung** alle Anlagen von Typen blockieren kann, die der Administrator angibt.

4. Wenn Microsoft Defender für Office 365 eine bösartige Anlage erkennt, werden der Hash der Datei und ein Hash des aktiven Inhalts Exchange Online Protection (EOP) hinzugefügt. Das Blockieren der **Anlagenreputation** blockiert diese Datei über alle Office 365 und auf Endpunkten über MSAV-Cloudaufrufe.

5. **Heuristic clustering** can determine that a file is suspicious based on delivery heuristics. Wenn eine verdächtige Anlage gefunden wird, wird die gesamte Kampagne angehalten, und die Datei wird im Sandkasten gespeichert. Wenn festgestellt wird, dass die Datei bösartig ist, wird die gesamte Kampagne blockiert.

6. **Machine Learning-Modelle** reagieren auf die Kopfzeile, den Textkörperinhalt und die URLs einer Nachricht, um Phishingversuche zu erkennen.

7. Microsoft verwendet eine Bestimmung der Zuverlässigkeit von URL-Sandboxing sowie der URL-Zuverlässigkeit von Feeds von Drittanbietern in **URL-Zuverlässigkeitsblockierung,** um alle Nachrichten mit einer bekannten schädlichen URL zu blockieren.

8. **Inhaltshuristiken** können verdächtige Nachrichten basierend auf der Struktur und Wortfrequenz innerhalb des Nachrichtentexts mithilfe von Machine Learning-Modellen erkennen.

9. **Tresor Attachments** sandboxes every attachment for Defender for Office 365 customers, using dynamic analysis to detect never-before seen threats.

10. **Die Detonation verknüpfter Inhalte** behandelt jede URL, die mit einer Datei in einer E-Mail verknüpft ist, als Anlage, wobei die Datei zum Zeitpunkt der Übermittlung asynchron in der Sandbox gespeichert wird.

11. **Die URL-Detonation** erfolgt, wenn die Upstream-Antiphishingtechnologie eine Nachricht oder URL als verdächtig findet. Die URL-Detonation sandkastent die URLs in der Nachricht zum Zeitpunkt der Übermittlung.

## <a name="phase-4---post-delivery-protection"></a>Phase 4: Schutz nach der Übermittlung

Die letzte Phase findet nach der E-Mail- oder Dateiübermittlung statt, wobei E-Mails in verschiedenen Postfächern und Dateien und Links verwendet werden, die in Clients wie Microsoft Teams angezeigt werden.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="Phase 4 der Filterung in Defender für Office 365 ist Post-Delivery-Schutz.":::

1. **Tresor Links** ist Defender für den Time-of-Click-Schutz von Office 365. Jede URL in jeder Nachricht wird umbrochen, um auf Microsoft Tresor Links-Server zu verweisen. Wenn auf eine URL geklickt wird, wird sie anhand der neuesten Zuverlässigkeit überprüft, bevor der Benutzer zur Zielwebsite umgeleitet wird. Die URL ist asynchron im Sandkasten gespeichert, um ihre Zuverlässigkeit zu aktualisieren.

2. **Zero-Hour Auto-Purge (ZAP) for Phishing** detects and neutralizes malicious phishing messages that have already beendelivered to Exchange Online mailboxes.

3. **ZAP für Schadsoftware** erkennt und neutralisiert bösartige Schadsoftwarenachrichten, die bereits an Exchange Online Postfächer übermittelt wurden.

4. **ZAP für Phishing** erkennt und neutralisiert schädliche Spamnachrichten, die bereits an Exchange Online Postfächer übermittelt wurden.

5. **Mit Kampagnenansichten** können Administratoren das Gesamtbild eines Angriffs sehen, schneller und vollständiger, als es jedes Team ohne Automatisierung hätte. Microsoft nutzt die großen Mengen an Antiphishing-, Antispam- und Antischadsoftwaredaten über den gesamten Dienst, um Kampagnen zu identifizieren. Administratoren können sie dann von Anfang bis Ende untersuchen, einschließlich Zielen, Auswirkungen und Flüssen, die auch in einer herunterladbaren Kampagne erstellt werden können.

6. **Mithilfe der Add-Ins "Nachricht** melden" können Benutzer zur weiteren Analyse einfach falsch positive Ergebnisse (gute E-Mails, fälschlicherweise als *"schlecht"* gekennzeichnet) oder falsch negative (als *"gute"* gekennzeichnete falsche E-Mails) an Microsoft melden.

7. **Tresor links for Office clients** offers the same Tresor Links time-of-click protection, natively, inside of Office clients like Word, PowerPoint, and Excel.

8. **Der Schutz für OneDrive, SharePoint und Teams** bietet den gleichen Tresor Anlagenschutz vor schädlichen Dateien, nativ, innerhalb von OneDrive, SharePoint und Microsoft Teams.

9. Wenn eine URL, die auf eine Datei verweist, nach der Zustellung ausgewählt ist, zeigt die **Detonation verknüpfter Inhalte** eine Warnseite an, bis die Sandkastenerstellung der Datei abgeschlossen ist und die URL als sicher eingestuft wird.

## <a name="the-filtering-stack-diagram"></a>Das Filterstapeldiagramm

Das endgültige Diagramm (wie alle Teile des Diagramms, das es zusammenstellen) *kann sich ändern, wenn das Produkt wächst und entwickelt* wird. Setzen Sie ein Lesezeichen auf diese Seite, und verwenden Sie die **Feedbackoption,** die Sie unten finden, wenn Sie nach Updates fragen müssen. Für Ihre Datensätze ist dies der Stapel mit allen Phasen in der folgenden Reihenfolge:

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="Alle Phasen der Filterung in Defender nach Office 365 in der Reihenfolge 1 bis 4.":::

## <a name="more-information"></a>Weitere Informationen

Müssen Sie Microsoft Defender für Office 365 ***jetzt** _einrichten? Verwenden Sie diesen Stapel, _now*, mit [diesem Schritt für Schritt,](protect-against-threats.md) um mit dem Schutz Ihrer Organisation zu beginnen.

*Besonderen Dank von MSFTTracyP und dem Docs-Schreibteam an Modaln Garr telemetr für diesen Inhalt.*
