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
description: Erfahren Sie mehr über Aufgaben, mit denen Sie schnell mit der Compliance in Microsoft 365 beginnen können.
ms.openlocfilehash: 61a057c3666faae51a012dd9db2d4c63ded0f77a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227259"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Schnelle Aufgaben für die ersten Schritte mit Microsoft 365 Compliance

Wenn Sie noch nicht mit der Microsoft 365 der Compliance begonnen haben und sich fragen, wo Sie beginnen sollten, enthält dieser Artikel Anleitungen zu den Grundlagen und priorisiert wichtige Complianceaufgaben. Dieser Artikel hilft Ihnen bei den ersten Schritten mit der Verwaltung und Überwachung Ihrer Daten, dem Schutz von Informationen und der Minimierung von Insider-Risiken.

Dieser Artikel ist auch hilfreich, wenn Sie herausfinden, wie Sie Risiken am besten verwalten, Ihre Daten schützen und den Vorschriften und Standards einer neu entlegenen Belegschaft entsprechen. Mitarbeiter arbeiten jetzt auf neue Weise zusammen und verbinden sich miteinander, was bedeutet, dass sich Ihre vorhandenen Complianceprozesse und Kontrollen möglicherweise anpassen müssen. Die Identifizierung und Verwaltung dieser neuen Compliancerisiken innerhalb Ihrer Organisation ist entscheidend, um Ihre Daten zu schützen und Bedrohungen und Risiken zu minimieren.

Nachdem Sie diese grundlegenden Complianceaufgaben abgeschlossen haben, sollten Sie erwägen, die Compliance-Abdeckung in Ihrer Organisation zu erweitern, indem Sie zusätzliche Microsoft 365 Compliancelösungen implementieren.

## <a name="task-1-configure-compliance-permissions"></a>Aufgabe 1: Konfigurieren von Complianceberechtigungen

Es ist wichtig zu verwalten, wer in Ihrer Organisation Zugriff auf die Microsoft 365 Compliance Center hat, um Inhalte anzuzeigen und Verwaltungsaufgaben auszuführen. Microsoft 365 stellt administrative Rollen bereit, die spezifisch für die Compliance und die Verwendung der in der Microsoft 365 Compliance Center enthaltenen Tools sind.

Beginnen Sie, indem Sie den Personen in Ihrer Organisation Complianceberechtigungen zuweisen, damit sie diese Aufgaben ausführen können und um zu verhindern, dass nicht autorisierte Personen Zugriff auf Bereiche haben, die außerhalb ihrer Verantwortlichkeiten liegen. Sie sollten sicherstellen, dass Sie dem **Compliancedatenadministrator** und den Administratorrollen des **Complianceadministrators** die richtigen Personen zugewiesen haben, bevor Sie mit der Konfiguration und Implementierung von Compliancelösungen beginnen, die in Microsoft 365 enthalten sind. Außerdem müssen Sie der Rolle Azure Active Directory globalen Lesers Benutzer zuweisen, um Daten im Compliance-Manager anzuzeigen.

