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
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: Administratoren können sich über die Berechtigungen informieren, die im Security & Compliance Center in Microsoft 365 verfügbar sind.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a2be234805977dd1efce10032e36113a460f3d96
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769881"
---
# <a name="permissions-in-the-security--compliance-center"></a>Berechtigungen im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Mit dem Security & Compliance Center können Sie Personen Berechtigungen erteilen, die Compliance-Aufgaben wie Geräteverwaltung, Verhinderung von Datenverlust, eDiscovery, Aufbewahrung usw. ausführen. Diese Personen können nur die Aufgaben ausführen, auf die Sie ihnen explizit Zugriff gewähren. Um auf das Security & Compliance Center zugreifen zu können, müssen Benutzer ein globaler Administrator oder Mitglied einer oder mehrerer Rollengruppen des Security & Compliance Centers sein.

Berechtigungen im Security & Compliance Center basieren auf dem Rollenbasierten Zugriffssteuerungsmodell (RBAC). RBAC ist das gleiche Berechtigungsmodell, das von Exchange verwendet wird. Wenn Sie also mit Exchange vertraut sind, ist das Gewähren von Berechtigungen im Security & Compliance Center sehr ähnlich. Es ist jedoch wichtig zu beachten, dass Exchange Rollengruppen und Sicherheits- & Compliance Center-Rollengruppen keine Mitgliedschaft oder Berechtigungen teilen. Zwar verfügen beide über eine Rollengruppe "Organisationsverwaltung", sie sind jedoch nicht identisch. Die erteilten Berechtigungen und die Mitglieder der Rollengruppen sind verschieden. Unten finden Sie eine Liste der Rollengruppen im Security & Compliance Center.

