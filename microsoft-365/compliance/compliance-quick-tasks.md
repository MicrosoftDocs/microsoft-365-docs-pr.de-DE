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
description: Erfahren Sie mehr über Aufgaben, mit deren Hilfe Sie schnell mit der Compliance in Microsoft 365 beginnen können.
ms.openlocfilehash: 36b6e2bd0d0339241748499826edf061a7259317
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928629"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Schnelle Aufgaben für die ersten Schritte mit Microsoft 365 Compliance

Wenn Sie noch nicht mit Der Compliance von Microsoft 365 beginnen und sich fragen, wo Sie beginnen sollten, bietet dieser Artikel Anleitungen zu den Grundlagen und priorisiert wichtige Complianceaufgaben. Dieser Artikel hilft Ihnen, schnell mit der Verwaltung und Überwachung Ihrer Daten, dem Schutz von Informationen und der Minimierung von Insiderrisiken zu beginnen.

Dieser Artikel ist auch hilfreich, wenn Sie herausfinden, wie Sie Risiken am besten verwalten, Ihre Daten schützen und die Vorschriften und Standards mit einer neu entfernten Belegschaft einhalten können. Mitarbeiter arbeiten jetzt auf neue Weise zusammen und verbinden sich miteinander, was bedeutet, dass ihre vorhandenen Complianceprozesse und -kontrollen möglicherweise angepasst werden müssen. Das Identifizieren und Verwalten dieser neuen Compliancerisiken innerhalb Ihrer Organisation ist entscheidend, um Ihre Daten zu schützen und Bedrohungen und Risiken zu minimieren.

Nachdem Sie diese grundlegenden Complianceaufgaben abgeschlossen haben, sollten Sie die Complianceabdeckung in Ihrer Organisation erweitern, indem Sie zusätzliche Microsoft 365-Compliancelösungen implementieren.

## <a name="task-1-configure-compliance-permissions"></a>Aufgabe 1: Konfigurieren von Kompatibilitätsberechtigungen

Es ist wichtig zu verwalten, wer in Ihrer Organisation Zugriff auf das Microsoft 365 Compliance Center hat, um Inhalte anzuzeigen und Verwaltungsaufgaben auszuführen. Microsoft 365 bietet administratorspezifische Rollen für Compliance und für die Verwendung der Tools, die im Microsoft 365 Compliance Center enthalten sind.

Beginnen Sie, indem Sie den Personen in Ihrer Organisation Complianceberechtigungen zuweisen, damit sie diese Aufgaben ausführen können, und um zu verhindern, dass nicht autorisierte Personen Zugriff auf Bereiche außerhalb ihrer Zuständigkeiten haben. Sie sollten sicherstellen, dass Sie die richtigen Personen  dem Compliancedatenadministrator  und den Administratorrollen des Complianceadministrators zugewiesen haben, bevor Sie mit der Konfiguration und Implementierung von Compliancelösungen beginnen, die in Microsoft 365 enthalten sind. Außerdem müssen Sie Benutzer der globalen Azure Active Directory-Leserolle zuweisen, um Daten im Compliance-Manager anzeigen zu können.

