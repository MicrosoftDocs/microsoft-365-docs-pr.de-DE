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
ms.openlocfilehash: 7701932cdd41b673dcc665c71983df9f4d244a8b
ms.sourcegitcommit: 9489aaf255f8bf165e6debc574e20548ad82e882
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "46632174"
---
# <a name="insider-risk-management-policies"></a>Richtlinien für Insider-Risikomanagement

Richtlinien für Insider-Risikomanagement bestimmen, welche Benutzer im Bereich sind und welche Arten von Risikoindikatoren für Warnungen konfiguriert sind. Sie können schnell eine Richtlinie erstellen, die für alle Benutzer in Ihrer Organisation gilt, oder einzelne Benutzer oder Gruppen für die Verwaltung in einer Richtlinie definieren. Richtlinien unterstützen Inhalts Prioritäten, um Richtlinienbedingungen auf mehrere oder bestimmte Microsoft Teams, SharePoint-Websites, Daten Sensitivitäts Typen und Datenbeschriftungen zu konzentrieren. Mithilfe von Vorlagen können Sie bestimmte Risikoindikatoren auswählen und Ereignis Schwellenwerte für Richtlinien Indikatoren anpassen, sodass Risikobewertungen und Grad und Häufigkeit von Warnungen effektiv angepasst werden. Darüber hinaus helfen Risiko Bewertungs Verstärker und anomale Erkennungen bei der Identifizierung von Benutzeraktivitäten, die eine höhere Bedeutung haben oder ungewöhnlich sind. Richtlinien-Fenster ermöglichen Ihnen, den Zeitrahmen zu definieren, um die Richtlinie auf Warnungs Aktivitäten anzuwenden, und werden verwendet, um die Dauer der Richtlinie nach der Aktivierung zu bestimmen.

## <a name="policy-dashboard"></a>Richtlinien-Dashboard

Über das **Richtlinien-Dashboard** können Sie sich schnell einen Überblick über die Richtlinien in Ihrer Organisation und den aktuellen Status der mit den einzelnen Richtlinien verbundenen Warnungen verschaffen.

- **Richtlinienname**: der Name, der der Richtlinie im Richtlinien-Assistenten zugewiesen ist.
- **Aktive Warnungen**: die Anzahl der aktiven Warnungen für jede Richtlinie.
- **Bestätigte Warnungen**: die Gesamtzahl der Warnungen, die in den Fällen aus der Richtlinie in den letzten 365 Tagen geführt wurden.
- **Bei Warnungen ausgeführte Aktionen**: die Gesamtzahl der Benachrichtigungen, die in den letzten 365 Tagen bestätigt oder entlassen wurden.
- **Richtlinien Effektivität**: der Prozentsatz, der durch die insgesamt bestätigten Warnungen dividiert durch die Gesamtanzahl der Aktionen, die für Warnungen vorgenommen wurden, bestimmt wird (die Summe der Warnungen, die im letzten Jahr bestätigt oder entlassen wurden).
- **Aktiv**: der Status des Falls, entweder *Ja* oder *Nein*.

![Richtlinien-Dashboard für Insider Risikomanagement](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Richtlinienvorlagen

Vorlagen für Insider Risikomanagement sind vordefinierte Richtlinienbedingungen, die die Arten von Risikoindikatoren und das risikobewertungsmodell definieren, das von der Richtlinie verwendet wird. Bevor eine Richtlinie erstellt wird, muss ihr im Richtlinienerstellungs-Assistenten eine Vorlage zugewiesen werden. Das Insider Risikomanagement unterstützt bis zu fünf Richtlinien für jede Richtlinienvorlage. Wenn Sie mit dem Richtlinien-Assistenten eine neue Insider Risiko Richtlinie erstellen, wählen Sie eine der folgenden Richtlinienvorlagen aus:

### <a name="data-theft-by-departing-users"></a>Datendiebstahl durch Benutzer

Wenn Benutzer Ihre Organisation verlassen, gibt es bestimmte Risikoindikatoren, die typischerweise mit dem Datendiebstahl durch abfliegende Benutzer verbunden sind. Diese Richtlinienvorlage verwendet Indikatoren für die Erkennung von Risiko Punkten und Schwerpunkten sowie Warnungen in diesem Risikobereich. Datendiebstahl für Benutzer, die abgemeldet werden, kann das Herunterladen von Dateien aus SharePoint Online, das Drucken von Dateien und das Kopieren von Daten in persönliche Cloud-Messaging-und-Speicherdienste in der Nähe von Arbeits Rücktritten und Endterminen umfassen. Diese Vorlage beginnt mit der Bewertung von Risikoindikatoren im Zusammenhang mit diesen Aktivitäten und ihrer Korrelation mit dem Status der Benutzereinstellung.

>[!IMPORTANT]
>Bei Verwendung dieser Vorlage müssen Sie einen Microsoft 365 HR-Connector für die regelmäßige Einfuhr von Kündigungs-und Beendigungsdaten für Benutzer in Ihrer Organisation konfigurieren. Lesen Sie den Artikel [Importieren von Daten mit dem HR-Connector](import-hr-data.md) , um schrittweise Anleitungen zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation zu erhalten.

### <a name="general-data-leaks"></a>Allgemeine Datenlecks

Das Schützen von Daten und das verhindern von Datenverlusten stellt für die meisten Organisationen eine ständige Herausforderung dar, insbesondere mit dem schnellen Wachstum neuer Daten, die von Benutzern, Geräten und Diensten erstellt werden. Benutzer sind befugt, Informationen über Dienste und Geräte hinweg zu erstellen, zu speichern und gemeinsam zu nutzen, mit denen die Verwaltung von Datenverlusten zunehmend komplexer und schwieriger wird. Datenlecks können eine versehentliche Übernutzung von Informationen außerhalb Ihrer Organisation oder Datendiebstahl mit böswilliger Absicht umfassen. In Verbindung mit einer zugewiesenen DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) beginnt diese Vorlage mit der Bewertung von Echt Zeit Erkennungen verdächtiger SharePoint Online von Daten Downloads, der Datei-und Ordnerfreigabe, dem Drucken von Dateien und dem Kopieren von Daten in Personal Cloud Messaging and Storage Services.

