---
title: Berechtigungen – Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.AdminRoleGroups
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: Administratoren können sich über die Berechtigungen informieren, die im Security & Compliance Center in Microsoft 365 zur Verfügung stehen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 82a2cd7716021c0c75b06d583c738994d9c65310
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750867"
---
# <a name="permissions-in-the-security--compliance-center"></a>Berechtigungen im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Mit dem Security & Compliance Center können Sie Personen, die Compliance-Aufgaben wie Geräteverwaltung, Verhinderung von Datenverlust, eDiscovery, Aufbewahrung usw. ausführen, Berechtigungen erteilen. Diese Personen können nur die Aufgaben ausführen, denen Sie explizit Zugriff gewähren. Für den Zugriff auf das Security & Compliance Center müssen Benutzer ein globaler Administrator oder Mitglied einer oder mehrerer Sicherheits & Compliance Center-Rollengruppen sein.

Berechtigungen im Security & Compliance Center basieren auf dem Berechtigungsmodell der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC). RBAC ist das gleiche Berechtigungsmodell, das von Exchange verwendet wird, wenn Sie also mit Exchange vertraut sind, wird das Gewähren von Berechtigungen im Security & Compliance Center sehr ähnlich sein. Beachten Sie jedoch, dass Exchange-Rollengruppen und Sicherheits & Compliance Center-Rollengruppen keine Mitgliedschaft oder Berechtigungen gemeinsam nutzen. Zwar verfügen beide über eine Rollengruppe "Organisationsverwaltung", sie sind jedoch nicht identisch. Die erteilten Berechtigungen und die Mitglieder der Rollengruppen sind verschieden. Unten finden Sie eine Liste der Rollengruppen Security & Compliance Center.

