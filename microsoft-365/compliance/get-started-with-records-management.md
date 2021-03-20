---
title: Erste Schritte mit der Datensatzverwaltung in Microsoft 365
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
description: Benötigen Sie eine Lösung für die Datensatzverwaltung für Microsoft 365, die hochwertige Inhalte für rechtliche, geschäftliche oder behördliche Verpflichtungen verwaltet, aber Sie sind sich nicht sicher, wo Sie anfangen sollen? Hier finden Sie einige praktische Anweisungen für die ersten Schritte.
ms.openlocfilehash: a757cabf13e85731bd16ccd84f1eea3dbe7e432a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906007"
---
# <a name="get-started-with-records-management"></a>Erste Schritte mit der Datensatzverwaltung

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Sind Sie bereit, mit der Verwaltung der hochwertigen Inhalte Ihrer Organisation für rechtliche, geschäftliche oder behördliche Verpflichtungen mithilfe einer Datensatzverwaltungslösung in Microsoft 365 zu beginnen? Verwenden Sie diese ausführliche Anleitung für Ihre ersten Schritte:

1. **Grundlegendes zur Datensatzverwaltungslösung** und welche Aktionen zulässig bzw. blockiert sind, wenn Dokumente und E-Mails als Datensätze deklariert werden: [Mehr zur Datensatzverwaltung](records-management.md). 

2. **Grundlegendes zu Aufbewahrungsbezeichnungen und zur Funktionsweise der Aufbewahrung** für SharePoint und Exchange, da Aufbewahrungsbezeichnungen zum Deklarieren von Datensätzen verwendet werden: [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md)

