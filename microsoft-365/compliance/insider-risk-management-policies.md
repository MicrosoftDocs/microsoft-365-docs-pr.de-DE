---
title: Richtlinien für das Insider-Risikomanagement
description: Informationen zu Richtlinien für das Insiderrisikomanagement in Microsoft 365
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
ms.collection: m365-security-compliance
ms.openlocfilehash: 9f8424beb7e4a078d14bce755fc399ecd41764d9
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126634"
---
# <a name="insider-risk-management-policies"></a>Richtlinien für das Insider-Risikomanagement

Richtlinien für das Insiderrisikomanagement bestimmen, welche Benutzer im Bereich sind und welche Arten von Risikoindikatoren für Warnungen konfiguriert sind. Sie können schnell eine Richtlinie erstellen, die für alle Benutzer in Ihrer Organisation gilt, oder einzelne Benutzer oder Gruppen für die Verwaltung in einer Richtlinie definieren. Richtlinien unterstützen Inhaltsprioritäten, um Richtlinienbedingungen auf mehrere oder bestimmte Microsoft Teams, SharePoint-Websites, Datensensitivitätstypen und Datenbeschriftungen zu konzentrieren. Mithilfe von Vorlagen können Sie bestimmte Risikoindikatoren auswählen und Ereignisschwellenwerte für Richtlinienindikatoren anpassen und die Risikobewertungen sowie die Ebene und Häufigkeit von Warnungen effektiv anpassen. Darüber hinaus helfen Risikobewertungen und Anomalieerkennungen, Benutzeraktivitäten zu identifizieren, die von höherer Wichtigkeit oder ungewöhnlicher sind. In Richtlinienfenstern können Sie den Zeitrahmen definieren, in dem die Richtlinie auf Warnungsaktivitäten angewendet wird, und sie werden verwendet, um die Dauer der nach der Aktivierung aktivierten Richtlinie zu bestimmen.

## <a name="policy-dashboard"></a>Richtlinien-Dashboard

Über das **Richtlinien-Dashboard** können Sie sich schnell einen Überblick über die Richtlinien in Ihrer Organisation und den aktuellen Status der mit den einzelnen Richtlinien verbundenen Warnungen verschaffen.

- **Richtlinienname:** Der Name, der der Richtlinie im Richtlinienassistenten zugewiesen ist.
- **Aktive Warnungen:** Die Anzahl der aktiven Warnungen für jede Richtlinie.
- **Bestätigte Warnungen:** Die Gesamtzahl der Warnungen, die in den letzten 365 Tagen zu Fällen aus der Richtlinie geführt haben.
- **Aktionen für Warnungen:** Die Gesamtzahl der Warnungen, die in den letzten 365 Tagen bestätigt oder verworfen wurden.
- **Effektivität der** Richtlinie: Der Prozentsatz, der durch die Gesamtzahl der bestätigten Warnungen bestimmt wird, dividiert durch die Gesamtzahl der Aktionen, die für Warnungen ergriffen wurden (dies ist die Summe der Warnungen, die im letzten Jahr bestätigt oder verworfen wurden).
- **Aktiv:** Der Status des Falls, entweder *Ja* oder *Nein*.

![Dashboard für Richtlinien für das Insider-Risikomanagement](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Richtlinienvorlagen

Vorlagen für das Insider-Risikomanagement sind vordefinierte Richtlinienbedingungen, die die Arten von Risikoindikatoren und das von der Richtlinie verwendete Risikobewertungsmodell definieren. Bevor eine Richtlinie erstellt wird, muss ihr im Richtlinienerstellungs-Assistenten eine Vorlage zugewiesen werden. Das Insiderrisikomanagement unterstützt bis zu fünf Richtlinien für jede Richtlinienvorlage. Wenn Sie eine neue Richtlinie für Insiderrisiken mit dem Richtlinienassistenten erstellen, wählen Sie eine der folgenden Richtlinienvorlagen aus:

### <a name="data-theft-by-departing-users"></a>Datendiebstahl durch ausscheidende Benutzer

Wenn Benutzer Ihre Organisation verlassen, gibt es bestimmte Risikoindikatoren, die in der Regel mit dem Datendiebstahl durch ausscheidende Benutzer verbunden sind. Diese Richtlinienvorlage verwendet Indikatoren für die Risikobewertung und konzentriert die Erkennung und Warnungen auf diesen Risikobereich. Der Diebstahl von Daten für ausscheidende Benutzer kann das Herunterladen von Dateien aus SharePoint Online, das Drucken von Dateien und das Kopieren von Daten in persönliche Cloudnachrichten- und Speicherdienste in der Nähe ihres Arbeitsverhältnisses und Enddatums umfassen. Diese Vorlage beginnt mit der Bewertung von Risikoindikatoren im Zusammenhang mit diesen Aktivitäten und deren Korrelation mit dem Status des Benutzerarbeitsstatus.

>[!IMPORTANT]
>Wenn Sie diese Vorlage verwenden, müssen Sie einen Microsoft 365 -PERSONAL-Connector so konfigurieren, dass regelmäßig Informationen zu Terminen und Kündigungen für Benutzer in Ihrer Organisation importiert werden. Schrittweise [Anleitungen zum](import-hr-data.md) Konfigurieren des Microsoft 365 -PERSONAL-Connectors für Ihre Organisation finden Sie im Artikel zum Importieren von Daten mit dem HR-Connector.

### <a name="general-data-leaks"></a>Allgemeine Datenlecks

Der Schutz von Daten und das Verhindern von Datenlecks stellt für die meisten Organisationen eine konstante Herausforderung dar, insbesondere durch den schnellen Zunehmen neuer Daten, die von Benutzern, Geräten und Diensten erstellt werden. Benutzer sind in der Lage, Informationen über Dienste und Geräte hinweg zu erstellen, zu speichern und gemeinsam zu nutzen, die die Verwaltung von Datenlecks zunehmend komplexer und schwieriger machen. Datenlecks können eine versehentliche Übersharingung von Informationen außerhalb Ihrer Organisation oder Datendiebstahl mit böswilliger Absicht beinhalten. In Verbindung mit einer zugewiesenen Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) beginnt diese Vorlage mit der Bewertung von Echtzeiterkennungen verdächtiger SharePoint Online-Datendownloads, Datei- und Ordnerfreigaben, dem Drucken von Dateien und dem Kopieren von Daten in persönliche Cloud-Messaging- und Speicherdienste.