![Seite "Berechtigungen" im Security & Compliance Center](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Beziehung zwischen Mitgliedern, Rollen und Rollengruppen

Eine **Rolle** gewährt Berechtigungen zum Ausführen einer Reihe von Aufgaben. Beispielsweise berechtigt die Rolle "Fallmanagement" Personen zum Arbeiten mit eDiscovery-Fällen.

Eine **Rollengruppe** ist eine Gruppe von Rollen, mit deren Hilfe Benutzer ihre Aufgaben über das Compliance Center für Sicherheits & erledigen können. Beispielsweise umfasst die Rollengruppe "Compliance Administrator" (unter anderem Rollen) die Rollen für die Fallverwaltung, die Inhaltssuche und die Organisationskonfiguration (plus andere), da eine Person, die ein Compliance-Administrator ist, die Berechtigungen für diese Aufgaben benötigt, um Ihre Arbeit zu erledigen.

Das Security & Compliance Center enthält Standardrollengruppen für die am häufigsten verwendeten Aufgaben und Funktionen, denen Sie Personen zuweisen müssen. Es wird empfohlen, nur einzelne Benutzer als **Mitglieder** zu den Standardrollengruppen hinzuzufügen.

![Diagramm mit Beziehungen zwischen Rollengruppen und Rollen und Mitgliedern](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Erforderliche Berechtigungen für die Verwendung von Features im Security & Compliance Center

In der folgenden Tabelle sind die Standardrollengruppen aufgelistet, die im Security & Compliance Center verfügbar sind, sowie die Rollen, die standardmäßig den Rollengruppen zugewiesen sind. Um einem Benutzerberechtigungen zum Ausführen einer Konformitäts Aufgabe zu erteilen, fügen Sie ihn der entsprechenden Sicherheits & Compliance Center-Rollengruppe hinzu.

Durch die Verwaltung von Berechtigungen im Sicherheits & Compliance Center können Benutzer nur auf die Compliance-Features zugreifen, die im Sicherheits & Compliance Center selbst verfügbar sind. Wenn Sie Berechtigungen für andere Kompatibilitätsfeatures gewähren möchten, die sich nicht im Security & Compliance Center befinden, wie Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln), müssen Sie das Exchange Admin Center verwenden.

Informationen zum Erteilen des Zugriffs auf das Compliance Center für Sicherheit & finden Sie unter Gewähren von [Benutzern Zugriff auf das Microsoft 365 Compliance Admin Center](grant-access-to-the-security-and-compliance-center.md).

****

|Rollengruppe|Beschreibung|Zugewiesene Standardrollen|
|---|---|---|
|**Kommunikation Compliance**|Stellt Berechtigungen für alle Kommunikations Konformitäts Rollen bereit: Administrator, Analyst, Prüfer und Viewer.|Fallverwaltung <p> Communication Compliance-Administrator <p> Kompatibilitätsanalyse für Kommunikation <p> Kommunikation Compliance Case Management <p> Untersuchung der Kommunikations Konformität <p> Communication Compliance Viewer <p> Feedback Anbieter für Datenklassifikation <p> View-Only Fall|
|**Kommunikation-Compliance-Administratoren**|Administratoren der Kommunikation Compliance, die Richtlinien erstellen/bearbeiten und globale Einstellungen definieren können.|Communication Compliance-Administrator <p> Kommunikation Compliance Case Management|
|**Kommunikations Compliance-Analysten**|Analysten der Kommunikations Konformität, die die Richtlinien Übereinstimmungen untersuchen, Metadaten von Nachrichten anzeigen und Korrekturaktionen durchführen können.|Kompatibilitätsanalyse für Kommunikation <p> Kommunikation Compliance Case Management|
|**Kommunikation Compliance Investigators**|Analysten der Kommunikations Konformität, die die Richtlinien Übereinstimmungen untersuchen, Nachrichteninhalte anzeigen und Korrekturaktionen durchführen können.|Fallverwaltung <p> Kompatibilitätsanalyse für Kommunikation <p> Kommunikation Compliance Case Management <p> Untersuchung der Kommunikations Konformität <p> Feedback Anbieter für Datenklassifikation <p> View-Only Fall|
|**Kommunikation-Compliance-Viewer**|Anzeige der Kommunikations Konformität, die auf die verfügbaren Berichte und Widgets zugreifen kann.|Kommunikation Compliance Case Management <p> Communication Compliance Viewer|
|**Kompatibilitäts Administrator**<sup>1</sup>|Mitglieder können Einstellungen für die Geräteverwaltung, Verhinderung von Datenverlust, Berichte und Aufbewahrung verwalten.|Fallverwaltung <p> Complianceadministrator <p> Compliance-Suche <p> Feedback Anbieter für Datenklassifikation <p> Feedback Prüfer für die Datenklassifizierung <p> Geräteverwaltung <p> Dispositionsverwaltung <p> DLP-Konformitätsverwaltung <p> Hold <p> IB-Compliance-Management <p> Benachrichtigungen verwalten <p> Organisationskonfiguration <p> RecordManagement <p> Aufbewahrungsverwaltung <p> Überwachungsprotokolle nur anzeigen <p> View-Only Fall <p> View-Only Geräteverwaltung <p> View-Only DLP-Konformitätsverwaltung <p> View-Only IB-Compliance-Management <p> View-Only Benachrichtigungen verwalten <p> Schreibgeschützte Empfänger <p> View-Only-Datensatzverwaltung <p> View-Only Aufbewahrungsverwaltung|
|**Kompatibilitätsdaten Administrator**|Mitglieder können Einstellungen für die Geräteverwaltung, Datenschutz, Verhinderung von Datenverlust, Berichte und Aufbewahrung verwalten.|Complianceadministrator <p> Compliance-Suche <p> Geräteverwaltung <p> DLP-Konformitätsverwaltung <p> Dispositionsverwaltung <p> IB-Compliance-Management <p> Benachrichtigungen verwalten <p> Organisationskonfiguration <p> RecordManagement <p> Aufbewahrungsverwaltung <p> Vertraulichkeits Bezeichnung-Administrator <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only DLP-Konformitätsverwaltung <p> View-Only IB-Compliance-Management <p> View-Only Benachrichtigungen verwalten <p> Schreibgeschützte Empfänger <p> View-Only-Datensatzverwaltung <p> View-Only Aufbewahrungsverwaltung|
|**Compliance-Manager-Administratoren**|Vorlagenerstellung und-Änderung verwalten.|Compliance-Manager-Verwaltung <p> Compliance-Manager-Bewertung <p> Compliance-Manager-Beitrag <p> Compliance-Manager-Leser|
|**Compliance-Manager-Prüfer**|Erstellen von Bewertungen, Implementieren von Verbesserungs Aktionen und Aktualisieren des Teststatus für Verbesserungs Aktionen.|Compliance-Manager-Bewertung <p> Compliance-Manager-Beitrag <p> Compliance-Manager-Leser|
|**Mitwirkende für Compliance-Manager**|Erstellen von Bewertungen und Ausführen von Aufgaben zur Implementierung von Verbesserungs Aktionen|Compliance-Manager-Beitrag <p> Compliance-Manager-Leser|
|**Compliance-Manager-Leser**|Anzeigen aller Kompatibilitäts-Manager-Inhalte mit Ausnahme der Administratorfunktionen.|Compliance-Manager-Leser|
|**Inhalts-Explorer-Inhaltsanzeige**|Zeigen Sie die Inhaltsdateien im Inhalts-Explorer an.|Daten Klassifizierungs-Inhaltsanzeige|
|**Inhalts-Explorer-Listenanzeige**|Zeigen Sie alle Elemente im Inhalts-Explorer nur im Listenformat an.|Listenanzeige für Datenklassifizierung|
|**eDiscovery-Manager**|Mitglieder können Suchvorgänge durchführen und Postfächer, SharePoint Online-Websites und OneDrive for Business-Orte im In-Situ-Speicher platzieren. Mitglieder können auch eDiscovery-Fälle erstellen und verwalten, Mitglieder zu einem Fall hinzufügen und entfernen, Inhalts Suchvorgänge für einen Fall erstellen und bearbeiten sowie auf Falldaten in Advanced eDiscovery zugreifen. <p> Ein eDiscovery-Administrator ist Mitglied der Rollengruppe "eDiscovery-Manager", der zusätzliche Berechtigungen zugewiesen wurden. Zusätzlich zu den Aufgaben, die ein eDiscovery-Manager ausführen kann, kann ein eDiscovery-Administrator Folgendes tun:<ul><li>Anzeigen aller eDiscovery-Fälle in der Organisation.</li><li>Verwalten von eDiscovery-Fällen, nachdem sie sich selbst als Fallmitglied hinzugefügt haben.</li></ul> <p> Der Hauptunterschied zwischen einem eDiscovery-Manager und einem eDiscovery-Administrator besteht darin, dass ein eDiscovery-Administrator auf alle Fälle zugreifen kann, die auf der Seite **eDiscovery-Fälle** im Security & Compliance Center aufgeführt sind. Ein eDiscovery-Manager kann nur auf die von Ihnen erstellten Fälle oder auf Fälle, in denen Sie Mitglied sind, zugreifen. Weitere Informationen zum Erstellen eines eDiscovery-Administrators für einen Benutzer finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center](../../compliance/assign-ediscovery-permissions.md).|Fallverwaltung <p> Kommunikation <p> Compliance-Suche <p> Custodian <p> Exportieren <p> Hold <p> Vorschau <p> Überprüfung <p> RMS-Entschlüsselung|
|**Globaler Leser**|Mitglieder verfügen über schreibgeschützten Zugriff auf Berichte, Warnungen und können alle Konfigurationen und Einstellungen anzeigen.<p> Der Hauptunterschied zwischen dem globalen Leser und dem Sicherheits Leser besteht darin, dass ein globaler Leser auf die **Konfiguration und die Einstellungen** zugreifen kann.|Sicherheitsleseberechtigter <p> Empfindlichkeits Beschriftungs Leser <p> Service Assurance-Ansicht <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only DLP-Konformitätsverwaltung <p> View-Only IB-Compliance-Management <p> View-Only Benachrichtigungen verwalten <p> Schreibgeschützte Empfänger <p> View-Only-Datensatzverwaltung <p> View-Only Aufbewahrungsverwaltung|
|**Insider Risiko Management**|Verwenden Sie diese Rollengruppe zum Verwalten des Risikomanagements für Ihr Unternehmen in einer einzigen Gruppe. Wenn Sie alle Benutzerkonten für designierte Administratoren, Analytiker und Prüfer hinzufügen, können Sie Berechtigungen für das Insider-Risikomanagement in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für Insider-Risikomanagement. Dies ist die einfachste Möglichkeit, den Einstieg in das Insider-Risikomanagement schnell zu finden und eignet sich gut für Unternehmen, die keine separaten Berechtigungen benötigen, die für getrennte Benutzergruppen definiert sind.|Fallverwaltung <p> Insider Risk Management-Administrator <p> Analyse des Insider Risikomanagements <p> Untersuchung des Insider Risikomanagements <p> View-Only Fall|
|**Insider Risk Management-Administratoren**|Verwenden Sie diese Rollengruppe, um zunächst das Insider Risikomanagement zu konfigurieren und später Insider Risiko Administratoren in eine definierte Gruppe zu unter trennen. Benutzer in dieser Rollengruppe können Verwaltungsrichtlinien, globale Einstellungen und Rollengruppenzuweisungen für Insiderrisiken erstellen, lesen, aktualisieren und löschen.|Fallverwaltung <p> Insider Risk Management-Administrator <p> View-Only Fall|
|**Insider Risk Management Analysten**|Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Analysten im Falle eines Insiderrisikos fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungs-, Falll- und Benachrichtigungsvorlagen für Insiderrisiken zugreifen. Sie könne nicht auf den Inhalts-Explorer für Insider-Risiken zugreifen.|Fallverwaltung <p> Analyse des Insider Risikomanagements <p> View-Only Fall|
|**Auditoren für Insider Risk Management**|Auditors of Insider Risk Management, die die Überwachungsprotokolle von von Analysten, Ermittlern und Administratoren durchgeführten Aktionen anzeigen können.|Überwachung des Insider Risikomanagements|
|**Insider Risk Management Investigators**|Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Datenprüfer für Insiderrisiken fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungs-, Falll- und Benachrichtigungsvorlagen für Insiderrisiken sowie auf den Inhalts-Explorer für alle Fälle zugreifen.|Fallverwaltung <p> Untersuchung des Insider Risikomanagements <p> View-Only Fall|
|**IRM-Mitwirkende**|Diese Rollengruppe ist sichtbar, wird aber nur von Hintergrunddiensten verwendet.|Insider Risiko Management dauerhafter Beitrag <p> Insider Risk Management-temporärer Beitrag|
|**Nachrichtenfluss-Administrator**|Mitglieder können den Nachrichtenfluss Einblicke und Berichte im Security & Compliance Center überwachen und anzeigen. Globale Administratoren können gewöhnliche Benutzer zu dieser Gruppe hinzufügen, aber wenn der Benutzer kein Mitglied der Exchange-Administratorgruppe ist, hat der Benutzer keinen Zugriff auf Aufgaben im Zusammenhang mit der Exchange-Verwaltungsaufgabe.|Schreibgeschützte Empfänger|
|**Organisationsverwaltung**<sup>1</sup>|Mitglieder können Berechtigungen für den Zugriff auf Features im Security & Compliance Center Steuern und außerdem Einstellungen für die Geräteverwaltung, Verhinderung von Datenverlust, Berichte und Aufbewahrung verwalten. <p> Benutzer, die keine globalen Administratoren sind, müssen Exchange-Administratoren sein, um auf Geräten, die von grundlegender Mobilität und Sicherheit verwaltet werden, für Microsoft 365 (früher als Mobile Device Management oder MDM bezeichnet) zu sehen und Maßnahmen zu ergreifen. <p> Globale Administratoren werden automatisch als Mitglieder dieser Rollengruppe hinzugefügt.|Überwachungsprotokolle <p> Fallverwaltung <p> Complianceadministrator <p> Compliance-Suche <p> Geräteverwaltung <p> DLP-Konformitätsverwaltung <p> Hold <p> IB-Compliance-Management <p> Benachrichtigungen verwalten <p> Organisationskonfiguration <p> Quarantäne <p> RecordManagement <p> Aufbewahrungsverwaltung <p> Rollenverwaltung <p> Suchen und löschen <p> Sicherheitsadministrator <p> Sicherheitsleseberechtigter <p> Vertraulichkeits Bezeichnung-Administrator <p> Empfindlichkeits Beschriftungs Leser <p> Service Assurance-Ansicht <p> Tag Mitwirkenden <p> Tag-Manager <p> Transponderleser <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only DLP-Konformitätsverwaltung <p> View-Only IB-Compliance-Management <p> View-Only Fall <p> View-Only Benachrichtigungen verwalten <p> Schreibgeschützte Empfänger <p> View-Only-Datensatzverwaltung <p> View-Only Aufbewahrungsverwaltung|
|**Quarantäne Administrator**|Mitglieder können auf Alle Quarantäneaktionen zugreifen. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EoP](manage-quarantined-messages-and-files.md)|Quarantäne|
|**Datenschutz Verwaltung**|Verwalten der Zugriffssteuerung für die Datenschutz-Verwaltungslösung im Microsoft 365 Compliance Center.|Datenschutz-Verwaltungs Administrator <p> Analyse der Datenschutz Verwaltung <p> Untersuchung der Datenschutz Verwaltung <p> Datenschutz-Verwaltung dauerhafter Beitrag <p> Privacy Management-temporärer Beitrag <p> Privacy Management-Viewer|
|**Datenschutz-Verwaltungs Administratoren**|Administratoren der Datenschutz-Verwaltungslösung, die Richtlinien erstellen/bearbeiten und globale Einstellungen definieren kann.|Datenschutz-Verwaltungs Administrator|
|**Datenschutz-Management-Analysten**|Analysten der Datenschutz-Verwaltungslösung, die die Richtlinien Übereinstimmungen untersuchen, Metadaten von Nachrichten anzeigen und Korrekturaktionen durchführen können.|Analyse der Datenschutz Verwaltung|
|**Datenschutz-Verwaltungsmitarbeiter**|Verwalten von Teilnehmerzugriff für Datenschutz-Verwaltungs Fälle.|Datenschutz-Verwaltung dauerhafter Beitrag <p> Privacy Management-temporärer Beitrag|
|**Datenschutz-Verwaltungs Ermittler**|Analysten der Datenschutz-Verwaltungslösung, die die Richtlinien Übereinstimmungen untersuchen, Nachrichteninhalte anzeigen und Korrekturaktionen ausführen kann.|Untersuchung der Datenschutz Verwaltung|
|**Datenschutz-Verwaltungs Betrachter**|Viewer für die Datenschutz-Verwaltungslösung, die auf die verfügbaren Dashboards und Widgets zugreifen kann.|Privacy Management-Viewer|
|**Datensatzverwaltung**|Mitglieder können alle Aspekte der Datensatzverwaltung konfigurieren, einschließlich Aufbewahrungs Bezeichnungen und Dispositions Überprüfungen.|Dispositionsverwaltung <p> RecordManagement <p> Aufbewahrungsverwaltung|
|**Reviewer**|Mitglieder können die Liste der Fälle nur auf der Seite eDiscovery-Fälle im Security & Compliance Center anzeigen. Sie können keine eDiscovery-Fälle erstellen, öffnen oder verwalten. Der primäre Zweck dieser Rollengruppe besteht darin, Mitgliedern das Anzeigen und Zugreifen auf Falldaten in [Advanced eDiscovery (Classic)](../../compliance/office-365-advanced-ediscovery.md) (auch bekannt als *Advanced eDiscovery v1*) zu gestatten. <p> Diese Rollengruppe verfügt über die restriktivsten Berechtigungen in Bezug auf eDiscovery. <p> **Hinweis:** Zu diesem Zeitpunkt können Benutzer, die Mitglied der Rollengruppe Prüfer sind, nicht auf Daten in [Advanced eDiscovery in Microsoft 365](../../compliance/overview-ediscovery-20.md) (auch bekannt als *Advanced eDiscovery v2*) zugreifen. Wenn Sie einem Fall in Advanced eDiscovery v2 Mitglieder hinzufügen möchten, damit Sie die Falldaten überprüfen können, muss ein Benutzer Mitglied der Rollengruppe "eDiscovery-Manager" sein.|Überprüfung|
|**Sicherheits Administrator**|Mitglieder haben Zugriff auf eine Reihe von Sicherheitsfeatures von Identity Protection Center, privilegierten Identitätsverwaltung, Überwachung des Microsoft 365-Dienststatus und Sicherheits & Compliance Center. <p> Standardmäßig kann diese Rollengruppe keine Mitglieder enthalten. Allerdings ist die Sicherheits Administrator Rolle aus Azure Active Directory dieser Rollengruppe zugewiesen. Daher erbt diese Rollengruppe die Funktionen und die Mitgliedschaft der Sicherheits Administrator Rolle von Azure Active Directory. <p> Um Berechtigungen zentral zu verwalten, fügen Sie Gruppenmitglieder im Azure Active Directory Admin Center hinzu, und entfernen Sie Sie. Weitere Informationen finden Sie unter [Administrator Rollen Berechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Wenn Sie diese Rollengruppe im Security & Compliance Center (Mitgliedschaft oder Rolle) bearbeiten, gelten diese Änderungen nur für das Security & Compliance Center und nicht für andere Dienste. <p> Diese Rollengruppe enthält alle schreibgeschützten Berechtigungen der Sicherheits Leserrolle sowie eine Reihe zusätzlicher Administratorberechtigungen für dieselben Dienste: Azure Information Protection, Identity Protection Center, privilegierte Identitätsverwaltung, Überwachung des Microsoft 365-Dienststatus und Sicherheits & Compliance Center.|Überwachungsprotokolle <p> Geräteverwaltung <p> DLP-Konformitätsverwaltung <p> IB-Compliance-Management <p> Benachrichtigungen verwalten <p> Quarantäne <p> Sicherheitsadministrator <p> Vertraulichkeits Bezeichnung-Administrator <p> Tag Mitwirkenden <p> Tag-Manager <p> Transponderleser <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only DLP-Konformitätsverwaltung <p> View-Only IB-Compliance-Management <p> View-Only Benachrichtigungen verwalten|
|**Sicherheits Operator**|Mitglieder können Sicherheitswarnungen verwalten und auch Berichte und Einstellungen von Sicherheitsfeatures anzeigen.|Compliance-Suche <p> Benachrichtigungen verwalten <p> Sicherheitsleseberechtigter <p> Tag Mitwirkenden <p> Transponderleser <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only DLP-Konformitätsverwaltung <p> View-Only IB-Compliance-Management <p> View-Only Benachrichtigungen verwalten|
|**Sicherheits Leser**|Mitglieder verfügen über Lesezugriff auf eine Reihe von Sicherheitsfeatures von Identity Protection Center, die privilegierte Identitätsverwaltung, die Überwachung des Microsoft 365-Dienststatus und Sicherheits & Compliance Center. <p> Standardmäßig kann diese Rollengruppe keine Mitglieder enthalten. Allerdings ist die Sicherheits Leserrolle aus Azure Active Directory dieser Rollengruppe zugewiesen. Daher erbt diese Rollengruppe die Funktionen und die Mitgliedschaft der Sicherheits Leserrolle von Azure Active Directory. <p> Um Berechtigungen zentral zu verwalten, fügen Sie Gruppenmitglieder im Azure Active Directory Admin Center hinzu, und entfernen Sie Sie. Weitere Informationen finden Sie unter [Administrator Rollen Berechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Wenn Sie diese Rollengruppe im Security & Compliance Center (Mitgliedschaft oder Rolle) bearbeiten, gelten diese Änderungen nur für das Security & Compliance Center und nicht für andere Dienste.|Sicherheitsleseberechtigter <p> Empfindlichkeits Beschriftungs Leser <p> Transponderleser <p> View-Only Geräteverwaltung <p> View-Only DLP-Konformitätsverwaltung <p> View-Only IB-Compliance-Management <p> View-Only Benachrichtigungen verwalten|
|**Dienstüberprüfungsbenutzer**|Mitglieder können im Security & Compliance Center auf den Abschnitt Service Assurance zugreifen. Service Assurance stellt Berichte und Dokumente bereit, in denen die Sicherheitspraktiken von Microsoft für Kundendaten beschrieben werden, die in Microsoft 365 gespeichert sind. Außerdem werden unabhängige Überwachungsberichte von Drittanbietern unter Microsoft 365 bereitgestellt. Weitere Informationen finden Sie unter [Service Assurance im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/service-assurance).|Service Assurance-Ansicht|
|**Aufsichtsüberprüfung**|Mitglieder können die Richtlinien erstellen und verwalten, die definieren, welche Kommunikation in einer Organisation einer Überprüfung unterliegt. Weitere Informationen finden Sie unter [configure Communications Compliance Policies for your organization](../../compliance/communication-compliance-configure.md).|Aufsichts Überprüfungs Administrator|
|

> [!NOTE]
> <sup>1</sup> diese Rollengruppe weist Mitgliedern keine Berechtigungen zu, die zum Durchsuchen des Überwachungsprotokolls erforderlich sind, oder um Berichte zu verwenden, die möglicherweise Exchange-Daten enthalten, beispielsweise DLP oder Defender für Office 365 Berichte. Um das Überwachungsprotokoll durchsuchen oder alle Berichte anzeigen zu können, muss einem Benutzer in Exchange Online Berechtigungen zugewiesen werden. Der Grund dafür ist, dass es sich bei dem zugrundeliegenden Cmdlet, das für die Durchsuchung des Überwachungsprotokolls verwendet wird, um ein Exchange Online-Cmdlet handelt. Globale Administratoren können das Überwachungsprotokoll durchsuchen und alle Berichte anzeigen, da diese automatisch als Mitglieder der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzugefügt werden. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="roles-in-the-security--compliance-center"></a>Rollen im Security & Compliance Center

In der folgenden Tabelle sind die verfügbaren Rollen und Rollengruppen aufgelistet, denen Sie standardmäßig zugewiesen sind.

Beachten Sie, dass die folgenden Rollen standardmäßig nicht der Rollengruppe "Organisationsverwaltung" zugewiesen sind:

- Angriffs Simulator-Administrator
- Angriffs Simulator-Nutz Last Autor
- Kommunikation
- Communication Compliance-Administrator
- Kompatibilitätsanalyse für Kommunikation
- Kommunikation Compliance Case Management
- Untersuchung der Kommunikations Konformität
- Communication Compliance Viewer
- Compliance-Manager-Verwaltung
- Compliance-Manager-Bewertung
- Compliance-Manager-Beitrag
- Compliance-Manager-Leser
- Custodian
- Daten Klassifizierungs-Inhaltsanzeige
- Feedback Anbieter für Datenklassifikation
- Feedback Prüfer für die Datenklassifizierung
- Listenanzeige für Datenklassifizierung
- Dispositionsverwaltung
- Exportieren
- Insider Risk Management-Administrator
- Analyse des Insider Risikomanagements
- Überwachung des Insider Risikomanagements
- Untersuchung des Insider Risikomanagements
- Insider Risiko Management dauerhafter Beitrag
- Insider Risk Management-temporärer Beitrag
- Vorschau
- Datenschutz-Verwaltungs Administrator
- Analyse der Datenschutz Verwaltung
- Untersuchung der Datenschutz Verwaltung
- Datenschutz-Verwaltung dauerhafter Beitrag
- Privacy Management-temporärer Beitrag
- Privacy Management-Viewer
- Überprüfung
- RMS-Entschlüsselung
- Aufsichts Überprüfungs Administrator

****

|Rolle|Beschreibung|Standardrollengruppen Zuweisungen|
|---|---|---|
|**Angriffs Simulator-Administrator**|Wird verwendet, um alle Aspekte von Angriffs Simulations Kampagnen zu erstellen und zu verwalten.||
|**Angriffs Simulator-Nutz Last Autor**|Dient zum Erstellen und Verwalten von Angriffs Nutzlasten, die vom Angriffs Simulator-Administrator bereitgestellt werden können.||
|**Überwachungsprotokolle**|Aktivieren und konfigurieren Sie die Überwachung für die Organisation, zeigen Sie die Überwachungsberichte der Organisation an, und exportieren Sie diese Berichte anschließend in eine Datei.|Organisationsverwaltung <p> Sicherheitsadministrator|
|**Fallverwaltung**|Erstellen, bearbeiten, löschen und Steuern des Zugriffs auf eDiscovery-Fälle.|Kommunikationscompliance <p> Kommunikation Compliance Investigators <p> Complianceadministrator <p>eDiscovery-Manager <p> Insider-Risikomanagement <p> Insider Risk Management-Administratoren <p> Insider Risk Management Analysten <p> Insider Risk Management Investigators <p> Organisationsverwaltung|
|**Kommunikation**|Verwalten Sie die gesamte Kommunikation mit den in einem erweiterten eDiscovery-Fall identifizierten Depotbanken.  Erstellen von Aufbewahrungs Benachrichtigungen, Speichern von Erinnerungen und Eskalationen an die Verwaltung. Verfolgen Sie die depotbestätigung für Aufbewahrungs Benachrichtigungen, und verwalten Sie den Zugriff auf das depotverwalter Portal, das von jeder Depotbank in einem Fall verwendet wird, um die Kommunikation für die Fälle nachzuverfolgen, in denen Sie als Depotbank identifiziert wurden.|eDiscovery-Manager|
|**Communication Compliance-Administrator**|Dient zum Verwalten von Richtlinien im Kommunikations Kompatibilitätsfeature.|Kommunikationscompliance <p> Kommunikation-Compliance-Administratoren|
|**Kompatibilitätsanalyse für Kommunikation**|Dient zum Durchführen einer Untersuchung, Korrektur der Nachrichten Verletzungen im Feature für die Kommunikations Kompatibilität. Kann nur Nachrichten Metadaten anzeigen.|Kommunikationscompliance <p> Kommunikations Compliance-Analysten <p> Kommunikation Compliance Investigators|
|**Kommunikation Compliance Case Management**|Wird für den Zugriff auf Kommunikations Compliance-Fälle verwendet.|Kommunikationscompliance <p> Kommunikation-Compliance-Administratoren <p> Kommunikations Compliance-Analysten <p> Kommunikation Compliance Investigators <p> Kommunikation-Compliance-Viewer|
|**Untersuchung der Kommunikations Konformität**|Dient zum Durchführen von Untersuchungen, Korrekturen und Überprüfen von Nachrichten Verletzungen im Feature für die Kommunikations Kompatibilität. Kann Nachrichten Metadaten und-Nachrichten anzeigen.|Kommunikationscompliance <p> Kommunikation Compliance Investigators|
|**Communication Compliance Viewer**|Wird für den Zugriff auf Berichte und Widgets im Kommunikations Kompatibilitätsfeature verwendet.|Kommunikationscompliance <p> Kommunikation-Compliance-Viewer|
|**Complianceadministrator**|Anzeigen und Bearbeiten von Einstellungen und Berichten für Compliance-Features.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Organisationsverwaltung|
|**Compliance-Manager-Verwaltung**|Vorlagenerstellung und-Änderung verwalten.|Compliance-Manager-Administratoren|
|**Compliance-Manager-Bewertung**|Erstellen von Bewertungen, Implementieren von Verbesserungs Aktionen und Aktualisieren des Teststatus für Verbesserungs Aktionen.|Compliance-Manager-Administratoren <p> Compliance-Manager-Prüfer|
|**Compliance-Manager-Beitrag**|Erstellen von Bewertungen und Ausführen von Aufgaben zur Implementierung von Verbesserungs Aktionen|Compliance-Manager-Administratoren <p> Compliance-Manager-Prüfer <p> Mitwirkende für Compliance-Manager|
|**Compliance Manager Reader**|Anzeigen aller Kompatibilitäts-Manager-Inhalte mit Ausnahme der Administratorfunktionen.|Compliance-Manager-Administratoren <p> Compliance-Manager-Prüfer <p> Mitwirkende für Compliance-Manager <p> Compliance-Manager-Leser|
|**Compliance-Suche**|Durchführen von Suchvorgängen in Postfächern und erhalten einer Schätzung der Ergebnisse.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p>eDiscovery-Manager <p> Organisationsverwaltung <p> Sicherheitsoperator|
|**Custodian**|Identifizieren und Verwalten von Verwaltern für erweiterte eDiscovery-Fälle und Verwenden der Informationen aus Azure Active Directory und anderen Quellen zum Auffinden von Datenquellen, die mit Depotbanken verknüpft sind. Ordnen Sie in einem Fall andere Datenquellen wie Postfächer, SharePoint-Websites und Teams mit depotbanks zu.  Halten Sie die Datenquellen, die Depotbanken zugeordnet sind, rechtlich geschützt, um Inhalte im Kontext eines Falles beizubehalten.|eDiscovery-Manager|
|**Daten Klassifizierungs-Inhaltsanzeige**|Anzeigen des in-Place-Renderings von Dateien im Inhalts-Explorer.|Inhalts-Explorer-Inhaltsanzeige|
|**Feedback Anbieter für Datenklassifikation**|Ermöglicht die Bereitstellung von Feedback für Klassifizierungen im Inhalts-Explorer.|Kommunikationscompliance <p> Kommunikation Compliance Investigators <p> Complianceadministrator|
|**Feedback Prüfer für die Datenklassifizierung**|Ermöglicht das Überprüfen von Feedback von Klassifizierungen im Feedback-Explorer.|Complianceadministrator|
|**Listenanzeige für Datenklassifizierung**|Zeigt die Liste der Dateien im Inhalts-Explorer an.|Inhalts-Explorer-Listenanzeige|
|**Geräteverwaltung**|Anzeigen und Bearbeiten von Einstellungen und Berichten für Geräteverwaltungsfeatures.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Organisationsverwaltung <p> Sicherheitsadministrator|
|**Dispositionsverwaltung**|Steuern der Berechtigungen für den Zugriff auf die manuelle Disposition im Security & Compliance Center.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Datensatzverwaltung|
|**DLP-Konformitätsverwaltung**|Anzeigen und Bearbeiten von Einstellungen und Berichten für DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust).|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Organisationsverwaltung <p> Sicherheitsadministrator|
|**Export**|Exportieren von Postfächern und Websiteinhalten, die von Suchvorgängen zurückgegeben werden.|eDiscovery-Manager|
|**Hold**|Platzieren Sie Inhalte in Postfächern, Websites und öffentlichen Ordnern in der Warteschleife. Wenn die Aufbewahrung aktiviert ist, wird eine Kopie des Inhalts an einem sicheren Speicherort gespeichert. Inhaltsbesitzer können den ursprünglichen Inhalt weiterhin ändern oder löschen.|Complianceadministrator <p>eDiscovery-Manager <p> Organisationsverwaltung|
|**IB-Compliance-Management**|Anzeigen, erstellen, entfernen, ändern und Testen von Richtlinien für Informationsbarrieren.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Organisationsverwaltung <p> Sicherheitsadministrator|
|**Insider Risk Management-Administrator**|Erstellen, bearbeiten, löschen und Steuern des Zugriffs auf das Insider Risiko Management Feature.|Insider-Risikomanagement <p> Insider Risk Management-Administratoren|
|**Analyse des Insider Risikomanagements**|Zugriff auf alle Alerts-, Cases-und Notices-Vorlagen für Insider Risk Management.|Insider-Risikomanagement <p> Insider Risk Management Analysten|
|**Überwachung des Insider Risikomanagements**|Anzeigen von Insider Risiko-Überwachungspfaden zulassen.|Auditoren für Insider Risk Management|
|**Untersuchung des Insider Risikomanagements**|Greifen Sie auf alle Insider Risk Management-Warnungen,-Fälle,-Benachrichtigungsvorlagen und den Inhalts-Explorer für alle Fälle zu.|Insider-Risikomanagement <p> Insider Risk Management Investigators|
|**Insider Risiko Management dauerhafter Beitrag**|Diese Rollengruppe ist sichtbar, wird aber nur von Hintergrunddiensten verwendet.|IRM-Mitwirkende|
|**Insider Risk Management-temporärer Beitrag**|Diese Rollengruppe ist sichtbar, wird aber nur von Hintergrunddiensten verwendet.|IRM-Mitwirkende|
|**Benachrichtigungen verwalten**|Anzeigen und Bearbeiten von Einstellungen und Berichten für Warnungen.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator|
|**Organisationskonfiguration**|Ausführen, anzeigen und Exportieren von Überwachungsberichten und Verwalten von Konformitätsrichtlinien für DLP, Geräte und Aufbewahrung.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Organisationsverwaltung|
|**Preview**|Zeigen Sie eine Liste der Elemente an, die von der Inhaltssuche zurückgegeben werden, und öffnen Sie jedes Element aus der Liste, um den Inhalt anzuzeigen.|eDiscovery-Manager|
|**Datenschutz-Verwaltungs Administrator**|Dient zum Verwalten von Richtlinien in der Datenschutz-Verwaltungslösung und hat Zugriff auf alle Funktionen der Lösung.|Datenschutz Verwaltung <p> Datenschutz-Verwaltungs Administratoren|
|**Analyse der Datenschutz Verwaltung**|Wird verwendet, um Untersuchungen und Korrekturen der Nachrichten Verletzungen in der Datenschutz-Verwaltungslösung durchzuführen. Kann nur Meta-Daten von Nachrichten anzeigen.|Datenschutz Verwaltung <p> Datenschutz-Management-Analysten|
|**Untersuchung der Datenschutz Verwaltung**|Dient zum Durchführen von Untersuchungen, Korrekturen, überprüfen von Nachrichten Verletzungen in der Datenschutz-Verwaltungslösung. Kann Nachrichten Metadaten & vollständigen Nachricht anzeigen.|Datenschutz Verwaltung <p> Datenschutz-Verwaltungs Ermittler|
|**Datenschutz-Verwaltung dauerhafter Beitrag**|Wird verwendet, um als permanenter Mitwirkender auf Datenschutz-Verwaltungs Fall zuzugreifen.|Datenschutz Verwaltung <p> Datenschutz-Verwaltungsmitarbeiter|
|**Privacy Management-temporärer Beitrag**|Wird für den Zugriff auf Datenschutz-Verwaltungs Fall als befristeter Teilnehmer verwendet.|Datenschutz Verwaltung <p> Datenschutz-Verwaltungsmitarbeiter|
|**Privacy Management-Viewer**|Wird für den Zugriff auf Dashboards & Widgets in der Datenschutz-Verwaltungslösung verwendet.|PrivacyManagement <p> Datenschutz-Verwaltungs Betrachter|
|**Quarantäne**|Ermöglicht das Anzeigen und Freigeben von e-Mails in Quarantäne.|Quarantäne Administrator <p> Sicherheitsadministrator <p> Organisationsverwaltung|
|**RecordManagement**|Hier können Sie die Konfiguration des Features für die Datensatzverwaltung anzeigen und bearbeiten.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Organisationsverwaltung <p> Datensatzverwaltung|
|**Aufbewahrungsverwaltung**|Verwalten von Aufbewahrungsrichtlinien, Aufbewahrungs Bezeichnungen und Aufbewahrungs Bezeichnungsrichtlinien|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Organisationsverwaltung <p> Datensatzverwaltung|
|**Überprüfung**|Verwenden Sie Advanced eDiscovery zum Nachverfolgen, markieren, analysieren und Testen von Dokumenten, die Ihnen zugewiesen sind.|eDiscovery-Manager <p> Reviewer|
|**RMS-Entschlüsselung**|Entschlüsseln RMS-geschützter Inhalte beim Exportieren von Suchergebnissen.|eDiscovery-Manager|
|**Rollenverwaltung**|Verwalten der Rollengruppenmitgliedschaft und erstellen oder Löschen benutzerdefinierter Rollengruppen.|Organisationsverwaltung|
|**Suchen und löschen**|Ermöglicht Benutzern das Massen Entfernen von Daten, die den Kriterien einer Inhaltssuche entsprechen.|Organisationsverwaltung|
|**Sicherheits Administrator**|Hier können Sie die Konfiguration und die Berichte für Sicherheitsfeatures anzeigen und bearbeiten.|Organisationsverwaltung <p> Sicherheitsadministrator|
|**Sicherheits Leser**|Anzeigen der Konfiguration und der Berichte für Sicherheitsfeatures.|Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Vertraulichkeits Bezeichnung-Administrator**|Anzeigen, erstellen, ändern und Entfernen von Vertraulichkeits Bezeichnungen.|Kompatibilitätsdaten Administrator <p> Organisationsverwaltung <p> Sicherheitsadministrator|
|**Empfindlichkeits Beschriftungs Leser**|Anzeigen der Konfiguration und Verwendung von Sensitivitäts Bezeichnungen.|Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsleseberechtigter|
|**Service Assurance-Ansicht**|Laden Sie die verfügbaren Dokumente aus dem Abschnitt Service Assurance herunter. Inhalt umfasst unabhängige Überwachung, Konformitäts Dokumentation und Vertrauens bezogene Anleitungen für die Verwendung von Microsoft 365-Features zum Verwalten von behördlicher Compliance und Sicherheitsrisiken.|Globaler Leser <p> Organisationsverwaltung <p> Dienstüberprüfungsbenutzer|
|**Aufsichts Überprüfungs Administrator**|Verwalten von Aufsichts Überprüfungsrichtlinien, einschließlich der zu überprüfenden Kommunikation und der Personen, die die Überprüfung durchführen sollten.|Aufsichtsüberprüfung|
|**Tag Mitwirkenden**|Anzeigen und Aktualisieren der Mitgliedschaft vorhandener Benutzer Tags.|Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator|
|**Tag-Manager**|Anzeigen, aktualisieren, erstellen und Löschen von Benutzer Tags.|Organisationsverwaltung <p> Sicherheitsadministrator|
|**Transponderleser**|Schreibgeschützter Zugriff auf vorhandene Benutzer Tags.|Sicherheitsleseberechtigter|
|**Überwachungsprotokolle nur anzeigen**|Anzeigen und Exportieren von Überwachungsberichten. Da diese Berichte möglicherweise vertrauliche Informationen enthalten, sollten Sie diese Rolle nur Personen zuweisen, die diese Informationen explizit anzeigen müssen.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator|
|**Nur-Ansicht-Fall**||Kommunikationscompliance <p> Kommunikation Compliance Investigators <p> Complianceadministrator <p> Insider-Risikomanagement <p> Insider Risk Management-Administratoren <p> Insider Risk Management Analysten <p> Insider Riskmanagement Investigators <p> Organisationsverwaltung|
|**Geräteverwaltung mit Ansichts Schutz**|Anzeigen der Konfiguration und der Berichte für die Geräte Verwaltungsfunktion.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**DLP-Konformitätsverwaltung mit Ansichts Schutz**|Anzeigen der Einstellungen und Berichte für DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust).|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Compliance-Management für die Anzeige von IB**|Anzeigen der Konfiguration und der Berichte für das Feature "Informationsbarrieren".|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Benachrichtigungen nur anzeigen verwalten**|Zeigen Sie die Konfiguration und die Berichte für das Feature Benachrichtigungen verwalten an.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Schreibgeschützte Empfänger**|Anzeigen von Informationen zu Benutzern und Gruppen.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Globaler Leser <p> Nachrichtenfluss-Administrator <p> Organisationsverwaltung|
|**Datensatzverwaltung mit Ansichts Schutz**|Zeigen Sie die Konfiguration des Features für die Datensatzverwaltung an.|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> <p> Globaler Leser <p> Organisationsverwaltung|
|**Aufbewahrungsverwaltung mit Ansichts Schutz**|Anzeigen der Konfiguration von Aufbewahrungsrichtlinien, Aufbewahrungs Bezeichnungen und Aufbewahrungs Bezeichnungsrichtlinien|Complianceadministrator <p> Kompatibilitätsdaten Administrator <p> Globaler Administrator <p> Organisationsverwaltung|
|
