---
title: Einstellungen für das Insider Risikomanagement
description: Informationen zu Einstellungen für das Insider Risikomanagement in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: c98c0081d95da19e79db03dc4b4fdb823a14e42c
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377270"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Erste Schritte mit Einstellungen für das Insider Risikomanagement

Die Einstellungen für das Insider Risikomanagement gelten für alle Richtlinien für das Insider Risikomanagement, unabhängig von der Vorlage, die Sie beim Erstellen einer Richtlinie ausgewählt haben. Die Einstellungen werden über das Steuerelement **Insider-Risiko-Einstellungen** konfiguriert, das sich oben auf allen Registerkarten des Insider-Risikomanagements befindet. Diese Einstellungen steuern Richtlinienkomponenten für die folgenden Bereiche:

- Datenschutz
- Indikatoren
- Richtlinien Zeitlinien
- Intelligente Erkennungen
- Warnungen exportieren (Vorschau)
- Prioritäts Benutzergruppen (Vorschau)
- Vorrangige physische Objekte (Vorschau)
- Power Automation Flows (Vorschau)
- Microsoft Teams (Vorschau)

Bevor Sie mit dem Erstellen von Richtlinien für die Verwaltung von Insider Risiken beginnen, müssen Sie sich mit diesen Einstellungen vertraut machen und die für die Compliance-Anforderungen am besten geeigneten Einstellungsstufen für Ihre Organisation auswählen.

## <a name="privacy"></a>Datenschutz

Der Schutz der Privatsphäre von Benutzern, die über Richtlinienübereinstimmungen verfügen, ist wichtig und kann zur Förderung der Objektivität bei der Überprüfung von Daten und Analysen im Hinblick auf Insider-Risikowarnungen beitragen. Für Benutzer, denen eine Insider Risiko Richtlinie zugeordnet ist, können Sie eine der folgenden Einstellungen auswählen:

- **Anonyme Versionen von Benutzernamen anzeigen**: die Namen der Benutzer werden anonymisiert, um zu verhindern, dass Administratoren, Daten Ermittler und Prüfer sehen, wem die Richtlinienwarnungen zugeordnet sind. Zum Beispiel würde ein Benutzer "Grace Taylor" mit einem randomisierten Pseudonym wie "AnonIS8-988" in allen Bereichen des Insider-Risikomanagements erscheinen. Wenn Sie diese Einstellung wählen, werden alle Benutzer mit aktuellen und früheren Richtlinienübereinstimmungen anonymisiert und gelten für alle Richtlinien. Benutzerprofilinformationen in der Warnung zu Insider Risiken und Fall Details sind nicht verfügbar, wenn diese Option ausgewählt wird. Benutzernamen werden jedoch beim Hinzufügen neuer Benutzer zu vorhandenen Richtlinien oder beim Zuweisen von Benutzern zu neuen Richtlinien angezeigt. Wenn Sie diese Einstellung deaktivieren, werden Benutzernamen für alle Benutzer angezeigt, die aktuelle oder vergangene Richtlinien Übereinstimmungen aufweisen.
- **Anonyme Versionen von Benutzernamen nicht anzeigen**: Benutzernamen werden für alle aktuellen und letzten Richtlinien Übereinstimmungen für Warnungen und Fälle angezeigt. Benutzerprofilinformationen (Name, Titel, Alias und Organisation oder Abteilung) werden für den Benutzer für alle Warnungen und Fälle im Insider Risikomanagement angezeigt.

![Datenschutzeinstellungen für das Insider Risikomanagement](../media/insider-risk-settings-privacy.png)

## <a name="indicators"></a>Indikatoren

Vorlagen für Insider Risikorichtlinien definieren Sie die Art der Risiko Aktivitäten, die Sie erkennen und untersuchen möchten. Jede Richtlinienvorlage basiert auf spezifischen Indikatoren, die bestimmten Auslösern und Risiko Aktivitäten entsprechen. Alle Indikatoren sind standardmäßig deaktiviert, und Sie müssen ein oder mehrere Richtlinien Indikatoren auswählen, bevor Sie eine Richtlinie für das Risikomanagement für Insider konfigurieren.

Warnungen werden durch Richtlinien ausgelöst, wenn Benutzeraktivitäten im Zusammenhang mit Richtlinien Indikatoren ausführen, die einen erforderlichen Schwellenwert erfüllen. Das Insider Risikomanagement verwendet zwei Arten von Indikatoren:

- **Auslösende Ereignisse**: Ereignisse, die bestimmen, ob ein Benutzer für eine Richtlinie zur Verwaltung von Insider Risiken aktiv ist. Wenn ein Benutzer einer Insider Risiko-Verwaltungsrichtlinie hinzugefügt wird und kein auslösendes Ereignis vorliegt, wird die Benutzeraktivität nicht von der Richtlinie ausgewertet. Beispielsweise wird Benutzer a einer Richtlinie hinzugefügt, die aus der Richtlinienvorlage " *Datendiebstahl durch Benutzer* " erstellt wurde, und die Richtlinie und der Microsoft 365 HR-Connector sind ordnungsgemäß konfiguriert. Bis für Benutzer a ein vom HR-Connector gemeldetes Terminierungs Datum vorliegt, werden die Aktivitäten des Benutzers a nicht von dieser Richtlinie für Insider-Risikomanagement für Risiken ausgewertet. Ein weiteres Beispiel für ein auslösendes Ereignis ist, wenn ein Benutzer über eine DLP-Richtlinien Warnung mit *hohem* Schweregrad verfügt, wenn *Datenlecks* -Richtlinien verwendet werden.
- **Richtlinien Indikatoren**: Indikatoren, die in Richtlinien für das Insider Risikomanagement verwendet werden, um eine Risikobewertung für einen in-Scope-Benutzer zu ermitteln. Diese Richtlinien Indikatoren werden nur aktiviert, nachdem ein auslösendes Ereignis für einen Benutzer auftritt. Einige Beispiele für Richtlinien Indikatoren sind, wenn ein Benutzerdaten in persönliche Cloud-Speicherdienste oder tragbare Speichergeräte kopiert oder wenn ein Benutzer interne Dateien und Ordner für nicht autorisierte externe Personen freigibt.

Richtlinien Indikatoren werden in die folgenden Bereiche segmentiert. Sie können die Indikatoren zum Aktivieren und Anpassen von Indikator Ereignis Grenzwerten für jede Indikator Ebene beim Erstellen einer Insider Risiko Richtlinie auswählen:

- **Office-Indikatoren**: dazu gehören Richtlinien Indikatoren für SharePoint-Websites, Teams und e-Mail-Nachrichten.
- **Geräte Indikatoren**: dazu gehören Richtlinien Indikatoren für Aktivitäten wie das Freigeben von Dateien über das Netzwerk oder mit Geräten. Indikatoren umfassen Aktivitäten mit Microsoft Office Dateien,. CSV-Dateien und. PDF-Dateien. Wenn Sie **Geräte Indikatoren**auswählen, wird die Aktivität nur für Geräte mit Windows 10 Build 1809 oder höher verarbeitet. Weitere Informationen zum Konfigurieren von Geräten für die Integration in Insider Risiken finden Sie unter [Erste Schritte mit Endpoint DLP](endpoint-dlp-getting-started.md).
- **Indikator für Sicherheitsrichtlinienverletzungen**: dazu zählen Indikatoren von Microsoft Defender ATP im Zusammenhang mit der Installation nicht genehmigter oder böswilliger Software oder der Umgehung von Sicherheitskontrollen. Um Warnungen im Insider Risk Management zu erhalten, müssen Sie über eine aktive Microsoft Defender ATP-Lizenz und die Integration aktivierter Insider Risiken verfügen. Weitere Informationen zum Konfigurieren von Microsoft Defender ATP für die Integration von Insider Risikomanagement finden Sie unter [configure Advanced Features in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).
- **Risiko Bewertungs Verstärker**: dazu gehören das Erhöhen der Risikobewertung für ungewöhnliche Aktivitäten oder vergangene Richtlinienverletzungen. Durch Aktivieren der Risiko Bewertungs Steigerung erhöhen Sie die Risikobewertung und die Wahrscheinlichkeit, dass Warnungen für diese Arten von Aktivitäten aktiviert werden. Risiko Bewertungs Verstärker können nur ausgewählt werden, wenn mindestens ein Indikator oben ausgewählt ist.

![Einstellungen für Insider Risikomanagement-Indikatoren](../media/insider-risk-settings-indicators.png)

In einigen Fällen möchten Sie möglicherweise die Insider-Risikorichtlinien Indikatoren einschränken, die auf Insider Risikorichtlinien in Ihrer Organisation angewendet werden. Sie können die Richtlinien Indikatoren für bestimmte Bereiche deaktivieren, indem Sie Sie von allen Insider Risikorichtlinien deaktivieren. Das Auslösen von Ereignissen kann für Vorlagen für Insider Risikorichtlinien nicht geändert werden.

