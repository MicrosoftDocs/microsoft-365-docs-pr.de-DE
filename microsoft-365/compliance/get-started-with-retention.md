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
search.appverid:
- MOE150
- MET150
description: Sie sind bereit, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen zum Schutz der Daten Ihrer Organisation zu implementieren, sind sich aber nicht sicher, wie Sie dies bewerkstelligen sollten? Hier finden Sie einige praktische Anweisungen für die ersten Schritte.
ms.openlocfilehash: 415313ac31fe4ad56f9a476576f14b90d7dd97f4
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127578"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>Erste Schritte zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Sind Sie bereit, die Daten Ihrer Organisation zu verwalten, indem Sie benötigte Inhalte beibehalten und nicht benötigte Inhalte löschen? Verwenden Sie diese ausführliche Anleitung für Ihre ersten Schritte:

1. **Informieren Sie sich über die Funktionsweise der Aufbewahrung** in Microsoft 365 und ermitteln Sie anschließend, ob Aufbewahrungsrichtlinien, Aufbewahrungsbezeichnungen oder eine entsprechende Kombination erforderlich sind: [Weitere Informationen zur Aufbewahrung](retention.md)

2. **Ermitteln Sie die Einstellungen und Aktionen der Aufbewahrung**, die laut Richtlinien Ihrer Organisation oder Branchenvorschriften erforderlich sind.
    
    Ermitteln Sie im Rahmen dieser Bewertung, ob Sie die [Datensatzverwaltung](records-management.md) verwenden werden.

3. **Erstellen Sie Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen**, anhand der von Ihnen ermittelten Aufbewahrungseinstellungen und Aktionen.
    
    Für Aufbewahrungsbezeichnungen ist es möglicherweise sinnvoll, Ihre Aufbewahrungsbezeichnungen anhand eines [Dateiplans](file-plan-manager.md)in einem Tabellenblatt zu definieren und zu verfeinern. Importieren Sie anschließend dieses Tabellenblatt, um Ihre Bezeichnungen zu erstellen.
    
