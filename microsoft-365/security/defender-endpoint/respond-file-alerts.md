---
title: Ausführen von Reaktionsaktionen für eine Datei in Microsoft Defender for Endpoint
description: Ergreifen Sie Reaktionsaktionen für dateibezogene Warnungen, indem Sie eine Datei beenden und quarantinieren oder eine Datei blockieren und Aktivitätsdetails überprüfen.
keywords: Reagieren, Beenden und Isolieren, Datei blockieren, tiefe Analyse
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ba48adcf93c5b768b2280729b33a1a7d361919cb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066192"
---
# <a name="take-response-actions-on-a-file"></a>Ergreifen von Reaktionen auf eine Datei

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-responddile-abovefoldlink)

Reagieren Sie schnell auf erkannte Angriffe, indem Sie Dateien beenden und quarantinieren oder eine Datei blockieren. Nach dem Ergreifen von Aktionen für Dateien können Sie die Aktivitätsdetails im Aktionscenter überprüfen.

Reaktionsaktionen sind auf der detaillierten Profilseite einer Datei verfügbar. Sobald Sie auf dieser Seite sind, können Sie zwischen den neuen und alten Seitenlayouts wechseln, indem Sie die neue **Dateiseite umschalten.** Der Rest dieses Artikels beschreibt das neuere Seitenlayout.

Reaktionsaktionen werden am oberen Rand der Dateiseite ausgeführt und umfassen Folgendes:

- Datei zum Beenden und Isolieren
- Add Indicator
- Datei herunterladen
- Wenden Sie sich an einen Bedrohungsexperten
- Info-Center

Sie können auch Dateien zur tiefen Analyse übermitteln, um die Datei in einem sicheren Cloud-Sandkasten ausführen zu können. Nach Abschluss der Analyse erhalten Sie einen detaillierten Bericht, der Informationen zum Verhalten der Datei enthält. Sie können Dateien zur tiefen Analyse übermitteln und vergangene Berichte lesen, indem Sie die Registerkarte **Tiefe Analyse** auswählen. Sie befindet sich unterhalb der Dateiinformationskarten.

Einige Aktionen erfordern bestimmte Berechtigungen. In der folgenden Tabelle wird beschrieben, welche Aktionen bestimmte Berechtigungen für portable ausführbare Dateien (PE) und Nicht-PE-Dateien ausführen können:

| Berechtigung             | PE-Dateien | Nicht-PE-Dateien |
| :--------------------- | :------: | :----------: |
| Anzeigen von Daten              |     X    |       X      |
| Warnungsuntersuchung   | &#x2611; |       X      |
| Grundlegende Liveantwort    |     X    |       X      |
| Erweiterte Liveantwort | &#x2611; |   &#x2611;   |

Weitere Informationen zu Rollen finden Sie unter Erstellen und Verwalten von [Rollen für die rollenbasierte Zugriffssteuerung](user-roles.md).

## <a name="stop-and-quarantine-files-in-your-network"></a>Dateien in Ihrem Netzwerk beenden und unter Quarantäne stellen

Sie können einen Angriff in Ihrer Organisation verhindern, indem Sie den bösartigen Prozess beenden und die Datei quarantinieren, in der sie beobachtet wurde.

> [!IMPORTANT]
> Sie können diese Aktion nur dann ergreifen, wenn:
>
> - Auf dem Gerät, auf dem Sie die Aktion ausführen, wird Windows 10 Version 1703 oder höher ausgeführt.
> - Die Datei gehört nicht zu vertrauenswürdigen Herausgebern von Drittanbietern oder nicht von Microsoft signiert
> - Microsoft Defender Antivirus muss mindestens im passiven Modus ausgeführt werden. Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Kompatibilität](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).

Die **Aktion Datei beenden und isolieren** umfasst das Beenden ausgeführter Prozesse, das Quarantinieren der Dateien und das Löschen von beständigen Daten wie Registrierungsschlüsseln.

Diese Aktion wird auf Geräten mit Windows 10 Version 1703 oder höher wirksam, auf denen die Datei in den letzten 30 Tagen beobachtet wurde.

