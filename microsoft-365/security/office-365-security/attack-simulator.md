---
title: Angriffs Simulator in ATP
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
ms.custom:
- seo-marvel-apr2020
description: Administratoren erfahren, wie Sie mithilfe des Angriffs Simulators simulierte Phishing-und Kennwortangriffe in Ihren Microsoft 365 E5-oder ATP-Plan-2-Organisationen ausführen können.
ms.openlocfilehash: 9fc28cdecc07f5325918e3d5176e52d1051a626c
ms.sourcegitcommit: 2b8c3fc39a7cbd4ca35e98dca430d2470cd2c925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47426993"
---
# <a name="attack-simulator-in-atp"></a>Angriffs Simulator in ATP

Wenn Ihre Organisation Office 365 Advanced Threat Protection (ATP) Plan 2, einschließlich der [Funktionen zur Ermittlung und Reaktion von Bedrohungen](office-365-ti.md), verfügt, können Sie den Angriffs Simulator im Security & Compliance Center verwenden, um realistische Angriffsszenarien in Ihrer Organisation auszuführen. Diese simulierten Angriffe können Sie bei der Identifizierung und Suche nach anfälligen Benutzern unterstützen, bevor ein echter Angriff Ihr Endergebnis beeinträchtigt. Lesen Sie diesen Artikel, um mehr zu erfahren.

> [!NOTE]
> Angriffssimulation und schulungsbezogene Daten werden mit anderen Kundendaten für Microsoft 365-Dienste gespeichert. Weitere Informationen finden Sie unter [Microsoft 365-Datenspeicherorte](/microsoft-365/enterprise/o365-data-locations).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com/>. Angriffs Simulator ist unter **Threat Management** \> **Attack Simulator**verfügbar. Wechseln Sie direkt zum Angriffs Simulator, öffnen Sie <https://protection.office.com/attacksimulator> .

