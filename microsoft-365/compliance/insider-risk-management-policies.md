---
title: Insider-Risikomanagement-Richtlinien
description: Informationen zu Insider-Risikomanagement-Richtlinien in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Compliance
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
ms.openlocfilehash: f64fcf4908f119e261b07bbc4feaed2151e30187
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226431"
---
# <a name="insider-risk-management-policies"></a>Insider-Risikomanagement-Richtlinien

Insider-Risikomanagement-Richtlinien legen fest, welche Benutzer in den Geltungsbereich fallen und welche Arten von Risikoindikatoren für Warnmeldungen konfiguriert werden. Sie können schnell eine Richtlinie erstellen, die für alle Benutzer in Ihrer Organisation gilt, oder einzelne Benutzer oder Gruppen für die Verwaltung in einer Richtlinie definieren. Richtlinien unterstützen Inhaltsprioritäten, um Richtlinienbedingungen auf mehrere oder bestimmte Microsoft-Teams, SharePoint-Sites, Vertraulichkeitstypen von Daten und Datenbezeichnungen zu konzentrieren. Mithilfe von Vorlagen können Sie bestimmte Risikoindikatoren auswählen und Ereignisschwellenwerte für Richtlinienindikatoren anpassen und so die Risikobewertungen sowie die Stufe und Häufigkeit von Warnungen effektiv anpassen. Darüber hinaus helfen Ihnen Risikobewertungsverstärker und Anomalieerkennungen, Benutzeraktivitäten zu identifizieren, die von höherer Bedeutung oder eher ungewöhnlich sind. Mit Richtlinienfenstern können Sie den Zeitrahmen definieren, in dem die Richtlinie auf Warnungsaktivitäten angewendet wird, und sie werden verwendet, um die Dauer der Richtlinie ab der Aktivierung zu bestimmen.