Wenn Sie die in allen Insider Risikorichtlinien aktivierten Insider-Risikorichtlinien Indikatoren definieren möchten, navigieren Sie zu Indikatoren für **Insider Risiko Einstellungen**,  >  **Indicators** und wählen Sie ein oder mehrere Richtlinien Indikatoren aus. Die auf der Seite indikatoreneinstellungen ausgewählten Indikatoren können beim Erstellen oder Bearbeiten einer Insider Risiko Richtlinie im Richtlinien-Assistenten nicht individuell konfiguriert werden.

>[!NOTE]
>Es kann mehrere Stunden dauern, bis neue manuell hinzugefügte Benutzer im **Dashboard Benutzer**angezeigt werden. Aktivitäten für die letzten 90 Tage für diese Benutzer können bis zu 24 Stunden dauern, bis Sie angezeigt werden. Um Aktivitäten für manuell hinzugefügte Benutzer anzuzeigen, wählen Sie den Benutzer im **Dashboard Benutzer** aus, und öffnen Sie die Registerkarte **Benutzeraktivität** im Detailbereich.

### <a name="indicator-level-settings-preview"></a>Einstellungen auf Indikator Ebene (Vorschau)

Beim Erstellen einer Richtlinie im Richtlinien-Assistenten können Sie konfigurieren, wie sich die tägliche Anzahl von Risikoereignissen auf die Risikobewertung für Insider Risikowarnungen auswirken soll. Mithilfe dieser Indikatoreinstellungen können Sie steuern, wie sich die Anzahl der Vorkommen von Risikoereignissen in Ihrer Organisation auf das Risikoergebnis und damit auf den zugeordneten Warnungsschweregrad für diese Ereignisse auswirken sollte. Wenn Sie möchten, können Sie auch die Standardschwellenwerte für Ereignisse beibehalten, die von Microsoft für alle aktivierten Indikatoren empfohlen werden.

Sie möchten beispielsweise SharePoint-Indikatoren in den Richtlinieneinstellungen für Insider Risiken aktivieren und benutzerdefinierte Schwellenwerte für SharePoint-Ereignisse festlegen, wenn Sie Indikatoren für eine neue Richtlinie für Insider-Risiko *Datenlecks* konfigurieren. Während Sie im Assistenten für Insider Risikorichtlinien die drei verschiedenen täglichen Ereignisebenen für jeden SharePoint-Indikator konfigurieren, um die Risikobewertung für Warnungen zu beeinflussen, die diesen Ereignissen zugeordnet sind.

![Einstellungen für benutzerdefinierte Kennzahlen für Insider Risk Management](../media/insider-risk-custom-indicators.png)

Für die erste tägliche Ereignisebene legen Sie den Schwellenwert bei *10 oder mehr Ereignissen pro Tag* fest, um eine geringere Auswirkung auf das Risikoergebnis für die Ereignisse, *20 oder mehr Ereignisse pro Tag* für eine mittlere Auswirkung auf das Risikoergebnis für die Ereignisse und *30 oder mehr Ereignisse pro Tag* einen höheren Einfluss auf die Risikobewertung für die Ereignisse zu haben. Diese Einstellungen bedeuten effektiv:

- Wenn es 1-9 SharePoint-Ereignisse gibt, die nach dem Auslösen des Ereignisses stattfinden, werden die Risikobewertungen minimal beeinträchtigt und würden tendenziell keine Warnung generieren.
- Wenn es 10-19 SharePoint-Ereignisse gibt, die nach einem auslösendem Ereignis stattfinden, ist das Risikoergebnis inhärent niedriger, und die Warnungsschweregrade tendieren zu einer niedrigen Ebene.
- Wenn es 20-29 SharePoint-Ereignisse gibt, die nach einem Triggern stattfinden, ist das Risikoergebnis inhärent höher, und die Warnungsschweregrade tendieren zu einer mittleren Ebene.
- Wenn 30 oder mehr SharePoint-Ereignisse nach einem Triggern stattfinden, ist das Risikoergebnis inhärent höher, und der Warnungsschweregrad würde sich tendenziell auf einem hohen Niveau befinden.

## <a name="policy-timeframes"></a>Zeitrahmen für Richtlinien

Mit Hilfe von Zeitrahmen für Richtlinien können Sie vergangene und zukünftige Überprüfungszeiträume definieren, die nach Richtlinienübereinstimmungen auf der Grundlage von Ereignissen und Aktivitäten für die Richtlinienvorlagen zum Insider-Risikomanagement ausgelöst werden. Je nach der ausgewählten Richtlinienvorlage stehen die folgenden Richtlinienzeit Rahmen zur Verfügung:

- **Aktivierungsfenster**: für alle Richtlinienvorlagen verfügbar ist das *Aktivierungsfenster* die festgelegte Anzahl von Tagen, die das Fenster **nach** einem auslösendem Ereignis aktiviert. Das Fenster wird für 1 bis 30 Tage aktiviert, nachdem für einen Benutzer, der der Richtlinie zugewiesen ist, ein auslösendes Ereignis auftritt. Sie haben beispielsweise eine Richtlinie für Insider-Risikoverwaltung konfiguriert und das *Aktivierungsfenster* auf 30 Tage festgelegt. Seit der Konfiguration der Richtlinie sind mehrere Monate vergangen, und für einen der in der Richtlinie enthaltenen Benutzer tritt ein auslösendes Ereignis ein. Das auslösende Ereignis aktiviert das *Aktivierungsfenster* , und die Richtlinie ist für diesen Benutzer 30 Tage lang aktiv, nachdem das auslösende Ereignis aufgetreten ist.
- **Erkennung der letzten Aktivität**: für alle Richtlinienvorlagen verfügbar, ist die *vergangene Aktivitätserkennung* die festgelegte Anzahl von Tagen, die das Fenster **vor** einem auslösendem Ereignis aktiviert. Das Fenster wird für 0 bis 180 Tage aktiviert, bevor ein auslösendes Ereignis für einen Benutzer eintritt, der der Richtlinie zugewiesen ist. Sie haben beispielsweise eine Richtlinie für Insider-Risikomanagement konfiguriert und die *bisherige Aktivitätserkennung* auf 90 Tage festgelegt. Seit der Konfiguration der Richtlinie sind mehrere Monate vergangen, und für einen der in der Richtlinie enthaltenen Benutzer tritt ein auslösendes Ereignis ein. Das auslösende Ereignis aktiviert die *bisherige Aktivitätserkennung* , und die Richtlinie sammelt historische Aktivitäten für diesen Benutzer 90 Tage vor dem auslösendem Ereignis.

![Zeitrahmen Einstellungen für das Insider Risikomanagement](../media/insider-risk-settings-timeframes.png)

## <a name="intelligent-detections"></a>Intelligente Erkennungen

Mithilfe intelligenter Erkennungseinstellungen können Sie die Verarbeitung von Erkennungen riskanter Aktivitäten für Warnungen optimieren. Unter bestimmten Umständen müssen Sie möglicherweise Dateitypen definieren, die ignoriert werden sollen, oder Sie möchten einen Erkennungs Grad für Dateien erzwingen, um eine minimale Leiste für Warnungen zu definieren. Wenn Sie anstößige Sprachrichtlinien verwenden, müssen Sie möglicherweise die Erkennungsempfindlichkeit erhöhen oder verringern, um die Anzahl der gemeldeten Richtlinienübereinstimmungen zu kontrollieren. Verwenden Sie diese Einstellungen, um das gesamte Warnungs Volumen, die Dateitypen Ausschlüsse, die Grenzwerte für Datei Volumina und die Empfindlichkeit bei der Erkennung anstößiger Sprachen zu steuern.

![Einstellungen für intelligente Erkennungen im Insider-Risikomanagement](../media/insider-risk-settings-detections.png)

### <a name="anomaly-detections"></a>Anomalie-Erkennungen

Zu den Anomalie-Erkennungen gehören Einstellungen für Dateityp-Ausschlüsse und Dateivolumen-Begrenzungen.

- **Dateitypen Ausschlüsse**: um bestimmte Dateitypen aus allen Richtlinien für die Insider Risikoverwaltung auszuschließen, geben Sie die Dateitypen Erweiterungen durch Kommas getrennt ein. Um beispielsweise bestimmte Arten von Musikdateien von den Richtlinienübereinstimmungen auszuschließen, können Sie *AAC, MP3, WAV, WMA* in das Feld **Dateityp-Ausschlüsse** eingeben. Dateien mit diesen Erweiterungen würden von allen Richtlinien zum Insider-Risikomanagement ignoriert werden.
- **Grenzwert für Datei volumenüberschreitung**: um eine mindestdateimenge zu definieren, bevor Aktivitäts Warnungen in Insider Risikorichtlinien gemeldet werden, geben Sie die Anzahl der Dateien ein. Beispielsweise würden Sie "10" eingeben, wenn Sie keine Insider Risikowarnungen generieren möchten, wenn ein Benutzer 10 Dateien oder weniger herunterlädt, selbst wenn die Richtlinien diese Aktivität als Anomalie ansehen.

