---
title: Featureberechtigungen in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Erfahren Sie mehr über die Berechtigungen, die für Aufgaben in eigenständigem Exchange Online Protection erforderlich sind
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 212a109c792522270b7e5000747bec950b7f4fe2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926982"
---
# <a name="permissions-in-standalone-eop"></a>Berechtigungen in EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection eigenständig](exchange-online-protection-overview.md)

Eigenständige Exchange Online Protection (EOP) ohne Exchange Online-Postfächer verwendet das Rollenbasierte Zugriffssteuerungsmodell (Role Based Access Control, RBAC) zum einfachen Erteilen von Berechtigungen für Administratoren. Sie können die Berechtigungsfeatures in eigenständigem EOP verwenden, um Ihre neue Organisation schnell in Betrieb zu setzen.

Informationen zum Erteilen von Berechtigungen für Benutzer finden Sie unter [Verwalten von Administratorrollegruppen in EOP](manage-admin-role-group-permissions-in-eop.md).

Weitere Informationen zu Berechtigungen in Microsoft 365 finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="role-based-permissions"></a>Rollenbasierte Berechtigungen

Die Administratorberechtigungen, die Sie Benutzern erteilen, basieren auf Verwaltungsrollen. Eine Verwaltungsrolle definiert die Cmdlets, die für eine Reihe von bestimmten Aufgaben verfügbar sind. Da sowohl das Exchange Admin Center (EAC) als auch die eigenständige EOP PowerShell Cmdlets verwenden, erteilt die Gewährung des Zugriffs auf ein Cmdlet dem Benutzer die Berechtigung, die zugehörigen Aufgaben in der EAC oder in der eigenständigen EOP PowerShell auszuführen. Die Rolle E-Mail-Empfänger definiert beispielsweise die Cmdlets, die zum Ändern von E-Mail-Benutzern erforderlich sind.

In eigenständigen EOP sind administrative Rollen die einzige Art von Verwaltungsrolle, die verfügbar ist (es gibt keine Endbenutzerrollen oder Rollenzuweisungsrichtlinien).

## <a name="role-groups"></a>Rollengruppen

Um das Zuweisen von Rollen zu Benutzern zu erleichtern, verwendet eigenständiges EOP Rollengruppen. Verwaltungsrollen werden Rollengruppen zugewiesen, und die Rollengruppenmitglieder erhalten die Berechtigungen, die den Rollen zugeordnet sind. Anders ausgedrückt: Verwaltungsrollen werden Benutzern nicht direkt zugewiesen. sie sind der Rollengruppe zugewiesen. Mit diesem Modell können Sie vielen Rollengruppenmitgliedern viele Rollen gleichzeitig zuweisen. Rollengruppenmitglieder können E-Mail-Benutzer, E-Mail-aktivierte Sicherheitsgruppen, Benutzer aus dem Microsoft 365 Admin Center und andere Rollengruppen sein.

Die folgende Abbildung zeigt die Beziehung zwischen Benutzern, Rollengruppen und Rollen.

