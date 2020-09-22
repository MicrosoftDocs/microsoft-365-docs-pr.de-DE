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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Erfahren Sie mehr über die Berechtigungen, die für Aufgaben in eigenständigen Exchange Online Schutz erforderlich sind.
ms.openlocfilehash: ae43dc2223b17d3b73f9b76fa6bde8fb9cb95e77
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202867"
---
# <a name="permissions-in-standalone-eop"></a>Berechtigungen in EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Eigenständiger Exchange Online Schutz (EoP) ohne Exchange Online Postfächer verwenden das Berechtigungsmodell für die rollenbasierte Zugriffssteuerung (Role Based Access Control, RBAC), um Ihren Administratoren einfach Berechtigungen zu gewähren. Sie können die Berechtigungsfunktionen in eigenständigen EoP verwenden, um Ihre neue Organisation schnell bereitzustellen und zu starten.

Informationen zum Erteilen von Berechtigungen für Benutzer finden Sie unter [Verwalten von Administratorrollengruppen in EoP](manage-admin-role-group-permissions-in-eop.md).

Weitere Informationen zu Berechtigungen in Microsoft 365 finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="role-based-permissions"></a>Rollenbasierte Berechtigungen

Die Administratorberechtigungen, die Sie Benutzern erteilen, basieren auf Verwaltungsrollen. Eine Verwaltungsrolle definiert die Cmdlets, die für eine Reihe von bestimmten Aufgaben zur Verfügung stehen. Da die Exchange-Verwaltungskonsole (EAC) und die eigenständige EoP-PowerShell Cmdlets verwenden, erteilt der Zugriff auf ein Cmdlet dem Benutzer die Berechtigung, die zugehörigen Aufgaben in der Exchange-Verwaltungskonsole oder in der eigenständigen EoP-PowerShell auszuführen. Beispielsweise definiert die Rolle "e-Mail-Empfänger" die Cmdlets, die zum Ändern von e-Mail-Benutzern erforderlich sind.

In eigenständigen EoP sind Administratorrollen die einzige Verwaltungsrolle, die verfügbar ist (es gibt keine Endbenutzerrollen oder Richtlinien für Rollenzuweisungen).

## <a name="role-groups"></a>Rollengruppen

Um Benutzern die Zuweisung von Rollen zu erleichtern, verwendet eigenständige EoP Rollengruppen. Verwaltungsrollen werden Rollengruppen zugewiesen, und die Rollengruppenmitglieder erhalten die Berechtigungen, die den Rollen zugeordnet sind. In anderen Worten: Verwaltungsrollen werden nicht direkt Benutzern zugewiesen; Sie werden der Rollengruppe zugewiesen. Dieses Modell ermöglicht Ihnen, viele Rollengruppenmitgliedern gleichzeitig zuzuweisen. Mitglieder der Rollengruppe können e-Mail-Benutzer, e-Mail-aktivierte Sicherheitsgruppen, Benutzer aus dem Microsoft 365 Admin Center und andere Rollengruppen sein.

Die folgende Abbildung zeigt die Beziehung zwischen Benutzern, Rollengruppen und Rollen.

