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
description: Sie sind bereit, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen zum Schutz der Daten Ihrer Organisation zu implementieren, sind sich aber nicht sicher, wie Sie dies bewerkstelligen sollten? Hier finden Sie einige praktische Anweisungen für die ersten Schritte.
ms.openlocfilehash: b4dcbe15e2a2d9e3d056555a9212125b60133826
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919863"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>Erste Schritte zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Sind Sie bereit, die Daten Ihrer Organisation zu verwalten, indem Sie benötigte Inhalte beibehalten und nicht benötigte Inhalte löschen? Verwenden Sie diese ausführliche Anleitung für Ihre ersten Schritte:

1. **Informieren Sie sich über die Funktionsweise der Aufbewahrung** in Microsoft 365 und ermitteln Sie anschließend, ob Aufbewahrungsrichtlinien, Aufbewahrungsbezeichnungen oder eine entsprechende Kombination erforderlich sind: [Weitere Informationen zur Aufbewahrung](retention.md)

2. **Ermitteln Sie die Einstellungen und Aktionen der Aufbewahrung** , die laut Richtlinien Ihrer Organisation oder Branchenvorschriften erforderlich sind.
    
    Ermitteln Sie im Rahmen dieser Bewertung, ob Sie die [Datensatzverwaltung](records-management.md) verwenden werden.

3. **Erstellen Sie Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen** , anhand der von Ihnen ermittelten Aufbewahrungseinstellungen und Aktionen.
    
    Für Aufbewahrungsbezeichnungen ist es möglicherweise sinnvoll, Ihre Aufbewahrungsbezeichnungen anhand eines [Dateiplans](file-plan-manager.md)in einem Tabellenblatt zu definieren und zu verfeinern. Importieren Sie anschließend dieses Tabellenblatt, um Ihre Bezeichnungen zu erstellen.
    
3. **Veröffentlichen und Anwenden Ihrer Aufbewahrungsbezeichnungen**. Aufbewahrungsrichtlinien sind so gestaltet, dass sie diese „einrichten und vergessen“ können. Dennoch sind die Aufbewahrungsrichtlinien wiederverwendbare Bausteine, die in mehreren Richtlinien verwendet und in Benutzer-Workflows eingebunden werden können. Beachten Sie die Liste der [Allgemeinen Szenarien](#common-scenarios-for-retention-policies-and-retention-labels), um Ihnen die Nutzung von Aufbewahrungsbezeichnungen zu erleichtern. 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>Abonnement- und Lizenzierungsanforderungen für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

Eine Reihe verschiedener, abonnementgestützter Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Lizenzierungsanforderungen für Benutzer, abhängig von den von Ihnen verwendeten Funktionen.

Die Optionen für die Lizenzierung Ihrer Benutzer zur Nutzung der Microsoft 365-Compliancefeatures, finden Sie im [Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD). Zum Thema Aufbewahrung, beachten Sie den Abschnitt [Informationsverwaltung](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) sowie den zugehörigen PDF- oder Excel-Download für Lizenzierungsanforderungen auf Funktionsebene.

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>Notwendige Berechtigungen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

Die Mitglieder Ihres Complianceteams, die Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen erstellen und verwalten sollen, benötigen Berechtigungen für das [Microsoft 365 Compliance Center](https://compliance.microsoft.com/). Standardmäßig hat der Mandantenadministrator (Globaler Administrator) Zugriff auf diese Ressource und kann anderen Personen den Zugriff darauf gewähren, ohne ihnen alle Berechtigungen eines Mandantenadministrators zu geben. Um Berechtigungen für diese eingeschränkte Administration zu erteilen, empfehlen wir, Benutzer zur Administrator-Rollengruppe „ **Compliance Administrator** “ hinzuzufügen. Anweisungen finden Sie unter [Benutzern den Zugriff auf das Security & Compliance Center gewähren](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

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

## <a name="end-user-documentation-for-retention-labels"></a>Dokumentation zu Aufbewahrungsbezeichnungen für Endbenutzer

Aufbewahrungsbezeichnungen erscheinen im Gegensatz zu Aufbewahrungsrichtlinien in der Benutzeroberfläche von Microsoft 365-Apps. Vergewissern Sie sich, Ihren Endbenutzern und Ihrem Helpdesk Anleitungen bereitstellen, bevor Sie Ihrem Produktionsnetzwerk Aufbewahrungsbezeichnungen bereitstellen.

Die effektivste Art der Dokumentation für Endbenutzer umfasst maßgeschneiderte Anleitungen und Anweisungen zu den von Ihnen gewählten Namen und Konfigurationen von Aufbewahrungsbezeichnungen. Lesen Sie den folgenden Blogbeitrag für ein Downloadpaket, mit dem sie Benutzer trainieren und Einführungen nutzen können: [Endbenutzertraining in Aufbewahrungsbezeichnungen in M365 – Wie Sie Ihre Einführung beschleunigen können](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-retention-labels-in-m365-how-to-accelerate/ba-p/1750861).

Sie können auch Grundanweisungen im folgenden Abschnitt finden: [Manuelles Anwenden von Aufbewahrungsbezeichnungen](create-apply-retention-labels.md#manually-apply-retention-labels).