![Seite "Berechtigungen" im Security & Compliance Center](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Beziehung zwischen Mitgliedern, Rollen und Rollengruppen

Eine **Rolle** gewährt Berechtigungen zum Ausführen einer Reihe von Aufgaben. Beispielsweise berechtigt die Rolle "Fallmanagement" Personen zum Arbeiten mit eDiscovery-Fällen.

Eine **Rollengruppe** ist eine Reihe von Rollen, mit denen Personen ihre Aufgaben im Security & Compliance Center erledigen können. Die Rollengruppe "Complianceadministrator" umfasst beispielsweise (neben anderen Rollen) die Rollen für Fallverwaltung, Inhaltssuche und Organisationskonfiguration (und andere), da eine Person, die ein Complianceadministrator ist, die Berechtigungen für diese Aufgaben benötigt, um ihre Arbeit zu erledigen.

Das Security & Compliance Center enthält Standardrollengruppen für die gängigsten Aufgaben und Funktionen, denen Sie Personen zuweisen müssen. Es wird empfohlen, einfach einzelne Benutzer als **Mitglieder** zu den Standardrollengruppen hinzuzufügen.

![Diagramm, das die Beziehung von Rollengruppen zu Rollen und Mitgliedern zeigt](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="role-groups-in-the-security--compliance-center"></a>Rollengruppen im Security & Compliance Center

In der folgenden Tabelle sind die Standardrollengruppen aufgeführt, die im Security & Compliance Center verfügbar sind, und die Rollen, die den Rollengruppen standardmäßig zugewiesen sind. Um einem Benutzer Berechtigungen zum Ausführen einer Complianceaufgabe zu erteilen, fügen Sie sie der entsprechenden Sicherheits- & Compliance Center-Rollengruppe hinzu.

Die Verwaltung von Berechtigungen im Security & Compliance Center gewährt Benutzern nur Zugriff auf die Compliance-Features, die im Security & Compliance Center selbst verfügbar sind. Wenn Sie anderen Compliancefeatures, die sich nicht im Security & Compliance Center befinden, Berechtigungen erteilen möchten, z. B. Exchange Nachrichtenflussregeln (auch als Transportregeln bezeichnet), müssen Sie das Exchange Admin Center verwenden.

Informationen zum Gewähren des Zugriffs auf das Security & Compliance Center finden Sie unter ["Benutzern Zugriff auf Microsoft 365 Compliance Admin Center](grant-access-to-the-security-and-compliance-center.md)gewähren".

> [!NOTE]
> Um die Registerkarte **"Berechtigungen"** im Security & Compliance Center anzuzeigen, müssen Sie Administrator sein. Insbesondere muss Ihnen die **Rollenverwaltungsrolle** zugewiesen werden, und diese Rolle wird standardmäßig nur der Rollengruppe **"Organisationsverwaltung"** im Security & Compliance Center zugewiesen. Darüber hinaus ermöglicht die **Rolle "Rollenverwaltung"** Benutzern das Anzeigen, Erstellen und Ändern von Rollengruppen.

<br>

****

|Rollengruppe|Beschreibung|Zugewiesene Standardrollen|
|---|---|---|
|**Kommunikationscompliance**|Bietet Berechtigungen für alle Kommunikationscompliancerollen: Administrator, Analyst, Ermittler und Betrachter.|Fallverwaltung <p> Kommunikationscompliance-Administrator <p> Analyse der Kommunikationscompliance <p> Kommunikationscompliance-Fallmanagement <p> Untersuchung der Kommunikationscompliance <p> Kommunikationscompliance Viewer <p> Feedbackanbieter für Datenklassifizierung <p> View-Only Fall|
|**Kommunikationscomplianceadministratoren**|Administratoren der Kommunikationscompliance, die Richtlinien erstellen/bearbeiten und globale Einstellungen definieren können.|Kommunikationscompliance-Administrator <p> Kommunikationscompliance-Fallmanagement|
|**Kommunikationscomplianceanalysten**|Analysten der Kommunikationscompliance, die Richtlinienübersprechung untersuchen, Nachrichtenmetadaten anzeigen und Korrekturmaßnahmen ergreifen können.|Analyse der Kommunikationscompliance <p> Kommunikationscompliance-Fallmanagement|
|**Ermittler der Kommunikationscompliance**|Analysten der Kommunikationscompliance, die Richtlinienüberstimmungen untersuchen, Nachrichteninhalte anzeigen und Korrekturmaßnahmen ergreifen können.|Fallverwaltung <p> Analyse der Kommunikationscompliance <p> Kommunikationscompliance-Fallmanagement <p> Untersuchung der Kommunikationscompliance <p> Feedbackanbieter für Datenklassifizierung <p> View-Only Fall|
|**Viewer für kommunikationscompliance**|Viewer der Kommunikationscompliance, die auf die verfügbaren Berichte und Widgets zugreifen kann.|Kommunikationscompliance-Fallmanagement <p> Kommunikationscompliance Viewer|
|**Complianceadministrator**<sup>1</sup>|Mitglieder können Einstellungen für geräteverwaltung, Verhinderung von Datenverlust, Berichte und Aufbewahrung verwalten.|Fallverwaltung <p> Complianceadministrator <p> Compliance-Suche <p> Feedbackanbieter für Datenklassifizierung <p> Feedbackprüfer zur Datenklassifizierung <p> Geräteverwaltung <p> Dispositionsverwaltung <p> DLP-Complianceverwaltung <p> Hold <p> IB-Compliance-Management <p> Benachrichtigungen verwalten <p> Organisationskonfiguration <p> RecordManagement <p> Aufbewahrungsverwaltung <p> Überwachungsprotokolle nur anzeigen <p> View-Only Fall <p> View-Only Geräteverwaltung <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Warnungen verwalten <p> Schreibgeschützte Empfänger <p> View-Only Datensatzverwaltung <p> View-Only-Aufbewahrungsverwaltung|
|**Compliancedatenadministrator**|Mitglieder können Einstellungen für Geräteverwaltung, Datenschutz, Verhinderung von Datenverlust, Berichte und Aufbewahrung verwalten.|Complianceadministrator <p> Compliance-Suche <p> Geräteverwaltung <p> DLP-Complianceverwaltung <p> Dispositionsverwaltung <p> IB-Compliance-Management <p> Benachrichtigungen verwalten <p> Organisationskonfiguration <p> RecordManagement <p> Aufbewahrungsverwaltung <p> Administrator für Vertraulichkeitsbezeichnungen <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Warnungen verwalten <p> Schreibgeschützte Empfänger <p> View-Only Datensatzverwaltung <p> View-Only-Aufbewahrungsverwaltung|
|**Compliance-Manager-Administratoren**|Verwalten der Erstellung und Änderung von Vorlagen.|Compliance-Manager-Verwaltung <p> Compliance-Manager-Bewertung <p> Compliance-Manager-Beitrag <p> Compliance-Manager-Leser|
|**Compliance-Manager-Prüfer**|Erstellen Sie Bewertungen, implementieren Sie Verbesserungsmaßnahmen, und aktualisieren Sie den Teststatus für Verbesserungsmaßnahmen.|Compliance-Manager-Bewertung <p> Compliance-Manager-Beitrag <p> Compliance-Manager-Leser|
|**Compliance-Manager-Mitwirkende**|Erstellen Sie Bewertungen, und führen Sie Arbeit aus, um Verbesserungsmaßnahmen zu implementieren.|Compliance-Manager-Beitrag <p> Compliance-Manager-Leser|
|**Compliance-Manager-Leser**|Zeigen Sie alle Compliance-Manager-Inhalte mit Ausnahme von Administratorfunktionen an.|Compliance-Manager-Leser|
|**Inhalts-Explorer-Inhaltsanzeige**|Zeigen Sie die Inhaltsdateien im Inhalts-Explorer an.|Inhaltsanzeige für Datenklassifizierung|
|**Inhalts-Explorer-Listenanzeige**|Zeigen Sie alle Elemente im Inhalts-Explorer nur im Listenformat an.|Datenklassifizierungslistenanzeige|
|**eDiscovery-Manager**|Mitglieder können Suchvorgänge durchführen und Postfächer, SharePoint Online-Websites und OneDrive for Business-Orte im In-Situ-Speicher platzieren. Mitglieder können auch eDiscovery-Fälle erstellen und verwalten, Mitglieder zu einem Fall hinzufügen und entfernen, Inhaltssuchen erstellen und bearbeiten, die einem Fall zugeordnet sind, und auf Falldaten in Advanced eDiscovery zugreifen. <p> Ein eDiscovery-Administrator ist Mitglied der Rollengruppe "eDiscovery-Manager", der zusätzliche Berechtigungen zugewiesen wurden. Zusätzlich zu den Aufgaben, die ein eDiscovery-Manager ausführen kann, kann ein eDiscovery-Administrator:<ul><li>Alle eDiscovery-Fälle in der Organisation anzeigen.</li><li>Verwalten von eDiscovery-Fällen, nachdem sie sich selbst als Fallmitglied hinzugefügt haben.</li></ul> <p> Der Hauptunterschied zwischen einem eDiscovery-Manager und einem eDiscovery-Administrator besteht darin, dass ein eDiscovery-Administrator auf alle Fälle zugreifen kann, die auf der Seite **"eDiscovery-Fälle"** im Security & Compliance Center aufgeführt sind. Ein eDiscovery-Manager kann nur auf die erstellten Fälle oder Fälle zugreifen, in denen er Mitglied ist. Weitere Informationen zum Festlegen eines Benutzers als eDiscovery-Administrator finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center.](../../compliance/assign-ediscovery-permissions.md)|Fallverwaltung <p> Kommunikation <p> Compliance-Suche <p> Verwahrer <p> Exportieren <p> Hold <p> Vorschau <p> Überprüfung <p> RMS Decrypt|
|**Globaler Leser**|Mitglieder haben schreibgeschützten Zugriff auf Berichte, Warnungen und können alle Konfigurationen und Einstellungen anzeigen.<p> Der Hauptunterschied zwischen dem globalen Reader und dem Sicherheitsleseberechtigten besteht darin, dass ein globaler Leser auf **Konfiguration und Einstellungen** zugreifen kann.|Sicherheitsleseberechtigter <p> Leseberechtigter für Vertraulichkeitsbezeichnungen <p> Service Assurance-Ansicht <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Warnungen verwalten <p> Schreibgeschützte Empfänger <p> View-Only Datensatzverwaltung <p> View-Only-Aufbewahrungsverwaltung|
|**Insider-Risikomanagement**|Verwenden Sie diese Rollengruppe zum Verwalten des Risikomanagements für Ihr Unternehmen in einer einzigen Gruppe. Wenn Sie alle Benutzerkonten für designierte Administratoren, Analytiker und Prüfer hinzufügen, können Sie Berechtigungen für das Insider-Risikomanagement in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für Insider-Risikomanagement. Dies ist die einfachste Möglichkeit, den Einstieg in das Insider-Risikomanagement schnell zu finden und eignet sich gut für Unternehmen, die keine separaten Berechtigungen benötigen, die für getrennte Benutzergruppen definiert sind.|Fallverwaltung <p> Administrator für Insider-Risikomanagement <p> Insider-Risikomanagementanalyse <p> Untersuchung des Insider-Risikomanagements <p> View-Only Fall|
|**Administratoren des Insider-Risikomanagements**|Verwenden Sie diese Rollengruppe, um zunächst das Insider-Risikomanagement zu konfigurieren und später Insider-Risikoadministratoren in eine definierte Gruppe zu unterteilen. Benutzer in dieser Rollengruppe können Verwaltungsrichtlinien, globale Einstellungen und Rollengruppenzuweisungen für Insiderrisiken erstellen, lesen, aktualisieren und löschen.|Fallverwaltung <p> Administrator für Insider-Risikomanagement <p> View-Only Fall|
|**Insider-Risikomanagement-Analysten**|Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Analysten im Falle eines Insiderrisikos fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungs-, Falll- und Benachrichtigungsvorlagen für Insiderrisiken zugreifen. Sie könne nicht auf den Inhalts-Explorer für Insider-Risiken zugreifen.|Fallverwaltung <p> Insider-Risikomanagementanalyse <p> View-Only Fall|
|**Auditoren des Insider-Risikomanagements**|Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die Aktivitäten des Insider-Risikomanagements überwachen. Benutzer in dieser Rollengruppe können auf das Überwachungsprotokoll für Insider-Risiken zugreifen.|Insider-Risikomanagement-Überwachung|
|**Insider-Risikomanagement-Prüfer**|Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Datenprüfer für Insiderrisiken fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungs-, Falll- und Benachrichtigungsvorlagen für Insiderrisiken sowie auf den Inhalts-Explorer für alle Fälle zugreifen.|Fallverwaltung <p> Untersuchung des Insider-Risikomanagements <p> View-Only Fall|
|**IRM-Mitwirkende**|Diese Rollengruppe ist sichtbar, wird aber nur von Hintergrunddiensten verwendet.|Permanenter Beitrag zum Insider-Risikomanagement <p> Temporärer Beitrag zum Insider-Risikomanagement|
|**MailFlow-Administrator**|Mitglieder können Nachrichtenfluss-Einblicke und -Berichte im Security & Compliance Center überwachen und anzeigen. Globale Administratoren können dieser Gruppe normale Benutzer hinzufügen, aber wenn der Benutzer kein Mitglied der Exchange Admin-Gruppe ist, hat der Benutzer keinen Zugriff auf Exchange administratorbezogene Aufgaben.|Schreibgeschützte Empfänger|
|**Organisationsverwaltung**<sup>1</sup>|Mitglieder können Berechtigungen für den Zugriff auf Features im Security & Compliance Center steuern und auch Einstellungen für geräteverwaltung, Verhinderung von Datenverlust, Berichte und Aufbewahrung verwalten. <p> Benutzer, die keine globalen Administratoren sind, müssen Exchange Administratoren sein, um Geräte anzuzeigen und Maßnahmen zu ergreifen, die von Basic Mobility and Security for Microsoft 365 (früher als Mobile Device Management oder MDM bezeichnet) verwaltet werden. <p> Globale Administratoren werden automatisch als Mitglieder dieser Rollengruppe hinzugefügt.|Überwachungsprotokolle <p> Fallverwaltung <p> Complianceadministrator <p> Compliance-Suche <p> Geräteverwaltung <p> DLP-Complianceverwaltung <p> Hold <p> IB-Compliance-Management <p> Benachrichtigungen verwalten <p> Organisationskonfiguration <p> Quarantäne <p> RecordManagement <p> Aufbewahrungsverwaltung <p> Rollenverwaltung <p> Suchen und Löschen <p> Sicherheitsadministrator <p> Sicherheitsleseberechtigter <p> Administrator für Vertraulichkeitsbezeichnungen <p> Leseberechtigter für Vertraulichkeitsbezeichnungen <p> Service Assurance-Ansicht <p> Tag-Mitwirkender <p> Tag-Manager <p> Tag Reader <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Fall <p> View-Only Warnungen verwalten <p> Schreibgeschützte Empfänger <p> View-Only Datensatzverwaltung <p> View-Only-Aufbewahrungsverwaltung|
|**Quarantäneadministrator**|Mitglieder können auf alle Quarantäneaktionen zugreifen. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md)|Quarantäne|
|**Datensatzverwaltung**|Mitglieder können alle Aspekte der Datensatzverwaltung konfigurieren, einschließlich Aufbewahrungsbezeichnungen und Löschungsüberprüfungen.|Dispositionsverwaltung <p> RecordManagement <p> Aufbewahrungsverwaltung|
|**Reviewer**|Mitglieder können in [Advanced eDiscovery](../../compliance/overview-ediscovery-20.md) Fällen auf Prüfdateisätze zugreifen. Mitglieder dieser Rollengruppe können die Liste der Fälle auf der Seite **"eDiscovery > Erweitert"** im Microsoft 365 Compliance Center anzeigen und öffnen, in dem sie Mitglieder sind. Nachdem der Benutzer auf einen Advanced eDiscovery Fall zugegriffen hat, kann er **Prüfdateisätze** auswählen, um auf Falldaten zuzugreifen. Mit dieser Rolle kann der Benutzer keine Vorschau der Ergebnisse einer Sammlungssuche anzeigen, die dem Fall zugeordnet ist, oder andere Such- oder Fallverwaltungsaufgaben ausführen. Mitglieder dieser Rollengruppe können nur auf die Daten in einem Prüfdateisatz zugreifen.|Überprüfung|
|**Sicherheitsadministrator**|Mitglieder haben Zugriff auf eine Reihe von Sicherheitsfeatures von Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health und Security & Compliance Center. <p> Standardmäßig scheint diese Rollengruppe keine Mitglieder zu haben. Die Rolle "Sicherheitsadministrator" aus Azure Active Directory wird dieser Rollengruppe zugewiesen. Daher erbt diese Rollengruppe die Funktionen und die Mitgliedschaft der Sicherheitsadministratorrolle von Azure Active Directory. <p> Um Berechtigungen zentral zu verwalten, fügen Sie Gruppenmitglieder im Azure Active Directory Admin Center hinzu und entfernen sie. Weitere Informationen finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Wenn Sie diese Rollengruppe im Security & Compliance Center bearbeiten (Mitgliedschaft oder Rollen), gelten diese Änderungen nur für das Security & Compliance Center und nicht für andere Dienste. <p> Diese Rollengruppe enthält alle schreibgeschützten Berechtigungen der Rolle "Sicherheitsleseberechtigter" sowie eine Reihe zusätzlicher Administratorberechtigungen für dieselben Dienste: Azure Information Protection, Identity Protection Center, Privileged Identity Management, Überwachen Microsoft 365 Dienststatus und Security & Compliance Center.|Überwachungsprotokolle <p> Geräteverwaltung <p> DLP-Complianceverwaltung <p> IB-Compliance-Management <p> Benachrichtigungen verwalten <p> Quarantäne <p> Sicherheitsadministrator <p> Administrator für Vertraulichkeitsbezeichnungen <p> Tag-Mitwirkender <p> Tag-Manager <p> Tag Reader <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Warnungen verwalten|
|**Sicherheitsoperator**|Mitglieder können Sicherheitswarnungen verwalten und auch Berichte und Einstellungen von Sicherheitsfeatures anzeigen.|Compliance-Suche <p> Benachrichtigungen verwalten <p> Sicherheitsleseberechtigter <p> Tag-Mitwirkender <p> Tag Reader <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Warnungen verwalten|
|**Sicherheitsleseberechtigter**|Mitglieder haben schreibgeschützten Zugriff auf eine Reihe von Sicherheitsfeatures von Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health und Security & Compliance Center. <p> Standardmäßig scheint diese Rollengruppe keine Mitglieder zu haben. Die Rolle "Sicherheitsleseberechtigter" von Azure Active Directory wird dieser Rollengruppe zugewiesen. Daher erbt diese Rollengruppe die Funktionen und die Mitgliedschaft der Rolle "Sicherheitsleseberechtigter" von Azure Active Directory. <p> Um Berechtigungen zentral zu verwalten, fügen Sie Gruppenmitglieder im Azure Active Directory Admin Center hinzu und entfernen sie. Weitere Informationen finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Wenn Sie diese Rollengruppe im Security & Compliance Center (Mitgliedschaft oder Rollen) bearbeiten, gelten diese Änderungen nur für das Security & Compliance Center und nicht für andere Dienste.|Sicherheitsleseberechtigter <p> Leseberechtigter für Vertraulichkeitsbezeichnungen <p> Tag Reader <p> View-Only Geräteverwaltung <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Warnungen verwalten|
|**Dienstüberprüfungsbenutzer**|Mitglieder können im Security & Compliance Center auf den Abschnitt "Service Assurance" zugreifen. Service Assurance stellt Berichte und Dokumente bereit, die die Sicherheitspraktiken von Microsoft für Kundendaten beschreiben, die in Microsoft 365 gespeichert sind. Außerdem werden unabhängige Überwachungsberichte von Drittanbietern zu Microsoft 365 bereitgestellt. Weitere Informationen finden Sie unter ["Dienstsicherung" im Security & Compliance Center.](../../compliance/service-assurance.md)|Service Assurance-Ansicht|
|**Aufsichtsüberprüfung**|Mitglieder können die Richtlinien erstellen und verwalten, die definieren, welche Kommunikation in einer Organisation einer Überprüfung unterliegt. Weitere Informationen finden Sie unter [Konfigurieren von Richtlinien für die Kommunikationscompliance für Ihre Organisation.](../../compliance/communication-compliance-configure.md)|Administrator der Aufsichtsüberprüfung|
|

> [!NOTE]
> <sup>1</sup> Diese Rollengruppe weist Mitgliedern nicht die Berechtigungen zu, die zum Durchsuchen des Überwachungsprotokolls oder zum Verwenden von Berichten erforderlich sind, die Exchange Daten enthalten können, z. B. DLP oder Defender für Office 365 Berichte. Um das Überwachungsprotokoll zu durchsuchen oder alle Berichte anzuzeigen, müssen einem Benutzer Berechtigungen in Exchange Online zugewiesen werden. Der Grund dafür ist, dass es sich bei dem zugrundeliegenden Cmdlet, das für die Durchsuchung des Überwachungsprotokolls verwendet wird, um ein Exchange Online-Cmdlet handelt. Globale Administratoren können das Überwachungsprotokoll durchsuchen und alle Berichte anzeigen, da sie automatisch als Mitglieder der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzugefügt werden. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

## <a name="roles-in-the-security--compliance-center"></a>Rollen im Security & Compliance Center

In der folgenden Tabelle sind die verfügbaren Rollen und Rollengruppen aufgeführt, denen sie standardmäßig zugewiesen sind.

Beachten Sie, dass die folgenden Rollen der Rollengruppe "Organisationsverwaltung" standardmäßig nicht zugewiesen sind:

- Administrator des Angriffssimulators
- Autor der Angriffssimulatornutzlast
- Kommunikation
- Kommunikationscompliance-Administrator
- Analyse der Kommunikationscompliance
- Kommunikationscompliance-Fallmanagement
- Untersuchung der Kommunikationscompliance
- Kommunikationscompliance Viewer
- Compliance-Manager-Verwaltung
- Compliance-Manager-Bewertung
- Compliance-Manager-Beitrag
- Compliance-Manager-Leser
- Verwahrer
- Inhaltsanzeige für Datenklassifizierung
- Feedbackanbieter für Datenklassifizierung
- Feedbackprüfer zur Datenklassifizierung
- Datenklassifizierungslistenanzeige
- Dispositionsverwaltung
- Exportieren
- Administrator für Insider-Risikomanagement
- Insider-Risikomanagementanalyse
- Insider-Risikomanagement-Überwachung
- Untersuchung des Insider-Risikomanagements
- Permanenter Beitrag zum Insider-Risikomanagement
- Temporärer Beitrag zum Insider-Risikomanagement
- Vorschau
- Überprüfung
- RMS Decrypt
- Administrator der Aufsichtsüberprüfung

<br>

****

|Rolle|Beschreibung|Standardmäßige Rollengruppenzuweisungen|
|---|---|---|
|**Administrator des Angriffssimulators**|Wird verwendet, um alle Aspekte von Angriffssimulationskampagnen zu erstellen und zu verwalten.||
|**Autor der Angriffssimulatornutzlast**|Wird verwendet, um Angriffsnutzlasten zu erstellen und zu verwalten, die vom Angriffssimulatoradministrator bereitgestellt werden können.||
|**Überwachungsprotokolle**|Aktivieren und konfigurieren Sie die Überwachung für die Organisation, zeigen Sie die Überwachungsberichte der Organisation an, und exportieren Sie diese Berichte in eine Datei.|Organisationsverwaltung <p> Sicherheitsadministrator|
|**Fallverwaltung**|Erstellen, Bearbeiten, Löschen und Steuern des Zugriffs auf eDiscovery-Fälle.|Kommunikationscompliance <p> Ermittler der Kommunikationscompliance <p> Complianceadministrator <p>eDiscovery-Manager <p> Insider-Risikomanagement <p> Administratoren des Insider-Risikomanagements <p> Insider-Risikomanagement-Analysten <p> Insider-Risikomanagement-Prüfer <p> Organisationsverwaltung|
|**Kommunikation**|Verwalten Sie die gesamte Kommunikation mit den in einem Advanced eDiscovery Fall identifizierten Verwaltern.  Erstellen Von Aufbewahrungsbenachrichtigungen, Erinnerungen und Eskalationen für die Verwaltung. Verfolgen Sie die Bestätigung von Aufbewahrungsbenachrichtigungen durch verwahrte Personen, und verwalten Sie den Zugriff auf das Verwahrerportal, das von jedem Verwahrer in einem Fall verwendet wird, um die Kommunikation für die Fälle nachzuverfolgen, in denen sie als Verwahrer identifiziert wurden.|eDiscovery-Manager|
|**Kommunikationscompliance-Administrator**|Wird verwendet, um Richtlinien im Kommunikationscompliance-Feature zu verwalten.|Kommunikationscompliance <p> Kommunikationscomplianceadministratoren|
|**Analyse der Kommunikationscompliance**|Wird zur Untersuchung, Behebung der Nachrichtenverstöße in der Kommunikationscompliance-Funktion verwendet. Nachrichtenmetadaten können nur angezeigt werden.|Kommunikationscompliance <p> Kommunikationscomplianceanalysten <p> Ermittler der Kommunikationscompliance|
|**Kommunikationscompliance-Fallmanagement**|Wird für den Zugriff auf Kommunikationscompliancefälle verwendet.|Kommunikationscompliance <p> Kommunikationscomplianceadministratoren <p> Kommunikationscomplianceanalysten <p> Ermittler der Kommunikationscompliance <p> Viewer für kommunikationscompliance|
|**Untersuchung der Kommunikationscompliance**|Wird verwendet, um Nachrichtenverstöße in der Kommunikationscompliance-Funktion zu untersuchen, zu beheben und zu überprüfen. Kann Nachrichtenmetadaten und -nachrichten anzeigen.|Kommunikationscompliance <p> Ermittler der Kommunikationscompliance|
|**Kommunikationscompliance Viewer**|Wird für den Zugriff auf Berichte und Widgets in der Kommunikationscompliance-Funktion verwendet.|Kommunikationscompliance <p> Viewer für kommunikationscompliance|
|**Complianceadministrator**|Anzeigen und Bearbeiten von Einstellungen und Berichten für Compliancefeatures.|Complianceadministrator <p> Compliancedatenadministrator <p> Organisationsverwaltung|
|**Compliance-Manager-Verwaltung**|Verwalten der Erstellung und Änderung von Vorlagen.|Compliance-Manager-Administratoren|
|**Compliance-Manager-Bewertung**|Erstellen Sie Bewertungen, implementieren Sie Verbesserungsmaßnahmen, und aktualisieren Sie den Teststatus für Verbesserungsmaßnahmen.|Compliance-Manager-Administratoren <p> Compliance-Manager-Prüfer|
|**Compliance-Manager-Beitrag**|Erstellen Sie Bewertungen, und führen Sie Arbeit aus, um Verbesserungsmaßnahmen zu implementieren.|Compliance-Manager-Administratoren <p> Compliance-Manager-Prüfer <p> Compliance-Manager-Mitwirkende|
|**Compliance Manager Reader**|Zeigen Sie alle Compliance-Manager-Inhalte mit Ausnahme von Administratorfunktionen an.|Compliance-Manager-Administratoren <p> Compliance-Manager-Prüfer <p> Compliance-Manager-Mitwirkende <p> Compliance-Manager-Leser|
|**Compliance-Suche**|Führen Sie Suchvorgänge in Postfächern durch, und erhalten Sie eine Schätzung der Ergebnisse.|Complianceadministrator <p> Compliancedatenadministrator <p>eDiscovery-Manager <p> Organisationsverwaltung <p> Sicherheitsoperator|
|**Custodian**|Identifizieren und Verwalten von Verwahrern für Advanced eDiscovery Fälle und Verwenden der Informationen aus Azure Active Directory und anderen Quellen, um Datenquellen zu finden, die mit Verwahrern verknüpft sind. Ordnen Sie in einem Fall andere Datenquellen wie Postfächer, SharePoint Websites und Teams den Verwahrern zu.  Legen Sie eine gesetzliche Aufbewahrungspflicht für die Datenquellen fest, die mit Verwahrern verbunden sind, um Inhalte im Kontext eines Falls beizubehalten.|eDiscovery-Manager|
|**Inhaltsanzeige für Datenklassifizierung**|Anzeigen des direkten Renderings von Dateien im Inhalts-Explorer.|Inhalts-Explorer-Inhaltsanzeige|
|**Feedbackanbieter für Datenklassifizierung**|Ermöglicht das Senden von Feedback an Klassifizierer im Inhalts-Explorer.|Kommunikationscompliance <p> Ermittler der Kommunikationscompliance <p> Complianceadministrator|
|**Feedbackprüfer zur Datenklassifizierung**|Ermöglicht das Überprüfen des Feedbacks von Klassifizierern im Feedback-Explorer.|Complianceadministrator|
|**Datenklassifizierungslistenanzeige**|Zeigen Sie die Liste der Dateien im Inhalts-Explorer an.|Inhalts-Explorer-Listenanzeige|
|**Geräteverwaltung**|Anzeigen und Bearbeiten von Einstellungen und Berichten für Geräteverwaltungsfunktionen.|Complianceadministrator <p> Compliancedatenadministrator <p> Organisationsverwaltung <p> Sicherheitsadministrator|
|**Dispositionsverwaltung**|Steuern von Berechtigungen für den Zugriff auf die manuelle Löschung im Security & Compliance Center.|Complianceadministrator <p> Compliancedatenadministrator <p> Datensatzverwaltung|
|**DLP-Complianceverwaltung**|Anzeigen und Bearbeiten von Einstellungen und Berichten für DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust).|Complianceadministrator <p> Compliancedatenadministrator <p> Organisationsverwaltung <p> Sicherheitsadministrator|
|**Export**|Exportieren Sie Postfach- und Websiteinhalte, die von Suchvorgängen zurückgegeben werden.|eDiscovery-Manager|
|**Hold**|Platzieren Sie Inhalte in Postfächern, Websites und öffentlichen Ordnern in der Warteschleife. Wenn die Aufbewahrung aktiviert ist, wird eine Kopie des Inhalts an einem sicheren Ort gespeichert. Inhaltsbesitzer können weiterhin den ursprünglichen Inhalt ändern oder löschen.|Complianceadministrator <p>eDiscovery-Manager <p> Organisationsverwaltung|
|**IB-Compliance-Management**|Anzeigen, Erstellen, Entfernen, Ändern und Testen von Richtlinien für Informationsbarrieren.|Complianceadministrator <p> Compliancedatenadministrator <p> Organisationsverwaltung <p> Sicherheitsadministrator|
|**Administrator für Insider-Risikomanagement**|Erstellen, Bearbeiten, Löschen und Steuern des Zugriffs auf das Insider-Risikomanagement-Feature.|Insider-Risikomanagement <p> Administratoren des Insider-Risikomanagements|
|**Insider-Risikomanagementanalyse**|Greifen Sie auf alle Warnungen, Fälle und Benachrichtigungsvorlagen des Insider-Risikomanagements zu.|Insider-Risikomanagement <p> Insider-Risikomanagement-Analysten|
|**Insider-Risikomanagement-Überwachung**|Zulassen der Anzeige von Insider-Risiko-Überwachungspfaden.|Auditoren des Insider-Risikomanagements|
|**Untersuchung des Insider-Risikomanagements**|Greifen Sie auf alle Warnungen, Fälle, Benachrichtigungsvorlagen und den Inhalts-Explorer für alle Fälle zu.|Insider-Risikomanagement <p> Insider-Risikomanagement-Prüfer|
|**Permanenter Beitrag zum Insider-Risikomanagement**|Diese Rollengruppe ist sichtbar, wird aber nur von Hintergrunddiensten verwendet.|IRM-Mitwirkende|
|**Temporärer Beitrag zum Insider-Risikomanagement**|Diese Rollengruppe ist sichtbar, wird aber nur von Hintergrunddiensten verwendet.|IRM-Mitwirkende|
|**Benachrichtigungen verwalten**|Anzeigen und Bearbeiten von Einstellungen und Berichten für Warnungen.|Complianceadministrator <p> Compliancedatenadministrator <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator|
|**Organisationskonfiguration**|Ausführen, Anzeigen und Exportieren von Überwachungsberichten und Verwalten von Compliancerichtlinien für DLP, Geräte und Aufbewahrung.|Complianceadministrator <p> Compliancedatenadministrator <p> Organisationsverwaltung|
|**Preview**|Zeigen Sie eine Liste von Elementen an, die von Inhaltssuchen zurückgegeben werden, und öffnen Sie jedes Element aus der Liste, um dessen Inhalt anzuzeigen.|eDiscovery-Manager|
|**Quarantäne**|Ermöglicht das Anzeigen und Freigeben von isolierten E-Mails.|Quarantäneadministrator <p> Sicherheitsadministrator <p> Organisationsverwaltung|
|**RecordManagement**|Anzeigen und Bearbeiten der Konfiguration des Datensatzverwaltungsfeatures.|Complianceadministrator <p> Compliancedatenadministrator <p> Organisationsverwaltung <p> Datensatzverwaltung|
|**Aufbewahrungsverwaltung**|Verwalten von Aufbewahrungsrichtlinien, Aufbewahrungsbezeichnungen und Aufbewahrungsbezeichnungsrichtlinien.|Complianceadministrator <p> Compliancedatenadministrator <p> Organisationsverwaltung <p> Datensatzverwaltung|
|**Überprüfung**|Mit dieser Rolle können Benutzer in Advanced eDiscovery Fällen auf Prüfdateisätze zugreifen. Benutzer, denen diese Rolle zugewiesen ist, können die Liste der Fälle auf der Seite **"eDiscovery > Erweitert"** im Microsoft 365 Compliance Center, in dem sie Mitglieder sind, anzeigen und öffnen. Nachdem der Benutzer auf einen Advanced eDiscovery Fall zugegriffen hat, kann er **Prüfdateisätze** auswählen, um auf Falldaten zuzugreifen. Mit dieser Rolle kann der Benutzer keine Vorschau der Ergebnisse einer Sammlungssuche anzeigen, die dem Fall zugeordnet ist, oder andere Such- oder Fallverwaltungsaufgaben ausführen. Benutzer mit dieser Rolle können nur auf die Daten in einem Prüfdateisatz zugreifen.|eDiscovery-Manager <p> Reviewer|
|**RMS Decrypt**|Entschlüsseln sie RMS-geschützte Inhalte beim Exportieren von Suchergebnissen.|eDiscovery-Manager|
|**Rollenverwaltung**|Verwalten sie die Rollengruppenmitgliedschaft, und erstellen oder löschen Sie benutzerdefinierte Rollengruppen.|Organisationsverwaltung|
|**Suchen und Löschen**|Ermöglicht Es Personen, Daten, die den Kriterien einer Inhaltssuche entsprechen, massenweise zu entfernen.|Organisationsverwaltung|
|**Sicherheitsadministrator**|Anzeigen und Bearbeiten der Konfiguration und der Berichte für Sicherheitsfeatures.|Organisationsverwaltung <p> Sicherheitsadministrator|
|**Sicherheitsleseberechtigter**|Anzeigen der Konfiguration und der Berichte für Sicherheitsfeatures.|Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Administrator für Vertraulichkeitsbezeichnungen**|Vertraulichkeitsbezeichnungen anzeigen, erstellen, ändern und entfernen.|Compliancedatenadministrator <p> Organisationsverwaltung <p> Sicherheitsadministrator|
|**Leseberechtigter für Vertraulichkeitsbezeichnungen**|Anzeigen der Konfiguration und Verwendung von Vertraulichkeitsbezeichnungen.|Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsleseberechtigter|
|**Service Assurance-Ansicht**|Laden Sie die verfügbaren Dokumente aus dem Abschnitt "Service Assurance" herunter. Der Inhalt umfasst unabhängige Überwachung, Compliance-Dokumentation und vertrauensbezogene Anleitungen für die Verwendung Microsoft 365 Features zur Verwaltung gesetzlicher Compliance- und Sicherheitsrisiken.|Globaler Leser <p> Organisationsverwaltung <p> Dienstüberprüfungsbenutzer|
|**Administrator der Aufsichtsüberprüfung**|Verwalten sie aufsichtsrechtliche Prüfrichtlinien, einschließlich der zu überprüfenden Mitteilungen und der Personen, die die Überprüfung durchführen sollten.|Aufsichtsüberprüfung|
|**Tag-Mitwirkender**|Anzeigen und Aktualisieren der Mitgliedschaft vorhandener Benutzertags.|Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator|
|**Tag-Manager**|Anzeigen, Aktualisieren, Erstellen und Löschen von Benutzertags.|Organisationsverwaltung <p> Sicherheitsadministrator|
|**Tag Reader**|Schreibgeschützter Zugriff auf vorhandene Benutzertags.|Sicherheitsleseberechtigter|
|**Überwachungsprotokolle nur anzeigen**|Anzeigen und Exportieren von Überwachungsberichten. Da diese Berichte möglicherweise vertrauliche Informationen enthalten, sollten Sie diese Rolle nur Personen zuweisen, die explizit diese Informationen anzeigen müssen.|Complianceadministrator <p> Compliancedatenadministrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator|
|**Schreibgeschützter Fall**||Kommunikationscompliance <p> Ermittler der Kommunikationscompliance <p> Complianceadministrator <p> Insider-Risikomanagement <p> Administratoren des Insider-Risikomanagements <p> Insider-Risikomanagement-Analysten <p> Insider RiskManagement-Ermittler <p> Organisationsverwaltung|
|**Schreibgeschützte Geräteverwaltung**|Anzeigen der Konfiguration und der Berichte für das Feature "Geräteverwaltung".|Complianceadministrator <p> Compliancedatenadministrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Schreibgeschütztes DLP-Compliance-Management**|Zeigen Sie die Einstellungen und Berichte für DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) an.|Complianceadministrator <p> Compliancedatenadministrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**View-Only IB Compliance Management**|Sehen Sie sich die Konfiguration und die Berichte für das Feature "Informationsbarrieren" an.|Complianceadministrator <p> Compliancedatenadministrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Nur anzeigen Verwalten von Warnungen**|Anzeigen der Konfiguration und der Berichte für das Feature "Warnungen verwalten".|Complianceadministrator <p> Compliancedatenadministrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Schreibgeschützte Empfänger**|Zeigen Sie Informationen zu Benutzern und Gruppen an.|Complianceadministrator <p> Compliancedatenadministrator <p> Globaler Leser <p> MailFlow-Administrator <p> Organisationsverwaltung|
|**Schreibgeschützte Datensatzverwaltung**|Zeigen Sie die Konfiguration des Datensatzverwaltungsfeatures an.|Complianceadministrator <p> Compliancedatenadministrator <p> <p> Globaler Leser <p> Organisationsverwaltung|
|**Schreibgeschützte Aufbewahrungsverwaltung**|Anzeigen der Konfiguration von Aufbewahrungsrichtlinien, Aufbewahrungsbezeichnungen und Aufbewahrungsbezeichnungsrichtlinien.|Complianceadministrator <p> Compliancedatenadministrator <p> Globaler Administrator <p> Organisationsverwaltung|
|