![Rolle, Rollengruppe und Mitglied - Beziehung](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

Die verfügbaren Rollengruppen in eigenständigen EoP werden in der folgenden Tabelle beschrieben.

****

|Rollengruppe|Beschreibung|Zugewiesene Standardrollen|
|---|---|---|
|ComplianceManagement|Konfigurieren und Verwalten von Kompatibilitätseinstellungen innerhalb der Organisation, einschließlich der Verhinderung von Datenverlust (DLP), wenn Ihr Abonnement über DLP-Funktionen verfügt. <br/><br/> Mitglieder der Rolle " [Konformitäts Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) " in Azure AD erhalten automatisch die Berechtigungen dieser Rollengruppe.|Überwachungsprotokolle <br/><br/> Compliance-Verwaltung <br/><br/> Verwaltung von Informationsrechten <br/><br/> Aufbewahrungsverwaltung <br/><br/> Überwachungsprotokolle nur anzeigen <br/><br/> Schreibgeschützte Konfiguration <br/><br/> Schreibgeschützte Empfänger|
|ContentExplorerContentViewer|Nicht verwendet.|Daten Klassifizierungs-Inhaltsanzeige|
|ContentExplorerListViewer|Nicht verwendet.|Listenanzeige für Datenklassifizierung|
|Helpdesk|Anzeigen und Verwalten von e-Mail-Benutzern|Kennwort zurücksetzen <br/><br/> Benutzeroptionen <br/><br/> Schreibgeschützte Empfänger|
|HygieneManagement|Verwalten von Schutzfunktionen (Anti-Spam, Antischadsoftware usw.).|Transport Hygiene <br/><br/> Schreibgeschützte Konfiguration <br/><br/> Schreibgeschützte Empfänger|
|MailFlowAdministrator|Anzeigen und Verwalten von akzeptierten Domänen und Connectors|Remote-und akzeptierte Domänen <br/><br/> Schreibgeschützte Empfänger|
|Mitglied|Administratorzugriff auf die gesamte Organisation und die Möglichkeit, nahezu jede Aufgabe auszuführen. <br/><br/> Mitglieder der [globalen Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) Rolle in Azure AD erhalten automatisch die Berechtigungen dieser Rollengruppe. <br/><br/> **Wichtig**: da es sich bei der Mitglied-Rollengruppe um eine leistungsstarke Rolle handelt, sollten nur Benutzer, die administrative Aufgaben auf Organisationsebene ausführen, Mitglieder dieser Rollengruppe sein.|Antischadsoftware <br/><br/> Antispam <br/><br/> Überwachungsprotokolle <br/><br/> Complianceadministrator <br/><br/> Dynamische Verteilergruppen <br/><br/> Verwaltung von Informationsrechten <br/><br/> Erstellen von E-Mail-Empfängern <br/><br/> E-Mail-Empfänger <br/><br/> Nachrichtenverfolgung <br/><br/> Migration <br/><br/> Organisations Client Zugriff <br/><br/> Organisationskonfiguration <br/><br/> Organisations Transport Einstellungen <br/><br/> Quarantäne <br/><br/> Empfängerrichtlinien <br/><br/> Remote-und akzeptierte Domänen <br/><br/> Kennwort zurücksetzen <br/><br/> Aufbewahrungsverwaltung <br/><br/> Rollenverwaltung <br/><br/> Sicherheitsadministrator <br/><br/> Erstellen und Mitgliedschaft von Sicherheitsgruppen <br/><br/> Sicherheitsleseberechtigter <br/><br/> Vertraulichkeits Bezeichnung-Administrator <br/><br/> Aufsicht <br/><br/> Transport Hygiene <br/><br/> Transportregeln <br/><br/> Benutzeroptionen <br/><br/> Nur anzeigen Antischadsoftware <br/><br/> Nur-anzeigen-Antispam <br/><br/> Überwachungsprotokolle nur anzeigen <br/><br/> Schreibgeschützte Konfiguration <br/><br/> Nur-Ansicht-Quarantäne <br/><br/> Schreibgeschützte Empfänger <br/><br/> Bedrohungs Intelligenz mit Ansichts Schutz|
|QuarantineAdministrator|Verwalten von Nachrichten in Quarantäne für alle Empfänger.|Quarantäne|
|RecipientManagement|Erstellen, verwalten und Entfernen von Empfängerobjekten in der Organisation.|Dynamische Verteilergruppen <br/><br/> Erstellen von E-Mail-Empfängern <br/><br/> E-Mail-Empfänger <br/><br/> Nachrichtenverfolgung <br/><br/> Migration <br/><br/> Empfängerrichtlinien <br/><br/> Kennwort zurücksetzen|
|RecordsManagement|Konfigurieren von Kompatibilitätsfeatures wie Aufbewahrungsrichtlinientags, Nachrichtenklassifikationen und Nachrichtenfluss Regeln (auch bekannt als Transportregeln)|Nachrichtenverfolgung <br/><br/> Aufbewahrungsverwaltung <br/><br/> Transportregeln|
|SecurityAdministrator|Konfigurieren Sie alle Aspekte des Schutzes in der Organisation (Anti-Spam, Antischadsoftware, Antispoofing, Quarantäne usw.). <br/><br/> Mitglieder der Rolle " [Sicherheits Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) " in Azure AD erhalten automatisch die Berechtigungen dieser Rollengruppe.|Antischadsoftware <br/><br/> Antispam <br/><br/> Überwachungsprotokolle <br/><br/> Quarantäne <br/><br/> Sicherheitsadministrator <br/><br/> Vertraulichkeits Bezeichnung-Administrator <br/><br/> Nur anzeigen Antischadsoftware <br/><br/> Nur-anzeigen-Antispam <br/><br/> Überwachungsprotokolle nur anzeigen <br/><br/> Nur-Ansicht-Quarantäne <br/><br/> Bedrohungs Intelligenz mit Ansichts Schutz|
|SecurityReader|Nur-Ansicht-Zugriff auf alle Aspekte des Schutzes in der Organisation (Antispam, Antischadsoftware, Antispoofing, Quarantäne usw.). <br/><br/> Mitglieder der [Sicherheits Leser](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) Rolle in Azure AD erhalten automatisch die Berechtigungen dieser Rollengruppe.|Sicherheitsleseberechtigter <br/><br/> Nur anzeigen Antischadsoftware <br/><br/> Nur-anzeigen-Antispam <br/><br/> Nur-Ansicht-Quarantäne <br/><br/> Bedrohungs Intelligenz mit Ansichts Schutz|
|TenantAdmins|Die Mitgliedschaft in dieser Rollengruppe wird in allen Diensten synchronisiert und zentral verwaltet. Standardmäßig ist dieser Rollengruppe keine Rollen zugewiesen. Sie ist jedoch Mitglied der Rollengruppe "Organisationsverwaltung" und erbt diese Berechtigungen.|keine|
|ViewOnlyOrganizationManagement|Zeigen Sie Empfänger-, Schutz-und Konfigurationsobjekte sowie deren Eigenschaften in der Organisation an.|Complianceadministrator <br/><br/> Sicherheitsadministrator <br/><br/> Sicherheitsleseberechtigter <br/><br/> Vertraulichkeits Bezeichnung-Administrator <br/><br/> Schreibgeschützte Konfiguration <br/><br/> Schreibgeschützte Empfänger|
|

Wenn Sie in einer kleinen Organisation mit nur wenigen Administratoren arbeiten, müssen Sie diese Benutzer möglicherweise nur der Rollengruppe "Organisationsverwaltung" hinzufügen, und Sie müssen möglicherweise nie die anderen Rollengruppen verwenden. Wenn Sie in einer größeren Organisation arbeiten, verfügen Sie möglicherweise über Administratoren, die bestimmte Aufgaben ausführen, beispielsweise die Empfängerkonfiguration. In diesen Fällen können Sie einen Administrator zur Rollengruppe "Empfängerverwaltung" und einen weiteren Administrator zur Rollengruppe "Organisationsverwaltung" hinzufügen. Diese Administratoren können dann Ihre spezifischen Bereiche verwalten, aber Sie verfügen nicht über Berechtigungen zum Verwalten von Bereichen, für die Sie nicht zuständig sind.

Wenn die integrierten Rollengruppen in Exchange Online nicht für die Aufgabenbereiche Ihrer Administratoren geeignet sind, können Sie Rollengruppen erstellen und Rollen zu diesen Gruppen hinzufügen. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in eigenständigen EoP](manage-admin-role-group-permissions-in-eop.md).

