---
title: Angriffssimulator in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie mithilfe des Angriffssimulators simulierte Phishing- und Kennwortangriffe in ihren Microsoft 365 E5- oder Microsoft Defender für Office 365 Plan 2-Organisationen ausführen.
ms.openlocfilehash: 2ffec891f7b1021f3c6c51b003c78aacb0ec0d6a
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794532"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Angriffssimulator in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Wenn Ihre Organisation über Microsoft Defender für Office 365 Plan 2 verfügt, der Funktionen zur Bedrohungsuntersuchung und -reaktion [umfasst,](office-365-ti.md)können Sie den Angriffssimulator im Security & Compliance Center verwenden, um realistische Angriffsszenarien in Ihrer Organisation zu führen. Diese simulierten Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren und zu finden, bevor sich ein tatsächlicher Angriff auf Ihr Endergebnis ausdingt. Lesen Sie diesen Artikel, um mehr zu erfahren.

> [!NOTE]
> Angriffssimulations- und Schulungsdaten werden mit anderen Kundendaten für Microsoft 365-Dienste gespeichert. Weitere Informationen finden Sie unter [Microsoft 365-Datenspeicherorte.](/microsoft-365/enterprise/o365-data-locations)

> [!TIP]
> Das Training zur Angriffssimulation ist für die öffentliche Vorschau im Microsoft 365 Security Center verfügbar. Weitere Informationen finden Sie hier: Simulieren eines Phishingangriffs mit [Microsoft Defender für Office 365.](attack-simulation-training.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com/>. Der Angriffssimulator ist im **Angriffssimulator für die Bedrohungsverwaltung** \> **verfügbar.** Wechseln Sie direkt zum Angriffssimulator, öffnen Sie <https://protection.office.com/attacksimulator> .

- Weitere Informationen zur Verfügbarkeit des Angriffssimulators in verschiedenen Microsoft 365-Abonnements finden Sie in der [Microsoft Defender für Office 365-Dienstbeschreibung.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- Sie müssen Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein. Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Ihr Konto muss für die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) konfiguriert sein, um Kampagnen im Angriffssimulator zu erstellen und zu verwalten. Anweisungen finden Sie unter [Einrichten der mehrstufigen Authentifizierung.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)

- Phishingkampagnen sammeln und verarbeiten Ereignisse 30 Tage lang. Verlaufsdaten für Kampagnen sind nach dem Start der Kampagne bis zu 90 Tage lang verfügbar.

- Es gibt keine entsprechenden PowerShell-Cmdlets für den Angriffssimulator.

## <a name="spear-phishing-campaigns"></a>Phishingkampagnen mit Speerspitze

*Phishing* ist ein allgemeiner Begriff für E-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die von legitimen oder vertrauenswürdigen Absendern zu sein scheinen. *Bei Phishing* handelt es sich um einen gezielten Phishingangriff, bei dem fokussierte und angepasste Inhalte verwendet werden, die speziell auf die Zielempfänger zugeschnitten sind (in der Regel nach der Aufarbeitung der Empfänger durch den Angreifer).

Im Angriffssimulator sind zwei verschiedene Arten von Phishingkampagnen verfügbar:

- **Phishing mit Phishing (Anmeldeinformationen)**– Der Angriff versucht, die Empfänger zu überzeugen, auf eine URL in der Nachricht zu klicken. Wenn sie auf den Link klicken, werden sie aufgefordert, ihre Anmeldeinformationen ein eingeben. Wenn sie dies tun, werden sie an einen der folgenden Speicherorte weiterverortet:

  - Eine Standardseite, auf der erläutert wird, dass dies nur ein Test war, und enthält Tipps zum Erkennen von Phishingnachrichten.

    ![Was Benutzer sehen, wenn sie auf den Phishinglink klicken und ihre Anmeldeinformationen eingeben](../../media/attack-simulator-phishing-result.png)

  - Eine benutzerdefinierte Seite (URL), die Sie angeben.

- **Speerphishing (Anlage):** Der Angriff versucht, die Empfänger zu überzeugen, eine DOCX- oder PDF-Anlage in der Nachricht zu öffnen. Die Anlage enthält den gleichen Inhalt des standardmäßigen Phishinglinks, aber der erste Satz beginnt mit " , Sie sehen diese Nachricht als kürzlich geöffnete E-Mail-Nachricht...". \<Display Name\>

> [!NOTE]
> Derzeit laufen Phishingkampagnen im Angriffssimulator nicht ab.

### <a name="create-a-spear-phishing-campaign"></a>Erstellen einer Phishingkampagne mit Phishing

Ein wichtiger Bestandteil jeder Phishingkampagne ist das Aussehen und Gefühl der E-Mail-Nachricht, die an die Zielempfänger gesendet wird. Zum Erstellen und Konfigurieren der E-Mail-Nachricht stehen Ihnen die folgenden Optionen zur Verfügung:

- **Verwenden Sie eine integrierte E-Mail-Vorlage:** Es stehen zwei integrierte Vorlagen zur Verfügung: **"Giveaway"** und **"Payroll Update".** Sie können einige, alle oder keine der E-Mail-Eigenschaften aus der Vorlage weiter anpassen, wenn Sie die Kampagne erstellen und starten.

- **Erstellen Sie eine wiederverwendbare** E-Mail-Vorlage: Nachdem Sie die E-Mail-Vorlage erstellt und gespeichert haben, können Sie sie in zukünftigen Phishingkampagnen erneut verwenden. Sie können einige, alle oder keine der E-Mail-Eigenschaften aus der Vorlage weiter anpassen, wenn Sie die Kampagne erstellen und starten.

- **Erstellen Sie die E-Mail-Nachricht im** Assistenten: Sie können die E-Mail-Nachricht direkt im Assistenten erstellen, während Sie die Phishingkampagne für Die Speerspitze erstellen und starten.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Schritt 1 (Optional): Erstellen einer benutzerdefinierten E-Mail-Vorlage

Wenn Sie eine der integrierten Vorlagen verwenden oder die E-Mail-Nachricht direkt im Assistenten erstellen möchten, können Sie diesen Schritt überspringen.

1. Wechseln Sie im Security & Compliance  Center zum Angriffssimulator für die \> **Bedrohungsverwaltung.**

2. Klicken Sie **auf der Seite** "Simulierte Angriffe" in den Abschnitten "Phishing mit Anmeldeinformationen" oder **"Phishing(Anlage)"** auf **"Angriffsdetails".** 

   Es spielt keine Rolle, wo Sie die Vorlage erstellen. Die verfügbaren Optionen in der Vorlage sind für beide Arten von Phishingangriffen identisch.

3. Klicken Sie **auf der Seite "Angriffsdetails",** die geöffnet wird, im Abschnitt **"Phishingvorlagen"** im Bereich "Vorlagen erstellen" auf **"Neue Vorlage".** 

4. Der **Assistent zum Konfigurieren von Phishingvorlagen** wird in einem neuen Flyout gestartet. Geben Sie **im Startschritt** einen eindeutigen Anzeigenamen für die Vorlage ein, und klicken Sie dann auf **"Weiter".**

5. Konfigurieren Sie **im Schritt "E-Mail-Details** konfigurieren" die folgenden Einstellungen:

   - **From (Name):** Der Anzeigename, der für den Absender der Nachricht verwendet wird.

   - **From (E-Mail):** Die E-Mail-Adresse des Absenders.

   - **Phishing-Anmeldeserver-URL:** Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus. Dies ist die URL, auf die Benutzer verlockend klicken. Sie können wie folgt vorgehen:

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > Ein URL-Reputationsdienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher. Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden.

   - **URL der benutzerdefinierten** Startseite: Geben Sie eine optionale Zielseite ein, auf der Benutzer weitergeleitet werden, wenn sie auf den Phishinglink klicken und ihre Anmeldeinformationen eingeben. Dieser Link ersetzt die Standardmäßige Zielseite. Wenn Sie beispielsweise eine interne Bewusstseinsschulung haben, können Sie diese URL hier angeben.

   - **Kategorie**: Derzeit wird diese Einstellung nicht verwendet (alles, was Sie eingeben, wird ignoriert).

   - **Betreff:** Das **Feld "Betreff"** der E-Mail-Nachricht.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

6. Erstellen Sie **im Schritt zum** Verfassen einer E-Mail den Nachrichtentext der E-Mail-Nachricht. Sie können die Registerkarte **"E-Mail"** (ein Rich-HTML-Editor) oder die Registerkarte **"Quelle"** (unformatiertes HTML-Code) verwenden.

   Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen. Sie können Bilder und Text einfügen, um die Gfähigkeit der Nachricht im E-Mail-Client des Empfängers zu verbessern.

   - `${username}` fügt den Namen des Empfängers ein.

   - `${loginserverurl}` Fügt den Wert der **Phishing-Anmeldeserver-URL** aus dem vorherigen Schritt ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

7. Klicken Sie **im Schritt "Bestätigen"** auf **"Fertig stellen".**

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Schritt 2: Erstellen und Starten der Phishingkampagne

1. Wechseln Sie im Security & Compliance  Center zum Angriffssimulator für die \> **Bedrohungsverwaltung.**

2. Treffen Sie **auf** der Seite "Angriffe simulieren" eine der folgenden Optionen basierend auf dem Typ der Kampagne, die Sie erstellen möchten:

   - Klicken Sie **im Abschnitt "Phishing mit Phishing (Credentials Harvest)"** auf **"Angriff** starten" oder **"Angriffsdetails** \> **Starten".**

   - Klicken Sie **im Abschnitt "Phishing(Anlage)"** auf **"Angriff** starten" oder auf **"Angriffsdetails** \> **Starten".**

3. Der **Assistent zum Konfigurieren von Phishingangriffen** wird in einem neuen Flyout gestartet. Gehen Sie **im Startschritt** wie folgt vor:

   - Geben Sie **in das Feld "Name"** einen eindeutigen Anzeigenamen für die Kampagne ein. Klicken Sie nicht auf Vorlage **verwenden,** da Sie die E-Mail-Nachricht später im Assistenten erstellen.

   - Klicken **Sie auf Vorlage verwenden,** und wählen Sie eine integrierte oder benutzerdefinierte E-Mail-Vorlage aus. Nachdem Sie die Vorlage ausgewählt haben, wird das Feld **"Name"** automatisch basierend auf der Vorlage ausgefüllt, Aber Sie können den Namen ändern.

   ![Phishingstartseite](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Gehen Sie **im Schritt "Zielempfänger"** wie folgt vor:

   - Klicken **Sie auf "Adressbuch",** um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen. Jeder Zielempfänger muss über ein Exchange Online-Postfach verfügen. Wenn Sie auf **"Filtern"** und **"Anwenden"** klicken, ohne ein Suchkriterium ein eingeben zu müssen, werden alle Empfänger zurückgegeben und der Kampagne hinzugefügt.

   - Klicken **Sie auf "Importieren"** und dann **auf "Datei importieren",** um einen durch Kommas getrennten Wert (CSV) oder eine durch Zeilen getrennte Datei mit E-Mail-Adressen zu importieren. Jede Zeile muss die E-Mail-Adresse des Empfängers enthalten.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Konfigurieren Sie **im Schritt "E-Mail-Details** konfigurieren" die folgenden Einstellungen:

   Wenn Sie im Startschritt eine Vorlage ausgewählt haben, sind die meisten dieser Werte bereits konfiguriert, sie können jedoch geändert werden. 

   - **From (Name):** Der Anzeigename, der für den Absender der Nachricht verwendet wird.

   - **From (E-Mail):** Die E-Mail-Adresse des Absenders. Sie können eine echte oder gefälschte E-Mail-Adresse aus der E-Mail-Domäne Ihrer Organisation oder eine echte oder gefälschte externe E-Mail-Adresse eingeben. Eine gültige Absender-E-Mail-Adresse aus Ihrer Organisation wird tatsächlich im E-Mail-Client des Empfängers aufgelöst.

   - **Phishing-Anmeldeserver-URL:** Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus. Dies ist die URL, auf die Benutzer verlockend klicken. Sie können wie folgt vorgehen:

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - Alle URLs sind absichtlich http, nicht https.
     >
     > - Ein URL-Reputationsdienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher. Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden.
     >
     > - Sie müssen eine URL auswählen. Bei **Einer Phishingkampagne (Anlage)** können Sie den Link im nächsten Schritt aus dem Nachrichtentext entfernen  (andernfalls enthält die Nachricht sowohl einen Link als auch eine Anlage).

   - **Anlagentyp:** Diese Einstellung ist nur in **Phishingkampagnen (Anlagen)** verfügbar. Klicken Sie auf die Dropdownliste, und wählen Sie **. DOCX oder** **. PDF** aus der Liste.

   - **Anlagenname:** Diese Einstellung ist nur in **Phishingkampagnen (Anlagen)** verfügbar. Geben Sie einen Dateinamen für die DOCX- oder PDF-Anlage ein.

   - **URL der benutzerdefinierten** Startseite: Geben Sie eine optionale Zielseite ein, auf der Benutzer weitergeleitet werden, wenn sie auf den Phishinglink klicken und ihre Anmeldeinformationen eingeben. Dieser Link ersetzt die Standardmäßige Zielseite. Wenn Sie beispielsweise eine interne Bewusstseinsschulung haben, können Sie diese URL hier angeben.

   - **Betreff:** Das **Feld "Betreff"** der E-Mail-Nachricht.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

6. Erstellen Sie **im Schritt zum** Verfassen einer E-Mail den Nachrichtentext der E-Mail-Nachricht. Wenn Sie im Startschritt eine Vorlage ausgewählt haben, ist der Nachrichtentext bereits konfiguriert, Sie können ihn jedoch anpassen.  Sie können die Registerkarte **"E-Mail"** (ein Rich-HTML-Editor) oder die Registerkarte **"Quelle"** (unformatiertes HTML-Code) verwenden.

   Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen. Sie können Bilder und Text einfügen, um die Gfähigkeit der Nachricht im E-Mail-Client des Empfängers zu verbessern.

   - `${username}` fügt den Namen des Empfängers ein.

   - `${loginserverurl}` Fügt den Wert der **Phishing-Anmeldeserver-URL** ein.

   Für Kampagnen mit **Phishing (Anlage)** sollten Sie den Link aus dem Nachrichtentext entfernen (andernfalls enthält die Nachricht sowohl einen Link als auch eine Anlage, und Linkklicks werden in einer Anlagenkampagne nicht nachverfolgt). 

   ![Verfassen des E-Mail-Textkörpers](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

7. Klicken Sie **im Schritt "Bestätigen"** auf **"Fertig** stellen", um die Kampagne zu starten. Die Phishingnachricht wird an die Zielempfänger zugestellt.

## <a name="password-attack-campaigns"></a>Kennwortangriffskampagnen

Ein *Kennwortangriff versucht,* Kennwörter für Benutzerkonten in einer Organisation zu erraten, in der Regel, nachdem der Angreifer mindestens ein gültiges Benutzerkonto identifiziert hat.

Im Angriffssimulator stehen Ihnen zwei verschiedene Arten von Kennwortangriffskampagnen zur Verfügung, um die Komplexität der Kennwörter Ihrer Benutzer zu testen:

- **Brute-Force-Kennwort (Wörterbuchangriff):** Ein  *Brute-Force-* oder Wörterbuchangriff verwendet eine große Wörterbuchdatei mit Kennwörtern für ein Benutzerkonto mit der Hoffen, dass eines davon funktioniert (viele Kennwörter für ein Konto). Falsche Kennwortsperrungen helfen, Brute-Force-Kennwortangriffe zu verhindern.

  Für den Wörterbuchangriff können Sie ein oder mehrere Kennwörter angeben, die Sie ausprobieren möchten (manuell eingegeben oder in eine hochgeladene Datei), und Sie können einen oder mehrere Benutzer angeben.

- **Kennwort-Spray-Angriff:** Ein *Kennwort-Spray-Angriff* verwendet dasselbe sorgfältig überlegte Kennwort für eine Liste von Benutzerkonten (ein Kennwort für viele Konten). Kennwort-Spray-Angriffe sind schwieriger zu erkennen als Brute-Force-Kennwortangriffe (die Erfolgswahrscheinlichkeit steigt, wenn ein Angreifer ein Kennwort über Dutzende oder Hunderte von Konten versucht, ohne das Risiko zu riskieren, dass das falsche Kennwort gesperrt wird).

  Für den Kennwort-Spray-Angriff können Sie nur ein Kennwort angeben, das Sie testen möchten, und Sie können einen oder mehrere Benutzer angeben.

> [!NOTE]
> Die Kennwortangriffe im Angriffssimulator übergeben benutzernamen- und kennwortbasierte Authentifizierungsanforderungen an einen Endpunkt, damit sie auch mit anderen Authentifizierungsmethoden (AD FS, Kennworthashsynchronisierung, Pass-Through, PingFederate usw.) funktionieren. Für Benutzer, für die MFA aktiviert ist, wird der Versuch auch dann, wenn der Kennwortangriff sein **tatsächliches** Kennwort versucht, immer als Fehler registriert (mit anderen Worten, MFA-Benutzer werden nie in der Anzahl der erfolgreichen Versuche der Kampagne angezeigt). Dies ist das erwartete Ergebnis. MFA ist eine primäre Methode zum Schutz vor Kennwortangriffen.

### <a name="create-and-launch-a-password-attack-campaign"></a>Erstellen und Starten einer Kennwortangriffskampagne

1. Wechseln Sie im Security & Compliance  Center zum Angriffssimulator für die \> **Bedrohungsverwaltung.**

2. Treffen Sie **auf** der Seite "Angriffe simulieren" eine der folgenden Optionen basierend auf dem Typ der Kampagne, die Sie erstellen möchten:

   - Klicken Sie **im Abschnitt "Brute Force Password (Dictionary Attack) "** auf **"Angriff** starten" oder auf **"Angriffsdetails** \> **Starten".**

   - Klicken Sie **im Abschnitt "Kennwort-Spray-Angriff"** auf **"Angriff starten"** oder auf **"Angriffsdetails** \> **Starten".**

3. Der **Assistent zum Konfigurieren von Kennwortangriffen** wird in einem neuen Flyout gestartet. Geben Sie **im Startschritt** einen eindeutigen Anzeigenamen für die Kampagne ein, und klicken Sie dann auf **"Weiter".**

4. Gehen Sie **im Schritt "Zielbenutzer"** wie folgt vor:

   - Klicken **Sie auf "Adressbuch",** um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen. Jeder Zielempfänger muss über ein Exchange Online-Postfach verfügen. Wenn Sie auf **"Filtern"** und **"Anwenden"** klicken, ohne ein Suchkriterium ein eingeben zu müssen, werden alle Empfänger zurückgegeben und der Kampagne hinzugefügt.

   - Klicken **Sie auf "Importieren"** und dann **auf "Datei importieren",** um einen durch Kommas getrennten Wert (CSV) oder eine durch Zeilen getrennte Datei mit E-Mail-Adressen zu importieren. Jede Zeile muss die E-Mail-Adresse des Empfängers enthalten.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Wählen Sie **im Schritt "Angriffseinstellungen** auswählen" die Aktion basierend auf dem Kampagnentyp aus:

   - **Brute Force Password (Dictionary Attack):** Gehen Sie wie folgt vor:

     - **Geben Sie Kennwörter manuell** ein: Geben Sie in **der** Eingabetaste ein Kennwortfeld ein, geben Sie ein Kennwort ein, und drücken Sie dann die EINGABETASTE. Wiederholen Sie diesen Schritt so oft wie nötig.

     - **Hochladen von Kennwörtern** aus einer Wörterbuchdatei: Klicken Sie auf **"Hochladen",** um eine vorhandene Textdatei zu importieren, die ein Kennwort in jeder Zeile und eine leere letzte Zeile enthält. Die Textdatei muss eine Größe von 10 MB oder weniger haben und darf nicht mehr als 30.000 Kennwörter enthalten.

   - **Kennwort-Spray-Angriff:** Geben Sie in den **Kennwörtern,** die im Angriffsfeld verwendet werden, ein Kennwort ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

6. Klicken Sie **im Schritt "Bestätigen"** auf **"Fertig** stellen", um die Kampagne zu starten. Die von Ihnen angegebenen Kennwörter werden für Benutzer ausprobiert, die Sie angegeben haben.

## <a name="view-campaign-results"></a>Anzeigen von Kampagnenergebnissen

Nachdem Sie eine Kampagne gestartet haben, können Sie den Fortschritt und die Ergebnisse auf der Hauptseite "Simulierte **Angriffe"** überprüfen.

Aktive Kampagnen zeigen eine Statusleiste, einen abgeschlossenen Prozentsatz und die Anzahl "(abgeschlossene Benutzer) (Gesamtbenutzer)" an. Durch Klicken **auf** die Schaltfläche "Aktualisieren" wird der Fortschritt aller aktiven Kampagnen aktualisiert. Sie können auch auf **"Beenden" klicken,** um eine aktive Kampagne zu beenden.

Wenn die Kampagne abgeschlossen ist, ändert sich der Status in **Angriff abgeschlossen**. Sie können die Ergebnisse der Kampagne anzeigen, indem Sie eine der folgenden Aktionen ausführen:

- Klicken Sie auf der Hauptseite **"Angriffe** **simulieren"** unter dem Namen der Kampagne auf "Bericht anzeigen".

- Klicken Sie **auf** der Hauptseite "Simulierte Angriffe" im Abschnitt auf **"Angriffsdetails"** für den Angriffstyp. Wählen Sie **auf der Seite "Angriffsdetails",** die geöffnet wird, die Kampagne im Abschnitt **"Angriffsverlauf"** aus.

Mit einer der vorherigen Aktionen gelangen Sie zu einer Seite mit dem Namen **"Angriffsdetails".** Die Informationen, die auf dieser Seite für jeden Kampagnentyp verfügbar sind, werden in den folgenden Abschnitten beschrieben.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Phishing (Credentials Harvest) – Kampagnenergebnisse

Die folgenden Informationen sind auf der Seite **"Angriffsdetails"** für jede Kampagne verfügbar:

- Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.

- **Gesamtzahl der benutzerorientierten Benutzer**

- **Erfolgreiche Versuche:** Die Anzahl der Benutzer,  die auf den Link geklickt und ihre Anmeldeinformationen eingegeben haben *(beliebiger* Benutzername und Kennwortwert).

- **Gesamterfolgsrate:** Ein Prozentsatz, der von erfolgreichen Versuchen berechnet  /  **wird. Zielbenutzer insgesamt.**

- **Schnellster Klick:** Wie lange es ge dauere, bis der erste Benutzer auf den Link geklickt hat, nachdem Sie die Kampagne gestartet haben.

- **Durchschnittlicher Klick:** Die Summe, wie lange es ge dauern hat, bis alle Benutzer auf den Link geklickt haben, dividiert durch die Anzahl der Benutzer, die auf den Link geklickt haben.

- **Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.

- **Schnellste Anmeldeinformationen:** Wie lange es ge dauern hat, bis der erste Benutzer seine Anmeldeinformationen eingegeben hat, nachdem Sie die Kampagne gestartet haben.

- **Durchschnittliche** Anmeldeinformationen: Die Summe der Zeit, die jeder für die Eingabe seiner Anmeldeinformationen brauchte, dividiert durch die Anzahl der Benutzer, die ihre Anmeldeinformationen eingegeben haben.

- **Erfolgsrate für Anmeldeinformationen:** Ein Prozentsatz, der von (Anzahl der Benutzer, die ihre Anmeldeinformationen eingegeben haben) / der Gesamtzahl der **benutzerorientierten Benutzer berechnet wird.**

- Ein Balkendiagramm, das zeigt, auf den **link geklickt** und **Anmeldeinformationen Zahlen** pro Tag angegeben.

- Ein Kreisdiagramm, das zeigt, auf den **Link geklickt** **wurde,** die angegebenen Anmeldeinformationen und die Prozentsätze **"Keine"** für die Kampagne.

- Im **Abschnitt "Gefährdete Benutzer"** werden die Details der Benutzer aufgeführt, die auf den Link geklickt haben:

  - Die E-Mail-Adresse des Benutzers

  - Datum/Uhrzeit, an dem/der auf den Link geklickt wurde.

  - Die Client-IP-Adresse.

  - Details zur Windows- und Webbrowserversion des Benutzers.

  Sie können auf **"Exportieren"** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.

### <a name="spear-phishing-attachment-campaign-results"></a>Kampagnenergebnisse für Das Phishing (Anlage)

Die folgenden Informationen sind auf der Seite **"Angriffsdetails"** für jede Kampagne verfügbar:

- Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.

- **Gesamtzahl der benutzerorientierten Benutzer**

- **Erfolgreiche Versuche:** Die Anzahl der Benutzer, die die Anlage geöffnet oder heruntergeladen und geöffnet haben (Die Vorschau zählt nicht).

- **Gesamterfolgsrate:** Ein Prozentsatz, der von erfolgreichen Versuchen berechnet  /  **wird. Zielbenutzer insgesamt.**

- **Schnellste Anlagenöffnzeit:** Wie lange das Öffnen der Anlage durch den ersten Benutzer nach dem Starten der Kampagne gezeit hat.

- **Durchschnittliche Anlageneröffnungszeit:** Die Summe der Zeit, in der alle Benutzer die Anlage geöffnet haben, dividiert durch die Anzahl der Benutzer, die die Anlage geöffnet haben.

- **Erfolgsrate für anlagenöffnend:** Ein Prozentsatz, der von (Anzahl der Benutzer, die die Anlage geöffnet haben) /Gesamtzahl der **benutzerorientierten berechnet wird.**

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Brute Force Password (Dictionary Attack)-Kampagnenergebnisse

Die folgenden Informationen sind auf der Seite **"Angriffsdetails"** für jede Kampagne verfügbar:

- Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.

- **Gesamtzahl der benutzerorientierten Benutzer**

- **Erfolgreiche Versuche:** Die Anzahl der Benutzer, die eines der angegebenen Kennwörter verwendet haben.

- **Gesamterfolgsrate:** Ein Prozentsatz, der von erfolgreichen Versuchen berechnet  /  **wird. Zielbenutzer insgesamt.**

- Im **Abschnitt "Gefährdete Benutzer"** werden die E-Mail-Adressen der betroffenen Benutzer aufgeführt. Sie können auf **"Exportieren"** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.

### <a name="password-spray-attack-campaign-results"></a>Ergebnisse der Kennwort-Spray-Angriffskampagne

Die folgenden Informationen sind auf der Seite **"Angriffsdetails"** für jede Kampagne verfügbar:

- Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.

- **Gesamtzahl der benutzerorientierten Benutzer**

- **Erfolgreiche Versuche:** Die Anzahl der Benutzer, die gefunden wurden, dass sie das angegebene Kennwort verwenden.

- **Gesamterfolgsrate:** Ein Prozentsatz, der von erfolgreichen Versuchen berechnet  /  **wird. Zielbenutzer insgesamt.**