### <a name="offensive-language-detections"></a>Erkennung anstößiger Sprache

>[!IMPORTANT]
>Ab dem 16. Oktober 2020 können Sie mit dieser Vorlage keine Richtlinien mehr erstellen. Alle aktiven Richtlinien, die diese Vorlage verwenden, funktionieren, bis Sie im Januar 2021 endgültig entfernt werden. Wir verwerfen die integrierte Klassifizierung der offensiven Sprache, die diese Vorlage unterstützt, da Sie eine hohe Anzahl falsch positiver Ergebnisse erzeugt. Um Risiko Probleme für anstößige Sprachen zu beheben, empfehlen wir die Verwendung von Microsoft 365 [Communication Compliance](communication-compliance.md) Policies. Weitere Informationen zu integrierten Klassifizierungen finden Sie unter [Erste Schritte mit Schulungs Klassifizierern](classifier-get-started-with.md).

Um die Empfindlichkeit des Klassifizierers für anstößige Sprache für Richtlinien anzupassen, welche die Vorlage *Anstößige Sprache in E-Mail* verwenden, wählen Sie eine der folgenden Einstellungen aus:

- **Niedrig**: die niedrigste Empfindlichkeitsstufe mit dem breitesten Bereich für Erkennungs Offensive Sprache und Sentiment. Die Wahrscheinlichkeit falsch positiver Ergebnisse bei anstößigen Sprachübereinstimmungen ist erhöht.
- **Mittel**: die Empfindlichkeitsstufe auf mittlerer Ebene mit einem ausgewogenen Bereich für Erkennungs Offensive Sprache und Sentiment. Die Wahrscheinlichkeit falsch positiver Ergebnisse bei anstößigen Sprachübereinstimmungen ist durchschnittlich.
- **High**: die höchste Empfindlichkeitsstufe mit einem engen Bereich für Erkennungs Offensive Sprache und Sentiment. Die Wahrscheinlichkeit falsch positiver Ergebnisse bei anstößigen Sprachübereinstimmungen ist niedrig.

### <a name="alert-volume"></a>Warnungs Lautstärke

Benutzeraktivitäten, die von Insider Risikorichtlinien erkannt werden, werden mit einem bestimmten Risikoergebnis versehen, das wiederum den Warnungsschweregrad (niedrig, Mittel, hoch) bestimmt. Standardmäßig wird eine bestimmte Anzahl von Warnungen mit niedrigem, mittlerem und hohem Schweregrad generiert, aber Sie können die Lautstärke entsprechend Ihren Anforderungen erweitern oder verringern. Wählen Sie eine der folgenden Einstellungen aus, um die Anzahl der Warnungen für alle Richtlinien für das Insider Risikomanagement anzupassen:

- **Weniger Warnungen**: Sie sehen alle Warnungen mit hohem Schweregrad, weniger Warnungen mittlerer Dringlichkeit und keine niedrigen Schweregrade. Diese Einstellungsebene bedeutet, dass Sie möglicherweise einige echte positive Ergebnisse verpassen.
- **Standard Volume**: alle Warnungen mit hohem Schweregrad und eine ausgewogene Anzahl mittlerer und niedriger Dringlichkeits Warnungen werden angezeigt.
- **Weitere Warnungen**: Es werden alle Warnungen bei mittlerer und hoher Dringlichkeit sowie Warnungen mit niedrigem Schweregrad angezeigt. Diese Einstellungsebene kann zu mehr falsch positiven Ergebnissen führen.

### <a name="microsoft-defender-advanced-threat-protection-preview"></a>Microsoft Defender Advanced Threat Protection (Vorschau)

[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) (ATP) ist eine Enterprise-Endpunkt-Sicherheitsplattform, die Unternehmensnetzwerken dabei helfen soll, erweiterte Bedrohungen zu verhindern, zu erkennen, zu untersuchen und darauf zu reagieren. Um eine bessere Sichtbarkeit der Sicherheitsverletzung in Ihrer Organisation zu erhalten, können Sie Microsoft Defender ATP-Warnungen für Aktivitäten importieren und Filtern, die in Richtlinien verwendet werden, die aus Richtlinienvorlagen für Sicherheitsverstöße bei Insider Risk Management erstellt wurden.

Je nach den Signaltypen, für die Sie sich interessieren, können Sie Warnungen in das Insider Risikomanagement basierend auf dem Status "Microsoft Defender ATP Alert Triage" importieren. Sie können einen oder mehrere der folgenden Status der Warnungs Auswahl in den globalen Einstellungen zum Importieren definieren:

- Unbekannt
- Neu
- In Arbeit
- Gelöst

Benachrichtigungen von Microsoft Defender ATP werden täglich importiert. Je nach ausgewähltem Status werden möglicherweise mehrere Benutzeraktivitäten für dieselbe Warnung angezeigt, wie sich der Status der Triage in Microsoft Defender ATP ändert.

Wenn Sie beispielsweise " *neu*", " *in Bearbeitung*" und "für diese Einstellung *aufgelöst* " auswählen, wird beim Generieren einer Microsoft Defender ATP-Warnung und dem Status " *neu*" eine anfängliche Warnungs Aktivität für den Benutzer in "Insider Risk" importiert. Wenn sich der Status der Microsoft Defender ATP-Triage in " *in Progress*" ändert, wird eine zweite Aktivität für diese Warnung in "Insider Risiko" für den Benutzer importiert. Wenn der endgültige Status der Microsoft Defender-ATP-Triage für *aufgelöst* festgelegt ist, wird eine dritte Aktivität für diese Warnung in Insider Risiko für den Benutzer importiert. Mit dieser Funktion können Ermittler dem Fortschritt der Microsoft Defender ATP-Warnungen folgern und die Sichtbarkeitsstufe auswählen, die ihre Untersuchung erfordert.

