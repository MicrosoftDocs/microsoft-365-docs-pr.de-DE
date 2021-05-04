---
title: Schnelle Aufgaben für die ersten Schritte mit Microsoft 365 Compliance
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- m365-security-compliance
- m365initiative-compliance
localization_priority: Normal
description: Erfahren Sie mehr über Aufgaben, mit deren Hilfe Sie schnell mit der Compliance in Microsoft 365.
ms.openlocfilehash: 3f93eb31800d158a33b1f3c0acdd48d650b2153e
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113391"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Schnelle Aufgaben für die ersten Schritte mit Microsoft 365 Compliance

Wenn Sie sich noch nicht mit Microsoft 365 und fragen, wo Sie beginnen sollten, enthält dieser Artikel Anleitungen zu den Grundlagen und priorisiert wichtige Complianceaufgaben. Dieser Artikel hilft Ihnen, schnell mit der Verwaltung und Überwachung Ihrer Daten, dem Schutz von Informationen und der Minimierung von Insiderrisiken zu beginnen.

Dieser Artikel ist auch hilfreich, wenn Sie herausfinden, wie Sie Risiken am besten verwalten, Ihre Daten schützen und die Vorschriften und Standards mit einer neuen Remote-Belegschaft einhalten können. Mitarbeiter arbeiten jetzt auf neue Weise zusammen und verbinden sich miteinander, und dies bedeutet, dass ihre vorhandenen Complianceprozesse und -steuerelemente möglicherweise angepasst werden müssen. Die Identifizierung und Verwaltung dieser neuen Compliancerisiken in Ihrer Organisation ist entscheidend für den Schutz Ihrer Daten und die Minimierung von Bedrohungen und Risiken.

Nachdem Sie diese grundlegenden Complianceaufgaben abgeschlossen haben, sollten Sie die Complianceabdeckung in Ihrer Organisation erweitern, indem Sie zusätzliche Lösungen Microsoft 365 implementieren.

## <a name="task-1-configure-compliance-permissions"></a>Aufgabe 1: Konfigurieren von Complianceberechtigungen

Es ist wichtig zu verwalten, wer in Ihrer Organisation Zugriff auf das Microsoft 365 Compliance Center hat, um Inhalte anzuzeigen und Verwaltungsaufgaben auszuführen. Microsoft 365 bietet administrative Rollen, die speziell auf die Compliance und die Verwendung der Tools im compliance Center Microsoft 365 sind.

Weisen Sie zunächst den Personen in Ihrer Organisation Complianceberechtigungen zu, damit sie diese Aufgaben ausführen können, und um zu verhindern, dass nicht autorisierte Personen Zugriff auf Bereiche haben, die außerhalb ihrer Zuständigkeiten stehen. Sie sollten sicherstellen, dass Sie dem Compliancedatenadministrator  und den Administratorrollen des Complianceadministrators die richtigen Personen zugewiesen haben, bevor Sie mit der Konfiguration und Implementierung von Compliancelösungen beginnen, die im Lieferumfang enthalten Microsoft 365.  Außerdem müssen Sie der globalen Leserolle benutzer Azure Active Directory, um Daten im Compliance-Manager anzeigen zu können.

