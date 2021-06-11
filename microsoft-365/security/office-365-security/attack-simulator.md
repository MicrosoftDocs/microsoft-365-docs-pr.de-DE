---
title: Angriffssimulator in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
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
description: Administratoren können erfahren, wie Sie den Angriffssimulator verwenden, um simulierte Phishing- und Kennwortangriffe in ihren Microsoft 365 E5 oder Microsoft Defender für Office 365 Plan 2-Organisationen auszuführen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 03e6c0077f13c85bfd20ac0583b64ce29e2535a1
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878676"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Angriffssimulator in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt** [für Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md)

Wenn Ihre Organisation über Microsoft Defender für Office 365 Plan 2 verfügt, der Funktionen für [die Untersuchung und Reaktion auf Bedrohungen](office-365-ti.md)umfasst, können Sie den Angriffssimulator im Security & Compliance Center verwenden, um realistische Angriffsszenarien in Ihrer Organisation auszuführen. Diese simulierten Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren und zu finden, bevor sich ein realer Angriff auf Ihre Unterlinie auswirkt. Lesen Sie diesen Artikel, um mehr zu erfahren.

> [!NOTE]
>
> Der Angriffssimulator, wie in diesem Artikel beschrieben, ist jetzt schreibgeschützt und wurde im Knoten **"E-Mail & Zusammenarbeit"** im Microsoft 365 Defender-Portal unter **"Angriffssimulationsschulung"** <https://security.microsoft.com> ersetzt. Weitere Informationen finden Sie unter ["Erste Schritte mit der Angriffssimulationsschulung".](attack-simulation-training-get-started.md)
>
> Die Möglichkeit, neue Simulationen aus dieser Version des Angriffssimulators zu starten, wurde deaktiviert. Sie können jedoch noch bis zum 24. April 2021 auf Berichte zugreifen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com/>. Der Angriffssimulator ist im Angriffssimulator für die **Bedrohungsverwaltung** \> verfügbar. Um direkt zum Angriffssimulator zu wechseln, öffnen Sie <https://protection.office.com/attacksimulator> .