>[!IMPORTANT]
>Sie müssen Microsoft Defender ATP in Ihrer Organisation konfigurieren und Microsoft Defender ATP for Insider Risk Management Integration in das Defender Security Center aktivieren, um Warnungen zu Sicherheitsverletzungen zu importieren. Weitere Informationen zum Konfigurieren von Microsoft Defender ATP für die Integration von Insider Risikomanagement finden Sie unter [configure Advanced Features in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="domains-preview"></a>Domänen (Vorschau)

Domäneneinstellungen unterstützen Sie bei der Definition von Risikostufen für die Kommunikation mit bestimmten Domänen. Diese Kommunikation umfasst das Freigeben von Dateien, e-Mail-Nachrichten oder das Herunterladen von Inhalten. Durch die Angabe von Domänen in diesen Einstellungen können Sie die Risikobewertung für Aktivitäten, die mit diesen Domänen stattfinden, vergrössern oder verringern. Um beispielsweise contoso.com und Sales.wingtiptoys.com als zugelassene Domänen anzugeben, geben Sie "contoso.com Sales.wingtiptoys.com" in das Feld **zugelassene Domänen** ein.

Für jede der folgenden Domäneneinstellungen können Sie bis zu 500 Domänen eingeben:

- Nicht **zugelassene Domänen:** Durch die Angabe unzulässiger Domänen werden Aktivitäten, die mit diesen Domänen stattfinden, mit *höheren* Risikobewertungen versehen.
- **Zugelassene Domänen:** Durch die Angabe zulässiger Domänen in Einstellungen haben Aktivitäten, die mit diesen Domänen stattfinden, *niedrigere* Risikobewertungen und werden entsprechend behandelt, wie die interne Organisations Aktivität behandelt wird. Beispielsweise werden e-Mail-Aktivitäten für diese Domänen ähnlich wie bei der Analyse interner e-Mail-Aktivitäten analysiert.
- **Drittanbieter Domänen:** Drittanbieter Domänen sind Domänen, die für geschäftliche Zwecke in Ihrer Organisation verwendet werden, und vertrauliche Inhalte können über diese Standorte hinweg gespeichert werden. Durch die Angabe einer Drittanbieter Domäne können Sie Benachrichtigungen für riskante Aktivitäten in diesen Domänen erhalten.

## <a name="export-alerts-preview"></a>Warnungen exportieren (Vorschau)

Warnungsinformationen für das Insider Risikomanagement können über das [API-Schema der Office 365 Verwaltungsaktivität](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#security-and-compliance-alerts-schema)für Siem-Dienste (Security Information and Event Management) exportierbar sein. Sie können die Office 365-Verwaltungs Aktivitäts-APIs verwenden, um Warnungsinformationen in andere Anwendungen zu exportieren, die Ihre Organisation zum Verwalten oder Aggregieren von Insider Risikoinformationen verwenden kann.

So verwenden Sie die APIs zum Überprüfen von Warnungsinformationen für Insider Risiken:

1. Aktivieren der API-Unterstützung für die Office 365 Verwaltungsaktivität im **Insider Risk Management**  >  **Settings**-  >  **Export**. Diese Einstellung ist standardmäßig für Ihre Microsoft 365-Organisation deaktiviert.
2. Filtern Sie die allgemeinen Office 365 Überwachungsaktivitäten nach *SecurityComplianceAlerts*.
3. Filtern Sie *SecurityComplianceAlerts* nach der Kategorie *InsiderRiskManagement* .

![Insider Risk Management-Export Benachrichtigungseinstellungen](../media/insider-risk-settings-export.png)

Warnungsinformationen enthalten Informationen aus dem Sicherheits-und Konformitäts Warn Schema und dem allgemeinen Schema der Office 365-Verwaltungs Aktivitäts-API.

Die folgenden Felder und Werte werden für Warnungen beim Insider Risikomanagement für das Sicherheits & Compliance-Warnungs Schema exportiert:

| **Warnungsparameter** | **Beschreibung** |
|:------------------|:----------------|
| AlertType | Der Typ der Warnung ist *Custom*.  |
| AlertId | Die GUID der Warnung. Warnungen beim Insider-Risikomanagement sind änderbar. Wenn sich der Warnungsstatus ändert, wird ein neues Protokoll mit der gleichen Warnungs-Nr generiert. Diese Warnungs-Nr kann zum Korrelieren von Updates für eine Warnung verwendet werden. |
| Kategorie | Die Kategorie der Warnung lautet *InsiderRiskManagement*. Diese Kategorie kann verwendet werden, um von diesen Warnungen von anderen Sicherheits &-Konformitätswarnungen zu unterscheiden. |
| Kommentare | Standardkommentare für die Warnung. Werte sind *neue Warnung* (protokolliert beim Erstellen einer Warnung) und *Benachrichtigungs Aktualisierung* (protokolliert, wenn ein Update für eine Warnung vorliegt). Verwenden Sie die Alert-Funktion, um Updates für eine Warnung zu korrelieren. |
| Daten | Die Daten für die Warnung umfassen die eindeutige Benutzer-ID, den Benutzerprinzipalnamen und Datum und Uhrzeit (UTC), wenn der Benutzer in einer Richtlinie ausgelöst wurde. |
| Name | Richtlinienname für die Richtlinie für das Insider Risikomanagement, die die Warnung generiert hat. |
| PolicyId | Die GUID der Richtlinie für das Insider Risikomanagement, die die Warnung ausgelöst hat. |
| Severity | Der Schweregrad der Warnung. Die Werte sind *hoch*, *Mittel*oder *niedrig*. |
| Quelle | Die Quelle der Warnung. Der Wert ist *Office 365 Sicherheit & Compliance*. |
| Status | Der Status der Warnung. Werte sind *aktiv* (*Bedarf Überprüfung* im Insider Risiko), *Ermittlungen* (im Hinblick auf Insider Risiken*bestätigt* ), *aufgelöst* (im Hinblick auf Insider Risiken*aufgelöst* ), *entlassen* (im Hinblick auf Insider Risiken*entlassen* ). |
| Version | Die Version des Sicherheits-und Konformitäts Warnungs Schemas. |

Die folgenden Felder und Werte werden für Warnungen beim Insider Risikomanagement für das [allgemeine Schema der Office 365-Verwaltungs Aktivitäts-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)exportiert.

- UserId
- Id
- RecordType
- CreationTime
- Vorgang
- OrganizationId
- UserType
- UserKey

## <a name="priority-user-groups-preview"></a>Prioritäts Benutzergruppen (Vorschau)

Benutzer in Ihrer Organisation können je nach Position, Zugriffsebene auf vertrauliche Informationen oder Risikoverlauf unterschiedliche Risikostufen aufweisen. Das Priorisieren der Untersuchung und Bewertung der Aktivitäten dieser Benutzer kann Ihnen dabei helfen, Sie auf mögliche Risiken aufmerksam zu machen, die für Ihre Organisation möglicherweise höhere Auswirkungen haben. Priority User Groups in Insider Risk Management helfen bei der Definition der Benutzer in Ihrer Organisation, die eine genauere Überprüfung und eine sensiblere Risikobewertung benötigen. In Verbindung mit den *Sicherheitsrichtlinienverletzungen durch Prioritäts* Benutzer und *Datenverlusten nach Prioritäts Benutzer* Richtlinienvorlagen haben Benutzer, die einer Priorität-Benutzergruppe hinzugefügt wurden, eine erhöhte Wahrscheinlichkeit für Insider Risikowarnungen und Warnungen mit einem höheren Schweregrad.

![Priorität der Benutzergruppeneinstellungen für das Insider-Risikomanagement](../media/insider-risk-settings-priority-users.png)

Sie müssen beispielsweise vor Datenverlusten für ein streng vertrauliches Projekt schützen, in dem Benutzer Zugriff auf vertrauliche Informationen haben. Sie können die Benutzergruppe für *vertrauliche Projekt* *Benutzer* Priority für Benutzer in Ihrer Organisation erstellen, die an diesem Projekt arbeiten. Mit dem Richtlinien-Assistenten und der Richtlinienvorlage *Datenverlust nach Priorität Benutzer* erstellen Sie eine neue Richtlinie und weisen der Richtlinie die Gruppe vertrauliche Benutzer mit Priorität *Project Users* zu. Aktivitäten, die von der Richtlinie für Mitglieder der Benutzergruppe " *vertrauliche Projekt Benutzer* Priorität" untersucht werden, reagieren empfindlicher auf Risiken, und Aktivitäten von diesen Benutzern werden eher eine Warnung generieren und Warnungen mit einem höheren Schweregrad aufweisen.

### <a name="create-a-priority-user-group"></a>Erstellen einer Priorität-Benutzergruppe

Um eine neue Priorität-Benutzergruppe zu erstellen, verwenden Sie Einstellungs Steuerelemente in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center. Zum Erstellen einer Priority-Benutzergruppe müssen Sie Mitglied der Administrator-Rollengruppe " *Insider Risk Management* *" oder "Insider Risk Management"* sein.

Führen Sie die folgenden Schritte aus, um eine Priorität-Benutzergruppe zu erstellen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie **Einstellungen für Insider Risiken**aus.
2. Auswählen der Registerkarte " **Prioritäts Benutzergruppen** "
3. Wählen Sie auf der Registerkarte **Prioritäts Benutzergruppen** die Option **Priorität-Benutzergruppe erstellen** aus, um den Gruppen Erstellungs-Assistenten zu starten.
4. Füllen Sie auf der Seite **Gruppe definieren** die folgenden Felder aus:
    - **Name (erforderlich)**: Geben Sie einen Anzeigenamen für die Benutzergruppe Priority ein. Sie können den Namen der Prioritäts Benutzergruppe nicht ändern, nachdem Sie den Assistenten abgeschlossen haben.
    - **Description (optional)**: Geben Sie eine Beschreibung für die Prioritäts Benutzergruppe ein.
5. Wählen Sie **weiter** aus, um fortzufahren.
6. Wählen Sie auf der Seite **Mitglieder** auswählen die Option zu durchsuchende **Mitglieder** auswählen aus, und wählen Sie aus, welche e-Mail-aktivierten Benutzerkonten in der Gruppe enthalten sind, oder aktivieren Sie das Kontrollkästchen **Alles auswählen** , um der Gruppe alle Benutzer in Ihrer Organisation hinzuzufügen. Wählen Sie **Hinzufügen** zum Fortfahren oder **Abbrechen** aus, um zu schließen, ohne Benutzer zur Gruppe hinzuzufügen.
7. Wählen Sie **weiter** aus, um fortzufahren.
8. Überprüfen Sie auf der Seite **überprüfen** die Einstellungen, die Sie für die Benutzergruppe Priorität ausgewählt haben. Wählen Sie **Bearbeiten** aus, um einen der Gruppenwerte zu ändern, oder wählen Sie **senden** aus, um die Benutzergruppe Priorität zu erstellen und zu aktivieren.
9. Wählen Sie auf der Seite Bestätigung die Option **Fertig** aus, um den Assistenten zu beenden.

### <a name="update-a-priority-user-group"></a>Aktualisieren einer Priorität-Benutzergruppe

Um eine vorhandene Priorität-Benutzergruppe zu aktualisieren, verwenden Sie Einstellungs Steuerelemente in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center. Zum Aktualisieren einer Prioritäts Benutzergruppe müssen Sie Mitglied der Administrator-Rollengruppe " *Insider Risk Management* *" oder "Insider Risk Management"* sein.

Führen Sie die folgenden Schritte aus, um eine Priorität-Benutzergruppe zu bearbeiten:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie **Einstellungen für Insider Risiken**aus.
2. Auswählen der Registerkarte " **Prioritäts Benutzergruppen** "
3. Wählen Sie die Benutzergruppe Priorität aus, die Sie bearbeiten möchten, und klicken Sie dann auf **Gruppe bearbeiten**.
4. Aktualisieren Sie auf der Seite **Gruppe definieren** bei Bedarf das Feld Beschreibung. Der Name der Prioritäts Benutzergruppe kann nicht aktualisiert werden. Wählen Sie **weiter** aus, um fortzufahren.
5. Fügen Sie auf der Seite **Mitglieder auswählen** mithilfe des Steuerelements **Choose** Members neue Mitglieder zu der Gruppe hinzu. Wenn Sie einen Benutzer aus der Gruppe entfernen möchten, wählen Sie das X neben dem Benutzer aus, den Sie entfernen möchten. Wählen Sie **weiter** aus, um fortzufahren.
6. Überprüfen Sie auf der Seite **überprüfen** die Updateeinstellungen, die Sie für die Benutzergruppe Priorität ausgewählt haben. Wählen Sie **Bearbeiten** aus, um einen der Gruppenwerte zu ändern, oder wählen Sie **Absenden** aus, um die Benutzergruppe Priorität zu aktualisieren.
7. Wählen Sie auf der Seite Bestätigung die Option **Fertig** aus, um den Assistenten zu beenden.

### <a name="delete-a-priority-user-group"></a>Löschen einer Benutzergruppe mit Priorität

Um eine vorhandene Priorität-Benutzergruppe zu löschen, verwenden Sie Einstellungs Steuerelemente in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center. Zum Löschen einer Prioritäts Benutzergruppe müssen Sie Mitglied der Administrator-Rollengruppe " *Insider Risk Management* *" oder "Insider Risk Management"* sein.

>[!IMPORTANT]
>Wenn Sie eine Prioritäts Benutzergruppe löschen, wird Sie aus jeder aktiven Richtlinie entfernt, der Sie zugewiesen ist. Wenn Sie eine Prioritäts Benutzergruppe löschen, die einer aktiven Richtlinie zugewiesen ist, enthält die Richtlinie keine Benutzer in einem Bereich, die sich effektiv im Leerlauf befinden und keine Warnungen erstellen können.

Führen Sie die folgenden Schritte aus, um eine Priorität-Benutzergruppe zu löschen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie **Einstellungen für Insider Risiken**aus.
2. Auswählen der Registerkarte " **Prioritäts Benutzergruppen** "
3. Wählen Sie die Benutzergruppe Priorität aus, die Sie bearbeiten möchten, und wählen Sie im Menü Dashboard die Option **Löschen** aus.
4. Wählen Sie im Dialogfeld **Löschen** die Option **Ja** aus, um die Benutzergruppe Priorität zu löschen, oder wählen Sie **Abbrechen** aus, um zum Dashboard zurückzukehren.

## <a name="priority-physical-assets-preview"></a>Vorrangige physische Objekte (Vorschau)

Das Identifizieren des Zugriffs auf physische Ressourcen mit Priorität und das korrelieren der Zugriffsaktivitäten mit Benutzerereignissen ist eine wichtige Komponente ihrer Konformitäts Infrastruktur. Diese physischen Objekte stellen prioritätspositionen in Ihrer Organisation dar, beispielsweise Firmengebäude, Rechenzentren oder Serverräume. Insider Risiko Aktivitäten können mit Benutzern verbunden sein, die ungewöhnliche Stunden arbeiten, den Zugriff auf diese nicht autorisierten vertraulichen oder sicheren Bereiche sowie Anforderungen für den Zugriff auf allgemeine Bereiche ohne legitime Anforderungen.

Wenn die Priorität "physische Objekte" aktiviert ist und der [physische Badges Data Connector](import-physical-badging-data.md) konfiguriert ist, integriert das Insider Risikomanagement Signale von ihren physikalischen Steuerungs-und Zugriffs Systemen mit anderen Benutzer Risiko Aktivitäten. Durch die Untersuchung von Verhaltensmustern für physikalische Zugriffssysteme und die Korrelation dieser Aktivitäten mit anderen Insider Risikoereignissen kann das Insider Risikomanagement den Compliance-Ermittlern und Analysten helfen, fundiertere Antwort Entscheidungen für Warnungen zu treffen. Der Zugriff auf vorrangige physische Objekte wird bewertet und in Einblicken unterschiedlich aus dem Zugriff auf nicht vorrangige Ressourcen ermittelt.

Beispielsweise verfügt Ihre Organisation über ein Badges-System für Benutzer, die den physischen Zugriff auf normale Arbeits-und vertrauliche Projektbereiche überwacht und genehmigt. Mehrere Benutzer arbeiten an einem vertraulichen Projekt, und diese Benutzer kehren zu anderen Bereichen Ihrer Organisation zurück, wenn das Projekt abgeschlossen ist. Wenn das vertrauliche Projekt abgeschlossen ist, möchten Sie sicherstellen, dass die Projektarbeit vertraulich bleibt und dass der Zugriff auf die Projektbereiche streng gesteuert wird.

Sie können den physischen Badges-Daten Konnektor in Microsoft 365 zum Importieren von Zugriffsinformationen aus Ihrem physischen Badges-System und zum Angeben von vorrangigen physischen Objekten im Insider-Risikomanagement aktivieren. Wenn Sie Informationen aus Ihrem Badges-System importieren und physische Zugriffsinformationen mit anderen Risiko Aktivitäten korrelieren, die im Insider Risikomanagement identifiziert werden, stellen Sie fest, dass einer der Benutzer im Projekt nach normaler Arbeitszeit auf die Projektbüros zugreift und auch große Datenmengen aus dem normalen Arbeitsbereich in einen persönlichen Cloud-Speicherdienst exportiert. Diese physische Zugriffs Aktivität im Zusammenhang mit der Online Aktivität kann auf mögliche Datendiebstahl-und Compliance-Ermittler hindeuten, und Analysten können geeignete Maßnahmen ergreifen, die von den Umständen für diesen Benutzer diktiert werden.

### <a name="configure-priority-physical-assets"></a>Konfigurieren von vorrangigen physischen Objekten

Zum Konfigurieren von vorrangigen physischen Objekten konfigurieren Sie den physischen Badges-Connector und verwenden Einstellungs Steuerelemente in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center. Zum Konfigurieren von vorrangigen physischen Objekten müssen Sie Mitglied der Administrator-Rollengruppe " *Insider Risk Management* *" oder "Insider Risk Management"* sein.

Führen Sie die folgenden Schritte aus, um vorrangige physische Objekte zu konfigurieren:

1. Befolgen Sie die Konfigurationsschritte für das Insider Risikomanagement im Artikel [Erste Schritte mit Insider-Risikomanagement](insider-risk-management-configure.md) . Stellen Sie in Schritt 3 sicher, dass Sie den physischen Badges-Connector konfigurieren.

    >[!IMPORTANT]
    >Damit Richtlinien für das Insider-Risiko-Management Signaldaten im Zusammenhang mit absteigenden und abgebrochenen Benutzern mit Ereignisdaten von ihren physikalischen Steuerungs-und Zugriffs Plattformen verwenden und korrelieren, müssen Sie auch den Microsoft 365 HR-Connector konfigurieren. Wenn Sie den physischen Badges-Connector aktivieren, ohne den Microsoft 365 HR-Connector zu aktivieren, verarbeiten die Richtlinien für den Umgang mit Insider-Risiken nur Ereignisse für den Zugriff auf den physischen Zugriff für Benutzer in Ihrer Organisation.

2. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie Einstellungen für die **Insider risk settings**  >  **Priorität physische Objekte**für Insider Risiken aus.
3. Auf der Seite " **physische Objekte mit Priorität** " können Sie entweder die physischen Objekt-IDs, die Sie überwachen möchten, manuell für die vom physischen Badges-Connector importierten Asset-Ereignisse hinzufügen oder importieren. CSV-Datei aller vom physischen Badges-Connector importierten physischen Objekt-IDs: a) wählen Sie zum manuellen Hinzufügen von physischen Ressourcen-IDs die Option " **physische Objekte hinzufügen**", geben Sie eine physische Objekt-ID ein, und wählen Sie dann **Hinzufügen**aus. Geben Sie zusätzliche physische Objekt-IDs ein, und wählen Sie dann **physische Objekte mit Priorität hinzufügen** aus, um alle eingegebenen Objekte zu speichern.
    b) So fügen Sie eine Liste physischer Objekt-IDs von einem hinzu. CSV-Datei, wählen Sie **Import Priority Physical Assets**. Wählen Sie im Dialogfeld Datei-Explorer die aus. CSV-Datei, die Sie importieren möchten, und wählen Sie dann **Öffnen**aus. Die physischen Objekt-IDs aus dem. CSV-Dateien werden der Liste hinzugefügt.