3. **Veröffentlichen und Anwenden Ihrer Aufbewahrungsbezeichnungen**. Aufbewahrungsrichtlinien sind so gestaltet, dass sie diese „einrichten und vergessen“ können. Dennoch sind die Aufbewahrungsrichtlinien wiederverwendbare Bausteine, die in mehreren Richtlinien verwendet und in Benutzer-Workflows eingebunden werden können. Beachten Sie die Liste der [Allgemeinen Szenarien](#common-scenarios-for-retention-policies-and-retention-labels), um Ihnen die Nutzung von Aufbewahrungsbezeichnungen zu erleichtern. 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>Abonnement- und Lizenzierungsanforderungen für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

Eine Reihe verschiedener, abonnementgestützter Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Lizenzierungsanforderungen für Benutzer, abhängig von den von Ihnen verwendeten Funktionen.

Die Optionen für die Lizenzierung Ihrer Benutzer zur Nutzung der Microsoft 365-Compliancefeatures, finden Sie im [Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD). Zum Thema Aufbewahrung, beachten Sie den Abschnitt [Informationsverwaltung](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) sowie den zugehörigen PDF- oder Excel-Download für Lizenzierungsanforderungen auf Funktionsebene.

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>Notwendige Berechtigungen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

Die Mitglieder Ihres Complianceteams, die Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen erstellen und verwalten sollen, benötigen Berechtigungen für das [Microsoft 365 Compliance Center](https://compliance.microsoft.com/). Standardmäßig hat der Mandantenadministrator (Globaler Administrator) Zugriff auf diese Ressource und kann anderen Personen den Zugriff darauf gewähren, ohne ihnen alle Berechtigungen eines Mandantenadministrators zu geben. Um Berechtigungen für diese eingeschränkte Administration zu erteilen, empfehlen wir, Benutzer zur Administrator-Rollengruppe „**Compliance Administrator**“ hinzuzufügen. Anweisungen finden Sie unter [Benutzern den Zugriff auf das Security & Compliance Center gewähren](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Diese Berechtigungen sind nur erforderlich, um eine Aufbewahrungsrichtlinie zu erstellen und anzuwenden. Die Person, die die Aufbewahrungsrichtlinie konfiguriert, benötigt keinen Zugriff auf die Inhalte.

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>Allgemeine Szenarien für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

Anhand der folgenden Tabelle können Sie Ihre geschäftlichen Anforderungen entsprechenden Aufbewahrungsszenarien zuordnen, die von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen unterstützt werden.

|Ich möchte...|Dokumentation|
|----------------|---------------|
|Aktionen effizient für Ihre Organisation oder nach Standort festlegen, aufbewahren und löschen: <br />– Exchange  <br />– SharePoint  <br />– OneDrive  <br />– Microsoft 365-Gruppen <br />– Skype for Business  <br />– Teams  |[Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md)|
|Aufbewahrungs- und Löschaktionen für Dokumente und E-Mails manuell von Administratoren und Benutzer anwenden lassen: <br />-  SharePoint <br />– OneDrive <br />– Outlook und Outlook im Web|[Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)|
|Zulassen, dass Seitenadministratoren eine Standardaufbewahrungsbezeichnung für alle Inhalte in einer SharePoint-Bibliothek, einem Ordner oder einer Dokumentenmappe festlegen können|[Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)|
|Zulassen, dass Benutzer mithilfe von Outlook-Regeln eine Aufbewahrungsbezeichnung automatisch auf E-Mails anwenden können|[Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)|
|Aufbewahrungs- und Löschaktionen automatisch auf Dokumente und E-Mails anwenden |[Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)|
|Starten Sie den Aufbewahrungszeitraum mit einem bestimmten Ereignis, wie:  <br />– Mitarbeiter verlässt das Unternehmen <br />– Vertrag läuft aus <br />– Ende der Produktlebensdauer| [Aufbewahrung mit Eintritt eines Ereignisses starten](event-driven-retention.md)|
|Verwenden einer einzelnen Datensatzverwaltungslösung für Dokumente und E-Mails |[Datensatzverwaltung in Microsoft 365](records-management.md) |
|Einhaltung der SEC-Richtlinie 17a-4|[Verwenden von Exchange Online und des Security & Compliance Centers, zur Einhaltung der SEC-Richtlinie 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md) |
|Vergewissern Sie sich, dass das Löschen von Inhalten am Ende deren Aufbewahrungszeitraums von jemandem überprüft und genehmigt wird|[Dispositionsüberprüfungen](disposition.md#disposition-reviews) |
|Vergewissern Sie sich, dass Sie für Inhalte, die am Ende deren Aufbewahrungszeitraums gelöscht werden, einen Dispositionsnachweis haben|[Disposition von Datensätzen](disposition.md#disposition-of-records) |

## <a name="end-user-documentation-for-retention-labels"></a>Dokumentation zu Aufbewahrungsbezeichnungen für Endbenutzer

Aufbewahrungsbezeichnungen erscheinen im Gegensatz zu Aufbewahrungsrichtlinien in der Benutzeroberfläche von Microsoft 365-Apps. Vergewissern Sie sich, Ihren Endbenutzern und Ihrem Helpdesk Anleitungen bereitstellen, bevor Sie Ihrem Produktionsnetzwerk Aufbewahrungsbezeichnungen bereitstellen.

Die effektivste Art der Dokumentation für Endbenutzer umfasst maßgeschneiderte Anleitungen und Anweisungen zu den von Ihnen gewählten Namen und Konfigurationen von Aufbewahrungsbezeichnungen. Für grundlegende Anweisungen können Sie die folgenden Ressourcen nutzen:

- [Manuelles Anwenden von Aufbewahrungsbezeichnungen](create-apply-retention-labels.md#manually-apply-retention-labels)