Wenn Sie eine Vorlage für **Datenlecks** verwenden, müssen Sie eine DLP-Richtlinie zuweisen, um Indikatoren in der Richtlinie für Insiderrisiken für Warnungen mit hohem Schweregrad in Ihrer Organisation auszulösen. Wenn eine Warnung mit hohem Schweregrad durch eine DLP-Richtlinienregel zum Office 365-Überwachungsprotokoll hinzugefügt wird, untersuchen mit dieser Vorlage erstellte Insiderrisikorichtlinien automatisch die Warnung mit hohem Schweregrad. Wenn die Warnung einen In-Scope-Benutzer enthält, der in der Richtlinie für Insiderrisiken definiert ist, wird die Warnung von der Richtlinie für Insiderrisiken als neue Warnung verarbeitet und einem Schweregrad und einer Risikobewertung für Insider zugewiesen. Mit dieser Richtlinie können Sie diese Warnung im Kontext mit anderen im Fall enthaltenen Aktivitäten auswerten.

#### <a name="data-leaks-policy-guidelines"></a>Richtlinien für Datenlecks

Berücksichtigen Sie beim Erstellen oder Ändern von DLP-Richtlinien für die Verwendung mit Richtlinien für das Insider-Risikomanagement die folgenden Richtlinien:

- Priorisieren Sie Daten-Exfiltrationsereignisse,  und wählen Sie beim Zuweisen von Vorfallberichtseinstellungen zu *"Hoch"* beim Konfigurieren von Regeln in Ihren DLP-Richtlinien selektiv aus. Beispielsweise sollte das Senden vertraulicher Dokumente an  einen bekannten Konkurrenten ein Exfiltrationsereignis mit hoher Warnungsstufe sein. Wenn Sie die  hohe Ebene  in den Vorfallberichtseinstellungen in anderen Regeln für die DLP-Richtlinie überbewerten, kann dies den Rausch im Warnungsworkflow des Insider-Risikomanagements erhöhen und es Ihren Datenermittlern und Analysten erschweren, diese Warnungen ordnungsgemäß auszuwerten. Das Zuweisen hoher  Warnungsstufen für den Zugriff auf Denialaktivitäten in den DLP-Richtlinien macht es beispielsweise schwieriger, das wirklich riskante Benutzerverhalten und die Aktivitäten auszuwerten.
- Stellen Sie sicher, dass Sie die In-Scope-Benutzer in den Richtlinien für das DLP- und das Insider-Risikomanagement verstehen und ordnungsgemäß konfigurieren. Nur Benutzer, die mithilfe der Vorlage **"Datenlecks"** als In-Scope für Richtlinien für das Insiderrisikomanagement definiert sind, werden mit hoher Schwere von Warnungen zu den DLP-Richtlinien verarbeitet. Darüber hinaus werden nur Benutzer, die in einer Regel für eine Warnung mit hohem Schweregrad als im Bereich definiert sind, von der Richtlinie für das Insider-Risikomanagement zur Prüfung geprüft. Es ist wichtig, dass Sie benutzer im Bereich nicht unwissentlich sowohl in Ihren DLP- als auch in Den-Insider-Risikorichtlinien in Konflikt stehen.

     Wenn Ihre Richtlinienregeln für DLP beispielsweise auf Benutzer im Vertriebsteam begrenzt sind  und die aus der Vorlage für Datenlecks erstellte Insiderrisikorichtlinie alle Benutzer als in den Bereich festgelegt hat, werden von der Richtlinie für Insiderrisiken nur Warnungen mit hohem Schweregrad für die Benutzer im Vertriebsteam tatsächlich verarbeiten. Die Richtlinie für Insiderrisiken erhält keine DLP-Warnungen mit hoher Priorität für Benutzer, die in diesem Beispiel nicht in den DLP-Regeln definiert sind. Wenn Ihre insider-Risikomanagementrichtlinie,  die aus Vorlagen für Datenlecks erstellt wurde, nur auf Benutzer im Vertriebsteam und die zugewiesene DLP-Richtlinie auf alle Benutzer begrenzt ist, werden von der Richtlinie für Insiderrisiken nur Warnungen mit hohem Schweregrad für Mitglieder des Vertriebsteams verwendet. Die Richtlinie für das Insider-Risikomanagement ignoriert die Warnungen des hohen Schweregrads von DLP für alle Benutzer, die nicht im Vertriebsteam sind.