## <a name="roles"></a>Rollen

Die integrierten Rollen, die in eigenständigen EoP verfügbar sind, werden in der folgenden Tabelle beschrieben.

****

|Rolle * *|Beschreibung|Standardrollengruppen Zuweisungen|
|---|---|---|
|Antischadsoftware|Anzeigen und Ändern der Konfiguration und der Berichte für Antischadsoftware-Features.|Mitglied <br/><br/> SecurityAdministrator|
|Antispam|Anzeigen und Ändern der Konfiguration und der Berichte für Anti-Spam-Features.|Mitglied <br/><br/> SecurityAdministrator|
|Überwachungsprotokolle|Durchsuchen Sie das administratorüberwachungsprotokoll, und zeigen Sie die Ergebnisse an.|ComplianceManagement <br/><br/> Mitglied <br/><br/> SecurityAdministrator|
|Kompatibilitäts Administrator<sup>\*</sup>||ComplianceManagement <br/><br/> Mitglied <br/><br/> ViewOnlyOrganizationManagement|
|Daten Klassifizierungs-Inhaltsanzeige<sup>\*</sup>||ContentExplorerContentViewer|
|Listenanzeige für Datenklassifizierung<sup>\*</sup>||
|Dynamische Verteilergruppen|Erstellen und verwalten Sie alle Verteilergruppen, e-Mail-aktivierten Sicherheitsgruppen und Mitglieder.|Mitglied <br/><br/> RecipientManagement|
|Verwaltung von Informationsrechten<sup>\*</sup>||ComplianceManagement <br/><br/> Mitglied|
|Erstellen von E-Mail-Empfängern|Erstellen und Entfernen von e-Mail-Benutzern.|Mitglied <br/><br/> RecipientManagement|
|E-Mail-Empfänger|Ändern vorhandener e-Mail-Benutzer|Mitglied <br/><br/> RecipientManagement|
|Nachrichtenverfolgung<sup>\*</sup>||Mitglied <br/><br/> RecipientManagement <br/><br/> Datensatzverwaltung|
|Migration<sup>\*</sup>||Mitglied <br/><br/> RecipientManagement|
|MyBaseOptions|Ermöglicht Benutzern das Anzeigen Ihrer eigenen isolierten Nachrichten. <br/><br/> Diese Rolle wird Benutzern automatisch zugewiesen, und Sie können Sie nicht manuell zuweisen.|keine|
|Organisations Client Zugriff<sup>\*</sup>||Mitglied|
|Organisationskonfiguration|Anzeigen von Berichten|Mitglied|
|Organisations Transport Einstellungen<sup>\*</sup>||Mitglied|
|Quarantäne|Verwalten aller Typen von isolierten Nachrichten für alle Empfänger.|Mitglied <br/><br/> QuarantineAdministrator <br/><br/> SecurityAdministrator|
|Empfängerrichtlinien<sup>\*</sup>||Mitglied <br/><br/> RecipientManagement|
|Remote-und akzeptierte Domänen|Verwalten von Remotedomänen, akzeptierten Domänen und Connectors|MailFlowAdministrator <br/><br/> Mitglied|
|Kennwort zurücksetzen<sup>\*</sup>||Helpdesk <br/><br/> Mitglied <br/><br/> RecipientManagement|
|Aufbewahrungsverwaltung<sup>\*</sup>||ComplianceManagement <br/><br/> Mitglied <br/><br/> RecordsManagement|
|Rollenverwaltung|Erstellen und Verwalten von Rollengruppen.|Mitglied|
|Sicherheitsadministrator|Verwalten der Konfiguration und der Berichte für alle Sicherheits-und Schutzfunktionen.|Mitglied <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Erstellen und Mitgliedschaft von Sicherheitsgruppen|Erstellen und Verwalten von e-Mail-aktivierten Sicherheitsgruppen.|Mitglied|
|Sicherheitsleseberechtigter|Zeigen Sie die Konfiguration und die Berichte für Sicherheits-und Schutzfunktionen an.|Organisationsverwaltung <br/><br/> SecurityReader <br/><br/> ViewOnlyOrganizationManagement|
|Vertraulichkeits Bezeichnung-Administrator<sup>\*</sup>||Mitglied <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Aufsicht<sup>\*</sup>||Mitglied|
|Transport Hygiene|Verwalten von Antischadsoftware, Anti-Spam-Funktionen und Antispoofing-Features.|HygieneManagement <br/><br/> Mitglied|
|Transportregeln|Erstellen und Verwalten von Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet).|Mitglied <br/><br/> RecordsManagement|
|Benutzeroptionen|Ändern vorhandener e-Mail-Benutzer|Helpdesk <br/><br/> Mitglied|
|Nur anzeigen Antischadsoftware|Anzeigen der Konfiguration und der Berichte für Antischadsoftware-Features.|Mitglied <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Nur-anzeigen-Antispam|Anzeigen der Konfiguration und der Berichte für Antispam-Features.|Mitglied <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Überwachungsprotokolle nur anzeigen|Durchsuchen Sie das administratorüberwachungsprotokoll, und zeigen Sie die Ergebnisse an.|ComplianceManagement <br/><br/> Mitglied <br/><br/> SecurityAdministrator|
|Schreibgeschützte Konfiguration|Zeigen Sie alle Organisations-und Nachrichtenfluss Einstellungen (nicht Empfänger) in der Organisation an.|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> Mitglied <br/><br/> ViewOnlyOrganizationManagement|
|Nur-Ansicht-Quarantäne|Zeigt alle isolierten Nachrichten für alle Empfänger an.|Mitglied <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Schreibgeschützte Empfänger|Anzeigen von Empfänger Eigenschaften und Ausführen der Nachrichtenablaufverfolgung.|ComplianceManagement <br/><br/> Helpdesk <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  Mitglied <br/><br/> ViewOnlyOrganizationManagement|
|Bedrohungs Intelligenz mit Ansichts Schutz<sup>\*</sup>||Mitglied <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|

