---
title: Erste Schritte mit Vertraulichkeitsbezeichnungen
f1.keywords:
- CSH
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
description: Sind Sie bereit für die Implementierung von Vertraulichkeitsbezeichnungen, um die Daten Ihrer Organisation zu schützen, aber nicht sicher, wo Sie beginnen sollten? Hier finden Sie einige praktische Anleitungen, die Ihnen auf dem Weg zu Bezeichnungen helfen.
ms.openlocfilehash: 9ffe0f52adf108ba03a41b2dba7261d21171bbba
ms.sourcegitcommit: 7dc36305721a92e19a6e397f906e19dcafa0073b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2020
ms.locfileid: "42101255"
---
# <a name="get-started-with-sensitivity-labels"></a>Erste Schritte mit Vertraulichkeitsbezeichnungen

Informationen darüber, was Vertraulichkeitsbezeichnungen sind und wie sie Ihnen helfen, die Daten Ihrer Organisation zu schützen, finden Sie unter [Weitere Informationen zu Vertraulichkeitsbezeichnungen](sensitivity-labels.md).

Wenn Sie [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) verwenden, ermitteln Sie, ob Sie Bezeichnungen zur Plattform für einheitliche Bezeichnungen migrieren müssen und welcher Bezeichnungsclient verwendet werden soll:
- [Wie kann ich feststellen, ob meine Mandanten sich auf der Plattform für einheitliche Bezeichnungen befinden?](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [Auswählen des zu verwendenden Bezeichnungsclients für Windows-Computer](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

Wenn Sie bereit sind, die Daten Ihrer Organisation mit Vertraulichkeitsbezeichnungen zu schützen:

1. **Erstellen Sie die Bezeichnungen.** Erstellen und benennen Sie Ihre Vertraulichkeitsbezeichnungen gemäß der Klassifizierungstaxonomie Ihrer Organisation für unterschiedliche Vertraulichkeitsstufen von Inhalten. Verwenden Sie allgemeine Namen oder Ausdrücke, die für Ihre Benutzer leicht verständlich sind. Wenn Sie noch nicht über eine festgelegte Taxonomie verfügen, können Sie mit Bezeichnungen wie "Privat", "Öffentlich", "Allgemein", "Vertraulich" und "Hoch vertraulich" beginnen. Danach können Sie Unterbezeichnungen verwenden, um ähnliche Bezeichnungen nach Kategorien zu gruppieren. Verwenden Sie beim Erstellen einer Bezeichnung den QuickInfo-Text, um die Benutzer bei der Auswahl der geeigneten Bezeichnung zu unterstützen.

2. **Legen Sie fest, wozu jede einzelne Bezeichnung dient.** Konfigurieren Sie die Schutzeinstellungen, die mit den einzelnen Bezeichnungen verknüpft werden sollen. Für Inhalte mit niedriger Vertraulichkeit (z.B. die Bezeichnung „Allgemein“) können Sie beispielsweise nur eine Kopf- oder Fußzeile benutzen, während auf vertraulichere Inhalt (z.B. die Bezeichnung „Vertraulich“) ein Wasserzeichen, Verschlüsselung und Endpoint Protection angewendet werden sollte.

3. **Veröffentlichen Sie die Bezeichnungen.** Nachdem Sie die Vertraulichkeitsbezeichnungen konfiguriert haben, können Sie sie mithilfe einer Bezeichnungsrichtlinie veröffentlichen. Legen Sie fest, welche Benutzer und Gruppen die Bezeichnungen haben sollen und welche Richtlinieneinstellungen verwendet werden. Eine einzelne Bezeichnung kann wiederverwendet werden, d. h. Sie definieren eine Bezeichnung nur einmal und können sie anschließend in mehrere Bezeichnungsrichtlinien einfügen, die unterschiedlichen Benutzern zugewiesen sind. So könnten Sie beispielsweise mit Vertraulichkeitsbezeichnungen beginnen, indem Sie nur wenigen Benutzern eine Kennzeichnungsrichtlinie zuweisen. Wenn Sie dann bereit sind, die Bezeichnungen für Ihre gesamte Organisation bereitzustellen, können Sie eine neue Bezeichnungsrichtlinie für Ihre Bezeichnungen erstellen und dieses Mal alle Benutzer angeben.

Im Folgenden werden die grundlegenden Schritte für die Bereitstellung und Anwendung von Vertraulichkeitsbezeichnungen beschrieben:

![Diagramm mit Workflow für Vertraulichkeitsbezeichnungen](../media/Sensitivity-label-flow.png)

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>Für das Erstellen und Verwalten von Vertraulichkeitsbezeichnungen erforderliche Berechtigungen

Mitglieder Ihres Complianceteams, die Vertraulichkeitsbezeichnungen erstellen, benötigen Berechtigungen für das Microsoft 365 Compliance Center, das Microsoft 365 Security Center oder das Office 365 Security & Compliance Center. 

Standardmäßig haben globale Administratoren für Ihren Mandanten Zugriff auf diese Admin Center und können Compliance-Beauftragte und anderen Personen Zugriff gewähren, ohne ihnen alle Berechtigungen eines Mandantenadministrators zu erteilen. Um diesen delegierten eingeschränkten Administratorzugriff zu erteilen, gehen Sie folgendermaßen vor: Navigieren Sie zur Seite **Berechtigungen** des jeweiligen Admin Centers, und fügen Sie dann der Rollengruppe **Compliancedatenadministrator**, **Complianceadministrator** oder **Sicherheitsadministrator** Mitglieder hinzu.

Alternativ zur Verwendung von Rollen können Sie eine neue Rollengruppe erstellen und dieser entweder die Rolle **Administrator für Vertraulichkeitsbezeichnungen** oder die Rolle **Organisationskonfiguration** hinzufügen. Anweisungen finden Sie unter [Gewähren des Zugriffs auf das Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Diese Berechtigungen sind nur zum Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen und deren Bezeichnungsrichtlinien erforderlich. Sie müssen die Bezeichnungen in Apps oder Diensten nicht anwenden.

## <a name="common-scenarios-for-sensitivity-labels"></a>Häufige Szenarien für Vertraulichkeitsbezeichnungen

Die folgende Dokumentation hilft Ihnen bei der Bereitstellung Ihrer Vertraulichkeitsbezeichnungen:

|Ich möchte...|Dokumentation|
|----------------|---------------|
|Vertraulichkeitsbezeichnungen zum Schützen der Daten meiner Organisation erstellen und veröffentlichen|[Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen und deren Richtlinien](create-sensitivity-labels.md)|
|Dokumente und E-Mails mit Vertraulichkeitsbezeichnungen verschlüsseln sowie einschränken, wer darauf zugreifen kann und wie diese Inhalte verwendet werden können |[Einschränken des Zugriffs auf Inhalte mithilfe der Vertraulichkeitsbezeichnungen zur Verschlüsselung](encryption-sensitivity-labels.md)|
|Funktionen für die Zusammenarbeit in SharePoint (und OneDrive) für Dokumente, die mit Bezeichnungen für Verschlüsselung versehen sind, aktivieren | [Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive (öffentliche Vorschau)](sensitivity-labels-sharepoint-onedrive-files.md)
|Vertraulichkeitsbezeichnungen für Office-Apps verwalten, sodass der Inhalt so bei der Erstellung mit Bezeichnungen versehen wird |[Verwenden von Vertraulichkeitsbezeichnungen in Office-Apps](sensitivity-labels-office-apps.md)|
|Vertraulichkeitsbezeichnungen oder empfohlene Bezeichnungen für Benutzer beim Erstellen von Inhalten automatisch anwenden | [Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)|
|Vertraulichkeitsbezeichnungen zum Schützen von Inhalten in Teams und SharePoint verwenden |[Verwenden von Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)](sensitivity-labels-teams-groups-sites.md)|
|Dateien, die in lokalen Datenspeichern gespeichert sind, ermitteln, mit Bezeichnungen versehen und schützen |[Bereitstellen des Azure Information Protection-Scanners zum automatischen Klassifizieren und Schützen von Dateien](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|Dateien, die in Datenspeichern in der Cloud gespeichert sind, ermitteln, mit Bezeichnungen versehen und schützen|[Ermitteln, Klassifizieren, Bezeichnen und Schützen regulierter und sensibler Daten, die in der Cloud gespeichert werde](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Visualisieren, wie Vertraulichkeitsbezeichnungen zum Melden des Bereitstellungsstatus und zum Optimieren der Bezeichnungskonfiguration verwendet werden|[Anzeigen der Bezeichnungsnutzung mit der Analyse der Bezeichnungen](label-analytics.md)|


## <a name="end-user-documentation-for-sensitivity-labels"></a>Dokumentation für Endbenutzer zu Vertraulichkeitsbezeichnungen

Die effektivste Dokumentation für Endbenutzer sind maßgeschneiderte Anleitungen und Anweisungen, die Sie für die von Ihnen ausgewählten Bezeichnungsnamen und -konfigurationen bereitstellen. Für grundlegende Anweisungen können Sie jedoch die folgenden Ressourcen verwenden:   

- [Verwenden von Vertraulichkeitsbezeichnungen auf Ihre Dateien und E-Mails in Office](https://support.office.com/article/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Bekannte Probleme mit Vertraulichkeitsbezeichnungen in Office](https://support.office.com/en-us/article/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Automatisches Anwenden oder Empfehlen von Vertraulichkeitsbezeichnungen für Ihre Dateien und E-Mails in Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Bekannte Probleme beim automatischen Anwenden oder Empfehlen von Vertraulichkeitsbezeichnungen](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Azure Information Protection-Benutzerleitfaden zu einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-user-guide)


