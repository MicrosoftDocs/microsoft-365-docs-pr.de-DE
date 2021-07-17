---
title: Testen Sie Microsoft 365 Defender Vorfallreaktionsfunktionen in einer Pilotumgebung, um Vorfälle zu priorisieren und zu verwalten, eine automatisierte Untersuchung und Reaktion zu konfigurieren und die erweiterte Suche zu verwenden.
description: Testen Sie die Funktionen zur Reaktion auf Vorfälle in Microsoft 365 Defender, um Vorfälle zu priorisieren und zu verwalten, Untersuchungen zu automatisieren und die erweiterte Suche bei der Bedrohungserkennung zu verwenden.
keywords: Microsoft 365 Defender Testversion, testen Sie Microsoft 365 Defender, bewerten Sie Microsoft 365 Defender, Microsoft 365 Defender Evaluierungslabor, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c554f7bcedbdb64118639f5a455fd6f6e55daaa6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458113"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a>Testen Microsoft 365 Defender Vorfallreaktionsfunktionen in einer Pilotumgebung

**Gilt für:**
- Microsoft 365 Defender

Dieser Artikel ist [Schritt 2 von 2,](eval-defender-investigate-respond.md) um eine Untersuchung und Reaktion auf einen Vorfall in Microsoft 365 Defender mithilfe einer Pilotumgebung durchzuführen. Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-investigate-respond.md)

Nachdem Sie eine [Vorfallreaktion für einen simulierten Angriff](eval-defender-investigate-respond-simulate-attack.md)ausgeführt haben, können Sie hier einige Microsoft 365 Defender Funktionen erkunden:

|Funktion |Beschreibung |
|:-------|:-----|
| [Priorisieren von Vorfällen](#prioritize-incidents) | Verwenden Sie filtering and sorting of the incidents queue to determine which incidents to address next. |
| [Verwalten von Vorfällen](#manage-incidents) | Ändern Sie Vorfalleigenschaften, um die korrekte Zuweisung sicherzustellen, Tags und Kommentare hinzuzufügen und einen Vorfall zu beheben. |
| [Automatische Untersuchung und Reaktion](#examine-automated-investigation-and-response-with-the-action-center) | Air-Funktionen (Automated Investigation and Response), die Ihrem Sicherheitsteam helfen können, Bedrohungen effizienter und effektiver zu bewältigen. Das Info-Center ist ein "einzelner Bereich" für Vorfall- und Warnungsaufgaben wie das Genehmigen ausstehender Abhilfemaßnahmen. |
| [Erweiterte Suche](#advanced-hunting) | Ein abfragebasiertes Tool zur Bedrohungssuche, mit dem Sie Ereignisse in Ihrem Netzwerk proaktiv untersuchen und Bedrohungsindikatoren und Entitäten suchen können. Sie verwenden auch die erweiterte Suche während der Untersuchung und Behebung eines Vorfalls. |
||||

## <a name="prioritize-incidents"></a>Priorisieren von Vorfällen

Sie gelangen in der Schnellstartleiste des Microsoft 365 Defender-Portals ( security.microsoft.com ) von **Vorfällen & Warnungen > Vorfällen** in die Vorfallswarteschlange.[](https://security.microsoft.com) Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Beispiel für die Vorfallwarteschlange":::

Der Abschnitt **"Letzte Vorfälle und Warnungen"** zeigt ein Diagramm der Anzahl der empfangenen Warnungen und vorfälle, die in den letzten 24 Stunden erstellt wurden.

Um die Liste der Vorfälle zu untersuchen und deren Wichtigkeit für die Zuweisung und Untersuchung zu priorisieren, können Sie: 

- Konfigurieren Sie anpassbare Spalten (wählen **Sie Spalten auswählen)** aus, um Einblicke in die verschiedenen Merkmale des Vorfalls oder der betroffenen Entitäten zu erhalten. Auf diese Weise können Sie eine fundierte Entscheidung hinsichtlich der Priorisierung von Vorfällen für die Analyse treffen.

- Verwenden Sie die Filterung, um sich auf ein bestimmtes Szenario oder eine bestimmte Bedrohung zu konzentrieren. Das Anwenden von Filtern auf die Vorfallswarteschlange kann helfen, zu bestimmen, welche Vorfälle sofortige Aufmerksamkeit erfordern. 

Wählen Sie in der Standardvorfallswarteschlange **Filter** aus, um einen **Filterbereich** anzuzeigen, aus dem Sie eine bestimmte Gruppe von Vorfällen angeben können. Hier ein Beispiel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Beispiel für den Filterbereich für die Vorfallwarteschlange":::

Weitere Informationen finden Sie unter [Priorisieren von Vorfällen.](incident-queue.md)

## <a name="manage-incidents"></a>Verwalten von Vorfällen

Sie können Vorfälle aus dem **Bereich "Vorfall verwalten"** für einen Vorfall verwalten. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Beispiel für den Bereich &quot;Vorfall verwalten&quot; eines Vorfalls":::

Sie können diesen Bereich über den Link **"Vorfall verwalten"** auf folgendem Link anzeigen:

- Eigenschaftenbereich eines Vorfalls in der Vorfallwarteschlange.
- **Zusammenfassungsseite** eines Vorfalls.

Hier sind die Möglichkeiten, wie Sie Ihre Vorfälle verwalten können:

- Bearbeiten des Vorfallnamens

  Ändern Sie den utomanisch zugewiesenen Namen basierend auf den bewährten Methoden Ihres Sicherheitsteams.
  
- Hinzufügen von Ereigniskategorien

  Fügen Sie Tags hinzu, die Ihr Sicherheitsteam zum Klassifizieren von Vorfällen verwendet, die später gefiltert werden können.
  
- Zuweisen des Vorfalls zu sich selbst

  Weisen Sie ihn Ihrem Benutzerkontonamen zu, der später gefiltert werden kann.
  
- Beheben eines Vorfalls

  Schließen Sie den Vorfall, nachdem er behoben wurde.
  
- Festlegen der Klassifizierung und Bestimmung

  Klassifizieren und wählen Sie den Bedrohungstyp aus, wenn Sie einen Vorfall beheben.
  
- Kommentare hinzufügen

  Verwenden Sie Kommentare für Fortschritt, Notizen oder andere Informationen, die auf den bewährten Methoden Ihres Sicherheitsteams basieren. Der vollständige Kommentarverlauf ist über die Option **"Kommentare und Verlauf"** auf der Detailseite eines Vorfalls verfügbar.

Weitere Informationen finden Sie unter [Verwalten von Vorfällen.](manage-incidents.md)

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a>Untersuchen der automatisierten Untersuchung und Reaktion mit dem Info-Center

Je nachdem, wie automatisierte Untersuchungs- und Reaktionsfunktionen für Ihre Organisation konfiguriert sind, werden Korrekturmaßnahmen automatisch oder nur nach Genehmigung durch Ihr Sicherheitsteam ausgeführt. Alle Aktionen, ob ausstehend oder abgeschlossen, werden im [Info-Center](m365d-action-center.md)aufgelistet, in dem ausstehende und abgeschlossene Korrekturaktionen für Ihre Geräte, E-Mails & Inhalte für die Zusammenarbeit und Identitäten an einem Ort aufgeführt sind.

Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Einheitliches Info-Center in Microsoft 365 Defender":::

Im Info-Center können Sie ausstehende Aktionen auswählen und diese dann im Flyoutbereich genehmigen oder ablehnen. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="Genehmigen oder Ablehnen einer Aktion":::

Genehmigen (oder ablehnen) Sie ausstehende Aktionen so bald wie möglich, damit Ihre automatisierten Untersuchungen zeitnah fortgesetzt und abgeschlossen werden können.

Weitere Informationen finden Sie im [Info-Center](m365d-action-center.md)für [automatisierte Untersuchung und Reaktion.](m365d-autoir.md)

## <a name="advanced-hunting"></a>Erweiterte Bedrohungssuche

> [!NOTE]
> Bevor wir Sie durch die Simulation der erweiterten Suche führen, sehen Sie sich das folgende Video an, um erweiterte Suchkonzepte zu verstehen, zu sehen, wo Sie sie im Portal finden und wissen, wie sie Ihnen bei Ihren Sicherheitsvorgängen helfen kann.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


Wenn es sich bei der [optionalen dateilosen PowerShell-Angriffssimulation](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) um einen echten Angriff handelte, der bereits die Anmeldeinformationszugriffsphase erreicht hat, können Sie die erweiterte Suche jederzeit in der Untersuchung verwenden, um proaktiv Ereignisse und Datensätze im Netzwerk mithilfe der Informationen zu durchsuchen, die Sie bereits aus den generierten Warnungen und betroffenen Entitäten kennen. Sie können beispielsweise in den letzten 30 Tagen alle Verbindungen mit der externen IP-Adresse abfragen.

### <a name="hunting-environment-requirements"></a>Anforderungen an die Umgebungssuche

Für diese Simulation ist ein einzelnes internes Postfach und Gerät erforderlich. Sie benötigen auch ein externes E-Mail-Konto, um die Testnachricht zu senden.

1. Stellen Sie sicher, dass Ihr Mandant [Microsoft 365 Defender aktiviert](m365d-enable.md#confirm-that-the-service-is-on)hat.
2. Identifizieren Sie ein Zielpostfach, das für den Empfang von E-Mails verwendet werden soll.

   - Dieses Postfach muss von Microsoft Defender auf Office 365 überwacht werden.

   - Das Gerät aus Anforderung 3 muss auf dieses Postfach zugreifen.

3. Konfigurieren eines Testgeräts:

    a. Stellen Sie sicher, dass Sie Windows 10 Version 1903 oder höher verwenden.

    b. Verknüpfen Sie das Testgerät mit der Testdomäne.

    c. [Aktivieren Sie Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Wenn Sie Probleme beim Aktivieren von Windows Defender Antivirus haben, lesen Sie [dieses Problembehandlungsthema.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)

    d. [Onboarding in Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="run-the-simulation"></a>Ausführen der Simulation

1. Senden Sie von einem externen E-Mail-Konto aus eine E-Mail an das Postfach, das in Schritt 2 des Abschnitts mit den Anforderungen für die Suchumgebung identifiziert wurde. Fügen Sie eine Anlage hinzu, die über alle vorhandenen E-Mail-Filterrichtlinien zulässig ist. Diese Datei muss nicht bösartig oder eine ausführbare Datei sein. Vorgeschlagene Dateitypen sind <i>.pdf, </i> <i>.exe</i> (sofern zulässig) oder ein Office Dokumenttyp, z. B. eine Word-Datei.

2. Öffnen Sie die gesendete E-Mail von dem Gerät, das gemäß der Definition in Schritt 3 des Abschnitts mit den Anforderungen an die Umgebung für die Suche konfiguriert ist. Öffnen Sie die Anlage, oder speichern Sie die Datei auf dem Gerät.

#### <a name="go-hunting"></a>Suche gehen

1. Öffnen Sie das [Microsoft 365 Defender Portal.](https://security.microsoft.com/)

2. Wählen Sie im Navigationsbereich **"Suche > Erweiterte Suche"** aus.

3. Erstellen Sie eine Abfrage, die mit dem Sammeln von E-Mail-Ereignissen beginnt.

   1. Select **Query > New**.

   1. Doppelklicken Sie in den **E-Mail-Gruppen** unter **"Erweiterte Suche"** auf **"EmailEvents".** Dies sollte im Abfragefenster angezeigt werden.

      ```console
      EmailEvents
      ```

   1. Ändern Sie den Zeitrahmen der Abfrage in die letzten 24 Stunden. Angenommen, die E-Mail, die Sie beim Ausführen der oben genannten Simulation gesendet haben, lag in den letzten 24 Stunden, andernfalls ändern Sie den Zeitrahmen nach Bedarf.

   1. Wählen Sie **Abfrage ausführen** aus. Je nach Pilotumgebung haben Sie möglicherweise unterschiedliche Ergebnisse.

      > [!NOTE]
      > Weitere Informationen zum Filtern von Optionen zum Einschränken der Datenrückgabe finden Sie im nächsten Schritt.

      ![Beispiel für die Abfrageergebnisse der erweiterten Suche](../../media/mtp/fig19.png)

        > [!NOTE]
        > Bei der erweiterten Suche werden Abfrageergebnisse als tabellarische Daten angezeigt. Sie können die Daten auch in anderen Formattypen wie Diagrammen anzeigen.

   1. Sehen Sie sich die Ergebnisse an, und überprüfen Sie, ob Sie die geöffnete E-Mail identifizieren können. Es kann bis zu zwei Stunden dauern, bis die Nachricht in der erweiterten Suche angezeigt wird. Um die Ergebnisse einzugrenzen, können Sie der Abfrage die Bedingung hinzufügen, **dass** nur nach E-Mails mit "yahoo.com" als SenderMailFromDomain gesucht wird. Hier ein Beispiel.

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. Klicken Sie auf die resultierenden Zeilen aus der Abfrage, damit Sie den Datensatz überprüfen können.

      ![Beispiel für den Seitenbereich "Datensatz untersuchen", der geöffnet wird, wenn ein Erweitertes Suchergebnis ausgewählt wird](../../media/mtp/fig21.png)

4. Nachdem Sie sich vergewissert haben, dass die E-Mail angezeigt wird, fügen Sie einen Filter für die Anlagen hinzu. Konzentrieren Sie sich auf alle E-Mails mit Anlagen in der Umgebung. Konzentrieren Sie sich für diese Simulation auf eingehende E-Mails, nicht auf E-Mails, die aus Ihrer Umgebung gesendet werden. Entfernen Sie alle Filter, die Sie hinzugefügt haben, um Ihre Nachricht zu suchen und "| wobei **AttachmentCount > 0** und **EmailDirection**  ==  **"Eingehend"**

   In der folgenden Abfrage wird das Ergebnis mit einer kürzeren Liste angezeigt als die ursprüngliche Abfrage für alle E-Mail-Ereignisse:

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. Fügen Sie als Nächstes die Informationen zur Anlage (z. B. Dateiname, Hashes) in das Resultset ein. Fügen Sie dazu der **Tabelle EmailAttachmentInfo** bei. Die allgemeinen Felder, die für die Verknüpfung verwendet werden sollen, in diesem Fall sind **NetworkMessageId** und **RecipientObjectId**.

   Die folgende Abfrage enthält auch eine zusätzliche Zeile "| **project-rename EmailTimestamp=Timestamp**" that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. Verwenden Sie als Nächstes den **SHA256-Wert** aus der **EmailAttachmentInfo-Tabelle,** um **DeviceFileEvents** (Dateiaktionen, die auf dem Endpunkt aufgetreten sind) für diesen Hash zu suchen. Das allgemeine Feld hier ist der SHA256-Hash für die Anlage.

   Die resultierende Tabelle enthält nun Details vom Endpunkt (Microsoft Defender für Endpunkt), z. B. den Gerätenamen, welche Aktion ausgeführt wurde (in diesem Fall gefiltert, um nur FileCreated-Ereignisse einzuschließen), und wo die Datei gespeichert wurde. Der dem Prozess zugeordnete Kontoname wird ebenfalls eingeschlossen.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   Sie haben nun eine Abfrage erstellt, die alle eingehenden E-Mails identifiziert, in denen der Benutzer die Anlage geöffnet oder gespeichert hat. Sie können diese Abfrage auch verfeinern, um nach bestimmten Absenderdomänen, Dateigrößen, Dateitypen usw. zu filtern.

7. Funktionen sind eine besondere Art von Verknüpfung, mit der Sie mehr TI-Daten zu einer Datei wie Verbreitung, Signaturgeber- und Ausstellerinformationen usw. abrufen können. Um weitere Details zur Datei zu erhalten, verwenden Sie die **FileProfile()-Funktionserweiterung:**

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

Nachdem Sie eine Abfrage erstellt haben, die Informationen identifiziert, über die Sie **benachrichtigt werden** möchten, ob sie in der Zukunft auftreten, können Sie eine benutzerdefinierte Erkennung aus der Abfrage erstellen.

Benutzerdefinierte Erkennungen führen die Abfrage entsprechend der von Ihnen festgelegten Häufigkeit aus, und die Ergebnisse der Abfragen erstellen Sicherheitswarnungen, basierend auf den betroffenen Ressourcen, die Sie auswählen. Diese Warnungen werden mit Vorfällen korreliert und können als jede andere Sicherheitswarnung, die von einem der Produkte generiert wird, triagediert werden.

1. Entfernen Sie auf der Abfrageseite die Zeilen 7 und 8, die in Schritt 7 der Go-Suchanweisungen hinzugefügt wurden, und klicken Sie auf **Erkennungsregel erstellen.**

   ![Beispiel dafür, wo Sie auf der Seite "Erweiterte Suche" auf "Erkennungsregel erstellen" klicken können](../../media/mtp/fig22.png)

   > [!NOTE]
   > Wenn Sie auf **"Erkennungsregel erstellen"** klicken und in Ihrer Abfrage Syntaxfehler vorhanden sind, wird die Erkennungsregel nicht gespeichert. Überprüfen Sie Ihre Abfrage, um sicherzustellen, dass keine Fehler vorhanden sind.

2. Füllen Sie die erforderlichen Felder mit den Informationen aus, die es dem Sicherheitsteam ermöglichen, die Warnung zu verstehen, warum sie generiert wurde und welche Aktionen sie erwarten.

   ![Beispiel für die Seite "Erkennungsregel erstellen", auf der Sie die Warnungsdetails definieren können](../../media/mtp/fig23.png)

   Stellen Sie sicher, dass Sie die Felder mit Klarheit ausfüllen, um dem nächsten Benutzer eine fundierte Entscheidung über diese Warnung zur Erkennungsregel zu geben.

3. Wählen Sie aus, welche Entitäten in dieser Warnung betroffen sind. Wählen Sie in diesem Fall **"Gerät** und **Postfach"** aus.

   ![Beispiel für die Seite "Erkennungsregel erstellen", auf der Sie die Parameter der betroffenen Entitäten auswählen können](../../media/mtp/fig24.png)

4. Bestimmen Sie, welche Aktionen ausgeführt werden sollen, wenn die Warnung ausgelöst wird. Führen Sie in diesem Fall eine Antivirenüberprüfung aus, obwohl andere Aktionen ausgeführt werden konnten.

   ![Beispiel für die Seite "Erkennungsregel erstellen", auf der Sie eine Antivirenüberprüfung ausführen können, wenn eine Warnung ausgelöst wird, um Bedrohungen zu begegnen](../../media/mtp/fig25.png)

5. Wählen Sie den Bereich für die Warnungsregel aus. Da diese Abfrage Geräte umfasst, sind die Gerätegruppen in dieser benutzerdefinierten Erkennung gemäß dem Kontext von Microsoft Defender für Endpunkt relevant. Beim Erstellen einer benutzerdefinierten Erkennung, die keine Geräte als betroffene Entitäten enthält, gilt der Bereich nicht.

   ![Beispiel für die Seite "Erkennungsregel erstellen", auf der Sie den Bereich für die Warnungsregel festlegen können, verwaltet Ihre Erwartungen an die Ergebnisse, die Angezeigt werden.](../../media/mtp/fig26.png)

   Bei diesem Pilotprojekt sollten Sie diese Regel auf eine Teilmenge der Testgeräte in Ihrer Produktionsumgebung beschränken.

6. Wählen Sie **Erstellen** aus. Wählen Sie dann im Navigationsbereich **benutzerdefinierte Erkennungsregeln** aus.

   ![Beispiel für die Option "Benutzerdefinierte Erkennungsregeln" im Menü](../../media/mtp/fig27a.png)

   ![Beispiel für die Seite "Erkennungsregeln", auf der die Regel- und Ausführungsdetails angezeigt werden](../../media/mtp/fig27b.png)

   Auf dieser Seite können Sie die Erkennungsregel auswählen, die eine Detailseite öffnet.

   ![Beispiel für die Seite "E-Mail-Anlagen", auf der Sie den Status der Regelausführung, ausgelöste Warnungen und Aktionen, die Erkennung bearbeiten usw.](../../media/mtp/fig28.png)

<!--

### Advanced hunting walk-through exercises

To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities, and create custom detections and remediation actions.

> [!NOTE]
> Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.

|Title|Description|Download MP4|Watch on YouTube|CSL file to use|
|---|---|---|---|---|
|Episode 1: KQL fundamentals|We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender. Learn about available advanced hunting data and basic KQL syntax and operators.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Episode 1: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Episode 2: Joins|We'll continue learning about data in advanced hunting and how to join tables together. Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Episode 2: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Episode 3: Summarizing, pivoting, and visualizing data|Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing. In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema. We turn our datasets into charts that can help improve analysis.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Episode 3: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Episode 4: Let's hunt! Applying KQL to incident tracking|Time to track some attacker activity! In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack. Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episode 4: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

--> 

### <a name="expert-training-on-advanced-hunting"></a>Expertenschulung zur erweiterten Suche

**Das Nachverfolgen des Angreifers** ist eine Webcast-Serie für neue Sicherheitsanalysten und erfahrene Bedrohungsexperten. Es führt Sie durch die Grundlagen der erweiterten Suche bis hin zum Erstellen Eigener anspruchsvoller Abfragen. 

Informationen zu den ersten Schritten finden Sie unter ["Expertenschulungen](advanced-hunting-expert-training.md) zur erweiterten Suche".

### <a name="navigation-you-may-need"></a>Navigation, die Sie möglicherweise benötigen

[Erstellen der Microsoft 365 Defender-Evaluierungsumgebung](eval-create-eval-environment.md)