Schrittweise Anleitungen zum Konfigurieren von Berechtigungen und zum Zuweisen von Personen zu Administratorrollen finden Sie unter "Berechtigungen" [im Security & Compliance Center.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

## <a name="task-2-know-your-state-of-compliance"></a>Aufgabe 2: Kennen Des Zustands der Compliance

Es ist schwierig zu wissen, wohin Sie gehen sollten, wenn Sie nicht wissen, wo Sie sich befinden. Wenn Sie Ihre Complianceanforderungen erfüllen, müssen Sie ihr aktuelles Risikoniveau verstehen und wissen, welche Updates in diesen sich ständig ändernden Zeiten erforderlich sein können. Unabhängig davon, ob Ihre Organisation mit den Complianceanforderungen neu ist oder über tiefe Erfahrung mit Standards und Vorschriften verfügt, die Ihre Branche steuern, ist das beste, was Sie tun können, um die Compliance zu verbessern, ist zu verstehen, wo Ihre Organisation steht.

[Microsoft Compliance Manager](compliance-manager.md) kann Ihnen dabei helfen, die Compliance ihres Unternehmens zu verstehen und Bereiche zu hervorheben, die möglicherweise verbessert werden müssen. Der Compliance-Manager verwendet ein zentrales Dashboard, um eine risikobasierte Bewertung zu berechnen und ihren Fortschritt bei der Durchführung von Aktionen zu messen, mit deren Hilfe Risiken im Zusammenhang mit Datenschutz und behördlichen Standards reduziert werden. Sie können den Compliance Manager auch als Tool verwenden, um alle Risikobewertungen nachverfolgt zu werden. Es bietet Workflowfunktionen, mit deren Hilfe Sie Ihre Risikobewertungen mithilfe eines gemeinsamen Tools effizient durchführen können.

Eine schrittweise Anleitung für die ersten Schritte mit dem Compliance-Manager finden Sie unter ["Erste Schritte mit Compliance-Manager".](compliance-manager-setup.md)

>[!IMPORTANT]
>Sicherheit und Compliance sind für die meisten Organisationen eng integriert. Es ist wichtig, dass sich Ihre Organisation mit grundlegenden Sicherheits-, Bedrohungs- und Identitäts- und Zugriffsverwaltungsbereichen befasst, um einen detaillierten Verteidigungsansatz für Sicherheit und Compliance zu bieten.
>
>Überprüfen Sie [Ihre Microsoft 365-Sicherheitsüberprüfung](../security/mtp/microsoft-secure-score.md) im Microsoft 365 Security Center, und erledigen Sie die in den folgenden Artikeln beschriebenen Aufgaben:
>
> - [Sicherheitsplan – Die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](../security/office-365-security/security-roadmap.md)
> - [Die 12 Am besten 12 Aufgaben für Sicherheitsteams, die die Arbeit von zu Hause aus unterstützen](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Aufgabe 3: Aktivieren der Überwachung für Ihre Organisation

Nachdem Sie den aktuellen Status Ihrer Organisation bestimmt haben und wer Compliancefunktionen verwalten kann, besteht der nächste Schritt im Sicherstellen, dass Sie über die Daten verfügen, um Complianceuntersuchungen durchzuführen und Berichte für Netzwerk- und Benutzeraktivitäten in Ihrer Organisation zu generieren. Das Aktivieren der Überwachung ist auch eine wichtige Voraussetzung für Compliancelösungen, die weiter später in diesem Artikel behandelt werden.

Die vom Überwachungsprotokoll bereitgestellten Erkenntnisse sind ein wertvolles Tool, um Ihre Complianceanforderungen an Lösungen anzupassen, mit denen Sie Compliancebereiche, die Verbesserung erfordern, verwalten und überwachen können. Die Überwachungsprotokollierung muss aktiviert sein, bevor Aktivitäten aufgezeichnet werden und bevor Sie das Überwachungsprotokoll durchsuchen können. Wenn diese Option aktiviert ist, werden Benutzer- und Administratoraktivitäten aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und 90 Tage lang und je nach den Benutzern zugewiesenen Lizenzen bis zu einem Jahr aufbewahrt.

Schrittweise Anweisungen zum Aktivieren der Überwachung finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](turn-audit-log-search-on-or-off.md)

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Aufgabe 4: Erstellen von Richtlinien, um Sie über potenzielle Kompatibilitätsprobleme zu warnen

Microsoft stellt mehrere integrierte Warnungsrichtlinien zur Verfügung, mit denen Administratorberechtigungen, Schadsoftwareaktivitäten, potenzielle externe und interne Bedrohungen sowie Risiken der Informationsverwaltung identifiziert werden können. Diese Richtlinien sind standardmäßig aktiviert, aber Sie müssen möglicherweise benutzerdefinierte Warnungen konfigurieren, um die für Ihre Organisation spezifischen Complianceanforderungen zu verwalten.

Verwenden Sie Warnungsrichtlinien- und Warnungsdashboardtools, um benutzerdefinierte Warnungsrichtlinien zu erstellen und die Warnungen anzuzeigen, die generiert werden, wenn Benutzer Aktivitäten ausführen, die den Richtlinienbedingungen entsprechen. Einige Beispiele könnten die Verwendung von Warnungsrichtlinien sein, um Benutzer- und Administratoraktivitäten nachverfolgt zu werden, die sich auf Complianceanforderungen, Berechtigungen und Datenverlustvorfälle in Ihrer Organisation ausdingen.

Eine schrittweise Anleitung zum Erstellen benutzerdefinierter Warnungsrichtlinien finden Sie unter Warnungsrichtlinien im [Security and Compliance Center.](alert-policies.md)

## <a name="task-5-classify-and-protect-sensitive-data"></a>Aufgabe 5: Klassifizieren und Schützen vertraulicher Daten

Im Rahmen ihrer Arbeit müssen Personen in Ihrer Organisation mit anderen Personen innerhalb und außerhalb der Organisation zusammenarbeiten. Dies bedeutet, dass Inhalte nicht mehr durch eine Firewall geschützt sind – sie können zwischen verschiedenen Geräten, Apps und Diensten hin- und herbewegt werden. Dies soll auf sichere und geschützte Weise geschehen, die den geschäftlichen Anforderungen und Compliancerichtlinien Ihrer Organisation entspricht.

[Mit Vertraulichkeitsbezeichnungen](sensitivity-labels.md) können Sie die Daten Ihrer Organisation klassifizieren und schützen und gleichzeitig sicherstellen, dass die Produktivität der Benutzer und ihre Fähigkeit zur Zusammenarbeit nicht beeinträchtigt werden. Verwenden Sie Vertraulichkeitsbezeichnungen, um Verschlüsselung und Verwendungseinschränkungen zu erzwingen und visuelle Markierungen anzuwenden und Informationen plattform- und geräteübergreifend, lokal und in der Cloud zu schützen.

Eine schrittweise Anleitung zum Konfigurieren und Verwenden von Vertraulichkeitsbezeichnungen finden Sie unter ["Erste Schritte mit Vertraulichkeitsbezeichnungen".](get-started-with-sensitivity-labels.md) Informationen zur Lizenzierung von Vertraulichkeitsbezeichnungen finden Sie unter [Microsoft 365-Lizenzierungsanleitungen für & Compliance.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

## <a name="task-6-configure-a-retention-policy"></a>Aufgabe 6: Konfigurieren einer Aufbewahrungsrichtlinie

Mit [einer Aufbewahrungsrichtlinie](retention.md) können Sie proaktiv entscheiden, ob Inhalte beibehalten, gelöscht oder beides, also am Ende eines bestimmten Aufbewahrungszeitraums, beibehalten und dann gelöscht werden. Diese Maßnahmen können erforderlich sein, um brancheninterne Vorschriften und interne Richtlinien einzuhalten und das Risiko im Falle von Rechtsstreitigkeiten oder Sicherheitsverletzungen zu verringern.

Wenn Inhalte einer Aufbewahrungsrichtlinie unterliegen, können Benutzer den Inhalt weiterhin bearbeiten und bearbeiten, als würde sich nichts ändern. Der Inhalt wird an seinem ursprünglichen Speicherort aufbewahrt. Wenn jedoch jemand Inhalte bearbeitet oder löscht, die der Aufbewahrungsrichtlinie unterliegen, wird eine Kopie des ursprünglichen Inhalts an einem sicheren Ort gespeichert, an dem er aufbewahrt wird, während die Aufbewahrungsrichtlinie für diese Inhalte gilt.

Sie können schnell eine Aufbewahrungsrichtlinie für mehrere Speicherorte in Ihrer Microsoft 365-Umgebung, z. B. Exchange-E-Mail, SharePoint-Websites, #A0 und Microsoft 365-Gruppen, erstellen. Es gibt keine Beschränkungen für die Anzahl von Postfächern oder Websites, die diese Richtlinie automatisch umfassen kann. Wenn Sie jedoch selektiver vorgehen müssen, können Sie dazu eine Aufbewahrungsrichtlinie für bestimmte Speicherorte konfigurieren und Websites oder Benutzer ein- oder ausschließen.

Eine schrittweise Anleitung zum Konfigurieren einer Aufbewahrungsrichtlinie finden Sie unter "Erstellen und [Konfigurieren von Aufbewahrungsrichtlinien".](create-retention-policies.md) Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>Aufgabe 7: Konfigurieren vertraulicher Informationen und Richtlinien für anstößige Sprache

Der Schutz vertraulicher Informationen sowie das Erkennen und Reagieren auf Belästigungsvorfälle am Arbeitsplatz ist ein wichtiger Bestandteil der Einhaltung interner Richtlinien und Standards. [Die](communication-compliance-feature-reference.md) Kommunikationskonformität in Microsoft 365 trägt dazu bei, diese Risiken zu minimieren, indem Sie E-Mail- und Microsoft Teams-Kommunikationen schnell erkennen, erfassen und Abhilfemaßnahmen ergreifen können. Dazu gehören unangemessene Kommunikationen mit Anstößigkeit, Bedrohungen sowie Belästigung und Kommunikation, die vertrauliche Informationen innerhalb und außerhalb Ihrer Organisation gemeinsam nutzen.

Eine vordefinierte Richtlinienvorlage für anstößige Sprache und *Antibelästigung* ermöglicht es Ihnen, die interne und externe Kommunikation auf Richtlinien übereinstimmungen zu überprüfen, damit sie von bestimmten Prüfern überprüft werden können. Prüfer können gescannte E-Mails, Microsoft Teams, Yammer oder Drittanbieterkommunikationen in Ihrer Organisation untersuchen und geeignete Abhilfemaßnahmen ergreifen, um sicherzustellen, dass sie den Standards Ihrer Organisation entsprechen.

Mit der  vordefinierten Richtlinienvorlage für vertrauliche Informationen können Sie schnell eine Richtlinie zum Überprüfen von E-Mails und Microsoft Teams-Kommunikationen erstellen, die definierte Typen vertraulicher Informationen oder Schlüsselwörter enthalten, um sicherzustellen, dass wichtige Daten nicht für Personen freigegeben werden, die keinen Zugriff haben sollen. Diese Aktivitäten können eine nicht autorisierte Kommunikation über vertrauliche Projekte oder branchenspezifische Regeln für Insiderhandel oder andere Kolumnionsaktivitäten umfassen.

Eine schrittweise Anleitung zum Planen und Konfigurieren der Kommunikationskonformität finden Sie unter ["Planen](communication-compliance-plan.md) der Kommunikationskonformität" und "Erste Schritte mit der [Kommunikationskonformität".](communication-compliance-configure.md) Informationen zur Lizenzierung der Kommunikationskonformität finden Sie unter [Microsoft 365-Lizenzierungsleitfas für](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)& Compliance.

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>Aufgabe 8: Sehen Sie, was mit Ihren vertraulichen Elementen geschieht

Vertraulichkeitsbezeichnungen, Typen vertraulicher Informationen, Aufbewahrungsbezeichnungen und Richtlinien sowie trainierbare Klassifizierungen können verwendet werden, um vertrauliche Elemente in Exchange, SharePoint und OneDrive zu klassifizieren und zu beschriften, wie Sie es in den vorherigen Aufgaben gesehen haben. Der letzte Schritt ihrer schnellen Aufgabenaufgabe besteht darin, zu sehen, welche Elemente mit Bezeichnungen versehen wurden und welche Aktionen Ihre Benutzer für diese vertraulichen Elemente ausführen. [Inhalts-Explorer](data-classification-content-explorer.md) und [Aktivitäts-Explorer](data-classification-activity-explorer.md) bieten diese Sichtbarkeit.

### <a name="content-explorer"></a>Inhalts-Explorer
 Mit dem Inhalts-Explorer können Sie in ihrem systemeigenen Format alle Elemente anzeigen, die als vertraulicher Informationstyp klassifiziert wurden oder zu einer bestimmten Klassifizierung durch einen trainierbaren Klassifikator gehören, sowie alle Elemente, auf die Vertraulichkeits- oder Aufbewahrungsbezeichnungen angewendet wurden.

Schritt-für-Schritt-Anleitungen zur Verwendung [](data-classification-overview.md)des Inhalts-Explorers finden Sie unter "Ihre Daten kennen – Übersicht über die Datenklassifizierung" und "Erste Schritte mit dem [Inhalts-Explorer".](data-classification-content-explorer.md)

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

