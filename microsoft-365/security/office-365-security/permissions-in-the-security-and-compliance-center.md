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
ms.openlocfilehash: 316f5ea742684a18c6ab531843cc4fef85d74896
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150219"
---
# <a name="permissions-in-the-security--compliance-center"></a>Berechtigungen im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Mit dem Security & Compliance Center können Sie Personen, die Complianceaufgaben wie Geräteverwaltung, Verhinderung von Datenverlust, eDiscovery, Aufbewahrung und so weiter ausführen, Berechtigungen erteilen. Diese Personen können nur die Aufgaben ausführen, auf die Sie ihnen explizit Zugriff gewähren. Für den Zugriff auf das Security & Compliance Center müssen Benutzer ein globaler Administrator oder Ein mitglied einer oder mehreren Security & Compliance Center-Rollengruppen sein.

Berechtigungen im Security & Compliance Center basieren auf dem Modell der rollenbasierten Zugriffssteuerung (RBAC). RbAC ist das gleiche Berechtigungsmodell, das auch von Exchange verwendet wird. Wenn Sie also mit Exchange vertraut sind, ist das Gewähren von Berechtigungen im Security & Compliance Center sehr ähnlich. Es ist jedoch wichtig zu beachten, dass die Mitgliedschaft oder Berechtigungen von Exchange-Rollengruppen und & Security & Compliance Center nicht gemeinsam sind. Zwar verfügen beide über eine Rollengruppe "Organisationsverwaltung", sie sind jedoch nicht identisch. Die erteilten Berechtigungen und die Mitglieder der Rollengruppen sind verschieden. Unten finden Sie eine Liste der & Compliance Center-Rollengruppen.

