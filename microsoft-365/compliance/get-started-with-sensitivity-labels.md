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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Sind Sie bereit für die Bereitstellung von Vertraulichkeitsbezeichnungen, um die Daten Ihrer Organisation zu schützen, aber nicht sicher, wo Sie beginnen sollten? Hier finden Sie einige praktische Anleitungen, die Ihnen auf dem Weg zu Bezeichnungen helfen.
ms.openlocfilehash: 550a1a84df88340de14caff08284ef6a8cadc9e9
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022486"
---
# <a name="get-started-with-sensitivity-labels"></a>Erste Schritte mit Vertraulichkeitsbezeichnungen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Informationen darüber, was Vertraulichkeitsbezeichnungen sind und wie sie Ihnen helfen, die Daten Ihrer Organisation zu schützen, finden Sie unter [Weitere Informationen zu Vertraulichkeitsbezeichnungen](sensitivity-labels.md).

Wenn Sie [Azure Information Protection](/azure/information-protection/what-is-information-protection) einsetzen und immer noch Azure Information Protection-Bezeichnungen verwenden, die vom Azure-Portal verwaltet wurden, müssen Sie diese Bezeichnungen auf die [einheitliche Bezeichnungsplattform](/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform) migrieren. Auf Windows-Computern können Sie dann auswählen, [welcher Bezeichnungsclient verwendet werden soll](/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) für Ihre veröffentlichen Vertraulichkeitsbezeichnungen.

Wenn Sie bereit sind, die Daten Ihrer Organisation mit Vertraulichkeitsbezeichnungen zu schützen:

1. **Erstellen Sie die Bezeichnungen.** Erstellen und benennen Sie Ihre Vertraulichkeitsbezeichnungen gemäß der Klassifizierungstaxonomie Ihrer Organisation für unterschiedliche Vertraulichkeitsstufen von Inhalten. Verwenden Sie allgemeine Namen oder Ausdrücke, die für Ihre Benutzer leicht verständlich sind. Wenn Sie noch nicht über eine festgelegte Taxonomie verfügen, können Sie mit Bezeichnungen wie "Privat", "Öffentlich", "Allgemein", "Vertraulich" und "Hoch vertraulich" beginnen. Danach können Sie Unterbezeichnungen verwenden, um ähnliche Bezeichnungen nach Kategorien zu gruppieren. Verwenden Sie beim Erstellen einer Bezeichnung den QuickInfo-Text, um die Benutzer bei der Auswahl der geeigneten Bezeichnung zu unterstützen.
    
    Ausführlichere Anleitungen zum Definieren einer Klassifizierungstaxonomie finden Sie im Whitepaper „Datenklassifizierung und Taxonomie von Vertraulichkeitsbezeichnungen“, das Sie über das [Service Trust Portal](https://aka.ms/DataClassificationWhitepaper) herunterladen können.

2. **Legen Sie fest, wozu jede einzelne Bezeichnung dient.** Konfigurieren Sie die Schutzeinstellungen, die mit den einzelnen Bezeichnungen verknüpft werden sollen. Für Inhalte mit geringer Vertraulichkeitsstufe (z.B. mit der Bezeichnung „Allgemein“) können Sie beispielsweise nur eine Kopf- oder Fußzeile benutzen, während für Inhalt mit höheren Vertraulichkeitsstufen (z.B. die Bezeichnung „Vertraulich“) ein Wasserzeichen und eine Verschlüsselung angewendet werden sollten.

3. **Veröffentlichen Sie die Bezeichnungen.** Nachdem Sie die Vertraulichkeitsbezeichnungen konfiguriert haben, können Sie sie mithilfe einer Bezeichnungsrichtlinie veröffentlichen. Legen Sie fest, welche Benutzer und Gruppen die Bezeichnungen haben sollen und welche Richtlinieneinstellungen verwendet werden. Eine einzelne Bezeichnung kann wiederverwendet werden – Sie definieren eine Bezeichnung nur einmal und können sie anschließend in mehrere Bezeichnungsrichtlinien einfügen, die unterschiedlichen Benutzern zugewiesen sind. So könnten Sie beispielsweise mit Vertraulichkeitsbezeichnungen beginnen, indem Sie nur wenigen Benutzern eine Kennzeichnungsrichtlinie zuweisen. Wenn Sie dann bereit sind, die Bezeichnungen für Ihre gesamte Organisation bereitzustellen, können Sie eine neue Bezeichnungsrichtlinie für Ihre Bezeichnungen erstellen und dieses Mal alle Benutzer angeben.

Im Folgenden werden die grundlegenden Schritte für die Bereitstellung und Anwendung von Vertraulichkeitsbezeichnungen beschrieben:

![Diagramm mit Workflow für Vertraulichkeitsbezeichnungen](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Abonnement- und Lizenzierungsanforderungen für Vertraulichkeitsbezeichnungen

Eine Reihe verschiedener Abonnements unterstützen Vertraulichkeitsbezeichnungen, und die Lizenzierungsanforderungen für Benutzer hängen von den von Ihnen verwendeten Features ab.

Die Optionen für die Lizenzierung Ihrer Benutzer zur Nutzung der Microsoft 365-Compliancefeatures, finden Sie im [Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Informationen zu Vertraulichkeitsbezeichnungen finden Sie im Abschnitt [Informationsschutz](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) und im zugehörigen PDF- oder Excel-Download.

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>Für das Erstellen und Verwalten von Vertraulichkeitsbezeichnungen erforderliche Berechtigungen

Mitglieder Ihres Compliance-Teams, die Vertraulichkeitsbezeichnungen erstellen, benötigen Berechtigungen für das Microsoft 365 Compliance Center oder für das ältere Security & Compliance Center. 

Standardmäßig haben globale Administratoren für Ihren Mandanten Zugriff auf diese Admin Center und können Compliance-Beauftragte und anderen Personen Zugriff gewähren, ohne ihnen alle Berechtigungen eines Mandantenadministrators zu erteilen. Um diesen delegierten eingeschränkten Administratorzugriff zu erteilen, gehen Sie folgendermaßen vor: Fügen Sie der Rollengruppe **Compliancedatenadministrator**, **Complianceadministrator** oder **Sicherheitsadministrator** Benutzer hinzu. 

Alternativ zur Verwendung der Standardrollen können Sie eine neue Rollengruppe erstellen und dieser entweder die Rolle **Administrator für Vertraulichkeitsbezeichnungen** oder die Rolle **Organisationskonfiguration** hinzufügen. Verwenden Sie für eine schreibgeschützte Rolle den **Vertraulichkeitsbezeichnungen-Leser**. 

Anweisungen zum Hinzufügen von Benutzern zu den Standardrollen oder zum Erstellen eigener Rollengruppen finden Sie unter [Freigeben des Benutzerzugriffs auf das Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

Diese Berechtigungen sind nur zum Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen und deren Bezeichnungsrichtlinien erforderlich. Sie müssen die Bezeichnungen in Apps oder Diensten nicht anwenden. Wenn für bestimmte Konfigurationen, die sich auf Vertraulichkeitsbezeichnungen beziehen, zusätzliche Berechtigungen erforderlich sind, sind diese Berechtigungen in den entsprechenden Dokumentations-Anweisungen aufgelistet.

## <a name="deployment-strategy-for-sensitivity-labels"></a>Bereitstellungsstrategie für Vertraulichkeitsbezeichnungen
Eine erfolgreiche Strategie zur Bereitstellung von Vertraulichkeitsbezeichnungen in einer Organisation ist es, ein virtuelles Team ins Leben zu rufen, das die geschäftlichen und technischen Anforderungen, die Proof of Concept-Überprüfung, interne Prüfpunkte und Genehmigungen sowie die endgültige Bereitstellung für die Produktumgebung ermittelt und verwaltet.

Wir empfehlen, mithilfe der Tabelle im nächsten Abschnitt ihre ein oder zwei wichtigsten Szenarien zu ermitteln, die Ihre wirksamsten geschäftlichen Anforderungen abbilden. Kehren Sie nach dem Bereitstellen dieser Szenarien zur Liste zurück, um die nächsten ein oder zwei Prioritäten für die Bereitstellung zu ermitteln.

Weitere allgemeine Hinweise zur Bereitstellung finden Sie im herunterladbaren Data Loss Prevention and Microsoft Information Protection Deployment Acceleration Guide zum Herunterladen. Weitere Informationen finden Sie im Blogbeitrag [Microsoft 365 Information Protection and Compliance Deployment Acceleration Guides](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-365-information-protection-and-compliance-deployment/ba-p/2076404).

## <a name="common-scenarios-for-sensitivity-labels"></a>Häufige Szenarien für Vertraulichkeitsbezeichnungen

In allen Szenarien müssen Sie [Vertraulichkeitsbezeichnungen und deren Richtlinien erstellen und konfigurieren](create-sensitivity-labels.md).

|Ich möchte...|Dokumentation|
|----------------|---------------|
|Verwalten von Vertraulichkeitsbezeichnungen für Office-Apps, sodass der Inhalt bei seiner Erstellung mit Bezeichnungen versehen wird – enthält Unterstützung für manuelle Bezeichnung auf allen Plattformen |[Verwalten von Vertraulichkeitsbezeichnungen in Office-Apps](sensitivity-labels-office-apps.md)|
|Erlauben Sie Benutzern, Dateien von Windows-Computern mithilfe von Office-Apps, Datei-Explorer und PowerShell zu bezeichnen und zu schützen.|[Azure Information Protection-Clients mit einheitlichen Bezeichnungen für Windows](/azure/information-protection/rms-client/aip-clientv2)|
|Verschlüsseln von Dokumenten und E-Mails mit Vertraulichkeitsbezeichnungen sowie Einschränken, wer darauf zugreifen kann und wie diese Inhalte verwendet werden können |[Einschränken des Zugriffs auf Inhalte mithilfe der Vertraulichkeitsbezeichnungen zur Verschlüsselung](encryption-sensitivity-labels.md)|
|Aktivieren Sie Vertraulichkeitsbezeichnungen für Office im Web mit Unterstützung für die gemeinsame Dokumenterstellung, eDiscovery, Verhinderung von Datenverlust und Suche – sogar für verschlüsselte Dokumente. | [Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)
|Verwenden von gemeinsamer Dokumenterstellung und AutoSpeichern in Office-Desktop-Apps, wenn Dokumente verschlüsselt werden | [Aktivieren der gemeinsamen Erstellung für Dateien, die mit Vertraulichkeitsbezeichnungen verschlüsselt sind](sensitivity-labels-coauthoring.md)
|Automatisches Anwenden von Vertraulichkeitsbezeichnungen auf Dokumente und E-Mails | [Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)|
|Vertraulichkeitsbezeichnungen zum Schützen von Inhalten in Teams und SharePoint verwenden |[Verwendung von Vertraulichkeitsbezeichnungen bei Microsoft Teams, Microsoft 365-Gruppen und Microsoft Office SharePoint Online-Websites](sensitivity-labels-teams-groups-sites.md) |
|Verhindern oder Warnen von Benutzern vor dem Freigeben von Dateien oder E-Mails mit einer bestimmten Vertraulichkeitsbezeichnung |[Verwenden von Vertraulichkeitsbezeichnungen als Bedingungen in DLP-Richtlinien](dlp-sensitivity-label-as-condition.md) |
|Dateien, die in lokalen Datenspeichern gespeichert sind, ermitteln, mit Bezeichnungen versehen und schützen |[Bereitstellen des Azure Information Protection-Scanners zum automatischen Klassifizieren und Schützen von Dateien](/azure/information-protection/deploy-aip-scanner)|
|Dateien, die in Datenspeichern in der Cloud gespeichert sind, ermitteln, mit Bezeichnungen versehen und schützen|[Ermitteln, Klassifizieren, Bezeichnen und Schützen regulierter und sensibler Daten, die in der Cloud gespeichert werde](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Anwenden und Anzeigen von Bezeichnungen in Power BI und Schutz der Daten beim Speichern außerhalb des Diensts|[Vertraulichkeitsbezeichnungen in Power BI](/power-bi/admin/service-security-sensitivity-label-overview)|
|Überwachen und Verstehen, wie Vertraulichkeitsbezeichnungen in meiner Organisation verwendet werden|[Kennen Sie Ihre Daten – Überblick über die Datenklassifizierung](data-classification-overview.md) <br /><br /> [Erste Schritte mit Datenklassifizierung](data-classification-overview.md)|
|Erweitern von Vertraulichkeitsbezeichnungen auf Drittanbieter-Apps und -Dienste.|[Microsoft Information Protection-SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)|
|Erweitern von Vertraulichkeitsbezeichnungen auf Inhalte in Azure Blob Storage, Azure Files, Azure Data Lake Storage Gen1, und Azure Data Lake Storage Gen12.|[Automatische Beschriftung Ihrer Inhalte in Azure Purview](/azure/purview/create-sensitivity-label) |


## <a name="end-user-documentation-for-sensitivity-labels"></a>Dokumentation für Endbenutzer zu Vertraulichkeitsbezeichnungen

Die effektivste Dokumentation für Endbenutzer sind maßgeschneiderte Anleitungen und Anweisungen, die Sie für die von Ihnen ausgewählten Bezeichnungsnamen und -konfigurationen bereitstellen. Sie können die Einstellung für die Bezeichnungsrichtlinie **Benutzern einen Link zu einer benutzerdefinierten Hilfeseite** verwenden, um einen internen Link für diese Dokumentation anzugeben. Benutzer können dann darauf ganz einfach mittels der Schaltfläche **Vertraulichkeit** zugreifen:

- Weitere Informationen zur integrierten Beschriftung: Menüoption **Weitere Informationen**.
- Für den einheitlichen Bezeichnungs-Assistenten von Azure Information Protection: Menüoption **Hilfe und Feedback** > Link **Weitere Informationen** im Dialogfeld "Microsoft Azure Information Protection".

Informationen zur Bereitstellung Ihrer angepassten Dokumentation finden Sie auf der folgenden Seite und den folgenden Downloads, die Sie zur Schulung Ihrer Benutzer verwenden können: [Endbenutzerschulungen für Vertraulichkeitsbezeichnungen](https://microsoft.github.io/ComplianceCxE/enduser/sensitivity/). 

Für grundlegende Anweisungen können Sie auch die folgenden Ressourcen verwenden:

- [Verwenden von Vertraulichkeitsbezeichnungen auf Ihre Dateien und E-Mails in Office](https://support.microsoft.com/de-DE/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Bekannte Probleme mit Vertraulichkeitsbezeichnungen in Office](https://support.microsoft.com/de-DE/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Automatisches Anwenden oder Empfehlen von Vertraulichkeitsbezeichnungen für Ihre Dateien und E-Mails in Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Bekannte Probleme beim automatischen Anwenden oder Empfehlen von Vertraulichkeitsbezeichnungen](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Azure Information Protection-Benutzerleitfaden zu einheitliche Bezeichnungen](/azure/information-protection/rms-client/clientv2-user-guide)

Wenn Ihre Vertraulichkeitsbezeichnungen Verschlüsselung für PDF-Dokumente anwenden, können Sie diese Dokumente mit Microsoft Edge unter Windows oder Mac öffnen. Weitere Informationen und alternative Reader finden Sie unter [Welche PDF-Reader werden bei geschützten PDFs unterstützt?](/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)