Schrittweise Anleitungen zur Verwendung des Aktivitäts-Explorers finden Sie unter ["Erste Schritte mit dem Aktivitäts-Explorer".](data-classification-activity-explorer.md)

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie nun die Grundlagen für die Verwaltung der Richtlinienkonformität für Ihre Organisation konfiguriert haben, sollten Sie die folgenden Compliancelösungen in Microsoft 365 in Betracht ziehen, die Ihnen dabei helfen, vertrauliche Informationen zu schützen und zusätzliche Insiderrisiken zu erkennen und zu reagieren.

### <a name="configure-retention-labels"></a>Aufbewahrungsbezeichnungen konfigurieren

Aufbewahrungsrichtlinien gelten zwar auf Containerebene für Speicherorte wie [](retention.md#retention-labels) SharePoint-Websites und Exchange-Postfächer, Aufbewahrungsbezeichnungen ermöglichen jedoch eine spezifischere Ausrichtung für Ihre Aufbewahrungs- und Löschrichtlinien. Beispielsweise auf Dokument- oder E-Mail-Nachrichtenebene, die Endbenutzer zusätzlich zur automatischen Anwendung durch Administratoren manuell anwenden können. Sie können eine Aufbewahrungsbezeichnung auch auf eine Dokumentbibliothek, einen Ordner oder eine Dokumentenmappe in SharePoint anwenden, sodass alle an diesem Speicherort gespeicherten Dokumente die Standardaufbewahrungsbezeichnung erben.

Darüber hinaus unterstützen Aufbewahrungsbezeichnungen [die Datensatzverwaltung,](records-management.md) um Inhalte als Datensatz zu markieren. In diesem Fall legt die Bezeichnung zusätzliche Einschränkungen für die Inhalte fest, die möglicherweise erforderlich sind, um Ihrer Organisation bei der Einhaltung gesetzlicher Vorschriften zu helfen.

Eine schrittweise Anleitung zum Erstellen und Veröffentlichen von Aufbewahrungsbezeichnungen finden Sie in den folgenden Anleitungen:
- [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)
- [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)

Informationen zu den ersten Schritte mit der Datensatzverwaltung finden Sie unter ["Erste Schritte mit der Datensatzverwaltung".](get-started-with-records-management.md)

### <a name="identify-and-define-sensitive-information-types"></a>Identifizieren und Definieren vertraulicher Informationstypen

Definieren Sie typen vertraulicher Informationen basierend auf dem Muster, das in den Informationen in den Daten Ihrer Organisation enthalten ist. Verwenden [Sie integrierte Typen vertraulicher](what-the-sensitive-information-types-look-for.md) Informationen, um Kreditkartennummern, Bankkontonummern, Reisepassnummern und vieles mehr zu identifizieren und zu schützen. Oder erstellen Sie ihre eigenen [benutzerdefinierten Vertraulichkeitsinformationstypen,](create-a-custom-sensitive-information-type.md) die für Ihre Organisation spezifisch sind.

Eine schrittweise Anleitung zum Definieren benutzerdefinierter Typen vertraulicher Informationen finden Sie unter Erstellen eines benutzerdefinierten typs für vertrauliche Informationen im [Security & Compliance Center.](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type)

### <a name="prevent-data-loss"></a>Verhindern von Datenverlust

[Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP)](data-loss-prevention-policies.md) ermöglichen Es Ihnen, vertrauliche Informationen in Ihrer Microsoft 365-Organisation zu identifizieren, zu überwachen und automatisch zu schützen. Verwenden Sie DLP-Richtlinien, um vertrauliche Elemente in allen Microsoft-Diensten zu identifizieren, die versehentliche Freigabe vertraulicher Elemente zu verhindern und Benutzern zu helfen, die Richtlinien zu erfüllen, ohne ihren Workflow zu unterbrechen.