![Rolle, Rollengruppe und Mitglied - Beziehung](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

Die verfügbaren Rollengruppen in eigenständigem EOP werden in der folgenden Tabelle beschrieben.

****

|Rollengruppe|Beschreibung|Zugewiesene Standardrollen|
|---|---|---|
|ComplianceManagement|Konfigurieren und Verwalten von Complianceeinstellungen innerhalb der Organisation, einschließlich Verhinderung von Datenverlust (Data Loss Prevention, DLP), wenn Ihr Abonnement über DLP-Funktionen verfügt. <p> Mitglieder der [Rolle "Complianceadministrator"](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) in Azure AD erhalten automatisch die Berechtigungen dieser Rollengruppe.|Überwachungsprotokolle <p> Complianceverwaltung <p> Verwaltung von Informationsrechten <p> Aufbewahrungsverwaltung <p> Überwachungsprotokolle nur anzeigen <p> Schreibgeschützte Konfiguration <p> Schreibgeschützte Empfänger|
|ContentExplorerContentViewer|Nicht verwendet.|Inhaltsanzeige für die Datenklassifizierung|
|ContentExplorerListViewer|Nicht verwendet.|Datenklassifizierungslistenanzeige|
|HelpDesk|Anzeigen und Verwalten von E-Mail-Benutzern.|Kennwort zurücksetzen <p> Benutzeroptionen <p> Schreibgeschützte Empfänger|
|HygieneManagement|Verwalten von Schutzfunktionen (Antispam, Anschmieren von Schadsoftware usw.).|Transporthygiene <p> Schreibgeschützte Konfiguration <p> Schreibgeschützte Empfänger|
|MailFlowAdministrator|Anzeigen und Verwalten akzeptierter Domänen und Connectors|Remote- und akzeptierte Domänen <p> Schreibgeschützte Empfänger|
|OrganizationManagement|Administratorzugriff auf die gesamte Organisation und die Möglichkeit, nahezu jede Aufgabe auszuführen. <p> Mitglieder der [Rolle "Globaler Administrator"](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) in Azure AD erhalten automatisch die Berechtigungen dieser Rollengruppe. <p> **Wichtig:** Da die Rollengruppe OrganizationManagement eine leistungsstarke Rolle ist, sollten nur Benutzer, die verwaltungstechnische Aufgaben auf Organisationsebene ausführen, Mitglieder dieser Rollengruppe sein.|Antischalware <p> AntiSpam <p> Überwachungsprotokolle <p> Complianceadministrator <p> Dynamische Verteilergruppen <p> Verwaltung von Informationsrechten <p> Erstellen von E-Mail-Empfängern <p> E-Mail-Empfänger <p> Nachrichtenverfolgung <p> Migration <p> Organisationsclientzugriff <p> Organisationskonfiguration <p> Organisations-Transport-Einstellungen <p> Quarantäne <p> Empfängerrichtlinien <p> Remote- und akzeptierte Domänen <p> Kennwort zurücksetzen <p> Aufbewahrungsverwaltung <p> Rollenverwaltung <p> Sicherheitsadministrator <p> Erstellung und Mitgliedschaft von Sicherheitsgruppen <p> Sicherheitsleseberechtigter <p> Vertraulichkeitsbezeichnungsadministrator <p> Aufsicht <p> Transporthygiene <p> Transportregeln <p> Benutzeroptionen <p> View-Only Antischalware <p> View-Only AntiSpam <p> Überwachungsprotokolle nur anzeigen <p> Schreibgeschützte Konfiguration <p> View-Only Quarantäne <p> Schreibgeschützte Empfänger <p> View-Only Threat Intelligence|
|QuarantineAdministrator|Verwalten von isolierten Nachrichten für alle Empfänger.|Quarantäne|
|RecipientManagement|Erstellen, Verwalten und Entfernen von Empfängerobjekten in der Organisation.|Dynamische Verteilergruppen <p> Erstellen von E-Mail-Empfängern <p> E-Mail-Empfänger <p> Nachrichtenverfolgung <p> Migration <p> Empfängerrichtlinien <p> Kennwort zurücksetzen|
|RecordsManagement|Konfigurieren von Compliancefeatures, z. B. Aufbewahrungsrichtlinientags, Nachrichtenklassifikationen und Nachrichtenflussregeln (auch als Transportregeln bekannt).|Nachrichtenverfolgung <p> Aufbewahrungsverwaltung <p> Transportregeln|
|SecurityAdministrator|Konfigurieren Sie alle Aspekte des Schutzes in der Organisation (Antispam, Anschmierung von Schadsoftware, Antis spoofing, Quarantäne usw.). <p> Mitglieder der Rolle ["Sicherheitsadministrator"](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) in Azure AD erhalten automatisch die Berechtigungen dieser Rollengruppe.|Antischalware <p> AntiSpam <p> Überwachungsprotokolle <p> Quarantäne <p> Sicherheitsadministrator <p> Vertraulichkeitsbezeichnungsadministrator <p> View-Only Antischalware <p> View-Only AntiSpam <p> Überwachungsprotokolle nur anzeigen <p> View-Only Quarantäne <p> View-Only Threat Intelligence|
|SecurityReader|Nur-Ansichtszugriff auf alle Aspekte des Schutzes in der Organisation (Antispam, Anschmierung von Schadsoftware, Antis spoofing, Quarantäne usw.). <p> Mitglieder der [Rolle "Security Reader"](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) in Azure AD erhalten automatisch die Berechtigungen dieser Rollengruppe.|Sicherheitsleseberechtigter <p> View-Only Antischalware <p> View-Only AntiSpam <p> View-Only Quarantäne <p> View-Only Threat Intelligence|
|TenantAdmins|Die Mitgliedschaft in dieser Rollengruppe wird dienstübergreifend synchronisiert und zentral verwaltet. Dieser Rollengruppe werden standardmäßig keine Rollen zugewiesen. Sie ist jedoch Mitglied der Rollengruppe Organisationsverwaltung und erbt diese Berechtigungen.|keine|
|ViewOnlyOrganizationManagement|Anzeigen von Empfänger-, Schutz- und Konfigurationsobjekten und deren Eigenschaften in der Organisation.|Complianceadministrator <p> Sicherheitsadministrator <p> Sicherheitsleseberechtigter <p> Vertraulichkeitsbezeichnungsadministrator <p> Schreibgeschützte Konfiguration <p> Schreibgeschützte Empfänger|
|

Wenn Sie in einer kleinen Organisation arbeiten, die nur über wenige Administratoren verfügt, müssen Sie diese Benutzer möglicherweise nur der Rollengruppe "Organisationsverwaltung" hinzufügen, und Sie müssen möglicherweise niemals die anderen Rollengruppen verwenden. Wenn Sie in einer größeren Organisation arbeiten, haben Sie möglicherweise Administratoren, die bestimmte Aufgaben ausführen, z. B. empfängerkonfiguration. In diesen Fällen können Sie der Rollengruppe Empfängerverwaltung einen Administrator und der Rollengruppe Organisationsverwaltung einen weiteren Administrator hinzufügen. Diese Administratoren können dann ihre spezifischen Bereiche verwalten, aber sie verfügen nicht über Berechtigungen zum Verwalten von Bereichen, für die sie nicht verantwortlich sind.

Wenn die integrierten Rollengruppen in Exchange Online nicht für die Aufgabenbereiche Ihrer Administratoren geeignet sind, können Sie Rollengruppen erstellen und Rollen zu diesen Gruppen hinzufügen. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in eigenständigem EOP](manage-admin-role-group-permissions-in-eop.md).

