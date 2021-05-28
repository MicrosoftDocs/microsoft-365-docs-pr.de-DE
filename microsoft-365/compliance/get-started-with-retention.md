---
title: Erste Schritte zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Sie sind bereit, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen zum Schutz der Daten Ihrer Organisation zu implementieren, sind aber nicht sicher, wo Sie starten sollen? Lesen Sie einige praxisbezogene Anleitungen für den Einstieg.
ms.openlocfilehash: bd3ed5e354ee80831cb1af073b6da6f277418b51
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689037"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>Erste Schritte zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Sind Sie bereit, die Daten Ihrer Organisation zu verwalten, indem Sie die Inhalte aufbewahren, die Sie behalten müssen, und die Inhalte löschen, die Sie nicht mehr benötigen? Verwenden Sie die folgende Anleitung für den Einstieg:

1. **Informieren Sie sich über die Funktionsweise der Aufbewahrung** in Microsoft 365 und ermitteln Sie anschließend, ob Aufbewahrungsrichtlinien, Aufbewahrungsbezeichnungen oder eine entsprechende Kombination erforderlich sind: [Weitere Informationen zur Aufbewahrung](retention.md)

2. **Ermitteln Sie die Einstellungen und Aktionen der Aufbewahrung**, die laut Richtlinien Ihrer Organisation oder Branchenvorschriften erforderlich sind.
    
    Ermitteln Sie im Rahmen dieser Bewertung, ob Sie die [Datensatzverwaltung](records-management.md) verwenden werden.

3. **Erstellen Sie Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen**, anhand der von Ihnen ermittelten Aufbewahrungseinstellungen und Aktionen.
    
    Für Aufbewahrungsbezeichnungen ist es möglicherweise sinnvoll, Ihre Aufbewahrungsbezeichnungen anhand eines [Dateiplans](file-plan-manager.md)in einem Tabellenblatt zu definieren und zu verfeinern. Importieren Sie anschließend dieses Tabellenblatt, um Ihre Bezeichnungen zu erstellen.
    