Schrittweise Anleitung zum Konfigurieren von DLP-Richtlinien, Erstellen, Testen und Optimieren [einer DLP-Richtlinie.](create-test-tune-dlp-policy.md) Lizenzierungsinformationen zur Verwaltung von Datenverlusten finden Sie unter Microsoft 365-Lizenzierungsanleitungen für & [Compliance.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)

### <a name="detect-and-act-on-insider-risks"></a>Erkennen und Handeln auf Insiderrisiken

Mitarbeiter haben immer mehr Zugriff auf das Erstellen, Verwalten und Freigeben von Daten über ein breites Spektrum von Plattformen und Diensten hinweg. In den meisten Fällen verfügen Organisationen über begrenzte Ressourcen und Tools, um organisationsweite Risiken zu identifizieren und zu mindern und gleichzeitig die Complianceanforderungen und Datenschutzstandards der Mitarbeiter zu erfüllen. Zu diesen Risiken können Datendiebstahl durch ausscheidende Mitarbeiter und Datenlecks von Informationen außerhalb Ihrer Organisation durch versehentliche Überschatten oder böswillige Absichten gehören.

[Das Risikomanagement](insider-risk-management-policies.md) von Insidern in Microsoft 365 verwendet die gesamte Bandbreite des Diensts und Drittanbieterindikatoren, um Ihnen zu helfen, riskante Benutzeraktivitäten schnell zu identifizieren, zu seigen und zu reagieren. Mithilfe von Protokollen von Microsoft 365 und Microsoft Graph können Sie mit dem Insiderrisikomanagement bestimmte Richtlinien definieren, um Risikoindikatoren zu identifizieren und Maßnahmen zur Minderung dieser Risiken zu ergreifen.

Schrittweise Anleitungen zum Planen und Konfigurieren von Richtlinien für das Insider-Risikomanagement finden Sie unter ["Planen](insider-risk-management-plan.md) des Insider-Risikomanagements" und "Erste Schritte mit dem [Insider-Risikomanagement".](insider-risk-management-configure.md) Informationen zur Lizenzierung des Insider-Risikomanagements finden Sie unter [Microsoft 365-Lizenzierungsanleitungen für](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)& Compliance.