- Weitere Informationen zur Verfügbarkeit des Angriffssimulators in verschiedenen Microsoft 365-Abonnements finden Sie unter [Microsoft Defender für Office 365 Dienstbeschreibung.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- Sie müssen Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein. Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Ihr Konto muss für die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) konfiguriert werden, um Kampagnen im Angriffssimulator zu erstellen und zu verwalten. Anweisungen finden Sie unter Einrichten der [mehrstufigen Authentifizierung.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Der Angriffssimulator funktioniert nur für cloudbasierte Postfächer.

- Phishingkampagnen sammeln und verarbeiten Ereignisse für 30 Tage. Verlaufskampagnendaten stehen bis zu 90 Tage nach dem Start der Kampagne zur Verfügung.

- Angriffssimulations- und Schulungsdaten werden zusammen mit anderen Kundendaten für Microsoft 365-Dienste gespeichert. Weitere Informationen finden Sie unter [Microsoft 365 Datenspeicherorten.](../../enterprise/o365-data-locations.md)

- Es gibt keine entsprechenden PowerShell-Cmdlets für den Angriffssimulator.

## <a name="spear-phishing-campaigns"></a>Spear-Phishingkampagnen

*Phishing* ist ein allgemeiner Begriff für E-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die scheinbar von legitimen oder vertrauenswürdigen Absendern stammen. *Spear-Phishing* ist ein gezielter Phishing-Angriff, der fokussierte und angepasste Inhalte verwendet, die speziell auf die Zielempfänger zugeschnitten sind (in der Regel nach der Aufarbeitung der Empfänger durch den Angreifer).

Im Angriffssimulator stehen zwei verschiedene Arten von Phishingkampagnen zur Verfügung:

- **Spear-Phishing (Credentials Harvest):** Der Angriff versucht, die Empfänger davon zu überzeugen, auf eine URL in der Nachricht zu klicken. Wenn sie auf den Link klicken, werden sie aufgefordert, ihre Anmeldeinformationen einzugeben. Wenn dies der Fall ist, werden sie an einen der folgenden Speicherorte weitergeleitet:

  - Eine Standardseite, auf der erläutert wird, dass dies nur ein Test war, und gibt Tipps zum Erkennen von Phishingnachrichten.

    ![Was Benutzern angezeigt wird, wenn sie auf den Phishing-Link klicken und ihre Anmeldeinformationen eingeben](../../media/attack-simulator-phishing-result.png)

  - Eine benutzerdefinierte Seite (URL), die Sie angeben.

- **Spear-Phishing (Anlage):** Der Angriff versucht, die Empfänger davon zu überzeugen, eine .docx oder .pdf Anlage in der Nachricht zu öffnen. Die Anlage enthält den gleichen Inhalt aus dem Standardmäßigen Phishing-Link, aber der erste Satz beginnt mit " \<Display Name\> , diese Nachricht wird als zuletzt geöffnete E-Mail-Nachricht angezeigt...".

> [!NOTE]
> Derzeit laufen Spear-Phishingkampagnen im Angriffssimulator nicht ab.

### <a name="create-a-spear-phishing-campaign"></a>Erstellen einer Spear-Phishing-Kampagne

Ein wichtiger Bestandteil jeder Spear-Phishing-Kampagne ist das Aussehen und Verhalten der E-Mail-Nachricht, die an die Zielempfänger gesendet wird. Zum Erstellen und Konfigurieren der E-Mail-Nachricht stehen Ihnen die folgenden Optionen zur Verfügung:

- **Verwenden Sie eine integrierte E-Mail-Vorlage:** Zwei integrierte Vorlagen sind verfügbar: **"Give away"** und **"Payroll Update".** Sie können einige, alle oder keine der E-Mail-Eigenschaften aus der Vorlage weiter anpassen, wenn Sie die Kampagne erstellen und starten.

- **Erstellen Sie eine wiederverwendbare E-Mail-Vorlage:** Nachdem Sie die E-Mail-Vorlage erstellt und gespeichert haben, können Sie sie in zukünftigen Spear-Phishingkampagnen erneut verwenden. Sie können einige, alle oder keine der E-Mail-Eigenschaften aus der Vorlage weiter anpassen, wenn Sie die Kampagne erstellen und starten.

- **Erstellen Sie die E-Mail-Nachricht im Assistenten:** Sie können die E-Mail-Nachricht direkt im Assistenten erstellen, während Sie die Speerphishingkampagne erstellen und starten.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Schritt 1 (Optional): Erstellen einer benutzerdefinierten E-Mail-Vorlage

Wenn Sie eine der integrierten Vorlagen verwenden oder die E-Mail-Nachricht direkt im Assistenten erstellen möchten, können Sie diesen Schritt überspringen.

1. Wechseln Sie im Security & Compliance Center zum Angriffssimulator für die **Bedrohungsverwaltung.** \> 

2. Klicken Sie auf der Seite **"Angriffe simulieren"** in den **Abschnitten "Spear Phishing (Credentials Harvest)** " oder **"Spear Phishing (Attachment)** " auf **"Angriffsdetails".**

   Es spielt keine Rolle, wo Sie die Vorlage erstellen. Die verfügbaren Optionen in der Vorlage sind für beide Arten von Phishingangriffen identisch.

3. Klicken Sie auf der daraufhin geöffneten **Seite "Angriffsdetails"** im Abschnitt **"Phishingvorlagen"** im Bereich **"Vorlagen erstellen"** auf **"Neue Vorlage".**

4. Der Assistent **zum Konfigurieren von Phishingvorlagen** wird in einem neuen Flyout gestartet. Geben Sie im **Startschritt** einen eindeutigen Anzeigenamen für die Vorlage ein, und klicken Sie dann auf **"Weiter".**

5. Konfigurieren Sie im Schritt **"E-Mail-Details konfigurieren"** die folgenden Einstellungen:

   - **From (Name)**: Der Anzeigename, der für den Absender der Nachricht verwendet wird.

   - **Von (E-Mail):** Die E-Mail-Adresse des Absenders.

   - URL des **Phishing-Anmeldeservers:** Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus. Dies ist die URL, auf die Benutzer klicken möchten. Sie können wie folgt vorgehen:

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
     > Ein URL-Zuverlässigkeitsdienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher. Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden.

   - URL der **benutzerdefinierten Zielseite:** Geben Sie eine optionale Zielseite ein, auf die Benutzer weitergeleitet werden, wenn sie auf den Phishing-Link klicken und ihre Anmeldeinformationen eingeben. Dieser Link ersetzt die Standardzielseite. Wenn Sie beispielsweise über eine interne Sensibilisierungsschulung verfügen, können Sie diese URL hier angeben.

   - **Kategorie:** Diese Einstellung wird derzeit nicht verwendet (alles, was Sie eingeben, wird ignoriert).

   - **Betreff:** Das **Feld "Betreff"** der E-Mail-Nachricht.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

6. Erstellen Sie im Schritt **"E-Mail verfassen"** den Nachrichtentext der E-Mail-Nachricht. Sie können die Registerkarte **"E-Mail"** (ein Rich-HTML-Editor) oder die Registerkarte **"Quelle"** (unformatierter HTML-Code) verwenden.

   Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie benötigen. Sie können Bilder und Text einfügen, um die Zuverlässigkeit der Nachricht im E-Mail-Client des Empfängers zu verbessern.

   - `${username}` fügt den Namen des Empfängers ein.

   - `${loginserverurl}` fügt den **URL-Wert des Phishing-Anmeldeservers** aus dem vorherigen Schritt ein.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

7. Klicken Sie im Schritt **"Bestätigen"** auf **"Fertig stellen".**

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Schritt 2: Erstellen und Starten der Spear-Phishing-Kampagne

1. Wechseln Sie im Security & Compliance Center zum Angriffssimulator für die **Bedrohungsverwaltung.** \> 

2. Treffen Sie auf der Seite **"Angriffe simulieren"** eine der folgenden Auswahlen basierend auf dem Typ der Kampagne, die Sie erstellen möchten:

   - Klicken Sie im Abschnitt **"Spear Phishing (Credentials Harvest)"** auf **"Angriff starten",** oder klicken Sie auf **"Angriffsdetails** \> **starten".**

   - Klicken Sie im Abschnitt **"Spear Phishing (Attachment)"** auf **"Angriff starten",** oder klicken Sie auf **"Angriffsdetails** \> **starten".**

3. Der Assistent **zum Konfigurieren von Phishingangriffen** wird in einem neuen Flyout gestartet. Führen Sie im **Startschritt** einen der folgenden Schritte aus:

   - Geben Sie im **Feld "Name"** einen eindeutigen Anzeigenamen für die Kampagne ein. Klicken Sie nicht auf **Vorlage verwenden,** da Sie die E-Mail-Nachricht später im Assistenten erstellen.

   - Klicken Sie auf **Vorlage verwenden,** und wählen Sie eine integrierte oder benutzerdefinierte E-Mail-Vorlage aus. Nachdem Sie die Vorlage ausgewählt haben, wird das **Feld Name** basierend auf der Vorlage automatisch ausgefüllt, Sie können den Namen jedoch ändern.

   > [!div class="mx-imgBorder"]
   > ![Phishing-Startseite](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

4. Führen Sie im Schritt **"Zielempfänger"** einen der folgenden Schritte aus:

   - Klicken Sie auf **"Adressbuch",** um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen. Jeder Zielempfänger muss über ein Exchange Online Postfach verfügen. Wenn Sie auf **"Filtern"** und **"Anwenden"** klicken, ohne suchkriterien einzugeben, werden alle Empfänger zurückgegeben und der Kampagne hinzugefügt.

   - Klicken Sie auf **"Importieren"** und dann auf **"Dateiimport",** um einen durch Trennzeichen getrennten Wert (CSV) oder eine zeilentrennte Datei mit E-Mail-Adressen zu importieren. Jede Zeile muss die E-Mail-Adresse des Empfängers enthalten.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Konfigurieren Sie im Schritt **"E-Mail-Details konfigurieren"** die folgenden Einstellungen:

   Wenn Sie im **Startschritt** eine Vorlage ausgewählt haben, sind die meisten dieser Werte bereits konfiguriert, sie können jedoch geändert werden.

   - **From (Name)**: Der Anzeigename, der für den Absender der Nachricht verwendet wird.

   - **Von (E-Mail):** Die E-Mail-Adresse des Absenders. Sie können eine echte oder gefälschte E-Mail-Adresse aus der E-Mail-Domäne Ihrer Organisation eingeben oder eine echte oder gefälschte externe E-Mail-Adresse eingeben. Eine gültige Absender-E-Mail-Adresse aus Ihrer Organisation wird tatsächlich im E-Mail-Client des Empfängers aufgelöst.

   - URL des **Phishing-Anmeldeservers:** Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus. Dies ist die URL, auf die Benutzer klicken möchten. Sie können wie folgt vorgehen:

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
     > - Ein URL-Zuverlässigkeitsdienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher. Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden.
     >
     > - Sie müssen eine URL auswählen. Bei **Kampagnen für Spear-Phishing (Attachment)** können Sie den Link im nächsten Schritt aus dem Nachrichtentext entfernen (andernfalls enthält die Nachricht sowohl einen **Link** als auch eine Anlage).

   - **Anlagentyp:** Diese Einstellung ist nur in **Spear-Phishing-Kampagnen (Attachment)** verfügbar. Klicken Sie auf die Dropdownliste, und wählen Sie **.DOCX** oder **.PDF** aus der Liste aus.

   - **Anlagenname:** Diese Einstellung ist nur in **Spear-Phishing-Kampagnen (Attachment)** verfügbar. Geben Sie einen Dateinamen für die .docx- oder .pdf-Anlage ein.

   - URL der **benutzerdefinierten Zielseite:** Geben Sie eine optionale Zielseite ein, auf die Benutzer weitergeleitet werden, wenn sie auf den Phishing-Link klicken und ihre Anmeldeinformationen eingeben. Dieser Link ersetzt die Standardzielseite. Wenn Sie beispielsweise über eine interne Sensibilisierungsschulung verfügen, können Sie diese URL hier angeben.

   - **Betreff:** Das **Feld "Betreff"** der E-Mail-Nachricht.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

6. Erstellen Sie im Schritt **"E-Mail verfassen"** den Nachrichtentext der E-Mail-Nachricht. Wenn Sie im **Startschritt** eine Vorlage ausgewählt haben, ist der Nachrichtentext bereits konfiguriert, Sie können sie jedoch anpassen. Sie können die Registerkarte **"E-Mail"** (ein Rich-HTML-Editor) oder die Registerkarte **"Quelle"** (unformatierter HTML-Code) verwenden.

   Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie benötigen. Sie können Bilder und Text einfügen, um die Zuverlässigkeit der Nachricht im E-Mail-Client des Empfängers zu verbessern.

   - `${username}` fügt den Namen des Empfängers ein.

   - `${loginserverurl}` fügt den **URL-Wert des Phishing-Anmeldeservers** ein.

   Für **Spear Phishing -Kampagnen (Attachment)** sollten Sie den Link aus dem Textkörper der Nachricht entfernen (andernfalls enthält die Nachricht sowohl einen **Link** als auch eine Anlage, und Linkklicks werden in einer Anlagenkampagne nicht nachverfolgt).

   > [!div class="mx-imgBorder"]
   > ![Verfassen des E-Mail-Textkörpers](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

7. Klicken Sie im Schritt **"Bestätigen"** auf **"Fertig stellen",** um die Kampagne zu starten. Die Phishingnachricht wird an die Zielempfänger übermittelt.

## <a name="password-attack-campaigns"></a>Kampagnen für Kennwortangriffe

Ein *Kennwortangriff* versucht, Kennwörter für Benutzerkonten in einer Organisation zu erraten, in der Regel nachdem der Angreifer ein oder mehrere gültige Benutzerkonten identifiziert hat.

Im Angriffssimulator stehen Ihnen zwei verschiedene Arten von Kennwortangriffskampagnen zur Verfügung, um die Komplexität der Kennwörter Ihrer Benutzer zu testen:

- **Brute-Force-Kennwort (Wörterbuchangriff):** Bei einem *Brute-Force-* oder *Wörterbuchangriff* wird eine große Wörterbuchdatei mit Kennwörtern für ein Benutzerkonto verwendet, in der Wunsch, dass eines davon funktioniert (viele Kennwörter für ein Konto). Falsche Kennwortsperrungen verhindern Brute-Force-Kennwortangriffe.

  Für den Wörterbuchangriff können Sie ein oder mehrere Kennwörter angeben, die Sie ausprobieren möchten (manuell eingegeben oder in einer hochgeladenen Datei), und Sie können einen oder mehrere Benutzer angeben.

- **Kennwort-Spray-Angriff:** Ein *Kennwort-Spray-Angriff* verwendet das gleiche sorgfältig durchdachte Kennwort für eine Liste von Benutzerkonten (ein Kennwort für viele Konten). Kennwort-Spray-Angriffe sind schwieriger zu erkennen als Brute-Force-Kennwortangriffe (die Wahrscheinlichkeit eines Erfolgs erhöht sich, wenn ein Angreifer ein Kennwort über Dutzende oder Hunderte von Konten hinweg versucht, ohne dass das Risiko besteht, dass er die falsche Kennwortsperrung des Benutzers durchläuft).

  Für den Kennwort-Spray-Angriff können Sie nur ein Kennwort angeben, das Sie ausprobieren möchten, und Sie können einen oder mehrere Benutzer angeben.

> [!NOTE]
> Die Kennwortangriffe im Angriffssimulator übergeben Benutzernamen- und Kennwort-Standardauthentifizierungsanforderungen an einen Endpunkt, sodass sie auch mit anderen Authentifizierungsmethoden (AD FS, Kennworthashsynchronisierung, Pass-Through, PingFederate usw.) funktionieren. Für Benutzer, für die MFA aktiviert ist, wird der Versuch auch dann immer als Fehler registriert, wenn der Kennwortangriff ihr tatsächliches Kennwort ausprobiert (mit anderen Worten, MFA-Benutzer werden nie in der Anzahl der **erfolgreichen Versuche** der Kampagne angezeigt). Dies ist das erwartete Ergebnis. MFA ist eine primäre Methode zum Schutz vor Kennwortangriffen.

### <a name="create-and-launch-a-password-attack-campaign"></a>Erstellen und Starten einer Kennwortangriffskampagne

1. Wechseln Sie im Security & Compliance Center zum Angriffssimulator für die **Bedrohungsverwaltung.** \> 

2. Treffen Sie auf der Seite **"Angriffe simulieren"** eine der folgenden Auswahlen basierend auf dem Typ der Kampagne, die Sie erstellen möchten:

   - Klicken Sie im Abschnitt **"Brute Force Password (Dictionary Attack)"** auf **"Angriff starten"** oder **"Angriffsdetails** \> **starten".**

   - Klicken Sie im Abschnitt **"Kennwort-Sprayangriff"** auf **"Angriff starten",** oder klicken Sie auf **"Angriffsdetails** \> **starten".**

3. Der Assistent zum **Konfigurieren von Kennwortangriffen** wird in einem neuen Flyout gestartet. Geben Sie im **Startschritt** einen eindeutigen Anzeigenamen für die Kampagne ein, und klicken Sie dann auf **"Weiter".**

4. Führen Sie im Schritt **"Zielbenutzer"** einen der folgenden Schritte aus:

   - Klicken Sie auf **"Adressbuch",** um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen. Jeder Zielempfänger muss über ein Exchange Online Postfach verfügen. Wenn Sie auf **"Filtern"** und **"Anwenden"** klicken, ohne suchkriterien einzugeben, werden alle Empfänger zurückgegeben und der Kampagne hinzugefügt.

   - Klicken Sie auf **"Importieren"** und dann auf **"Dateiimport",** um einen durch Trennzeichen getrennten Wert (CSV) oder eine zeilentrennte Datei mit E-Mail-Adressen zu importieren. Jede Zeile muss die E-Mail-Adresse des Empfängers enthalten.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Wählen Sie im Schritt **"Angriffseinstellungen auswählen"** basierend auf dem Kampagnentyp die gewünschten Aktionen aus:

   - **Brute Force Password (Dictionary Attack):** Führen Sie einen der folgenden Schritte aus:

     - **Geben Sie Kennwörter manuell** ein: Geben Sie in der **Eingabetaste zum Hinzufügen eines Kennwortfelds** ein Kennwort ein, und drücken Sie dann die EINGABETASTE. Wiederholen Sie diesen Schritt so oft wie nötig.

     - **Hochladen Kennwörter aus einer Wörterbuchdatei:** Klicken Sie auf **Hochladen,** um eine vorhandene Textdatei zu importieren, die ein Kennwort in jeder Zeile und eine leere letzte Zeile enthält. Die Textdatei darf maximal 10 MB groß sein und darf nicht mehr als 30.000 Kennwörter enthalten.

   - **Kennwort-Sprayangriff:** Geben Sie **in die im Angriffsfeld zu verwendenden Kennwörter** ein Kennwort ein.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

6. Klicken Sie im Schritt **"Bestätigen"** auf **"Fertig stellen",** um die Kampagne zu starten. Die von Ihnen angegebenen Kennwörter werden für die von Ihnen angegebenen Benutzer ausprobiert.

## <a name="view-campaign-results"></a>Anzeigen der Kampagnenergebnisse

Nachdem Sie eine Kampagne gestartet haben, können Sie den Fortschritt und die Ergebnisse auf der Hauptseite **"Angriffe simulieren"** überprüfen.

Aktive Kampagnen zeigen eine Statusleiste, einen abgeschlossenen Prozentwert und die Anzahl "(abgeschlossene Benutzer) von (Benutzer insgesamt)" an. Durch Klicken auf die Schaltfläche **"Aktualisieren"** wird der Fortschritt aller aktiven Kampagnen aktualisiert. Sie können auch auf **"Beenden"** klicken, um eine aktive Kampagne zu beenden.

Wenn die Kampagne abgeschlossen ist, ändert sich der Status in **Angriff abgeschlossen.** Sie können die Ergebnisse der Kampagne anzeigen, indem Sie eine der folgenden Aktionen ausführen:

- Klicken Sie auf der Hauptseite **"Angriffe simulieren"** unter dem Namen der Kampagne auf **"Bericht anzeigen".**

- Klicken Sie auf der Hauptseite **"Angriffe simulieren"** im Abschnitt auf **"Angriffsdetails"** für die Art des Angriffs. Wählen Sie auf der daraufhin geöffneten **Seite "Angriffsdetails"** die Kampagne im Abschnitt **"Angriffsverlauf"** aus.

Eine der vorherigen Aktionen führt Sie zu einer Seite mit dem Namen **"Angriffsdetails".** Die Informationen, die auf dieser Seite für jeden Kampagnentyp verfügbar sind, werden in den folgenden Abschnitten beschrieben.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Ergebnisse der Kampagne "Spear Phishing (Credentials Harvest)"

Die folgenden Informationen sind auf der **Seite "Angriffsdetails"** für jede Kampagne verfügbar:

- Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.

- **Gesamtzahl der Benutzer, die als Ziel verwendet werden**

- **Erfolgreiche Versuche:** Die Anzahl der Benutzer, die auf den Link geklickt **und** ihre Anmeldeinformationen eingegeben haben *(beliebiger* Benutzername und Kennwortwert).

- **Gesamterfolgsrate:** Ein Prozentsatz, der von **der** Gesamtzahl der  /  **benutzerzielen** erfolgreichen Versuche berechnet wird.

- **Schnellster Klick:** Wie lange es gedauert hat, bis der erste Benutzer nach dem Start der Kampagne auf den Link geklickt hat.

- **Durchschnittlicher Klick**: Die Summe, wie lange es gedauert hat, bis jeder auf den Link geklickt hat, dividiert durch die Anzahl der Benutzer, die auf den Link geklickt haben.

- **Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.

- **Schnellste Anmeldeinformationen:** Wie lange der erste Benutzer nach dem Start der Kampagne seine Anmeldeinformationen eingegeben hat.

- **Durchschnittliche Anmeldeinformationen:** Die Summe, wie lange es gedauert hat, bis alle Ihre Anmeldeinformationen eingegeben haben, dividiert durch die Anzahl der Benutzer, die ihre Anmeldeinformationen eingegeben haben.

- **Erfolgsrate für Anmeldeinformationen:** Ein Prozentsatz, der von (Anzahl der Benutzer, die ihre Anmeldeinformationen eingegeben haben) **/Die Gesamtzahl** der benutzerorientierte berechnet wird.

- Ein Balkendiagramm, das den **angeklickten Link** und **die angegebenen Anmeldeinformationen** pro Tag anzeigt.

- Ein Kreisdiagramm, das die Prozentsätze **Link geklickt ,** **Credential** supplied und **None** für die Kampagne anzeigt.

- Im Abschnitt **"Kompromittierte Benutzer"** werden die Details der Benutzer aufgelistet, die auf den Link geklickt haben:

  - Die E-Mail-Adresse des Benutzers

  - Das Datum/die Uhrzeit, an dem/der auf den Link geklickt wurde.

  - Die Client-IP-Adresse.

  - Details zur Version des Benutzers von Windows und Webbrowser.

  Sie können auf **"Exportieren"** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.

### <a name="spear-phishing-attachment-campaign-results"></a>Ergebnisse der Kampagne "Spear Phishing (Attachment) "

Die folgenden Informationen sind auf der **Seite "Angriffsdetails"** für jede Kampagne verfügbar:

- Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.

- **Gesamtzahl der Benutzer, die als Ziel verwendet werden**

- **Erfolgreiche Versuche:** Die Anzahl der Benutzer, die die Anlage geöffnet oder heruntergeladen und geöffnet haben (Vorschau zählt nicht).

- **Gesamterfolgsrate:** Ein Prozentsatz, der von **der** Gesamtzahl der  /  **benutzerzielen** erfolgreichen Versuche berechnet wird.

- Schnellste Zeit zum Öffnen von **Anlagen:** Wie lange es gedauert hat, bis der erste Benutzer die Anlage geöffnet hat, nachdem Sie die Kampagne gestartet haben.

- **Durchschnittliche Anlageöffnungszeit:** Die Summe, wie lange es gedauert hat, bis alle Personen die Anlage geöffnet haben, dividiert durch die Anzahl der Benutzer, die die Anlage geöffnet haben.

- **Erfolgsrate** beim Öffnen von Anlagen: Ein Prozentsatz, der von (Anzahl der Benutzer, die die Anlage geöffnet haben) /Die Gesamtzahl der benutzer, auf die **verwiesen wird,** berechnet wird.

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Ergebnisse der Brute Force Password (Dictionary Attack)-Kampagne

Die folgenden Informationen sind auf der **Seite "Angriffsdetails"** für jede Kampagne verfügbar:

- Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.

- **Gesamtzahl der Benutzer, die als Ziel verwendet werden**

- **Erfolgreiche Versuche:** Die Anzahl der Benutzer, die eines der angegebenen Kennwörter verwendet haben.

- **Gesamterfolgsrate:** Ein Prozentsatz, der von **der** Gesamtzahl der  /  **benutzerzielen** erfolgreichen Versuche berechnet wird.

- Im Abschnitt **"Kompromittierte Benutzer"** sind die E-Mail-Adressen der betroffenen Benutzer aufgeführt. Sie können auf **"Exportieren"** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.

### <a name="password-spray-attack-campaign-results"></a>Ergebnisse der Kennwort-Spray-Angriffskampagne

Die folgenden Informationen sind auf der **Seite "Angriffsdetails"** für jede Kampagne verfügbar:

- Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.

- **Gesamtzahl der Benutzer, die als Ziel verwendet werden**

- **Erfolgreiche Versuche:** Die Anzahl der Benutzer, die das angegebene Kennwort verwendet haben.

- **Gesamterfolgsrate:** Ein Prozentsatz, der von **der** Gesamtzahl der  /  **benutzerzielen** erfolgreichen Versuche berechnet wird.
