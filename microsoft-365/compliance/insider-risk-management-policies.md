---
title: Richtlinien für Insider-Risikomanagement
description: Informationen zu Richtlinien für das Insider Risikomanagement in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: eff935eb39884d9003b64b5be952c8e8e73b286a
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515880"
---
# <a name="insider-risk-management-policies"></a>Richtlinien für Insider-Risikomanagement

Richtlinien für Insider-Risikomanagement bestimmen, welche Mitarbeiter im Bereich sind und welche Arten von Risikoindikatoren für Warnungen konfiguriert sind. Sie können schnell eine Richtlinie erstellen, die für alle Benutzer in Ihrer Organisation gilt, oder einzelne Benutzer oder Gruppen für die Verwaltung in einer Richtlinie definieren. Richtlinien unterstützen Inhalts Prioritäten, um Richtlinienbedingungen auf mehrere oder bestimmte Microsoft Teams, SharePoint-Websites, Daten Sensitivitäts Typen und Datenbeschriftungen zu konzentrieren. Die Verwendung von Vorlagen umfasst spezifische Risikoindikatoren und deren Gewichtung innerhalb einer Richtlinie, wobei die Gewichtung der einzelnen Warnungsauslöser in der Richtlinie effektiv bestimmt wird. Richtlinien-Fenster ermöglichen Ihnen, den Zeitrahmen zu definieren, um die Richtlinie auf Warnungs Aktivitäten anzuwenden, und werden verwendet, um die Dauer der Richtlinie nach der Aktivierung zu bestimmen. Die maximale Richtlinien Grenze beträgt fünf aktive Richtlinien gleichzeitig. Sie können jedoch weitere Richtlinien konfigurieren und Richtlinien bei Bedarf aktivieren und deaktivieren.

## <a name="policy-dashboard"></a>Richtlinien Dashboard

Mit dem **Richtlinien Dashboard** können Sie schnell die Richtlinien in Ihrer Organisation und den aktuellen Status von Warnungen anzeigen, die den einzelnen Richtlinien zugeordnet sind.

- **Richtlinienname**: der Name, der der Richtlinie im Richtlinien-Assistenten zugewiesen ist.
- **Aktive Warnungen**: die Anzahl der aktiven Warnungen für jede Richtlinie.
- **Bestätigte Warnungen**: die Gesamtzahl der Warnungen, die in den Fällen aus der Richtlinie in den letzten 365 Tagen geführt wurden.
- **Bei Warnungen ausgeführte Aktionen**: die Gesamtzahl der Benachrichtigungen, die in den letzten 365 Tagen bestätigt oder entlassen wurden.
- **Richtlinien Effektivität**: der Prozentsatz, der durch die insgesamt bestätigten Warnungen dividiert durch die Gesamtanzahl der Aktionen, die für Warnungen vorgenommen wurden, bestimmt wird (die Summe der Warnungen, die im letzten Jahr bestätigt oder entlassen wurden).
- **Aktiv**: der Status des Falls, entweder *Ja* oder *Nein*.