- Stellen Sie  sicher, dass die Regeleinstellung für Vorfallberichte in der  DLP-Richtlinie, die für diese Vorlage für das Insiderrisikomanagement verwendet wird, für Warnungen mit hohem Schweregrad konfiguriert ist. Der *Schweregrad* "Hoher Schweregrad" ist die auslösenden Ereignisse, und Warnungen zum Insider-Risikomanagement werden nicht aus Regeln in den DLP-Richtlinien generiert, deren Feld **"Vorfallberichte"** auf *"Niedrig"* oder *"Mittel" festgelegt ist.*

    ![Warnungseinstellung für die DLP-Richtlinie](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Wenn Sie eine neue DLP-Richtlinie mithilfe der integrierten Vorlagen erstellen, müssen Sie die Option  zum Erstellen  oder Anpassen erweiterter **DLP-Regeln** auswählen, um die Einstellung für Vorfallberichte für den Hohen Schweregrad zu konfigurieren.

Jeder insider-Risikomanagementrichtlinie, die aus der Vorlage für **Datenlecks** erstellt wurde, kann nur eine DLP-Richtlinie zugewiesen werden. Erwägen Sie die Erstellung einer dedizierten DLP-Richtlinie, die die verschiedenen Aktivitäten kombiniert, die Sie erkennen möchten, und als Auslösen von Ereignissen für Insider-Risikorichtlinien, die die Vorlage für **Datenlecks** verwenden.

Schrittweise [Anleitungen zum Konfigurieren von DLP-Richtlinien](create-test-tune-dlp-policy.md) für Ihre Organisation finden Sie im Artikel zum Erstellen, Testen und Optimieren eines DLP-Richtlinienartikels.

### <a name="data-leaks-by-priority-users-preview"></a>Datenlecks nach Prioritätsbenutzern (Vorschau)

Der Schutz von Daten und das Verhindern von Datenlecks für Benutzer in Ihrer Organisation hängt möglicherweise von ihrer Position, dem Grad des Zugriffs auf vertrauliche Informationen oder dem Risikoverlauf ab. Datenlecks können das versehentliche Überschatten hochgradig vertraulicher Informationen außerhalb Ihrer Organisation oder datendiebstahl mit böswilliger Absicht beinhalten. In Verbindung mit einer zugewiesenen Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) beginnt diese Vorlage mit der Bewertung von Echtzeiterkennungen verdächtiger Aktivitäten und führt zu einer erhöhten Wahrscheinlichkeit von Warnungen und Warnungen mit höherem Schweregrad. Prioritätsbenutzer werden in [Benutzergruppen mit](insider-risk-management-settings.md#priority-user-groups-preview) Priorität definiert, die im Bereich "Einstellungen für das Insider-Risikomanagement" konfiguriert sind.

Wie bei der Vorlage **"Allgemeine Datenlecks"** müssen Sie eine DLP-Richtlinie zuweisen, um Indikatoren in der Richtlinie für Insiderrisiken für Warnungen mit hohem Schweregrad in Ihrer Organisation auszulösen. Befolgen Sie beim Erstellen einer Richtlinie mit dieser Vorlage die oben genannten Richtlinien für Datenlecks. Darüber hinaus müssen Sie der Richtlinie in den Einstellungen des **Insider-Risikomanagements** erstellte Benutzergruppen mit  >    >   Priorität zuweisen.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Datenlecks von verärgerten Benutzern (Vorschau)

Wenn Benutzer mit Arbeitsstressoren zu verärgern sind, können sie verärgert werden, was die Wahrscheinlichkeit von Insiderrisikoaktivitäten erhöhen kann. Diese Vorlage beginnt mit der Bewertung der Benutzeraktivität, wenn ein Indikator identifiziert wird, der mit Verärgerung verknüpft ist. Beispiele hierfür sind Leistungsverbesserungsbenachrichtigungen, Leistungsüberprüfungen oder Änderungen am Status auf Auftragsebene. Datenlecks für unzufriedene Benutzer können das Herunterladen von Dateien aus SharePoint Online und das Kopieren von Daten in persönliche Cloudnachrichten und Speicherdienste in der Nähe von Stressorereignissen bei Der Beschäftigung umfassen.

Wenn Sie diese Vorlage verwenden, müssen Sie auch einen Microsoft 365 -PERSONAL-Connector konfigurieren, um regelmäßig Leistungsverbesserungsbenachrichtigungen, Status der Leistungsüberprüfung oder Informationen zur Änderung auf Auftragsebene für Benutzer in Ihrer Organisation zu importieren. Schrittweise [Anleitungen zum](import-hr-data.md) Konfigurieren des Microsoft 365 -HR-Connectors für Ihre Organisation finden Sie im Artikel zum Importieren von Daten mit dem HR-Connector.

### <a name="general-security-policy-violations-preview"></a>Allgemeine Sicherheitsrichtlinienverletzungen (Vorschau)

In vielen Organisationen verfügen Benutzer über berechtigungen zum Installieren von Software auf ihren Geräten oder zum Ändern von Geräteeinstellungen zur Unterstützung ihrer Aufgaben. Entweder versehentlich oder mit böswilliger Absicht können Benutzer Schadsoftware installieren oder wichtige Sicherheitsfeatures deaktivieren, die zum Schutz von Informationen auf ihrem Gerät oder in Ihren Netzwerkressourcen beitragen. Diese Richtlinienvorlage verwendet Sicherheitswarnungen von Microsoft Defender for Endpoint, um mit der Bewertung dieser Aktivitäten zu beginnen und die Erkennung und Warnungen für diesen Risikobereich zu fokussieren. Verwenden Sie diese Vorlage, um Einblicke in Verstöße gegen Sicherheitsrichtlinien in Szenarien zu liefern, in denen Benutzer möglicherweise einen Verlauf von Sicherheitsrichtlinienverstößen haben, die ein Indikator für Insiderrisiken sein können.

Sie müssen Microsoft Defender für Endpunkt in Ihrer Organisation konfiguriert haben und Defender for Endpoint für die Integration des Insider-Risikomanagements im Defender Security Center aktivieren, um Warnungen zu Sicherheitsverletzungen zu importieren. Weitere Informationen zum Konfigurieren von Defender for Endpoint für die Integration des Insider-Risikomanagements finden Sie unter ["Konfigurieren erweiterter Features in Defender for Endpoint".](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="security-policy-violations-by-departing-users-preview"></a>Sicherheitsrichtlinienverletzungen durch verlassene Benutzer (Vorschau)

Verlassene Benutzer, ob positiv oder negativ, können höhere Risiken für Verstöße gegen Sicherheitsrichtlinien haben. Zum Schutz vor unbeabsichtigten oder böswilligen Sicherheitsverstößen für ausscheidende Benutzer verwendet diese Richtlinienvorlage Defender for Endpoint-Warnungen, um Einblicke in sicherheitsrelevante Aktivitäten zu erhalten. Zu diesen Aktivitäten gehören das Installieren von Schadsoftware oder anderer potenziell schädlicher Anwendungen sowie das Deaktivieren von Sicherheitsfeatures auf ihren Geräten. Richtlinienindikatoren werden aktiviert, nachdem Benutzer ein Austritts- oder Beendigungsdatum aus dem Microsoft 365 HR Connector als auslösendes Ereignis importiert haben.

Wenn Sie diese Vorlage verwenden, müssen Sie einen Microsoft 365 -PERSONAL-Connector so konfigurieren, dass regelmäßig Informationen zu Terminen und Kündigungen für Benutzer in Ihrer Organisation importiert werden. Schrittweise [Anleitungen zum](import-hr-data.md) Konfigurieren des Microsoft 365 -HR-Connectors für Ihre Organisation finden Sie im Artikel zum Importieren von Daten mit dem HR-Connector.

Sie müssen Microsoft Defender für Endpunkt in Ihrer Organisation konfiguriert haben und Defender for Endpoint für die Integration des Insider-Risikomanagements im Defender Security Center aktivieren, um Warnungen zu Sicherheitsverletzungen zu importieren. Weitere Informationen zum Konfigurieren von Defender for Endpoint für die Integration von Insider-Risikomanagement finden Sie unter ["Konfigurieren erweiterter Features in Defender for Endpoint".](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="security-policy-violations-by-priority-users-preview"></a>Sicherheitsrichtlinienverletzungen nach Prioritätsbenutzern (Vorschau)

Der Schutz vor Sicherheitsverstößen für Benutzer in Ihrer Organisation kann von ihrer Position, dem Grad des Zugriffs auf vertrauliche Informationen oder dem Risikoverlauf abhängen. Da Sicherheitsverstöße durch Prioritätsbenutzer möglicherweise eine outsized Auswirkung auf die kritischen Bereiche Ihrer Organisation haben, beginnt diese Richtlinienvorlage mit der Bewertung dieser Indikatoren und verwendet Microsoft Defender for Endpoint-Warnungen, um Einblicke in sicherheitsbezogene Aktivitäten für diese Benutzer zu erhalten. Dazu können die Priorität von Benutzern gehören, die Schadsoftware oder andere potenziell schädliche Anwendungen installieren und Sicherheitsfeatures auf ihren Geräten deaktivieren. Prioritätsbenutzer werden in benutzerprioritätsorientierten Benutzergruppen definiert, die im Bereich "Einstellungen für das Insider-Risikomanagement" konfiguriert sind.

Sie müssen Microsoft Defender für Endpunkt in Ihrer Organisation konfiguriert haben und Defender for Endpoint für die Integration des Insider-Risikomanagements im Defender Security Center aktivieren, um Warnungen zu Sicherheitsverletzungen zu importieren. Weitere Informationen zum Konfigurieren von Defender for Endpoint für die Integration von Insider-Risikomanagement finden Sie unter ["Konfigurieren erweiterter Features in Defender for Endpoint".](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) Darüber hinaus müssen Sie der Richtlinie in den Einstellungen des **Insider-Risikomanagements** erstellte Benutzergruppen mit  >    >   Priorität zuweisen.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Sicherheitsrichtlinienverletzungen durch verärgerte Benutzer (Vorschau)

Benutzer mit Arbeitsstressoren können ein höheres Risiko für unbeabsichtigte oder böswillige Sicherheitsrichtlinienverletzungen haben. Zu diesen Stressoren kann es gehören, dass der Benutzer in einen Leistungsverbesserungsplan, einen Status der Leistungsüberprüfung oder aus seiner aktuellen Position herabgestuft wird. Diese Richtlinienvorlage startet die Risikobewertung basierend auf diesen Indikatoren und Aktivitäten, die diesen Ereignissen für diese Benutzer zugeordnet sind.

Wenn Sie diese Vorlage verwenden, müssen Sie auch einen Microsoft 365 -PERSONAL-Connector konfigurieren, um regelmäßig Leistungsverbesserungsbenachrichtigungen, Status der Leistungsüberprüfung oder Informationen zur Änderung auf Auftragsebene für Benutzer in Ihrer Organisation zu importieren. Schrittweise [Anleitungen zum](import-hr-data.md) Konfigurieren des Microsoft 365 -HR-Connectors für Ihre Organisation finden Sie im Artikel zum Importieren von Daten mit dem HR-Connector.

Außerdem müssen Sie Microsoft Defender für Endpunkt in Ihrer Organisation konfiguriert haben und Defender for Endpoint für die Integration des Insider-Risikomanagements im Defender Security Center aktivieren, um Warnungen zu Sicherheitsverletzungen zu importieren. Weitere Informationen zum Konfigurieren von Defender for Endpoint für die Integration von Insider-Risikomanagement finden Sie unter ["Konfigurieren erweiterter Features in Defender for Endpoint".](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="policy-template-prerequisites-and-triggering-events"></a>Voraussetzungen für Richtlinienvorlagen und Auslösen von Ereignissen

Abhängig von der Vorlage, die Sie für eine Richtlinie für das Insiderrisikomanagement auswählen, variieren die auslösenden Ereignisse und Richtlinienvoraussetzungen. Triggering events are prerequisites that determine if a user is active for an insider risk management policy. Wenn ein Benutzer einer Richtlinie für das Insiderrisikomanagement hinzugefügt wird, aber kein auslösendes Ereignis hat, wird die Benutzeraktivität nicht von der Richtlinie ausgewertet, es sei denn, sie werden manuell im Benutzerdashboard hinzugefügt. Richtlinienvoraussetzungen sind erforderliche Elemente, damit die Richtlinie die Signale oder Aktivitäten empfängt, die zum Bewerten des Risikos erforderlich sind.

In der folgenden Tabelle sind die auslösenden Ereignisse und Voraussetzungen für Richtlinien aufgeführt, die aus den einzelnen Richtlinienvorlagen für das Insiderrisikomanagement erstellt wurden:

| **Richtlinienvorlage** | **Auslösen von Ereignissen für Richtlinien** | **Voraussetzungen** |
| :------------------ | :--------------------------------- | :---------------- |
| Datendiebstahl durch ausscheidende Benutzer | Datumsanzeige für Einbruch oder Beendigung vom Personalconnector | Microsoft 365 HR-Connector, konfiguriert für Datumsindikatoren für Beendigung und Termin |
| Allgemeine Datenlecks | Datenleck-Richtlinienaktivität, die eine Warnung mit hohem Schweregrad erstellt | Für Warnungen mit hohem Schweregrad konfigurierte DLP-Richtlinie |
| Datenlecks nach Prioritätsbenutzern | Datenleck-Richtlinienaktivität, die eine Warnung mit hohem Schweregrad erstellt | Für Warnungen mit hohem Schweregrad konfigurierte DLP-Richtlinie <br><br> In den Einstellungen für Insiderrisiken konfigurierte Benutzergruppen mit Priorität |
| Datenlecks von verärgerten Benutzern | Leistungsverbesserung, schlechte Leistung oder Änderungsindikatoren auf Auftragsebene vom Personalabteilungsconnector | Microsoft 365 HR-Connector, konfiguriert für Verärgerungsindikatoren |
| Verstöße gegen allgemeine Sicherheitsrichtlinien | Defensiv eingestellte Sicherheitskontrollen oder unerwünschte Software, die von Microsoft Defender for Endpoint erkannt wurden | Aktives Microsoft Defender für Endpunktabonnement <br><br> Microsoft Defender für Endpunkt integration in Microsoft 365 Compliance Center konfiguriert |
| Verstöße gegen Sicherheitsrichtlinien durch ausscheidende Benutzer | Datumsanzeigen für Die Kündigung oder Kündigung vom Personalconnector | Microsoft 365 HR-Connector, konfiguriert für Datumsindikatoren für Beendigung und Termin <br><br> Aktives Microsoft Defender für Endpunktabonnement <br><br> Microsoft Defender für Endpunkt integration in Microsoft 365 Compliance Center konfiguriert |
| Sicherheitsrichtlinienverletzungen nach Prioritätsbenutzern | Defensiv eingestellte Sicherheitskontrollen oder unerwünschte Software, die von Microsoft Defender for Endpoint erkannt wurden | Aktives Microsoft Defender für Endpunktabonnement <br><br> Microsoft Defender für Endpunkt integration in Microsoft 365 Compliance Center konfiguriert <br><br> In den Einstellungen für Insiderrisiken konfigurierte Benutzergruppen mit Priorität |
| Sicherheitsrichtlinienverletzungen durch verärgerte Benutzer | Leistungsverbesserung, schlechte Leistung oder Änderungsindikatoren auf Auftragsebene vom Personalabteilungsconnector | Microsoft 365 HR-Connector, konfiguriert für Verärgerungsindikatoren <br><br> Aktives Microsoft Defender für Endpunktabonnement <br><br> Microsoft Defender für Endpunkt integration in Microsoft 365 Compliance Center konfiguriert |

## <a name="prioritize-content-in-policies"></a>Priorisieren von Inhalten in Richtlinien

Richtlinien für das Insiderrisikomanagement unterstützen die Festlegung einer höheren Priorität für Inhalte, je nachdem, wo sie gespeichert oder klassifiziert werden. Die Angabe von Inhalten als Priorität erhöht die Risikobewertung für alle zugehörigen Aktivitäten, wodurch wiederum die Wahrscheinlichkeit erhöht wird, dass eine Warnung mit hohem Schweregrad generiert wird. Einige Aktivitäten generieren jedoch keine Warnung, es sei denn, der zugehörige Inhalt enthält integrierte oder benutzerdefinierte Typen vertraulicher Informationen oder wurde in der Richtlinie als Priorität angegeben.

Beispielsweise verfügt Ihre Organisation über eine dedizierte SharePoint-Website für ein streng vertrauliches Projekt. Datenlecks für Informationen auf dieser SharePoint-Website könnten das Projekt gefährdeten und sich erheblich auf den Erfolg auswirken. Durch die Priorisierung dieser SharePoint-Website in einer Richtlinie für Datenlecks werden die Risikobewertungen für qualifizierende Aktivitäten automatisch erhöht. Diese Priorisierung erhöht die Wahrscheinlichkeit, dass diese Aktivitäten eine Warnung zu Insiderrisiken generieren, und erhöht den Schweregrad für die Warnung.

Wenn Sie eine Richtlinie für das Insiderrisikomanagement im Richtlinienassistenten erstellen, können Sie aus den folgenden Prioritäten wählen:

- **SharePoint-Websites:** Jeder Aktivität, die allen Dateitypen in definierten SharePoint-Websites zugeordnet ist, wird eine höhere Risikobewertung zugewiesen. 
- **Typen vertraulicher** Informationen: Jeder Aktivität, die Inhalten zugeordnet ist, die Typen vertraulicher Informationen [enthalten,](sensitive-information-type-entity-definitions.md) wird eine höhere Risikobewertung zugewiesen.
- **Vertraulichkeitsbezeichnungen:** Allen Aktivitäten, die Inhalten zugeordnet sind, auf die bestimmte [Vertraulichkeitsbezeichnungen](sensitivity-labels.md) angewendet wurden, wird eine höhere Risikobewertung zugewiesen.

## <a name="create-a-new-policy"></a>Erstellen einer neuen Richtlinie

Um eine neue Richtlinie für das Insider-Risikomanagement zu erstellen, verwenden Sie den Richtlinienassistenten in der Lösung für **das Insider-Risikomanagement** im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine neue Richtlinie zu erstellen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Registerkarte **"Richtlinien"** aus. 
2. Wählen Sie **"Richtlinie erstellen"** aus, um den Richtlinienassistenten zu öffnen.
3. Füllen Sie **auf der Seite "Neue Insider-Risikorichtlinie"** die folgenden Felder aus:
    - **Name (erforderlich):** Geben Sie einen Anzeigenamen für die Richtlinie ein.
    - **Beschreibung (optional):** Geben Sie eine Beschreibung für die Richtlinie ein.
    - **Richtlinienvorlage auswählen (erforderlich):** Wählen Sie eine der [Richtlinienvorlagen](insider-risk-management-policies.md#policy-templates) aus, um die Arten von Risikoindikatoren zu definieren, die von der Richtlinie überwacht werden.

    >[!IMPORTANT]
    >Die meisten Richtlinienvorlagen verfügen über Voraussetzungen, die konfiguriert werden müssen, damit die Richtlinie relevante Warnungen generiert. Wenn Sie die geltenden Richtlinienvoraussetzungen nicht konfiguriert haben, lesen Sie "Erste Schritte mit dem [Insider-Risikomanagement".](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)

4. Wählen Sie **"Weiter"** aus, um fortzufahren.
5. Wählen Sie **auf**  der Seite "Benutzer" die Option "Benutzer oder Gruppe hinzufügen" oder "Priorität" aus, um zu definieren, welche Benutzer oder Benutzergruppen mit Priorität in der Richtlinie enthalten sind, je nach ausgewählter Richtlinienvorlage.  Aktivieren **Sie ggf. das** Kontrollkästchen Alle Benutzer und E-Mail-aktivierte Gruppen (wenn Sie keine benutzerbasierte Vorlage mit Priorität ausgewählt haben). Wählen Sie **"Weiter"** aus, um fortzufahren.
6. Auf der Seite "Angeben, welcher Inhalt priorisiert werden soll **(optional)"** können Sie die Quellen zuweisen, um höhere Risikobewertungen zu priorisieren. Einige Aktivitäten generieren jedoch keine Warnung, es sei denn, der zugehörige Inhalt enthält integrierte oder benutzerdefinierte Typen vertraulicher Informationen oder wurde auf dieser Seite als Priorität angegeben:
    - **SharePoint-Websites:** Wählen **Sie "SharePoint-Website hinzufügen"** aus, und wählen Sie die SharePoint-Organisationen aus, die Sie priorisieren möchten. Beispiel: *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Vertraulicher Informationstyp:** Wählen Sie **"Vertraulichen Informationstyp hinzufügen"** aus, und wählen Sie die Vertraulichkeitstypen aus, die Sie priorisieren möchten. Beispiel: *"US-Bankkontonummer"* und *"Kreditkartennummer"*.
    - **Vertraulichkeitsbezeichnungen:** Wählen Sie **"Vertraulichkeitsbezeichnung hinzufügen"** aus, und wählen Sie die Bezeichnungen aus, die Sie priorisieren möchten. Beispiel: *"Vertraulich"* und *"Geheim".*
7. Wählen Sie **"Weiter"** aus, um fortzufahren.
8. Auf der **Seite "Richtlinienindikatoren** auswählen" [](insider-risk-management-settings.md#indicators) werden die Indikatoren angezeigt, die Sie auf der Seite "Indikatoren für Insider-Risikoeinstellungen" als verfügbar   >  **definiert** haben. Wenn Sie  zu Beginn des Assistenten eine Vorlage für Datenlecks ausgewählt haben, müssen Sie eine DLP-Richtlinie aus der Dropdownliste der **DLP-Richtlinien** auswählen, um Triggering Indicators für die Richtlinie zu aktivieren. Wählen Sie die Indikatoren aus, die Sie auf die Richtlinie anwenden möchten. Wenn Sie die Standardmäßigen Richtlinienschwelleneinstellungen für diese Indikatoren nicht verwenden möchten, deaktivieren Sie die von **Microsoft** empfohlenen Standardschwellenwerte, und geben Sie die Schwellenwerte für jeden ausgewählten Indikator ein. Wenn Sie mindestens einen *Office-* oder Geräteindikator ausgewählt haben, wählen Sie die **Risikobewertungen** entsprechend aus.  Risikobewertungsindikatoren gelten nur für ausgewählte Indikatoren.

    >[!IMPORTANT]
    >Wenn Indikatoren auf dieser Seite nicht ausgewählt werden können, müssen Sie die Indikatoren auswählen, die Sie für alle Richtlinien auf der Seite **"Einstellungsrichtlinienindikatoren** für das Insider-Risikomanagement"  >    >  **aktivieren** möchten.

9. Wählen Sie **"Weiter"** aus, um fortzufahren.
10. Auf der **Seite "Zeitrahmen für Richtlinien"** werden die Bedingungen des [](insider-risk-management-settings.md#policy-timeframes) Aktivierungsfensters für die Richtlinie angezeigt, die auf der Seite "Richtlinien für Insider-Risikoeinstellungen" angezeigt   >   wird.
11. Wählen Sie **"Weiter"** aus, um fortzufahren.
12. Überprüfen Sie **auf** der Seite "Überprüfen" die Einstellungen, die Sie für die Richtlinie ausgewählt haben. Wählen **Sie "Bearbeiten"** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **"Senden"** aus, um die Richtlinie zu erstellen und zu aktivieren.

## <a name="update-a-policy"></a>Aktualisieren einer Richtlinie

Um eine vorhandene Richtlinie für das Insiderrisikomanagement zu aktualisieren, verwenden Sie den Richtlinienassistenten in der **Lösung** für das Insider-Risikomanagement im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine vorhandene Richtlinie zu verwalten:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Registerkarte **"Richtlinien"** aus. 
2. Wählen Sie im Richtliniendashboard die Richtlinie aus, die Sie verwalten möchten.
3. Wählen Sie auf der Seite "Richtliniendetails" die Option **"Richtlinie bearbeiten" aus.**
4. Im Richtlinienassistenten können Sie die folgenden Felder nicht bearbeiten:
    - **Name**: Der Anzeigename für die Richtlinie
    - **Richtlinienvorlage auswählen:** Die Vorlage zum Definieren der Arten von Risikoindikatoren, die von der Richtlinie überwacht werden.
5. Geben Sie im Feld Beschreibung eine neue Beschreibung für **die Richtlinie** ein. 
6. Wählen Sie **"Weiter"** aus, um fortzufahren.
7. Wählen Sie **auf**  der Seite "Benutzer" die Option "Benutzer oder Gruppe hinzufügen" oder "Priorität" aus, um zu definieren, welche Benutzer oder Benutzergruppen mit Priorität in der Richtlinie enthalten sind, je nach ausgewählter Richtlinienvorlage.  Aktivieren **Sie ggf. das** Kontrollkästchen Alle Benutzer und E-Mail-aktivierte Gruppen (wenn Sie keine benutzerbasierte Vorlage mit Priorität ausgewählt haben). Wählen Sie **"Weiter"** aus, um fortzufahren.
8. Auf der Seite angeben, welche Inhalte priorisiert werden **(optional)** können Sie die Quellen zuweisen, um höhere Risikobewertungen zu priorisieren. Einige Aktivitäten generieren jedoch keine Warnung, es sei denn, der zugehörige Inhalt enthält integrierte oder benutzerdefinierte Typen vertraulicher Informationen oder wurde auf dieser Seite als Priorität angegeben:
    - **SharePoint-Websites:** Wählen **Sie "SharePoint-Website hinzufügen"** aus, und wählen Sie die SharePoint-Organisationen aus, die Sie priorisieren möchten. Beispiel: *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Vertraulicher Informationstyp:** Wählen Sie **"Vertraulichen Informationstyp hinzufügen"** aus, und wählen Sie die Vertraulichkeitstypen aus, die Sie priorisieren möchten. Beispiel: *"US-Bankkontonummer"* und *"Kreditkartennummer"*.
    - **Vertraulichkeitsbezeichnungen:** Wählen Sie **"Vertraulichkeitsbezeichnung hinzufügen"** aus, und wählen Sie die Bezeichnungen aus, die Sie priorisieren möchten. Beispiel: *"Vertraulich"* und *"Geheim".*
9. Wählen Sie **"Weiter"** aus, um fortzufahren.
10. Auf der **Seite "Richtlinienindikatoren** auswählen" [](insider-risk-management-settings.md#indicators) werden die Indikatoren angezeigt, die Sie auf der Seite "Indikatoren für Insider-Risikoeinstellungen" als verfügbar   >  **definiert** haben. Wenn Sie  zu Beginn des Assistenten eine Vorlage für Datenlecks ausgewählt haben, müssen Sie eine DLP-Richtlinie aus der Dropdownliste der **DLP-Richtlinien** auswählen, um Triggering Indicators für die Richtlinie zu aktivieren. Wählen Sie die Indikatoren aus, die Sie auf die Richtlinie anwenden möchten. Wenn Sie die Standardmäßigen Richtlinienschwelleneinstellungen für diese Indikatoren nicht verwenden möchten, deaktivieren Sie die von **Microsoft** empfohlenen Standardschwellenwerte, und geben Sie die Schwellenwerte für jeden ausgewählten Indikator ein. Wenn Sie mindestens einen *Office-* oder Geräteindikator ausgewählt haben, wählen Sie die **Risikobewertungen** entsprechend aus.  Risikobewertungsindikatoren gelten nur für ausgewählte Indikatoren.

    >[!IMPORTANT]
    >Wenn Indikatoren auf dieser Seite nicht ausgewählt werden können, müssen Sie die Indikatoren auswählen, die Sie für alle Richtlinien auf der Seite **"Einstellungsrichtlinienindikatoren** für das Insider-Risikomanagement"  >    >  **aktivieren** möchten.

11. Wählen Sie **"Weiter"** aus, um fortzufahren.
12. Auf der **Seite "Zeitrahmen für Richtlinien"** werden die Bedingungen des [](insider-risk-management-settings.md#policy-timeframes) Aktivierungsfensters für die Richtlinie angezeigt, die auf der Seite "Richtlinien für Insider-Risikoeinstellungen" angezeigt   >   wird.
13. Wählen Sie **"Weiter"** aus, um fortzufahren.
14. Überprüfen Sie **auf** der Seite "Überprüfen" die Einstellungen, die Sie für die Richtlinie aktualisiert haben. Wählen **Sie "Bearbeiten"** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **"Senden"** aus, um die Richtlinie zu aktualisieren und zu aktivieren.

## <a name="delete-a-policy"></a>Löschen einer Richtlinie

>[!NOTE]
>Durch das Löschen einer Richtlinie werden keine aktiven oder archivierten Warnungen gelöscht, die aus der Richtlinie generiert werden.

Führen Sie die folgenden Schritte aus, um eine vorhandene Richtlinie für das Insiderrisikomanagement zu löschen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Registerkarte **"Richtlinien"** aus. 
2. Wählen Sie im Richtliniendashboard die Richtlinie aus, die Sie löschen möchten.
3. Wählen **Sie auf der** Dashboardsymbolleiste "Löschen" aus.
4. Wählen Sie **im Dialogfeld "Löschen"** **"Ja"** aus, um die Richtlinie zu löschen, oder wählen Sie **"Abbrechen"** aus, um das Dialogfeld zu schließen.