## <a name="roles"></a>Rollen

Die integrierten Rollen, die in eigenständigen EOP verfügbar sind, werden in der folgenden Tabelle beschrieben.

****

|Role**|Beschreibung|Standardzuweisungen für Rollengruppen|
|---|---|---|
|Antischalware|Anzeigen und Ändern der Konfiguration und berichte für Anti-Malware-Features.|OrganizationManagement <p> SecurityAdministrator|
|AntiSpam|Anzeigen und Ändern der Konfiguration und berichte für Antispamfunktionen.|OrganizationManagement <p> SecurityAdministrator|
|Überwachungsprotokolle|Durchsuchen Sie das Administrator-Überwachungsprotokoll, und zeigen Sie die Ergebnisse an.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|Complianceadministrator<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|Inhaltsanzeige für die Datenklassifizierung<sup>\*</sup>||ContentExplorerContentViewer|
|Datenklassifizierungslistenanzeige<sup>\*</sup>||
|Dynamische Verteilergruppen|Erstellen und verwalten Sie alle Verteilergruppen, E-Mail-aktivierten Sicherheitsgruppen und Mitglieder.|OrganizationManagement <p> RecipientManagement|
|Verwaltung von Informationsrechten<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement|
|Erstellen von E-Mail-Empfängern|Erstellen und Entfernen von E-Mail-Benutzern.|OrganizationManagement <p> RecipientManagement|
|E-Mail-Empfänger|Ändern vorhandener E-Mail-Benutzer.|OrganizationManagement <p> RecipientManagement|
|Nachrichtenverfolgung<sup>\*</sup>||OrganizationManagement <p> RecipientManagement <p> Datensatzverwaltung|
|Migration<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|MyBaseOptions|Ermöglicht Benutzern das Anzeigen eigener isolierter Nachrichten. <p> Diese Rolle wird Benutzern automatisch zugewiesen, und Sie können sie nicht manuell zuweisen.|keine|
|Organisationsclientzugriff<sup>\*</sup>||OrganizationManagement|
|Organisationskonfiguration|Anzeigen von Berichten|OrganizationManagement|
|Organisations-Transport-Einstellungen<sup>\*</sup>||OrganizationManagement|
|Quarantäne|Verwalten Sie alle Arten von isolierten Nachrichten für alle Empfänger.|OrganizationManagement <p> QuarantineAdministrator <p> SecurityAdministrator|
|Empfängerrichtlinien<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|Remote- und akzeptierte Domänen|Verwalten von Remotedomänen, akzeptierten Domänen und Connectors.|MailFlowAdministrator <p> OrganizationManagement|
|Kennwort zurücksetzen<sup>\*</sup>||HelpDesk <p> OrganizationManagement <p> RecipientManagement|
|Aufbewahrungsverwaltung<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> RecordsManagement|
|Rollenverwaltung|Erstellen und Verwalten von Rollengruppen.|OrganizationManagement|
|Sicherheitsadministrator|Verwalten Sie die Konfiguration und Berichte für alle Sicherheits- und Schutzfunktionen.|OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Erstellung und Mitgliedschaft von Sicherheitsgruppen|Erstellen und Verwalten von E-Mail-aktivierten Sicherheitsgruppen.|OrganizationManagement|
|Sicherheitsleseberechtigter|Zeigen Sie die Konfiguration und Berichte für Sicherheits- und Schutzfeatures an.|Organisationsverwaltung <p> SecurityReader <p> ViewOnlyOrganizationManagement|
|Vertraulichkeitsbezeichnungsadministrator<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Aufsicht<sup>\*</sup>||OrganizationManagement|
|Transporthygiene|Verwalten von Anti-Malware-, Antispamfunktionen und Anti-Spoofing-Features.|HygieneManagement <p> OrganizationManagement|
|Transportregeln|Erstellen und Verwalten von Nachrichtenflussregeln (auch als Transportregeln bekannt).|OrganizationManagement <p> RecordsManagement|
|Benutzeroptionen|Ändern vorhandener E-Mail-Benutzer.|HelpDesk <p> OrganizationManagement|
|View-Only Antischalware|Zeigen Sie die Konfiguration und Berichte für Anti-Malware-Features an.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only AntiSpam|Zeigen Sie die Konfiguration und Berichte für Antispamfeatures an.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|Überwachungsprotokolle nur anzeigen|Durchsuchen Sie das Administrator-Überwachungsprotokoll, und zeigen Sie die Ergebnisse an.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|Schreibgeschützte Konfiguration|Zeigen Sie alle Einstellungen für Organisation und Nachrichtenfluss (nicht empfängerfrei) in der Organisation an.|ComplianceManagement <p> HygieneManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only Quarantäne|Zeigen Sie alle isolierten Nachrichten für alle Empfänger an.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|Schreibgeschützte Empfänger|Anzeigen von Empfängereigenschaften und Ausführen der Nachrichtenverfolgung.|ComplianceManagement <p> HelpDesk <p> HygieneManagement <p> MailFlowAdministrator <p>  OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only Threat Intelligence<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|

