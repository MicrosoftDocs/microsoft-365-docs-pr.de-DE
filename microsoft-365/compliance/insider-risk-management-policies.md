---
title: Richtlinien für das Risikomanagement von Insidern
description: Erfahren Sie mehr über Insider-Risikomanagementrichtlinien in Microsoft 365
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
ms.openlocfilehash: 23c2ed180606e61820c6e736e472aef0ae4933a5
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445685"
---
# <a name="insider-risk-management-policies"></a>Richtlinien für das Risikomanagement von Insidern

Richtlinien für das Risikomanagement von Insidern bestimmen, welche Benutzer in den Bereich gehören und welche Arten von Risikoindikatoren für Warnungen konfiguriert sind. Sie können schnell eine Richtlinie erstellen, die für alle Benutzer in Ihrer Organisation gilt, oder einzelne Benutzer oder Gruppen für die Verwaltung in einer Richtlinie definieren. Richtlinien unterstützen Inhaltsprioritäten, um Richtlinienbedingungen auf mehrere oder bestimmte Microsoft Teams, SharePoint-Websites, Datensensitivitätstypen und Datenbeschriftungen zu konzentrieren. Mithilfe von Vorlagen können Sie bestimmte Risikoindikatoren auswählen und Ereignisschwellenwerte für Richtlinienindikatoren anpassen, risikosentsprechende Bewertungen effektiv anpassen sowie Die Höhe und Häufigkeit von Warnungen. Darüber hinaus helfen Risikosentsprecher und Anomalieerkennungen, Benutzeraktivitäten zu identifizieren, die von höherer Bedeutung oder ungewöhnlicher sind. Mit Richtlinienfenstern können Sie den Zeitrahmen für die Anwendung der Richtlinie auf Benachrichtigungsaktivitäten definieren und die Dauer der nach der Aktivierung aktivierten Richtlinie bestimmen.