<sup>\*</sup> Obwohl diese Rolle verfügbar ist, wird Sie im Grunde nichts Nützliches in eigenständigen EoP.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365-Berechtigungen in eigenständigen EoP

Wenn Sie einen Benutzer im Microsoft 365 Admin Center erstellen, können Sie festlegen, ob dem Benutzer verschiedene Administratorrollen wie globaler Administrator, Dienstadministrator, Kennwort-Administrator usw. zugewiesen werden sollen. Einige, jedoch nicht alle, Microsoft 365-Rollen erteilen dem Benutzer Administratorberechtigungen in EoP.

> [!NOTE]
> Das Konto, das Sie zum Erstellen ihrer eigenständigen EoP-Organisation verwendet haben, wird automatisch der globalen Administratorrolle zugewiesen.

In der folgenden Tabelle sind die Microsoft 365-Rollen und die eigenständigen EoP-Rollengruppen aufgelistet, denen Sie entsprechen. Weitere Informationen zu diesen Rollen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

****

|Microsoft 365-Rolle|EoP-Rollengruppe|
|---|---|
|Exchange-Administrator|Mitglied|
|Globaler Administrator|Mitglied <br/><br/> **Hinweis**: die globale Administratorrolle und die Mitglied-Rollengruppe sind über eine spezielle Rollengruppe "Unternehmens Administrator" verbunden. Die Rollengruppe "Unternehmens Administrator" wird intern verwaltet und kann nicht direkt geändert werden.|
|Kennwortadministrator|Helpdesk|
|Globaler Leser|ViewOnlyOrganizationManagement|
|Sicherheitsadministrator|SecurityAdministrator|
|Benutzer mit Leseberechtigung für Sicherheitsfunktionen|SecurityReader|
|