- Weitere Informationen zur Verfügbarkeit des Angriffs Simulators in verschiedenen Microsoft 365-Abonnements finden Sie unter [Office 365 Advanced Threat Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Sie müssen Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein. Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Ihr Konto muss für die mehrstufige Authentifizierung (MFA) konfiguriert sein, um Kampagnen im Angriffs Simulator zu erstellen und zu verwalten. Anweisungen finden Sie unter [Einrichten der mehr](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)stufigen Authentifizierung.

- Bei Phishing-Kampagnen werden Ereignisse für 30 Tage gesammelt und verarbeitet. Die Daten der Verlaufs Kampagne werden bis zu 90 Tage nach dem Start der Kampagne zur Verfügung stehen.

- Es gibt keine entsprechenden PowerShell-Cmdlets für den Angriffs Simulator.

## <a name="spear-phishing-campaigns"></a>Speer-Phishing-Kampagnen

*Phishing* ist ein allgemeiner Begriff für e-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die anscheinend von legitimen oder vertrauenswürdigen Absendern sind. *Spear-Phishing* ist ein gezielter Phishing-Angriff, der fokussierte und angepasste Inhalte verwendet, die speziell auf die Zielempfänger zugeschnitten sind (normalerweise nach Aufklärung der Empfänger durch den Angreifer).

In Attack Simulator stehen zwei verschiedene Arten von Speer-Phishing-Kampagnen zur Verfügung:

- **Spear Phishing (Credentials Harvest)**: der Angriff versucht, die Empfänger davon zu überzeugen, auf eine URL in der Nachricht zu klicken. Wenn Sie auf den Link klicken, werden Sie aufgefordert, Ihre Anmeldeinformationen einzugeben. Wenn dies der Fall ist, werden Sie an einen der folgenden Speicherorte geleitet:

  - Eine Standardseite, die erklärt, dass dies ein nur ein Test war, und gibt Tipps zum Erkennen von Phishing-Nachrichten.

    ![Was die Benutzer sehen, wenn Sie auf den Phishing-Link klicken und Ihre Anmeldeinformationen eingeben](../../media/attack-simulator-phishing-result.png)

  - Eine benutzerdefinierte Seite (URL), die Sie angeben.

- **Spear-Phishing (Attachment)**: der Angriff versucht, die Empfänger davon zu überzeugen, eine DOCX-oder PDF-Anlage in der Nachricht zu öffnen. Die Anlage enthält denselben Inhalt aus dem standardmäßigen Phishing-Link, aber der erste Satz beginnt mit " \<Display Name\> , diese Nachricht wird als kürzlich geöffnete e-Mail-Nachricht angezeigt...".

> [!NOTE]
> Derzeit laufen Speer-Phishing-Kampagnen in Attack Simulator nicht ab.

### <a name="create-a-spear-phishing-campaign"></a>Erstellen einer Speer-Phishing-Kampagne

Ein wichtiger Bestandteil jeder Speer-Phishing-Kampagne ist das Aussehen und Verhalten der e-Mail-Nachricht, die an die Zielempfänger gesendet wird. Sie haben folgende Möglichkeiten, um die e-Mail-Nachricht zu erstellen und zu konfigurieren:

- **Verwenden Sie eine integrierte e-Mail-Vorlage**: zwei integrierte Vorlagen stehen zur Verfügung: **Preis Giveaway** -und **Gehaltslisten Update**. Sie können einige, alle oder keine der e-Mail-Eigenschaften von der Vorlage anpassen, wenn Sie die Kampagne erstellen und starten.

- **Erstellen einer wiederverwendbaren e-Mail-Vorlage**: Nachdem Sie die e-Mail-Vorlage erstellt und gespeichert haben, können Sie Sie in künftigen Spear-Phishing-Kampagnen erneut verwenden. Sie können einige, alle oder keine der e-Mail-Eigenschaften von der Vorlage anpassen, wenn Sie die Kampagne erstellen und starten.

- **Erstellen Sie die e-Mail-Nachricht im Assistenten**: Sie können die e-Mail-Nachricht direkt im Assistenten erstellen, während Sie die Spear-Phishing-Kampagne erstellen und starten.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Schritt 1 (optional): Erstellen einer benutzerdefinierten e-Mail-Vorlage

Wenn Sie eine der integrierten Vorlagen verwenden oder die e-Mail-Nachricht direkt im Assistenten erstellen, können Sie diesen Schritt überspringen.

1. Wechseln Sie im Security & Compliance Center zum **Threat Management** - \> **Angriffs Simulator**.

2. Klicken Sie auf der Seite " **Angriffe simulieren** " entweder in den Abschnitten **Spear Phishing (Credentials Harvest)** oder **Spear Phishing (Attachment)** auf **Attack Details**.

   Es spielt keine Rolle, wo Sie die Vorlage erstellen. Die verfügbaren Optionen in der Vorlage sind für beide Arten von Phishing-Angriffen identisch.

3. Klicken Sie auf der daraufhin geöffneten Seite mit den **Angriffs Details** im Abschnitt **Phishing-Vorlagen** im Bereich **Vorlagen erstellen** auf **neue Vorlage**.

4. Der Assistent zum **Konfigurieren von Phishing-Vorlagen** wird in einem neuen Flyout gestartet. Geben Sie im Schritt **Start** einen eindeutigen Anzeigenamen für die Vorlage ein, und klicken Sie dann auf **weiter**.

5. Konfigurieren Sie im Schritt **e-Mail-Details konfigurieren** die folgenden Einstellungen:

   - **From (Name)**: der Anzeige Name, der für den Absender der Nachricht verwendet wird.

   - **Von (e-Mail)**: die e-Mail-Adresse des Absenders.

   - **URL des Phishing-Anmeldeservers**: Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus. Dies ist die URL, auf die Benutzer klicken sollen. Sie können wie folgt vorgehen:

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
     > - Alle URLs sind absichtlich HTTP und nicht HTTPS.
     >
     > - Ein URL-Reputations Dienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher. Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishing-Kampagne verwenden.

   - **Benutzerdefinierte Startseiten-URL**: Geben Sie eine optionale Startseite ein, auf der Benutzer angezeigt werden, wenn Sie auf den Link Phishing klicken und die Anmeldeinformationen eingeben. Dieser Link ersetzt die standardmäßige Ziel Seite. Wenn Sie beispielsweise ein internes Bewusstseinstraining haben, können Sie diese URL hier angeben.

   - **Kategorie**: Derzeit wird diese Einstellung nicht verwendet (alles, was Sie eingeben, wird ignoriert).

   - **Subject**: das **Subject** -Feld der e-Mail-Nachricht.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

6. Erstellen Sie im Schritt **e-Mail verfassen** den Nachrichtentext der e-Mail-Nachricht. Sie können die Registerkarte " **e-Mail** " (ein Rich-HTML-Editor) oder die Registerkarte " **Quelle** " (unformatierter HTML-Code) verwenden.

   Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen. Sie können Bilder und Text einfügen, um die Glaubwürdigkeit erhöhen der Nachricht im e-Mail-Client des Empfängers zu verbessern.

   - `${username}` Fügt den Namen des Empfängers ein.

   - `${loginserverurl}` Fügt den URL-Wert des **Phishing-Anmeldeservers** aus dem vorherigen Schritt ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

7. Klicken Sie im Schritt **bestätigen** auf **Fertig stellen**.

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Schritt 2: Erstellen und Starten der Spear-Phishing-Kampagne

1. Wechseln Sie im Security & Compliance Center zum **Threat Management** - \> **Angriffs Simulator**.

2. Wählen Sie auf der Seite **Angriffe simulieren** eine der folgenden Optionen basierend auf der Art der Kampagne aus, die Sie erstellen möchten:

   - Klicken Sie im Abschnitt **Spear Phishing (Credentials Harvest)** auf **Angriff starten** oder auf Angriff **Details** \> **starten Angriff**.

   - Klicken Sie im Abschnitt **Spear Phishing (Attachment)** auf **Angriff starten** oder auf Angriff **Details** \> **starten Angriff**.

3. Der Assistent zum **Konfigurieren von Phishing-Angriffen** wird in einem neuen Flyout gestartet. Führen Sie im **Start** Schritt einen der folgenden Schritte aus:

   - Geben Sie im Feld **Name** einen eindeutigen Anzeigenamen für die Kampagne ein. Klicken Sie nicht auf **Vorlage verwenden**, da Sie die e-Mail-Nachricht später im Assistenten erstellen.

   - Klicken Sie auf **Vorlage verwenden** , und wählen Sie eine integrierte oder benutzerdefinierte e-Mail-Vorlage aus. Nachdem Sie die Vorlage ausgewählt haben, wird das Feld **Name** automatisch basierend auf der Vorlage ausgefüllt, aber Sie können den Namen ändern.

   ![Phishing-Start Seite](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Führen Sie im Schritt **Zielempfänger** einen der folgenden Schritte aus:

   - Klicken Sie auf **Adressbuch** , um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen. Jeder Zielempfänger muss über ein Exchange Online Postfach verfügen. Wenn Sie auf **Filtern** und **anwenden** klicken, ohne Suchkriterien einzugeben, werden alle Empfänger zurückgegeben und zur Kampagne hinzugefügt.

   - Klicken Sie auf **Import** dann auf **Dateiimport** , um einen durch Kommas getrennten Wert (CSV) oder eine durch die Datei getrennte Datei mit e-Mail-Adressen zu importieren. Jede Reihe muss die e-Mail-Adresse des Empfängers enthalten.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Konfigurieren Sie im Schritt **e-Mail-Details konfigurieren** die folgenden Einstellungen:

   Wenn Sie im **Start** Schritt eine Vorlage ausgewählt haben, sind die meisten dieser Werte bereits konfiguriert, aber Sie können Sie ändern.

   - **From (Name)**: der Anzeige Name, der für den Absender der Nachricht verwendet wird.

   - **Von (e-Mail)**: die e-Mail-Adresse des Absenders. Sie können eine reale oder gefälschte e-Mail-Adresse aus der e-Mail-Domäne Ihrer Organisation eingeben, oder Sie können eine reale oder gefälschte externe e-Mail-Adresse eingeben. Eine gültige Absender-e-Mail-Adresse aus Ihrer Organisation wird tatsächlich im e-Mail-Client des Empfängers aufgelöst.

   - **URL des Phishing-Anmeldeservers**: Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus. Dies ist die URL, auf die Benutzer klicken sollen. Sie können wie folgt vorgehen:

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
     > - Alle URLs sind absichtlich HTTP und nicht HTTPS.
     >
     > - Ein URL-Reputations Dienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher. Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishing-Kampagne verwenden.
     >
     > - Sie müssen eine URL auswählen. Bei Kampagnen mit **Spear-Phishing (Attachment)** können Sie den Link aus dem Textkörper der Nachricht im nächsten Schritt entfernen (andernfalls enthält die Nachricht sowohl einen Link als **auch** eine Anlage).

   - **Anlagentyp**: Diese Einstellung ist nur in Kampagnen für **Spear-Phishing (Attachment)** verfügbar. Klicken Sie auf die Dropdownliste, und wählen Sie aus **. DOCX** oder **. PDF** aus der Liste.

   - **Name der Anlage**: Diese Einstellung ist nur in Kampagnen für **Spear-Phishing (Attachment)** verfügbar. Geben Sie einen Dateinamen für die Datei. docx oder. PDF ein.

   - **Benutzerdefinierte Startseiten-URL**: Geben Sie eine optionale Startseite ein, auf der Benutzer angezeigt werden, wenn Sie auf den Link Phishing klicken und die Anmeldeinformationen eingeben. Dieser Link ersetzt die standardmäßige Ziel Seite. Wenn Sie beispielsweise ein internes Bewusstseinstraining haben, können Sie diese URL hier angeben.

   - **Subject**: das **Subject** -Feld der e-Mail-Nachricht.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

6. Erstellen Sie im Schritt **e-Mail verfassen** den Nachrichtentext der e-Mail-Nachricht. Wenn Sie im **Start** Schritt eine Vorlage ausgewählt haben, ist der Nachrichtentext bereits konfiguriert, Sie können ihn jedoch anpassen. Sie können die Registerkarte " **e-Mail** " (ein Rich-HTML-Editor) oder die Registerkarte " **Quelle** " (unformatierter HTML-Code) verwenden.

   Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen. Sie können Bilder und Text einfügen, um die Glaubwürdigkeit erhöhen der Nachricht im e-Mail-Client des Empfängers zu verbessern.

   - `${username}` Fügt den Namen des Empfängers ein.

   - `${loginserverurl}` Fügt den URL-Wert für den **Phishing-Anmelde Server** ein.

   Bei Kampagnen mit **Spear-Phishing (Attachment)** sollten Sie den Link aus dem Nachrichtentext entfernen (andernfalls enthält die Nachricht sowohl einen Link als **auch** eine Anlage, und Link Klicks werden nicht in einer Anlagen Kampagne nachverfolgt).

   ![E-Mail-Textkörper erstellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

7. Klicken Sie im Schritt **bestätigen** auf **Fertig stellen** , um die Kampagne zu starten. Die Phishing-Nachricht wird an die Zielempfänger übermittelt.

## <a name="password-attack-campaigns"></a>Kenn Wort Angriffs Kampagnen

Ein *Kennwortangriff* versucht, Kennwörter für Benutzerkonten in einer Organisation zu erraten, in der Regel, nachdem der Angreifer mindestens ein gültiges Benutzerkonto erkannt hat.

In Attack Simulator stehen zwei verschiedene Arten von Kenn Wort Angriffs Kampagnen zur Verfügung, um die Komplexität der Kennwörter Ihrer Benutzer zu testen:

- **Brute-Force-Kennwort (Wörterbuchangriff)**: bei einem *Brute-Force* -oder *Wörterbuch* Angriff wird eine große Wörterbuchdatei mit Kennwörtern für ein Benutzerkonto verwendet, wobei die Hoffnung besteht, dass einer von Ihnen funktioniert (viele Kennwörter für ein Konto). Falsche Kenn Wort Sperren helfen, Brute-Force-Kennwortangriffe zu verhindern.

  Für den Wörterbuchangriff können Sie ein oder mehrere Kennwörter angeben, die Sie ausprobieren möchten (manuell eingegeben oder in eine hochgeladene Datei), und Sie können einen oder mehrere Benutzer angeben.

- **Kenn Wort Sprüh Angriff**: bei einem *Kenn Wort Sprüh* Angriff wird dasselbe sorgfältig überprüfte Kennwort für eine Liste von Benutzerkonten verwendet (ein Kennwort für viele Konten). Kenn Wort Sprüh Angriffe sind schwerer zu erkennen als Brute-Force-Kennwortangriffe (die Erfolgswahrscheinlichkeit steigt, wenn ein Angreifer ein Kennwort in Dutzenden oder Hunderten von Konten versucht, ohne dass die falsche Kenn Wort Sperrung des Benutzers ausgelöst wird).

  Für den Kenn Wort Sprüh Angriff können Sie nur ein Kennwort angeben, das Sie ausprobieren möchten, und Sie können einen oder mehrere Benutzer angeben.

> [!NOTE]
> Die Kennwortangriffe im Angriffs Simulator übergeben Benutzernamen-und Kenn Wort grundlegende Authentifizierungsanforderungen an einen Endpunkt, sodass Sie auch mit anderen Authentifizierungsmethoden (AD FS, Kennworthash Synchronisierung, Pass-Through, PingFederate usw.) funktionieren. Für Benutzer, die MFA aktiviert haben, wird der Versuch, selbst wenn der Kennwortangriff sein tatsächliches Kennwort versucht, immer als Fehler registriert (in anderen Worten: MFA-Benutzer werden nie in der Anzahl der **erfolgreichen Versuche** der Kampagne angezeigt). Dies ist das erwartete Ergebnis. MFA ist eine primäre Methode zum Schutz vor Kennwortangriffen.

### <a name="create-and-launch-a-password-attack-campaign"></a>Erstellen und Starten einer Kenn Wort Angriffs Kampagne

1. Wechseln Sie im Security & Compliance Center zum **Threat Management** - \> **Angriffs Simulator**.

2. Wählen Sie auf der Seite **Angriffe simulieren** eine der folgenden Optionen basierend auf der Art der Kampagne aus, die Sie erstellen möchten:

   - Klicken Sie im Abschnitt **Brute-Force-Kennwort (Wörterbuchangriff)** auf **Angriff starten** , oder klicken Sie auf Angriff **Details** \> **starten**.

   - Klicken Sie im Abschnitt **Kenn Wort Sprüh Angriff** auf **Angriff starten** oder auf Angriff **Details** \> **starten Angriff**.

3. Der Assistent zum **Konfigurieren von Kennwortangriffen** wird in einem neuen Flyout gestartet. Geben Sie im Schritt **Start** einen eindeutigen Anzeigenamen für die Kampagne ein, und klicken Sie dann auf **weiter**.

4. Führen Sie im Schritt **Zielbenutzer** einen der folgenden Schritte aus:

   - Klicken Sie auf **Adressbuch** , um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen. Jeder Zielempfänger muss über ein Exchange Online Postfach verfügen. Wenn Sie auf **Filtern** und **anwenden** klicken, ohne Suchkriterien einzugeben, werden alle Empfänger zurückgegeben und zur Kampagne hinzugefügt.

   - Klicken Sie auf **Import** dann auf **Dateiimport** , um einen durch Kommas getrennten Wert (CSV) oder eine durch die Datei getrennte Datei mit e-Mail-Adressen zu importieren. Jede Reihe muss die e-Mail-Adresse des Empfängers enthalten.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Wählen Sie im Schritt **Angriffs Einstellungen auswählen** aus, welche Aktionen basierend auf dem Kampagnentyp vorgenommen werden sollen:

   - **Brute-Force-Kennwort (Wörterbuchangriff)**: führen Sie einen der folgenden Schritte aus:

     - **Manuelles Eingeben von Kennwörtern**: Geben Sie in das Feld **EINGABETASTE drücken, um ein Kennwort hinzuzufügen** ein Kennwort ein, und drücken Sie dann die EINGABETASTE. Wiederholen Sie diesen Schritt so oft wie nötig.

     - **Hochladen von Kennwörtern aus einer Wörterbuchdatei**: Klicken Sie auf **hochladen** , um eine vorhandene Textdatei zu importieren, die in jeder Zeile ein Kennwort enthält, und eine leere letzte Zeile. Die Textdatei muss mindestens 10 MB groß sein und darf nicht mehr als 30000 Kennwörter enthalten.

   - **Kenn Wort Sprüh Angriff**: Geben Sie in **den zu verwendenden Kennwörtern im Feld Angriff** ein Kennwort ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

6. Klicken Sie im Schritt **bestätigen** auf **Fertig stellen** , um die Kampagne zu starten. Die von Ihnen angegebenen Kennwörter werden für Benutzer ausprobiert, die Sie angegeben haben.

## <a name="view-campaign-results"></a>Anzeigen von kampagnenergebnissen

Nachdem Sie eine Kampagne gestartet haben, können Sie den Fortschritt und die Ergebnisse auf der Seite Haupt **Angriffe simulieren** überprüfen.

In aktiven Kampagnen wird eine Statusleiste, ein abgeschlossener Prozentwert und "(abgeschlossene Benutzer) von (Gesamtanzahl der Benutzer)" angezeigt. Durch Klicken auf die Schaltfläche **Aktualisieren** wird der Status aller aktiven Kampagnen aktualisiert. Sie können auch auf **Beenden** klicken, um eine aktive Kampagne zu beenden.

Wenn die Kampagne abgeschlossen ist, wird der Status in **Angriff abgeschlossen**geändert. Sie können die Ergebnisse der Kampagne anzeigen, indem Sie eine der folgenden Aktionen ausführen:

- Klicken Sie auf der Seite Haupt **Angriffe simulieren** auf **Bericht anzeigen** unter dem Namen der Kampagne.

- Klicken Sie auf der Seite Haupt **Angriffe simulieren** auf **Angriffs Details** im Abschnitt für den Typ des Angriffs. Wählen Sie auf der Seite **Angriffs Details** , die geöffnet wird, die Kampagne im Abschnitt **Angriffs Verlauf** aus.

Mit einer der vorherigen Aktionen gelangen Sie zu einer Seite mit dem Namen " **Angriffs Details**". Die Informationen, die auf dieser Seite für jede Art von Kampagne zur Verfügung stehen, werden in den folgenden Abschnitten beschrieben.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Kampagnenergebnisse für Spear-Phishing (Sammeln von Anmeldeinformationen)

Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:

- Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.

- **Zielgruppe der Gesamtbenutzer**

- **Erfolgreiche Versuche**: die Anzahl der Benutzer, die auf den Link geklickt **und** Ihre Anmeldeinformationen eingegeben haben (*beliebiger* Benutzername und Kennwortwert).

- **Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen**berechnet wird  /  .**Gesamtzahl der Benutzer**, die gezielt sind.

- **Schnellster Mausklick**: wie lange es dauerte, bis der erste Benutzer auf den Link klickt, nachdem Sie die Kampagne gestartet haben.

- **Durchschnittlicher Mausklick**: die Summe, wie lange es dauerte, bis jeder auf den Link geklickt hat, dividiert durch die Anzahl der Benutzer, die auf den Link geklickt haben.

- **Klicken Sie auf Erfolgs Rate**: einen Prozentsatz, der von berechnet wird (Anzahl der Benutzer, die auf den Link geklickt haben)/Gesamtanzahl der Benutzer, die als **Ziel**ausgewählt wurden

- **Schnellste Anmeldeinformationen**: wie lange dauerte es, bis der erste Benutzer seine Anmeldeinformationen eingegeben hat, nachdem die Kampagne gestartet wurde.

- **Durchschnittliche Anmeldeinformationen**: die Summe der Dauer, die jeder zum Eingeben der Anmeldeinformationen benötigte, dividiert durch die Anzahl der Benutzer, die Ihre Anmeldeinformationen eingegeben haben.

- **Erfolgs Rate der Anmeldeinformationen**: ein Prozentsatz, der von berechnet wird (Anzahl der Benutzer, die Ihre Anmeldeinformationen eingegeben haben)/Gesamtanzahl der Benutzer, die **zielgerichtet**sind.

- Ein Balkendiagramm, in dem der **Link geklickt** wird und die Anzahl der **Anmeldeinformationen** pro Tag angegeben wird.

- Ein Kreisdiagramm, in dem der **angeklickte Link**, die **angegebenen Anmeldeinformationen**und **keine** Prozentsätze für die Kampagne angezeigt werden.

- Im Abschnitt **kompromittierte Benutzer** werden die Details der Benutzer aufgelistet, die auf den Link geklickt haben:

  - Die E-Mail-Adresse des Benutzers

  - Das Datum/die Uhrzeit, zu dem der Link geklickt hat.

  - Die Client-IP-Adresse.

  - Details zur Benutzerversion von Windows und Webbrowser.

  Sie können auf **exportieren** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.

### <a name="spear-phishing-attachment-campaign-results"></a>Kampagnenergebnisse für Spear-Phishing (Attachment)

Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:

- Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.

- **Zielgruppe der Gesamtbenutzer**

- **Erfolgreiche Versuche**: die Anzahl der Benutzer, die die Anlage geöffnet oder heruntergeladen und geöffnet haben (Vorschau wird nicht gezählt).

- **Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen**berechnet wird  /  .**Gesamtzahl der Benutzer**, die gezielt sind.

- **Schnellste Anlage Open Time**: wie lange dauerte es, bis der erste Benutzer die Anlage geöffnet hat, nachdem Sie die Kampagne gestartet haben.

- **Open Time (durchschnittliche Anlage**): die Summe der Dauer, die jeder zum Öffnen der Anlage benötigte, dividiert durch die Anzahl der Benutzer, die die Anlage geöffnet haben.

- **Anlage offene Erfolgsrate**: ein Prozentsatz, der von berechnet wird (Anzahl der Benutzer, die die Anlage geöffnet haben)/Gesamtanzahl der **Zielbenutzer**.

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Kampagnenergebnisse für Brute-Force-Kennwort (Wörterbuchangriffe)

Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:

- Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.

- **Zielgruppe der Gesamtbenutzer**

- **Erfolgreiche Versuche**: die Anzahl der Benutzer, bei denen festgestellt wurde, dass Sie eines der angegebenen Kennwörter verwenden.

- **Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen**berechnet wird  /  .**Gesamtzahl der Benutzer**, die gezielt sind.

- Im Abschnitt **kompromittierte Benutzer** werden die e-Mail-Adressen der betroffenen Benutzer aufgelistet. Sie können auf **exportieren** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.

### <a name="password-spray-attack-campaign-results"></a>Kenn Wort Sprüh Angriff-Kampagnenergebnisse

Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:

- Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.

- **Zielgruppe der Gesamtbenutzer**

- **Erfolgreiche Versuche**: die Anzahl der Benutzer, für die das angegebene Kennwort verwendet wurde.

- **Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen**berechnet wird  /  .**Gesamtzahl der Benutzer**, die gezielt sind.