Bei Verwendung einer **Datenlecks** -Vorlage müssen Sie eine DLP-Richtlinie zuweisen, um Indikatoren in der Insider Risiko Richtlinie für Warnungen mit hohem Schweregrad in Ihrer Organisation auszulösen. Wenn eine DLP-Richtlinienregel zum Office 365 Überwachungsprotokoll hinzugefügt wird, wird eine Warnung mit hohem Schweregrad generiert, und die mit dieser Vorlage erstellten Insider Risikorichtlinien untersuchen automatisch die DLP-Warnung mit hohem Schweregrad. Wenn die Warnung einen in-Scope-Benutzer enthält, der in der Insider Risiko Richtlinie definiert ist, wird die Warnung von der Insider Risiko Richtlinie als neue Warnung verarbeitet und einem Insider risikoschweregrad und Risikobewertung zugeordnet. Mit dieser Richtlinie können Sie diese Warnung im Kontext mit anderen in der Anfrage enthaltenen Aktivitäten auswerten.

#### <a name="data-leaks-policy-guidelines"></a>Richtlinien Richtlinien für Datenlecks

Beachten Sie beim Erstellen oder Ändern von DLP-Richtlinien für die Verwendung mit Richtlinien für Insider-Risikomanagement die folgenden Richtlinien:

- Priorisieren von Daten zugrunde liegenden Ereignissen und selektives Zuweisen von **Vorfalls Berichten** zu *hohen* Einstellungen beim Konfigurieren von Regeln in ihren DLP-Richtlinien. Wenn Sie beispielsweise vertrauliche Dokumente an einen bekannten Mitbewerber senden möchten, sollte dies ein *hohes* Ereignis bei der Warnstufe für die Alarmstufe sein. Die übermäßige Zuweisung der *hohen* Ebene in den **Vorfall Berichts** Einstellungen in anderen DLP-Richtlinien Regeln kann das Rauschen im Warnungs Workflow für Insider Risken verbessern und es erschweren, dass Ihre Daten Ermittler und Analysten diese Warnungen ordnungsgemäß auswerten. Wenn Sie beispielsweise *hohe* Warnstufen für Zugriffs Verweigerungs Aktivitäten in DLP-Richtlinien zuweisen, ist es schwieriger, wirklich riskante Benutzerverhalten und-Aktivitäten zu bewerten.
- Stellen Sie sicher, dass Sie die in-Scope-Benutzer in den DLP-und Insider Risk Management-Richtlinien verstehen und ordnungsgemäß konfigurieren. Nur Benutzer, die im Rahmen von Richtlinien für das Insider Risikomanagement mithilfe der **Datenlecks** -Vorlage definiert sind, werden mit hohem Schweregrad DLP-Richtlinienwarnungen verarbeitet. Darüber hinaus werden nur Benutzer, die in einer Regel für eine DLP-Warnung mit hohem Schweregrad in einem Bereich definiert sind, von der Richtlinie für den Umgang mit Insider Risiken untersucht. Es ist wichtig, dass Sie nicht unwissentlich in ihrer DLP-und Insider-Risiko Richtlinie auf widersprüchliche Weise Benutzer in einem Bereich konfigurieren.

     Wenn beispielsweise ihre DLP-Richtlinien Regeln nur auf Benutzer im Vertriebsteam beschränkt sind und die Insider Risiko Richtlinie, die aus der **Datenlecks** -Vorlage erstellt wurde, alle Benutzer als in-Scope definiert hat, verarbeitet die Insider Risiko Richtlinie nur DLP-Warnungen mit hohem Schweregrad für die Benutzer im Verkaufsteam. Die Insider Risiko Richtlinie erhält keine DLP-Warnungen hoher Priorität für Benutzer, die verarbeitet werden sollen, die in den DLP-Regeln in diesem Beispiel nicht definiert sind. Wenn Ihre Richtlinie für das Insider-Risikomanagement, die aus **Datenverlust** Vorlagen erstellt wurde, nur auf Benutzer im Vertriebsteam beschränkt ist und die zugewiesene DLP-Richtlinie auf alle Benutzer beschränkt ist, verarbeitet die Insider Risiko Richtlinie nur DLP-Warnungen mit hohem Schweregrad für Mitglieder des Vertriebsteams. Die Richtlinie für das Insider Risikomanagement ignoriert die DLP-Warnungen mit hohem Schweregrad für alle Benutzer, die sich nicht im Verkaufs Team befinden.