Andere Microsoft 365-Rollen verfügen nicht über eine entsprechende EoP-Rollengruppe und erteilen keine administrativen Berechtigungen in EoP. Weitere Informationen zum Zuweisen einer Microsoft 365-Rolle zu einem Benutzer finden Sie unter [Zuweisen von Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).

Benutzern können in EoP Administratorrechte erteilt werden, ohne Sie zu Microsoft 365-Rollen hinzuzufügen. Hierzu fügen Sie den Benutzer als Mitglied einer EoP-Rollengruppe hinzu. Der Benutzer erhält Berechtigungen in EoP, erhält aber keine Berechtigungen in anderen Microsoft 365-Arbeitsauslastungen.

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie eine Rollengruppe erfolgreich kopiert haben:

- Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**, und überprüfen Sie, ob die Rollengruppe aufgeführt (oder nicht aufgeführt) ist. Wählen Sie die Rollengruppe aus, und überprüfen Sie die Einstellungen im Detail **Edit** Bereich, oder klicken Sie auf ![ Bearbeitungssymbol bearbeiten ](../../media/ITPro-EAC-EditIcon.png) , um die Einstellungen zu überprüfen.

- Ersetzen Sie in Exchange Online PowerShell \<Role Group Name\> durch den Namen der Rollengruppe, und führen Sie den folgenden Befehl aus, um zu überprüfen, ob die Rollengruppe vorhanden ist (oder nicht vorhanden ist), und überprüfen Sie die Einstellungen:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