![Berechtigungsseite im Security & Compliance Center](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Beziehung zwischen Mitgliedern, Rollen und Rollengruppen

Eine **Rolle** gewährt Berechtigungen zum Ausführen einer Reihe von Aufgaben. Beispielsweise berechtigt die Rolle "Fallmanagement" Personen zum Arbeiten mit eDiscovery-Fällen.

Eine **Rollengruppe ist** ein Satz von Rollen, mit dem Personen ihre Aufgaben im Security & Compliance Center übernehmen können. Die Rollengruppe "Complianceadministrator" umfasst beispielsweise (neben anderen Rollen) die Rollen für die Fallverwaltung, die Inhaltssuche und die Organisationskonfiguration (sowie andere), da ein Complianceadministrator die Berechtigungen für diese Aufgaben benötigt.

Das Security & Compliance Center enthält Standard-Rollengruppen für die gängigsten Aufgaben und Funktionen, die Sie zum Zuweisen von Personen benötigen. Es wird empfohlen, einzelne Benutzer einfach **als Mitglieder zu** den Standard-Rollengruppen hinzufügen.

![Diagramm mit der Beziehung von Rollengruppen zu Rollen und Mitgliedern](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Für die Verwendung von Features im Security & Compliance Center benötigte Berechtigungen

In der folgenden Tabelle sind die Standardrollengruppen aufgeführt, die im Security & Compliance Center verfügbar sind, sowie die Rollen, die den Rollengruppen standardmäßig zugewiesen sind. Um einem Benutzer Berechtigungen zum Ausführen einer Complianceaufgabe zu erteilen, fügen Sie sie der entsprechenden Rollengruppe "Security & Compliance Center" hinzu.

Durch das Verwalten von Berechtigungen im Security & Compliance Center erhalten Benutzer nur Zugriff auf die Compliancefeatures, die im Security & Compliance Center selbst verfügbar sind. Wenn Sie Berechtigungen für andere Kompatibilitätsfeatures erteilen möchten, die sich nicht im Security & Compliance Center befinden, z. B. Exchange-Nachrichtenflussregeln (auch als Transportregeln bezeichnet), müssen Sie das Exchange Admin Center verwenden.

Informationen zum Gewähren des Zugriffs auf das Security & Compliance Center finden Sie unter "Benutzern Zugriff auf [Das Microsoft 365 Compliance Admin Center gewähren".](grant-access-to-the-security-and-compliance-center.md)

> [!NOTE]
> Um die Registerkarte **"Berechtigungen"** im Security & Compliance Center anzeigen zu können, müssen Sie Administrator sein. Insbesondere muss Ihnen die  Rolle "Rollenverwaltung" zugewiesen werden,  und diese Rolle wird standardmäßig nur der Rollengruppe "Organisationsverwaltung" im Security & Compliance Center zugewiesen. Darüber hinaus können **Benutzer mit der** Rolle "Rollenverwaltung" Rollengruppen anzeigen, erstellen und ändern.

<br><br>

****

|Rollengruppe|Beschreibung|Zugewiesene Standardrollen|
|---|---|---|
|**Kommunikationskonformität**|Bietet Berechtigungen für alle Kommunikationskonformitätsrollen: Administrator, Analyst, Ermittler und Viewer.|Fallverwaltung <p> Kommunikationskonformitätsadministrator <p> Analyse der Kommunikationskonformität <p> Kommunikationskonformitätsfallverwaltung <p> Untersuchung der Kommunikationskonformität <p> Kommunikations-Compliance-Viewer <p> Datenklassifizierungsfeedbackanbieter <p> View-Only Fall|
|**Kommunikationskonformitätsadministratoren**|Administratoren der Kommunikationskonformität, die Richtlinien erstellen/bearbeiten und globale Einstellungen definieren kann.|Kommunikationskonformitätsadministrator <p> Kommunikationskonformitätsfallverwaltung|
|**Kommunikations-Compliance-Analysten**|Analysten der Kommunikationskonformität, die Richtlinienkonformität untersuchen, Nachrichtenmetadaten anzeigen und Abhilfemaßnahmen ergreifen können.|Analyse der Kommunikationskonformität <p> Kommunikationskonformitätsfallverwaltung|
|**Kommunikations-Compliance-Ermittler**|Analysten der Kommunikationskonformität, die Richtlinienkonformität untersuchen, Nachrichteninhalte anzeigen und Abhilfemaßnahmen ergreifen können.|Fallverwaltung <p> Analyse der Kommunikationskonformität <p> Kommunikationskonformitätsfallverwaltung <p> Untersuchung der Kommunikationskonformität <p> Datenklassifizierungsfeedbackanbieter <p> View-Only Fall|
|**Kommunikations-Compliance-Viewer**|Anzeige der Kommunikationskonformität, die auf die verfügbaren Berichte und Widgets zugreifen kann.|Kommunikationskonformitätsfallverwaltung <p> Kommunikations-Compliance-Viewer|
|**Kompatibilitätsadministrator**<sup>1</sup>|Mitglieder können Einstellungen für geräteverwaltung, Verhinderung von Datenverlust, Berichte und Aufbewahrung verwalten.|Fallverwaltung <p> Complianceadministrator <p> Compliance-Suche <p> Datenklassifizierungsfeedbackanbieter <p> Datenklassifizierungsfeedback reviewer <p> Geräteverwaltung <p> Dispositionsverwaltung <p> Verwaltung der DLP-Compliance <p> Hold <p> IB-Compliance-Management <p> Benachrichtigungen verwalten <p> Organisationskonfiguration <p> RecordManagement <p> Aufbewahrungsverwaltung <p> Überwachungsprotokolle nur anzeigen <p> View-Only Fall <p> View-Only Geräteverwaltung <p> View-Only von DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Verwalten von Warnungen <p> Schreibgeschützte Empfänger <p> View-Only Datensatzverwaltung <p> View-Only Der Aufbewahrungsverwaltung|
|**Kompatibilitätsdatenadministrator**|Mitglieder können Einstellungen für Geräteverwaltung, Datenschutz, Verhinderung von Datenverlust, Berichte und Aufbewahrung verwalten.|Complianceadministrator <p> Compliance-Suche <p> Geräteverwaltung <p> Verwaltung der DLP-Compliance <p> Dispositionsverwaltung <p> IB-Compliance-Management <p> Benachrichtigungen verwalten <p> Organisationskonfiguration <p> RecordManagement <p> Aufbewahrungsverwaltung <p> Administrator für Vertraulichkeitsbezeichnungen <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only von DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Verwalten von Warnungen <p> Schreibgeschützte Empfänger <p> View-Only Datensatzverwaltung <p> View-Only Der Aufbewahrungsverwaltung|
|**Compliance-Manager-Administratoren**|Verwalten der Erstellung und Änderung von Vorlagen.|Verwaltung des Compliance-Managers <p> Compliance-Manager-Bewertung <p> Compliance-Manager-Beitrag <p> Compliance-Manager-Leser|
|**Compliance-Manager-Assessoren**|Erstellen Sie Bewertungen, implementieren Sie Verbesserungsmaßnahmen, und aktualisieren Sie den Teststatus für Verbesserungsmaßnahmen.|Compliance-Manager-Bewertung <p> Compliance-Manager-Beitrag <p> Compliance-Manager-Leser|
|**Mitwirkende im Compliance-Manager**|Erstellen Sie Bewertungen, und führen Sie Arbeit zur Implementierung von Verbesserungsmaßnahmen aus.|Compliance-Manager-Beitrag <p> Compliance-Manager-Leser|
|**Compliance-Manager-Leser**|Alle Inhalte des Compliance-Managers anzeigen, mit Ausnahme von Administratorfunktionen.|Compliance-Manager-Leser|
|**Inhalts-Explorer-Inhaltsanzeige**|Zeigen Sie die Inhaltsdateien im Inhalts-Explorer an.|Inhaltsanzeige für die Datenklassifizierung|
|**Inhalts-Explorer-Listenanzeige**|Alle Elemente im Inhalts-Explorer nur im Listenformat anzeigen.|Datenklassifizierungslistenanzeige|
|**eDiscovery-Manager**|Mitglieder können Suchvorgänge durchführen und Postfächer, SharePoint Online-Websites und OneDrive for Business-Orte im In-Situ-Speicher platzieren. Mitglieder können auch eDiscovery-Fälle erstellen und verwalten, Mitglieder zu einem Fall hinzufügen und entfernen, Inhaltssuchen erstellen und bearbeiten, die einem Fall zugeordnet sind, und auf Falldaten in Advanced eDiscovery zugreifen. <p> Ein eDiscovery-Administrator ist Mitglied der Rollengruppe "eDiscovery-Manager", der zusätzliche Berechtigungen zugewiesen wurden. Zusätzlich zu den Aufgaben, die ein eDiscovery-Manager ausführen kann, kann ein eDiscovery-Administrator:<ul><li>Alle eDiscovery-Fälle in der Organisation anzeigen.</li><li>Verwalten von eDiscovery-Fällen, nachdem sie sich selbst als Fallmitglied hinzugefügt haben.</li></ul> <p> Der Hauptunterschied zwischen einem eDiscovery-Manager und einem eDiscovery-Administrator besteht in dem, dass ein eDiscovery-Administrator auf alle Fälle zugreifen kann, die auf der Seite **"eDiscovery-Fälle"** im Security & Compliance Center aufgeführt sind. Ein eDiscovery-Manager kann nur auf die von ihnen erstellten Fälle oder Fälle zugreifen, in denen sie Mitglied sind. Weitere Informationen zum Festlegen eines eDiscovery-Administrators finden Sie unter ["Zuweisen von eDiscovery-Berechtigungen" im Security & Compliance Center.](../../compliance/assign-ediscovery-permissions.md)|Fallverwaltung <p> Kommunikation <p> Compliance-Suche <p> Custodian <p> Exportieren <p> Hold <p> Vorschau <p> Überprüfung <p> RMS Decrypt|
|**Globaler Leser**|Mitglieder haben schreibgeschützten Zugriff auf Berichte, Warnungen und können alle Konfigurationen und Einstellungen anzeigen.<p> Der Hauptunterschied zwischen "Globaler Leser" und "Sicherheitsleseprogramm" besteht in dem Zugriff auf Konfiguration **und Einstellungen durch einen globalen Leser.**|Sicherheitsleseberechtigter <p> Leser von Vertraulichkeitsbezeichnungen <p> Service Assurance View <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only von DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Verwalten von Warnungen <p> Schreibgeschützte Empfänger <p> View-Only Datensatzverwaltung <p> View-Only Der Aufbewahrungsverwaltung|
|**Insider Risk Management**|Verwenden Sie diese Rollengruppe zum Verwalten des Risikomanagements für Ihr Unternehmen in einer einzigen Gruppe. Wenn Sie alle Benutzerkonten für designierte Administratoren, Analytiker und Prüfer hinzufügen, können Sie Berechtigungen für das Insider-Risikomanagement in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für Insider-Risikomanagement. Dies ist die einfachste Möglichkeit, den Einstieg in das Insider-Risikomanagement schnell zu finden und eignet sich gut für Unternehmen, die keine separaten Berechtigungen benötigen, die für getrennte Benutzergruppen definiert sind.|Fallverwaltung <p> Administrator des Insider-Risikomanagements <p> Analyse des Insider-Risikomanagements <p> Untersuchung des Insider-Risikomanagements <p> View-Only Fall|
|**Administratoren des Insider-Risikomanagements**|Verwenden Sie diese Rollengruppe, um zunächst das Insiderrisikomanagement zu konfigurieren und später Insider-Risikoadministratoren in eine definierte Gruppe zu untergtrennen. Benutzer in dieser Rollengruppe können Verwaltungsrichtlinien, globale Einstellungen und Rollengruppenzuweisungen für Insiderrisiken erstellen, lesen, aktualisieren und löschen.|Fallverwaltung <p> Administrator des Insider-Risikomanagements <p> View-Only Fall|
|**Insider-Risikomanagement-Analysten**|Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Analysten im Falle eines Insiderrisikos fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungs-, Falll- und Benachrichtigungsvorlagen für Insiderrisiken zugreifen. Sie könne nicht auf den Inhalts-Explorer für Insider-Risiken zugreifen.|Fallverwaltung <p> Analyse des Insider-Risikomanagements <p> View-Only Fall|
|**Insider-Risikomanagement-Auditoren**|Auditoren des Insider-Risikomanagements, die die Überwachungsprotokolle von Aktionen anzeigen können, die von Analysten, Ermittlern und Administratoren ausgeführt wurden.|Insider Risk Management Audit|
|**Insider-Risikomanagement-Prüfer**|Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Datenprüfer für Insiderrisiken fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungs-, Falll- und Benachrichtigungsvorlagen für Insiderrisiken sowie auf den Inhalts-Explorer für alle Fälle zugreifen.|Fallverwaltung <p> Untersuchung des Insider-Risikomanagements <p> View-Only Fall|
|**IRM Contributors**|Diese Rollengruppe ist sichtbar, wird jedoch nur von Hintergrunddiensten verwendet.|Dauerhafter Beitrag des Insider-Risikomanagements <p> Temporärer Beitrag für das Insider-Risikomanagement|
|**MailFlow Administrator**|Mitglieder können Einblicke und Berichte zum Nachrichtenfluss im Security & Compliance Center überwachen und anzeigen. Globale Administratoren können dieser Gruppe normale Benutzer hinzufügen, aber wenn der Benutzer kein Mitglied der Gruppe "Exchange-Administrator" ist, hat der Benutzer keinen Zugriff auf Exchange-Administratoraufgaben.|Schreibgeschützte Empfänger|
|**Organisationsverwaltung**<sup>1</sup>|Mitglieder können Berechtigungen für den Zugriff auf Features im Security & Compliance Center steuern und auch Einstellungen für Geräteverwaltung, Verhinderung von Datenverlust, Berichte und Aufbewahrung verwalten. <p> Benutzer, die keine globalen Administratoren sind, müssen Exchange-Administratoren sein, um Geräte, die von Basic Mobility and Security für Microsoft 365 (früher als Mobile Device Management oder MDM bekannt) verwaltet werden, ein- und zu nutzen. <p> Globale Administratoren werden automatisch als Mitglieder dieser Rollengruppe hinzugefügt.|Überwachungsprotokolle <p> Fallverwaltung <p> Complianceadministrator <p> Compliance-Suche <p> Geräteverwaltung <p> Verwaltung der DLP-Compliance <p> Hold <p> IB-Compliance-Management <p> Benachrichtigungen verwalten <p> Organisationskonfiguration <p> Quarantine <p> RecordManagement <p> Aufbewahrungsverwaltung <p> Rollenverwaltung <p> Suchen und Löschen <p> Sicherheitsadministrator <p> Sicherheitsleseberechtigter <p> Administrator für Vertraulichkeitsbezeichnungen <p> Leser von Vertraulichkeitsbezeichnungen <p> Service Assurance View <p> Mitwirkender von Tags <p> Tag Manager <p> Tag Reader <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only von DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Fall <p> View-Only Verwalten von Warnungen <p> Schreibgeschützte Empfänger <p> View-Only Datensatzverwaltung <p> View-Only Der Aufbewahrungsverwaltung|
|**Quarantäneadministrator**|Mitglieder können auf alle Quarantäneaktionen zugreifen. Weitere Informationen finden Sie unter ["Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP"](manage-quarantined-messages-and-files.md)|Quarantine|
|**Datensatzverwaltung**|Mitglieder können alle Aspekte der Datensatzverwaltung konfigurieren, einschließlich Aufbewahrungsbezeichnungen und Dispositionsüberprüfungen.|Dispositionsverwaltung <p> RecordManagement <p> Aufbewahrungsverwaltung|
|**Reviewer**|Mitglieder können in Advanced [eDiscovery-Fällen auf Überprüfungssätze](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) zugreifen. Mitglieder dieser Rollengruppe können die Liste der Fälle auf der **Seite "eDiscovery > Erweitert"** im Microsoft 365 Compliance Center anzeigen und öffnen, in dem sie Mitglied sind. Nachdem der Benutzer auf einen Advanced eDiscovery-Fall zugegriffen hat, kann er Überprüfungssätze für **den** Zugriff auf Falldaten auswählen. Mit dieser Rolle kann der Benutzer keine Vorschau der Ergebnisse einer Sammlungssuche anzeigen, die dem Fall zugeordnet ist, oder andere Such- oder Fallverwaltungsaufgaben ausführen. Mitglieder dieser Rollengruppe können nur auf die Daten in einem Überprüfungssatz zugreifen.|Überprüfung|
|**Sicherheitsadministrator**|Mitglieder haben Zugriff auf eine Reihe von Sicherheitsfunktionen wie Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health und Security & Compliance Center. <p> Standardmäßig scheint diese Rollengruppe keine Mitglieder zu haben. Die Rolle "Sicherheitsadministrator" aus Azure Active Directory wird dieser Rollengruppe jedoch zugewiesen. Daher erbt diese Rollengruppe die Funktionen und die Mitgliedschaft der Rolle "Sicherheitsadministrator" von Azure Active Directory. <p> Um Berechtigungen zentral zu verwalten, fügen Sie Gruppenmitglieder im Azure Active Directory Admin Center hinzu und entfernen sie. Weitere Informationen finden Sie unter [Administrator-Rollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Wenn Sie diese Rollengruppe im Security & Compliance Center (Mitgliedschaft oder Rollen) bearbeiten, gelten diese Änderungen nur für das Security & Compliance Center und nicht für andere Dienste. <p> Diese Rollengruppe umfasst alle schreibgeschützten Berechtigungen der Rolle "Sicherheitsleseprogramm" sowie eine Reihe zusätzlicher Administratorberechtigungen für die gleichen Dienste: Azure Information Protection, Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health und Security & Compliance Center.|Überwachungsprotokolle <p> Geräteverwaltung <p> Verwaltung der DLP-Compliance <p> IB-Compliance-Management <p> Benachrichtigungen verwalten <p> Quarantine <p> Sicherheitsadministrator <p> Administrator für Vertraulichkeitsbezeichnungen <p> Mitwirkender von Tags <p> Tag Manager <p> Tag Reader <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only von DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Verwalten von Warnungen|
|**Sicherheitsoperator**|Mitglieder können Sicherheitswarnungen verwalten und auch Berichte und Einstellungen von Sicherheitsfeatures anzeigen.|Compliance-Suche <p> Benachrichtigungen verwalten <p> Sicherheitsleseberechtigter <p> Mitwirkender von Tags <p> Tag Reader <p> Überwachungsprotokolle nur anzeigen <p> View-Only Geräteverwaltung <p> View-Only von DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Verwalten von Warnungen|
|**Sicherheitsleseprogramm**|Mitglieder haben schreibgeschützten Zugriff auf eine Reihe von Sicherheitsfeatures wie Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health und Security & Compliance Center. <p> Standardmäßig scheint diese Rollengruppe keine Mitglieder zu haben. Die Rolle "Sicherheitsleseprogramm" aus Azure Active Directory wird dieser Rollengruppe jedoch zugewiesen. Daher erbt diese Rollengruppe die Funktionen und die Mitgliedschaft der Rolle "Sicherheitsleseprogramm" von Azure Active Directory. <p> Um Berechtigungen zentral zu verwalten, fügen Sie Gruppenmitglieder im Azure Active Directory Admin Center hinzu und entfernen sie. Weitere Informationen finden Sie unter [Administrator-Rollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Wenn Sie diese Rollengruppe im Security & Compliance Center (Mitgliedschaft oder Rollen) bearbeiten, gelten diese Änderungen nur für das Security & Compliance Center und nicht für andere Dienste.|Sicherheitsleseberechtigter <p> Leser von Vertraulichkeitsbezeichnungen <p> Tag Reader <p> View-Only Geräteverwaltung <p> View-Only von DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Verwalten von Warnungen|
|**Dienstüberprüfungsbenutzer**|Mitglieder können auf den Abschnitt "Service Assurance" im Security & Compliance Center zugreifen. Service Assurance stellt Berichte und Dokumente zur Beschreibung der Sicherheitspraktiken von Microsoft für Kundendaten zur Verfügung, die in Microsoft 365 gespeichert sind. Darüber hinaus werden unabhängige Prüfungsberichte von Drittanbietern zu Microsoft 365 erstellt. Weitere Informationen finden Sie unter [Service Assurance im Security & Compliance Center.](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)|Service Assurance View|
|**Aufsichtsüberprüfung**|Mitglieder können die Richtlinien erstellen und verwalten, die definieren, welche Kommunikation in einer Organisation einer Überprüfung unterliegt. Weitere Informationen finden Sie unter ["Konfigurieren von Kommunikationskonformitätsrichtlinien für Ihre Organisation".](../../compliance/communication-compliance-configure.md)|Aufsichtsüberprüfungsadministrator|
|

> [!NOTE]
> <sup>1</sup> Diese Rollengruppe weist Mitgliedern nicht die berechtigungen zu, die zum Durchsuchen des Überwachungsprotokolls oder zum Verwenden von Berichten erforderlich sind, die Möglicherweise Exchange-Daten enthalten, z. B. DLP- oder Defender für Office 365-Berichte. Zum Durchsuchen des Überwachungsprotokolls oder zum Anzeigen aller Berichte müssen einem Benutzer Berechtigungen in Exchange Online zugewiesen werden. Der Grund dafür ist, dass es sich bei dem zugrundeliegenden Cmdlet, das für die Durchsuchung des Überwachungsprotokolls verwendet wird, um ein Exchange Online-Cmdlet handelt. Globale Administratoren können das Überwachungsprotokoll durchsuchen und alle Berichte anzeigen, da sie automatisch als Mitglieder der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzugefügt werden. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)im Security & Compliance Center.

## <a name="roles-in-the-security--compliance-center"></a>Rollen im Security & Compliance Center

In der folgenden Tabelle sind die verfügbaren Rollen und rollengruppen aufgeführt, denen sie standardmäßig zugewiesen sind.

Beachten Sie, dass die folgenden Rollen nicht standardmäßig der Rollengruppe "Organisationsverwaltung" zugewiesen sind:

- Attack Simulator Admin
- Autor der Nutzlast des Angriffssimulators
- Kommunikation
- Kommunikationskonformitätsadministrator
- Analyse der Kommunikationskonformität
- Kommunikationskonformitätsfallverwaltung
- Untersuchung der Kommunikationskonformität
- Kommunikations-Compliance-Viewer
- Verwaltung des Compliance-Managers
- Compliance-Manager-Bewertung
- Compliance-Manager-Beitrag
- Compliance-Manager-Leser
- Custodian
- Inhaltsanzeige für die Datenklassifizierung
- Datenklassifizierungsfeedbackanbieter
- Datenklassifizierungsfeedback reviewer
- Datenklassifizierungslistenanzeige
- Dispositionsverwaltung
- Exportieren
- Administrator des Insider-Risikomanagements
- Analyse des Insider-Risikomanagements
- Insider Risk Management Audit
- Untersuchung des Insider-Risikomanagements
- Dauerhafter Beitrag des Insider-Risikomanagements
- Temporärer Beitrag für das Insider-Risikomanagement
- Vorschau
- Überprüfung
- RMS Decrypt
- Aufsichtsüberprüfungsadministrator

<br><br>

****

|Rolle|Beschreibung|Standardzuweisungen für Rollengruppen|
|---|---|---|
|**Attack Simulator Admin**|Wird verwendet, um alle Aspekte von Angriffssimulationskampagnen zu erstellen und zu verwalten.||
|**Autor der Nutzlast des Angriffssimulators**|Wird verwendet, um Angriffsnutzlasten zu erstellen und zu verwalten, die vom Administrator des Angriffssimulators bereitgestellt werden können.||
|**Überwachungsprotokolle**|Aktivieren und konfigurieren Sie die Überwachung für die Organisation, zeigen Sie die Überwachungsberichte der Organisation an, und exportieren Sie diese Berichte dann in eine Datei.|Organisationsverwaltung <p> Sicherheitsadministrator|
|**Fallverwaltung**|Erstellen, Bearbeiten, Löschen und Steuern des Zugriffs auf eDiscovery-Fälle.|Kommunikationscompliance <p> Kommunikations-Compliance-Ermittler <p> Complianceadministrator <p>eDiscovery-Manager <p> Insider-Risikomanagement <p> Administratoren des Insider-Risikomanagements <p> Insider-Risikomanagement-Analysten <p> Insider-Risikomanagement-Prüfer <p> Organisationsverwaltung|
|**Kommunikation**|Verwalten Sie die gesamte Kommunikation mit den in einem Advanced eDiscovery-Fall identifizierten Verwahrern.  Erstellen Sie Haltebenachrichtigungen, Halten von Erinnerungen und Eskalationen an die Verwaltung. Verfolgen Sie die Bestätigung von Benachrichtigungen über das Halterecht, und verwalten Sie den Zugriff auf das Verwahrerportal, das von jedem Verwahrer in einem Fall verwendet wird, um die Kommunikation für fälle nachverfolgt zu werden, in denen sie als Verwahrer identifiziert wurden.|eDiscovery-Manager|
|**Kommunikationskonformitätsadministrator**|Wird zum Verwalten von Richtlinien im Feature "Kommunikationskonformität" verwendet.|Kommunikationscompliance <p> Kommunikationskonformitätsadministratoren|
|**Analyse der Kommunikationskonformität**|Wird verwendet, um Untersuchungen und Korrekturen der Nachrichtenverstöße im Feature "Kommunikationskonformität" durchzuführen. Kann nur Nachrichtenmetadaten anzeigen.|Kommunikationscompliance <p> Kommunikations-Compliance-Analysten <p> Kommunikations-Compliance-Ermittler|
|**Kommunikationskonformitätsfallverwaltung**|Wird für den Zugriff auf Kommunikationskonformitätsfälle verwendet.|Kommunikationscompliance <p> Kommunikationskonformitätsadministratoren <p> Kommunikations-Compliance-Analysten <p> Kommunikations-Compliance-Ermittler <p> Kommunikations-Compliance-Viewer|
|**Untersuchung der Kommunikationskonformität**|Wird verwendet, um Untersuchungen, Korrekturen und Überprüfungen von Nachrichtenverstößen im Feature "Kommunikationskonformität" durchzuführen. Kann Nachrichtenmetadaten und -nachrichten anzeigen.|Kommunikationscompliance <p> Kommunikations-Compliance-Ermittler|
|**Kommunikations-Compliance-Viewer**|Wird für den Zugriff auf Berichte und Widgets im Feature "Kommunikationskonformität" verwendet.|Kommunikationscompliance <p> Kommunikations-Compliance-Viewer|
|**Complianceadministrator**|Anzeigen und Bearbeiten von Einstellungen und Berichten für Kompatibilitätsfeatures.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Organisationsverwaltung|
|**Verwaltung des Compliance-Managers**|Verwalten der Erstellung und Änderung von Vorlagen.|Compliance-Manager-Administratoren|
|**Compliance-Manager-Bewertung**|Erstellen Sie Bewertungen, implementieren Sie Verbesserungsmaßnahmen, und aktualisieren Sie den Teststatus für Verbesserungsmaßnahmen.|Compliance-Manager-Administratoren <p> Compliance-Manager-Assessoren|
|**Compliance-Manager-Beitrag**|Erstellen Sie Bewertungen, und führen Sie Arbeit zur Implementierung von Verbesserungsmaßnahmen aus.|Compliance-Manager-Administratoren <p> Compliance-Manager-Assessoren <p> Mitwirkende im Compliance-Manager|
|**Compliance Manager Reader**|Alle Inhalte des Compliance-Managers anzeigen, mit Ausnahme von Administratorfunktionen.|Compliance-Manager-Administratoren <p> Compliance-Manager-Assessoren <p> Mitwirkende im Compliance-Manager <p> Compliance-Manager-Leser|
|**Compliance-Suche**|Durchführen von Suchen in allen Postfächern und Erhalten einer Schätzung der Ergebnisse.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p>eDiscovery-Manager <p> Organisationsverwaltung <p> Sicherheitsoperator|
|**Custodian**|Identifizieren und verwalten Sie Verwahrer für Advanced eDiscovery-Fälle, und verwenden Sie die Informationen aus Azure Active Directory und anderen Quellen, um Datenquellen zu finden, die verwahrern zugeordnet sind. Ordnen Sie andere Datenquellen wie Postfächer, SharePoint-Websites und Teams in einem Fall Verwahrern zu.  Setzen Sie die Datenquellen, die Wahrern zugeordnet sind, für die gesetzliche Speicherung ein, um Inhalte im Kontext eines Falls zu erhalten.|eDiscovery-Manager|
|**Inhaltsanzeige für die Datenklassifizierung**|Anzeigen des in-Place-Renderings von Dateien im Inhalts-Explorer.|Inhalts-Explorer-Inhaltsanzeige|
|**Datenklassifizierungsfeedbackanbieter**|Ermöglicht das Bereitstellen von Feedback an Klassifikatoren im Inhalts-Explorer.|Kommunikationscompliance <p> Kommunikations-Compliance-Ermittler <p> Complianceadministrator|
|**Datenklassifizierungsfeedback reviewer**|Ermöglicht die Überprüfung von Feedback von Klassifizierungen im Feedback-Explorer.|Complianceadministrator|
|**Datenklassifizierungslistenanzeige**|Anzeigen der Liste der Dateien im Inhalts-Explorer.|Inhalts-Explorer-Listenanzeige|
|**Geräteverwaltung**|Anzeigen und Bearbeiten von Einstellungen und Berichten für Geräteverwaltungsfeatures.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Organisationsverwaltung <p> Sicherheitsadministrator|
|**Dispositionsverwaltung**|Steuern von Berechtigungen für den Zugriff auf die manuelle Disposition im Security & Compliance Center.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Datensatzverwaltung|
|**Verwaltung der DLP-Compliance**|Anzeigen und Bearbeiten von Einstellungen und Berichten für Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP).|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Organisationsverwaltung <p> Sicherheitsadministrator|
|**Export**|Exportieren von Postfach- und Websiteinhalten, die von Suchbegriffen zurückgegeben werden.|eDiscovery-Manager|
|**Hold**|Platzieren Sie Inhalte in Postfächern, Websites und öffentlichen Ordnern im Archiv. Wenn die Daten aufbewahrt werden, wird eine Kopie des Inhalts an einem sicheren Ort gespeichert. Inhaltsbesitzer können den ursprünglichen Inhalt weiterhin ändern oder löschen.|Complianceadministrator <p>eDiscovery-Manager <p> Organisationsverwaltung|
|**IB-Compliance-Management**|Anzeigen, Erstellen, Entfernen, Ändern und Testen von Richtlinien für Informationsbarrieren.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Organisationsverwaltung <p> Sicherheitsadministrator|
|**Administrator des Insider-Risikomanagements**|Erstellen, Bearbeiten, Löschen und Steuern des Zugriffs auf das Feature "Insider-Risikomanagement".|Insider-Risikomanagement <p> Administratoren des Insider-Risikomanagements|
|**Analyse des Insider-Risikomanagements**|Zugriff auf alle Vorlagen für Insider-Risikomanagement, -fälle und -benachrichtigungen.|Insider-Risikomanagement <p> Insider-Risikomanagement-Analysten|
|**Insider Risk Management Audit**|Zulassen der Anzeige von Insider-Risiko-Überwachungsprotokollen.|Insider-Risikomanagement-Auditoren|
|**Untersuchung des Insider-Risikomanagements**|Zugriff auf alle Warnungen, Fälle, Benachrichtigungsvorlagen und den Inhalts-Explorer für alle Fälle.|Insider-Risikomanagement <p> Insider-Risikomanagement-Prüfer|
|**Dauerhafter Beitrag des Insider-Risikomanagements**|Diese Rollengruppe ist sichtbar, wird jedoch nur von Hintergrunddiensten verwendet.|IRM Contributors|
|**Temporärer Beitrag für das Insider-Risikomanagement**|Diese Rollengruppe ist sichtbar, wird jedoch nur von Hintergrunddiensten verwendet.|IRM Contributors|
|**Benachrichtigungen verwalten**|Anzeigen und Bearbeiten von Einstellungen und Berichten für Warnungen.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator|
|**Organisationskonfiguration**|Ausführen, Anzeigen und Exportieren von Überwachungsberichten und Verwalten von Compliancerichtlinien für DLP, Geräte und Aufbewahrung.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Organisationsverwaltung|
|**Preview**|Zeigen Sie eine Liste von Elementen an, die von Inhaltssuchen zurückgegeben werden, und öffnen Sie jedes Element aus der Liste, um dessen Inhalt anzuzeigen.|eDiscovery-Manager|
|**Quarantäne**|Ermöglicht das Anzeigen und Freigeben von isolierten E-Mails.|Quarantäneadministrator <p> Sicherheitsadministrator <p> Organisationsverwaltung|
|**RecordManagement**|Anzeigen und Bearbeiten der Konfiguration des Datensatzverwaltungsfeatures.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Organisationsverwaltung <p> Datensatzverwaltung|
|**Aufbewahrungsverwaltung**|Verwalten von Aufbewahrungsrichtlinien, Aufbewahrungsbezeichnungen und Aufbewahrungsbezeichnungsrichtlinien.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Organisationsverwaltung <p> Datensatzverwaltung|
|**Überprüfung**|Mit dieser Rolle können Benutzer auf Überprüfungssätze in Advanced eDiscovery-Fällen zugreifen. Benutzer, denen diese Rolle zugewiesen ist, können die Liste der Fälle auf der **Seite "eDiscovery > Erweitert"** im Microsoft 365 Compliance Center anzeigen und öffnen, in dem sie Mitglied sind. Nachdem der Benutzer auf einen Advanced eDiscovery-Fall zugegriffen hat, kann er Überprüfungssätze für **den** Zugriff auf Falldaten auswählen. Mit dieser Rolle kann der Benutzer keine Vorschau der Ergebnisse einer Sammlungssuche anzeigen, die dem Fall zugeordnet ist, oder andere Such- oder Fallverwaltungsaufgaben ausführen. Benutzer mit dieser Rolle können nur auf die Daten in einem Überprüfungssatz zugreifen.|eDiscovery-Manager <p> Reviewer|
|**RMS Decrypt**|Entschlüsseln Sie RMS-geschützte Inhalte beim Exportieren von Suchergebnissen.|eDiscovery-Manager|
|**Rollenverwaltung**|Verwalten sie die Rollengruppenmitgliedschaft, und erstellen oder löschen Sie benutzerdefinierte Rollengruppen.|Organisationsverwaltung|
|**Suchen und Löschen**|Ermöglicht Personen das Massen entfernen von Daten, die den Kriterien einer Inhaltssuche entsprechen.|Organisationsverwaltung|
|**Sicherheitsadministrator**|Anzeigen und Bearbeiten der Konfiguration und der Berichte für Sicherheitsfeatures.|Organisationsverwaltung <p> Sicherheitsadministrator|
|**Sicherheitsleseprogramm**|Zeigen Sie die Konfiguration und Berichte für Sicherheitsfeatures an.|Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Administrator für Vertraulichkeitsbezeichnungen**|Anzeigen, Erstellen, Ändern und Entfernen von Vertraulichkeitsbezeichnungen.|Kompatibilitätsdatenadministrator <p> Organisationsverwaltung <p> Sicherheitsadministrator|
|**Leser von Vertraulichkeitsbezeichnungen**|Anzeigen der Konfiguration und Verwendung von Vertraulichkeitsbezeichnungen.|Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsleseberechtigter|
|**Service Assurance View**|Laden Sie die verfügbaren Dokumente aus dem Abschnitt "Service Assurance" herunter. Der Inhalt umfasst eine unabhängige Überwachung, Compliancedokumentation und vertrauensbezogene Anleitungen für die Verwendung von Microsoft 365-Features zur Verwaltung gesetzlicher Compliance- und Sicherheitsrisiken.|Globaler Leser <p> Organisationsverwaltung <p> Dienstüberprüfungsbenutzer|
|**Aufsichtsüberprüfungsadministrator**|Verwalten von Aufsichtsüberprüfungsrichtlinien, einschließlich der zu überprüfende Mitteilungen und der Personen, die die Überprüfung führen sollten.|Aufsichtsüberprüfung|
|**Mitwirkender von Tags**|Anzeigen und Aktualisieren der Mitgliedschaft vorhandener Benutzertags.|Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator|
|**Tag Manager**|Anzeigen, Aktualisieren, Erstellen und Löschen von Benutzertags.|Organisationsverwaltung <p> Sicherheitsadministrator|
|**Tag Reader**|Schreibgeschützter Zugriff auf vorhandene Benutzertags.|Sicherheitsleseberechtigter|
|**Überwachungsprotokolle nur anzeigen**|Anzeigen und Exportieren von Überwachungsberichten. Da diese Berichte möglicherweise vertrauliche Informationen enthalten, sollten Sie diese Rolle nur Personen zuweisen, die diese Informationen explizit anzeigen müssen.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator|
|**Nur-Ansicht-Fall**||Kommunikationscompliance <p> Kommunikations-Compliance-Ermittler <p> Complianceadministrator <p> Insider-Risikomanagement <p> Administratoren des Insider-Risikomanagements <p> Insider-Risikomanagement-Analysten <p> Insider-RiskManagement-Ermittler <p> Organisationsverwaltung|
|**Nur-Ansicht-Geräteverwaltung**|Zeigen Sie die Konfiguration und Berichte für das Feature "Geräteverwaltung" an.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Nur-Ansicht-DLP-Kompatibilitätsverwaltung**|Anzeigen der Einstellungen und Berichte für Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP).|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Nur-Ansicht-IB-Compliance-Verwaltung**|Zeigen Sie die Konfiguration und Berichte für das Feature "Informationsbarrieren" an.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Warnungen nur anzeigen**|Zeigen Sie die Konfiguration und Berichte für das Feature zum Verwalten von Warnungen an.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Globaler Leser <p> Organisationsverwaltung <p> Sicherheitsadministrator <p> Sicherheitsoperator <p> Sicherheitsleseberechtigter|
|**Schreibgeschützte Empfänger**|Anzeigen von Informationen zu Benutzern und Gruppen.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Globaler Leser <p> MailFlow Administrator <p> Organisationsverwaltung|
|**Nur-Ansicht-Datensatzverwaltung**|Zeigen Sie die Konfiguration des Datensatzverwaltungsfeatures an.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> <p> Globaler Leser <p> Organisationsverwaltung|
|**Aufbewahrungsverwaltung nur anzeigen**|Anzeigen der Konfiguration von Aufbewahrungsrichtlinien, Aufbewahrungsbezeichnungen und Aufbewahrungsbezeichnungsrichtlinien.|Complianceadministrator <p> Kompatibilitätsdatenadministrator <p> Globaler Administrator <p> Organisationsverwaltung|
|