3. **Erstellen Ihres Dateiplans für Aufbewahrungseinstellungen und -aktionen**, indem Sie [einen vorhandenen Plan importieren](file-plan-manager.md#import-retention-labels-into-your-file-plan ) (falls vorhanden), oder [neue Aufbewahrungsbezeichnungen erstellen, die Datensätze deklarieren](declare-records.md).

4. **Veröffentlichen und Anwenden Ihrer Aufbewahrungsbezeichnungen**. Aufbewahrungsrichtlinien sind wiederverwendbare Bausteine, die in mehreren Richtlinien verwendet und in Benutzer-Workflows eingebunden werden können: 
    
    - [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)
    - [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)

## <a name="subscription-and-licensing-requirements-for-records-management"></a>Abonnement- und Lizenzierungsanforderungen für Datensatzverwaltung

Eine Reihe verschiedener Abonnements unterstützen die Datensatzverwaltung, und die Lizenzierungsanforderungen für Benutzer hängen von den von Ihnen verwendeten Features ab.

Die Optionen für die Lizenzierung Ihrer Benutzer zur Nutzung der Microsoft 365-Compliancefeatures, finden Sie im [Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Zum Thema Datensatzverwaltung beachten Sie den Abschnitt [Datensatzverwaltung](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) sowie den zugehörigen PDF- oder Excel-Download für Lizenzierungsanforderungen auf Funktionsebene.

## <a name="permissions-required-for-records-management"></a>Erforderliche Berechtigungen für die Datensatzverwaltung

Die Mitglieder Ihres Complianceteams, die für die Datensatzverwaltung verantwortlich sind, benötigen Berechtigungen für das [Microsoft 365 Compliance Center](https://compliance.microsoft.com/). Standardmäßig hat der Mandantenadministrator (Globaler Administrator) Zugriff auf diese Ressource und kann anderen Personen den Zugriff darauf gewähren, ohne ihnen alle Berechtigungen eines Mandantenadministrators zu geben. Um Berechtigungen für diese eingeschränkte Administration zu erteilen, empfehlen wir, Benutzer zur Administrator-Rollengruppe **Datensatzverwaltung** hinzuzufügen, wodurch Berechtigungen für alle Features im Zusammenhang mit der Datensatzverwaltung zugewiesen werden, einschließlich [Dispositionsprüfung und -Verifizierung](disposition.md). 

Für eine schreibgeschützte Rolle können Sie eine neue Rollengruppe erstellen und die Rolle **Datensatzverwaltung – nur Leserechte** zu dieser Gruppe hinzufügen. 

Weitere Informationen zu Rollengruppen und Rollen finden Sie unter [Berechtigungen im Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center).

Anweisungen zum Hinzufügen von Benutzern zu Rollengruppen und zum Zuweisen von Rollen finden Sie unter [Freigeben des Benutzerzugriffs auf das Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

Diese Berechtigungen sind nur erforderlich, um Aufbewahrungsbezeichnungen zu erstellen, zu konfigurieren und anzuwenden, die Datensätze deklarieren, um Löschungen zu verwalten. Die Person, die die Bezeichnungen konfiguriert, benötigt keinen Zugriff auf die Inhalte.

## <a name="common-scenarios-for-records-management"></a>Häufige Szenarien für die Datensatzverwaltung

Anhand der folgenden Tabelle können Sie Ihre geschäftlichen Anforderungen entsprechenden Szenarien zuordnen, die von der Datensatzverwaltung unterstützt werden.

> [!NOTE]
> Da die Datensatzverwaltung Aufbewahrungsbezeichnungen zum Markieren eines Elements als Datensatz verwendet, werden viele Szenarios in dieser Tabelle auch als [häufige Szenarios für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md#common-scenarios-for-retention-policies-and-retention-labels) aufgeführt.

|Ich möchte...|Dokumentation|
|----------------|---------------|
|Deklarieren eines Datensatzes |[Datensätze mithilfe von Aufbewahrungsbezeichnungen deklarieren](declare-records.md)|
|Aktualisieren eines Datensatzes |[Versionsverwaltung zur Aktualisierung von Datensätzen verwenden, die in Microsoft Office SharePoint Online oder OneDrive gespeichert sind](record-versioning.md)|
|Lassen Sie Admins und Benutzer manuell Aktionen zum Einbehalten und Löschen von Dokumenten und E-Mails anwenden: <br />-  SharePoint <br />– OneDrive <br />– Outlook und Outlook im Web|[Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)|
|Site-Administratoren können Aktionen für alle Inhalte in einer SharePoint-Bibliothek, einem Ordner oder einem Dokumentensatz standardmäßig beibehalten und löschen.|[Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)|
|Benutzer können mithilfe von Outlook-Regeln automatisch Aufbewahrungs- und Löschaktionen auf E-Mails anwenden|[Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)|
|Administratoren können Aktionen zum Aufbewahren und Löschen von Dokumenten auf ein Dokumentenverständnismodell anwenden, so dass diese automatisch auf identifizierte Dokumente in einer Microsoft Office SharePoint Online Bibliothek angewendet werden.|[Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)|
|Automatische Anwendung von Aufbewahrungs- und Löschaktionen auf Dokumente und E-Mails |[Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)|
|Starten Sie den Aufbewahrungszeitraum mit einem bestimmten Ereignis, wie:  <br />– Mitarbeiter verlässt das Unternehmen <br />– Vertrag läuft aus <br />– Ende der Produktlebensdauer| [Aufbewahrung mit Eintritt eines Ereignisses starten](event-driven-retention.md)|
|Richtlinienänderungen einschränken, um bei Einhaltung behördlicher Anforderungen oder beim Schutz vor böswilligen Administratoren zu helfen.| [Verwenden Sie Erhaltungssperre, um Änderungen an Aufbewahrungsregeln und den Richtlinien zur Aufbewahrungsbezeichnung einzuschränken](retention-preservation-lock.md)
|Verwalten des Lebenszyklus verschiedener Dokumenttypen in SharePoint| [Verwenden von Aufbewahrungsbezeichnungen zum Verwalten des Lebenszyklus von in SharePoint gespeicherten Dokumenten](auto-apply-retention-labels-scenario.md)|
|Vergewissern Sie sich, dass das Löschen von Inhalten am Ende deren Aufbewahrungszeitraums von jemandem überprüft und genehmigt wird|[Dispositionsüberprüfungen](disposition.md#disposition-reviews) |
|Verfügungsnachweis für Inhalte haben, die am Ende ihrer Aufbewahrungsfrist endgültig gelöscht werden|[Disposition von Datensätzen](disposition.md#disposition-of-records) |
| Einstellungen überwachen, wie und wo Aufbewahrungs- und Löschungseinstellungen auf Elemente angewendet werden | [Überwachen von Aufbewahrungsbezeichnungen](retention.md#monitoring-retention-labels) |

## <a name="end-user-documentation-for-records"></a>Dokumentation zu Datensätzen für Endbenutzer

Aufbewahrungsbezeichnungen, die für die Datensatzverwaltung verwendet werden, sind in Microsoft 365-Apps in der Benutzeroberfläche vorhanden. Vergewissern Sie sich, Ihren Endbenutzern und Ihrem Helpdesk Anleitungen bereitstellen, bevor Sie Ihrem Produktionsnetzwerk Aufbewahrungsbezeichnungen bereitstellen.

Die effektivste Art der Dokumentation für Endbenutzer umfasst maßgeschneiderte Anleitungen und Anweisungen zu den von Ihnen gewählten Namen und Konfigurationen von Aufbewahrungsbezeichnungen. Lesen Sie den folgenden Beitrag für ein Downloadpaket, mit dem sie Benutzer trainieren und Einführungen nutzen können: [Endbenutzertraining in Aufbewahrungsbezeichnungen in M365 – Wie Sie Ihre Einführung beschleunigen können](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-retention-labels-in-m365-how-to-accelerate/ba-p/1750861).

Sie können auch Grundanweisungen im folgenden Abschnitt finden: [Manuelles Anwenden von Aufbewahrungsbezeichnungen](create-apply-retention-labels.md#manually-apply-retention-labels).