Sehen Sie sich das [Video zur Konfiguration von Risikomanagementrichtlinien](https://www.youtube.com/watch?v=kudK5ajZTUo) an, um einen Überblick darüber zu erhalten, wie Ihnen mithilfe integrierter Richtlinienvorlagen erstellte Richtlinien helfen können, schnell Maßnahmen bei potenziellen Risiken zu ergreifen.

## <a name="policy-dashboard"></a>Richtlinien-Dashboard

Über das **Richtlinien-Dashboard** können Sie sich schnell einen Überblick über die Richtlinien in Ihrer Organisation und deren Integrität verschaffen, den Richtlinien manuell Benutzer hinzufügen und den Status der mit den einzelnen Richtlinien verbundenen Warnungen anzeigen.

- **Richtlinienname:** Der Name, der im Richtlinien-Assistenten der Richtlinie zugewiesen wurde.
- **Status**: Der Integritätsstatus für jede Richtlinie. Zeigt die Anzahl der Richtlinienwarnungen und Empfehlungen oder den Status *Fehlerfrei* für Richtlinien ohne Probleme an.  Sie können auf die Richtlinie klicken, um die Integritätsstatusdetails für Warnungen oder Empfehlungen anzuzeigen.
- **Aktive Warnungen:** Die Anzahl der aktiven Warnungen für jede Richtlinie.
- **Bestätigte Warnungen:** Die Gesamtzahl der Warnungen, die in den letzten 365 Tagen durch die Richtlinie zu Fällen geführt haben.
- **Maßnahmen bei Warnungen**: Die Gesamtzahl der Warnungen, die in den letzten 365 Tagen bestätigt oder verworfen wurden.
- **Richtlinien-Warnungswirksamkeit:** Der Prozentsatz, der sich aus der Gesamtzahl der bestätigten Warnungen, geteilt durch die Gesamtzahl der aufgrund von Warnungen ergriffenen Maßnahmen ergibt (dies ist die Summe der Warnungen, die im Laufe des letzten Jahres bestätigt oder verworfen wurden).

![Insider-Risikomanagement-Richtlinien-Dashboard](../media/insider-risk-policy-dashboard.png)

## <a name="policy-recommendations-from-analytics-preview"></a>Richtlinienempfehlungen aus Analysen (Vorschau)

Mit Insider-Risikoanalysen können Sie eine Auswertung potenzieller Insider-Risiken in Ihrer Organisation durchführen, ohne Insider-Risikorichtlinien konfigurieren zu müssen. Diese Auswertung kann Ihrer Organisation dabei helfen, potenzielle Bereiche mit höherem Benutzerrisiko zu identifizieren und den Typ und Umfang von Insider-Risikomanagement-Richtlinien zu bestimmen, die Sie konfigurieren sollten.

Weitere Informationen zu Insider-Risikoanalysen und Richtlinienempfehlungen finden Sie unter [Insider-Risikomanagement-Einstellungen: Analysen (Vorschau)](insider-risk-management-settings.md#analytics-preview).

## <a name="policy-templates"></a>Richtlinienvorlagen

Insider-Risikomanagementvorlagen sind vordefinierte Richtlinienbedingungen, mit denen die von der Richtlinie verwendeten Arten von Risikoindikatoren und das verwendete Risikobewertungsmodell definiert werden. Bevor eine Richtlinie erstellt wird, muss ihr im Richtlinienerstellungs-Assistenten eine Vorlage zugewiesen werden. Das Insider-Risikomanagement unterstützt bis zu fünf Richtlinien für jede Richtlinienvorlage. Wenn Sie mit dem Richtlinien-Assistenten eine neue Insider-Risikorichtlinie erstellen, stehen Ihnen die folgenden Richtlinienvorlagen zur Auswahl:

### <a name="data-theft-by-departing-users"></a>Datendiebstahl durch ausscheidende Benutzer

Wenn Benutzer Ihre Organisation verlassen, gibt es spezifische Risikoindikatoren, die in der Regel mit Datendiebstahl durch ausscheidende Benutzer verbunden sind. Diese Richtlinienvorlage verwendet zur Bewertung des Risikos Exfiltrationsindikatoren und konzentriert sich auf Erkennung und Warnungen in diesem Risikobereich. Datendiebstahl durch ausscheidende Benutzer kann das Herunterladen von Dateien von SharePoint Online, das Drucken von Dateien sowie das Kopieren von Daten in persönliche Cloud-Messaging- und -Speicherdienste in zeitlicher Nähe zu den Daten der Kündigung und des Ausscheidens umfassen. Durch die Verwendung des Microsoft 365 HR-Connectors oder mithilfe der Option zum automatischen Überwachen auf das Löschen von Benutzerkonten in Azure Active Directory für Ihre Organisation beginnt diese Vorlage mit der Bewertung von Risikoindikatoren im Zusammenhang mit diesen Aktivitäten und ihrer Korrelation mit dem Benutzeranstellungsstatus.

> [!IMPORTANT]
> Wenn Sie diese Vorlage verwenden, können Sie einen Microsoft 365 HR-Connector so konfigurieren, dass er regelmäßig Informationen zu Ausscheide-und Kündigungsdaten von Benutzern Ihrer Organisation importiert. Eine schrittweise Anleitung zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation finden Sie in dem Artikel [Importieren von Daten mit dem HR-Connector](import-hr-data.md). Wenn Sie sich dafür entscheiden, den HR-Connector nicht zu verwenden, müssen Sie beim Konfigurieren von Triggerereignissen im Richtlinien-Assistenten die Option „Aus Azure AD gelöschtes Benutzerkonto“ auswählen.

### <a name="general-data-leaks"></a>Allgemeine Datenlecks

Der Schutz von Daten und die Verhinderung von Datenlecks stellt für die meisten Organisationen eine konstante Herausforderung dar, insbesondere angesichts des schnellen Anstiegs neuer Daten, die von Benutzern, Geräten und Diensten erstellt werden. Die Benutzer sind in der Lage, Informationen dienst- und geräteübergreifend zu erstellen, zu speichern und zu teilen, was die Verwaltung von Datenlecks immer komplexer und schwieriger macht. Zu den Datenlecks können die versehentliche Weitergabe von Informationen außerhalb Ihres Unternehmens oder Datendiebstahl in böswilliger Absicht gehören. Mit einer zugewiesenen Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) oder dem integrierten auslösenden Ereignis beginnt diese Vorlage mit der Bewertung von Erkennungen verdächtiger Downloads von SharePoint Online-Daten, verdächtiger Freigaben von Dateien und Ordnern, des verdächtigen Druckens von Dateien und des verdächtigen Kopierens von Daten in persönliche Cloud-Messaging- und -Speicherdienste in Echtzeit.

Bei Verwendung einer *Datenlecks*-Vorlage können Sie eine DLP-Richtlinie zuweisen, um Indikatoren in der Insider-Risikorichtlinie für Warnungen mit hohem Schweregrad in Ihrer Organisation auszulösen. Immer, wenn eine Warnung mit hohem Schweregrad, die von einer DLP-Richtlinienregel generiert wurde, dem Office 365-Überwachungsprotokoll hinzugefügt wird, untersuchen mit dieser Vorlage erstellte Insider-Risikorichtlinien automatisch die DLP-Warnung mit hohem Schweregrad. Wenn die Warnung einen in der Insider-Risikorichtlinie definierten, im Umfang enthaltenen Benutzer enthält, wird die Warnung von der Insider-Risikorichtlinie als neue Warnung verarbeitet und ihr ein Schweregrad sowie eine Risikobewertung für ein Insider-Risiko zugewiesen. Diese Richtlinie ermöglicht es Ihnen, diese Warnung im Kontext mit anderen in den Fall enthaltenen Aktivitäten auszuwerten. Wenn Sie keine DLP-Richtlinie auswählen, müssen Sie das integrierte auslösende Ereignis auswählen.

#### <a name="data-leaks-policy-guidelines"></a>Richtlinien für Datenleckrichtlinien

Berücksichtigen Sie beim Erstellen oder Ändern von DLP-Richtlinien für die Verwendung mit Insider-Risikomanagement-Richtlinien die folgenden Richtlinien:

- Priorisieren Sie Datenexfiltrationsereignisse, und gehen Sie selektiv vor, wenn Sie beim Konfigurieren von Regeln in Ihren DLP-Richtlinien die Einstellungen von **Vorfallsberichten** auf *Hoch* festlegen. Das Senden vertraulicher Dokumente per E-Mail an einen bekannten Mitbewerber sollte ein Exfiltrationsereignis der Warnstufe *Hoch* sein. Zu häufiges Zuweisen der Stufe *Hoch* in den Einstellungen von **Vorfallsberichten** in anderen DLP-Richtlinienregeln kann zu mehr Störungen (noise) im Warnungsworkflow des Insider-Risikomanagements führen und Ihren Datenprüfern und -analysten die angemessene Auswertung dieser Warnungen erschweren. Das Zuweisen der Warnstufe *Hoch* zu „Zugriff verweigert“-Aktivitäten in DLP-Richtlinien erschwert die Auswertung tatsächlich riskanter Benutzerverhalten und -aktivitäten.
- Stellen Sie sicher, dass Sie die im Umfang enthaltenen Benutzer sowohl in den DLP- als auch in den Insider-Risikomanagement-Richtlinien verstehen und ordnungsgemäß konfigurieren. Nur für Benutzer, die mithilfe der Vorlage **Datenlecks** für Insider-Risikomanagement-Richtlinien als im Umfang enthalten definiert sind, werden DLP-Richtlinienwarnungen mit hohem Schweregrad verarbeitet. Darüber hinaus werden nur Benutzer, die in einer Regel für eine DLP-Warnung mit hohem Schweregrad als im Umfang enthalten definiert sind, von der betreffenden Insider-Risikomanagement-Richtlinie untersucht. Es ist wichtig, dass Sie nicht unwissentlich im Umfang enthaltene Benutzer sowohl in Ihren DLP- als auch in Ihren Insider-Risikorichtlinien in widersprüchlicher Weise definieren.

     Wenn Ihre DLP-Richtlinienregeln beispielsweise nur Benutzer im Vertriebsteam umfassen und in der aus der Vorlage **Datenlecks** erstellten Insider-Risikorichtlinie alle Benutzer als im Umfang enthalten definiert sind, verarbeitet die Insider-Risikorichtlinie tatsächlich nur DLP-Warnungen mit hohem Schweregrad für die Benutzer im Vertriebsteam. Die Insider-Risikorichtlinie erhält keine DLP-Warnungen der Stufe „Hoch“ für Benutzer zur Verarbeitung, die in diesem Beispiel nicht in den DLP-Regeln definiert sind. Wenn im Gegensatz dazu Ihre aus der Vorlage **Datenlecks** erstellte Insider-Risikomanagement-Richtlinie nur Benutzer im Vertriebsteam umfasst und im Umfang der zugewiesenen DLP-Richtlinie alle Benutzer enthalten sind, verarbeitet die Insider-Risikorichtlinie nur DLP-Warnungen mit hohem Schweregrad für Mitglieder des Vertriebsteams. Die Insider-Risikomanagement-Richtlinie ignoriert DLP-Warnungen mit hohem Schweregrad für alle Benutzer, die nicht zum Vertriebsteam gehören.

- Stellen Sie sicher, dass die Regeleinstellung für **Vorfallsberichte** in der DLP-Richtlinie, die für diese Insider-Risikomanagementvorlage verwendet wird, für Warnungen mit Schweregrad *Hoch* konfiguriert ist. Der Schweregrad *Hoch* ist das auslösende Ereignis, und Insider-Risikomanagementwarnungen werden nicht aus Regeln in DLP-Richtlinien generiert, bei denen das Feld für **Vorfallsberichte** auf *Niedrig* oder *Mittel* festgelegt ist.

    ![Einstellungen für DLP-Richtlinienwarnungen](../media/insider-risk-DLP-policy-high-severity.png)

     > [!NOTE]
     > Wenn Sie eine neue DLP-Richtlinie mithilfe der integrierten Vorlagen erstellen, müssen Sie die Option **Erweiterte DLP-Regeln erstellen oder anpassen** auswählen, um die Einstellung für **Vorfallsberichte** auf den Schweregrad *Hoch* zu konfigurieren.

Jeder Insider-Risikomanagement-Richtlinie, die aus der Vorlage **Datenlecks** erstellt wurde, kann nur eine DLP-Richtlinie zugewiesen werden. Erwägen Sie, eine dedizierte DLP-Richtlinie zu erstellen, die die verschiedenen Aktivitäten kombiniert, die Sie erkennen möchten und die als auslösende Ereignisse für Insider-Risikorichtlinien fungieren sollen, die die Vorlage **Datenlecks** verwenden.

Eine schrittweise Anleitung zum Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie in dem Artikel [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md).

### <a name="data-leaks-by-priority-users-preview"></a>Datenlecks durch prioritäre Benutzer (Vorschau)

Der Schutz von Daten und die Verhinderung von Datenlecks durch Benutzer in Ihrer Organisation hängt möglicherweise von deren Position, ihrer Zugriffsebene auf vertrauliche Informationen oder ihrem Risikoverlauf ab. Zu den Datenlecks gehören die versehentliche Weitergabe hochgradig vertraulicher Informationen außerhalb Ihres Unternehmens oder Datendiebstahl in böswilliger Absicht. Mit einer zugewiesenen Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) beginnt diese Vorlage mit der Bewertung von Erkennungen verdächtiger Aktivitäten in Echtzeit und führt zu einer höheren Wahrscheinlichkeit für Insider-Risikowarnungen und Warnungen mit höheren Schweregraden. Prioritäre Benutzer werden in [Gruppen prioritärer Benutzer](insider-risk-management-settings.md#priority-user-groups-preview) definiert, die im Bereich der Insider-Risikomanagementeinstellungen konfiguriert sind.

Wie auch bei der Vorlage **Allgemeine Datenlecks** müssen Sie eine DLP-Richtlinie zuweisen, um Indikatoren in der Insider-Risikorichtlinie für Warnungen mit hohem Schweregrad in Ihrer Organisation auszulösen. Befolgen Sie die oben genannten Richtlinien für Datenleckrichtlinien, wenn Sie eine Richtlinie mit dieser Vorlage erstellen. Darüber hinaus müssen Sie der Richtlinie Gruppen prioritärer Benutzer zuweisen, die in **Insider-Risikomanagement** > **Einstellungen** > **Gruppen prioritärer Benutzer** erstellt wurden.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Datenlecks durch verärgerte Benutzer (Vorschau)

Wenn bei Benutzern Stressoren im Beschäftigungsverhältnis auftreten, werden sie möglicherweise verärgert, wodurch sich die Wahrscheinlichkeit von Insider-Risikoaktivitäten erhöhen kann. Diese Vorlage beginnt mit der Bewertung von Benutzeraktivitäten, wenn ein Indikator erkannt wird, der „Verärgerung“ zugeordnet ist. Beispiele hierfür sind Aufforderungen/Benachrichtigungen zur Leistungsverbesserung, schlechte Leistungsbeurteilungen oder Änderungen am Status der Beschäftigungsstufe. Datenlecks durch verärgerte Benutzer können das Herunterladen von Dateien von SharePoint Online, sowie das Kopieren von Daten in persönliche Cloud-Messaging- und -Speicherdienste in zeitlicher Nähe zu Stressorereignissen im Beschäftigungsverhältnis umfassen.

Wenn Sie diese Vorlage verwenden, müssen Sie auch einen Microsoft 365 HR-Connector so konfigurieren, dass er regelmäßig Aufforderungen/Benachrichtigungen zur Leistungsverbesserung, schlechte Leistungsbeurteilungen oder Informationen über Änderungen am Status der Beschäftigungsstufe für Benutzer Ihrer Organisation importiert. Eine schrittweise Anleitung zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation finden Sie in dem Artikel [Importieren von Daten mit dem HR-Connector](import-hr-data.md).

### <a name="general-security-policy-violations-preview"></a>Allgemeine Verstöße gegen Sicherheitsrichtlinien (Vorschau)

In vielen Organisationen verfügen Benutzer über die Berechtigung zum Installieren von Software auf ihren Geräten oder zum Ändern von Geräteeinstellungen, um sie bei ihren Aufgaben zu unterstützen. Benutzer können unabsichtlich oder mit böswilligen Absichten Schadsoftware installieren oder wichtige Sicherheitsfeatures deaktivieren, die zum Schutz von Informationen auf ihrem Gerät oder in Ihren Netzwerkressourcen beitragen. Diese Richtlinienvorlage verwendet Sicherheitswarnungen von Microsoft Defender für Endpunkt, um mit der Bewertung dieser Aktivitäten sowie zu beginnen und die Erkennung und Warnungen auf diesen Risikobereich zu fokussieren. Verwenden Sie diese Vorlage, um Erkenntnisse über Sicherheitsrichtlinienverstöße in Szenarien zu bieten, in denen Benutzer möglicherweise eine Vorgeschichte von Sicherheitsrichtlinienverstößen aufweisen, die als Indikator für ein Insider-Risiko dienen können.

Sie müssen Microsoft Defender für Endpunkt in Ihrer Organisation konfiguriert haben und für die Integration des Insider-Risikomanagements Defender für Endpunkt im Defender Security Center aktivieren, um Warnungen bei Sicherheitsverstößen zu importieren. Weitere Informationen zum Konfigurieren von Defender für Endpunkt für die Insider-Risikomanagementintegration finden Sie unter [Konfigurieren erweiterter Features in Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-departing-users-preview"></a>Verstöße gegen Sicherheitsrichtlinien durch ausscheidende Benutzer (Vorschau)

Ausscheidende Benutzer, unabhängig davon, ob sie im Guten oder Bösen gehen, können höhere Risiken für Verstöße gegen Sicherheitsrichtlinien darstellen. Zum Schutz vor versehentlichen oder böswilligen Sicherheitsverstößen durch ausscheidende Benutzer verwendet diese Richtlinienvorlage Defender für Endpunkt-Warnungen, um Erkenntnisse über sicherheitsrelevante Aktivitäten zu bieten. Zu diesen Aktivitäten gehört das Installieren von Schadsoftware oder anderen potenziell schädlichen Anwendungen durch den Benutzer sowie das Deaktivieren von Sicherheitsfeatures auf seinen Geräten. Durch die Verwendung des [Microsoft 365 HR-Connectors](import-hr-data.md) oder mithilfe der Option zum automatischen Überwachen auf das Löschen von Benutzerkonten in Azure Active Directory für Ihre Organisation beginnt diese Vorlage mit der Bewertung von Risikoindikatoren im Zusammenhang mit diesen Sicherheitsaktivitäten und ihrer Korrelation mit dem Benutzeranstellungsstatus.

Sie müssen Microsoft Defender für Endpunkt in Ihrer Organisation konfiguriert haben und für die Integration des Insider-Risikomanagements Defender für Endpunkt im Defender Security Center aktivieren, um Warnungen bei Sicherheitsverstößen zu importieren. Weitere Informationen zum Konfigurieren von Defender für Endpunkt für die Insider-Risikomanagementintegration finden Sie unter [Konfigurieren erweiterter Features in Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-priority-users-preview"></a>Verstöße gegen Sicherheitsrichtlinien durch prioritäre Benutzer (Vorschau)

Der Schutz vor Sicherheitsverstößen durch Benutzer in Ihrer Organisation hängt möglicherweise von deren Position, ihrer Zugriffsebene auf vertrauliche Informationen oder ihrem Risikoverlauf ab. Da Sicherheitsverstöße durch prioritäre Benutzer erhebliche Auswirkungen auf die kritischen Bereiche Ihrer Organisation haben können, beginnt diese Richtlinienvorlage mit der Bewertung dieser Indikatoren und verwendet Microsoft Defender für Endpunkt-Warnungen, um Erkenntnisse über sicherheitsrelevante Aktivitäten für diese Benutzer zu bieten. Zu diesen Aktivitäten kann das Installieren von Schadsoftware oder anderen potenziell schädlichen Anwendungen durch prioritäre Benutzer sowie das Deaktivieren von Sicherheitsfeatures auf ihren Geräten gehören. Prioritäre Benutzer werden in Gruppen prioritärer Benutzer definiert, die im Bereich der Insider-Risikomanagementeinstellungen konfiguriert sind.

Sie müssen Microsoft Defender für Endpunkt in Ihrer Organisation konfiguriert haben und für die Integration des Insider-Risikomanagements Defender für Endpunkt im Defender Security Center aktivieren, um Warnungen bei Sicherheitsverstößen zu importieren. Weitere Informationen zum Konfigurieren von Defender für Endpunkt für die Insider-Risikomanagementintegration finden Sie unter [Konfigurieren erweiterter Features in Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center). Darüber hinaus müssen Sie der Richtlinie Gruppen prioritärer Benutzer zuweisen, die in **Insider-Risikomanagement** > **Einstellungen** > **Gruppen prioritärer Benutzer** erstellt wurden.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Verstöße gegen Sicherheitsrichtlinien durch verärgerte Benutzer (Vorschau)

Benutzern, bei denen Stressoren im Beschäftigungsverhältnis auftreten, haben möglicherweise ein höheres Risiko für versehentliche oder böswillige Verstößen gegen Sicherheitsrichtlinien. Zu diesen Stressoren kann gehören, dass der Benutzer einem Plan zur Leistungsverbesserung zugeteilt wird, dass er schlechte Leistungsbeurteilungen erhält oder seine berufliche Stellung herabgestuft wird. Diese Richtlinienvorlage beginnt mit der Risikobewertung anhand dieser Indikatoren und Aktivitäten, die diesen Ereignissen für diese Benutzer zugeordnet sind.

Wenn Sie diese Vorlage verwenden, müssen Sie auch einen Microsoft 365 HR-Connector so konfigurieren, dass er regelmäßig Aufforderungen/Benachrichtigungen zur Leistungsverbesserung, schlechte Leistungsbeurteilungen oder Informationen über Änderungen am Status der Beschäftigungsstufe für Benutzer Ihrer Organisation importiert. Eine schrittweise Anleitung zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation finden Sie in dem Artikel [Importieren von Daten mit dem HR-Connector](import-hr-data.md).

Sie müssen außerdem Microsoft Defender für Endpunkt in Ihrer Organisation konfiguriert haben und für die Integration des Insider-Risikomanagements Defender für Endpunkt im Defender Security Center aktivieren, um Warnungen bei Sicherheitsverstößen zu importieren. Weitere Informationen zum Konfigurieren von Defender für Endpunkt für die Insider-Risikomanagementintegration finden Sie unter [Konfigurieren erweiterter Features in Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="policy-template-prerequisites-and-triggering-events"></a>Voraussetzungen und auslösende Ereignisse für Richtlinienvorlagen

Je nach der Vorlage, die Sie für eine Insider-Risikomanagement-Richtlinie auswählen, variieren die auslösenden Ereignisse und Richtlinienvoraussetzungen. Auslösende Ereignisse sind Voraussetzungen, die bestimmen, ob eine Insider-Risikomanagement-Richtlinie einen Benutzer als aktiv ansieht. Wenn ein Benutzer einer Insider-Risikomanagement-Richtlinie hinzugefügt wird, ohne dass ein auslösendes Ereignis vorhanden ist, wird die Benutzeraktivität nur dann von der Richtlinie ausgewertet, wenn sie manuell im Benutzer-Dashboard hinzugefügt wird. Richtlinienvoraussetzungen sind erforderliche Elemente, damit die Richtlinie die Signale oder Aktivitäten empfängt, die zum Auswerten von Risiken erforderlich sind.

In der folgenden Tabelle werden die auslösenden Ereignisse und Voraussetzungen für Richtlinien aufgeführt, die aus der jeweiligen Insider-Risikomanagement-Richtlinienvorlage erstellt wurden:

| **Richtlinienvorlage** | **Auslösende Ereignisse für Richtlinien** | **Voraussetzungen** |
| :------------------ | :--------------------------------- | :---------------- |
| Datendiebstahl durch ausscheidende Benutzer | Indikator für Datum des Ausscheidens oder der Kündigung vom HR-Connector | (Optional) Für Indikatoren für Kündigungs- und Ausscheidensdaten konfigurierter Microsoft 365 HR-Connector oder aktivierte Azure Active Directory-Integration |
| Allgemeine Datenlecks | Datenleck-Richtlinienaktivität die eine Warnung mit hohem Schweregrad erzeugt | (Optional) Für Warnungen mit hohem Schweregrad konfigurierte DLP-Richtlinie oder integrierte auslösendes Ereignis für Datenexfiltration |
| Datenlecks durch prioritäre Benutzer | Datenleck-Richtlinienaktivität die eine Warnung mit *Schweregrad „Hoch“* erzeugt oder integrierte auslösende Trigger für Exfiltration | (Optional) Für Warnungen mit hohem Schweregrad konfigurierte DLP-Richtlinie <br><br> In den Insider-Risikoeinstellungen konfigurierte Gruppen prioritärer Benutzer |
| Datenlecks durch verärgerte Benutzer | Indikatoren für Leistungsverbesserung, schlechte Leistung oder Änderungen am Status der Beschäftigungsstufe vom HR-Connector | Für Verärgerungsindikatoren konfigurierter Microsoft 365 HR-Connector |
| Allgemeine Verstöße gegen Sicherheitsrichtlinien | Defensives Ausweichen gegenüber Sicherheitskontrollen oder unerwünschte Software, die von Microsoft Defender für Endpunkt erkannt wurde | Aktives Microsoft Defender für Endpunkt-Abonnement <br><br> Konfigurierte Integration von Microsoft Defender für Endpunkt in das Microsoft 365 Compliance Center |
| Verstöße gegen Sicherheitsrichtlinien durch ausscheidende Benutzer | Indikatoren für Datum des Ausscheidens bzw. der Kündigung vom HR-Connector oder Kontolöschung in Azure Active Directory | (Optional) Für Indikatoren für Kündigungs- und Ausscheidensdaten konfigurierter Microsoft 365 HR-Connector <br><br> Aktives Microsoft Defender für Endpunkt-Abonnement <br><br> Konfigurierte Integration von Microsoft Defender für Endpunkt in das Microsoft 365 Compliance Center |
| Verstöße gegen Sicherheitsrichtlinien durch prioritäre Benutzer | Defensives Ausweichen gegenüber Sicherheitskontrollen oder unerwünschte Software, die von Microsoft Defender für Endpunkt erkannt wurde | Aktives Microsoft Defender für Endpunkt-Abonnement <br><br> Konfigurierte Integration von Microsoft Defender für Endpunkt in das Microsoft 365 Compliance Center <br><br> In den Insider-Risikoeinstellungen konfigurierte Gruppen prioritärer Benutzer |
| Verstöße gegen Sicherheitsrichtlinien durch verärgerte Benutzer | Indikatoren für Leistungsverbesserung, schlechte Leistung oder Änderungen am Status der Beschäftigungsstufe vom HR-Connector | Für Verärgerungsindikatoren konfigurierter Microsoft 365 HR-Connector <br><br> Aktives Microsoft Defender für Endpunkt-Abonnement <br><br> Konfigurierte Integration von Microsoft Defender für Endpunkt in das Microsoft 365 Compliance Center |

## <a name="prioritize-content-in-policies"></a>Priorisieren von Inhalten in Richtlinien

Insider-Risikomanagement-Richtlinien unterstützen die Angabe einer höheren Priorität für Inhalte, je nachdem, wo diese gespeichert werden oder wie sie klassifiziert sind. Durch Angeben von Inhalten als Priorität wird die Risikobewertung für jede zugeordnete Aktivität erhöht, wodurch wiederum die Wahrscheinlichkeit steigt, eine Warnung mit hohem Schweregrad zu generieren. Bei einigen Aktivitäten wird jedoch überhaupt keine Warnung generiert, es sei denn, der relevante Inhalt enthält integrierte oder benutzerdefinierte Typen vertraulicher Informationen oder wurde in der Richtlinie als Priorität festgelegt.

Angenommen, Ihre Organisation besitzt eine dedizierte SharePoint-Site für ein hochgradig vertrauliches Projekt. Datenlecks mit Informationen auf dieser SharePoint-Site könnten das Projekt kompromittieren und hätten erheblichen Einfluss auf den Projekterfolg. Durch Priorisierung dieser SharePoint-Site in einer Datenleckrichtlinie werden die Risikobewertungen für qualifizierende Aktivitäten automatisch erhöht. Diese Priorisierung erhöht die Wahrscheinlichkeit, dass diese Aktivitäten eine Insider-Risikowarnung generieren, und erhöht den Schweregrad der Warnung.

Wenn Sie im Richtlinien-Assistenten eine Insider-Risikomanagement-Richtlinie erstellen, stehen Ihnen die folgenden Prioritäten zur Auswahl:

- **SharePoint-Sites**: Jede Aktivität, die mit allen Dateitypen auf definierten SharePoint-Sites verknüpft ist, erhält eine höhere Risikobewertung. 
- **Typen vertraulicher Informationen**: Jegliche Aktivität, die mit Inhalten verknüpft ist, die [Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md) enthalten, erhält eine höhere Risikobewertung.
- **Vertraulichkeitsbezeichnungen**: Jegliche Aktivität, die mit Inhalten in Zusammenhang steht, auf die spezielle [Vertraulichkeitsbezeichnungen](sensitivity-labels.md) angewendet wurden, erhält eine höhere Risikobewertung.

## <a name="sequence-detection-preview"></a>Sequenzerkennung (Vorschau)

Riskante Aktivitäten müssen nicht als isolierte Ereignisse auftreten. Diese Risiken sind häufig Teil einer größeren Ereignissequenz. Eine Sequenz ist eine Gruppe von zwei oder mehr Benutzeraktivitäten, die nacheinander ausgeführt werden und eventuell auf ein erhöhtes Risiko schließen lassen. Das Identifizieren dieser relevanten Aktivitäten ist ein wichtiger Bestandteil der Auswertung des Gesamtrisikos. Wenn die Sequenzerkennung für Datendiebstahl- oder Datenleckrichtlinien aktiviert ist, werden Erkenntnisse aus Sequenzinformationsaktivitäten auf der Registerkarte **Benutzeraktivität** in einem Insider-Risikomanagementfall angezeigt. Die folgenden Richtlinienvorlagen unterstützen Sequenzerkennung:

- Datendiebstahl durch ausscheidende Benutzer
- Allgemeine Datenlecks
- Datenlecks durch prioritäre Benutzer
- Datenlecks durch verärgerte Benutzer

Diese Insider-Risikomanagement-Richtlinien können bestimmte Indikatoren und die Reihenfolge, in der sie auftreten, verwenden, um jeden Schritt in einer Risikosequenz zu erkennen. Beim Zuordnen von Aktivitäten über eine Sequenz hinweg werden Dateinamen verwendet. Diese Risiken sind in vier Hauptkategorien von Aktivitäten unterteilt:

- **Sammlung**: Diese Kategorie signalisiert den Fokus auf Downloadaktivitäten durch im Umfang einer Richtlinie enthaltene Benutzer. Eine Beispielaktivität in dieser Kategorie wäre das Herunterladen von Dateien von SharePoint-Sites.
- **Exfiltration**: Diese Kategorie signalisiert den Fokus auf Freigabe- oder Extraktionsaktivitäten an internen und externen Quellen durch im Umfang einer Richtlinie enthaltene Benutzer. Eine Beispielaktivität in dieser Kategorie wäre das Senden von E-Mails mit Anlagen aus Ihrer Organisation an externe Empfänger.
- **Verschleierung**: Diese Kategorie signalisiert den Fokus auf der Maskierung riskanter Aktivitäten durch im Umfang einer Richtlinie enthaltene Benutzer. Eine Beispielaktivität in dieser Kategorie wäre das Umbenennen von Dateien auf einem Gerät.
- **Bereinigung**: Diese Kategorie signalisiert den Fokus auf Löschaktivitäten durch im Umfang einer Richtlinie enthaltene Benutzer. Eine Beispielaktivität in dieser Kategorie wäre das Löschen von Dateien auf einem Gerät.

> [!NOTE]
> Die Sequenzerkennung verwendet Indikatoren, die in den globalen Einstellungen für das Insider-Risikomanagement aktiviert sind, sowie Indikatoren, die in einer Richtlinie ausgewählt sind. Wenn keine geeigneten Indikatoren ausgewählt sind, funktioniert die Sequenzerkennung nicht.

Sie können einzelne Schwellenwerteinstellungen für jeden Sequenzerkennungstyp anpassen, wenn dieser in der Richtlinie konfiguriert ist. Mit diesen Schwellenwerteinstellungen werden Warnungen auf Grundlage der Menge der Dateien angepasst, die der Sequenz zugeordnet sind.

Weitere Informationen zur Verwaltung der Sequenzerkennung in der Ansicht **Benutzeraktivität** finden Sie unter [Insider-Risikomanagementfälle: Benutzeraktivität](insider-risk-management-cases.md#user-activity).

## <a name="cumulative-exfiltration-detection-preview"></a>Erkennung kumulativer Exfiltration (Vorschau)

Insider-Risikoindikatoren helfen dabei, ungewöhnliche Niveaus von Risikoaktivitäten zu erkennen, wenn diese täglich für Benutzer ausgewertet werden, die sich im Umfang von Insider-Risikorichtlinien befinden. Die Erkennung kumulativer Exfiltration verwendet Machine Learning-Modelle, um zu erkennen, wann Exfiltrationsaktivitäten von Benutzern die Durchschnittswerte der Organisation überschreiten, wenn sie über einen Zeitraum und für mehrere Typen von Exfiltrationsaktivitäten gemessen wurden. Analysten und Prüfer des Insider-Risikomanagements können mithilfe von Erkenntnissen der Erkennung kumulativer Exfiltration Exfiltrationsaktivitäten identifizieren, die normalerweise keine Warnungen generieren, jedoch den für ihre Organisation typischen Umfang überschreiten. Einige Beispiele können ausscheidende Benutzer sein, die Daten langsam über Tage verteilt exfiltrieren, oder wenn Benutzer häufiger als in Ihrer Organisation für die Datenfreigabe gewöhnlich wiederholt Daten über mehrere Kanäle teilen.

Die Erkennung kumulierter Exfiltration ist standardmäßig aktiviert, wenn die folgenden Richtlinienvorlagen verwendet werden:

- Datendiebstahl durch ausscheidende Benutzer
- Allgemeine Datenlecks
- Datenlecks durch prioritäre Benutzer
- Datenlecks durch verärgerte Benutzer

> [!NOTE]
> Die Erkennung kumulativer Exfiltration verwendet Exfiltrationsindikatoren, die in den globalen Einstellungen für das Insider-Risikomanagement aktiviert sind, sowie Exfiltrationsindikatoren, die in einer Richtlinie ausgewählt sind. Als solches wird die Erkennung kumulativer Exfiltration nur für die erforderlichen, ausgewählten Exfiltrationsindikatoren ausgewertet.

Wenn die Erkennung kumulativer Exfiltration für Datendiebstahl- oder Datenleckrichtlinien aktiviert ist, werden Erkenntnisse aus kumulativen Exfiltrationsaktivitäten auf der Registerkarte **Benutzeraktivität** in einem Insider-Risikomanagementfall angezeigt.

Weitere Informationen zur Verwaltung von Benutzeraktivitäten finden Sie unter [Insider-Risikomanagementfälle: Benutzeraktivitäten](insider-risk-management-cases.md#user-activity).

## <a name="policy-health-preview"></a>Richtlinienintegrität (Vorschau)

Der Richtlinienintegritätsstatus verschafft Ihnen Erkenntnisse über potenzielle Probleme mit Ihren Insider-Risikomanagement-Richtlinien. In der Spalte „Status“ auf der Registerkarte „Richtlinien“ können Sie auf Richtlinienprobleme aufmerksam gemacht werden, die möglicherweise verhindern, dass Benutzeraktivitäten gemeldet werden, oder warum die Anzahl der Aktivitätswarnungen ungewöhnlich ist. Der Richtlinienintegritätsstatus kann auch bestätigen, dass die Richtlinie fehlerfrei ist und keine Maßnahmen oder Konfigurationsänderungen erforderlich sind.

Wenn es Probleme mit einer Richtlinie gibt, werden im Richtlinienintegritätsstatus Warnungen und Empfehlungen angezeigt, die Ihnen helfen sollen, Maßnahmen zur Lösung von Richtlinienproblemen zu ergreifen. Diese Benachrichtigungen können Ihnen bei der Behebung dieser Probleme helfen:

- Richtlinien mit unvollständiger Konfiguration. Diese Probleme können fehlende Benutzer oder Gruppen in der Richtlinie oder andere unvollständige Richtlinienkonfigurationsschritte umfassen.
- Richtlinien mit Problemen bei der Indikatorkonfiguration. Indikatoren sind ein wichtiger Bestandteil jeder Richtlinie. Wenn Indikatoren nicht konfiguriert sind, oder wenn zu wenige Indikatoren ausgewählt sind, wertet die Richtlinie riskante Aktivitäten möglicherweise nicht erwartungsgemäß aus.
- Richtlinientrigger funktionieren nicht, oder Anforderungen an Richtlinientrigger sind nicht ordnungsgemäß konfiguriert. Die Richtlinienfunktionalität kann von anderen Diensten oder Konfigurationsanforderungen abhängig sein, um auslösende Ereignisse effektiv zu erkennen und so die Zuweisung von Risikobewertungen an Benutzer in der Richtlinie zu aktivieren. Diese Abhängigkeiten können Probleme mit der Connectorkonfiguration, mit der Warnungsfreigabe von Microsoft Defender für Endpunkte oder mit den Konfigurationseinstellungen von Richtlinien zur Verhinderung von Datenverlust umfassen.
- Die Volumengrenzwerte nähern sich den Grenzwerten oder überschreiten sie. Insider-Risikomanagement-Richtlinien verwenden zahlreiche Microsoft 365-Dienste und -Endpunkte, um Signale von Risikoaktivitäten zu aggregieren. Abhängig von der Anzahl der Benutzer in Ihren Richtlinien können Volumengrenzwerte die Identifizierung und Meldung von Risikoaktivitäten verzögern. Weitere Informationen zu diesen Grenzwerten finden Sie im Abschnitt „Grenzwerte für Richtlinienvorlagen“ in diesem Artikel.

Um schnell den Integritätsstatus einer Richtlinie anzuzeigen, navigieren Sie zur Registerkarte „Richtlinie“ und zur Spalte „Status“. Hier werden die folgenden Optionen für den Richtlinienintegritätsstatus der jeweiligen Richtlinie angezeigt:

- Fehlerfrei: Es wurden keine Probleme mit der Richtlinie identifiziert.
- Empfehlungen: Es gibt ein paar Probleme mit der Richtlinie, die möglicherweise verhindern, dass die Richtlinie wie erwartet funktioniert.
- Warnungen: Es gibt Probleme mit der Richtlinie, die verhindern, dass sie riskante Aktivitäten identifiziert.

Um weitere Details zu Empfehlungen oder Warnungen zu erhalten, wählen Sie eine Richtlinie auf der Registerkarte **Richtlinie** aus, um die Karte „Richtliniendetails“ zu öffnen. Weitere Informationen zu den Empfehlungen und Warnungen, einschließlich Anleitungen zur Behandlung dieser Probleme, werden im Abschnitt „Benachrichtigungen“ der Karte „Details“ angezeigt.

![Integrität von Insider-Risikomanagement-Richtlinien](../media/insider-risk-policy-health.png)

In der folgenden Tabelle finden Sie weitere Informationen zu Empfehlungen und Warnungsbenachrichtigungen sowie zu den Maßnahmen, die Sie ergreifen können, um potenzielle Probleme zu beheben.

|**Benachrichtigungen**|**Richtlinienvorlagen**|**Ursachen/Korrekturversuch mit dieser Aktion**|
|:------------------------|:-------------------|:---------------------------|
| Die Richtlinie weist Aktivitäten keine Risikobewertungen zu. | Alle Richtlinienvorlagen | Sie sollten die Konfiguration des Umfangs und der auslösenden Ereignisse Ihrer Richtlinie überprüfen, damit die Richtlinie Risikobewertungen zu Aktivitäten zuweisen kann. <br><br> 1. Überprüfen Sie die Benutzer, die für die Richtlinie ausgewählt sind. Wenn Sie nur wenige Benutzer ausgewählt haben, sollten Sie weitere Benutzer auswählen. <br> 2. Wenn Sie einen HR-Connector verwenden, überprüfen Sie, ob Ihr HR-Connector die richtigen Daten sendet. <br> 3. Wenn Sie eine DLP-Richtlinie als Ihr auslösendes Ereignis verwenden, überprüfen Sie ihre DLP-Richtlinienkonfiguration, um sicherzustellen, dass sie für die Verwendung in dieser Richtlinie konfiguriert ist. <br> 4. Überprüfen Sie bei Richtlinien für Sicherheitsverstöße den Warnungsselektierungsstatus von Microsoft Defender für Endpunkt, der in „Insider-Risikoeinstellungen > Intelligente Erkennungen“ ausgewählt ist. Vergewissern Sie sich, dass der Warnungsfilter nicht zu eng gefasst ist. |
| Die Richtlinie hat noch keine Warnungen generiert. | Alle Richtlinienvorlagen | Sie sollten Ihre Richtlinienkonfiguration überprüfen, damit Sie die Bewertung der betreffenden Aktivität analysieren. <br><br> 1. Vergewissern Sie sich, dass Sie Indikatoren ausgewählt haben, die Sie bewerten möchten. Je mehr Indikatoren ausgewählt sind, desto mehr Risikobewertungen werden zu Aktivitäten zugewiesen. <br> 2. Überprüfen sie die Anpassung der Schwellenwerte für die Richtlinie. Wenn die ausgewählten Schwellenwerte nicht an der Risikotoleranz Ihrer Organisation ausgerichtet sind, passen Sie die Auswahl so an, dass Warnungen auf Grundlage Ihrer bevorzugten Schwellenwerten erzeugt werden. <br> 3. Überprüfen Sie die für die Richtlinie ausgewählten Benutzer und Gruppen. Vergewissern Sie sich, dass Sie alle anwendbaren Benutzer und Gruppen ausgewählt haben. <br> 4. Vergewissern Sie sich bei Richtlinien für Sicherheitsverstöße, dass Sie den Warnungsselektierungsstatus, den Sie für Microsoft Defender für Endpunkt-Warnungen bewerten möchten, in den Einstellungen unter „Intelligente Erkennungen“ ausgewählt haben.|
| In dieser Richtlinie sind keine Benutzer oder Gruppen enthalten. | Alle Richtlinienvorlagen | Der Richtlinie sind keine Benutzer oder Gruppen zugewiesen. <br><br> Bearbeiten Sie Ihre Richtlinie, und wählen Sie Benutzer oder Gruppen für die Richtlinie aus. |
| Für diese Richtlinie wurden keine Indikatoren ausgewählt. | Alle Richtlinienvorlagen | Für die Richtlinie wurden keine Indikatoren ausgewählt. <br><br> Bearbeiten Sie Ihre Richtlinie, und wählen Sie geeignete Richtlinienindikatoren für die Richtlinie aus. |
| Es sind keine Gruppen prioritärer Benutzer in dieser Richtlinie enthalten. | – Datenlecks durch prioritäre Benutzer <br> – Verstöße gegen Sicherheitsrichtlinien durch prioritäre Benutzer | Der Richtlinie sind keine Gruppen prioritärer Benutzer zugewiesen. <br><br> Konfigurieren Sie Gruppen prioritärer Benutzer in den Einstellungen für das Insider-Risikomanagement, und weisen Sie der Richtline Gruppen prioritärer Benutzer zu. |
| Für diese Richtlinie wurde kein auslösendes Ereignis ausgewählt. | Alle Richtlinienvorlagen | Für die Richtlinie ist kein auslösendes Ereignis konfiguriert. <br><br> Risikobewertungen werden Benutzeraktivitäten erst zugewiesen, wenn Sie die Richtlinie bearbeiten und ein auslösendes Ereignis auswählen. |
| Der HR-Connector ist nicht konfiguriert oder funktioniert nicht wie erwartet. | – Datendiebstahl durch ausscheidende Benutzer <br> – Verstöße gegen Sicherheitsrichtlinien durch ausscheidende Benutzer <br> – Datenlecks durch verärgerte Benutzer <br> – Verstöße gegen Sicherheitsrichtlinien durch verärgerte Benutzer | Es liegt ein Problem mit dem HR-Connector vor. <br><br> 1. Wenn Sie einen HR-Connector verwenden, überprüfen Sie, ob Ihr HR-Connector die richtigen Daten sendet. <br><br> ODER <br><br> 2. Wählen Sie das auslösende Ereignis „Azure AD-Konto gelöscht“ aus. |
| Es wurden noch keine Geräte integriert. | – Datendiebstahl durch ausscheidende Benutzer <br> – Allgemeine Datenlecks <br> – Datenlecks durch verärgerte Benutzer <br> – Datenlecks durch prioritäre Benutzer | Geräteindikatoren sind ausgewählt, aber es sind keine Geräte in Microsoft 365 integriert. <br><br> Überprüfen Sie, ob Geräte eingebunden sind und die Anforderungen erfüllen. |
| Der HR-Connector hat in letzter Zeit keine Daten hochgeladen. | – Datendiebstahl durch ausscheidende Benutzer <br> – Verstöße gegen Sicherheitsrichtlinien durch ausscheidende Benutzer <br> – Datenlecks durch verärgerte Benutzer <br> – Verstöße gegen Sicherheitsrichtlinien durch verärgerte Benutzer | Der HR-Connector hat länger als 7 Tage keine Daten importiert. <br><br> Überprüfen Sie, ob Ihr HR-Connector richtig konfiguriert ist und Daten sendet. |
| Wir können den Status Ihres HR-Connectors derzeit nicht überprüfen. Versuchen Sie es bitte später noch mal. | – Datendiebstahl durch ausscheidende Benutzer <br> – Verstöße gegen Sicherheitsrichtlinien durch ausscheidende Benutzer <br> – Datenlecks durch verärgerte Benutzer <br> – Verstöße gegen Sicherheitsrichtlinien durch verärgerte Benutzer | Die Insider-Risikomanagementlösung kann den Status Ihres HR-Connectors nicht überprüfen. <br><br> Überprüfen Sie, ob Ihr HR-Connector richtig konfiguriert ist und Daten sendet, oder kehren Sie zurück, und überprüfen Sie den Richtlinienstatus.  |
| Die DLP-Richtlinie ist nicht als auslösendes Ereignis ausgewählt. | – Allgemeine Datenlecks <br> – Datenlecks durch prioritäre Benutzer | Es wurde keine DLP-Richtlinie als auslösendes Ereignis ausgewählt, oder die ausgewählte DLP-Richtlinie wurde gelöscht. <br><br> Bearbeitung Sie die Richtlinie, und wählen Sie entweder eine aktive DLP-Richtlinie oder „Benutzer führt eine Exfiltrationsaktivität durch“ als auslösendes Ereignis in der Richtlinienkonfiguration aus. |
| Die in dieser Richtlinie verwendete DLP-Richtlinie ist deaktiviert. | – Allgemeine Datenlecks <br> – Datenlecks durch prioritäre Benutzer | Die in dieser Richtlinie verwendete DLP-Richtlinie ist deaktiviert. <br><br> 1. Aktivieren Sie die DLP-Richtlinie, die dieser Richtlinie zugewiesen ist. <br><br> ODER <br><br> 2. Bearbeitung Sie diese Richtlinie, und wählen Sie entweder eine neue DLP-Richtlinie oder „Benutzer führt eine Exfiltrationsaktivität durch“ als auslösendes Ereignis in der Richtlinienkonfiguration aus. |
| Die DLP-Richtlinie entspricht nicht den Anforderungen. | – Allgemeine Datenlecks <br> – Datenlecks durch prioritäre Benutzer | Als auslösende Ereignisse verwendete DLP-Richtlinien müssen zum Generieren von Warnungen mit hohem Schweregrad konfiguriert sein. <br><br>  1. Bearbeiten Sie Ihre DLP-Richtlinie, um anwendbare Warnungen als *Schweregrad „Hoch“* zuzuweisen. <br><br> ODER <br><br> 2. Bearbeitung Sie diese Richtlinie, und wählen Sie *Benutzer führt eine Exfiltrationsaktivität durch* als auslösendes Ereignis aus. |
| Ihre Organisation besitzt kein Abonnement für Microsoft Defender für Endpunkt. | – Allgemeine Verstöße gegen Sicherheitsrichtlinien <br> – Verstöße gegen Sicherheitsrichtlinien durch ausscheidende Benutzer <br> – Verstöße gegen Sicherheitsrichtlinien durch verärgerte Benutzer <br> – Verstöße gegen Sicherheitsrichtlinien durch prioritäre Benutzer | Es wurde kein aktives Microsoft Defender für Endpunkt-Abonnement für Ihre Organisation gefunden. <br><br> Diese Richtlinien weisen Benutzeraktivitäten erst dann Risikobewertungen zu, wenn ein Microsoft Defender für Endpunkt-Abonnement hinzugefügt wurde. |
| Microsoft Defender für Endpunkt-Warnungen werden nicht mit dem Compliance-Center geteilt.. | – Allgemeine Verstöße gegen Sicherheitsrichtlinien <br> – Verstöße gegen Sicherheitsrichtlinien durch ausscheidende Benutzer <br> – Verstöße gegen Sicherheitsrichtlinien durch verärgerte Benutzer <br> – Verstöße gegen Sicherheitsrichtlinien durch prioritäre Benutzer | Microsoft Defender für Endpunkt-Warnungen werden nicht mit dem Compliance-Center geteilt. <br><br> Konfigurieren Sie das Teilen von Microsoft Defender für Endpunkt-Warnungen. |
| Sie nähern sich dem maximalen Grenzwert von aktiv bewerteten Benutzern für diese Richtlinienvorlage. | Alle Richtlinienvorlagen | Jede Richtlinienvorlage besitzt eine maximale Anzahl von im Umfang enthaltenen Benutzern. Informationen hierzu finden Sie in den Details im Abschnitt mit den Vorlagengrenzwerten. <br><br> Überprüfen Sie die Benutzer auf der Registerkarte „Benutzer“, und entfernen Sie alle Benutzer, die nicht mehr bewertet werden müssen. |

## <a name="policy-template-limits"></a>Grenzwerte für Richtlinienvorlagen

Insider-Risikomanagement-Richtlinienvorlagen verwenden Grenzwerte, um Verarbeitungsvolumen und -rate für Risikoaktivitäten von im Umfang enthaltenen Benutzern sowie die Art, in der dieser Prozess in unterstützende Microsoft 365-Dienste integriert wird, zu verwalten. Jede Richtlinienvorlage besitzt eine maximale Anzahl von Benutzern, denen aktiv Risikobewertungen für die Richtlinie, die sie unterstützen kann, zugewiesen werden können, sowie einen Höchstwert an Risikoaktivitäten, die effektiv verarbeitet und gemeldet werden können. Im Umfang enthaltene Benutzer sind Benutzer mit auslösenden Ereignissen für die Richtlinie.

Der Grenzwert für jede Richtlinie wird auf Grundlage der Gesamtzahl der eindeutigen Benutzer berechnet, die Risikobewertungen pro Richtlinienvorlagentyp erhalten. Wenn sich die Anzahl der Benutzer für einen Richtlinienvorlagentyp dem Benutzergrenzwert nähert oder diesen überschreitet, verringert sich die Richtlinienleistung. Um die aktuelle Anzahl von Benutzern für eine Richtlinie anzuzeigen, navigieren Sie zur Registerkarte „Richtlinie“ und zur Spalte „Benutzer im Umfang“. Für jede Richtlinienvorlage können bis zu fünf Richtlinien vorhanden sein. Diese maximalen Grenzwerte gelten für Benutzer in allen Richtlinien, die eine bestimmte Richtlinienvorlage verwenden.

Mithilfe der folgenden Tabelle können Sie die maximale Anzahl von im Umfang enthaltenen Benutzern ermitteln, die für jede Richtlinienvorlage unterstützt werden:

|**Richtlinienvorlage**|**Aktueller Höchstwert für im Umfang enthaltene Benutzer**|
|:------------------|:--------------------------------|
| Allgemeines Datenleck | 15.000 |
| Datenlecks durch verärgerte Benutzer | 7.500 |
| Datenlecks durch prioritäre Benutzer | 1.000 |
| Datendiebstahl durch ausscheidende Benutzer | 20.000 |
| Allgemeine Verstöße gegen Sicherheitsrichtlinien | 1.000 |
| Verstöße gegen Sicherheitsrichtlinien durch prioritäre Benutzer | 1.000 |
| Verstöße gegen Sicherheitsrichtlinien durch ausscheidende Benutzer | 15.000 |
| Verstöße gegen Sicherheitsrichtlinien durch verärgerte Benutzer | 7.500 |

## <a name="create-a-new-policy"></a>Erstellen einer neuen Richtlinie

Wenn Sie eine neue Insider-Risikomanagement-Richtlinie erstellen möchten, verwenden Sie den Richtlinien-Assistenten in der **Insider-Risikomanagement**-Lösung im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine neue Richtlinie zu erstellen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com) zu **Insider-Risikomanagement**, und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie **Richtlinie erstellen** aus, um den Richtlinien-Assistenten zu öffnen.
3. Wählen Sie auf der Seite **Richtlinienvorlage** eine Richtlinienkategorie aus, und wählen Sie dann die Vorlage für die neue Richtlinie aus. Diese Vorlagen bestehen aus Bedingungen und Indikatoren, die die zu erkennenden und zu untersuchenden Risikoaktivitäten definieren. Überprüfen Sie die Vorlagenvoraussetzungen, die auslösenden Ereignisse und die erkannten Aktivitäten, um zu bestätigen, dass diese Richtlinienvorlage Ihren Anforderungen entspricht.

    > [!IMPORTANT]
    > Für einige Richtlinienvorlagen gibt es Voraussetzungen, die für die Richtlinie konfiguriert werden müssen, damit sie relevante Warnungen generiert. Wenn Sie die anwendbaren Richtlinienvoraussetzungen nicht konfiguriert haben, sehen Sie weiter oben unter **Schritt 4** nach.

4. Wählen Sie **Weiter** aus, um fortzufahren.
5. Füllen Sie auf der Seite **Name und Beschreibung** die folgenden Felder aus:
    - **Name (erforderlich)**: Geben Sie einen Anzeigenamen für die Richtlinie ein. Dieser Name kann nach dem Erstellen der Richtlinie nicht mehr geändert werden.
    - **Beschreibung (optional)**: Geben Sie eine Beschreibung für die Richtlinie ein.

6. Wählen Sie **Weiter** aus, um fortzufahren.
7. Wählen Sie auf der Seite **Benutzer und Gruppen** die Option **Alle Benutzer und Gruppen einschließen** oder **Bestimmte Benutzer und Gruppen einschließen** aus, um zu definieren, welche Benutzer oder Gruppen in die Richtlinie einbezogen werden, oder wenn Sie eine auf prioritären Benutzern basierende Vorlage ausgewählt haben, wählen Sie **Gruppen prioritärer Benutzer hinzufügen oder bearbeiten** aus. Wenn Sie **Alle Benutzer und Gruppen einschließen** auswählen, wird nach auslösenden Ereignissen für alle Benutzer und Gruppen in Ihrer Organisation gesucht, um mit dem Zuweisen von Risikobewertungen für die Richtlinie zu beginnen. Wenn Sie **Bestimmte Benutzer und Gruppen einschließen** auswählen, können Sie definieren, welche Benutzer und Gruppen der Richtlinie zugewiesen werden sollen.
8. Wählen Sie **Weiter** aus, um fortzufahren.
9. Auf der Seite **Zu priorisierende Inhalte** können Sie (bei Bedarf) die zu priorisierenden Quellen zuweisen, wodurch sich die Wahrscheinlichkeit erhöht, dass eine Warnung mit hohem Schweregrad für diese Quellen generiert wird. Wählen Sie eine der folgenden Optionen aus:

    - **Ich möchte SharePoint-Sites, Vertraulichkeitsbezeichnungen und/oder Typen vertraulicher Informationen als Inhalte mit Priorität angeben**. Wenn Sie diese Option auswählen, werden Detailseiten im Assistenten aktiviert, um diese Kanäle zu konfigurieren.
    - **Ich möchte jetzt keine Inhalte mit Priorität angeben (Sie können dies nach der Erstellung der Richtlinie tun)**. Wenn Sie diese Option auswählen, werden die Kanaldetailseiten im Assistenten übersprungen.

10. Wählen Sie **Weiter** aus, um fortzufahren.

11. Wenn Sie im vorherigen Schritt **Ich möchte SharePoint-Sites, Vertraulichkeitsbezeichnungen und/oder Typen vertraulicher Informationen als Inhalte mit Priorität angeben** ausgewählt haben, werden die Detailseiten für *SharePoint-Sites*, *Typen vertraulicher Informationen* und *Vertraulichkeitsbezeichnungen* angezeigt. Auf diesen Detailseiten können Sie die SharePoint-Sites, die Typen vertraulicher Informationen und die Vertraulichkeitsbezeichnungen definieren, die in der Richtlinie priorisiert werden sollen.

    - **SharePoint-Sites**: Wählen Sie **SharePoint-Site hinzufügen** und dann die SharePoint-Sites aus, auf die Sie Zugriff haben und die Sie priorisieren möchten. Beispiel: *„group1@contoso.sharepoint.com/sites/group1“*.
    - **Typ vertraulicher Informationen**: Wählen Sie **Typ vertraulicher Informationen hinzufügen** und dann die Typen vertraulicher Informationen aus, die Sie priorisieren möchten. Beispiel: *„US-Bankkontonummer“* oder *„Kreditkartennummer“*.
    - **Vertraulichkeitsbezeichnungen**: Wählen Sie **Vertraulichkeitsbezeichnung hinzufügen** und dann die Vertraulichkeitsbezeichnungen aus, die Sie priorisieren möchten. Beispiel: *„Vertraulich“* oder *„Geheim“*.

12. Wählen Sie **Weiter** aus, um fortzufahren.
13. Auf der Seite **Indikatoren und auslösende Ereignisse** werden die [Indikatoren](insider-risk-management-settings.md#indicators) angezeigt, die Sie auf der Seite **Insider-Risikoeinstellungen** > **Indikatoren** als verfügbar definiert haben. Wenn Sie am Anfang des Assistenten eine *Datenleck* vorlage ausgewählt haben, müssen Sie aus der Dropdownliste **DLP-Richtlinie** eine DLP-Richtlinie auswählen, um das Auslösen von Indikatoren für die Richtlinie zu aktivieren, oder das integrierte auslösende Ereignis auswählen.

    > [!IMPORTANT]
    > Wenn Indikatoren auf dieser Seite nicht ausgewählt werden können, müssen Sie die Indikatoren auswählen, die Sie für alle Richtlinien aktivieren möchten. Sie können die Schaltfläche **Indikatoren aktivieren** im Assistenten verwenden oder Indikatoren auf der Seite **Insider-Risikomanagement** > **Einstellungen** > **Richtlinienindikatoren** auswählen.

    Wählen Sie die Indikatoren aus, die Sie auf die Richtlinie anwenden möchten. Wenn Sie für diese Indikatoren lieber nicht die Standardeinstellungen für Richtlinienschwellenwerte verwenden möchten, deaktivieren Sie **Von Microsoft empfohlene Standardschwellenwerte verwenden**, und geben Sie die Schwellenwerte für jeden ausgewählten Indikator ein.

    - Wenn Sie mindestens einen *Office*- oder *Geräte*-Indikator ausgewählt haben, wählen Sie die entsprechenden **Risikobewertungsverstärker** aus. Risikobewertungsverstärker sind nur auf ausgewählte Indikatoren anwendbar.
    - Wenn Sie eine *Datendiebstahl*- oder *Datenleck*-Richtlinienvorlage ausgewählt haben, wählen Sie eine oder mehrere **Sequenzerkennungs** methoden sowie eine Methode für die **Erkennung kumulativer Exfiltration** aus, die auf die Richtlinie angewendet werden sollen.

14. Wählen Sie **Weiter** aus, um fortzufahren.
15. Wählen Sie auf der Seite **Indikatorschwellenwerte** die Option aus, um Standardschwellenwerte für Indikatoren zu verwenden, oder die, um benutzerdefinierte Schwellenwerte für einzelne Indikatoren anzugeben. Wählen Sie für jeden Indikator die geeignete Stufe aus, um den gewünschten Schwergrad von Aktivitätswarnungen zu generieren.
16. Wählen Sie **Weiter** aus, um fortzufahren.
17. Überprüfen Sie auf der Seite **Überprüfen** die Einstellungen, die Sie für die Richtlinie ausgewählt haben, sowie alle Vorschläge oder Warnungen zu Ihrer Auswahl. Wählen Sie **Bearbeiten** aus, um die Richtlinienwerte zu ändern, oder wählen Sie **Absenden** aus, um die Richtlinie zu erstellen und zu aktivieren.

## <a name="update-a-policy"></a>Aktualisieren einer Richtlinie

Um eine vorhandene Insider-Risikomanagement-Richtlinie zu aktualisieren, verwenden Sie den Richtlinien-Assistenten in der **Insider-Risikomanagement**-Lösung im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine vorhandene Richtlinie zu verwalten:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com) zu **Insider-Risikomanagement**, und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie im Richtlinien-Dashboard die Richtlinie aus, die verwaltet werden soll.
3. Wählen Sie auf der Seite „Richtliniendetails“ die Option **Richtlinie bearbeiten** aus.
4. Folgendes können Sie im Richtlinien-Assistenten nicht bearbeiten:
    - **Richtlinienvorlage**: Die Vorlage, die zum Definieren der Arten von Risikoindikatoren verwendet wird, die von der Richtlinie überwacht werden.
    - **Name**: Der Anzeigename für die Richtlinie.
5. Aktualisieren Sie auf der Seite **Name und Beschreibung** die Beschreibung für die Richtlinie im Feld **Beschreibung**.
6. Wählen Sie **Weiter** aus, um fortzufahren.
7. Wählen Sie auf der Seite **Benutzer und Gruppen** die Option **Alle Benutzer und Gruppen einschließen** oder **Bestimmte Benutzer und Gruppen einschließen** aus, um zu definieren, welche Benutzer oder Gruppen in die Richtlinie einbezogen werden, oder wenn Sie eine auf prioritären Benutzern basierende Vorlage ausgewählt haben, wählen Sie **Gruppen prioritärer Benutzer hinzufügen oder bearbeiten** aus. Wenn Sie **Alle Benutzer und Gruppen einschließen** auswählen, wird nach auslösenden Ereignissen für alle Benutzer und Gruppen in Ihrer Organisation gesucht, um mit dem Zuweisen von Risikobewertungen für die Richtlinie zu beginnen. Wenn Sie **Bestimmte Benutzer und Gruppen einschließen** auswählen, können Sie definieren, welche Benutzer und Gruppen der Richtlinie zugewiesen werden sollen.
8. Wählen Sie **Weiter** aus, um fortzufahren.
9. Auf der Seite **Zu priorisierende Inhalte** können Sie (bei Bedarf) die zu priorisierenden Quellen zuweisen, wodurch sich die Wahrscheinlichkeit erhöht, dass eine Warnung mit hohem Schweregrad für diese Quellen generiert wird. Wählen Sie eine der folgenden Optionen aus:

    - **Ich möchte SharePoint-Sites, Vertraulichkeitsbezeichnungen und/oder Typen vertraulicher Informationen als Inhalte mit Priorität angeben**. Wenn Sie diese Option auswählen, werden Detailseiten im Assistenten aktiviert, um diese Kanäle zu konfigurieren.
    - **Ich möchte jetzt keine Inhalte mit Priorität angeben (Sie können dies nach der Erstellung der Richtlinie tun)**. Wenn Sie diese Option auswählen, werden die Kanaldetailseiten im Assistenten übersprungen.

10. Wählen Sie **Weiter** aus, um fortzufahren.

11. Wenn Sie im vorherigen Schritt **Ich möchte SharePoint-Sites, Vertraulichkeitsbezeichnungen und/oder Typen vertraulicher Informationen als Inhalte mit Priorität angeben** ausgewählt haben, werden die Detailseiten für *SharePoint-Sites*, *Typen vertraulicher Informationen* und *Vertraulichkeitsbezeichnungen* angezeigt. Auf diesen Detailseiten können Sie die SharePoint-Sites, die Typen vertraulicher Informationen und die Vertraulichkeitsbezeichnungen definieren, die in der Richtlinie priorisiert werden sollen.

    - **SharePoint-Sites**: Wählen Sie **SharePoint-Site hinzufügen** und dann die SharePoint-Sites aus, auf die Sie Zugriff haben und die Sie priorisieren möchten. Beispiel: *„group1@contoso.sharepoint.com/sites/group1“*.
    - **Typ vertraulicher Informationen**: Wählen Sie **Typ vertraulicher Informationen hinzufügen** und dann die Typen vertraulicher Informationen aus, die Sie priorisieren möchten. Beispiel: *„US-Bankkontonummer“* oder *„Kreditkartennummer“*.
    - **Vertraulichkeitsbezeichnungen**: Wählen Sie **Vertraulichkeitsbezeichnung hinzufügen** und dann die Vertraulichkeitsbezeichnungen aus, die Sie priorisieren möchten. Beispiel: *„Vertraulich“* oder *„Geheim“*.

12. Wählen Sie **Weiter** aus, um fortzufahren.
13. Auf der Seite **Indikatoren und auslösende Ereignisse** werden die [Indikatoren](insider-risk-management-settings.md#indicators) angezeigt, die Sie auf der Seite **Insider-Risikoeinstellungen** > **Indikatoren** als verfügbar definiert haben. Wenn Sie am Anfang des Assistenten eine *Datenleck* vorlage ausgewählt haben, müssen Sie aus der Dropdownliste **DLP-Richtlinie** eine DLP-Richtlinie auswählen, um das Auslösen von Indikatoren für die Richtlinie zu aktivieren, oder das integrierte auslösende Ereignis auswählen.

    > [!IMPORTANT]
    > Wenn Indikatoren auf dieser Seite nicht ausgewählt werden können, müssen Sie die Indikatoren auswählen, die Sie für alle Richtlinien aktivieren möchten. Sie können die Schaltfläche **Indikatoren aktivieren** im Assistenten verwenden oder Indikatoren auf der Seite **Insider-Risikomanagement** > **Einstellungen** > **Richtlinienindikatoren** auswählen.

    Wählen Sie die Indikatoren aus, die Sie auf die Richtlinie anwenden möchten. Wenn Sie für diese Indikatoren lieber nicht die Standardeinstellungen für Richtlinienschwellenwerte verwenden möchten, deaktivieren Sie **Von Microsoft empfohlene Standardschwellenwerte verwenden**, und geben Sie die Schwellenwerte für jeden ausgewählten Indikator ein.

    - Wenn Sie mindestens einen *Office*- oder *Geräte*-Indikator ausgewählt haben, wählen Sie die entsprechenden **Risikobewertungsverstärker** aus. Risikobewertungsverstärker sind nur auf ausgewählte Indikatoren anwendbar.
    - Wenn Sie eine *Datendiebstahl*- oder *Datenleck*-Richtlinienvorlage ausgewählt haben, wählen Sie eine oder mehrere **Sequenzerkennungs** methoden sowie eine Methode für die **Erkennung kumulativer Exfiltration** aus, die auf die Richtlinie angewendet werden sollen.

14. Wählen Sie **Weiter** aus, um fortzufahren.
15. Wählen Sie auf der Seite **Indikatorschwellenwerte** die Option aus, um Standardschwellenwerte für Indikatoren zu verwenden, oder die, um benutzerdefinierte Schwellenwerte für einzelne Indikatoren anzugeben. Wählen Sie für jeden Indikator die geeignete Stufe aus, um den gewünschten Schwergrad von Aktivitätswarnungen zu generieren.
16. Wählen Sie **Weiter** aus, um fortzufahren.
17. Überprüfen Sie auf der Seite **Überprüfen** die Einstellungen, die Sie für die Richtlinie ausgewählt haben, sowie alle Vorschläge oder Warnungen zu Ihrer Auswahl. Wählen Sie **Bearbeiten** aus, um die Richtlinienwerte zu ändern, oder wählen Sie **Absenden** aus, um die Richtlinie zu erstellen und zu aktivieren.

## <a name="copy-a-policy"></a>Kopieren einer Richtlinie

Eventuell müssen Sie eine neue Richtlinie erstellen, die einer vorhandenen Richtlinie ähnelt, aber nur ein paar Konfigurationsänderungen benötigt. Statt eine vollständig neue Richtlinie zu erstellen, können Sie eine vorhandene Richtlinie kopieren und dann die Bereiche ändern, die in der neuen Richtlinie aktualisiert werden müssen.

Führen Sie die folgenden Schritte aus, um eine vorhandene Richtlinie zu kopieren:

1. Wechseln Sie im Microsoft 365 Compliance Center zu „Insider-Risikomanagement“, und wählen Sie die Registerkarte „Richtlinien“ aus.
2. Wählen Sie im Richtlinien-Dashboard die Richtlinie aus, die kopiert werden soll.
3. Wählen Sie auf der Seite „Richtliniendetails“ die Option „Kopieren“ aus.
4. Benennen Sie im Richtlinien-Assistenten die neue Richtlinie, und aktualisieren Sie die Richtlinienkonfiguration nach Bedarf.

## <a name="immediately-start-scoring-user-activity"></a>Sofortiges Starten der Bewertung von Benutzeraktivitäten

Es kann Szenarien geben, in denen Sie möglicherweise sofort mit dem Zuweisen von Risikobewertungen für Benutzer mit Insider-Risikorichtlinien beginnen müssen, die sich außerhalb des auslösenden Ereignisworkflows des Insider-Risikomanagements befinden. Verwenden Sie **Bewerten der Aktivitäten für Benutzer starten** auf der Registerkarte **Richtlinien**, um einen (oder mehrere) Benutzer mindestens einer Insider-Risikorichtlinie für einen bestimmten Zeitraum manuell hinzuzufügen, um sofort damit zu beginnen, ihrer Aktivität Risikobewertungen zuzuweisen, und die Anforderung zu umgehen, dass ein Benutzer einen auslösenden Indikator (z. B. eine DLP-Richtlinienübereinstimmung) aufweisen muss. Sie können auch einen Grund für das Hinzufügen des Benutzers zur Richtlinie hinzufügen, der in der Aktivitätszeitachse des Benutzers angezeigt wird. Benutzer, die Richtlinien manuell hinzugefügt wurden, werden im **Benutzer**-Dashboard angezeigt, und es werden Warnungen erstellt, wenn die Aktivität die Warnungsschwellenwerte der Richtlinie erfüllt.

Einige Szenarien, bei denen Sie eventuell sofort mit der Bewertung von Benutzeraktivitäten beginnen sollten:

- Wenn Benutzer, für die Bedenken hinsichtlich ihres Risikos bestehen, identifiziert werden, und Sie sofort damit beginnen möchten, ihren Aktivitäten Risikobewertungen für eine oder mehrere Ihrer Richtlinien zuzuweisen.
- Wenn es einen Vorfall gibt, der es erforderlich macht, dass Sie sofort mit dem Zuweisen von Risikobewertungen für die Aktivität der betroffenen Benutzer für eine oder mehrere Ihrer Richtlinien beginnen.
- Wenn Sie Ihren HR-Connector noch nicht konfiguriert haben, aber damit beginnen möchten, Benutzeraktivitäten Risikobewertungen für HR-Ereignisse zuzuweisen, indem Sie eine CSV-Datei für die Benutzer hochladen.

> [!NOTE]
> Es kann mehrere Stunden dauern, bis neue, manuell hinzugefügte Benutzer im **Benutzer**-Dashboard angezeigt werden. Die Anzeige von Aktivitäten für die vorherigen 90 Tage für diese Benutzer kann bis zu 24 Stunden dauern. Um Aktivitäten für manuell hinzugefügte Benutzer anzuzeigen, navigieren Sie zur Registerkarte **Benutzer**, wählen Sie den Benutzer im **Benutzer**-Dashboard aus, und öffnen Sie die Registerkarte **Benutzeraktivität** im Detailbereich.

Um die Bewertung von Aktivitäten für Benutzer in einer oder mehreren Insider-Risikomanagement-Richtlinien manuell zu starten, führen Sie die folgenden Schritte aus:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com) zu **Insider-Risikomanagement**, und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie im Richtlinien-Dashboard die Richtlinie(n) aus, der/denen Sie Benutzer hinzufügen möchten.
3. Wählen Sie **Bewertung der Aktivitäten für Benutzer starten** aus.
4. Fügen Sie im Feld **Grund** im Bereich **Benutzer zu mehreren Richtlinien hinzufügen** einen Grund für das Hinzufügen der Benutzer hinzu.
5. Definieren Sie im Feld **Dies sollte für (wählen Sie zwischen 5 und 30 Tagen) dauern** die Anzahl der Tage, für die die Aktivitäten des Benutzers für die Richtlinie, der er hinzugefügt wurde, bewertet werden sollen.
6. Um Ihr Active Directory nach Benutzern zu durchsuchen, verwenden Sie das Feld **Benutzer suchen, um Sie zu Richtlinien hinzuzufügen**. Geben Sie den Namen des Benutzers ein, den Sie den Richtlinien hinzufügen möchten. Wählen Sie den Benutzernamen aus, und wiederholen Sie den Vorgang, um den Richtlinien weitere Benutzer zuzuweisen. Die Liste der von Ihnen ausgewählten Benutzer wird im Abschnitt „Benutzer“ des Bereichs „Benutzer zu mehreren Richtlinien hinzufügen“ angezeigt.
7. Zum Importieren einer Liste von Benutzern, um sie den Richtlinien hinzuzufügen, wählen Sie **Importieren** aus, um eine CSV-Datei (durch Trennzeichen getrennte Werte) zu importieren. Die Datei muss das folgende Format haben und die Benutzerprinzipalnamen in der Datei auflisten:

    ```csv
    user principal name
    user1@domain.com
    user2@domain.com
    ```

8. Wählen Sie „Benutzer zu Richtlinien hinzufügen“ aus, um die Änderungen zu akzeptieren und den Richtlinien Benutzer hinzuzufügen, oder wählen Sie „Abbrechen“ aus, um die Änderungen zu verwerfen und das Dialogfeld zu schließen.

## <a name="stop-scoring-users-in-a-policy"></a>Beenden der Bewertung von Benutzern in einer Richtlinie

Informationen zum Beenden der Bewertung von Benutzern in einer Richtlinie finden Sie in dem Artikel [Insider-Risikomanagementbenutzer: Entfernen von Benutzern aus der Zuweisung zum Umfang von Richtlinien](insider-risk-management-users.md#remove-users-from-in-scope-assignment-to-policies).

## <a name="delete-a-policy"></a>Löschen einer Richtlinie

> [!NOTE]
> Beim Löschen einer Richtlinie werden keine aktiven oder archivierten Warnungen gelöscht, die von der Richtlinie generiert wurden.

Um eine vorhandene Insider-Risikomanagement-Richtlinie zu löschen, führen Sie die folgenden Schritte aus:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com) zu **Insider-Risikomanagement**, und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie im Richtlinien-Dashboard die Richtlinie aus, die gelöscht werden soll.
3. Wählen Sie **Löschen** auf der Dashboardsymbolleiste aus.
4. Wählen Sie im Dialogfeld **Löschen** die Option **Ja** aus, um die Richtlinie zu löschen, oder wählen Sie **Abbrechen** aus, um das Dialogfeld zu schließen.