4. Navigieren Sie zur Registerkarte **Richtlinien Indikatoren** in Einstellungen.
5. Navigieren Sie auf der Seite **Richtlinien Indikatoren** zum Abschnitt **physikalische Zugriffs Indikatoren** , und aktivieren Sie das Kontrollkästchen für **physischen Zugriff nach Beendigung oder fehlgeschlagener Zugriff auf vertrauliches Objekt**.
6. Wählen Sie **Save** to configure and Exit aus.

### <a name="delete-a-priority-physical-asset"></a>Löschen eines physischen Objekts der Priorität

Um ein vorhandenes physisches Priority-Objekt zu löschen, verwenden Sie die Einstellungs Steuerelemente in der Lösung für das Insider Risikomanagement im Microsoft 365 Compliance Center. Zum Löschen eines physischen Objekts der Priorität müssen Sie Mitglied der Administrator-Rollengruppe "Insider Risk Management" oder "Insider Risk Management" sein.

>[!IMPORTANT]
>Wenn Sie ein physisches Objekt mit Priorität löschen, wird es aus der Untersuchung durch eine aktive Richtlinie entfernt, zu der es zuvor gehörte. Warnungen, die durch Aktivitäten generiert werden, die dem physischen Objekt der Priorität zugeordnet sind, werden nicht gelöscht.