- Stellen Sie sicher, dass die Einstellung " **vorfallberichte** " in der für diese Insider Risikomanagement-Vorlage verwendeten DLP-Richtlinie für Warnungen mit *hohem* Schweregrad konfiguriert ist. Der *hohe* Schweregrad ist das Auslösen von Ereignissen und Warnungen beim Insider Risikomanagement werden nicht aus Regeln in DLP-Richtlinien generiert, wobei das Feld " **vorfallberichte** " auf *niedrig* oder *Mittel*festgelegt ist.

    ![Warnungseinstellung für DLP-Richtlinie](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Wenn Sie eine neue DLP-Richtlinie mithilfe der integrierten Vorlagen erstellen, müssen Sie die Option **Advanced DLP Rules erstellen oder anpassen** auswählen, um die Einstellung **vorfallberichte** für den *hohen* Schweregrad zu konfigurieren.

Für jede Richtlinie für Insider-Risikomanagement, die aus der **Datenlecks** -Vorlage erstellt wurde, kann nur eine DLP-Richtlinie zugewiesen werden. Sie sollten eine dedizierte DLP-Richtlinie erstellen, die die verschiedenen Aktivitäten kombiniert, die Sie erkennen möchten, und als auslösende Ereignisse für Insider Risikorichtlinien fungieren, die die Vorlage **Datenlecks** verwenden.

Eine schrittweise Anleitung zum Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie unter [erstellen, testen und Optimieren eines DLP-Richtlinien](create-test-tune-dlp-policy.md) Themas.

### <a name="data-leaks-by-priority-users-preview"></a>Datenlecks nach Prioritäts Benutzern (Vorschau)

Das Schützen von Daten und das verhindern von Datenverlusten für Benutzer in Ihrer Organisation hängt möglicherweise von ihrer Position, dem Grad des Zugriffs auf vertrauliche Informationen oder der Risiko Historie ab. Datenlecks können eine versehentliche Übernutzung hoch vertraulicher Informationen außerhalb Ihrer Organisation oder Datendiebstahl mit böswilliger Absicht umfassen. In Verbindung mit einer zugewiesenen DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) beginnt diese Vorlage mit der Bewertung von Echt Zeit Erkennungen verdächtiger Aktivitäten und einer erhöhten Wahrscheinlichkeit von Warnungen und Warnungen bei Insider Risiken mit einem höheren Schweregrad. Prioritäts Benutzer sind im Bereich Einstellungen für Insider Risikoverwaltung in [Prioritäts Benutzergruppen](insider-risk-management-settings.md#priority-user-groups-preview) definiert.

Wie bei der **Vorlage "allgemeine Datenlecks**" müssen Sie eine DLP-Richtlinie zum Auslösen von Indikatoren in der Insider Risiko Richtlinie für Warnungen mit hohem Schweregrad in Ihrer Organisation zuweisen. Beachten Sie beim Erstellen einer Richtlinie mit dieser Vorlage die Richtlinien Richtlinien für Datenlecks. Darüber hinaus müssen Sie die Prioritäts Benutzergruppen, die in den Einstellungen für die Priorität " **Insider Risk Management**" erstellt wurden,  >  **Settings**  >  **Priority user groups** der Richtlinie zuweisen.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Datenverluste durch verärgerte Benutzer (Vorschau)

Wenn Benutzer Beschäftigungs Stressoren erleben, werden Sie möglicherweise verärgert, was die Wahrscheinlichkeit von Insider Risiko Aktivitäten erhöhen kann. Diese Vorlage beginnt mit der Bewertung der Benutzeraktivität, wenn ein Indikator zugeordnet ist, der mit Unmut verbunden ist. Beispiele sind Leistungs Verbesserungs Benachrichtigungen, schlechte Leistungsbewertungen oder Änderungen des Status der Auftragsstufe. Datenlecks für verärgerte Benutzer können das Herunterladen von Dateien aus SharePoint Online und das Kopieren von Daten in persönliche Cloud-Messaging-und-Speicherdienste in der Nähe von Employment Stressor-Ereignissen umfassen.

Bei Verwendung dieser Vorlage müssen Sie auch einen Microsoft 365 HR-Connector konfigurieren, um regelmäßige Leistungs Verbesserungs Benachrichtigungen, schlechten Leistungs Überprüfungsstatus oder Änderungsinformationen auf Auftragsebene für Benutzer in Ihrer Organisation zu importieren. Lesen Sie den Artikel [Importieren von Daten mit dem HR-Connector](import-hr-data.md) , um schrittweise Anleitungen zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation zu erhalten.

### <a name="general-security-policy-violations-preview"></a>Allgemeine Sicherheitsrichtlinienverletzungen (Vorschau)

In vielen Organisationen haben Benutzer die Berechtigung, Software auf Ihren Geräten zu installieren oder Geräteeinstellungen zu ändern, um Ihre Aufgaben zu unterstützen. Entweder versehentlich oder mit böswilliger Absicht können Benutzer Malware installieren oder wichtige Sicherheitsfeatures deaktivieren, die zum Schutz von Informationen auf Ihrem Gerät oder in ihren Netzwerkressourcen beitragen. Diese Richtlinienvorlage verwendet Sicherheitswarnungen von Microsoft Defender Advanced Threat Protection (ATP), um mit der Bewertung dieser Aktivitäten und der Fokus Erkennung sowie Warnungen in diesem Risikobereich zu beginnen. Verwenden Sie diese Vorlage, um Einblicke in Sicherheitsrichtlinienverletzungen in Szenarien zu geben, in denen Benutzer möglicherweise einen Verlauf von Sicherheitsrichtlinienverletzungen haben, die möglicherweise ein Indiz für Insider Risiken darstellen.

Sie müssen Microsoft Defender ATP in Ihrer Organisation konfigurieren und Microsoft Defender ATP for Insider Risk Management Integration in das Defender Security Center aktivieren, um Warnungen zu Sicherheitsverletzungen zu importieren. Weitere Informationen zum Konfigurieren von Microsoft Defender ATP für die Integration von Insider Risikomanagement finden Sie unter [configure Advanced Features in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-departing-users-preview"></a>Sicherheitsrichtlinienverletzungen durch abgehende Benutzer (Vorschau)

Benutzer, die nicht mit positiven oder negativen Bedingungen ausgehen, können höhere Risiken für Sicherheitsrichtlinienverletzungen darstellen. Um den Schutz vor versehentlichen oder böswilligen Sicherheitsverletzungen für Benutzer zu vermeiden, verwendet diese Richtlinienvorlage Microsoft Defender ATP-Warnungen, um Einblicke in sicherheitsbezogene Aktivitäten zu geben. Zu diesen Aktivitäten gehören der Benutzer, der Malware oder andere potenziell schädliche Anwendungen installiert und Sicherheitsfunktionen auf seinen Geräten deaktiviert. Richtlinien Indikatoren werden aktiviert, nachdem Benutzer einen Rücktritt oder ein Kündigungsdatum aus dem Microsoft 365 HR-Connector als auslösendes Ereignis importiert haben.

Bei Verwendung dieser Vorlage müssen Sie einen Microsoft 365 HR-Connector für die regelmäßige Einfuhr von Kündigungs-und Beendigungsdaten für Benutzer in Ihrer Organisation konfigurieren. Lesen Sie den Artikel [Importieren von Daten mit dem HR-Connector](import-hr-data.md) , um schrittweise Anleitungen zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation zu erhalten.

Sie müssen Microsoft Defender ATP in Ihrer Organisation konfigurieren und Microsoft Defender ATP for Insider Risk Management Integration in das Defender Security Center aktivieren, um Warnungen zu Sicherheitsverletzungen zu importieren. Weitere Informationen zum Konfigurieren von Microsoft Defender ATP für die Integration von Insider Risikomanagement finden Sie unter [configure Advanced Features in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-priority-users-preview"></a>Sicherheitsrichtlinienverletzungen nach Prioritäts Benutzern (Vorschau)

Der Schutz vor Sicherheitsverletzungen für Benutzer in Ihrer Organisation hängt möglicherweise von ihrer Position, dem Grad des Zugriffs auf vertrauliche Informationen oder der Risiko Historie ab. Da Sicherheitsverletzungen von Prioritäts Benutzern möglicherweise einen übergroßen Einfluss auf die kritischen Bereiche Ihrer Organisation haben, beginnt diese Richtlinienvorlage mit der Bewertung dieser Indikatoren und verwendet Microsoft Defender ATP Alerts, um Einblicke in sicherheitsbezogene Aktivitäten für diese Benutzer bereitzustellen. Diese können die Priorität von Benutzern bei der Installation von Schadsoftware oder anderen potenziell schädlichen Anwendungen und das Deaktivieren von Sicherheitsfeatures auf Ihren Geräten umfassen. Prioritäts Benutzer sind im Bereich Einstellungen für Insider Risikoverwaltung in Prioritäts Benutzergruppen definiert.

Sie müssen Microsoft Defender ATP in Ihrer Organisation konfigurieren und Microsoft Defender ATP for Insider Risk Management Integration in das Defender Security Center aktivieren, um Warnungen zu Sicherheitsverletzungen zu importieren. Weitere Informationen zum Konfigurieren von Microsoft Defender ATP für die Integration von Insider Risikomanagement finden Sie unter [configure Advanced Features in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center). Darüber hinaus müssen Sie die Prioritäts Benutzergruppen, die in den Einstellungen für die Priorität " **Insider Risk Management**" erstellt wurden,  >  **Settings**  >  **Priority user groups** der Richtlinie zuweisen.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Sicherheitsrichtlinienverletzungen durch verärgerte Benutzer (Vorschau)

Benutzer, die Berufs Stressoren erleben, können ein höheres Risiko für unbeabsichtigte oder böswillige Sicherheitsrichtlinienverletzungen haben. Diese Stressoren können den Benutzer enthalten, der in einen Leistungsverbesserungsplan, einen schlechten Leistungs Prüfungsstatus oder von seiner aktuellen Position herabgestuft wird. Diese Richtlinienvorlage startet die Risikobewertung basierend auf diesen Indikatoren und Aktivitäten, die diesen Ereignissen für diese Benutzer zugeordnet sind.

Bei Verwendung dieser Vorlage müssen Sie auch einen Microsoft 365 HR-Connector konfigurieren, um regelmäßige Leistungs Verbesserungs Benachrichtigungen, schlechten Leistungs Überprüfungsstatus oder Änderungsinformationen auf Auftragsebene für Benutzer in Ihrer Organisation zu importieren. Lesen Sie den Artikel [Importieren von Daten mit dem HR-Connector](import-hr-data.md) , um schrittweise Anleitungen zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation zu erhalten.

Außerdem müssen Sie Microsoft Defender ATP in Ihrer Organisation konfigurieren und Microsoft Defender ATP for Insider Risk Management Integration in das Defender Security Center aktivieren, um Warnungen zu Sicherheitsverletzungen zu importieren. Weitere Informationen zum Konfigurieren von Microsoft Defender ATP für die Integration von Insider Risikomanagement finden Sie unter [configure Advanced Features in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="offensive-language-in-email"></a>Anstößige Sprache in E-Mails

Das Erkennen von und das Ergreifen von Maßnahmen zur Vorbeugung von anstößigem und missbräuchlichem Verhalten ist eine wichtige Komponente zur Vermeidung von Risiken. Integrierte Klassifizierungen in Microsoft 365 Scan gesendete e-Mail-Nachrichten von Exchange Online Postfächern in Ihrer Organisation für verschiedene Arten von Kompatibilitätsproblemen. Diese Klassifizierungen verwenden eine Kombination aus künstlicher Intelligenz und Stichwörtern, um die Sprache in e-Mails zu identifizieren, die gegen Belästigungs Richtlinien verstoßen dürften. Verwenden Sie diese Vorlage, um schnell eine Richtlinie zu erstellen, die diese Klassifizierungen verwendet, um e-Mail-Nachrichteninhalte, die als missbräuchlich oder beleidigend eingestuft werden können, automatisch zu erkennen. Für das Insider Risikomanagement werden Klassifizierungen verwendet, die gesendete e-Mail-Nachrichten für anstößige Sprachen nach englischen sprach Begriffen und-Ansichten scannen.

### <a name="policy-template-prerequisites-and-triggering-events"></a>Richtlinienvorlagen Voraussetzungen und auslösende Ereignisse

Je nach der Vorlage, die Sie für eine Richtlinie für das Risikomanagement für Insider auswählen, sind die auslösenden Ereignisse und Richtlinien Voraussetzungen unterschiedlich. Auslösende Ereignisse sind Voraussetzungen, mit denen bestimmt wird, ob ein Benutzer für eine Richtlinie zur Verwaltung von Insider Risiken aktiv ist. Wenn ein Benutzer einer Richtlinie für Insider Risiken hinzugefügt wird, aber kein auslösendes Ereignis vorliegt, wird die Benutzeraktivität nicht von der Richtlinie ausgewertet, es sei denn, Sie wird manuell im Dashboard Benutzer hinzugefügt. Richtlinien Voraussetzungen sind erforderliche Elemente, damit die Richtlinie die zum Bewerten des Risikos erforderlichen Signale oder Aktivitäten erhält.

In der folgenden Tabelle sind die auslösenden Ereignisse und Voraussetzungen für Richtlinien aufgeführt, die von den einzelnen Richtlinien für Insider Risiken erstellt werden:

| **Richtlinienvorlage** | **Auslösen von Ereignissen für Richtlinien** | **Voraussetzungen** |
| :------------------ | :--------------------------------- | :---------------- |
| Datendiebstahl durch Benutzer | Kennzeichen für Rücktritt oder Terminierung aus dem HR-Connector | Microsoft 365 HR-Connector, konfiguriert für Terminierungs-und Datums Indikatoren für das resignieren |
| Allgemeine Datenlecks | Datenverlust-Richtlinienaktivität, die eine Warnung mit hohem Schweregrad erstellt | Für Warnungen mit hohem Schweregrad konfigurierte DLP-Richtlinie |
| Datenverluste nach Prioritäts Benutzern | Datenverlust-Richtlinienaktivität, die eine Warnung mit hohem Schweregrad erstellt | Für Warnungen mit hohem Schweregrad konfigurierte DLP-Richtlinie <br><br> In Einstellungen für Insider Risiken konfigurierte Prioritäts Benutzergruppen |
| Datenverluste durch verärgerte Benutzer | Leistungsverbesserungen, schlechte Leistung oder Änderungs Indikatoren auf Auftragsebene aus dem HR-Connector | Microsoft 365 HR-Connector für Unmut-Indikatoren konfiguriert |
| Allgemeine Sicherheitsrichtlinienverletzungen | Defensive Umgehung von Sicherheitskontrollen oder unerwünschter Software, die von Microsoft Defender ATP erkannt wurde | Aktives Microsoft Defender ATP-Abonnement <br><br> Microsoft Defender ATP-Integration in das Microsoft 365 Compliance Center konfiguriert |
| Sicherheitsrichtlinienverletzungen durch Benutzer, die abgemeldet werden | Kennzahlen zum Rücktritt oder zum Terminierungs Datum aus dem HR-Connector | Microsoft 365 HR-Connector, konfiguriert für Terminierungs-und Datums Indikatoren für das resignieren <br><br> Aktives Microsoft Defender ATP-Abonnement <br><br> Microsoft Defender ATP-Integration in das Microsoft 365 Compliance Center konfiguriert |
| Sicherheitsrichtlinienverletzungen nach Prioritäts Benutzern | Defensive Umgehung von Sicherheitskontrollen oder unerwünschter Software, die von Microsoft Defender ATP erkannt wurde | Aktives Microsoft Defender ATP-Abonnement <br><br> Microsoft Defender ATP-Integration in das Microsoft 365 Compliance Center konfiguriert <br><br> In Einstellungen für Insider Risiken konfigurierte Prioritäts Benutzergruppen |
| Sicherheitsrichtlinienverletzungen durch verärgerte Benutzer | Leistungsverbesserungen, schlechte Leistung oder Änderungs Indikatoren auf Auftragsebene aus dem HR-Connector | Microsoft 365 HR-Connector für Unmut-Indikatoren konfiguriert <br><br> Aktives Microsoft Defender ATP-Abonnement <br><br> Microsoft Defender ATP-Integration in das Microsoft 365 Compliance Center konfiguriert |
| Anstößige Sprache in E-Mails | Anstößige, Drohungen oder belästigende Sprachen in e-Mail-Nachrichten | Aktives Exchange Online-Abonnement |

## <a name="prioritize-content-in-policies"></a>Priorisieren von Inhalten in Richtlinien

Richtlinien für das Insider Risikomanagement unterstützen die Angabe einer höheren Priorität für Inhalte, je nachdem, wo Sie gespeichert ist oder wie Sie klassifiziert werden. Durch die Angabe von Inhalt als Priorität wird das Risikoergebnis für alle zugeordneten Aktivitäten erhöht, was wiederum die Wahrscheinlichkeit erhöht, dass eine Warnung mit hohem Schweregrad generiert wird. Einige Aktivitäten generieren jedoch nur dann eine Warnung, wenn der zugehörige Inhalt integrierte oder benutzerdefinierte vertrauliche Informationstypen enthält oder als Priorität in der Richtlinie angegeben wurde.

Beispielsweise verfügt Ihre Organisation über eine dedizierte SharePoint-Website für ein streng vertrauliches Projekt. Datenlecks für Informationen auf dieser SharePoint-Website können das Projekt gefährden und haben erhebliche Auswirkungen auf den Erfolg. Durch priorisieren dieser SharePoint-Website in einer Richtlinie für Datenverluste werden Risikobewertungen für qualifizierende Aktivitäten automatisch erhöht. Dadurch wird die Wahrscheinlichkeit erhöht, dass diese Aktivitäten eine Warnung bei Insider Risiken generieren und den Schweregrad für die Warnung erhöhen.

Wenn Sie im Richtlinien-Assistenten eine Richtlinie für das Insider Risikomanagement erstellen, können Sie eine der folgenden Prioritäten auswählen:

- **SharePoint-Websites**: jeder Aktivität, die allen Dateitypen in definierten SharePoint-Websites zugeordnet ist, wird ein höheres Risikoergebnis zugewiesen. 
- **Typen vertraulicher Informationen**: jede Aktivität, die Inhalten zugeordnet ist, die [vertrauliche Informationstypen](sensitive-information-type-entity-definitions.md) enthalten, erhält ein höheres Risikoergebnis.
- **Vertraulichkeits Bezeichnungen**: jeder Aktivität, die Inhalten zugeordnet ist, für die bestimmte [Sensitivitäts Bezeichnungen](sensitivity-labels.md) gelten, wird ein höheres Risikoergebnis zugewiesen.

## <a name="create-a-new-policy"></a>Erstellen einer neuen Richtlinie

Um eine neue Richtlinie für das Insider Risikomanagement zu erstellen, verwenden Sie den Richtlinien-Assistenten in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine neue Richtlinie zu erstellen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie **Richtlinie erstellen** aus, um den richtlinienassistenten zu öffnen
3. Füllen Sie auf der Seite **neue Insider Risiko Richtlinie** die folgenden Felder aus:
    - **Name (erforderlich)**: Geben Sie einen Anzeigenamen für die Richtlinie ein.
    - **Description (optional)**: Geben Sie eine Beschreibung für die Richtlinie ein.
    - **Richtlinienvorlage auswählen (erforderlich)**: Wählen Sie eine der [Richtlinienvorlagen](insider-risk-management-policies.md#policy-templates) aus, um die Arten von Risikoindikatoren zu definieren, die von der Richtlinie überwacht werden.

    >[!IMPORTANT]
    >Die meisten Richtlinienvorlagen verfügen über Voraussetzungen, die für die Richtlinie konfiguriert werden müssen, um relevante Warnungen zu generieren. Wenn Sie die entsprechenden Richtlinien Voraussetzungen nicht konfiguriert haben, finden Sie weitere Informationen unter [Erste Schritte mit dem Insider Risikomanagement](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates).

4. Wählen Sie **weiter** aus, um fortzufahren.
5. Wählen Sie auf der Seite **Benutzer** die Option **Benutzer oder Gruppe hinzufügen** oder Benutzer **Gruppen mit Priorität auswählen** aus, um festzulegen, welche Benutzer oder Prioritäts Benutzergruppen in der Richtlinie enthalten sind, je nachdem, welche Richtlinienvorlage Sie ausgewählt haben. Aktivieren Sie gegebenenfalls **alle Benutzer und e-Mail-aktivierten Gruppen** (sofern Sie keine benutzerbasierte Prioritäts Vorlage ausgewählt haben). Wählen Sie **weiter** aus, um fortzufahren.
6. Auf der Seite geben Sie an, **welche Inhalte priorisiert werden sollen (optional)** , können Sie die Quellen zuweisen, um höhere Risikobewertungen zu priorisieren. Einige Aktivitäten generieren jedoch nur dann eine Warnung, wenn der zugehörige Inhalt integrierte oder benutzerdefinierte vertrauliche Informationstypen enthält oder als Priorität auf dieser Seite angegeben wurde:
    - **SharePoint-Websites**: Wählen Sie **SharePoint-Website hinzufügen** und die SharePoint-Organisationen aus, die Sie priorisieren möchten. Beispiel: *"group1@contoso.SharePoint.com/Sites/Group1"*.
    - **Typ vertraulicher Informationen**: Wählen Sie **vertraulichen Infotyp hinzufügen** aus, und wählen Sie die Vertraulichkeits Typen aus, die Sie priorisieren möchten. Beispiel: *"US Bank Account Number"* und *"Kreditkartennummer"*.
    - **Vertraulichkeits Bezeichnungen**: Wählen Sie **Vertraulichkeits Bezeichnung hinzufügen** aus, und wählen Sie die Beschriftungen aus, die Sie priorisieren möchten. Beispiel: *"vertraulich"* und *"geheim"*.
7. Wählen Sie **weiter** aus, um fortzufahren.
8. Auf der Seite **Richtlinien Indikatoren auswählen** werden die [Indikatoren](insider-risk-management-settings.md#indicators) angezeigt, die Sie auf der Seite Indikatoren für **Insider Risiko Einstellungen**als verfügbar definiert haben  >  **Indicators** . Wenn Sie zu Beginn des Assistenten eine Vorlage *Datenverlust* ausgewählt haben, müssen Sie in der Dropdownliste **DLP-Richtlinie** eine DLP-Richtlinie auswählen, um auslösende Indikatoren für die Richtlinie zu aktivieren. Wählen Sie die Indikatoren aus, die Sie auf die Richtlinie anwenden möchten. Wenn Sie die Standardeinstellungen für den Richtlinien Schwellenwert für diese Indikatoren nicht verwenden möchten, deaktivieren Sie die **von Microsoft empfohlenen Standardschwellen** Werte und geben Sie die Schwellenwerte für jedes ausgewählte Kennzeichen ein. Wenn Sie mindestens ein *Office* -oder Gerätekennzeichen ausgewählt haben, wählen Sie je nach Bedarf das **Risiko Bewertungs** *Modul* aus. Risiko Bewertungs Verstärker gelten nur für ausgewählte Indikatoren.

    >[!IMPORTANT]
    >Wenn keine Indikatoren auf dieser Seite ausgewählt werden können, müssen Sie die Indikatoren auswählen, die für alle Richtlinien auf der Seite mit **Insider risk management**den  >  **Settings**  >  **Richtlinien Indikatoren** für Insider Risk Management-Einstellungen aktiviert werden sollen.

9. Wählen Sie **weiter** aus, um fortzufahren.
10. Auf der Seite " **Richtlinienzeit Rahmen** " werden die Bedingungen für das [Aktivierungsfenster](insider-risk-management-settings.md#policy-timeframes) für die Richtlinie angezeigt, die auf der Seite mit den Richtlinien für die Richtlinienzeit für **Insider Risiken**vorliegt  >  **Policy timeframes** .
11. Wählen Sie **weiter** aus, um fortzufahren.
12. Überprüfen Sie auf der Seite **überprüfen** die Einstellungen, die Sie für die Richtlinie ausgewählt haben. Wählen Sie **Bearbeiten** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **senden** aus, um die Richtlinie zu erstellen und zu aktivieren.

## <a name="update-a-policy"></a>Aktualisieren einer Richtlinie

Um eine vorhandene Richtlinie für das Insider Risikomanagement zu aktualisieren, verwenden Sie den Richtlinien-Assistenten in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine vorhandene Richtlinie zu verwalten:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie im Richtlinien Dashboard die Richtlinie aus, die Sie verwalten möchten.
3. Wählen Sie auf der Seite Richtliniendetails die Option **Richtlinie bearbeiten** aus.
4. Im Richtlinien-Assistenten können Sie die folgenden Felder nicht bearbeiten:
    - **Name**: der Anzeigename für die Richtlinie
    - **Wählen Sie Richtlinienvorlage**: die Vorlage, mit der die Typen von Risikoindikatoren definiert werden, die von der Richtlinie überwacht werden.
5. Geben Sie eine neue Beschreibung für die Richtlinie in das Feld **Beschreibung** ein. 
6. Wählen Sie **weiter** aus, um fortzufahren.
7. Wählen Sie auf der Seite **Benutzer** die Option **Benutzer oder Gruppe hinzufügen** oder Benutzer **Gruppen mit Priorität auswählen** aus, um festzulegen, welche Benutzer oder Prioritäts Benutzergruppen in der Richtlinie enthalten sind, je nachdem, welche Richtlinienvorlage Sie ausgewählt haben. Aktivieren Sie gegebenenfalls **alle Benutzer und e-Mail-aktivierten Gruppen** (sofern Sie keine benutzerbasierte Prioritäts Vorlage ausgewählt haben). Wählen Sie **weiter** aus, um fortzufahren.
8. Auf der Seite geben Sie an, **welche Inhalte priorisiert werden sollen (optional)** , können Sie die Quellen zuweisen, um höhere Risikobewertungen zu priorisieren. Einige Aktivitäten generieren jedoch nur dann eine Warnung, wenn der zugehörige Inhalt integrierte oder benutzerdefinierte vertrauliche Informationstypen enthält oder als Priorität auf dieser Seite angegeben wurde:
    - **SharePoint-Websites**: Wählen Sie **SharePoint-Website hinzufügen** und die SharePoint-Organisationen aus, die Sie priorisieren möchten. Beispiel: *"group1@contoso.SharePoint.com/Sites/Group1"*.
    - **Typ vertraulicher Informationen**: Wählen Sie **vertraulichen Infotyp hinzufügen** aus, und wählen Sie die Vertraulichkeits Typen aus, die Sie priorisieren möchten. Beispiel: *"US Bank Account Number"* und *"Kreditkartennummer"*.
    - **Vertraulichkeits Bezeichnungen**: Wählen Sie **Vertraulichkeits Bezeichnung hinzufügen** aus, und wählen Sie die Beschriftungen aus, die Sie priorisieren möchten. Beispiel: *"vertraulich"* und *"geheim"*.
9. Wählen Sie **weiter** aus, um fortzufahren.
10. Auf der Seite **Richtlinien Indikatoren auswählen** werden die [Indikatoren](insider-risk-management-settings.md#indicators) angezeigt, die Sie auf der Seite Indikatoren für **Insider Risiko Einstellungen**als verfügbar definiert haben  >  **Indicators** . Wenn Sie zu Beginn des Assistenten eine Vorlage *Datenverlust* ausgewählt haben, müssen Sie in der Dropdownliste **DLP-Richtlinie** eine DLP-Richtlinie auswählen, um auslösende Indikatoren für die Richtlinie zu aktivieren. Wählen Sie die Indikatoren aus, die Sie auf die Richtlinie anwenden möchten. Wenn Sie die Standardeinstellungen für den Richtlinien Schwellenwert für diese Indikatoren nicht verwenden möchten, deaktivieren Sie die **von Microsoft empfohlenen Standardschwellen** Werte und geben Sie die Schwellenwerte für jedes ausgewählte Kennzeichen ein. Wenn Sie mindestens ein *Office* -oder Gerätekennzeichen ausgewählt haben, wählen Sie je nach Bedarf das **Risiko Bewertungs** *Modul* aus. Risiko Bewertungs Verstärker gelten nur für ausgewählte Indikatoren.

    >[!IMPORTANT]
    >Wenn keine Indikatoren auf dieser Seite ausgewählt werden können, müssen Sie die Indikatoren auswählen, die für alle Richtlinien auf der Seite mit **Insider risk management**den  >  **Settings**  >  **Richtlinien Indikatoren** für Insider Risk Management-Einstellungen aktiviert werden sollen.

11. Wählen Sie **weiter** aus, um fortzufahren.
12. Auf der Seite " **Richtlinienzeit Rahmen** " werden die Bedingungen für das [Aktivierungsfenster](insider-risk-management-settings.md#policy-timeframes) für die Richtlinie angezeigt, die auf der Seite mit den Richtlinien für die Richtlinienzeit für **Insider Risiken**vorliegt  >  **Policy timeframes** .
13. Wählen Sie **weiter** aus, um fortzufahren.
14. Überprüfen Sie auf der Seite **überprüfen** die Einstellungen, die Sie für die Richtlinie aktualisiert haben. Wählen Sie **Bearbeiten** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **senden** aus, um die Richtlinie zu aktualisieren und zu aktivieren.

## <a name="delete-a-policy"></a>Löschen einer Richtlinie

>[!NOTE]
>Durch das Löschen einer Richtlinie werden keine aktiven oder archivierten Warnungen gelöscht, die aus der Richtlinie generiert wurden.

Führen Sie die folgenden Schritte aus, um eine vorhandene Richtlinie für Insider-Risikomanagement zu löschen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie im Richtlinien Dashboard die Richtlinie aus, die Sie löschen möchten.
3. Wählen Sie auf der Dashboard-Symbolleiste **Löschen** aus.
4. Wählen Sie im Dialogfeld **Löschen** die Option **Ja** aus, um die Richtlinie zu löschen, oder klicken Sie auf **Abbrechen** , um das Dialogfeld zu schließen.