3. **Veröffentlichen und Anwenden Ihrer Aufbewahrungsbezeichnungen**. Aufbewahrungsrichtlinien sind so gestaltet, dass sie diese „einrichten und vergessen“ können. Dennoch sind die Aufbewahrungsrichtlinien wiederverwendbare Bausteine, die in mehreren Richtlinien verwendet und in Benutzer-Workflows eingebunden werden können. Beachten Sie die Liste der [Allgemeinen Szenarien](#common-scenarios-for-retention-policies-and-retention-labels), um Ihnen die Nutzung von Aufbewahrungsbezeichnungen zu erleichtern. 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>Abonnement- und Lizenzierungsanforderungen für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

Eine Reihe verschiedener, abonnementgestützter Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Lizenzierungsanforderungen für Benutzer, abhängig von den von Ihnen verwendeten Funktionen.

Die Optionen für die Lizenzierung Ihrer Benutzer zur Nutzung der Microsoft 365-Compliancefeatures, finden Sie im [Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Zum Thema Aufbewahrung, beachten Sie den Abschnitt [Informationsverwaltung](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) sowie den zugehörigen PDF- oder Excel-Download für Lizenzierungsanforderungen auf Funktionsebene.

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>Notwendige Berechtigungen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

Die Mitglieder Ihres Complianceteams, die Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen erstellen und verwalten sollen, benötigen Berechtigungen für das [Microsoft 365 Compliance Center](https://compliance.microsoft.com/). Standardmäßig hat der Mandantenadministrator (Globaler Administrator) Zugriff auf diese Ressource und kann anderen Personen den Zugriff darauf gewähren, ohne ihnen alle Berechtigungen eines Mandantenadministrators zu geben. Um Berechtigungen für diese eingeschränkte Administration zu erteilen, empfehlen wir, Benutzer zur Administrator-Rollengruppe „**Compliance Administrator**“ hinzuzufügen.

Alternativ zur Verwendung dieser Standardrolle können Sie eine neue Rollengruppe erstellen und die Rolle **Aufbewahrungsverwaltung** zu dieser Gruppe hinzufügen. Für eine schreibgeschützte Rolle verwenden Sie **Aufbewahrungsverwaltung – nur Leserechte**. 

Weitere Informationen zu Rollengruppen und Rollen finden Sie unter [Berechtigungen im Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center).

Anweisungen zum Hinzufügen von Benutzern zu Rollengruppen und zum Zuweisen von Rollen finden Sie unter [Freigeben des Benutzerzugriffs auf das Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

Diese Berechtigungen sind nur erforderlich, um Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen zu erstellen und anzuwenden. Die Person, die die Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen konfiguriert, benötigt keinen Zugriff auf die Inhalte.

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>Allgemeine Szenarien für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

Anhand der folgenden Tabelle können Sie Ihre geschäftlichen Anforderungen entsprechenden Aufbewahrungsszenarien zuordnen, die von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen unterstützt werden.

|Ich möchte...|Dokumentation|
|----------------|---------------|
|Effizientes Festlegen von Aktionen zum Aufbewahren und Löschen durch den Microsoft 365-Dienst: <br />– Exchange  <br />– SharePoint  <br />– OneDrive  <br />– Microsoft 365-Gruppen <br />– Skype for Business  <br />– Microsoft Teams <br />– Yammer-Netzwerks |[Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md)|
|Lassen Sie Administratoren und Benutzer manuell Aktionen zum Aufbewahren und Löschen von Dokumenten und E-Mails anwenden: <br />-  SharePoint <br />– OneDrive <br />– Outlook und Outlook im Web|[Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)|
|Site-Administratoren können Aktionen für alle Inhalte in einer SharePoint-Bibliothek, einem Ordner oder einem Dokumentensatz standardmäßig beibehalten und löschen.|[Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)|
|Benutzer können mithilfe von Outlook-Regeln automatisch Aufbewahrungs- und Löschaktionen auf E-Mails anwenden|[Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)|
|Administratoren können Aktionen zum Aufbewahren und Löschen von Dokumenten auf ein Dokumentenverständnismodell anwenden, so dass diese automatisch auf identifizierte Dokumente in einer Microsoft Office SharePoint Online Bibliothek angewendet werden.|[Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)|
|Automatische Anwendung von Aufbewahrungs- und Löschaktionen auf Dokumente und E-Mails |[Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)|
|Starten Sie den Aufbewahrungszeitraum mit einem bestimmten Ereignis, wie:  <br />– Mitarbeiter verlässt das Unternehmen <br />– Vertrag läuft aus <br />– Ende der Produktlebensdauer| [Aufbewahrung mit Eintritt eines Ereignisses starten](event-driven-retention.md)|
|Richtlinienänderungen einschränken, um bei Einhaltung behördlicher Anforderungen oder beim Schutz vor böswilligen Administratoren zu helfen.| [Verwenden Sie Erhaltungssperre, um Änderungen an Aufbewahrungsregeln und den Richtlinien zur Aufbewahrungsbezeichnung einzuschränken](retention-preservation-lock.md)
|Vergewissern Sie sich, dass das Löschen von Inhalten am Ende deren Aufbewahrungszeitraums von jemandem überprüft und genehmigt wird|[Dispositionsüberprüfungen](disposition.md#disposition-reviews) |
| Einstellungen überwachen, wie und wo Aufbewahrungs- und Löscheinstellungen auf Elemente angewendet werden | [Überwachen von Aufbewahrungsbezeichnungen](retention.md#monitoring-retention-labels) |
|Verwenden einer einzelnen Datensatzverwaltungslösung für Dokumente und E-Mails |[Mehr zur Datensatzverwaltung](records-management.md) |

Wenn Sie Aufbewahrungsbezeichnungen für die Datensatzverwaltung verwenden, gibt es zusätzliche Szenarios, die einzigartig für Aufbewahrungsbezeichnungen sind, die Inhalte als Datensatz kennzeichnen. Siehe [Häufige Szenarien für die Datensatzverwaltung](get-started-with-records-management.md#common-scenarios-for-records-management).

## <a name="end-user-documentation-for-retention"></a>Dokumentation zur Aufbewahrung für Endbenutzer

Die meisten Aufbewahrungsrichtlinien arbeiten unauffällig im Hintergrund ohne Benutzerinteraktion und benötigen daher nur wenig Dokumentation für Benutzer. Aufbewahrungsrichtlinien für Teams informieren Benutzer, wenn ihre Nachrichten gelöscht wurden, mit einem Link zu [Teams-Nachrichten über Aufbewahrungsrichtlinien](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

Da Aufbewahrungsbezeichnungen in Microsoft 365-Apps über eine Benutzeroberfläche verfügen, sollten Sie den Endbenutzern und Ihrem Helpdesk eine Anleitung geben, bevor Sie diese Bezeichnungen in Ihrem Produktionsnetzwerk bereitstellen. Informationen zum Anwenden von Aufbewahrungsbezeichnungen in SharePoint und OneDrive, finden Sie unter [Anwenden von Aufbewahrungsbezeichnungen auf Dateien in SharePoint oder OneDrive ](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df).

Die effektivste Art der Dokumentation für Endbenutzer sind jedoch maßgeschneiderte Anleitungen und Anweisungen zu den von Ihnen gewählten Namen und Konfigurationen von Aufbewahrungsbezeichnungen. Schauen Sie sich die folgende Seite und Downloads an, die Sie verwenden können, um Ihre Benutzer zu schulen: [Endbenutzerschulungen für Aufbewahrungsbezeichnungen](https://microsoft.github.io/ComplianceCxE/enduser/retention/).