Im Konfigurationsvideo [zu Insider-Risikomanagementrichtlinien](https://www.youtube.com/watch?v=kudK5ajZTUo) finden Sie eine Übersicht darüber, wie Richtlinien, die mit integrierten Richtlinienvorlagen erstellt wurden, Ihnen helfen können, schnell Maßnahmen gegen potenzielle Risiken zu ergreifen.

## <a name="policy-dashboard"></a>Richtlinien-Dashboard

Mit **dem Richtliniendashboard** können Sie schnell die Richtlinien in Ihrer Organisation, den Status der Richtlinie, manuell Benutzer zu Richtlinien hinzufügen und den Status von Warnungen anzeigen, die jeder Richtlinie zugeordnet sind.

- **Richtlinienname**: Der Name, der der Richtlinie im Richtlinien-Assistenten zugewiesen ist.
- **Status**: Der Integritätsstatus für jede Richtlinie. Zeigt die Anzahl der Richtlinienwarnungen und Empfehlungen oder den Status *Fehlerfrei für* Richtlinien ohne Probleme an.  Sie können auf die Richtlinie klicken, um die Integritätsstatusdetails für alle Warnungen oder Empfehlungen anzuzeigen.
- **Aktive Warnungen**: Die Anzahl der aktiven Warnungen für jede Richtlinie.
- **Bestätigte Warnungen**: Die Gesamtzahl der Warnungen, die in den letzten 365 Tagen in Fällen aus der Richtlinie resultierten.
- **Aktionen für Warnungen:** Die Gesamtanzahl der Warnungen, die in den letzten 365 Tagen bestätigt oder zurückgewiesen wurden.
- **Effektivität von** Richtlinienwarnungen: Der Prozentsatz, der durch die Gesamtzahl bestätigter Warnungen dividiert wird, geteilt durch die Gesamtaktionen, die für Warnungen ergriffen wurden (dies ist die Summe der Warnungen, die im vergangenen Jahr bestätigt oder abgelehnt wurden).

![Dashboard für Insider-Risikomanagementrichtlinien](../media/insider-risk-policy-dashboard.png)

## <a name="policy-recommendations-from-analytics-preview"></a>Richtlinienempfehlungen aus der Analyse (Vorschau)

Insider-Risikoanalysen ermöglichen Es Ihnen, potenzielle Insiderrisiken in Ihrer Organisation zu evaluieren, ohne Insiderrisikorichtlinien zu konfigurieren. Diese Bewertung kann Ihre Organisation dabei unterstützen, potenzielle Bereiche mit einem höheren Benutzerrisiko zu identifizieren und den Typ und Umfang von Insider-Risikomanagementrichtlinien zu bestimmen, die Sie möglicherweise konfigurieren möchten.

Weitere Informationen zu Insider Risk Analytics und Richtlinienempfehlungen finden Sie unter [Insider risk management settings: Analytics (preview)](insider-risk-management-settings.md#analytics-preview).

## <a name="policy-templates"></a>Richtlinienvorlagen

Vorlagen für das Insiderrisikomanagement sind vordefinierte Richtlinienbedingungen, die die Arten von Risikoindikatoren und das von der Richtlinie verwendete Risikobewertungsmodell definieren. Bevor eine Richtlinie erstellt wird, muss ihr im Richtlinienerstellungs-Assistenten eine Vorlage zugewiesen werden. Das Insider-Risikomanagement unterstützt bis zu fünf Richtlinien für jede Richtlinienvorlage. Wenn Sie eine neue Insiderrisikorichtlinie mit dem Richtlinien-Assistenten erstellen, wählen Sie aus einer der folgenden Richtlinienvorlagen aus:

### <a name="data-theft-by-departing-users"></a>Datendiebstahl durch ausgehende Benutzer

Wenn Benutzer Ihre Organisation verlassen, gibt es bestimmte Risikoindikatoren, die in der Regel mit Datendiebstahl durch ausscheidende Benutzer verknüpft sind. Diese Richtlinienvorlage verwendet Exfiltrationsindikatoren für die Risikobewertung und konzentriert sich auf Erkennung und Warnungen in diesem Risikobereich. Datendiebstahl für ausscheidende Benutzer kann das Herunterladen von Dateien von SharePoint Online, das Drucken von Dateien und das Kopieren von Daten in persönliche Cloudnachrichten- und Speicherdienste in der Nähe ihrer Kündigungs- und Endtermine umfassen. Indem Sie entweder den Microsoft 365-Personalconnector oder die Option verwenden, die Löschung von Benutzerkonten in Azure Active Directory für Ihre Organisation automatisch zu überwachen, beginnt diese Vorlage mit der Bewertung von Risikoindikatoren im Zusammenhang mit diesen Aktivitäten und deren Korrelation mit dem Status der Benutzerbeschäftigung.

>[!IMPORTANT]
>Wenn Sie diese Vorlage verwenden, können Sie einen Microsoft 365 HR-Connector so konfigurieren, dass regelmäßig Informationen zu Kündigungs- und Beendigungsdatum für Benutzer in Ihrer Organisation importiert werden. Schrittweise [Anleitungen zum](import-hr-data.md) Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation finden Sie im Artikel Importieren von Daten mit dem Hr-Connector. Wenn Sie den Personalconnector nicht verwenden möchten, müssen Sie beim Konfigurieren von Triggerereignissen im Richtlinien-Assistenten die Option Benutzerkonto aus Azure AD gelöscht auswählen.

### <a name="general-data-leaks"></a>Allgemeine Datenlecks

Der Schutz von Daten und das Verhindern von Datenlecks stellt für die meisten Organisationen eine ständige Herausforderung dar, insbesondere mit dem schnellen Wachstum neuer Daten, die von Benutzern, Geräten und Diensten erstellt werden. Benutzer sind in der Lage, Informationen über Dienste und Geräte hinweg zu erstellen, zu speichern und gemeinsam zu nutzen, was die Verwaltung von Datenlecks immer komplexer und schwieriger macht. Datenlecks können versehentliche Überschatten von Informationen außerhalb Ihrer Organisation oder Datendiebstahl mit böswilliger Absicht umfassen. Mit einer zugewiesenen Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) oder dem integrierten Triggerereignis beginnt diese Vorlage mit der Bewertung von Echtzeiterkennungen verdächtiger SharePoint Online-Datendownloads, Datei- und Ordnerfreigabe, Drucken von Dateien und Kopieren von Daten in persönliche Cloudnachrichten- und Speicherdienste.

Wenn Sie eine Vorlage für *Datenlecks* verwenden, können Sie eine DLP-Richtlinie zuweisen, um Indikatoren in der Insiderrisikorichtlinie für Warnungen mit hohem Schweregrad in Ihrer Organisation auszulösen. Wenn eine Warnung mit hohem Schweregrad durch eine DLP-Richtlinienregel zum Office 365-Überwachungsprotokoll hinzugefügt wird, untersuchen Mit dieser Vorlage erstellte Insiderrisikorichtlinien automatisch die DLP-Warnung mit hohem Schweregrad. Wenn die Warnung einen In-Scope-Benutzer enthält, der in der Insiderrisikorichtlinie definiert ist, wird die Warnung von der Insiderrisikorichtlinie als neue Warnung verarbeitet und einem Insiderrisikoschweregrad und einer Risikobewertung zugewiesen. Mit dieser Richtlinie können Sie diese Warnung im Kontext mit anderen In diesem Fall enthaltenen Aktivitäten auswerten. Wenn Sie keine DLP-Richtlinie auswählen, müssen Sie das integrierte auslösende Ereignis auswählen.

#### <a name="data-leaks-policy-guidelines"></a>Richtlinien für Datenlecks

Berücksichtigen Sie beim Erstellen oder Ändern von DLP-Richtlinien für die Verwendung mit Richtlinien für das Insiderrisikomanagement die folgenden Richtlinien:

- Priorisieren Sie Daten-Exfiltrationsereignisse,  und weisen Sie beim Konfigurieren von Regeln in Ihren DLP-Richtlinien beim Zuweisen von Vorfallberichtseinstellungen zu *High* selektiv zu. Beispielsweise sollte das Senden vertraulicher Dokumente an  einen bekannten Konkurrenten ein Exfiltrationsereignis mit hoher Warnungsstufe sein. Das Über zuweisen  der Hohen  Ebene in den Einstellungen für Vorfallberichte in anderen DLP-Richtlinienregeln kann das Rauschen im Workflow für Insider-Risikomanagementwarnungen erhöhen und es für Datenermittler und Analysten erschweren, diese Warnungen ordnungsgemäß auszuwerten. Das Zuweisen hoher  Benachrichtigungsebenen für den Zugriff auf Denial-Aktivitäten in DLP-Richtlinien macht es beispielsweise schwieriger, wirklich riskante Benutzerverhalten und -aktivitäten zu bewerten.
- Stellen Sie sicher, dass Sie die In-Scope-Benutzer sowohl in den DLP- als auch in den Insider-Risikomanagementrichtlinien verstehen und ordnungsgemäß konfigurieren. Nur Benutzer, die mithilfe der Vorlage **Datenlecks** als In-Scope für Insider-Risikomanagementrichtlinien definiert sind, werden mit hohem Schweregrad DLP-Richtlinienwarnungen verarbeitet. Darüber hinaus werden nur Benutzer, die in einer Regel für eine DLP-Warnung mit hohem Schweregrad als In-Scope definiert sind, von der Insider-Risikomanagementrichtlinie zur Prüfung geprüft. Es ist wichtig, dass Sie nicht unwissentlich In-Scope-Benutzer sowohl in Ihren DLP- als auch in Insiderrisikorichtlinien in Konflikt bringen.

     Wenn Ihre DLP-Richtlinienregeln beispielsweise nur auf Benutzer im Vertriebsteam begrenzt sind  und die in der Vorlage Datenlecks erstellte Insiderrisikorichtlinie alle Benutzer als in-Scope definiert hat, werden in der Richtlinie für Insiderrisiken nur DLP-Warnungen mit hohem Schweregrad für die Benutzer im Vertriebsteam tatsächlich verarbeiten. Die Richtlinie für Insiderrisiken erhält keine DLP-Warnungen mit hoher Priorität für Benutzer, die nicht in den DLP-Regeln in diesem Beispiel definiert sind. Wenn Ihre insider risk management policy created from **Data leaks** templates hingegen nur auf Benutzer im Vertriebsteam begrenzt ist und die zugewiesene DLP-Richtlinie auf alle Benutzer begrenzt ist, werden in der Richtlinie für Insiderrisiken nur DLP-Warnungen mit hohem Schweregrad für Mitglieder des Vertriebsteams verarbeiten. Die Insider-Risikomanagementrichtlinie ignoriert DLP-Warnungen mit hohem Schweregrad für alle Benutzer, die nicht im Vertriebsteam sind.

- Stellen Sie **sicher,** dass die Regeleinstellung für Vorfälleberichte in der  für diese Vorlage für das Insiderrisikomanagement verwendeten DLP-Richtlinie für Warnungen mit hohem Schweregrad konfiguriert ist. Der *Schweregrad* "Hoher Schweregrad" ist die auslösenden Ereignisse, und Warnungen zum  Risikomanagement von Insidern werden nicht aus Regeln in DLP-Richtlinien generiert, und das Feld Vorfallberichte ist auf *"Niedrig"* oder *"Mittel" festgelegt.*

    ![Warnungseinstellung für DLP-Richtlinien](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Beim Erstellen einer neuen DLP-Richtlinie mithilfe der integrierten Vorlagen müssen Sie die Option Erweiterte  **DLP-Regeln**  erstellen oder anpassen auswählen, um die Einstellung Für Vorfälleberichte für den Hohen Schweregrad zu konfigurieren.

Jeder Insider-Risikomanagementrichtlinie, die aus der **Vorlage Datenlecks** erstellt wurde, kann nur eine DLP-Richtlinie zugewiesen werden. Erwägen Sie, eine dedizierte DLP-Richtlinie zu erstellen, die die verschiedenen Aktivitäten kombiniert, die Sie erkennen und als Auslösen von Ereignissen für Insiderrisikorichtlinien verwenden, die die Vorlage **Datenlecks** verwenden.

Schrittweise [Anleitungen zum](create-test-tune-dlp-policy.md) Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie im Artikel Erstellen, Testen und Optimieren eines DLP-Richtlinienartikels.

### <a name="data-leaks-by-priority-users-preview"></a>Datenlecks nach Prioritätsbenutzern (Vorschau)

Der Schutz von Daten und das Verhindern von Datenlecks für Benutzer in Ihrer Organisation kann von ihrer Position, dem Grad des Zugriffs auf vertrauliche Informationen oder dem Risikoverlauf abhängen. Datenlecks können versehentliche Überschatten von hochsensiblen Informationen außerhalb Ihrer Organisation oder Datendiebstahl mit böswilliger Absicht umfassen. Mit einer zugewiesenen Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) beginnt diese Vorlage mit der Bewertung von Echtzeiterkennungen verdächtiger Aktivitäten und führt zu einer erhöhten Wahrscheinlichkeit von Insiderrisikowarnungen und Warnungen mit höherem Schweregrad. Prioritätsbenutzer werden in [bevorzugten Benutzergruppen definiert,](insider-risk-management-settings.md#priority-user-groups-preview) die im Bereich Insider risk management settings konfiguriert sind.

Wie bei der **Vorlage Allgemeine Datenlecks** müssen Sie eine DLP-Richtlinie zuweisen, um Indikatoren in der Insiderrisikorichtlinie für Warnungen mit hohem Schweregrad in Ihrer Organisation auszulösen. Befolgen Sie beim Erstellen einer Richtlinie mit dieser Vorlage die oben genannten Richtlinien für Datenlecks. Darüber hinaus müssen Sie der Richtlinie in Den Einstellungen für insider risk **management** erstellte Benutzergruppen Priorität  >    >   zuweisen.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Datenlecks durch verärgerte Benutzer (Vorschau)

Wenn Benutzer Mitarbeitsstressoren haben, werden sie möglicherweise unzufrieden, was die Wahrscheinlichkeit von Insiderrisikoaktivitäten erhöhen kann. Diese Vorlage beginnt mit der Bewertung der Benutzeraktivität, wenn ein Indikator identifiziert wird, der mit Unzufriedenen verknüpft ist. Beispiele hierfür sind Leistungsverbesserungsbenachrichtigungen, Leistungsüberprüfungen oder Änderungen am Status der Auftragsebene. Datenlecks für unzufriedene Benutzer können das Herunterladen von Dateien aus SharePoint Online und das Kopieren von Daten in persönliche Cloudnachrichten- und Speicherdienste in der Nähe von Stressorereignissen umfassen.

Wenn Sie diese Vorlage verwenden, müssen Sie auch einen Microsoft 365 HR-Connector konfigurieren, um regelmäßig Leistungsverbesserungsbenachrichtigungen, Status der Leistungsüberprüfung oder Änderungsinformationen auf Auftragsebene für Benutzer in Ihrer Organisation zu importieren. Schrittweise [Anleitungen zum](import-hr-data.md) Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation finden Sie im Artikel Importieren von Daten mit dem Hr-Connector.

### <a name="general-security-policy-violations-preview"></a>Allgemeine Sicherheitsrichtlinienverletzungen (Vorschau)

In vielen Organisationen haben Benutzer die Berechtigung, Software auf ihren Geräten zu installieren oder Geräteeinstellungen zu ändern, um ihre Aufgaben zu erledigen. Entweder versehentlich oder mit böswilliger Absicht können Benutzer Schadsoftware installieren oder wichtige Sicherheitsfeatures deaktivieren, die zum Schutz von Informationen auf ihrem Gerät oder in Ihren Netzwerkressourcen beitragen. Diese Richtlinienvorlage verwendet Sicherheitswarnungen von Microsoft Defender for Endpoint, um mit der Bewertung dieser Aktivitäten zu beginnen und die Erkennung und Warnungen für diesen Risikobereich zu fokussieren. Verwenden Sie diese Vorlage, um Einblicke in Sicherheitsrichtlinienverletzungen in Szenarien zu liefern, in denen Benutzer möglicherweise einen Verlauf von Sicherheitsrichtlinienverstößen haben, die ein Indikator für Insiderrisiken sein können.

Sie müssen Microsoft Defender for Endpoint in Ihrer Organisation konfigurieren und Defender for Endpoint für insider risk management integration in das Defender Security Center aktivieren, um Sicherheitsverletzungswarnungen zu importieren. Weitere Informationen zum Konfigurieren von Defender for Endpoint für insider risk management integration finden Sie unter [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-departing-users-preview"></a>Sicherheitsrichtlinienverletzungen durch ausgehende Benutzer (Vorschau)

Ausgehende Benutzer, unabhängig davon, ob sie positive oder negative Konditionen verlassen, können höhere Risiken für Sicherheitsrichtlinienverletzungen haben. Zum Schutz vor unbeabsichtigten oder böswilligen Sicherheitsverstößen für ausscheidende Benutzer verwendet diese Richtlinienvorlage Defender for Endpoint-Warnungen, um Einblicke in sicherheitsrelevante Aktivitäten zu erhalten. Zu diesen Aktivitäten gehören das Installieren von Schadsoftware oder anderen potenziell schädlichen Anwendungen sowie das Deaktivieren von Sicherheitsfeatures auf ihren Geräten. Indem Sie entweder den [Microsoft 365-Personalconnector](import-hr-data.md) oder die Option verwenden, die Löschung von Benutzerkonten in Azure Active Directory für Ihre Organisation automatisch zu überwachen, beginnt diese Vorlage mit der Bewertung von Risikoindikatoren im Zusammenhang mit diesen Sicherheitsaktivitäten und deren Korrelation mit dem Status der Benutzerbeschäftigung.

Sie müssen Microsoft Defender for Endpoint in Ihrer Organisation konfigurieren und Defender for Endpoint für insider risk management integration in das Defender Security Center aktivieren, um Sicherheitsverletzungswarnungen zu importieren. Weitere Informationen zum Konfigurieren von Defender for Endpoint für insider risk management integration finden Sie unter [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-priority-users-preview"></a>Sicherheitsrichtlinienverletzungen durch Prioritätsbenutzer (Vorschau)

Der Schutz vor Sicherheitsverletzungen für Benutzer in Ihrer Organisation kann von ihrer Position, dem Grad des Zugriffs auf vertrauliche Informationen oder dem Risikoverlauf abhängen. Da Sicherheitsverletzungen durch Prioritätsbenutzer erhebliche Auswirkungen auf die kritischen Bereiche Ihrer Organisation haben können, beginnt diese Richtlinienvorlage mit der Bewertung dieser Indikatoren und verwendet Microsoft Defender for Endpoint-Warnungen, um Einblicke in sicherheitsrelevante Aktivitäten für diese Benutzer zu erhalten. Zu diesen Aktivitäten können die Prioritätsbenutzer gehören, die Schadsoftware oder andere potenziell schädliche Anwendungen installieren und Sicherheitsfeatures auf ihren Geräten deaktivieren. Prioritätsbenutzer werden in bevorzugten Benutzergruppen definiert, die im Bereich Insider risk management settings konfiguriert sind.

Sie müssen Microsoft Defender for Endpoint in Ihrer Organisation konfigurieren und Defender for Endpoint für insider risk management integration in das Defender Security Center aktivieren, um Sicherheitsverletzungswarnungen zu importieren. Weitere Informationen zum Konfigurieren von Defender for Endpoint für insider risk management integration finden Sie unter [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center). Darüber hinaus müssen Sie der Richtlinie in Den Einstellungen für insider risk **management** erstellte Benutzergruppen Priorität  >    >   zuweisen.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Sicherheitsrichtlinienverletzungen durch verärgerte Benutzer (Vorschau)

Benutzer mit Beschäftigungsstressoren können ein höheres Risiko für unbeabsichtigte oder böswillige Sicherheitsrichtlinienverletzungen haben. Zu diesen Stressoren kann der Benutzer gehören, der in einen Leistungsverbesserungsplan, den Status der Leistungsüberprüfung oder von seiner aktuellen Position herabgestuft wird. Diese Richtlinienvorlage startet die Risikobewertung basierend auf diesen Indikatoren und Aktivitäten, die diesen Ereignissen für diese Benutzer zugeordnet sind.

Wenn Sie diese Vorlage verwenden, müssen Sie auch einen Microsoft 365 HR-Connector konfigurieren, um regelmäßig Leistungsverbesserungsbenachrichtigungen, Status der Leistungsüberprüfung oder Änderungsinformationen auf Auftragsebene für Benutzer in Ihrer Organisation zu importieren. Schrittweise [Anleitungen zum](import-hr-data.md) Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation finden Sie im Artikel Importieren von Daten mit dem Hr-Connector.

Außerdem müssen Sie Microsoft Defender for Endpoint in Ihrer Organisation konfigurieren und Defender for Endpoint für die Integration von Insider-Risikomanagement im Defender Security Center aktivieren, um Sicherheitsverletzungswarnungen zu importieren. Weitere Informationen zum Konfigurieren von Defender for Endpoint für insider risk management integration finden Sie unter [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="policy-template-prerequisites-and-triggering-events"></a>Voraussetzungen für Richtlinienvorlagen und auslösende Ereignisse

Je nach Vorlage, die Sie für eine Insider-Risikomanagementrichtlinie auswählen, variieren die auslösenden Ereignisse und Richtlinienvoraussetzungen. Auslösen von Ereignissen sind Voraussetzungen, die bestimmen, ob ein Benutzer für eine Insider-Risikomanagementrichtlinie aktiv ist. Wenn ein Benutzer einer Insider-Risikomanagementrichtlinie hinzugefügt wird, aber kein auslösendes Ereignis hat, wird die Benutzeraktivität nicht von der Richtlinie ausgewertet, es sei denn, sie werden manuell im Benutzerdashboard hinzugefügt. Richtlinienvoraussetzungen sind erforderliche Elemente, damit die Richtlinie die Signale oder Aktivitäten empfängt, die zum Bewerten des Risikos erforderlich sind.

In der folgenden Tabelle sind die auslösenden Ereignisse und Voraussetzungen für Richtlinien aufgeführt, die aus jeder Vorlage für Insiderrisikomanagementrichtlinien erstellt wurden:

| **Richtlinienvorlage** | **Auslösen von Ereignissen für Richtlinien** | **Voraussetzungen** |
| :------------------ | :--------------------------------- | :---------------- |
| Datendiebstahl durch ausgehende Benutzer | Anzeige des Kündigungs- oder Kündigungsdatums vom Personalabteilungsconnector | (optional) Microsoft 365 HR-Connector, konfiguriert für Datumsindikatoren für Beendigung und Kündigung oder aktivierte Azure Active Directory-Integration |
| Allgemeine Datenlecks | Datenleckrichtlinienaktivität, die eine Warnung mit hohem Schweregrad erstellt | (optional) DLP-Richtlinie, die für Warnungen mit hohem Schweregrad oder integriertes Daten-Exfiltrations-Triggerereignis konfiguriert ist |
| Datenlecks nach Prioritätsbenutzern | Datenleckrichtlinienaktivität, die eine Warnung mit hohem *Schweregrad* oder integrierte Exfiltrationsereignisauslöser erstellt | (optional) Für Warnungen mit hohem Schweregrad konfigurierte DLP-Richtlinie <br><br> In Insiderrisikoeinstellungen konfigurierte Benutzergruppen mit Priorität |
| Datenlecks durch unzufriedene Benutzer | Leistungsverbesserung, leistungsärmere Leistung oder Änderungsindikatoren auf Auftragsebene vom Personalabteilungsconnector | Microsoft 365 HR-Connector, konfiguriert für Unzufriedene Indikatoren |
| Verstöße gegen allgemeine Sicherheitsrichtlinien | Schutz vor Sicherheitskontrollen oder unerwünschter Software, die von Microsoft Defender for Endpoint erkannt werden | Aktives Microsoft Defender for Endpoint-Abonnement <br><br> Microsoft Defender for Endpoint-Integration in microsoft 365 Compliance Center konfiguriert |
| Sicherheitsrichtlinienverletzungen durch ausscheidende Benutzer | Kündigungs- oder Beendigungsdatumsindikatoren aus der Löschung des Personalconnector oder Azure Active Directory-Kontos | (optional) Microsoft 365 HR-Connector, konfiguriert für Datumsindikatoren für Kündigungen und Kündigungen <br><br> Aktives Microsoft Defender for Endpoint-Abonnement <br><br> Microsoft Defender for Endpoint-Integration in microsoft 365 Compliance Center konfiguriert |
| Sicherheitsrichtlinienverletzungen durch Prioritätsbenutzer | Schutz vor Sicherheitskontrollen oder unerwünschter Software, die von Microsoft Defender for Endpoint erkannt werden | Aktives Microsoft Defender for Endpoint-Abonnement <br><br> Microsoft Defender for Endpoint-Integration in microsoft 365 Compliance Center konfiguriert <br><br> In Insiderrisikoeinstellungen konfigurierte Benutzergruppen mit Priorität |
| Sicherheitsrichtlinienverletzungen durch verärgerte Benutzer | Leistungsverbesserung, leistungsärmere Leistung oder Änderungsindikatoren auf Auftragsebene vom Personalabteilungsconnector | Microsoft 365 HR-Connector, konfiguriert für Unzufriedene Indikatoren <br><br> Aktives Microsoft Defender for Endpoint-Abonnement <br><br> Microsoft Defender for Endpoint-Integration in microsoft 365 Compliance Center konfiguriert |

## <a name="prioritize-content-in-policies"></a>Priorisieren von Inhalten in Richtlinien

Insider-Risikomanagementrichtlinien unterstützen die Angabe einer höheren Priorität für Inhalte, je nachdem, wo sie gespeichert oder wie sie klassifiziert werden. Wenn Sie Inhalte als Priorität angeben, erhöht sich die Risikosentwertung für alle zugeordneten Aktivitäten, was wiederum die Wahrscheinlichkeit erhöht, eine Warnung mit hohem Schweregrad zu generieren. Bei einigen Aktivitäten wird jedoch keine Warnung generiert, es sei denn, der zugehörige Inhalt enthält integrierte oder benutzerdefinierte Typen vertraulicher Informationen oder wurde als Priorität in der Richtlinie angegeben.

Beispielsweise verfügt Ihre Organisation über eine dedizierte SharePoint-Website für ein streng vertrauliches Projekt. Datenlecks für Informationen auf dieser SharePoint-Website könnten das Projekt gefährdeten und sich erheblich auf den Erfolg auswirken. Durch die Priorisierung dieser SharePoint-Website in einer Richtlinie für Datenlecks werden die Risikobewertungen für qualifizierende Aktivitäten automatisch erhöht. Diese Priorisierung erhöht die Wahrscheinlichkeit, dass diese Aktivitäten eine Insiderrisikowarnung generieren, und erhöht den Schweregrad für die Warnung.

Wenn Sie eine Insider-Risikomanagementrichtlinie im Richtlinien-Assistenten erstellen, können Sie aus den folgenden Prioritäten wählen:

- **SharePoint-Websites:** Jeder Aktivität, die allen Dateitypen in definierten SharePoint-Websites zugeordnet ist, wird eine höhere Risikopunktzahl zugewiesen. 
- **Typen vertraulicher** Informationen: Jeder Aktivität, die Inhalten zugeordnet ist, die Typen vertraulicher Informationen [enthalten,](sensitive-information-type-entity-definitions.md) wird eine höhere Risikopunktzahl zugewiesen.
- **Vertraulichkeitsbezeichnungen**: Jeder Aktivität, die Inhalten zugeordnet ist, auf die bestimmte [Vertraulichkeitsbezeichnungen](sensitivity-labels.md) angewendet wurden, wird eine höhere Risikopunktzahl zugewiesen.

## <a name="sequence-detection-preview"></a>Sequenzerkennung (Vorschau)

Riskante Aktivitäten treten möglicherweise nicht als isolierte Ereignisse auf. Diese Risiken sind häufig Teil einer größeren Abfolge von Ereignissen. Eine Sequenz ist eine Gruppe von zwei oder mehr Benutzeraktivitäten, die eine nach der anderen ausgeführt werden, die ein erhöhtes Risiko nahelegen kann. Die Identifizierung dieser verwandten Aktivitäten ist ein wichtiger Bestandteil der Bewertung des Gesamtrisikos. Wenn die Sequenzerkennung für Richtlinien für Datendiebstahl oder Datenlecks aktiviert  ist, werden Einblicke aus Sequenzinformationsaktivitäten auf der Registerkarte Benutzeraktivität in einem Fall für insider risk management angezeigt. Die folgenden Richtlinienvorlagen unterstützen die Sequenzerkennung:

- Datendiebstahl durch ausgehende Benutzer
- Allgemeine Datenlecks
- Datenlecks nach Prioritätsbenutzern
- Datenlecks durch unzufriedene Benutzer

Diese Insider-Risikomanagementrichtlinien können bestimmte Indikatoren und die Reihenfolge verwenden, in der sie auftreten, um jeden Schritt in einer Abfolge von Risiken zu erkennen. Dateinamen werden beim Zuordnen von Aktivitäten in einer Sequenz verwendet. Diese Risiken sind in vier Hauptkategorien von Aktivitäten unterteilt:

- **Sammlung**: Diese Kategoriesignale konzentrieren sich auf Downloadaktivitäten von Richtlinienbenutzern in einem Bereich. Eine Beispielaktivität in dieser Kategorie wäre das Herunterladen von Dateien von SharePoint-Websites.
- **Exfiltration:** Diese Kategoriesignale konzentrieren sich auf die Freigabe oder Extraktion von internen und externen Quellen durch Richtlinienbenutzer im Bereich. Eine Beispielaktivität in dieser Kategorie wäre das Senden von E-Mails mit Anlagen aus Ihrer Organisation an externe Empfänger.
- **Verschleierung:** Diese Kategoriesignale konzentrieren sich auf die Maskierung riskanter Aktivitäten durch Richtlinienbenutzer in einem Bereich. Eine Beispielaktivität in dieser Kategorie wäre das Umbenennen von Dateien auf einem Gerät.
- **Bereinigung:** Diese Kategoriesignale konzentrieren sich auf Löschaktivitäten von Richtlinienbenutzern in einem Bereich. Eine Beispielaktivität in dieser Kategorie wäre das Löschen von Dateien von einem Gerät.

>[!NOTE]
>Die Sequenzerkennung verwendet Indikatoren, die in den globalen Einstellungen für insider risk management aktiviert sind, und Indikatoren, die in einer Richtlinie ausgewählt sind. Wenn keine geeigneten Indikatoren ausgewählt sind, funktioniert die Sequenzerkennung nicht.

Sie können individuelle Schwellenwerteinstellungen für jeden Sequenzerkennungstyp anpassen, wenn sie in der Richtlinie konfiguriert sind. Diese Schwellenwerteinstellungen passen Warnungen basierend auf dem Umfang der Dateien an, die der Sequenz zugeordnet sind.

Weitere Informationen zur Sequenzerkennungsverwaltung in der Ansicht **Benutzeraktivität** finden Sie unter [Insider risk management cases: User activity](insider-risk-management-cases.md#user-activity).

## <a name="cumulative-exfiltration-detection-preview"></a>Kumulative Exfiltrationserkennung (Vorschau)

Insider-Risikoindikatoren helfen, ungewöhnliche Risikoaktivitäten zu identifizieren, wenn sie täglich für Benutzer ausgewertet werden, die für Insiderrisikorichtlinien in den Bereich gehören. Die kumulierte Exfiltrationserkennung verwendet Machine Learning-Modelle, um zu ermitteln, wann Benutzer-Exfiltrationsaktivitäten die durchschnittlichen Werte der Organisation überschreiten, wenn sie im Laufe der Zeit und über mehrere Exfiltrationsaktivitätstypen gemessen werden. Insider-Risikomanagementanalysten und -ermittler können kumulative Erkenntnisse zur Exfiltrationserkennung verwenden, um Exfiltrationsaktivitäten zu identifizieren, die in der Regel keine Warnungen generieren, aber über dem für ihre Organisation typischen Wert liegen. Einige Beispiele sind möglicherweise ausgehende Benutzer, die Daten über mehrere Tage hinweg langsam exfiltrieren, oder wenn Benutzer Daten wiederholt über mehrere Kanäle mehr als üblich für die Datenfreigabe für Ihre Organisation freigeben.

Die kumulierte Exfiltrationserkennung ist standardmäßig aktiviert, wenn die folgenden Richtlinienvorlagen verwendet werden:

- Datendiebstahl durch ausgehende Benutzer
- Allgemeine Datenlecks
- Datenlecks nach Prioritätsbenutzern
- Datenlecks durch unzufriedene Benutzer

>[!NOTE]
>Die kumulierte Exfiltrationserkennung verwendet Exfiltrationsindikatoren, die in den globalen Einstellungen für insider risk management und exfiltration indicators aktiviert sind, die in einer Richtlinie ausgewählt sind. Die kumulierte Exfiltrationserkennung wird also nur für die ausgewählten erforderlichen Exfiltrationsindikatoren ausgewertet.

Wenn die kumulierte Exfiltrationserkennung für Datendiebstahl- oder Datenleckrichtlinien aktiviert  ist, werden Einblicke aus kumulierten Exfiltrationsaktivitäten auf der Registerkarte Benutzeraktivität in einem Fall für insider risk management angezeigt.

Weitere Informationen zum Benutzeraktivitätsmanagement finden Sie unter [Insider risk management cases: User activities](insider-risk-management-cases.md#user-activity).

## <a name="policy-health-preview"></a>Richtlinieninte health (Vorschau)

Der Status der Richtlinieninte health gibt Ihnen Einblicke in potenzielle Probleme mit Ihren Insider-Risikomanagementrichtlinien. Die Spalte Status auf der Registerkarte Richtlinien kann Sie vor Richtlinienproblemen warnen, die verhindern können, dass Benutzeraktivitäten gemeldet werden oder warum die Anzahl der Aktivitätswarnungen ungewöhnlich ist. Der Integritätsstatus der Richtlinie kann auch bestätigen, dass die Richtlinie fehlerfrei ist und keine Aufmerksamkeit oder Konfigurationsänderungen benötigt.

Wenn Probleme mit einer Richtlinie auftreten, zeigt der Status des Richtlinienstatus Benachrichtigungswarnungen und Empfehlungen an, mit deren Hilfe Sie Maßnahmen zur Lösung von Richtlinienproblemen ergreifen können. Mit diesen Benachrichtigungen können Sie die folgenden Probleme beheben:

- Richtlinien mit unvollständiger Konfiguration. Zu diesen Problemen können fehlende Benutzer oder Gruppen in der Richtlinie oder andere unvollständige Richtlinienkonfigurationsschritte gehören.
- Richtlinien mit Problemen mit der Indikatorkonfiguration. Indikatoren sind ein wichtiger Bestandteil jeder Richtlinie. Wenn Indikatoren nicht konfiguriert sind oder zu wenige Indikatoren ausgewählt sind, bewertet die Richtlinie riskante Aktivitäten möglicherweise nicht wie erwartet.
- Richtlinienauslöser funktionieren nicht, oder Richtlinienauslöseranforderungen sind nicht ordnungsgemäß konfiguriert. Die Richtlinienfunktionalität kann von anderen Diensten oder Konfigurationsanforderungen abhängen, um auslösende Ereignisse effektiv zu erkennen, um die Zuweisung von Risikobewertungen für Benutzer in der Richtlinie zu aktivieren. Diese Abhängigkeiten können Probleme mit der Connectorkonfiguration, der Microsoft Defender for Endpoint-Benachrichtigungsfreigabe oder Konfigurationseinstellungen für Richtlinien für die Verhinderung von Datenverlust enthalten.
- Volumenbeschränkungen nähern sich oder überschreiten Grenzwerte. Insider risk management policies use numerous Microsoft 365 services and endpoints to aggregate risk activity signals. Abhängig von der Anzahl der Benutzer in Ihren Richtlinien können Volumenbeschränkungen die Identifizierung und Berichterstellung von Risikoaktivitäten verzögern. Weitere Informationen zu diesen Grenzwerten finden Sie im Abschnitt Richtlinienvorlagenbeschränkungen in diesem Artikel.

Um den Integritätsstatus einer Richtlinie schnell anzeigen zu können, navigieren Sie auf der Registerkarte Richtlinie und in der Spalte Status. Hier sehen Sie die folgenden Richtlinienstatusoptionen für jede Richtlinie:

- Fehlerfrei: Es wurden keine Probleme mit der Richtlinie identifiziert.
- Empfehlungen: Es gibt einige Probleme mit der Richtlinie, die möglicherweise verhindern, dass die Richtlinie wie erwartet ausgeführt wird.
- Warnungen: Es gibt Probleme mit der Richtlinie, die verhindern, dass riskante Aktivitäten identifiziert werden.

Weitere Informationen zu Empfehlungen oder Warnungen finden Sie unter Auswählen einer Richtlinie auf der **Registerkarte** Richtlinie, um die Richtliniendetailsekarte zu öffnen. Weitere Informationen zu den Empfehlungen und Warnungen, einschließlich Anleitungen zur Problembe beheben, finden Sie im Abschnitt Benachrichtigungen der Detailkarte.

![Integrität von Insider-Risikomanagementrichtlinien](../media/insider-risk-policy-health.png)

In der folgenden Tabelle finden Sie weitere Informationen zu Empfehlungen und Warnbenachrichtigungen und Aktionen zur Lösung potenzieller Probleme.

|**Benachrichtigungen**|**Richtlinienvorlagen**|**Ursachen / Versuchen Sie, diese Aktion zu beheben**|
|:------------------------|:-------------------|:---------------------------|
| Richtlinie weist Aktivität keine Risikoergebnisse zu | Alle Richtlinienvorlagen | Möglicherweise möchten Sie den Richtlinienbereich überprüfen und die Ereigniskonfiguration auslösen, damit die Richtlinie Der Aktivität Risikobewertungen zuweisen kann. <br><br> 1. Überprüfen Sie die Benutzer, die für die Richtlinie ausgewählt sind. Wenn Sie nur wenige Benutzer ausgewählt haben, können Sie zusätzliche Benutzer auswählen. <br> 2. Wenn Sie einen Hr-Connector verwenden, überprüfen Sie, ob Ihr Hr-Connector die richtigen Daten sendet. <br> 3. Wenn Sie eine DLP-Richtlinie als auslösendes Ereignis verwenden, überprüfen Sie ihre DLP-Richtlinienkonfiguration, um sicherzustellen, dass sie für die Verwendung in dieser Richtlinie konfiguriert ist. <br> 4. Überprüfen Sie für Sicherheitsverletzungsrichtlinien den Microsoft Defender for Endpoint-Warnungstriagestatus, der unter Insider risk settings > Intelligent detections ausgewählt ist. Vergewissern Sie sich, dass der Warnungsfilter nicht zu schmal ist. |
| Richtlinie hat keine Warnungen generiert | Alle Richtlinienvorlagen | Möglicherweise sollten Sie die Richtlinienkonfiguration überprüfen, damit Sie die Bewertung der Aktivität analysieren, die Ihnen am Ende am ende am liegen. <br><br> 1. Vergewissern Sie sich, dass Sie Indikatoren ausgewählt haben, die Sie punkten möchten. Wenn mehr Indikatoren ausgewählt sind, werden den Aktivitäten Risikoergebnisse zugewiesen. <br> 2. Überprüfen sie die Anpassung des Schwellenwerts für die Richtlinie. Wenn die ausgewählten Schwellenwerte nicht mit der Risikotoleranz Ihrer Organisation in Einklang stehen, passen Sie die Auswahl so an, dass Warnungen basierend auf Ihren bevorzugten Schwellenwerten erstellt werden. <br> 3. Überprüfen Sie die für die Richtlinie ausgewählten Benutzer und Gruppen. Bestätigen Sie, dass Sie alle zutreffenden Benutzer und Gruppen ausgewählt haben. <br> 4. Bestätigen Sie bei Sicherheitsverletzungsrichtlinien, dass Sie den Warnungstriagestatus ausgewählt haben, den Sie für Microsoft Defender for Endpoint-Warnungen in Intelligenten Erkennungen in den Einstellungen überprüfen möchten.|
| In dieser Richtlinie sind keine Benutzer oder Gruppen enthalten | Alle Richtlinienvorlagen | Benutzer oder Gruppen werden der Richtlinie nicht zugewiesen. <br><br> Bearbeiten Sie Ihre Richtlinie, und wählen Sie Benutzer oder Gruppen für die Richtlinie aus. |
| Für diese Richtlinie wurden keine Indikatoren ausgewählt | Alle Richtlinienvorlagen | Indikatoren wurden für die Richtlinie nicht ausgewählt <br><br> Bearbeiten Sie Ihre Richtlinie, und wählen Sie geeignete Richtlinienindikatoren für die Richtlinie aus. |
| In dieser Richtlinie sind keine Benutzergruppen mit Priorität enthalten | – Datenlecks nach Prioritätsbenutzern <br> - Sicherheitsrichtlinienverletzungen durch Prioritätsbenutzer | Prioritätsbenutzergruppen werden der Richtlinie nicht zugewiesen. <br><br> Konfigurieren Sie benutzerprioritätsgruppen in den Insider-Risikomanagementeinstellungen, und weisen Sie der Richtlinie Prioritätsbenutzergruppen zu. |
| Für diese Richtlinie wurde kein auslösendes Ereignis ausgewählt. | Alle Richtlinienvorlagen | Ein auslösendes Ereignis ist für die Richtlinie nicht konfiguriert <br><br> Risikoergebnisse werden benutzeraktivitäten erst zugewiesen, wenn Sie die Richtlinie bearbeiten und ein auslösendes Ereignis auswählen. |
| Der Personalconnector ist nicht konfiguriert oder funktioniert nicht wie erwartet | - Datendiebstahl durch ausscheidenden Benutzer <br> - Sicherheitsrichtlinienverletzungen durch ausscheidenden Benutzer <br> – Datenlecks von unzufriedenen Benutzern <br> - Sicherheitsrichtlinienverletzungen durch unzufriedene Benutzer | Es liegt ein Problem mit dem Hr-Connector vor. <br><br> 1. Wenn Sie einen Personalabteilungsconnector verwenden, überprüfen Sie, ob Ihr Personalabteilungsconnector die richtigen Daten sendet. <br><br> ODER <br><br> 2. Wählen Sie das gelöschte Triggerereignis des Azure AD-Kontos aus. |
| Keine Geräte werden onboarded | - Datendiebstahl durch ausgehende Benutzer <br> – Allgemeine Datenlecks <br> – Datenlecks von unzufriedenen Benutzern <br> – Datenlecks nach Prioritätsbenutzern | Geräteindikatoren sind ausgewählt, es sind jedoch keine Geräte in Microsoft 365 onboarded <br><br> Überprüfen Sie, ob Geräte onboarded sind und die Anforderungen erfüllen. |
| Hr connector hasn't uploaded data recently | - Datendiebstahl durch ausscheidenden Benutzer <br> - Sicherheitsrichtlinienverletzungen durch ausscheidenden Benutzer <br> – Datenlecks von unzufriedenen Benutzern <br> - Sicherheitsrichtlinienverletzungen durch unzufriedene Benutzer | Der Personalconnector hat keine Daten in mehr als 7 Tagen importiert. <br><br> Überprüfen Sie, ob Ihr Personalconnector ordnungsgemäß konfiguriert ist, und senden Sie Daten. |
| Der Status Ihres Personalconnector kann derzeit nicht überprüft werden. Überprüfen Sie dies später erneut. | - Datendiebstahl durch ausscheidenden Benutzer <br> - Sicherheitsrichtlinienverletzungen durch ausscheidenden Benutzer <br> – Datenlecks von unzufriedenen Benutzern <br> - Sicherheitsrichtlinienverletzungen durch unzufriedene Benutzer | Die Insider-Risikomanagementlösung kann den Status Ihres Personalconnector nicht überprüfen. <br><br> Überprüfen Sie, ob Ihr Personalconnector ordnungsgemäß konfiguriert ist, und senden Sie Daten, oder kommen Sie zurück, und überprüfen Sie den Richtlinienstatus.  |
| Die DLP-Richtlinie ist nicht als auslösendes Ereignis ausgewählt. | – Allgemeine Datenlecks <br> – Datenlecks nach Prioritätsbenutzern | Eine DLP-Richtlinie wurde nicht als auslösendes Ereignis ausgewählt, oder die ausgewählte DLP-Richtlinie wurde gelöscht. <br><br> Bearbeiten Sie die Richtlinie, und wählen Sie entweder eine aktive DLP-Richtlinie oder "Benutzer führt eine Exfiltrationsaktivität aus" als auslösendes Ereignis in der Richtlinienkonfiguration aus. |
| In dieser Richtlinie verwendete DLP-Richtlinie ist deaktiviert | – Allgemeine Datenlecks <br> – Datenlecks nach Prioritätsbenutzern | Die in dieser Richtlinie verwendete DLP-Richtlinie ist deaktiviert. <br><br> 1. Aktivieren Sie die dieser Richtlinie zugewiesene DLP-Richtlinie. <br><br> ODER <br><br> 2. Bearbeiten Sie diese Richtlinie, und wählen Sie entweder eine neue DLP-Richtlinie oder "Benutzer führt eine Exfiltrationsaktivität aus" als auslösendes Ereignis in der Richtlinienkonfiguration aus. |
| DLP-Richtlinie erfüllt keine Anforderungen | – Allgemeine Datenlecks <br> – Datenlecks nach Prioritätsbenutzern | Als Auslösen von Ereignissen verwendete DLP-Richtlinien müssen so konfiguriert werden, dass Warnungen mit hohem Schweregrad generiert werden. <br><br>  1. Bearbeiten Sie Ihre DLP-Richtlinie, um entsprechende Warnungen als *Hoher Schweregrad zuzuordnen.* <br><br> ODER <br><br> 2. Bearbeiten Sie diese Richtlinie, und wählen Sie *Benutzer führt eine Exfiltrationsaktivität* als auslösendes Ereignis aus. |
| Ihre Organisation hat kein Microsoft Defender for Endpoint-Abonnement | – Allgemeine Sicherheitsrichtlinienverletzungen <br> - Sicherheitsrichtlinienverletzungen durch ausscheidende Benutzer <br> - Sicherheitsrichtlinienverletzungen durch unzufriedene Benutzer <br> - Sicherheitsrichtlinienverletzungen durch Prioritätsbenutzer | Ein aktives Microsoft Defender for Endpoint-Abonnement wurde für Ihre Organisation nicht erkannt. <br><br> Bis ein Microsoft Defender for Endpoint-Abonnement hinzugefügt wurde, weisen diese Richtlinien keine Risikoergebnisse zu Benutzeraktivitäten zu. |
| Microsoft Defenders for Endpoint-Warnungen werden nicht für das Compliance Center freigegeben | – Allgemeine Sicherheitsrichtlinienverletzungen <br> - Sicherheitsrichtlinienverletzungen durch ausscheidende Benutzer <br> - Sicherheitsrichtlinienverletzungen durch unzufriedene Benutzer <br> - Sicherheitsrichtlinienverletzungen durch Prioritätsbenutzer | Microsoft Defender for Endpoint-Warnungen werden nicht für das Compliance Center freigegeben. <br><br> Konfigurieren der Freigabe von Microsoft Defender for Endpoint-Warnungen. |
| Sie nähern sich der maximalen Anzahl von Benutzern, die aktiv für diese Richtlinienvorlage punkten. | Alle Richtlinienvorlagen | Jede Richtlinienvorlage verfügt über eine maximale Anzahl von Benutzern im Bereich. Weitere Informationen finden Sie im Abschnitt vorlagenlimit. <br><br> Überprüfen Sie die Benutzer auf der Registerkarte Benutzer, und entfernen Sie alle Benutzer, die nicht mehr überprüft werden müssen. |

## <a name="policy-template-limits"></a>Richtlinienvorlagenbeschränkungen

Richtlinienvorlagen für Insider-Risikomanagement verwenden Beschränkungen zum Verwalten des Umfangs und der Verarbeitungsrate für aktivitäten im Bereich des Benutzerrisikos und zur Integration dieses Prozesses in die Unterstützung von Microsoft 365-Diensten. Jede Richtlinienvorlage verfügt über eine maximale Anzahl von Benutzern, denen aktiv Risikoergebnisse für die Richtlinie zugewiesen werden können, die sie unterstützen und effektiv verarbeiten und Risikoaktivitäten melden kann. Bereichsintegende Benutzer sind Benutzer mit auslösenden Ereignissen für die Richtlinie.

Der Grenzwert für jede Richtlinie wird basierend auf der Gesamtanzahl eindeutiger Benutzer berechnet, die Risikoergebnisse pro Richtlinienvorlagentyp erhalten. Wenn sich die Anzahl der Benutzer für einen Richtlinienvorlagentyp in der Nähe oder über dem Benutzergrenzwert befindet, wird die Richtlinienleistung reduziert. Zum Anzeigen der aktuellen Anzahl von Benutzern für eine Richtlinie navigieren Sie zur Registerkarte Richtlinie und zur Spalte Benutzer im Bereich. Für jede Richtlinienvorlage können bis zu fünf Richtlinien verwendet werden. Diese Höchstgrenzwerte gelten für Benutzer in allen Richtlinien, die eine bestimmte Richtlinienvorlage verwenden.

Verwenden Sie die folgende Tabelle, um die maximale Anzahl von Benutzern im Bereich zu ermitteln, die für jede Richtlinienvorlage unterstützt werden:

|**Richtlinienvorlage**|**Maximale Anzahl aktueller Benutzer im Bereich**|
|:------------------|:--------------------------------|
| Allgemeines Datenleck | 15,000 |
| Datenleck durch unzufriedene Benutzer | 7,500 |
| Datenlecks nach Prioritätsbenutzern | 1,000 |
| Datendiebstahl durch ausgehende Benutzer | 20,000 |
| Verstöße gegen allgemeine Sicherheitsrichtlinien | 1,000 |
| Sicherheitsrichtlinienverletzung durch Prioritätsbenutzer | 1,000 |
| Sicherheitsrichtlinienverletzungen durch ausscheidende Benutzer | 15,000 |
| Sicherheitsrichtlinienverletzungen durch verärgerte Benutzer | 7,500 |

## <a name="create-a-new-policy"></a>Erstellen einer neuen Richtlinie

Um eine neue Richtlinie für das Insiderrisikomanagement zu erstellen, verwenden Sie den Richtlinien-Assistenten in **Der Insider-Risikomanagement-Lösung** im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine neue Richtlinie zu erstellen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen **Sie Richtlinie erstellen aus,** um den Richtlinien-Assistenten zu öffnen.
3. Wählen Sie **auf der Seite** Richtlinienvorlage eine Richtlinienkategorie aus, und wählen Sie dann die Vorlage für die neue Richtlinie aus. Diese Vorlagen sind aus Bedingungen und Indikatoren, die die Risikoaktivitäten definieren, die Sie erkennen und untersuchen möchten. Überprüfen Sie die Voraussetzungen der Vorlage, lösen Sie Ereignisse und erkannte Aktivitäten aus, um zu bestätigen, dass diese Richtlinienvorlage Ihren Anforderungen entspricht.

    >[!IMPORTANT]
    >Einige Richtlinienvorlagen verfügen über Voraussetzungen, die konfiguriert werden müssen, damit die Richtlinie relevante Warnungen generiert. Wenn Sie die entsprechenden Richtlinienvoraussetzungen nicht konfiguriert haben, lesen **Sie Schritt 4** weiter oben.

4. Wählen **Sie Weiter aus,** um fortzufahren.
5. Füllen Sie **auf der Seite Name** und Beschreibung die folgenden Felder aus:
    - **Name (erforderlich):** Geben Sie einen Anzeigenamen für die Richtlinie ein. Dieser Name kann nach dem Erstellen der Richtlinie nicht mehr geändert werden.
    - **Beschreibung (optional):** Geben Sie eine Beschreibung für die Richtlinie ein.

6. Wählen **Sie Weiter aus,** um fortzufahren.
7. Wählen **Sie** auf der  Seite Benutzer und  Gruppen alle Benutzer und Gruppen oder Bestimmte Benutzer und Gruppen hinzufügen aus, um zu definieren, welche Benutzer oder Gruppen in der Richtlinie enthalten sind, oder wenn Sie eine benutzerbasierte Vorlage mit Priorität ausgewählt haben. Wählen **Sie Benutzergruppen mit Priorität hinzufügen oder bearbeiten aus.** Wenn Sie Alle Benutzer und Gruppen **aktivieren,** suchen Sie nach auslösenden Ereignissen für alle Benutzer und Gruppen in Ihrer Organisation, um mit der Zuweisung von Risikobewertungen für die Richtlinie zu beginnen. Wenn **Sie bestimmte Benutzer und Gruppen auswählen,** können Sie definieren, welche Benutzer und Gruppen der Richtlinie zugewiesen werden.
8. Wählen **Sie Weiter aus,** um fortzufahren.
9. Auf der **Seite Zu priorisierende** Inhalte können Sie (bei Bedarf) die zu priorisierenden Quellen zuweisen. Dies erhöht die Wahrscheinlichkeit, dass eine Warnung mit hohem Schweregrad für diese Quellen generiert wird. Wählen Sie eine der folgenden Optionen aus:

    - **Ich möchte SharePoint-Websites, Vertraulichkeitsbezeichnungen und/oder Typen** vertraulicher Informationen als Prioritätsinhalt angeben. Wenn Sie diese Option auswählen, werden Detailseiten im Assistenten zum Konfigurieren dieser Kanäle aktiviert.
    - **Ich möchte derzeit keine Prioritätsinhalte** angeben (Sie können dies tun, nachdem die Richtlinie erstellt wurde). Wenn Sie diese Option auswählen, werden die Kanaldetailseiten im Assistenten übersprungen.

10. Wählen **Sie Weiter aus,** um fortzufahren.

11. Wenn Sie im vorherigen Schritt die Option Ich möchte **SharePoint-Websites,** Vertraulichkeitsbezeichnungen und/oder vertrauliche Informationstypen als Prioritätsinhalte angeben, werden die Detailseiten für *SharePoint-Websites,* Typen vertraulicher Informationen und Vertraulichkeitsbezeichnungen *angezeigt.* Verwenden Sie diese Detailseiten, um die SharePoint-, vertraulichen Informationstypen und Vertraulichkeitsbezeichnungen zu definieren, die in der Richtlinie priorisiert werden.

    - **SharePoint-Websites:** Wählen Sie **SharePoint-Website hinzufügen aus,** und wählen Sie die SharePoint-Websites aus, auf die Sie Zugriff haben und priorisieren möchten. Beispiel: *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Vertraulicher Infotyp:** Wählen Sie **Vertraulichen Informationstyp hinzufügen aus,** und wählen Sie die Vertraulichkeitstypen aus, die Sie priorisieren möchten. Beispiel: *"US-Bankkontonummer"* und *"Kreditkartennummer"*.
    - **Vertraulichkeitsbezeichnungen:** Wählen Sie **Vertraulichkeitsbezeichnung hinzufügen aus,** und wählen Sie die Bezeichnungen aus, die Sie priorisieren möchten. Beispiel: *"Vertraulich"* und *"Geheim"*.

12. Wählen **Sie Weiter aus,** um fortzufahren.
13. Auf der **Seite Indikatoren und auslösende** Ereignisse [](insider-risk-management-settings.md#indicators) werden die Indikatoren angezeigt, die Sie auf der Seite Indikatoren für **Insiderrisikoeinstellungen**  >  **als verfügbar definiert** haben. Wenn Sie  zu Beginn des Assistenten eine Vorlage für Datenlecks ausgewählt haben, müssen Sie eine DLP-Richtlinie aus der **Dropdownliste der DLP-Richtlinie** auswählen, um Auslösenindikatoren für die Richtlinie zu aktivieren oder das integrierte Auslösenereignis auszuwählen.

    >[!IMPORTANT]
    >Wenn Indikatoren auf dieser Seite nicht ausgewählt werden können, müssen Sie die Indikatoren auswählen, die Sie für alle Richtlinien aktivieren möchten. Sie können die Schaltfläche Indikatoren **aktivieren** im Assistenten verwenden oder Indikatoren auf der Seite Richtlinienindikatoren für **Insider-Risikomanagementeinstellungen**  >    >   auswählen.

    Wählen Sie die Indikatoren aus, die Sie auf die Richtlinie anwenden möchten. Wenn Sie die standardrichtlinienschwelleneinstellungen für diese Indikatoren nicht verwenden möchten, deaktivieren Sie die von **Microsoft** empfohlenen Standardwerte verwenden, und geben Sie die Schwellenwerte für jeden ausgewählten Indikator ein.

    - Wenn Sie mindestens einen  Office- oder *Geräteindikator* ausgewählt haben, wählen Sie die **Risikosentwertungsbooster entsprechend** aus. Risikopunkthilfen gelten nur für ausgewählte Indikatoren.
    - Wenn Sie eine  Richtlinienvorlage für Datendiebstahl oder Datenlecks ausgewählt haben, wählen Sie mindestens eine **Sequenzerkennungsmethode** und eine **kumulative Exfiltrationserkennungsmethode** aus, die auf die Richtlinie angewendet werden soll. 

14. Wählen **Sie Weiter aus,** um fortzufahren.
15. Wählen Sie **auf der Seite Schwellenwerte** des Indikators die Option aus, um Standardindikatorschwellenwerte zu verwenden oder benutzerdefinierte Schwellenwerte für einzelne Indikatoren anzugeben. Wählen Sie für jeden Indikator die entsprechende Ebene aus, um die gewünschte Stufe von Aktivitätswarnungen zu generieren.
16. Wählen **Sie Weiter aus,** um fortzufahren.
17. Überprüfen Sie **auf** der Seite Überprüfen die Einstellungen, die Sie für die Richtlinie ausgewählt haben, sowie alle Vorschläge oder Warnungen für Ihre Auswahl. Wählen **Sie Bearbeiten** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **Senden** aus, um die Richtlinie zu erstellen und zu aktivieren.

## <a name="update-a-policy"></a>Aktualisieren einer Richtlinie

Zum Aktualisieren einer vorhandenen Insider-Risikomanagementrichtlinie verwenden Sie den Richtlinien-Assistenten in **Der Insider-Risikomanagement-Lösung** im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine vorhandene Richtlinie zu verwalten:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie im Richtliniendashboard die Richtlinie aus, die Sie verwalten möchten.
3. Wählen Sie auf der Seite Richtliniendetails die Option **Richtlinie bearbeiten aus.**
4. Im Richtlinien-Assistenten können Sie folgendes nicht bearbeiten:
    - **Richtlinienvorlage:** Die Vorlage zum Definieren der Typen von Risikoindikatoren, die von der Richtlinie überwacht werden.
    - **Name**: Der Anzeigename für die Richtlinie
5. Aktualisieren Sie **auf der** Seite Name und Beschreibung die Beschreibung für die Richtlinie im **Feld Beschreibung.**
6. Wählen **Sie Weiter aus,** um fortzufahren.
7. Wählen **Sie** auf der  Seite Benutzer und  Gruppen alle Benutzer und Gruppen oder Bestimmte Benutzer und Gruppen hinzufügen aus, um zu definieren, welche Benutzer oder Gruppen in der Richtlinie enthalten sind, oder wenn Sie eine benutzerbasierte Vorlage mit Priorität ausgewählt haben. Wählen **Sie Benutzergruppen mit Priorität hinzufügen oder bearbeiten aus.** Wenn Sie Alle Benutzer und Gruppen **aktivieren,** suchen Sie nach auslösenden Ereignissen für alle Benutzer und Gruppen in Ihrer Organisation, um mit der Zuweisung von Risikobewertungen für die Richtlinie zu beginnen. Wenn **Sie bestimmte Benutzer und Gruppen auswählen,** können Sie definieren, welche Benutzer und Gruppen der Richtlinie zugewiesen werden.
8. Wählen **Sie Weiter aus,** um fortzufahren.
9. Auf der **Seite Zu priorisierende** Inhalte können Sie (bei Bedarf) die zu priorisierenden Quellen zuweisen. Dies erhöht die Wahrscheinlichkeit, dass eine Warnung mit hohem Schweregrad für diese Quellen generiert wird. Wählen Sie eine der folgenden Optionen aus:

    - **Ich möchte SharePoint-Websites, Vertraulichkeitsbezeichnungen und/oder Typen** vertraulicher Informationen als Prioritätsinhalt angeben. Wenn Sie diese Option auswählen, werden Detailseiten im Assistenten zum Konfigurieren dieser Kanäle aktiviert.
    - **Ich möchte derzeit keine Prioritätsinhalte** angeben (Sie können dies tun, nachdem die Richtlinie erstellt wurde). Wenn Sie diese Option auswählen, werden die Kanaldetailseiten im Assistenten übersprungen.

10. Wählen **Sie Weiter aus,** um fortzufahren.

11. Wenn Sie im vorherigen Schritt die Option Ich möchte **SharePoint-Websites,** Vertraulichkeitsbezeichnungen und/oder vertrauliche Informationstypen als Prioritätsinhalte angeben, werden die Detailseiten für *SharePoint-Websites,* Typen vertraulicher Informationen und Vertraulichkeitsbezeichnungen *angezeigt.* Verwenden Sie diese Detailseiten, um die SharePoint-, vertraulichen Informationstypen und Vertraulichkeitsbezeichnungen zu definieren, die in der Richtlinie priorisiert werden.

    - **SharePoint-Websites:** Wählen Sie **SharePoint-Website hinzufügen aus,** und wählen Sie die SharePoint-Websites aus, auf die Sie Zugriff haben und priorisieren möchten. Beispiel: *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Vertraulicher Infotyp:** Wählen Sie **Vertraulichen Informationstyp hinzufügen aus,** und wählen Sie die Vertraulichkeitstypen aus, die Sie priorisieren möchten. Beispiel: *"US-Bankkontonummer"* und *"Kreditkartennummer"*.
    - **Vertraulichkeitsbezeichnungen:** Wählen Sie **Vertraulichkeitsbezeichnung hinzufügen aus,** und wählen Sie die Bezeichnungen aus, die Sie priorisieren möchten. Beispiel: *"Vertraulich"* und *"Geheim"*.

12. Wählen **Sie Weiter aus,** um fortzufahren.
13. Auf der **Seite Indikatoren und auslösende** Ereignisse [](insider-risk-management-settings.md#indicators) werden die Indikatoren angezeigt, die Sie auf der Seite Indikatoren für **Insiderrisikoeinstellungen**  >  **als verfügbar definiert** haben. Wenn Sie  zu Beginn des Assistenten eine Vorlage für Datenlecks ausgewählt haben, müssen Sie eine DLP-Richtlinie aus der **Dropdownliste der DLP-Richtlinie** auswählen, um Auslösenindikatoren für die Richtlinie zu aktivieren oder das integrierte Auslösenereignis auszuwählen.

    >[!IMPORTANT]
    >Wenn Indikatoren auf dieser Seite nicht ausgewählt werden können, müssen Sie die Indikatoren auswählen, die Sie für alle Richtlinien aktivieren möchten. Sie können die Schaltfläche Indikatoren **aktivieren** im Assistenten verwenden oder Indikatoren auf der Seite Richtlinienindikatoren für **Insider-Risikomanagementeinstellungen**  >    >   auswählen.

    Wählen Sie die Indikatoren aus, die Sie auf die Richtlinie anwenden möchten. Wenn Sie die standardrichtlinienschwelleneinstellungen für diese Indikatoren nicht verwenden möchten, deaktivieren Sie die von **Microsoft** empfohlenen Standardwerte verwenden, und geben Sie die Schwellenwerte für jeden ausgewählten Indikator ein.

    - Wenn Sie mindestens einen  Office- oder *Geräteindikator* ausgewählt haben, wählen Sie die **Risikosentwertungsbooster entsprechend** aus. Risikopunkthilfen gelten nur für ausgewählte Indikatoren.
    - Wenn Sie eine  Richtlinienvorlage für Datendiebstahl oder Datenlecks ausgewählt haben, wählen Sie mindestens eine **Sequenzerkennungsmethode** und eine **kumulative Exfiltrationserkennungsmethode** aus, die auf die Richtlinie angewendet werden soll. 

14. Wählen **Sie Weiter aus,** um fortzufahren.
15. Wählen Sie **auf der Seite Schwellenwerte** des Indikators die Option aus, um Standardindikatorschwellenwerte zu verwenden oder benutzerdefinierte Schwellenwerte für einzelne Indikatoren anzugeben. Wählen Sie für jeden Indikator die entsprechende Ebene aus, um die gewünschte Stufe von Aktivitätswarnungen zu generieren.
16. Wählen **Sie Weiter aus,** um fortzufahren.
17. Überprüfen Sie **auf** der Seite Überprüfen die Einstellungen, die Sie für die Richtlinie ausgewählt haben, sowie alle Vorschläge oder Warnungen für Ihre Auswahl. Wählen **Sie Bearbeiten** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **Senden** aus, um die Richtlinie zu erstellen und zu aktivieren.

## <a name="copy-a-policy"></a>Kopieren einer Richtlinie

Möglicherweise müssen Sie eine neue Richtlinie erstellen, die einer vorhandenen Richtlinie ähnelt, aber nur wenige Konfigurationsänderungen benötigt. Anstatt eine neue Richtlinie von Grund auf neu zu erstellen, können Sie eine vorhandene Richtlinie kopieren und dann die Bereiche ändern, die in der neuen Richtlinie aktualisiert werden müssen.

Führen Sie die folgenden Schritte aus, um eine vorhandene Richtlinie zu kopieren:

1. Wechseln Sie im Microsoft 365 Compliance Center zu Insider Risk Management, und wählen Sie die Registerkarte Richtlinien aus.
2. Wählen Sie im Richtliniendashboard die Richtlinie aus, die Sie kopieren möchten.
3. Wählen Sie auf der Seite Richtliniendetails die Option Kopieren aus.
4. Benennen Sie im Richtlinien-Assistenten die neue Richtlinie, und aktualisieren Sie die Richtlinienkonfiguration nach Bedarf.

## <a name="immediately-start-scoring-user-activity"></a>Sofort mit der Bewertung der Benutzeraktivität beginnen

Es kann Szenarien gibt, in denen Sie sofort damit beginnen müssen, Benutzern mit Insiderrisikorichtlinien außerhalb des Insiderrisikomanagements, der den Ereignisworkflow auslöst, Risikoergebnisse zuzuordnen. Verwenden **Sie Die** Bewertungsaktivität starten für Benutzer auf der Registerkarte Richtlinien, um einen Benutzer (oder Benutzer) manuell für einen bestimmten Zeitraum zu einer oder mehreren Insiderrisikorichtlinien hinzuzufügen, um sofort mit dem Zuweisen von Risikobewertungen zu ihrer Aktivität zu beginnen und die Anforderung zu umgehen, dass ein Benutzer über einen auslösenden Indikator (z. B. eine Übereinstimmung mit einer DLP-Richtlinie) verfügen muss.  Sie können auch einen Grund für das Hinzufügen des Benutzers zur Richtlinie hinzufügen, der auf der Aktivitätszeitachse der Benutzer angezeigt wird. Benutzer, die Richtlinien manuell hinzugefügt  werden, werden im Benutzerdashboard angezeigt, und Warnungen werden erstellt, wenn die Aktivität die Schwellenwerte für Richtlinienwarnungen erfüllt.

Einige Szenarien, in denen Sie möglicherweise sofort mit der Bewertung von Benutzeraktivitäten beginnen möchten:

- Wenn Benutzer mit Risikobedenken identifiziert werden und Sie sofort mit der Zuweisung von Risikoergebnissen zu ihren Aktivitäten für eine oder mehrere Ihrer Richtlinien beginnen möchten
- Wenn ein Vorfall vorkommt, der möglicherweise erfordert, dass Sie sofort mit der Zuweisung von Risikoergebnissen für die Aktivitäten beteiligter Benutzer für eine oder mehrere Ihrer Richtlinien beginnen
- Wenn Sie Ihren Personalconnector noch nicht konfiguriert haben, Sie jedoch mit der Zuweisung von Risikoergebnissen zu Benutzeraktivitäten für Hr-Ereignisse beginnen möchten, indem Sie eine CSV-Datei für die Benutzer hochladen

>[!NOTE]
>Es kann mehrere Stunden dauern, bis neue manuell hinzugefügte Benutzer im Benutzerdashboard **angezeigt** werden. Die Anzeige von Aktivitäten für die vorherigen 90 Tage für diese Benutzer kann bis zu 24 Stunden dauern. Um Aktivitäten für manuell hinzugefügte Benutzer anzuzeigen, navigieren Sie  zur Registerkarte  Benutzer, wählen Sie den Benutzer im Benutzerdashboard aus, und öffnen Sie die Registerkarte Benutzeraktivität im Detailbereich. 

Führen Sie die folgenden Schritte aus, um die Bewertungsaktivität für Benutzer in einer oder mehreren Insider-Risikomanagementrichtlinien manuell zu starten:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie im Richtliniendashboard die Richtlinie oder Richtlinien aus, der Sie Benutzer hinzufügen möchten.
3. Wählen **Sie Bewertungsaktivität für Benutzer starten aus.**
4. Fügen Sie **im Feld Reason** im Bereich **Benutzer** zu mehreren Richtlinien hinzufügen einen Grund für das Hinzufügen der Benutzer hinzu.
5. Definieren Sie im Feld This **should last for (choose between 5 and 30 days)** die Anzahl der Tage, um die Aktivität des Benutzers für die Richtlinie zu bestimmen, der er hinzugefügt wird.
6. Verwenden Sie das Feld Suchbenutzer zum Hinzufügen zu Richtlinien, um Active Directory nach Benutzern **zu** durchsuchen. Geben Sie den Namen des Benutzers ein, den Sie den Richtlinien hinzufügen möchten. Wählen Sie den Benutzernamen aus, und wiederholen Sie den Vorgang, um den Richtlinien weitere Benutzer zuzuordnen. Die liste der ausgewählten Benutzer wird im Abschnitt Benutzer im Bereich Benutzer zu mehreren Richtlinien hinzufügen angezeigt.
7. Wenn Sie eine Liste der Benutzer importieren möchten, die den Richtlinien hinzugefügt werden, wählen Sie **Importieren** aus, um eine CSV-Datei (durch Kommas getrennte Werte) zu importieren. Die Datei muss das folgende Format haben, und Sie müssen die Benutzerprinzipalnamen in der Datei auflisten:

    ```csv
    user principal name
    user1@domain.com
    user2@domain.com
    ```

8. Wählen Sie Benutzer zu Richtlinien hinzufügen aus, um die Änderungen zu akzeptieren, und fügen Sie den Richtlinien Benutzer hinzu, oder wählen Sie Abbrechen aus, um die Änderungen zu verwerfen und das Dialogfeld zu schließen.

## <a name="stop-scoring-users-in-a-policy"></a>Beenden der Bewertung von Benutzern in einer Richtlinie

Informationen zum Beenden der Bewertung von Benutzern in einer Richtlinie finden Sie im Artikel [Insider risk management users: Remove users from in-scope assignment to policies.](insider-risk-management-users.md#remove-users-from-in-scope-assignment-to-policies)

## <a name="delete-a-policy"></a>Löschen einer Richtlinie

>[!NOTE]
>Durch das Löschen einer Richtlinie werden keine aktiven oder archivierten Warnungen gelöscht, die aus der Richtlinie generiert wurden.

Führen Sie die folgenden Schritte aus, um eine vorhandene Insider-Risikomanagementrichtlinie zu löschen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie im Richtliniendashboard die Richtlinie aus, die Sie löschen möchten.
3. Wählen **Sie auf** der Dashboardsymbolleiste Löschen aus.
4. Wählen Sie **im Dialogfeld** Löschen die Option **Ja** aus, um die Richtlinie zu löschen, oder wählen Sie **Abbrechen** aus, um das Dialogfeld zu schließen.