> [!NOTE]
> Sie können die Datei jederzeit aus der Quarantäne wiederherstellen.

### <a name="stop-and-quarantine-files"></a>Beenden und Isolieren von Dateien

1. Wählen Sie die Datei aus, die Sie beenden und isolieren möchten. Sie können eine Datei aus einer der folgenden Ansichten auswählen oder das Feld Suchen verwenden:

   - **Warnungen** – Klicken Sie in der Artefaktzeitachse auf die entsprechenden Links in der Beschreibung oder den Details.
   - **Suchfeld** : Wählen **Sie im** Dropdownmenü Datei aus, und geben Sie den Dateinamen ein.

   > [!NOTE]
   > Die Aktion "Beenden und Isolieren" ist auf maximal 1.000 Geräte beschränkt. Informationen zum Beenden einer Datei auf einer größeren Anzahl von Geräten finden Sie unter [Add indicator to block or allow file](#add-indicator-to-block-or-allow-a-file).

2. Wechseln Sie zur oberen Leiste, und wählen **Sie Stop and Quarantine File aus.**

   ![Abbildung der Aktion zum Beenden und Isolieren von Dateien](images/atp-stop-quarantine-file.png)

3. Geben Sie einen Grund an, und wählen Sie **dann Bestätigen aus.**

   ![Abbildung des modalen Fensters für Stopp- und Quarantänedatei](images/atp-stop-quarantine.png)

   Das Aktionscenter zeigt die Übermittlungsinformationen an:
   
   ![Abbildung des Aktionscenters für Stop- und Quarantänedatei](images/atp-stopnquarantine-file.png)

   - **Übermittlungszeit** – Zeigt an, wann die Aktion übermittelt wurde.
   - **Erfolg** – Zeigt die Anzahl der Geräte an, auf denen die Datei beendet und unter Quarantäne gestellt wurde.
   - **Fehler** – Zeigt die Anzahl der Geräte an, auf denen die Aktion fehlgeschlagen ist, und Details zu dem Fehler.
   - **Ausstehend** – Zeigt die Anzahl der Geräte an, auf denen die Datei noch beendet und unter Quarantäne gestellt werden muss. Dies kann für Fälle dauern, in denen das Gerät offline ist oder nicht mit dem Netzwerk verbunden ist.

4. Wählen Sie einen der Statusindikatoren aus, um weitere Informationen zur Aktion anzeigen zu können. Wählen Sie beispielsweise **Fehler aus,** um zu sehen, wo die Aktion fehlgeschlagen ist.

**Benachrichtigung für Gerätebenutzer:**</br>
Wenn die Datei von einem Gerät entfernt wird, wird die folgende Benachrichtigung angezeigt:

![Abbildung der Benachrichtigung auf dem Gerätebenutzer](images/atp-notification-file.png)

Auf der Gerätezeitachse wird für jedes Gerät, auf dem eine Datei beendet und isoliert wurde, ein neues Ereignis hinzugefügt.

Es wird eine Warnung angezeigt, bevor die Aktion für Dateien implementiert wird, die in einer Organisation weit verbreitet sind. Es wird überprüft, ob der Vorgang beabsichtigt ist.

## <a name="restore-file-from-quarantine"></a>Datei aus der Quarantäne wiederherstellen

Sie können ein Rollback für eine Datei aus der Quarantäne erstellen und entfernen, wenn Sie nach einer Untersuchung festgestellt haben, dass sie sauber ist. Führen Sie auf jedem Gerät, auf dem die Datei isoliert wurde, den folgenden Befehl aus.

1. Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät:

   1. Wechseln Sie zu **Start**, und geben Sie _cmd_ ein.

   1. Klicken Sie mit der rechten Maustaste auf Eingabeaufforderung, und wählen **Sie Als Administrator ausführen aus.** 

2. Geben Sie den folgenden Befehl ein, und drücken Sie die **EINGABETASTE**:

   ```powershell
   “%ProgramFiles%\Windows Defender\MpCmdRun.exe” –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
   ```

> [!NOTE]
> In einigen Szenarien wird **ThreatName** möglicherweise als EUS:Win32/CustomEnterpriseBlock!cl angezeigt.
>
> Defender for Endpoint stellt alle benutzerdefinierten blockierten Dateien wieder in Quarantäne, die in den letzten 30 Tagen auf diesem Gerät isoliert wurden.

> [!IMPORTANT]
> Eine Datei, die als potenzielle Netzwerkbedrohung isoliert wurde, kann möglicherweise nicht wiederhergestellt werden. Wenn ein Benutzer versucht, die Datei nach der Quarantäne wiederherzustellen, ist der Zugriff auf diese Datei möglicherweise nicht möglich. Dies kann daran liegt, dass das System keine Netzwerkanmeldeinformationen mehr für den Zugriff auf die Datei hat. In der Regel ist dies das Ergebnis einer temporären Anmeldung bei einem System oder freigegebenen Ordner, und die Zugriffstoken sind abgelaufen.

## <a name="download-or-collect-file"></a>Datei herunterladen oder sammeln

Wenn **Sie Datei aus** den Antwortaktionen herunterladen auswählen, können Sie ein lokales, kennwortgeschütztes .zip, das Ihre Datei enthält. Es wird ein Flyout angezeigt, in dem Sie einen Grund für das Herunterladen der Datei aufzeichnen und ein Kennwort festlegen können.

Standardmäßig können Sie keine Dateien herunterladen, die sich in Quarantäne befinden.

![Abbildung der Downloaddateiaktion](images/atp-download-file-action.png)

### <a name="collect-files"></a>Sammeln von Dateien

Wenn eine Datei noch nicht von Microsoft Defender for Endpoint gespeichert ist, können Sie sie nicht herunterladen. Stattdessen wird die Schaltfläche **Datei** sammeln am gleichen Speicherort angezeigt. Wenn in den letzten 30 Tagen keine Datei in der Organisation angezeigt wurde, wird **die Datei Sammeln** deaktiviert.
> [!Important]
> Eine Datei, die als potenzielle Netzwerkbedrohung isoliert wurde, kann möglicherweise nicht wiederhergestellt werden. Wenn ein Benutzer versucht, die Datei nach der Quarantäne wiederherzustellen, ist der Zugriff auf diese Datei möglicherweise nicht möglich. Dies kann daran liegt, dass das System keine Netzwerkanmeldeinformationen mehr für den Zugriff auf die Datei hat. In der Regel ist dies das Ergebnis einer temporären Anmeldung bei einem System oder freigegebenen Ordner, und die Zugriffstoken sind abgelaufen.

## <a name="add-indicator-to-block-or-allow-a-file"></a>Hinzufügen eines Indikators zum Blockieren oder Zulassen einer Datei

Verhindern Sie die weitere Verbreitung eines Angriffs in Ihrer Organisation, indem Sie potenziell schädliche Dateien oder mutmaßliche Schadsoftware verbieten. Wenn Sie eine potenziell schädliche ausführbare Datei (PE) kennen, können Sie sie blockieren. Dieser Vorgang verhindert, dass er auf Geräten in Ihrer Organisation gelesen, geschrieben oder ausgeführt wird.

> [!IMPORTANT]
>
> - Dieses Feature ist verfügbar, wenn Ihre Organisation Microsoft Defender Antivirus und der von der Cloud zugestellte Schutz aktiviert ist. Weitere Informationen finden Sie unter [Manage cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).
>
> - Die Antischalwareclientversion muss 4.18.1901.x oder höher sein.
> - Dieses Feature soll verhindern, dass mutmaßliche Schadsoftware (oder potenziell schädliche Dateien) aus dem Web heruntergeladen werden. Es unterstützt derzeit portable ausführbare (PE)-Dateien, einschließlich.exe _und_ _.dll_ Dateien. Die Abdeckung wird im Laufe der Zeit erweitert.
> - Diese Reaktionsaktion ist für Geräte auf Windows 10 Version 1703 oder höher verfügbar.
> - Die Allow- oder Block-Funktion kann nicht für Dateien durchgeführt werden, wenn die Dateiklassifikation im Cache des Geräts vor der Aktion zulassen oder blockieren vorhanden ist.

> [!NOTE]
> Die PE-Datei muss in der Gerätezeitachse enthalten sein, damit Sie diese Aktion ergreifen können.
>
> Es kann einige Minuten Wartezeit zwischen dem Zeitpunkt der Aktion und der tatsächlichen Datei liegen, die blockiert wird.

### <a name="enable-the-block-file-feature"></a>Aktivieren des Blockdateifeatures

Um mit dem Blockieren von Dateien zu beginnen, müssen Sie zuerst das [ **Feature Blockieren**](advanced-features.md) oder Zulassen in der Einstellungen.
### <a name="allow-or-block-file"></a>Zulassen oder Blockieren von Dateien

Wenn Sie einen Indikatorhash für eine Datei hinzufügen, können Sie eine Warnung ausgelöst und die Datei blockieren, wenn ein Gerät in Ihrer Organisation versucht, sie zu ausführen.

Dateien, die automatisch von einem Indikator blockiert werden, werden nicht im Aktionscenter der Datei angezeigt, aber die Warnungen werden weiterhin in der Warnungswarteschlange angezeigt.

Weitere [Informationen zum Blockieren](manage-indicators.md) und Auslösen von Warnungen für Dateien finden Sie unter Verwalten von Indikatoren.

Um das Blockieren einer Datei zu beenden, entfernen Sie den Indikator. Sie können dies über die **Aktion Indikator** bearbeiten auf der Profilseite der Datei tun. Diese Aktion wird an derselben Position wie die Aktion **Indikator** hinzufügen angezeigt, bevor Sie den Indikator hinzugefügt haben.

Sie können Indikatoren auch auf der Seite **Einstellungen** unter **Regelindikatoren**  >  **bearbeiten.** Indikatoren werden in diesem Bereich nach dem Hash ihrer Datei aufgelistet.

## <a name="consult-a-threat-expert"></a>Wenden Sie sich an einen Bedrohungsexperten

Wenden Sie sich an einen Microsoft-Bedrohungsexperten, um weitere Einblicke auf ein potenziell gefährdetes Gerät oder bereits gefährdete Geräte zu erhalten. Microsoft-Bedrohungsexperten werden direkt innerhalb der Microsoft Defender Security Center für eine zeitnahe und genaue Antwort engagiert. Experten bieten Einblicke in ein potenziell gefährdetes Gerät und helfen Ihnen, komplexe Bedrohungen und gezielte Angriffsbenachrichtigungen zu verstehen. Sie können auch Informationen zu den Warnungen oder einem Bedrohungsintelligenzkontext bereitstellen, den Sie im Portaldashboard sehen.

Weitere Informationen finden Sie unter Consult [a Microsoft Threat Expert.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization)

## <a name="check-activity-details-in-action-center"></a>Überprüfen von Aktivitätsdetails im Aktionscenter

Das **Aktionscenter** enthält Informationen zu Aktionen, die auf einem Gerät oder einer Datei ergriffen wurden. Sie können die folgenden Details anzeigen:

- Sammlung von Untersuchungspaketen
- Antivirusscan
- App-Einschränkung
- Geräteisolation

Alle anderen zugehörigen Details werden ebenfalls angezeigt, z. B. Übermittlungsdatum/-uhrzeit, Übermitteln des Benutzers und ob die Aktion erfolgreich war oder fehlgeschlagen ist.

![Abbildung des Aktionscenters mit Informationen](images/action-center-details.png)

## <a name="deep-analysis"></a>Tiefe Analyse

Cybersicherheitsuntersuchungen werden in der Regel durch eine Warnung ausgelöst. Warnungen stehen im Zusammenhang mit einer oder mehreren beobachteten Dateien, die häufig neu oder unbekannt sind. Wenn Sie eine Datei auswählen, können Sie die Dateiansicht anzeigen, in der die Metadaten der Datei angezeigt werden. Zum Anreichern der Daten im Zusammenhang mit der Datei können Sie die Datei zur tiefen Analyse übermitteln.

Das Feature "Tiefe Analyse" führt eine Datei in einer sicheren, vollständig instrumentierten Cloudumgebung aus. Tiefe Analyseergebnisse zeigen die Aktivitäten der Datei, beobachtete Verhaltensweisen und zugehörige Artefakte, z. B. gelöschte Dateien, Registrierungsänderungen und die Kommunikation mit IPs.
Eine umfassende Analyse unterstützt derzeit eine umfassende Analyse von portablen ausführbaren Dateien (einschließlich.exe _und_ _.dll_ Dateien).

Die tiefe Analyse einer Datei dauert mehrere Minuten. Sobald die Dateianalyse abgeschlossen ist, wird die Registerkarte Tiefenanalyse aktualisiert, um eine Zusammenfassung sowie das Datum und die Uhrzeit der neuesten verfügbaren Ergebnisse anzeigen zu können.

Die Zusammenfassung der tiefen Analyse enthält eine Liste der beobachteten Verhaltensweisen, von denen einige auf böswillige Aktivitäten hinweisen können, sowie *Observables*, einschließlich kontaktierte IPs und Dateien, die auf dem Datenträger erstellt wurden. Wenn nichts gefunden wurde, wird in diesen Abschnitten eine kurze Meldung angezeigt.

Ergebnisse einer tiefen Analyse werden mit der Bedrohungsintelligenz abgestimmt, und alle Übereinstimmungen generieren entsprechende Warnungen.

Verwenden Sie das Deep Analysis-Feature, um die Details einer Datei zu untersuchen, in der Regel während einer Untersuchung einer Warnung oder aus einem anderen Grund, aus dem Sie schädliches Verhalten vermuten. Dieses Feature ist auf der Registerkarte **Tiefe Analyse** auf der Profilseite der Datei verfügbar.<br/>
<br/>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4aAYy?rel=0]