![Richtlinien-Dashboard für Insider Risikomanagement](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Richtlinienvorlagen

Vorlagen für Insider Risikomanagement sind vordefinierte Richtlinienbedingungen, mit denen die Typen von Risikoindikatoren definiert werden, die von einer Richtlinie überwacht werden. Für jede Richtlinie muss eine Vorlage im Richtlinien Erstellungs-Assistenten zugewiesen sein, bevor die Richtlinie erstellt wird. Wenn Sie eine neue Insider Risiko Richtlinie erstellen, wählen Sie eine der folgenden Vorlagen aus.

### <a name="departing-employee-data-theft"></a>Verabschiedung von Datendiebstahl durch Mitarbeiter

Wenn Mitarbeiter Ihre Organisation verlassen, gibt es bestimmte Risikoindikatoren, die typischerweise mit dem Datendiebstahl durch abfliegende Mitarbeiter verbunden sind. Diese Richtlinienvorlage priorisiert diese Indikatoren und konzentriert die Erkennung und Warnungen auf diesen Risikobereich. Datendiebstahl für abwesende Mitarbeiter kann das Herunterladen von Dateien aus SharePoint Online, das Kopieren von Dateien auf tragbare Geräte wie USB-Laufwerke, das Drucken von Dateien und das Kopieren von Daten in persönliche Cloud-Messaging-und-Speicherdienste in der Nähe ihrer Arbeits Rücktritts-und Endtermine umfassen. In dieser Vorlage werden die Risikoindikatoren für diese Aktivitäten sowie deren Korrelation mit dem Status der Mitarbeitereinstellung priorisiert.

>[!IMPORTANT]
>Bei Verwendung dieser Vorlage müssen Sie einen Microsoft 365-HR-Connector für die regelmäßige Einfuhr von Rücktritts-und Kündigungsdatum-Informationen für Mitarbeiter in Ihrer Organisation konfigurieren. Lesen Sie den Abschnitt [Importieren von Daten mit dem HR-Connector](import-hr-data.md) , um Schritt-für-Schritt-Anleitungen zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation zu erhalten.

### <a name="data-leaks"></a>Datenlecks

Das Schützen von Daten und das verhindern von Datenverlusten stellt für die meisten Organisationen eine ständige Herausforderung dar, insbesondere mit dem schnellen Wachstum neuer Daten, die von Mitarbeitern, Geräten und Diensten erstellt wurden. Mitarbeiter sind befugt, Informationen über Dienste und Geräte hinweg zu erstellen, zu speichern und gemeinsam zu nutzen, mit denen die Verwaltung von Datenverlusten immer komplexer und schwieriger wird. Datenlecks können eine versehentliche Übernutzung von Informationen außerhalb Ihrer Organisation oder Datendiebstahl mit böswilliger Absicht umfassen. In Verbindung mit einer zugewiesenen DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) priorisiert diese Vorlage die Echtzeiterkennung verdächtiger SharePoint Online von Daten Downloads, die Datei-und Ordnerfreigabe, das Kopieren von Dateien auf tragbare Geräte wie USB-Laufwerke, das Drucken von Dateien und das Kopieren von Daten in persönliche Cloud-Messaging-und-Speicherdienste.

Bei Verwendung von **Datenlecks** -Vorlage müssen Sie eine DLP-Richtlinie zuweisen, um Indikatoren in der Insider Risiko Richtlinie für Warnungen mit hohem Schweregrad in Ihrer Organisation auszulösen. Wenn eine DLP-Richtlinienregel zum Office 365 Überwachungsprotokoll hinzugefügt wird, wird eine Warnung mit hohem Schweregrad generiert, und die mit dieser Vorlage erstellten Insider Risikorichtlinien untersuchen automatisch die DLP-Warnung mit hohem Schweregrad. Wenn die Warnung einen in-Scope-Benutzer enthält, der in der Insider Risiko Richtlinie definiert ist, wird die Warnung von der Insider Risiko Richtlinie als neue Warnung verarbeitet und einem Insider risikoschweregrad und Risikobewertung zugeordnet. Diese Warnung kann im Rahmen des Insider Risk Management-Workflows ausgewertet und bei Bedarf zu einem Insider Risikomanagement-Fall hinzugefügt werden.

Beachten Sie beim Erstellen oder Ändern von DLP-Richtlinien für die Verwendung mit Richtlinien für Insider-Risikomanagement die folgenden Richtlinien:

- Priorisieren von Daten zugrunde liegenden Ereignissen und selektives Zuweisen von **Vorfalls Berichten** zu *hohen* Einstellungen beim Konfigurieren von Regeln in ihren DLP-Richtlinien. Wenn Sie beispielsweise vertrauliche Dokumente an einen bekannten Mitbewerber senden möchten, sollte dies ein *hohes* Ereignis bei der Warnstufe für die Alarmstufe sein. Die übermäßige Zuweisung der *hohen* Ebene in den **Vorfall Berichts** Einstellungen in anderen DLP-Richtlinien Regeln kann das Rauschen im Warnungs Workflow für Insider Risken verbessern und es erschweren, dass Ihre Daten Ermittler und Analysten diese Warnungen ordnungsgemäß auswerten. Durch die Zuweisung *hoher* Warnungsstufen zu Blockierungs Aktivitäten in DLP-Richtlinien ist es beispielsweise schwieriger, wirklich riskante Benutzerverhalten und-Aktivitäten zu bewerten.
- Stellen Sie sicher, dass Sie die in-Scope-Benutzer in den DLP-und Insider Risk Management-Richtlinien verstehen und ordnungsgemäß konfigurieren. Nur Benutzer, die im Rahmen von Richtlinien für das Insider Risikomanagement mithilfe der **Datenlecks** -Vorlage definiert sind, werden mit hohem Schweregrad DLP-Richtlinienwarnungen verarbeitet. Darüber hinaus werden nur Benutzer, die in einer Regel für eine DLP-Warnung mit hohem Schweregrad in einem Bereich definiert sind, von der Richtlinie für den Umgang mit Insider Risiken untersucht. Es ist wichtig, dass Sie nicht unwissentlich in ihrer DLP-und Insider-Risiko Richtlinie auf widersprüchliche Weise Benutzer in einem Bereich konfigurieren.

     Wenn beispielsweise ihre DLP-Richtlinien Regeln nur auf Benutzer im Vertriebsteam beschränkt sind und die Insider Risiko Richtlinie, die aus der **Datenlecks** -Vorlage erstellt wurde, alle Benutzer als in-Scope definiert hat, verarbeitet die Insider Risiko Richtlinie nur DLP-Warnungen mit hohem Schweregrad für die Benutzer im Verkaufsteam. Die Insider Risiko Richtlinie erhält keine DLP-Warnungen hoher Priorität für Benutzer, die verarbeitet werden sollen, die in den DLP-Regeln in diesem Beispiel nicht definiert sind. Wenn Ihre Richtlinie für das Insider Risikomanagement, die aus der **Datenlecks** -Vorlage erstellt wurde, auf die Benutzer im Vertriebsteam beschränkt ist und die zugewiesene DLP-Richtlinie auf alle Benutzer beschränkt ist, verarbeitet die Insider Risiko Richtlinie nur DLP-Warnungen mit hohem Schweregrad für Mitglieder des Vertriebsteams. Die Richtlinie für das Insider Risikomanagement ignoriert die DLP-Warnungen mit hohem Schweregrad für alle Benutzer, die sich nicht im Verkaufs Team befinden.