<sup>\*</sup> Obwohl diese Rolle verfügbar ist, ist sie in eigenständigem EOP im Wesentlichen nicht hilfreich.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365-Berechtigungen in eigenständigem EOP

Wenn Sie einen Benutzer im Microsoft 365 Admin Center erstellen, können Sie auswählen, ob dem Benutzer verschiedene administrative Rollen zugewiesen werden, z. B. globaler Administrator, Dienstadministrator, Kennwortadministrator und so weiter. Einige, aber nicht alle Microsoft 365-Rollen erteilen dem Benutzer administrative Berechtigungen in EOP.

> [!NOTE]
> Das Konto, das Sie zum Erstellen Ihrer eigenständigen EOP-Organisation verwendet haben, wird automatisch der Globalen Administratorrolle zugewiesen.

In der folgenden Tabelle sind die Microsoft 365-Rollen und die eigenständigen EOP-Rollengruppen aufgeführt, denen sie entsprechen. Weitere Informationen zu diesen Rollen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

****

|Microsoft 365-Rolle|EOP-Rollengruppe|
|---|---|
|Exchange-Administrator|OrganizationManagement|
|Globaler Administrator|OrganizationManagement <p> **Hinweis:** Die Rolle "Globaler Administrator" und die Rollengruppe "OrganizationManagement" sind mithilfe einer speziellen Rollengruppe "Unternehmensadministrator" verbunden. Die Rollengruppe "Unternehmensadministrator" wird intern verwaltet und kann nicht direkt geändert werden.|
|Kennwortadministrator|HelpDesk|
|Globale Leseberechtigung|ViewOnlyOrganizationManagement|
|Sicherheitsadministrator|SecurityAdministrator|
|Benutzer mit Leseberechtigung für Sicherheitsfunktionen|SecurityReader|
|

Andere Microsoft 365-Rollen verfügen nicht über eine entsprechende EOP-Rollengruppe und erteilen keine Administratorberechtigungen in EOP. Weitere Informationen zum Zuweisen einer Microsoft 365-Rolle zu einem Benutzer finden Sie unter [Assign admin roles](../../admin/add-users/assign-admin-roles.md).

Benutzern können Administratorrechte in EOP gewährt werden, ohne sie zu Microsoft 365-Rollen hinzufügen zu müssen. Dazu fügen Sie den Benutzer als Mitglied einer EOP-Rollengruppe hinzu. Der Benutzer bekommt Berechtigungen in EOP, aber keine Berechtigungen in anderen Microsoft 365-Workloads.

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Gehen Sie wie folgt vor, um sicherzustellen, dass Sie eine Rollengruppe erfolgreich kopiert haben:

- Wechseln Sie in der EAC zu **Berechtigungen** Administratorrollen, und überprüfen Sie, ob die \> Rollengruppe aufgeführt ist (oder nicht aufgeführt). Wählen Sie die Rollengruppe aus, und überprüfen Sie die Einstellungen im Detailbereich, oder klicken Sie **auf** Bearbeiten ![ ](../../media/ITPro-EAC-EditIcon.png) (Symbol), um die Einstellungen zu überprüfen.

- Ersetzen Sie in Exchange Online PowerShell durch den Namen der Rollengruppe, und führen Sie den folgenden Befehl aus, um zu überprüfen, ob die Rollengruppe vorhanden (oder nicht vorhanden) ist, und überprüfen Sie die \<Role Group Name\> Einstellungen:

  ```PowerShell
  Get-RoleGroup -Identity "<Role Group Name>" | Format-List
  ```