Schrittweise Anleitungen zum Konfigurieren von Berechtigungen und Zuweisen von Personen zu Administratorrollen finden Sie unter Permissions in the [Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

## <a name="task-2-know-your-state-of-compliance"></a>Aufgabe 2: Kennen Des Status der Compliance

Es ist schwierig zu wissen, wo Sie hingehen sollen, wenn Sie nicht wissen, wo Sie sich befinden. Die Erfüllung Ihrer Complianceanforderungen umfasst das Verständnis Ihres aktuellen Risikoniveaus und welche Updates in diesen sich ständig ändernden Zeiten erforderlich sein können. Unabhängig davon, ob Ihre Organisation mit den Complianceanforderungen neu ist oder über tiefe Erfahrung mit Standards und Vorschriften verfügt, die Ihre Branche steuern, können Sie die Compliance am besten verbessern, um zu verstehen, wo Ihre Organisation steht.

[Microsoft Compliance Manager](compliance-manager.md) kann Ihnen dabei helfen, die Compliance-Haltung Ihrer Organisation zu verstehen und Bereiche zu markieren, die möglicherweise verbessert werden müssen. Der Compliance-Manager verwendet ein zentrales Dashboard, um eine risikobasierte Bewertung zu berechnen und Ihren Fortschritt bei der Durchführung von Aktionen zu messen, die dazu beitragen, Risiken im Zusammenhang mit Datenschutz und behördlichen Standards zu reduzieren. Sie können compliance Manager auch als Tool verwenden, um alle Risikobewertungen nachverfolgt zu werden. Es bietet Workflowfunktionen, um Ihre Risikobewertungen mithilfe eines zentralen Tools effizient durchzuführen.

Eine schrittweise Anleitung für die ersten Schritte mit Compliance Manager finden Sie unter [Erste Schritte mit Compliance Manager](compliance-manager-setup.md).

>[!IMPORTANT]
>Sicherheit und Compliance sind für die meisten Organisationen eng integriert. Es ist wichtig, dass Ihre Organisation grundlegende Sicherheits-, Bedrohungsschutz- und Identitäts- und Zugriffsverwaltungsbereiche behandelt, um einen detaillierten Schutzansatz für Sicherheit und Compliance zu bieten.
>
>Überprüfen Sie [Microsoft 365 Secure Score](../security/defender/microsoft-secure-score.md) im Microsoft 365 Security Center, und erledigen Sie die in den folgenden Artikeln beschriebenen Aufgaben:
>
> - [Security Roadmap – Die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](../security/office-365-security/security-roadmap.md)
> - [Top 12 Aufgaben für Sicherheitsteams zur Unterstützung der Arbeit von zu Hause aus](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Aufgabe 3: Aktivieren der Überwachung für Ihre Organisation

Nachdem Sie den aktuellen Status Ihrer Organisation ermittelt haben und wer Compliancefunktionen verwalten kann, müssen Sie im nächsten Schritt sicherstellen, dass Sie über die Daten verfügen, um Complianceuntersuchungen durchzuführen und Berichte für Netzwerk- und Benutzeraktivitäten in Ihrer Organisation zu generieren. Das Aktivieren der Überwachung ist auch eine wichtige Voraussetzung für Compliancelösungen, die weiter später in diesem Artikel behandelt werden.

Einblicke aus dem Überwachungsprotokoll sind ein wertvolles Tool, mit dem Sie Ihre Complianceanforderungen an Lösungen anpassen können, mit denen Sie Compliancebereiche verwalten und überwachen können, die verbessert werden müssen. Die Überwachungsprotokollierung muss aktiviert sein, bevor Aktivitäten aufgezeichnet werden und bevor Sie das Überwachungsprotokoll durchsuchen können. Wenn diese Option aktiviert ist, werden Benutzer- und Administratoraktivitäten aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und für 90 Tage und bis zu einem Jahr in Abhängigkeit von der den Benutzern zugewiesenen Lizenz aufbewahrt.

Schrittweise Anweisungen zum Aktivieren der Überwachung finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](turn-audit-log-search-on-or-off.md)

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Aufgabe 4: Erstellen von Richtlinien, um Sie über potenzielle Complianceprobleme zu warnen

Microsoft bietet mehrere integrierte Warnungsrichtlinien, mit denen Der Missbrauch von Administratorberechtigungen, Schadsoftwareaktivitäten, potenzielle externe und interne Bedrohungen sowie Risiken der Informationsverwaltung identifiziert werden können. Diese Richtlinien sind standardmäßig aktiviert, sie müssen jedoch möglicherweise benutzerdefinierte Warnungen konfigurieren, um die für Ihre Organisation spezifischen Complianceanforderungen zu verwalten.

Verwenden Sie Warnungsrichtlinien- und Benachrichtigungsdashboardtools, um benutzerdefinierte Warnungsrichtlinien zu erstellen und die generierten Warnungen anzuzeigen, wenn Benutzer Aktivitäten ausführen, die den Richtlinienbedingungen entsprechen. Einige Beispiele könnten die Verwendung von Warnungsrichtlinien sein, um Benutzer- und Administratoraktivitäten nachverfolgt zu werden, die sich auf Complianceanforderungen, Berechtigungen und Vorfälle mit Datenverlust in Ihrer Organisation ausdingen.

Schrittweise Anleitungen zum Erstellen benutzerdefinierter Warnungsrichtlinien finden Sie unter [Warnungsrichtlinien im Security and Compliance Center](alert-policies.md).

## <a name="task-5-classify-and-protect-sensitive-data"></a>Aufgabe 5: Klassifizieren und Schützen vertraulicher Daten

Im Rahmen ihrer Arbeit müssen Personen in Ihrer Organisation mit anderen Personen innerhalb und außerhalb der Organisation zusammenarbeiten. Dies bedeutet, dass Inhalte nicht mehr durch eine Firewall geschützt sind – sie können zwischen verschiedenen Geräten, Apps und Diensten hin- und herbewegt werden. Dies soll auf sichere und geschützte Weise geschehen, die den geschäftlichen Anforderungen und Compliancerichtlinien Ihrer Organisation entspricht.

[Mit Vertraulichkeitsbezeichnungen](sensitivity-labels.md) können Sie die Daten Ihrer Organisation klassifizieren und schützen und gleichzeitig sicherstellen, dass die Benutzerproduktivität und ihre Zusammenarbeitsfähigkeit nicht beeinträchtigt werden. Verwenden Sie Vertraulichkeitsbezeichnungen, um Verschlüsselung zu erzwingen, und Verwendungseinschränkungen wenden visuelle Markierungen an und schützen Sie Informationen auf Plattformen und Geräten, lokal und in der Cloud.

Schrittweise Anleitungen zum Konfigurieren und Verwenden von Vertraulichkeitsbezeichnungen finden Sie unter [Erste Schritte mit Vertraulichkeitsbezeichnungen](get-started-with-sensitivity-labels.md). Informationen zur Lizenzierung von Vertraulichkeitsbezeichnungen finden Sie [unter Microsoft 365 Lizenzierungsleitfade für & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="task-6-configure-a-retention-policy"></a>Aufgabe 6: Konfigurieren einer Aufbewahrungsrichtlinie

Mit [einer Aufbewahrungsrichtlinie](retention.md) können Sie proaktiv entscheiden, ob Inhalte beibehalten, Inhalte gelöscht oder beides beibehalten werden soll. Sie können den Inhalt am Ende eines bestimmten Aufbewahrungszeitraums beibehalten und dann löschen. Diese Maßnahmen sind möglicherweise erforderlich, um Branchenbestimmungen und internen Richtlinien zu entsprechen und Ihr Risiko im Falle eines Rechtsstreits oder einer Sicherheitsverletzung zu verringern.

Wenn Inhalte einer Aufbewahrungsrichtlinie unterliegen, können Die Benutzer den Inhalt weiterhin bearbeiten und bearbeiten, als würde sich nichts ändern. Der Inhalt wird an seinem ursprünglichen Speicherort beibehalten. Wenn jedoch jemand Inhalte bearbeitet oder löscht, die der Aufbewahrungsrichtlinie unterliegen, wird eine Kopie des ursprünglichen Inhalts an einem sicheren Speicherort gespeichert, an dem er aufbewahrt wird, während die Aufbewahrungsrichtlinie für diesen Inhalt wirksam ist.

Sie können schnell eine Aufbewahrungsrichtlinie für mehrere Speicherorte in Ihrer Microsoft 365-Umgebung wie Exchange-E-Mails, SharePoint-Websites, OneDrive-Konten und Microsoft 365 erstellen. Es gibt keine Beschränkungen für die Anzahl von Postfächern oder Websites, die diese Richtlinie automatisch umfassen kann. Wenn Sie jedoch selektiver werden müssen, können Sie dazu eine Aufbewahrungsrichtlinie für bestimmte Speicherorte konfigurieren und Websites oder Benutzer ein- oder ausschließen.

Schrittweise Anleitungen zum Konfigurieren einer Aufbewahrungsrichtlinie finden Sie unter [Create and configure retention policies](create-retention-policies.md). Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>Aufgabe 7: Konfigurieren vertraulicher Informationen und anstößige Sprachrichtlinien

Der Schutz vertraulicher Informationen sowie das Erkennen und Reagieren auf Belästigungsvorfälle am Arbeitsplatz ist ein wichtiger Bestandteil der Einhaltung interner Richtlinien und Standards. [Die Kommunikationskonformität](communication-compliance-feature-reference.md) in Microsoft 365 hilft, diese Risiken zu minimieren, indem Sie E-Mail- und Kommunikationsmaßnahmen schnell erkennen, erfassen und Microsoft Teams können. Dazu gehören unangemessene Kommunikationen, die Anstößigkeit, Bedrohungen sowie Belästigungen und Kommunikationen enthalten, die vertrauliche Informationen innerhalb und außerhalb Ihrer Organisation freigeben.

Mit einer vordefinierten Richtlinienvorlage für Anstößige Sprache und *Anti-Mobbing* können Sie interne und externe Kommunikation auf Richtlinien übereinstimmungen überprüfen, damit sie von bestimmten Prüfern geprüft werden können. Prüfer können gescannte E-Mails, Microsoft Teams, Yammer- oder Drittanbieterkommunikationen in Ihrer Organisation untersuchen und geeignete Abhilfemaßnahmen ergreifen, um sicherzustellen, dass sie den Standards Ihrer Organisation entsprechen.

Mit der  vordefinierten Vorlage für Richtlinien für vertrauliche Informationen können Sie schnell eine Richtlinie zum Überprüfen von E-Mails und Microsoft Teams-Kommunikationen erstellen, die definierte Typen vertraulicher Informationen oder Schlüsselwörter enthalten, um sicherzustellen, dass wichtige Daten nicht für Personen freigegeben werden, die keinen Zugriff haben sollten. Diese Aktivitäten können eine nicht autorisierte Kommunikation über vertrauliche Projekte oder branchenspezifische Regeln für Insiderhandel oder andere Zusammenarbeitsaktivitäten umfassen.

Schrittweise Anleitungen zum Planen und Konfigurieren der Kommunikationskonformität finden Sie unter [Plan for communication compliance](communication-compliance-plan.md) und Get started with communication [compliance](communication-compliance-configure.md). Informationen zur Lizenzierung von Kommunikationskonformität finden Sie [unter Microsoft 365 Lizenzierungsleitfade für & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance).

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>Aufgabe 8: Sehen Sie, was mit Ihren vertraulichen Elementen geschieht

Vertraulichkeitsbezeichnungen, Typen vertraulicher Informationen, Aufbewahrungsbezeichnungen und Richtlinien sowie trainierbare Klassifizierungen können verwendet werden, um vertrauliche Elemente in Exchange, SharePoint und OneDrive zu klassifizieren und zu beschriften, wie Sie in den vorherigen Aufgaben gesehen haben. Der letzte Schritt ihrer schnellen Aufgabenreise besteht darin, zu sehen, welche Elemente mit bezeichnungen versehen wurden und welche Aktionen Ihre Benutzer für diese vertraulichen Elemente ausführen. [Inhalts-Explorer](data-classification-content-explorer.md) und [Aktivitäts-Explorer](data-classification-activity-explorer.md) bieten diese Sichtbarkeit.

### <a name="content-explorer"></a>Inhaltsexplorer
 Mit dem Inhalts-Explorer können Sie im systemeigenen Format alle Elemente anzeigen, die als vertraulicher Informationstyp klassifiziert wurden oder zu einer bestimmten Klassifizierung durch einen trainierbaren Klassifikator gehören, sowie alle Elemente, auf die Vertraulichkeits- oder Aufbewahrungsbezeichnungen angewendet wurden.

Schrittweise Anleitungen zur Verwendung des Inhalts-Explorers finden Sie unter [Know your data - data classification overview](data-classification-overview.md)und Get started with content [explorer](data-classification-content-explorer.md).

### <a name="activity-explorer"></a>Aktivitäten-Explorer
Der Aktivitäts-Explorer hilft Ihnen zu überwachen, was mit Ihren klassifizierten und mit Bezeichnungen versehenen vertraulichen Elementen geschieht:
- SharePoint
- Exchange
- OneDrive

Es stehen über 30 verschiedene Filter zur Verfügung, einschließlich:

- Zeitraum:
- Aktivitätstyp
- Speicherort
- Benutzer
- Vertraulichkeitsbezeichnung
- Aufbewahrungsbezeichnung
- Dateipfad
- DLP-Richtlinie

Schrittweise Anleitungen zur Verwendung des Aktivitäts-Explorers finden Sie unter [Erste Schritte mit dem Aktivitäts-Explorer](data-classification-activity-explorer.md).

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie nun die Grundlagen für das Compliancemanagement für Ihre Organisation konfiguriert haben, sollten Sie die folgenden Compliancelösungen in Microsoft 365 in Betracht ziehen, um Ihnen zu helfen, vertrauliche Informationen zu schützen und zusätzliche Insiderrisiken zu erkennen und zu reagieren.

### <a name="configure-retention-labels"></a>Aufbewahrungsbezeichnungen konfigurieren

Aufbewahrungsrichtlinien gelten zwar auf Containerebene für Speicherorte wie SharePoint-Websites und [](retention.md#retention-labels) Exchange-Postfächer, aufbewahrungsbezeichnungen ermöglichen jedoch eine spezifischere Ausrichtung ihrer Aufbewahrungs- und Löschrichtlinien. Beispielsweise auf der Dokument- oder E-Mail-Nachrichtenebene, die Endbenutzer zusätzlich zur automatischen Anwendung durch Administratoren manuell anwenden können. Sie können eine Aufbewahrungsbezeichnung auch auf eine Dokumentbibliothek, einen Ordner oder einen Dokumentensatz in SharePoint anwenden, sodass alle an diesem Speicherort gespeicherten Dokumente die Standardaufbewahrungsbezeichnung erben.

Darüber hinaus unterstützen Aufbewahrungsbezeichnungen [die Datensatzverwaltung,](records-management.md) um Inhalte als Datensatz zu kennzeichnen. In diesem Fall legt die Bezeichnung zusätzliche Einschränkungen für die Inhalte fest, die möglicherweise erforderlich sind, um Ihre Organisation bei der Einhaltung gesetzlicher Anforderungen zu unterstützen.

Schrittweise Anleitungen zum Erstellen und Veröffentlichen von Aufbewahrungsbezeichnungen finden Sie in den folgenden Anleitungen:
- [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)
- [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)

Informationen zu den ersten Schritte mit der Datensatzverwaltung finden Sie unter [Erste Schritte mit der Datensatzverwaltung](get-started-with-records-management.md).

### <a name="identify-and-define-sensitive-information-types"></a>Identifizieren und Definieren vertraulicher Informationstypen

Definieren Sie Typen vertraulicher Informationen basierend auf dem Muster, das in Informationen in den Daten Ihrer Organisation enthalten ist. Verwenden [Sie integrierte Typen vertraulicher Informationen,](./sensitive-information-type-entity-definitions.md) um Kreditkartennummern, Bankkontonummern, Reisepassnummern und vieles mehr zu identifizieren und zu schützen. Oder erstellen Sie ihre eigenen [benutzerdefinierten Vertraulichkeitsinformationstypen,](create-a-custom-sensitive-information-type.md) die für Ihre Organisation spezifisch sind.

Schrittweise Anleitungen zum Definieren benutzerdefinierter typen vertraulicher Informationen finden Sie unter [Create a custom sensitive information type in](./create-a-custom-sensitive-information-type.md)the Security & Compliance Center .

### <a name="prevent-data-loss"></a>Verhindern von Datenverlust

Richtlinien zur Verhinderung von Datenverlust [(Data Loss Prevention, DLP)](dlp-learn-about-dlp.md) ermöglichen ihnen das Identifizieren, Überwachen und automatische Schützen vertraulicher Informationen in Microsoft 365 Organisation. Verwenden Sie DLP-Richtlinien, um vertrauliche Elemente Microsoft-Dienste zu identifizieren, die versehentliche Freigabe vertraulicher Elemente zu verhindern und Benutzern zu helfen, richtlinienkonform zu bleiben, ohne ihren Workflow zu unterbrechen.

Für schrittweise Anleitungen zum Konfigurieren von DLP-Richtlinien erstellen, testen und optimieren Sie [eine DLP-Richtlinie.](create-test-tune-dlp-policy.md) Informationen zur Lizenzierung zur Verwaltung von Datenverlusten finden Sie [unter Microsoft 365 Lizenzierungsleitfader für & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

### <a name="detect-and-act-on-insider-risks"></a>Erkennen und Handeln bei Insiderrisiken

Mitarbeiter haben immer mehr Zugriff auf das Erstellen, Verwalten und Freigeben von Daten über ein breites Spektrum von Plattformen und Diensten hinweg. In den meisten Fällen verfügen Organisationen über begrenzte Ressourcen und Tools, um organisationsweite Risiken zu identifizieren und zu mindern und gleichzeitig Complianceanforderungen und Datenschutzstandards für Mitarbeiter zu erfüllen. Diese Risiken können Datendiebstahl durch ausscheidende Mitarbeiter und Datenlecks von Informationen außerhalb Ihrer Organisation durch versehentliche Überschatten oder böswillige Absichten umfassen.

[Das Risikomanagement](insider-risk-management-policies.md) von Insidern in Microsoft 365 verwendet die gesamte Bandbreite an Dienst- und Drittanbieterindikatoren, um riskante Benutzeraktivitäten schnell zu identifizieren, zu verdingen und zu reagieren. Mithilfe von Protokollen von Microsoft 365 und Microsoft Graph können Sie bestimmte Richtlinien definieren, um Risikoindikatoren zu identifizieren und Maßnahmen zur Minderung dieser Risiken zu ergreifen.

Schrittweise Anleitungen zum Planen und Konfigurieren von Insider-Risikomanagementrichtlinien finden Sie unter [Plan for insider risk management](insider-risk-management-plan.md) und Get started with insider risk [management](insider-risk-management-configure.md). Informationen zur Lizenzierung von Insidern im Risikomanagement finden Sie [unter Microsoft 365 Lizenzierungsleitfade für & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management).