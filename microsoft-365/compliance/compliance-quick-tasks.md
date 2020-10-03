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
description: Erfahren Sie mehr über Aufgaben, die Ihnen helfen, die Compliance in Microsoft 365 schnell zu beginnen.
ms.openlocfilehash: 98526104d2ced7b86315b24bd2843701047a097c
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341181"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Schnelle Aufgaben für die ersten Schritte mit Microsoft 365 Compliance

Wenn Sie neu bei der Microsoft 365-Konformität sind und sich Fragen, wo Sie beginnen sollten, enthält dieser Artikel Anleitungen zu den Grundlagen und priorisiert wichtige Compliance-Aufgaben. In diesem Artikel erfahren Sie, wie Sie schnell mit der Verwaltung und Überwachung Ihrer Daten beginnen, Informationen schützen und Insider Risiken minimieren können.

Dieser Artikel ist auch hilfreich, wenn Sie herausfinden möchten, wie Sie Risiken am besten verwalten, Ihre Daten schützen und mit den Vorschriften und Standards für neue Remotemitarbeiter konform bleiben. Die Mitarbeiter arbeiten nun auf neue Weise zusammen und verbinden sich miteinander, was bedeutet, dass Ihre vorhandenen Compliance-Prozesse und-Kontrollen sich möglicherweise anpassen müssen. Das identifizieren und Verwalten dieser neuen Compliance-Risiken in Ihrer Organisation ist wichtig, um Ihre Daten zu schützen und Bedrohungen und Risiken zu minimieren.

Nachdem Sie diese grundlegenden Kompatibilitäts Aufgaben abgeschlossen haben, sollten Sie den Richtlinien Schutz in Ihrer Organisation erweitern, indem Sie zusätzliche Microsoft 365-Kompatibilitätslösungen implementieren.

## <a name="task-1-configure-compliance-permissions"></a>Aufgabe 1: Konfigurieren der Konformitäts Berechtigungen

Es ist wichtig, zu verwalten, wer in Ihrer Organisation über Zugriff auf das Microsoft 365 Compliance Center verfügt, um Inhalte anzuzeigen und Verwaltungsaufgaben auszuführen. Microsoft 365 bietet administrative Rollen, die speziell für die Compliance und für die Verwendung der im Microsoft 365 Compliance Center enthaltenen Tools verwendet werden.

Beginnen Sie mit dem Zuweisen von Konformitäts Berechtigungen für die Personen in Ihrer Organisation, damit diese diese Aufgaben ausführen und verhindern können, dass nicht autorisierte Personen Zugriff auf Bereiche außerhalb ihrer Aufgaben haben. Sie sollten sicherstellen, dass Sie die richtigen Personen dem **Compliance Data Administrator** und den Administratorrollen für den **Compliance Administrator** zugewiesen haben, bevor Sie mit der Konfiguration und Implementierung von Compliance-Lösungen in Microsoft 365 beginnen. Sie müssen auch Benutzer der Azure Active Directory globalen Leserrolle zuweisen, um Daten im Compliance-Manager anzuzeigen.