Führen Sie die folgenden Schritte aus, um ein physisches Objekt der Priorität zu löschen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie Einstellungen für die **Insider risk settings**  >  **Priorität physische Objekte**für Insider Risiken aus.
2. Wählen Sie auf der Seite **physische Objekte mit Priorität** das Objekt aus, das Sie löschen möchten.
3. Wählen Sie im Menü Aktion die Option **Löschen** aus, um das Objekt zu löschen.

## <a name="power-automate-flows-preview"></a>Power Automation Flows (Vorschau)

[Microsoft Power Automation](https://docs.microsoft.com/power-automate/getting-started) ist ein Workflowdienst, der Aktionen zwischen Anwendungen und Diensten automatisiert. Durch die Verwendung von Flows aus Vorlagen oder manuell erstellt, können Sie allgemeine Aufgaben automatisieren, die mit diesen Anwendungen und Diensten verbunden sind. Wenn Sie Power Automation Flows für Insider Risk Management aktivieren, können Sie wichtige Aufgaben für Fälle und Benutzer automatisieren. Sie können Power-Automatisierungs Flüsse so konfigurieren, dass Benutzer-, Benachrichtigungs-und Fall Informationen abgerufen und diese Informationen für beteiligte und andere Anwendungen freigegeben werden, sowie zum Automatisieren von Aktionen im Insider Risikomanagement, beispielsweise für das Veröffentlichen von fallnotizen. Power Automation Flows gelten für Fälle und für jeden Benutzer im Bereich einer Richtlinie.

Kunden mit Microsoft 365-Abonnements, die das Insider Risikomanagement umfassen, benötigen keine zusätzlichen Power-Automatisierungs Lizenzen für die Verwendung der empfohlenen Insider Risk Management Power automatisieren-Vorlagen. Diese Vorlagen können angepasst werden, um Ihre Organisation zu unterstützen und Kern Szenarien für das Insider Risikomanagement zu behandeln. Wenn Sie sich für die Verwendung von Premium Power Automation-Funktionen in diesen Vorlagen entscheiden, eine benutzerdefinierte Vorlage mit dem Microsoft 365-Konformitäts-Konnektor erstellen oder Power automatisieren-Vorlagen für andere Kompatibilitäts Bereiche in Microsoft 365 verwenden, benötigen Sie möglicherweise zusätzliche Power automatisieren-Lizenzen.

Die folgenden Power-Automatisierungs Vorlagen werden für Kunden bereitgestellt, um die Prozessautomatisierung für Benutzer und Fälle des Insider Risikomanagements zu unterstützen:

- **Benutzer benachrichtigen, wenn Sie einer Insider Risiko Richtlinie hinzugefügt**werden: Diese Vorlage richtet sich an Organisationen mit internen Richtlinien, Datenschutz oder behördlichen Anforderungen, die Benutzern mitgeteilt werden müssen, wenn Sie den Richtlinien für Insider Risk Management unterliegen. Wenn dieser Datenfluss für einen Benutzer auf der Seite Benutzer konfiguriert und ausgewählt ist, werden Benutzern und deren Managern eine e-Mail-Nachricht gesendet, wenn der Benutzer einer Richtlinie für Insider-Risikomanagement hinzugefügt wird. Diese Vorlage unterstützt auch das Aktualisieren einer SharePoint-Liste, die auf einer SharePoint-Website gehostet wird, um Details zur Benachrichtigung wie Datum/Uhrzeit und Nachrichtenempfänger nachzuverfolgen. Wenn Sie die Benutzer in den **Datenschutzeinstellungen**anonymisieren möchten, funktionieren die aus dieser Vorlage erstellten Flows nicht wie beabsichtigt, damit der Benutzerdaten Schutz beibehalten wird. Power Automation Flows mit dieser Vorlage stehen im **benutzerdashboard**zur Verfügung.
- **Fordern Sie Informationen von HR oder Unternehmen über einen Benutzer in einem Insider Risikofall**an: Wenn Sie in einem Fall handeln, müssen Insider Risikoanalysten und Ermittler möglicherweise mit HR oder anderen Beteiligten zusammenarbeiten, um den Kontext der Fall Aktivitäten zu verstehen. Wenn dieser Ablauf konfiguriert und für einen Fall ausgewählt ist, senden Analysten und Prüfer eine e-Mail-Nachricht an die für diesen Ablauf konfigurierten HR-und Unternehmens Beteiligten. Jedem Empfänger wird eine Nachricht mit vorkonfigurierten oder anpassbaren Antwortoptionen gesendet. Wenn Empfänger eine Antwortoption auswählen, wird die Antwort als Fall Hinweis aufgezeichnet und enthält Informationen zu Empfänger-und Datum/Uhrzeit. Wenn Sie die Benutzer in den **Datenschutzeinstellungen**anonymisieren möchten, funktionieren die aus dieser Vorlage erstellten Flows nicht wie beabsichtigt, damit der Benutzerdaten Schutz beibehalten wird. Power Automation Flows mit dieser Vorlage stehen im **Cases-Dashboard**zur Verfügung.
- Benachrichtigungs **-Manager, wenn ein Benutzer eine Insider Risiko Warnung hat**: einige Organisationen benötigen möglicherweise eine sofortige Verwaltungs Benachrichtigung, wenn ein Benutzer über eine Warnung beim Insider Risikomanagement verfügt. Wenn dieser Ablauf konfiguriert und ausgewählt ist, wird dem Manager für den Fall Benutzer eine e-Mail-Nachricht mit den folgenden Informationen zu allen Fall Benachrichtigungen gesendet: 
    - Zutreffende Richtlinie für die Warnung
    - Datum/Uhrzeit der Warnung
    - Schweregrad der Warnung

    Der Flow aktualisiert automatisch die fallnotizen, dass die Nachricht gesendet wurde und dass der Fluss aktiviert wurde. Wenn Sie die Benutzer in den **Datenschutzeinstellungen**anonymisieren möchten, funktionieren die aus dieser Vorlage erstellten Flows nicht wie beabsichtigt, damit der Benutzerdaten Schutz beibehalten wird. Power Automation Flows mit dieser Vorlage stehen im **Cases-Dashboard**zur Verfügung.

- **Hinzufügen einer Kalender Erinnerung zur Nachverfolgung bei einem Insider Risikofall**: mit dieser Vorlage können Risikoprüfer und Analysten Kalendererinnerungen für Fälle zu Ihrem Office 365 Outlook-Kalender hinzufügen. Durch diesen Fluss wird verhindert, dass Benutzer den Workflow für den Insider Risikomanagement beenden oder aus dem Prozess für die Verarbeitung von Fällen und der Behandlung von veralteten Warnungen wechseln. Wenn dieser Fluss konfiguriert und ausgewählt ist, wird Office 365 Outlook-Kalender eine Erinnerung für den Benutzer hinzugefügt, der den Fluss ausführt. Power Automation Flows mit dieser Vorlage stehen im **Cases-Dashboard**zur Verfügung.

### <a name="create-a-power-automate-flow-from-insider-risk-management-template"></a>Erstellen eines Power-Automatisierungs Flusses aus der Vorlage für Insider Risikomanagement

Um einen Power-Automatisierungs Fluss aus einer empfohlenen Insider Risiko-Verwaltungs Vorlage zu erstellen, verwenden Sie die Einstellungs Steuerelemente in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center oder die Option **Power Automation Flow verwalten** aus dem **Automatisierungs** Steuerelement, wenn Sie direkt in den **Dashboards**für **Fälle** oder Benutzer arbeiten.

Zum Erstellen eines Power-Automatisierungs Flusses im Bereich "Einstellungen" müssen Sie Mitglied der Administrator-Rollengruppe " *Insider Risk Management* *" oder "Insider Risk Management"* sein. Sie müssen Mitglied mindestens einer Rollengruppe "Insider Risk Management" sein, um einen Strom Automatisierungs Fluss mit der Option **Power Automation** Flows verwalten zu erstellen.

Führen Sie die folgenden Schritte aus, um einen Power-Automatisierungs Fluss aus einer empfohlenen Insider Risiko-Verwaltungs Vorlage zu erstellen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)zu **Insider Risk Management** , und wählen Sie **interne Risiko Einstellungen**  >  **Power Automation Flows**aus. Sie können auch auf den Seiten **Dashboards** für **Fälle** oder Benutzer zugreifen, indem Sie die Option **automatisieren**der  >  **Verwaltung von Power Automation Flows**auswählen.
2. Wählen Sie auf der Seite **Power Automation Flows** eine empfohlene Vorlage aus den **Insider Risk Management-Vorlagen** aus, die Sie im Abschnitt auf der Seite mögen.
3. Der Flow listet die eingebetteten Verbindungen auf, die für den Fluss benötigt werden, und beachtet, wenn die Verbindungsstatus verfügbar sind. Aktualisieren Sie bei Bedarf alle Verbindungen, die nicht als verfügbar angezeigt werden. Wählen Sie **weiter**aus.
4. Standardmäßig sind die empfohlenen Flows mit den empfohlenen Insider Risk Management-und Microsoft 365-Dienst Datenfeldern vorkonfiguriert, die zum Abschließen der zugewiesenen Aufgabe für den Fluss erforderlich sind. Passen Sie bei Bedarf die Fluss Komponenten mithilfe des Steuerelements " **Erweiterte Optionen anzeigen** " und Konfigurieren der verfügbaren Eigenschaften für die Fluss Komponente an.
5. Fügen Sie bei Bedarf zusätzliche Schritte zum Ablauf hinzu, indem Sie die Schaltfläche **neuer Schritt** auswählen. In den meisten Fällen sollte dies für die empfohlenen Standardvorlagen nicht erforderlich sein.
6. Wählen Sie **Entwurf speichern** aus, um den Fluss zur weiteren Konfiguration zu speichern, oder wählen Sie **Speichern** aus, um die Konfiguration für den Fluss abzuschließen.
7. Wählen Sie **Schließen** aus, um zur Seite **Power Automation Flow** zurückzukehren. Die neue Vorlage wird als Fluss auf den Registerkarten **meine Flüsse** aufgeführt und wird automatisch aus dem Dropdown-Steuerelement **automatisieren** zur Verfügung gestellt, wenn Sie mit Insider Risiko-Verwaltungs Fällen für den Benutzer arbeiten, der den Fluss erstellt.