**Submit for deep analysis** is enabled when the file is available in the Defender for Endpoint backend sample collection, or if it was observed on a Windows 10 device that supports submiting to deep analysis.

> [!NOTE]
> Nur Dateien aus Windows 10 können automatisch erfasst werden.

Sie können auch ein Beispiel über das [Microsoft Security Center-Portal](https://www.microsoft.com/security/portal/submission/submit.aspx) übermitteln, wenn die Datei  nicht auf einem Windows 10-Gerät beobachtet wurde, und auf die Schaltfläche Übermitteln warten, bis die Schaltfläche "Tiefe Analyse" verfügbar ist.

> [!NOTE]
> Aufgrund von Back-End-Verarbeitungsflüssen im Microsoft Security Center Portal kann es bis zu 10 Minuten Wartezeit zwischen der Dateiübermittlung und der Verfügbarkeit des Features für die tiefe Analyse in Defender for Endpoint sein.

Wenn das Beispiel gesammelt wird, führt Defender for Endpoint die Datei in einer sicheren Umgebung aus. Anschließend wird ein detaillierter Bericht über beobachtete Verhaltensweisen und zugehörige Artefakte erstellt, z. B. auf Geräten abgelegte Dateien, Kommunikation mit IPs und Registrierungsänderungen.

### <a name="submit-files-for-deep-analysis"></a>Übermitteln von Dateien für eine tiefe Analyse

1. Wählen Sie die Datei aus, die Sie zur tiefen Analyse übermitteln möchten. Sie können eine Datei aus einer der folgenden Ansichten auswählen oder durchsuchen:

    - Warnungen – Wählen Sie die Dateilinks aus der **Beschreibung** oder **details** auf der Artefaktzeitachse aus.
    - **Geräteliste** – Wählen Sie die Dateilinks im Abschnitt **Beschreibung** oder **Details** im Abschnitt Gerät **in Organisation** aus.
    - Suchfeld : Wählen **Sie im** Dropdownmenü Datei aus, und geben Sie den Dateinamen ein.

2. Wählen Sie **auf der Registerkarte** Tiefe Analyse der Dateiansicht die Option Senden **aus.**

   ![Sie können nur PE-Dateien im Abschnitt "Dateidetails" übermitteln.](images/submit-file.png)

   > [!NOTE]
   > Es werden nur PE-Dateien unterstützt, _einschließlich.exe_ _und.dll_ Dateien.

Eine Statusleiste wird angezeigt und enthält Informationen zu den verschiedenen Phasen der Analyse. Anschließend können Sie den Bericht anzeigen, wenn die Analyse erfolgt ist.

> [!NOTE]
> Je nach Geräteverfügbarkeit kann die Zeit der Beispielsammlung variieren. Für die Beispielsammlung gibt es ein Timeout von 3 Stunden. Bei der Auflistung wird ein Fehler angezeigt, und der Vorgang wird abgebrochen, wenn zu diesem Zeitpunkt Windows 10 keine Geräteberichte verfügbar sind. Sie können Dateien erneut für eine tiefe Analyse übermitteln, um neue Daten für die Datei zu erhalten.

### <a name="view-deep-analysis-reports"></a>Anzeigen von detaillierten Analyseberichten

Sehen Sie sich den bereitgestellten ausführlichen Analysebericht an, um detailliertere Einblicke in die von Ihnen übermittelte Datei zu erhalten. Dieses Feature ist im Kontext der Dateiansicht verfügbar.

Sie können den umfassenden Bericht anzeigen, der Details zu den folgenden Abschnitten enthält:

- Behaviors
- Observables

Die bereitgestellten Details können Ihnen bei der Untersuchung helfen, ob Anzeichen für einen potenziellen Angriff vorhanden sind.

1. Wählen Sie die Datei aus, die Sie zur tiefen Analyse übermittelt haben.
2. Wählen Sie die **Registerkarte Tiefe Analyse** aus. Wenn frühere Berichte vor sind, wird die Berichtszusammenfassung auf dieser Registerkarte angezeigt.

    ![Der ausführliche Analysebericht enthält detaillierte Informationen über eine Reihe von Kategorien hinweg.](images/analysis-results-nothing500.png)

#### <a name="troubleshoot-deep-analysis"></a>Problembehandlung bei der tiefen Analyse

Wenn beim Versuch, eine Datei zu übermitteln, ein Problem besteht, führen Sie die folgenden Schritte zur Problembehandlung aus.

1. Stellen Sie sicher, dass es sich bei der datei um eine PE-Datei handelt. PE-Dateien verfügen _.exe_ oder _.dll_ (ausführbare Programme oder Anwendungen).
2. Stellen Sie sicher, dass der Dienst Zugriff auf die Datei hat, dass sie noch vorhanden ist und nicht beschädigt oder geändert wurde.
3. Warten Sie kurz, und versuchen Sie, die Datei erneut zu übermitteln. Die Warteschlange ist möglicherweise voll, oder es gab einen temporären Verbindungs- oder Kommunikationsfehler.
4. Wenn die Beispielsammlungsrichtlinie nicht konfiguriert ist, ist das Standardverhalten, die Beispielsammlung zu erlauben. Wenn sie konfiguriert ist, überprüfen Sie, ob die Richtlinieneinstellung eine Beispielsammlung zulässt, bevor Sie die Datei erneut übermitteln. Wenn die Beispielsammlung konfiguriert ist, überprüfen Sie den folgenden Registrierungswert:

    ```powershell
    Path: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
    Name: AllowSampleCollection
    Type: DWORD
    Hexadecimal value :
      Value = 0 – block sample collection
      Value = 1 – allow sample collection
    ```

1. Ändern Sie die Organisationseinheit über die Gruppenrichtlinie. Weitere Informationen finden Sie unter [Configure with Group Policy](configure-endpoints-gp.md).
1. Wenn das Problem durch diese Schritte nicht behoben werden kann, wenden Sie sich [an winatp@microsoft.com](mailto:winatp@microsoft.com).

## <a name="related-topics"></a>Verwandte Themen

- [Ergreifen von Reaktionen auf einem Gerät](respond-machine-alerts.md)
- [Untersuchen von Dateien](investigate-files.md)