Eine Schritt-für-Schritt-Anleitung zum Konfigurieren von Berechtigungen und Zuweisen von Personen zu Administratorrollen finden Sie unter [Permissions in the Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

## <a name="task-2-know-your-state-of-compliance"></a>Aufgabe 2: kennen Ihres Konformitätszustands

Es ist schwierig zu wissen, wohin Sie wechseln müssen, wenn Sie nicht wissen, wo Sie sich befinden. Die Erfüllung der Compliance-Anforderungen umfasst das Verständnis ihres aktuellen Risikograds und die erforderlichen Aktualisierungen für diese immer ändernden Zeiten. Unabhängig davon, ob Ihre Organisation für Compliance-Anforderungen neu ist oder über umfassende Erfahrung mit Standards und Vorschriften verfügt, die Ihre Branche steuern, ist es das beste, was Sie zur Verbesserung der Compliance tun können, um zu verstehen, wo Ihre Organisation steht.

[Microsoft Compliance Manager](compliance-manager.md) kann Ihnen helfen, die Compliance-Haltung ihrer Organisation zu verstehen und Bereiche hervorzuheben, die möglicherweise Verbesserungen erforderlich sind. Compliance-Manager verwendet ein zentralisiertes Dashboard, um eine risikobasierte Bewertung zu berechnen, und misst Ihren Fortschritt bei der Durchführung von Aktionen, die zur Verringerung von Risiken hinsichtlich des Datenschutzes und der regulatorischen Standards beitragen. Sie können auch den Compliance-Manager als Tool verwenden, um alle ihre Risikobewertungen nachzuverfolgen. Es bietet Workflowfunktionen, die Sie bei der effizienten Durchführung ihrer Risikobewertungen mithilfe eines allgemeinen Tools unterstützen.

Eine Schritt-für-Schritt-Anleitung für die ersten Schritte mit dem Compliance-Manager finden Sie unter [Erste Schritte mit Compliance-Manager](compliance-manager-setup.md).

>[!IMPORTANT]
>Sicherheit und Compliance sind für die meisten Organisationen eng integriert. Es ist wichtig, dass Ihre Organisation grundlegende Sicherheits-, Bedrohungsschutz-und Identitäts-und Zugriffs Verwaltungsbereiche anspricht, um eine umfassende Verteidigungsstrategie für Sicherheit und Compliance zu bieten.
>
>Überprüfen Sie Ihre [Microsoft 365 Secure Score](../security/mtp/microsoft-secure-score.md) im Microsoft 365 Security Center, und führen Sie die in den folgenden Artikeln beschriebenen Aufgaben aus:
>
> - [Security Roadmap – die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](../security/office-365-security/security-roadmap.md)
> - [Die 12 wichtigsten Aufgaben für Sicherheitsteams zur Unterstützung der Arbeit von zu Hause aus](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Aufgabe 3: Aktivieren der Überwachung für Ihre Organisation

Nachdem Sie den aktuellen Status Ihrer Organisation festgelegt haben und die Compliance-Funktionen verwalten können, müssen Sie im nächsten Schritt sicherstellen, dass Sie über die Daten verfügen, um Compliance-Untersuchungen durchzuführen und Berichte für Netzwerk-und Benutzeraktivitäten in Ihrer Organisation zu generieren. Das Aktivieren der Überwachung ist auch eine wichtige Voraussetzung für Compliance-Lösungen, die weiter unten in diesem Artikel behandelt werden.

Die im Überwachungsprotokoll bereitgestellten Einblicke sind ein nützliches Tool, um Ihre Compliance-Anforderungen mit Lösungen abzugleichen, die Sie beim Verwalten und Überwachen von verbesserungsbedürftigen Compliance-Bereichen unterstützen können. Die Überwachungsprotokollierung muss aktiviert werden, bevor Aktivitäten aufgezeichnet werden und bevor Sie das Überwachungsprotokoll durchsuchen können. Wenn diese Option aktiviert ist, werden Benutzer-und Administratoraktivitäten in Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und für 90 Tage und bis zu einem Jahr in Abhängigkeit von der Lizenz, die Benutzern zugewiesen ist, aufbewahrt.

Eine Schritt-für-Schritt-Anleitung zum Aktivieren der Überwachung finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](turn-audit-log-search-on-or-off.md).

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Aufgabe 4: Erstellen von Richtlinien, um Sie über mögliche Kompatibilitätsprobleme zu informieren

Microsoft stellt verschiedene integrierte Warnungsrichtlinien zur Verfügung, mit denen Administrator Berechtigungs Missbrauch, malwareaktivität, potenzielle externe und interne Bedrohungen sowie Risiken der Informationssteuerung identifiziert werden können. Diese Richtlinien sind standardmäßig aktiviert, aber Sie müssen möglicherweise benutzerdefinierte Warnungen konfigurieren, um die Compliance-Anforderungen Ihrer Organisation zu verwalten.

Verwenden Sie Alert Policy und Alert Dashboard Tools, um benutzerdefinierte Warnungsrichtlinien zu erstellen und die Warnungen anzuzeigen, die generiert werden, wenn Benutzeraktivitäten ausführen, die den Richtlinienbedingungen entsprechen. Beispiele hierfür sind beispielsweise die Verwendung von Warnungsrichtlinien zum Nachverfolgen von Benutzer-und Administratoraktivitäten, die sich auf Compliance-Anforderungen, Berechtigungen und Datenverlust Vorfälle in Ihrer Organisation auswirken.

Eine Schritt-für-Schritt-Anleitung zum Erstellen benutzerdefinierter Warnungsrichtlinien finden Sie unter [Warnungsrichtlinien im Security and Compliance Center](alert-policies.md).

## <a name="task-5-configure-just-in-time-access-for-your-administrators"></a>Aufgabe 5: Just-in-Time-Zugriff für Ihre Administratoren konfigurieren

Der Zugriff durch einige Benutzer auf vertrauliche Informationen oder wichtige Netzwerkkonfigurationseinstellungen ist ein potenzieller Weg für gefährdete Konten oder für interne Bedrohungen. Die [Verwaltung privilegierter Zugriffsrechte](privileged-access-management-overview.md) schützt Ihre Organisation vor Verstößen und hilft bei der Einhaltung bewährter Methoden, indem der ständige Zugriff auf vertrauliche Daten oder der Zugriff auf wichtige Konfigurationseinstellungen eingeschränkt wird. Anstelle von Administratoren, die über ständigen Zugriff verfügen, werden just-in-Time-Zugriffsregeln für Aufgaben implementiert, die erweiterte Berechtigungen benötigen. Durch die Aktivierung der privilegierten Zugriffsverwaltung in Microsoft 365 kann Ihre Organisation mit NULL stehenden rechten arbeiten und eine Verteidigungsstufe gegenständige administrative Zugriffs Sicherheitsrisiken bieten.

Eine Schritt-für-Schritt-Anleitung zum Konfigurieren der privilegierten Zugriffsverwaltung finden Sie unter [Erste Schritte mit privilegierter Zugriffsverwaltung](privileged-access-management-configuration.md). Informationen zur Lizenzierung von privilegierten Zugriffs Verwaltungen finden Sie unter [Microsoft 365 Licensing Guidance for Security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#privileged-access-management-in-office-365).

## <a name="task-6-classify-and-protect-sensitive-data"></a>Aufgabe 6: klassifizieren und schützen von vertraulichen Daten

Im Rahmen ihrer Arbeit müssen Personen in Ihrer Organisation mit anderen Personen innerhalb und außerhalb der Organisation zusammenarbeiten. Dies bedeutet, dass Inhalte nicht mehr durch eine Firewall geschützt sind – sie können zwischen verschiedenen Geräten, Apps und Diensten hin- und herbewegt werden. Dies soll auf sichere und geschützte Weise geschehen, die den geschäftlichen Anforderungen und Compliancerichtlinien Ihrer Organisation entspricht.

Mit [Sensitivitäts Bezeichnungen](sensitivity-labels.md) können Sie die Daten Ihrer Organisation klassifizieren und schützen und gleichzeitig sicherstellen, dass die Produktivität der Benutzer und ihre Zusammenarbeit nicht behindert werden. Verwenden von Sensitivitäts Bezeichnungen zur Erzwingung von Verschlüsselungs-und Nutzungseinschränkungen wenden Sie visuelle Markierungen an, und schützen Sie Informationen über Plattformen und Geräte hinweg, lokal und in der Cloud.

Eine Schritt-für-Schritt-Anleitung zum Konfigurieren und Verwenden von Sensitivitäts Bezeichnungen finden Sie unter [Erste Schritte mit Vertraulichkeits Bezeichnungen](get-started-with-sensitivity-labels.md). Informationen zur Lizenzierung von Sensitivitäts Bezeichnungen finden Sie unter [Microsoft 365 Licensing Guidance for Security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="task-7-configure-a-retention-policy"></a>Aufgabe 7: Konfigurieren einer Aufbewahrungsrichtlinie

Mit einer [Aufbewahrungsrichtlinie](retention.md) können Sie proaktiv entscheiden, ob Sie Inhalte beibehalten, Inhalte löschen oder beides speichern möchten, und dann den Inhalt am Ende eines bestimmten Aufbewahrungszeitraums beibehalten und löschen. Diese Aktionen sind möglicherweise erforderlich, um Branchenvorschriften und interne Richtlinien einzuhalten und das Risiko im Fall eines Rechtsstreits oder einer Sicherheitsverletzung zu verringern.

Wenn Inhalte einer Aufbewahrungsrichtlinie unterliegen, können Personen weiterhin mit dem Inhalt bearbeiten und arbeiten, als ob nichts geändert würde. Der Inhalt wird an seiner ursprünglichen Stelle aufbewahrt. Aber wenn jemand Inhalte bearbeitet oder löscht, die der Aufbewahrungsrichtlinie unterliegen, wird eine Kopie des ursprünglichen Inhalts an einem sicheren Ort gespeichert, an dem Sie aufbewahrt wird, während die Aufbewahrungsrichtlinie für diese Inhalte aktiv ist.

Sie können schnell eine Aufbewahrungsrichtlinie für mehrere Standorte in Ihrer Microsoft 365-Umgebung wie Exchange-Mail, SharePoint-Websites, OneDrive-Konten und Microsoft 365-Gruppen platzieren. Es gibt keine Beschränkungen für die Anzahl von Postfächern oder Websites, die diese Richtlinie automatisch enthalten kann. Wenn Sie jedoch selektiver sein müssen, können Sie dies durch Konfigurieren einer Aufbewahrungsrichtlinie für bestimmte Speicherorte und einschließen oder Ausschließen von Websites oder Benutzern erreichen.

Eine Schritt-für-Schritt-Anleitung zum Konfigurieren einer Aufbewahrungsrichtlinie finden Sie unter [Erstellen und Konfigurieren von Aufbewahrungs](create-retention-policies.md)Richtlinien. Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

## <a name="task-8-configure-sensitive-information-and-offensive-language-policies"></a>Aufgabe 8: Konfigurieren von vertraulichen Informationen und Richtlinien für anstößige Sprachen

Der Schutz vertraulicher Informationen sowie das erkennen und handeln von Belästigungs Ereignissen am Arbeitsplatz ist ein wichtiger Bestandteil der Einhaltung interner Richtlinien und Standards. Die [Kommunikations Kompatibilität](communication-compliance-feature-reference.md) in Microsoft 365 hilft, diese Risiken zu minimieren, indem Sie Ihnen helfen, schnell Wiederherstellungsaktionen für e-Mail-und Microsoft Teams-Kommunikation zu erkennen, zu erfassen und zu ergreifen. Dazu gehören unangemessene Kommunikation mit anstößigen Inhalten, Bedrohungen sowie Belästigung und Kommunikation, die vertrauliche Informationen innerhalb und außerhalb Ihrer Organisation gemeinsam nutzen.

Mit einer vordefinierten Richtlinienvorlage für *anstößige Sprache und antibelästigungs* Maßnahmen können Sie interne und externe Kommunikationen nach Richtlinien Übereinstimmungen durchsuchen, damit Sie von bestimmten Prüfern geprüft werden können. Bearbeiter können gescannte e-Mails, Microsoft Teams, jammern oder Kommunikation von Drittanbietern in Ihrer Organisation untersuchen und geeignete Korrekturaktionen durchführen, um sicherzustellen, dass diese mit den Standards Ihrer Organisation konform sind.

Mit der vordefinierten Richtlinie für *vertrauliche Informationen* können Sie schnell eine Richtlinie zum Überprüfen von e-Mails und Microsoft Teams-Kommunikationen mit definierten vertraulichen Informationstypen oder Stichwörtern erstellen, um sicherzustellen, dass wichtige Daten nicht für Personen freigegeben werden, die keinen Zugriff haben sollten. Diese Aktivitäten können nicht autorisierte Kommunikation über vertrauliche Projekte oder branchenspezifische Regeln für Insidergeschäfte oder andere betrügerische Aktivitäten umfassen.

Eine Schritt-für-Schritt-Anleitung zum Planen und Konfigurieren der Kommunikations Kompatibilität finden Sie unter [Planen der Kommunikation](communication-compliance-plan.md) Compliance und [Erste Schritte mit der Kommunikation Compliance](communication-compliance-configure.md). Informationen zur Lizenzierung von Kommunikationsrichtlinien finden Sie unter [Microsoft 365 Licensing Guidance for Security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance).

## <a name="task-9-see-whats-happening-with-your-sensitive-items"></a>Aufgabe 9: sehen Sie, was mit Ihren vertraulichen Elementen passiert

Vertraulichkeits Bezeichnungen, vertrauliche Informationstypen, Aufbewahrungs Bezeichnungen und Richtlinien sowie Schulungs relevante Klassifizierungen können verwendet werden, um vertrauliche Elemente in Exchange, SharePoint und OneDrive zu klassifizieren und zu bezeichnen, wie Sie es in den vorherigen Aufgaben gesehen haben. Der letzte Schritt in ihrer schnellen Aufgabenstellung ist, zu sehen, welche Elemente beschriftet wurden und welche Aktionen Ihre Benutzer für diese vertraulichen Elemente durchführen. Diese Sichtbarkeit wird von [Inhalts-Explorer](data-classification-content-explorer.md) und [Aktivitäts-Explorer](data-classification-activity-explorer.md) bereitgestellt.

### <a name="content-explorer"></a>Inhalts-Explorer
 Mit dem Inhalts-Explorer können Sie alle Elemente, die als vertraulicher Informationstyp klassifiziert wurden oder zu einer bestimmten Klassifizierung gehören, in ihrem systemeigenen Format anzeigen, sowie alle Elemente, für die eine Sensitivitäts-oder Aufbewahrungs Bezeichnung gilt.

Eine Schritt-für-Schritt-Anleitung zur Verwendung des Inhalts-Explorers finden Sie unter [kennen ihrer Daten Datenklassifizierung (Übersicht](data-classification-overview.md)) und [Erste Schritte mit dem Inhalts-Explorer](data-classification-content-explorer.md).

### <a name="activity-explorer"></a>Aktivitäten-Explorer
Mit dem Aktivitäts-Explorer können Sie überwachen, was mit den vertraulichen Elementen ihrer klassifizierten und beschrifteten Elemente geschieht:
- Microsoft Office SharePoint Online
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

Eine Schritt-für-Schritt-Anleitung zur Verwendung des Aktivitäts-Explorers finden Sie unter [Erste Schritte mit dem Aktivitäts-Explorer](data-classification-activity-explorer.md).

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Grundlagen für die Verwaltung der Richtlinientreue für Ihre Organisation konfiguriert haben, sollten Sie die folgenden Kompatibilitätslösungen in Microsoft 365 verwenden, um vertrauliche Informationen zu schützen und zusätzliche Insider Risiken zu erkennen und zu handeln.

### <a name="configure-retention-labels"></a>Aufbewahrungsbezeichnungen konfigurieren

Während Aufbewahrungsrichtlinien auf Containerebene auf Standorte wie SharePoint-Websites und Exchange-Postfächer angewendet werden, ermöglichen [Aufbewahrungs Bezeichnungen](retention.md#retention-labels) spezifischere Zielgruppenadressierung für Ihre Aufbewahrungs-und Löschungsrichtlinien. Beispielsweise auf der Ebene des Dokuments oder der e-Mail-Nachricht, die Endbenutzer zusätzlich zur automatischen Anwendung durch Administratoren manuell anwenden können. Sie können auch eine Aufbewahrungs Bezeichnung auf eine Dokumentbibliothek, einen Ordner oder eine Dokumentenmappe in SharePoint anwenden, sodass alle Dokumente, die an diesem Speicherort gespeichert sind, die standardmäßige Aufbewahrungs Bezeichnung erben.

Darüber hinaus unterstützen Aufbewahrungs Bezeichnungen die [Datensatzverwaltung](records-management.md) , um Inhalte als Datensatz zu kennzeichnen. In diesem Fall legt die Bezeichnung zusätzliche Einschränkungen für die Inhalte fest, die möglicherweise erforderlich sind, um Ihrer Organisation die Einhaltung behördlicher Anforderungen zu erleichtern.

Eine Schritt-für-Schritt-Anleitung zum Erstellen und Veröffentlichen von Aufbewahrungs Bezeichnungen finden Sie in den folgenden Anleitungen:
- [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)
- [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)

Erste Schritte mit der Datensatzverwaltung finden Sie unter [Erste Schritte mit der Datensatzverwaltung](get-started-with-records-management.md).

### <a name="identify-and-define-sensitive-information-types"></a>Identifizieren und Definieren von Typen für vertrauliche Informationen

Definieren Sie Typen vertraulicher Informationen basierend auf dem Muster, das in Informationen in den Daten Ihrer Organisation enthalten ist. Verwenden Sie [integrierte vertrauliche Informationstypen](what-the-sensitive-information-types-look-for.md) , um Kreditkartennummern, Bank Kontonummern, Passport-Nummern und vieles mehr zu identifizieren und zu schützen. Oder erstellen Sie Ihre eigenen [benutzerdefinierten Vertraulichkeits Informationstypen](custom-sensitive-info-types.md) , die für Ihre Organisation spezifisch sind.

Eine Schritt-für-Schritt-Anleitung zum Definieren von benutzerdefinierten Typen vertraulicher Informationen finden Sie unter [Erstellen eines benutzerdefinierten vertraulichen Informationstyps im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type).

### <a name="prevent-data-loss"></a>Datenverlust verhindern

Mit den [Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP)](data-loss-prevention-policies.md) können Sie vertrauliche Informationen in Ihrer Microsoft 365-Organisation identifizieren, überwachen und automatisch schützen. Verwenden Sie DLP-Richtlinien, um vertrauliche Elemente in Microsoft-Diensten zu identifizieren, die unbeabsichtigte Freigabe von vertraulichen Elementen zu verhindern und Benutzer dabei zu unterstützen, die Kompatibilität zu verbleiben, ohne den Workflow zu unterbrechen.

Eine Schritt-für-Schritt-Anleitung zum Konfigurieren von DLP-Richtlinien finden Sie unter [Erste Schritte mit DLP-Richtlinien Empfehlungen](get-started-with-dlp-policy-recommendations.md) und [Erste Schritte mit der standardmäßigen DLP-Richtlinie](get-started-with-the-default-dlp-policy.md). Informationen zur Lizenzierung von Datenverlust Management finden Sie unter [Microsoft 365 Licensing Guidance for Security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

### <a name="detect-and-act-on-insider-risks"></a>Erkennen und handeln von Insider Risiken

Die Mitarbeiter haben zunehmend Zugriff auf das Erstellen, verwalten und Freigeben von Daten für ein breites Spektrum an Plattformen und Diensten. In den meisten Fällen verfügen Organisationen über beschränkte Ressourcen und Tools, um organisationsweite Risiken zu identifizieren und zu verringern und gleichzeitig Compliance-Anforderungen und Datenschutzstandards für Mitarbeiter zu erfüllen. Zu diesen Risiken können Datendiebstahl durch das Ablegen von Mitarbeitern und Datenverluste von Informationen außerhalb Ihrer Organisation durch versehentliche über-oder böswillige Übernutzung oder böswillige Absicht gehören.

Das [Insider Risk Management](insider-risk-management-policies.md) in Microsoft 365 verwendet die gesamte Bandbreite an Dienst-und Drittanbieter Indikatoren, damit Sie riskante Benutzeraktivitäten schnell erkennen, selektieren und handeln können. Mithilfe von Protokollen aus Microsoft 365 und Microsoft Graph können Sie mit dem Insider Risikomanagement bestimmte Richtlinien definieren, um Risikoindikatoren zu identifizieren und Maßnahmen zur Minderung dieser Risiken zu ergreifen.

Eine Schritt-für-Schritt-Anleitung zum Planen und Konfigurieren von Richtlinien für das Insider Risikomanagement finden Sie unter [Plan for Insider Risk](insider-risk-management-plan.md) Management und [Erste Schritte mit Insider Risk Management](insider-risk-management-configure.md). Informationen zur Lizenzierung von Insider-Risikomanagement finden Sie unter [Microsoft 365-Lizenzierungsrichtlinien für Sicherheits & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management).