Eine schrittweise Anleitung zum Konfigurieren von Berechtigungen und Zuweisen von Personen zu Administratorrollen finden Sie unter ["Berechtigungen" im Security & Compliance Center.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

## <a name="task-2-know-your-state-of-compliance"></a>Aufgabe 2: Kennen Sie Ihren Compliancestatus

Es ist schwierig zu wissen, wohin Sie gehen sollten, wenn Sie nicht wissen, wo Sie sich befinden. Die Erfüllung Ihrer Complianceanforderungen umfasst das Verständnis Ihres aktuellen Risikoniveaus und darüber, welche Updates in diesen sich ständig ändernden Zeiten erforderlich sein können. Unabhängig davon, ob Ihre Organisation noch nicht mit Complianceanforderungen vertraut ist oder über umfassende Erfahrung mit Standards und Vorschriften verfügt, die Ihre Branche steuern, können Sie die Compliance am besten verbessern, wenn Sie wissen, wo Ihre Organisation steht.

[Microsoft Compliance Manager](compliance-manager.md) kann Ihnen dabei helfen, den Compliancestatus Ihrer Organisation zu verstehen und Bereiche hervorzuheben, die möglicherweise verbessert werden müssen. Compliance-Manager verwendet ein zentrales Dashboard, um eine risikobasierte Bewertung zu berechnen und Ihren Fortschritt bei der Durchführung von Maßnahmen zu messen, die dazu beitragen, Risiken im Zusammenhang mit Datenschutz und gesetzlichen Standards zu verringern. Sie können den Compliance-Manager auch als Tool verwenden, um alle Ihre Risikobewertungen nachzuverfolgen. Es bietet Workflowfunktionen, um Ihre Risikobewertungen mithilfe eines zentralen Tools effizient durchzuführen.

Eine schrittweise Anleitung für die ersten Schritte mit Compliance-Manager finden Sie unter ["Erste Schritte mit Compliance-Manager".](compliance-manager-setup.md)

> [!IMPORTANT]
> Sicherheit und Compliance sind für die meisten Organisationen eng integriert. Es ist wichtig, dass Sich Ihre Organisation mit grundlegenden Sicherheits-, Bedrohungsschutz- und Identitäts- und Zugriffsverwaltungsbereichen befasst, um einen umfassenden Ansatz für Sicherheit und Compliance bereitzustellen.
>
> Überprüfen Sie Ihre [Microsoft 365 Sicherheitsbewertung](../security/defender/microsoft-secure-score.md) im Microsoft 365 Security Center, und führen Sie die in den folgenden Artikeln beschriebenen Aufgaben aus:
>
> - [Sicherheits-Roadmap – Die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](../security/office-365-security/security-roadmap.md)
> - [Die 12 wichtigsten Aufgaben für Sicherheitsteams zur Unterstützung der Arbeit von zu Hause aus](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Aufgabe 3: Aktivieren der Überwachung für Ihre Organisation

Nachdem Sie nun den aktuellen Status Ihrer Organisation bestimmt haben und wer Compliancefunktionen verwalten kann, besteht der nächste Schritt darin, sicherzustellen, dass Sie über die Daten verfügen, um Complianceuntersuchungen durchzuführen und Berichte für Netzwerk- und Benutzeraktivitäten in Ihrer Organisation zu generieren. Die Aktivierung der Überwachung ist auch eine wichtige Voraussetzung für Compliancelösungen, die weiter unten in diesem Artikel behandelt werden.

Insights, die vom Überwachungsprotokoll bereitgestellt werden, sind ein wertvolles Tool, um Ihre Complianceanforderungen an Lösungen anzupassen, die Ihnen helfen können, Compliancebereiche zu verwalten und zu überwachen, die verbessert werden müssen. Die Überwachungsprotokollierung muss aktiviert sein, bevor Aktivitäten aufgezeichnet werden und bevor Sie das Überwachungsprotokoll durchsuchen können. Wenn dies aktiviert ist, werden die Aktivitäten von Benutzern und Administratoren aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und 90 Tage lang und bis zu einem Jahr aufbewahrt, je nach den Benutzern zugewiesenen Lizenz.

Schritt-für-Schritt-Anleitungen zum Aktivieren der Überwachung finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](turn-audit-log-search-on-or-off.md)

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Aufgabe 4: Erstellen von Richtlinien, um Sie über potenzielle Complianceprobleme zu informieren

Microsoft bietet mehrere integrierte Warnungsrichtlinien, mit denen Administratorberechtigungsverletzungen, Schadsoftwareaktivitäten, potenzielle externe und interne Bedrohungen sowie Informationsgovernancerisiken identifiziert werden können. Diese Richtlinien sind standardmäßig aktiviert, sie müssen jedoch möglicherweise benutzerdefinierte Warnungen konfigurieren, um compliancespezifische Complianceanforderungen für Ihre Organisation zu verwalten.

Verwenden Sie Warnungsrichtlinien- und Warnungsdashboardtools, um benutzerdefinierte Warnungsrichtlinien zu erstellen und die Warnungen anzuzeigen, die generiert werden, wenn Benutzer Aktivitäten ausführen, die den Richtlinienbedingungen entsprechen. Einige Beispiele könnten die Verwendung von Warnungsrichtlinien sein, um Benutzer- und Administratoraktivitäten nachzuverfolgen, die sich auf Complianceanforderungen, Berechtigungen und Datenverlustvorfälle in Ihrer Organisation auswirken.

For step-by-step guidance to create custom alert policies, see [Alert policies in the security and compliance center](alert-policies.md).

## <a name="task-5-classify-and-protect-sensitive-data"></a>Aufgabe 5: Klassifizieren und Schützen vertraulicher Daten

Im Rahmen ihrer Arbeit müssen Personen in Ihrer Organisation mit anderen Personen innerhalb und außerhalb der Organisation zusammenarbeiten. Dies bedeutet, dass Inhalte nicht mehr durch eine Firewall geschützt sind – sie können zwischen verschiedenen Geräten, Apps und Diensten hin- und herbewegt werden. Dies soll auf sichere und geschützte Weise geschehen, die den geschäftlichen Anforderungen und Compliancerichtlinien Ihrer Organisation entspricht.

[Mit Vertraulichkeitsbezeichnungen](sensitivity-labels.md) können Sie die Daten Ihrer Organisation klassifizieren und schützen und gleichzeitig sicherstellen, dass die Produktivität der Benutzer und ihre Fähigkeit zur Zusammenarbeit nicht beeinträchtigt wird. Verwenden Sie Vertraulichkeitsbezeichnungen, um Verschlüsselungs- und Nutzungseinschränkungen durchzusetzen, wenden Sie visuelle Markierungen an und schützen Sie Informationen plattform- und geräteübergreifend, lokal und in der Cloud.

Eine schrittweise Anleitung zum Konfigurieren und Verwenden von Vertraulichkeitsbezeichnungen finden Sie unter ["Erste Schritte mit Vertraulichkeitsbezeichnungen".](get-started-with-sensitivity-labels.md) Informationen zur Lizenzierung von Vertraulichkeitsbezeichnungen finden Sie [unter Microsoft 365 Lizenzierungsleitfaden für die Sicherheit & Compliance.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

## <a name="task-6-configure-a-retention-policy"></a>Aufgabe 6: Konfigurieren einer Aufbewahrungsrichtlinie

Mithilfe einer [Aufbewahrungsrichtlinie](retention.md) können Sie proaktiv entscheiden, ob Inhalte aufbewahrt, gelöscht oder beides, also aufbewahrt und dann am Ende eines bestimmten Aufbewahrungszeitraums gelöscht werden sollen. Diese Maßnahmen sind möglicherweise erforderlich, um branchenspezifische Vorschriften und interne Richtlinien einzuhalten und Ihr Risiko im Falle von Rechtsstreitigkeiten oder Sicherheitsverletzungen zu verringern.

Wenn Inhalte einer Aufbewahrungsrichtlinie unterliegen, können Benutzer den Inhalt weiterhin bearbeiten und damit arbeiten, als ob sich nichts geändert hätte. Der Inhalt wird an seinem ursprünglichen Speicherort beibehalten. Wenn jedoch jemand Inhalte bearbeitet oder löscht, die der Aufbewahrungsrichtlinie unterliegen, wird eine Kopie des ursprünglichen Inhalts an einem sicheren Speicherort gespeichert, an dem er aufbewahrt wird, während die Aufbewahrungsrichtlinie für diese Inhalte wirksam ist.

Sie können schnell eine Aufbewahrungsrichtlinie für mehrere Speicherorte in Ihrer Microsoft 365 Umgebung einrichten, z. B. Exchange E-Mail, SharePoint Websites, OneDrive Konten und Microsoft 365 Gruppen. Es gibt keine Beschränkungen für die Anzahl der Postfächer oder Websites, die diese Richtlinie automatisch einschließen kann. Wenn Sie jedoch selektiver arbeiten müssen, können Sie dies tun, indem Sie eine Aufbewahrungsrichtlinie für bestimmte Speicherorte konfigurieren und Websites oder Benutzer einschließen oder ausschließen.

Eine schrittweise Anleitung zum Konfigurieren einer Aufbewahrungsrichtlinie finden Sie unter Erstellen und Konfigurieren von [Aufbewahrungsrichtlinien.](create-retention-policies.md) Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>Aufgabe 7: Konfigurieren vertraulicher Informationen und Richtlinien für anstößige Sprachen

Der Schutz vertraulicher Informationen und die Erkennung und Behandlung von Vorfällen bei Belästigung am Arbeitsplatz ist ein wichtiger Bestandteil der Einhaltung interner Richtlinien und Standards. [Die Kommunikationscompliance](communication-compliance-feature-reference.md) in Microsoft 365 trägt dazu bei, diese Risiken zu minimieren, indem es Ihnen hilft, E-Mails und Microsoft Teams Kommunikation schnell zu erkennen, zu erfassen und Korrekturmaßnahmen zu ergreifen. Dazu gehören unangemessene Kommunikationen, die Anstößigkeit, Bedrohungen sowie Belästigungen und Kommunikationen enthalten, die vertrauliche Informationen innerhalb und außerhalb Ihrer Organisation teilen.

Mit einer vordefinierten Vorlage für *anstößige Sprache und Antibelästigungsrichtlinien* können Sie die interne und externe Kommunikation auf Richtlinienübereinstimmungen überprüfen, damit sie von bestimmten Prüfern überprüft werden können. Prüfer können gescannte E-Mails, Microsoft Teams, Yammer oder Drittanbieterkommunikationen in Ihrer Organisation untersuchen und geeignete Korrekturmaßnahmen ergreifen, um sicherzustellen, dass sie den Standards Ihrer Organisation entsprechen.

Die vordefinierte Vorlage für Richtlinien für *vertrauliche Informationen* hilft Ihnen, schnell eine Richtlinie zum Scannen von E-Mails und Microsoft Teams Kommunikationen zu erstellen, die definierte Typen vertraulicher Informationen oder Schlüsselwörter enthalten, um sicherzustellen, dass wichtige Daten nicht für Personen freigegeben werden, die keinen Zugriff haben sollten. Diese Aktivitäten können eine nicht autorisierte Kommunikation über vertrauliche Projekte oder branchenspezifische Regeln für Insider-Geschäfte oder andere geheime Aktivitäten umfassen.

Eine schrittweise Anleitung zum Planen und Konfigurieren der Kommunikationscompliance finden Sie unter ["Planen der Kommunikationscompliance"](communication-compliance-plan.md) und ["Erste Schritte mit der Kommunikationscompliance".](communication-compliance-configure.md) Informationen zur Lizenzierung der Kommunikationscompliance finden Sie [unter Microsoft 365 Lizenzierungsleitfaden für Die Sicherheit & Compliance.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>Aufgabe 8: Sehen Sie sich an, was mit Ihren vertraulichen Elementen geschieht

Vertraulichkeitsbezeichnungen, Typen vertraulicher Informationen, Aufbewahrungsbezeichnungen und Richtlinien sowie trainierbare Klassifizierer können verwendet werden, um vertrauliche Elemente in Exchange, SharePoint und OneDrive zu klassifizieren und zu kennzeichnen, wie Sie in den vorherigen Aufgaben gesehen haben. Der letzte Schritt ihrer schnellen Aufgaben besteht darin, zu sehen, welche Elemente bezeichnet wurden und welche Aktionen Ihre Benutzer für diese vertraulichen Elemente ausführen. [Der Inhalts-Explorer](data-classification-content-explorer.md) und [der Aktivitäten-Explorer](data-classification-activity-explorer.md) bieten diese Sichtbarkeit.

### <a name="content-explorer"></a>Inhaltsexplorer
 Mit dem Inhalts-Explorer können Sie in ihrem systemeigenen Format alle Elemente anzeigen, die als vertraulicher Informationstyp klassifiziert wurden oder zu einer bestimmten Klassifizierung durch einen trainierbaren Klassifizierer gehören, sowie alle Elemente, auf die Vertraulichkeits- oder Aufbewahrungsbezeichnungen angewendet wurden.

Eine schrittweise Anleitung zur Verwendung des Inhalts-Explorers finden Sie unter ["Kennen Sie Ihre Daten – Übersicht über die Datenklassifizierung"](data-classification-overview.md)und ["Erste Schritte mit dem Inhalts-Explorer".](data-classification-content-explorer.md)

### <a name="activity-explorer"></a>Aktivitäten-Explorer
Der Aktivitäts-Explorer hilft Ihnen, zu überwachen, was mit Ihren klassifizierten und bezeichneten vertraulichen Elementen geschieht:
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

Schritt-für-Schritt-Anleitungen zur Verwendung des Aktivitäten-Explorers finden Sie unter [Erste Schritte mit dem Aktivitäten-Explorer.](data-classification-activity-explorer.md)

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie nun die Grundlagen für die Complianceverwaltung für Ihre Organisation konfiguriert haben, sollten Sie die folgenden Compliance-Lösungen in Microsoft 365 in Betracht ziehen, um vertrauliche Informationen zu schützen und zusätzliche Insider-Risiken zu erkennen und darauf zu reagieren.

### <a name="configure-retention-labels"></a>Konfigurieren von Aufbewahrungsbezeichnungen

Während Aufbewahrungsrichtlinien auf Containerebene auf Speicherorte wie SharePoint Websites und Exchange Postfächer angewendet werden, ermöglichen [Aufbewahrungsbezeichnungen](retention.md#retention-labels) eine spezifischere Ausrichtung für Ihre Aufbewahrungs- und Löschrichtlinien. Beispielsweise auf Dokument- oder E-Mail-Nachrichtenebene, die Endbenutzer zusätzlich zur automatischen Anwendung durch Administratoren manuell anwenden können. Sie können eine Aufbewahrungsbezeichnung auch auf eine Dokumentbibliothek, einen Ordner oder eine Dokumentenmappe in SharePoint anwenden, sodass alle an diesem Speicherort gespeicherten Dokumente die Standardaufbewahrungsbezeichnung erben.

Darüber hinaus unterstützen Aufbewahrungsbezeichnungen die [Datensatzverwaltung,](records-management.md) um Inhalte als Datensatz zu markieren. In diesem Fall legt die Bezeichnung zusätzliche Einschränkungen für den Inhalt fest, die möglicherweise erforderlich sind, um Ihre Organisation bei der Einhaltung gesetzlicher Vorschriften zu unterstützen.

Eine schrittweise Anleitung zum Erstellen und Veröffentlichen von Aufbewahrungsbezeichnungen finden Sie in den folgenden Anleitungen:
- [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)
- [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)

Informationen zu den ersten Schritten mit der Datensatzverwaltung finden Sie unter [Erste Schritte mit der Datensatzverwaltung.](get-started-with-records-management.md)

### <a name="identify-and-define-sensitive-information-types"></a>Identifizieren und Definieren vertraulicher Informationstypen

Definieren Sie Typen vertraulicher Informationen basierend auf dem Muster, das in den Informationen in den Daten Ihrer Organisation enthalten ist. Verwenden Sie [integrierte Typen vertraulicher Informationen,](./sensitive-information-type-entity-definitions.md) um Kreditkartennummern, Bankkontonummern, Reisepassnummern und vieles mehr zu identifizieren und zu schützen. Oder erstellen Sie eigene [benutzerdefinierte Vertraulichkeitsinformationstypen,](create-a-custom-sensitive-information-type.md) die für Ihre Organisation spezifisch sind.

Eine schrittweise Anleitung zum Definieren benutzerdefinierter Typen vertraulicher Informationen finden Sie unter [Erstellen eines benutzerdefinierten Vertraulichen Informationstyps im Security & Compliance Center.](./create-a-custom-sensitive-information-type.md)

### <a name="prevent-data-loss"></a>Verhindern von Datenverlust

[Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP)](dlp-learn-about-dlp.md) ermöglichen es Ihnen, vertrauliche Informationen in Ihrer Microsoft 365 Organisation zu identifizieren, zu überwachen und automatisch zu schützen. Verwenden Sie DLP-Richtlinien, um vertrauliche Elemente über Microsoft-Dienste hinweg zu identifizieren, die versehentliche Freigabe vertraulicher Elemente zu verhindern und Benutzern zu zeigen, wie sie konform bleiben, ohne ihren Workflow zu unterbrechen.

Eine schrittweise Anleitung zum Konfigurieren von DLP-Richtlinien finden Sie unter [Erstellen, Testen und Optimieren einer DLP-Richtlinie.](create-test-tune-dlp-policy.md) Informationen zur Verwaltung von Datenverlusten finden Sie unter [Microsoft 365 Lizenzierungsleitfaden für Die Sicherheit & Compliance.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)

### <a name="detect-and-act-on-insider-risks"></a>Erkennen und Reagieren auf Insider-Risiken

Immer mehr Mitarbeiter haben zunehmenden Zugriff auf das Erstellen, Verwalten und Freigeben von Daten über ein breites Spektrum von Plattformen und Diensten hinweg. In den meisten Fällen verfügen Organisationen über begrenzte Ressourcen und Tools, um organisationsweite Risiken zu erkennen und zu mindern und gleichzeitig compliancebezogene Anforderungen und Datenschutzstandards der Mitarbeiter zu erfüllen. Zu diesen Risiken können Datendiebstahl durch ausscheidende Mitarbeiter und Datenlecks von Informationen außerhalb Ihrer Organisation durch versehentliche Überteilung oder böswillige Absichten gehören.

Das [Insider-Risikomanagement](insider-risk-management-policies.md) in Microsoft 365 nutzt die gesamte Bandbreite von Service- und Drittanbieterindikatoren, um riskante Benutzeraktivitäten schnell zu identifizieren, zu selektieren und zu bearbeiten. Mithilfe von Protokollen aus Microsoft 365 und Microsoft Graph können Sie mithilfe des Insider-Risikomanagements bestimmte Richtlinien definieren, um Risikoindikatoren zu identifizieren und Maßnahmen zur Minderung dieser Risiken zu ergreifen.

Eine schrittweise Anleitung zum Planen und Konfigurieren von Richtlinien für das Insider-Risikomanagement finden Sie unter ["Planen des Insider-Risikomanagements"](insider-risk-management-plan.md) und ["Erste Schritte mit dem Insider-Risikomanagement".](insider-risk-management-configure.md) Informationen zur Lizenzierung des Insider-Risikomanagements finden Sie [unter Microsoft 365 Lizenzierungsleitfaden für Die Sicherheit & Compliance.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)