- Stellen Sie sicher, dass die Einstellung " **vorfallberichte** " in der für diese Insider Risikomanagement-Vorlage verwendeten DLP-Richtlinie für Warnungen mit *hohem* Schweregrad konfiguriert ist. Der *hohe* Schweregrad ist der auslösende Indikator, und Warnungen im Hinblick auf Insider Risikomanagement werden nicht aus Regeln in DLP-Richtlinien generiert, wobei das Feld **vorfallberichte** auf *niedrig* oder *Mittel*festgelegt ist.

    ![Warnungseinstellung für DLP-Richtlinie](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Wenn Sie eine neue DLP-Richtlinie mithilfe der integrierten Vorlagen erstellen, müssen Sie die Option **Advanced DLP Rules erstellen oder anpassen** auswählen, um die Einstellung **vorfallberichte** für den *hohen* Schweregrad zu konfigurieren.

Für jede Richtlinie für Insider-Risikomanagement, die aus der **Datenlecks** -Vorlage erstellt wurde, kann nur eine DLP-Richtlinie zugewiesen werden. Wenn Sie über mehr als eine DLP-Richtlinie verfügen, für die Warnungen mit hohem Schweregrad von einer Richtlinie für den Umgang mit Insider Risiken verarbeitet werden sollen, müssen Sie pro DLP-Richtlinie eine separate Richtlinie für Insider-Risikomanagement erstellen.

Eine schrittweise Anleitung zum Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie unter [erstellen, testen und Optimieren eines DLP-Richtlinien](create-test-tune-dlp-policy.md) Themas.

### <a name="offensive-language-in-email"></a>Anstößige Sprache in e-Mail

Das erkennen und ergreifen von Aktionen zur Vorbeugung gegen beleidigendes und missbräuchliches Verhalten ist eine wichtige Komponente zur Vermeidung von Risiken. Integrierte beleidigende sprach Klassifizierungen in Microsoft 365 können gesendete e-Mail-Nachrichten von Exchange Online Postfächern in Ihrer Organisation für unterschiedliche Arten von Kompatibilitätsproblemen überprüfen. Diese Klassifizierungen verwenden eine Kombination aus künstlicher Intelligenz und Stichwörtern, um die Sprache in e-Mails zu identifizieren, die gegen Belästigungs Richtlinien verstoßen dürften. Verwenden Sie diese Vorlage, um schnell eine Richtlinie zu erstellen, die diese Klassifizierungen verwendet, um e-Mail-Nachrichteninhalte, die als missbräuchlich oder beleidigend eingestuft werden können, automatisch zu erkennen. Für das Insider Risikomanagement werden Klassifizierungen verwendet, die gesendete e-Mail-Nachrichten für anstößige Sprachen nach englischen sprach Begriffen und-Ansichten scannen.

## <a name="policy-settings"></a>Richtlinieneinstellungen

Die Einstellungen für Insider Risiken gelten unabhängig von der Vorlage, die Sie beim Erstellen einer Richtlinie ausgewählt haben, für alle Insider Risiko-Verwaltungsrichtlinien. Einstellungen werden mit dem Steuerelement " **Insider Risk Settings** " konfiguriert, das sich oben auf allen Registerkarten für das Insider Risikomanagement befindet. Mit diesen Einstellungen werden Datenschutz, Indikatoren, Überwachungsfenster und intelligente Erkennungen gesteuert.

### <a name="privacy"></a>Datenschutz

Der Schutz der Privatsphäre von Benutzern mit Richtlinien Übereinstimmungen ist wichtig und kann zur Förderung der Objektivität bei Daten Ermittlungs-und Analyse Überprüfungen für Insider Risikowarnungen beitragen. Für Benutzer, denen eine Insider Risiko Richtlinie zugeordnet ist, können Sie eine der folgenden Einstellungen auswählen:

- **Anonyme Versionen von**Benutzernamen anzeigen: Benutzernamen werden anonymisiert, um zu verhindern, dass Administratoren, Daten Ermittler und Prüfer sehen, wem die Richtlinienwarnungen zugeordnet sind. Beispielsweise würde ein Benutzer "Grace Taylor" mit einem randomisierten Pseudonym wie "AnonIS8-988" in allen Bereichen der Insider Risikomanagement-Erfahrung angezeigt. Wenn Sie diese Einstellung auswählen, werden alle Benutzer mit aktuellen und früheren Richtlinien Übereinstimmungen anonymisiert und gilt für alle Richtlinien. Benutzerprofilinformationen in der Warnung zu Insider Risiken und Fall Details sind nicht verfügbar, wenn diese Option ausgewählt wird. Benutzernamen werden jedoch beim Hinzufügen neuer Benutzer zu vorhandenen Richtlinien oder beim Zuweisen von Benutzern zu neuen Richtlinien angezeigt. Wenn Sie diese Einstellung deaktivieren, werden Benutzernamen für alle Benutzer angezeigt, die aktuelle oder vergangene Richtlinien Übereinstimmungen aufweisen.
- **Anonyme Versionen von Benutzernamen nicht anzeigen**: Benutzernamen werden für alle aktuellen und letzten Richtlinien Übereinstimmungen für Warnungen und Fälle angezeigt. Benutzerprofilinformationen (Name, Titel, Alias und Organisation oder Abteilung) werden für den Benutzer für alle Warnungen und Fälle im Insider Risikomanagement angezeigt.

### <a name="indicators"></a>Indikatoren

Vorlagen für Insider Risikorichtlinien definieren Sie die Art der Risiko Aktivitäten, die Sie erkennen und untersuchen möchten. Jede Richtlinienvorlage basiert auf spezifischen Indikatoren, die bestimmten Risiko Aktivitäten entsprechen, und Warnungen werden durch Richtlinien ausgelöst, wenn Benutzeraktivitäten im Zusammenhang mit diesen Indikatoren ausführen. In einigen Fällen möchten Sie möglicherweise die Indikatoren einschränken, die auf Insider Risikorichtlinien in Ihrer Organisation angewendet werden. Sie können die Indikatoren für bestimmte Bereiche deaktivieren, indem Sie Sie von allen Insider Risikorichtlinien deaktivieren.

Um die Indikatoren zu definieren, die in allen Richtlinien aktiviert sind, navigieren Sie zu Indikatoren für **Insider Risiko Einstellungen**,  >  **Indicators** und wählen Sie ein oder mehrere Indikatoren aus. Die auf der Seite **indikatoreneinstellungen** ausgewählten Indikatoren können beim Erstellen oder Bearbeiten einer Insider Risiko Richtlinie im Richtlinien-Assistenten nicht individuell konfiguriert werden.

>[!IMPORTANT]
>Um Warnungen für riskante Aktivitäten zu erhalten, die in ihren Richtlinien definiert sind, müssen Sie vor dem Konfigurieren einer Insider Risiko Richtlinie ein oder mehrere Indikatoren auswählen.

### <a name="policy-timeframes"></a>Richtlinienzeit Rahmen

Mithilfe von Richtlinienzeit Rahmen können Sie vergangene und zukünftige Überprüfungszeiten definieren, die ausgelöst werden, nachdem die Richtlinien Übereinstimmungen basierend auf Ereignissen und Aktivitäten für die Richtlinien für Insider-Risikomanagement-Vorlagen ausgeführt wurden. Je nach der ausgewählten Richtlinienvorlage stehen die folgenden Richtlinienzeit Rahmen zur Verfügung:

- **Aktivierungsfenster**: für alle Richtlinienvorlagen verfügbar ist das *Aktivierungsfenster* die festgelegte Anzahl von Tagen, die das Fenster **nach** einem auslösendem Ereignis aktiviert. Das Fenster wird für 1 bis 30 Tage aktiviert, nachdem für einen Benutzer, der der Richtlinie zugewiesen ist, ein auslösendes Ereignis auftritt. Sie haben beispielsweise eine Richtlinie für Insider-Risikoverwaltung konfiguriert und das *Aktivierungsfenster* auf 30 Tage festgelegt. Seit dem Konfigurieren der Richtlinie sind mehrere Monate vergangen, und für einen der in der Richtlinie enthaltenen Benutzer tritt ein auslösendes Ereignis ein. Das auslösende Ereignis aktiviert das *Aktivierungsfenster* , und die Richtlinie ist für diesen Benutzer 30 Tage lang aktiv, nachdem das auslösende Ereignis aufgetreten ist.
- **Erkennung der letzten Aktivität**: für alle Richtlinienvorlagen verfügbar, ist die *vergangene Aktivitätserkennung* die festgelegte Anzahl von Tagen, die das Fenster **vor** einem auslösendem Ereignis aktiviert. Das Fenster wird für 0 bis 180 Tage aktiviert, bevor ein auslösendes Ereignis für einen Benutzer eintritt, der der Richtlinie zugewiesen ist. Sie haben beispielsweise eine Richtlinie für Insider-Risikomanagement konfiguriert und die *bisherige Aktivitätserkennung* auf 90 Tage festgelegt. Seit dem Konfigurieren der Richtlinie sind mehrere Monate vergangen, und für einen der in der Richtlinie enthaltenen Benutzer tritt ein auslösendes Ereignis ein. Das auslösende Ereignis aktiviert die *bisherige Aktivitätserkennung* , und die Richtlinie sammelt historische Aktivitäten für diesen Benutzer 90 Tage vor dem auslösendem Ereignis.

### <a name="intelligent-detections"></a>Intelligente Erkennungen

Mithilfe intelligenter Erkennungseinstellungen können Sie die Verarbeitung von Erkennungen riskanter Aktivitäten für Warnungen optimieren. Unter bestimmten Umständen müssen Sie möglicherweise Dateitypen definieren, die ignoriert werden sollen, oder Sie möchten einen Erkennungs Grad für Dateien erzwingen, um eine minimale Leiste für Warnungen zu definieren. Wenn Sie Richtlinien für anstößige Sprachen verwenden, müssen Sie möglicherweise die Erkennungsempfindlichkeit erweitern oder verringern, um die Menge der gemeldeten Richtlinien Übereinstimmungen zu steuern. Verwenden Sie diese Einstellungen, um das gesamte Warnungs Volumen, die Dateitypen Ausschlüsse, die Grenzwerte für Datei Volumina und die Empfindlichkeit bei der Erkennung anstößiger Sprachen zu steuern.

#### <a name="anomaly-detections"></a>Anomale Erkennungen

Zu den anomalen Erkennungen gehören Einstellungen für Dateitypen Ausschlüsse und Datei Volumenbeschränkungen.

- **Dateitypen Ausschlüsse**: um bestimmte Dateitypen aus allen Richtlinien für die Insider Risikoverwaltung auszuschließen, geben Sie die Dateitypen Erweiterungen durch Kommas getrennt ein. Wenn Sie beispielsweise bestimmte Typen von Musikdateien aus Richtlinien Übereinstimmungen ausschließen möchten, können Sie im Feld **Dateitypen Ausschlüsse** *AAC, MP3, WAV, WMA* eingeben. Dateien mit diesen Erweiterungen würden von allen Insider Risk Management-Richtlinien ignoriert.
- **Grenzwert für Datei Volumenbegrenzung**: um eine mindestdateimenge zu definieren, bevor Aktivitäts Warnungen in Insider Risikorichtlinien gemeldet werden, geben Sie die Anzahl der Dateien ein. Beispielsweise würden Sie "10" eingeben, wenn Sie keine Insider Risikowarnungen generieren möchten, wenn ein Benutzer 10 Dateien oder weniger herunterlädt, selbst wenn die Richtlinien diese Aktivität als Anomalie ansehen.

#### <a name="offensive-language-detections"></a>Anstößige Spracherkennungen

Wählen Sie eine der folgenden Einstellungen aus, um die Empfindlichkeit der Klassifizierung für anstößige Sprachen für Richtlinien mithilfe der Vorlage *anstößige Sprache in e-Mail* anzupassen:

- **Niedrig**: die niedrigste Empfindlichkeitsstufe mit dem breitesten Bereich für Erkennungs Offensive Sprache und Sentiment. Die Wahrscheinlichkeit, dass falsch positive Ergebnisse für anstößige Sprachen übereinstimmen, wird erhöht.
- **Mittel**: die Empfindlichkeitsstufe auf mittlerer Ebene mit einem ausgewogenen Bereich für Erkennungs Offensive Sprache und Sentiment. Die Wahrscheinlichkeit, dass falsch positive Ergebnisse für anstößige Sprachen übereinstimmen, ist durchschnittlich.
- **High**: die höchste Empfindlichkeitsstufe mit einem engen Bereich für Erkennungs Offensive Sprache und Sentiment. Die Wahrscheinlichkeit, dass falsch positive Ergebnisse für anstößige Sprachen übereinstimmen, ist gering.

#### <a name="alert-volume"></a>Warnungs Lautstärke

Benutzeraktivitäten, die von Insider Risikorichtlinien erkannt werden, werden mit einem bestimmten Risikoergebnis versehen, das wiederum den Warnungsschweregrad (niedrig, Mittel, hoch) bestimmt. Standardmäßig wird eine bestimmte Anzahl von Warnungen mit niedrigem, mittlerem und hohem Schweregrad generiert, aber Sie können die Lautstärke entsprechend Ihren Anforderungen erweitern oder verringern. Wählen Sie eine der folgenden Einstellungen aus, um die Anzahl der Warnungen für alle Richtlinien für das Insider Risikomanagement anzupassen:

- **Weniger Warnungen**: Sie sehen alle Warnungen mit hohem Schweregrad, weniger Warnungen mittlerer Dringlichkeit und keine niedrigen Schweregrade. Diese Einstellungsebene bedeutet, dass Sie möglicherweise einige echte positive Ergebnisse verpassen.
- **Standard Volume**: alle Warnungen mit hohem Schweregrad und eine ausgewogene Anzahl mittlerer und niedriger Dringlichkeits Warnungen werden angezeigt.
- **Weitere Warnungen**: Es werden alle Warnungen bei mittlerer und hoher Dringlichkeit sowie Warnungen mit niedrigem Schweregrad angezeigt. Diese Einstellungsebene kann zu mehr falsch positiven Ergebnissen führen.

## <a name="create-a-new-policy"></a>Erstellen einer neuen Richtlinie

Um eine neue Richtlinie für das Insider Risikomanagement zu erstellen, verwenden Sie den Richtlinien-Assistenten in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine neue Richtlinie zu erstellen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie **Richtlinie erstellen** aus, um den richtlinienassistenten zu öffnen
3. Füllen Sie auf der Seite **Ihre Richtlinie benennen und eine Vorlage auswählen** die folgenden Felder aus:
    - **Name (erforderlich)**: Geben Sie einen Anzeigenamen für die Richtlinie ein.
    - **Description (optional)**: Geben Sie eine Beschreibung für die Richtlinie ein.
    - **Richtlinienvorlage auswählen (erforderlich)**: Wählen Sie eine der [Richtlinienvorlagen](insider-risk-management-policies.md#policy-templates) aus, um die Arten von Risikoindikatoren zu definieren, die von der Richtlinie überwacht werden.

    >[!IMPORTANT]
    >Wenn Sie die *Datenlecks* -Vorlage auswählen, müssen Sie mindestens eine DLP-Richtlinie konfigurieren, die Sie später im Assistenten zuweisen. Wenn Sie die *Datendiebstahl Vorlage "departing Employee* " auswählen, müssen Sie den HR-Connector so konfigurieren, dass er die vollständigen Signal Erkennungsfunktionen der Richtlinienvorlage verwendet.

4. Wählen Sie **weiter** aus, um fortzufahren.
5. Wählen Sie auf der Seite **Benutzer und Gruppen** auswählen die Option **Benutzer oder Gruppen** auswählen aus, um festzulegen, welche Benutzer in der Richtlinie enthalten sind, oder aktivieren Sie das Kontrollkästchen **alle Benutzer und e-Mail-aktivierten Gruppen** . Wählen Sie **weiter** aus, um fortzufahren.
6. Auf der Seite geben Sie an, **welche Inhalte priorisiert werden sollen (optional)** , können Sie der erkannten Aktivität höhere Risikobewertungen zuweisen, basierend darauf, wo sich der zugehörige Inhalt befindet, welche vertraulichen Informationen enthalten sind und welche Vertraulichkeits Bezeichnungen angewendet werden:
    - SharePoint-Websites: Wählen Sie **SharePoint-Websites** auswählen, und wählen Sie die SharePoint-Organisationen aus, die Sie priorisieren möchten. Beispiel: *"group1@contoso.SharePoint.com/Sites/Group1"*.
    - Typ vertraulicher Informationen: Wählen Sie **vertrauliche Informationstypen** auswählen aus, und wählen Sie die Vertraulichkeits Typen aus, die Sie priorisieren möchten. Beispiel: *"US Bank Account Number"* und *"Kreditkartennummer"*.
    - Vertraulichkeits Bezeichnungen: Wählen Sie **Vertraulichkeits Bezeichnungen** auswählen aus, und wählen Sie die Beschriftungen aus, die Sie priorisieren möchten. Beispiel: *"vertraulich"* und *"geheim"*.
7. Wählen Sie **weiter** aus, um fortzufahren.
8. Auf der Seite mit den **Warnungsindikatoren** werden die Indikatoren angezeigt, die Sie auf der Seite Indikatoren für **Insider Risiko Einstellungen**definiert haben  >  **Indicators** . Wenn Sie die *Datenlecks* -Vorlage zu Beginn des Assistenten ausgewählt haben, müssen Sie in der Dropdownliste DLP- **Richtlinie** eine DLP-Richtlinie auswählen.
9. Auf der Seite **Überwachungsfenster auswählen** werden die Bedingungen für das [Überwachungsfenster](insider-risk-management-policies.md#policy-timeframes) für die Richtlinie angezeigt, die Sie in den Einstellungen für Insider Risiken konfiguriert haben. Wenn Sie die Datendiebstahl Richtlinienvorlage für *departs-Mitarbeiter* ausgewählt haben, können Sie das Kontrollkästchen nach *Beendigung der Aktivität nach Abschluss überprüfen* aktivieren, um die Aktivität nach dem vom Microsoft 365 HR-Connector importierten Beendigungsdatum zu erkennen.
10. Wählen Sie **weiter** aus, um fortzufahren.
11. Überprüfen Sie auf der Seite **überprüfen** die Einstellungen, die Sie für die Richtlinie ausgewählt haben. Wählen Sie **Bearbeiten** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **senden** aus, um die Richtlinie zu erstellen und zu aktivieren.

## <a name="update-a-policy"></a>Aktualisieren einer Richtlinie

Um eine vorhandene Richtlinie für das Insider Risikomanagement zu aktualisieren, verwenden Sie den Richtlinien-Assistenten in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine vorhandene Richtlinie zu verwalten:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie im Richtlinien Dashboard die Richtlinie aus, die Sie verwalten möchten.
3. Wählen Sie auf der Seite Richtliniendetails die Option **Richtlinie bearbeiten** aus.
4. Im Richtlinien-Assistenten können Sie die folgenden Felder nicht bearbeiten:
    - **Name**: der Anzeigename für die Richtlinie
    - **Wählen Sie**Textbuch: die Vorlage, mit der die Typen von Risikoindikatoren definiert werden, die von der Richtlinie überwacht werden.
5. Geben Sie eine neue Beschreibung für die Richtlinie in das Feld **Beschreibung** ein. Wählen Sie **weiter** aus, um fortzufahren.
6. Wählen Sie auf der Seite **Benutzer und Gruppen** auswählen die Option **Benutzer oder Gruppen** auswählen aus, um festzulegen, welche Benutzer in der Richtlinie enthalten sind, oder aktivieren Sie das Kontrollkästchen **alle Benutzer und e-Mail-aktivierten Gruppen** . Wählen Sie **weiter** aus, um fortzufahren
7. Aktualisieren Sie auf der Seite **Geben Sie an, welche Inhalte priorisiert werden sollen (optional)** die Quellen an, um Prioritäten für riskante Benutzeraktivitäten zu setzen:
    - SharePoint-Websites: Wählen Sie **SharePoint-Websites** auswählen, und wählen Sie die SharePoint-Organisationen aus, die Sie priorisieren möchten. Beispiel: *"group1@contoso.SharePoint.com/Sites/Group1"*.
    - Typ vertraulicher Informationen: Wählen Sie **vertrauliche Informationstypen** auswählen aus, und wählen Sie die Vertraulichkeits Typen aus, die Sie priorisieren möchten. Beispiel: *"US Bank Account Number"* und *"Kreditkartennummer"*.
    - Vertraulichkeits Bezeichnungen: Wählen Sie **Vertraulichkeits Bezeichnungen** auswählen aus, und wählen Sie die Beschriftungen aus, die Sie priorisieren möchten. Beispiel: *"vertraulich"* und *"geheim"*.
8. Wählen Sie **weiter** aus, um fortzufahren.
9. Auf der Seite mit den **Warnungsindikatoren** werden die Indikatoren angezeigt, die Sie auf der Seite Indikatoren für **Insider Risiko Einstellungen**definiert haben  >  **Indicators** . Wenn Sie die *Datenlecks* -Vorlage zu Beginn des Assistenten ausgewählt haben, müssen Sie in der Dropdownliste DLP- **Richtlinie** eine DLP-Richtlinie auswählen.
10. Auf der Seite **Überwachungsfenster auswählen** werden die Bedingungen für das [Überwachungsfenster](insider-risk-management-policies.md#policy-timeframes) für die Richtlinie angezeigt, die Sie in den Einstellungen für Insider Risiken konfiguriert haben. Wenn Sie die Datendiebstahl Richtlinienvorlage für *departs-Mitarbeiter* ausgewählt haben, können Sie das Kontrollkästchen nach *Beendigung der Aktivität nach Abschluss überprüfen* aktivieren, um die Aktivität nach dem vom Microsoft 365 HR-Connector importierten Beendigungsdatum zu erkennen.
11. Überprüfen Sie auf der Seite **überprüfen** die Einstellungen, die Sie für die Richtlinie ausgewählt haben. Wählen Sie **Bearbeiten** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **Submit** to Update aus, und aktivieren Sie die Änderungen in der Richtlinie.

## <a name="delete-a-policy"></a>Löschen einer Richtlinie

>[!NOTE]
>Durch das Löschen einer Richtlinie werden keine aktiven oder archivierten Warnungen gelöscht, die aus der Richtlinie generiert wurden.

Führen Sie die folgenden Schritte aus, um eine vorhandene Richtlinie für Insider-Risikomanagement zu löschen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie im Richtlinien Dashboard die Richtlinie aus, die Sie verwalten möchten.
3. Wählen Sie auf der Dashboard-Symbolleiste **Löschen** aus.
4. Wählen Sie im Dialogfeld **Löschen** die Option **Ja** aus, um die Richtlinie zu löschen, oder klicken Sie auf **Abbrechen** , um das Dialogfeld zu schließen.