>[!IMPORTANT]
>Wenn andere Benutzer in Ihrer Organisation Zugriff auf den Fluss benötigen, muss der Fluss freigegeben werden.

### <a name="create-a-custom-power-automate-flow-for-insider-risk-management"></a>Erstellen eines benutzerdefinierten Power-Automatisierungs Flusses für Insider-Risikomanagement

Einige Prozesse und Workflows für Ihre Organisation liegen möglicherweise außerhalb der empfohlenen Fluss Vorlagen für das Insider Risikomanagement, und Sie müssen möglicherweise benutzerdefinierte Power-Automatisierungs Flüsse für Insider Risikomanagement Bereiche erstellen. Power Automation Flows sind flexibel und unterstützen umfangreiche Anpassungen, aber es gibt Schritte, die für die Integration in Insider Risk Management-Funktionen ergriffen werden müssen.

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Power-Automatisierungs Vorlage für das Insider Risikomanagement zu erstellen:

1. **Überprüfen der Power automatisieren-Fluss Lizenz**: um benutzerdefinierte Power-Automatisierungs Flüsse zu erstellen, die Insider Risk Management-Auslöser verwenden, benötigen Sie eine Power autoautomatisierungs-Lizenz. Die empfohlenen Fluss Vorlagen für das Insider Risikomanagement erfordern keine zusätzliche Lizenzierung und sind Bestandteil ihrer Insider Risk Management-Lizenz.
2. **Erstellen eines automatisierten Ablaufs**: Erstellen eines Flusses, der einen oder mehrere Aufgaben ausführt, nachdem dieser durch ein Insider Risk Management-Ereignis ausgelöst wurde. Ausführliche Informationen zum Erstellen eines automatisierten Flusses finden Sie unter [Erstellen eines Flusses in Power Automation](https://docs.microsoft.com/power-automate/get-started-logic-flow).
3. **Wählen Sie den Microsoft 365 Compliance Connector**aus: Suchen Sie nach, und wählen Sie den Microsoft 365-Kompatibilitäts-Konnektor aus. Dieser Connector aktiviert Insider Risikomanagement-Auslöser und-Aktionen. Weitere Informationen zu Connectors finden Sie im Artikel [Connector Reference Overview](https://docs.microsoft.com/connectors/connector-reference/) .
4. **Wählen Sie Insider Risk Management-Auslöser für Ihren Flow**aus: Insider Risk Management bietet zwei Trigger für benutzerdefinierte Power Automation Flows:
    - **Für einen ausgewählten Insider Risk Management-Fall**: Flows with this Trigger können auf der Seite "Insider Risk Management Cases" ausgewählt werden.
    - **Für einen ausgewählten Insider Risk Management-Benutzer**: Flows with this Trigger kann auf der Seite "Insider Risk Management-benutzerdashboard" ausgewählt werden.
5. Wählen Sie Insider Risk Management-Aktionen für Ihren Flow aus: Sie können aus mehreren Aktionen für das Insider Risikomanagement auswählen, um Sie in den benutzerdefinierten Ablauf einzubeziehen:
    - Alert für Insider Risk Management abrufen
    - Holen Sie sich Insider Risk Management Case
    - Insider Risk Management-Benutzer abrufen
    - Alerts für Insider Risk Management für einen Fall abrufen
    - Hinzufügen von Insider Risikomanagement-Fall Hinweis

### <a name="share-a-power-automate-flow"></a>Freigeben eines Power-Automatisierungs Flusses

Standardmäßig sind Power Automation Flows, die von einem Benutzer erstellt werden, nur für diesen Benutzer verfügbar. Damit andere Benutzer des Insider Risikomanagements Zugriff haben und einen Flow verwenden können, muss der Flow vom Flow Creator gemeinsam verwendet werden. Um einen Fluss freizugeben, verwenden Sie die Einstellungs Steuerelemente in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center oder die Option **Power Automation Flows verwalten** aus dem Automatisierungs Steuerelement, wenn Sie direkt auf den **Dashboardseiten** " **Cases** " oder "Users" arbeiten. Nachdem Sie einen Flow freigegeben haben, können alle Personen, für die er freigegeben wurde, auf den Fluss in der Dropdownliste zur **Automatisierung** von Steuerelementen in den **Dashboards**für **Fall** und Benutzer zugreifen.

Wenn Sie einen Power-Automatisierungs Fluss im Bereich "Einstellungen" freigeben möchten, müssen Sie Mitglied der Administrator-Rollengruppe " *Insider Risk Management* *" oder "Insider Risk Management"* sein. Zum Freigeben eines Power-Automatisierungs Flusses mit der Option **Power-Automatisierungs Fluss verwalten** können Sie Mitglied mindestens einer Rollengruppe für die Verwaltung von Insider Risiken sein.

Führen Sie die folgenden Schritte aus, um einen Power-Automatisierungs Fluss freizugeben:

1. Wechseln Sie im [Microsoft 365 Compliance Center](htttps://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie **interne Risiko Einstellungen**  >  **Power Automation Flows**aus. Sie können auch auf den Seiten **Dashboards** für **Fälle** oder Benutzer zugreifen, indem Sie die Option **automatisieren**der  >  **Verwaltung von Power Automation Flows**auswählen.
2. Wählen Sie auf der Seite **Power Automation Flows** die Registerkarte **meine Flows** oder **Team Flows** aus.
3. Wählen Sie den freizugebenden Fluss aus, und wählen Sie dann im Menü Fluss Optionen die Option **Freigeben** aus.
4. Geben Sie auf der Seite Fluss Freigabe den Namen des Benutzers oder der Gruppe ein, den Sie als Besitzer für den Datenfluss hinzufügen möchten.
5. Wählen Sie im Dialogfeld **Verbindung verwendet** die Option **OK** aus, um zu bestätigen, dass der hinzugefügte Benutzer oder die Gruppe Vollzugriff auf den Fluss haben wird.

### <a name="edit-a-power-automate-flow"></a>Bearbeiten eines Power-Automatisierungs Flusses

Um einen Fluss zu bearbeiten, verwenden Sie die Einstellungs Steuerelemente in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center oder die Option **Power Automation Flows verwalten** aus dem **Automatisierungs** Steuerelement, wenn Sie direkt in den **Dashboards**für **Fälle** oder Benutzer arbeiten.

Zum Bearbeiten eines Power-Automatisierungs Flusses im Bereich "Einstellungen" müssen Sie Mitglied der Administrator-Rollengruppe " *Insider Risk Management* *" oder "Insider Risk Management"* sein. Zum Bearbeiten eines Power-Automatisierungs Flusses mit der Option **Power-Automatisierungs Fluss verwalten** können Sie Mitglied mindestens einer Rollengruppe für die Verwaltung von Insider Risiken sein.

Führen Sie die folgenden Schritte aus, um einen Power-Automatisierungs Fluss zu bearbeiten:

1. Wechseln Sie im [Microsoft 365 Compliance Center](htttps://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie **interne Risiko Einstellungen**  >  **Power Automation Flows**aus. Sie können auch auf den Seiten **Dashboards** für **Fälle** oder Benutzer zugreifen, indem Sie die Option **automatisieren**der  >  **Verwaltung von Power Automation Flows**auswählen.
2. Wählen Sie auf der Seite **Strom Automatisierungs Flüsse** einen zu bearbeitenden Fluss aus, und wählen Sie im Menü Flusssteuerung die Option **Bearbeiten** aus.
3. Wählen Sie die **Auslassungs**  >  **Einstellungen** aus, um eine Fluss Komponenteneinstellung zu ändern, oder **Auslassungs**Punkte  >  **Löschen** , um eine Fluss Komponente zu löschen.
4. Klicken Sie auf **Speichern** und dann auf **Schließen** , um die Bearbeitung des Flusses abzuschließen.

### <a name="delete-a-power-automate-flow"></a>Löschen eines Power-Automatisierungs Flusses

Zum Löschen eines Flusses verwenden Sie die Einstellungs Steuerelemente in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center oder die Option **Power Automation Flows verwalten** aus dem **Automatisierungs** Steuerelement, wenn Sie direkt in den **Dashboards**für **Fälle** oder Benutzer arbeiten. Wenn ein Flow gelöscht wird, wird er als Option für alle Benutzer entfernt.

Zum Löschen eines Power-Automatisierungs Flusses im Bereich "Einstellungen" müssen Sie Mitglied der Administrator-Rollengruppe " *Insider Risk Management* *" oder "Insider Risk Management"* sein. Sie müssen Mitglied mindestens einer Rollengruppe "Insider Risk Management" sein, um einen Power-Automatisierungs Fluss mit der Option **Power Automation** Flows verwalten zu löschen.

Führen Sie die folgenden Schritte aus, um einen Power-Automatisierungs Fluss zu löschen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](htttps://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie **interne Risiko Einstellungen**  >  **Power Automation Flows**aus. Sie können auch auf den Seiten **Dashboards** für **Fälle** oder Benutzer zugreifen, indem Sie die Option **automatisieren**der  >  **Verwaltung von Power Automation Flows**auswählen.
2. Wählen Sie auf der Seite **Strom Automatisierungs Flüsse** einen zu löschenden Fluss aus, und wählen Sie im Menü Flusssteuerung die Option **Löschen** aus.
3. Wählen Sie im Dialogfeld Löschbestätigung die Option **Löschen** aus, um den Fluss zu entfernen, oder wählen Sie **Abbrechen** aus, um die Löschaktion zu beenden.

## <a name="microsoft-teams-preview"></a>Microsoft Teams (Vorschau)

Compliance-Analysten und Ermittler können Microsoft Teams problemlos für die Zusammenarbeit bei Insider Risikomanagement-Fällen verwenden. Sie können koordinieren und mit anderen Beteiligten in Microsoft Teams kommunizieren, um Folgendes zu erreichen:

- Koordinieren und Überprüfen von Antwort Aktivitäten für Fälle in privaten Teams-Kanälen
- Sicheres freigeben und Speichern von Dateien und beweisen in Bezug auf einzelne Fälle
- Verfolgen und Überprüfen von Reaktions Aktivitäten durch Analysten und Ermittler

Nachdem Microsoft Teams für das Insider Risikomanagement aktiviert wurde, wird jedes Mal, wenn eine Warnung bestätigt wird und ein Fall erstellt wird, ein dediziertes Microsoft Teams-Team erstellt. Standardmäßig enthält das Team automatisch alle Mitglieder des *Insider Risk Managements*, der *Insider Risk Management Analysts*und der *Insider Risk Management Investigators* -Rollengruppen (bis zu 100 anfängliche Benutzer). Zusätzliche Organisations Mitarbeiter können dem Team hinzugefügt werden, nachdem es erstellt wurde und je nach Bedarf. Bei vorhandenen Fällen, die vor dem Aktivieren von Microsoft Teams erstellt wurden, können Analysten und Ermittler bei Bedarf ein neues Microsoft Teams-Team erstellen, wenn Sie in einem Fall arbeiten.  Nachdem Sie den zugehörigen Fall im Insider Risikomanagement aufgelöst haben, wird das Team automatisch archiviert (in ausgeblendet und schreibgeschützt verschoben).

Weitere Informationen zur Verwendung von Teams und Kanälen in Microsoft Teams finden Sie unter [Übersicht über Teams und Kanäle in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-channels-overview).

Das Aktivieren der Microsoft Teams-Unterstützung für Fälle ist schnell und einfach zu konfigurieren. Führen Sie die folgenden Schritte aus, um Microsoft Teams für das Insider Risikomanagement zu aktivieren:

1. Wechseln Sie im [Microsoft 365 Compliance Center](htttps://compliance.microsoft.com)zu Insider Risk **Management**-  >  **Insider Risiko Einstellungen**.
2. Klicken Sie auf die Registerkarte **Microsoft Teams** .
3. Aktivieren Sie die Microsoft Teams-Integration für Insider Risk Management.
4. Wählen Sie **Save** to configure and Exit aus.

### <a name="create-a-microsoft-teams-team-for-existing-cases"></a>Erstellen eines Microsoft Teams-Teams für vorhandene Fälle

Wenn Sie Microsoft Teams-Unterstützung für Insider Risk Management aktivieren, nachdem Sie vorhandene Fälle haben, müssen Sie ein Team für jeden Fall nach Bedarf manuell erstellen. Nach dem Aktivieren der Microsoft Teams-Unterstützung in den Einstellungen für das Insider Risikomanagement werden in neuen Fällen automatisch ein neues Microsoft Teams-Team erstellt.

Benutzer benötigen die Berechtigung zum Erstellen von Microsoft 365-Gruppen in Ihrer Organisation, um ein Microsoft Teams-Team aus einem Fall zu erstellen. Weitere Informationen zum Verwalten von Berechtigungen für Microsoft 365-Gruppen finden Sie unter [Manage who can create Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups).

Um ein Team für einen Fall zu erstellen, verwenden Sie das Microsoft Team-Steuerelement erstellen, wenn Sie direkt in einem vorhandenen Fall arbeiten. Führen Sie die folgenden Schritte aus, um ein neues Team zu erstellen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](htttps://compliance.microsoft.com)zu **Insider Risikomanagement**  >  -**Fälle** , und wählen Sie einen vorhandenen Fall aus.
2. Wählen Sie im Menü Fall Aktion die Option **Microsoft-Team erstellen**aus.
3. Geben Sie im Feld **Teamname** einen Namen für das neue Microsoft Teams-Team ein.
4. Wählen Sie **Microsoft-Team erstellen** aus, und klicken Sie dann auf **Schließen**.

Je nach Anzahl der Benutzer, die Rollengruppen für das Insider Risikomanagement zugewiesen sind, kann es 15 Minuten dauern, bis alle Ermittler und Analysten dem Microsoft Teams-Team für einen Fall hinzugefügt werden.
