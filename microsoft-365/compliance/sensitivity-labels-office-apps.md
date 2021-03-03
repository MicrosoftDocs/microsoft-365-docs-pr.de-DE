---
title: Verwalten von Vertraulichkeitsbezeichnungen in Office-Apps
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informationen für IT-Administratoren zum Verwalten von Vertraulichkeitsbezeichnungen in Office-Apps für Desktop, Mobile und das Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1834e1071c56e03ef20ae0e87b63fc4c03a6921b
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407305"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Verwalten von Vertraulichkeitsbezeichnungen in Office-Apps

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Wenn Sie [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) Vertraulichkeitsbezeichnungen aus dem Microsoft 365 Compliance Center oder einem gleichwertigen Bezeichnungscenter veröffentlicht haben, werden sie in Office-Apps angezeigt, damit Benutzer Daten bei deren Erstellen oder Bearbeiten klassifizieren und schützen können.

Verwenden Sie die Informationen in diesem Artikel, um Vertraulichkeitsbezeichnungen in Office-Apps erfolgreich zu verwalten. Identifizieren Sie beispielsweise die Mindestversionen von Apps, die Sie für die Unterstützung der integrierten Bezeichnung benötigen, und verstehen Sie die Interaktionen mit dem Azure Information Protection Unified Labeling Client und die Kompatibilität mit anderen Apps und Diensten.

## <a name="labeling-client-for-desktop-apps"></a>Bezeichnungsclient für Desktop-Apps

Um Vertraulichkeitsbezeichnungen zu verwenden, die in Office-Desktop-Apps für Windows und Mac integrierte sind, müssen Sie eine Abonnementversion von Office verwenden. Dieser Bezeichnungsclient unterstützt keine eigenständigen Editionen von Office, z. B. Office 2016 oder Office 2019.

Installieren Sie den Azure Information Protection Unified Labeling Client, um Vertraulichkeitsbezeichnungen mit diesen eigenständigen Editionen von Office auf [Windows-Computern zu verwenden.](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Unterstützung für Vertraulichkeitsbezeichnungsfunktionen in Apps

Für jede Funktion enthält die folgende Tabelle die minimale Office-Version, die Sie zur Unterstützung von Vertraulichkeitsbezeichnungen mithilfe der integrierten Bezeichnung benötigen. Oder wenn sich die Bezeichnungsfunktion in der öffentlichen Vorschau befindet oder für eine zukünftige Version überprüft wird. Weitere Informationen zu zukünftigen Versionen finden Sie in der [Microsoft 365-Roadmap.](https://aka.ms/MIPC/Roadmap)

Neue Versionen von Office-Apps werden zu unterschiedlichen Zeiten für verschiedene Updatekanäle verfügbar gemacht. Weitere Informationen, einschließlich der Konfiguration Ihres Updatekanals, damit Sie eine neue Bezeichnungsfunktion testen können, die Sie interessieren, finden Sie unter [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/overview-update-channels). Neue Funktionen, die sich in der privaten Vorschau befinden, sind nicht in der Tabelle enthalten, aber Sie können diese Vorschauen möglicherweise durch Nominieren Ihrer Organisation für das private [Microsoft Information Protection-Vorschauprogramm nominieren.](https://aka.ms/mip-preview)

> [!NOTE]
> Die Namen der Updatekanäle für Office-Apps haben sich kürzlich geändert. Beispielsweise ist monatlicher Kanal jetzt aktueller Kanal, und Office Insider ist jetzt Beta-Kanal. Weitere Informationen finden Sie unter [Änderungen am Aktualisieren von Kanälen für Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/update-channels-changes).

Office für iOS und Office für Android: Vertraulichkeitsbezeichnungen sind in die [Office-App integrierte.](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)

Zusätzliche Funktionen sind verfügbar, wenn Sie den Azure Information Protection Unified Labeling-Client installieren, der nur auf Windows-Computern ausgeführt wird. Weitere Informationen finden Sie [unter Compare the labeling clients for Windows computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Vertraulichkeitsbezeichnungsfunktionen in Word, Excel und PowerPoint

Bei den aufgeführten Nummern handelt es sich um die mindestens erforderliche Office-Anwendungsversion für jede Funktion.

|Funktion                                                                                                        |Windows |Mac |iOS    |Android      |Netz                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Bezeichnung manuell anwenden, ändern oder entfernen](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Opt-In](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Anwenden einer Standardbezeichnung](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Opt-In](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Erfordern einer Begründung zum Ändern einer Bezeichnung](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Opt-In](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Bereitstellen eines Hilfelinks zu einer benutzerdefinierten Hilfeseite](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Opt-In](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Inhalt markieren](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Opt-In](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Dynamische Markierungen mit Variablen](#dynamic-markings-with-variables)                                              | 2010+           | 16.42+     | 2.42+ | 16.0.13328+ | Zu überprüfen |
|[Berechtigungen sofort zuweisen](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Opt-In](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Benutzern die Zuweisung von Berechtigungen überlassen](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | Zu überprüfen   | Zu überprüfen         | Zu überprüfen                                                        |
|[Erste Schritte mit der Datenklassifizierung](data-classification-overview.md) und dem Senden von Daten für Administratoren                      | 2011+ | 16.43+ | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider) | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider) | Ja <sup>\*</sup>                                                        |
|[Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden](#require-users-to-apply-a-label-to-their-email-and-documents)   | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider)             | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider)         | Zu überprüfen   | Roll out: 16.0.13628+ | Zu überprüfen                                            
|[Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)                    | 2009+                                  | Roll out: 16.44+ | Zu überprüfen | Zu überprüfen | [Ja – Opt-In](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Unterstützung der gemeinsamen Dokumenterstellung und automatischen Dokumenterstellung](sensitivity-labels-coauthoring.md) für gekennzeichnete und verschlüsselte Dokumente | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider) | Vorschau: [Betakanal](https://office.com/insider) | Zu überprüfen | Zu überprüfen | [Ja – Opt-In](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Fußnote:**

<sup>\*</sup> Enthält derzeit keinen Begründungstext, um eine Bezeichnung zu entfernen oder die Klassifizierungsebene zu senken.

### <a name="sensitivity-label-capabilities-in-outlook"></a>Funktionen für Vertraulichkeitsbezeichnungen in Outlook

Bei den aufgeführten Nummern handelt es sich um die mindestens erforderliche Office-Anwendungsversion für jede Funktion.

|Funktion                                                                                                        |Outlook für Windows |Outlook für Mac |Outlook unter iOS |Outlook unter Android |Outlook im Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Bezeichnung manuell anwenden, ändern oder entfernen](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Anwenden einer Standardbezeichnung](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Erfordern einer Begründung zum Ändern einer Bezeichnung](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Bereitstellen eines Hilfelinks zu einer benutzerdefinierten Hilfeseite](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Inhalt markieren](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Dynamische Markierungen mit Variablen](#dynamic-markings-with-variables)                                              | Zu überprüfen                     | Zu überprüfen                 | Zu überprüfen         | Zu überprüfen           | Zu überprüfen               |
|[Berechtigungen sofort zuweisen](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Benutzern die Zuweisung von Berechtigungen überlassen](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden](#require-users-to-apply-a-label-to-their-email-and-documents)   | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider))                        | 16.43+ <sup>\*</sup>                    | Zu überprüfen            | Zu überprüfen                | Ja                |
|[Erste Schritte mit der Datenklassifizierung](data-classification-overview.md) und dem Senden von Daten für Administratoren                      | 2011+ | Zu überprüfen | Zu überprüfen           | Zu überprüfen               | Zu überprüfen |
|[Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16.44+ <sup>\*</sup>                    | Zu überprüfen           | Zu überprüfen               | Ja |
|

**Fußnote:**

<sup>\*</sup> Erfordert das [neue Outlook für Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office-integrierter Bezeichnungsclient und andere Bezeichnungslösungen

Der integrierte Office-Bezeichnungsclient lädt Vertraulichkeitsbezeichnungen und Richtlinieneinstellungen für Vertraulichkeitsbezeichnungen aus den folgenden Admin Centern herunter:

- Microsoft 365 Compliance Center
- Microsoft 365 Security Center
- Office 365 Security & Compliance Center

Um den integrierten Office-Bezeichnungsclient verwenden zu [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) können, müssen Sie eine oder mehrere Bezeichnungsrichtlinien für Benutzer aus einem der aufgeführten Admin Center und eine unterstützte Version von [Office veröffentlichen.](#support-for-sensitivity-label-capabilities-in-apps)

Wenn beide Bedingungen erfüllt sind, Sie jedoch den integrierten Office-Bezeichnungsclient deaktivieren müssen, verwenden Sie die folgende Gruppenrichtlinieneinstellung:

1. Navigieren Sie **zu Benutzerkonfiguration/Administrative Vorlagen/Microsoft Office 2016/Sicherheitseinstellungen**.

2. Festlegen **Verwenden Sie das Vertraulichkeitsfeature in Office, um Vertraulichkeitsbezeichnungen** auf 0 anzuwenden und **anzeigen.** 
 
Stellen Sie diese Einstellung mithilfe von Gruppenrichtlinien oder mithilfe des [Office-Cloudrichtliniendiensts zur Verfügung.](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service) Die Einstellung wird wirksam, wenn Office-Apps neu gestartet werden.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Integrierter Office-Bezeichnungsclient und Azure Information Protection-Client

Wenn Benutzer einen der Azure Information Protection-Clients[installiert](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) haben ( Client mit einheitlicher Bezeichnung oder klassischer [Client),](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)ist der integrierte Bezeichnungsclient in seinen Office-Apps standardmäßig deaktiviert. 

Um die integrierte Bezeichnung anstelle des Azure Information Protection-Clients für Office-Apps zu verwenden, verwenden Sie die Anweisungen aus dem vorherigen Abschnitt, legen Sie jedoch die Gruppenrichtlinieneinstellung Verwenden Sie das Vertraulichkeitsfeature **in Office** zum Anwenden und Anzeigen von Vertraulichkeitsbezeichnungen auf **1** ein. 

Alternativ können Sie das Office-Add-In Azure Information Protection deaktivieren oder **entfernen.** Diese Methode eignet sich für einen einzelnen Computer und ad-hoc-Tests. Anweisungen finden Sie unter Anzeigen, Verwalten und [Installieren von Add-Ins in Office-Programmen.](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) 

Wenn Sie dieses Office-Add-In deaktivieren oder entfernen, bleibt der Azure Information Protection-Client installiert, damit Sie Weiterhin Dateien außerhalb Ihrer Office-Apps beschriften können. Beispielsweise mithilfe des Datei-Explorers oder von PowerShell.

Informationen dazu, welche Features von den Azure Information Protection-Clients und dem integrierten Office-Bezeichnungsclient unterstützt werden, finden Sie in der Azure Information Protection-Dokumentation unter Auswählen des für [Windows-Computer](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) zu verwendenden Bezeichnungsclients.

## <a name="office-file-types-supported"></a>Unterstützte Office-Dateitypen

Office-Apps mit integrierter Bezeichnung für Word-, Excel- und PowerPoint-Dateien unterstützen das Open XML-Format (z. B. DOCX und XLSX), aber nicht das Microsoft Office 97-2003-Format (z. B. DOC und XLS), das Open Document Format (z. B. ODT und ODS) oder andere Formate. Wenn ein Dateityp für die integrierte Bezeichnung  nicht unterstützt wird, ist die Schaltfläche Vertraulichkeit in der Office-App nicht verfügbar.

Der Azure Information Protection Unified Labeling Client unterstützt sowohl das Open XML-Format als auch das Microsoft Office 97-2003-Format. Weitere Informationen finden Sie unter [File types supported by the Azure Information Protection unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) from that client's admin guide.

Weitere Bezeichnungslösungen finden Sie in der Dokumentation zu unterstützten Dateitypen.

## <a name="protection-templates-and-sensitivity-labels"></a>Schutzvorlagen und Vertraulichkeitsbezeichnungen

Vom Administrator definierte [Schutzvorlagen,](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)z. B. die, die Sie für die Office 365-Nachrichtenverschlüsselung definieren, werden in Office-Apps nicht angezeigt, wenn Sie die integrierte Bezeichnung verwenden. Diese vereinfachte Erfahrung zeigt, dass keine Schutzvorlage ausgewählt werden muss, da dieselben Einstellungen in Vertraulichkeitsbezeichnungen enthalten sind, für die die Verschlüsselung aktiviert ist.

Wenn Sie vorhandene Schutzvorlagen in Bezeichnungen konvertieren müssen, verwenden Sie das Azure-Portal und die folgenden Anweisungen: So konvertieren Sie Vorlagen [in Bezeichnungen.](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Information Rights Management (IRM)-Optionen und Vertraulichkeitsbezeichnungen

Vertraulichkeitsbezeichnungen, die Sie zum Anwenden der Verschlüsselung konfigurieren, entfernen die Komplexität von Benutzern, um eigene Verschlüsselungseinstellungen anzugeben. In vielen Office-Apps können diese einzelnen Verschlüsselungseinstellungen weiterhin manuell von Benutzern mithilfe von Information Rights Management (IRM)-Optionen konfiguriert werden. Beispiel: Für Windows-Apps:

- For a document: **File**  >  **Info**  >  **Protect Document Restrict**  >  **Access**
- für eine E-Mail: Auf **der** Registerkarte Optionen > **Verschlüsseln** 
  
Wenn Benutzer zunächst ein Dokument oder eine E-Mail beschriften, können sie ihre Bezeichnungskonfigurationseinstellungen immer mit ihren eigenen Verschlüsselungseinstellungen überschreiben. Beispiel:

- Ein Benutzer wendet die **Bezeichnung Vertraulich \ Alle** Mitarbeiter auf ein Dokument an, und diese Bezeichnung ist so konfiguriert, dass Verschlüsselungseinstellungen für alle Benutzer in der Organisation angewendet werden. Dieser Benutzer konfiguriert dann manuell die IRM-Einstellungen, um den Zugriff auf einen Benutzer außerhalb Ihrer Organisation einzuschränken. Das Endergebnis ist ein Dokument mit der Bezeichnung **Vertraulich \ Alle** Mitarbeiter und verschlüsselt, aber Benutzer in Ihrer Organisation können es nicht wie erwartet öffnen.

- Ein Benutzer wendet die **Bezeichnung Vertraulich \ Empfänger nur** auf eine E-Mail an, und diese E-Mail ist so konfiguriert, dass die Verschlüsselungseinstellung Do Not Forward angewendet **wird.** Dieser Benutzer konfiguriert dann manuell die IRM-Einstellungen, sodass die E-Mail uneingeschränkt ist. Das Endergebnis ist, dass die E-Mail von Empfängern weitergeleitet werden kann, obwohl die **Bezeichnung Vertraulich \ Empfänger nur angegeben** ist.

- Ein Benutzer wendet die **Bezeichnung Allgemein** auf ein Dokument an, und diese Bezeichnung ist nicht für die Anwendung der Verschlüsselung konfiguriert. Dieser Benutzer konfiguriert dann manuell die IRM-Einstellungen, um den Zugriff auf das Dokument einzuschränken. Das Endergebnis ist ein Dokument mit der Bezeichnung **Allgemein,** das aber auch Verschlüsselung verwendet, sodass einige Benutzer es nicht wie erwartet öffnen können.

Wenn das Dokument oder die E-Mail bereits beschriftet ist, kann ein Benutzer eine dieser Aktionen ausführen, wenn der Inhalt noch nicht verschlüsselt ist oder das Verwendungsrecht [Export](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) or Full Control hat. 

Um eine konsistentere Bezeichnungserfahrung mit aussagekräftiger Berichterstellung zu erhalten, stellen Sie den Benutzern geeignete Bezeichnungen und Anleitungen zur Verfügung, um nur Bezeichnungen zum Schutz von Dokumenten anzuwenden. Beispiel:

- Für Ausnahmefälle, in denen Benutzer eigene Berechtigungen zuweisen müssen, geben Sie Bezeichnungen an, mit denen Benutzer [ihre eigenen Berechtigungen zuweisen können.](encryption-sensitivity-labels.md#let-users-assign-permissions) 

- Anstatt dass Benutzer die Verschlüsselung manuell entfernen, nachdem sie eine Bezeichnung mit Verschlüsselung ausgewählt haben, stellen Sie eine Sublabelalternative zur Verfügung, wenn Benutzer eine Bezeichnung mit derselben Klassifizierung, aber keine Verschlüsselung benötigen. Beispiel:
    - **Vertraulich \ Alle Mitarbeiter**
    - **Vertraulich \ Jeder (keine Verschlüsselung)**

> [!NOTE]
> Wenn Benutzer die Verschlüsselung aus einem in SharePoint oder OneDrive gespeicherten gekennzeichneten Dokument manuell entfernen und Vertraulichkeitsbezeichnungen für [#A0 in SharePoint](sensitivity-labels-sharepoint-onedrive-files.md)und OneDrive aktiviert haben, wird die Bezeichnungsverschlüsselung beim nächsten Zugriff auf das Dokument oder herunterladen automatisch wiederhergestellt. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Anwenden von Vertraulichkeitsbezeichnungen auf Dateien, E-Mails und Anlagen

Benutzer können jeweils nur eine Bezeichnung für jedes Dokument oder jede E-Mail anwenden.

Wenn Sie eine E-Mail-Nachricht mit Anlagen beschriften, erben die Anlagen die Bezeichnung nur, wenn die Bezeichnung, die Sie auf die E-Mail-Nachricht anwenden, Verschlüsselung angewendet wird und die Anlage ein Office-Dokument ist, das noch nicht verschlüsselt ist. Da die geerbte Bezeichnung Verschlüsselung verwendet, wird die Anlage neu verschlüsselt.

Eine Anlage erbt die Bezeichnungen nicht von der E-Mail-Nachricht, wenn die auf die E-Mail-Nachricht angewendete Bezeichnung keine Verschlüsselung angewendet hat oder die Anlage bereits verschlüsselt ist.

Beispiele für die Vererbung von Bezeichnungen, bei denen die Bezeichnung **Vertraulich** Verschlüsselung und die Bezeichnung **Allgemein** keine Verschlüsselung anwenden:

- Ein Benutzer erstellt eine neue E-Mail-Nachricht und wendet die **Bezeichnung Vertraulich** auf diese Nachricht an. Anschließend fügen sie ein Word-Dokument hinzu, das nicht beschriftet oder verschlüsselt ist. Als Ergebnis der Vererbung wird das Dokument neu als **Vertraulich bezeichnet** und hat nun die Verschlüsselung von dieser Bezeichnung angewendet.

- Ein Benutzer erstellt eine neue E-Mail-Nachricht und wendet die **Bezeichnung Vertraulich** auf diese Nachricht an. Anschließend fügen sie ein Word-Dokument mit der Bezeichnung **Allgemein** hinzu, und diese Datei ist nicht verschlüsselt. Als Ergebnis der Vererbung wird das Dokument als **Vertraulich** umetikettiert und hat jetzt die Verschlüsselung von dieser Bezeichnung angewendet.

## <a name="sensitivity-label-compatibility"></a>Kompatibilität von Vertraulichkeitsbezeichnungen

Mit **RMS-aufgeklärten** Apps: Wenn Sie ein gekennzeichnetes und verschlüsseltes Dokument oder eine verschlüsselte E-Mail in einer [RMS-aufgeklärten](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) Anwendung öffnen, die Vertraulichkeitsbezeichnungen nicht unterstützt, erzwingt die App weiterhin verschlüsselungs- und rechteverwaltung.

Mit dem **Azure Information Protection-Client:** Sie können Vertraulichkeitsbezeichnungen anzeigen und ändern, die Sie mit dem integrierten Office-Bezeichnungsclient auf Dokumente und E-Mails anwenden, indem Sie den Azure Information Protection-Client verwenden und umgekehrt.

**Mit anderen Versionen von Office:** Jeder autorisierte Benutzer kann mit Bezeichnungen versehene Dokumente und E-Mails in anderen Versionen von Office öffnen. Sie können die Bezeichnung jedoch nur in unterstützten Office-Versionen oder mithilfe des Azure Information Protection-Clients anzeigen oder ändern. Unterstützte Office-App-Versionen sind im [vorherigen Abschnitt aufgeführt.](#support-for-sensitivity-label-capabilities-in-apps)

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Unterstützung für SharePoint- und OneDrive-Dateien, die durch Vertraulichkeitsbezeichnungen geschützt sind

Um den integrierten #A0 mit Office im Web für Dokumente in SharePoint oder OneDrive zu verwenden, stellen Sie sicher, dass Sie Vertraulichkeitsbezeichnungen für #A1 in SharePoint und [OneDrive aktiviert haben.](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="support-for-external-users-and-labeled-content"></a>Unterstützung für externe Benutzer und mit Bezeichnungen versehene Inhalte

Wenn Sie ein Dokument oder eine E-Mail-Adresse beschriften, wird die Bezeichnung als Metadaten gespeichert, die Ihren Mandanten und eine Bezeichnungs-GUID enthalten. Wenn ein mit Bezeichnungen versehenes Dokument oder eine E-Mail von einer Office-App geöffnet wird, die Vertraulichkeitsbezeichnungen unterstützt, werden diese Metadaten gelesen, und nur wenn der Benutzer demselben Mandanten angehört, wird die Bezeichnung in ihrer App angezeigt. Bei der integrierten Bezeichnung für Word, PowerPoint und Excel wird beispielsweise der Bezeichnungsname auf der Statusleiste angezeigt. 

Das bedeutet, wenn Sie Dokumente für eine andere Organisation freigeben, die unterschiedliche Bezeichnungsnamen verwendet, kann jede Organisation eine eigene Bezeichnung anwenden und sehen, die auf das Dokument angewendet wird. Die folgenden Elemente einer angewendeten Bezeichnung sind jedoch für Benutzer außerhalb Ihrer Organisation sichtbar:

- Inhaltsmarkierungen. Wenn eine Bezeichnung eine Kopfzeile, Fußzeile oder ein Wasserzeichen an wendet, werden diese direkt dem Inhalt hinzugefügt und bleiben sichtbar, bis sie von jemandem geändert oder gelöscht werden.

- Der Name und die Beschreibung der zugrunde liegenden Schutzvorlage aus einer Bezeichnung, die die Verschlüsselung angewendet hat. Diese Informationen werden oben im Dokument in einer Meldungsleiste angezeigt, um Informationen darüber zu erhalten, wer autorisiert ist, das Dokument zu öffnen, und deren Nutzungsrechte für dieses Dokument.

### <a name="sharing-encrypted-documents-with-external-users"></a>Freigeben verschlüsselter Dokumente für externe Benutzer

Zusätzlich zum Einschränken des Zugriffs auf Benutzer in Ihrer eigenen Organisation können Sie den Zugriff auf jeden anderen Benutzer erweitern, der über ein Konto in Azure Active Directory verfügt. Wenn Ihre Organisation jedoch Richtlinien für bedingten Zugriff verwendet, finden Sie im [nächsten Abschnitt](#conditional-access-policies) weitere Überlegungen.

Alle Office-Apps und andere [RMS-aufklärte](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) Anwendung können verschlüsselte Dokumente öffnen, nachdem der Benutzer erfolgreich authentifiziert wurde. 

Wenn externe Benutzer kein Konto in Azure Active Directory haben, können sie sich mithilfe von Gastkonten in Ihrem Mandanten authentifizieren. Diese Gastkonten können auch für den Zugriff auf freigegebene Dokumente in SharePoint oder OneDrive verwendet werden, wenn Sie Vertraulichkeitsbezeichnungen für #A0 in SharePoint und [OneDrive aktiviert haben:](sensitivity-labels-sharepoint-onedrive-files.md)

- Eine Option ist, diese Gastkonten selbst zu erstellen. Sie können jede E-Mail-Adresse angeben, die diese Benutzer bereits verwenden. Beispielsweise ihre Gmail-Adresse.
    
    Der Vorteil dieser Option besteht in der Einschränkung des Zugriffs und der Rechte auf bestimmte Benutzer, indem Sie ihre E-Mail-Adresse in den Verschlüsselungseinstellungen angeben. Der Nachteil ist der Verwaltungsaufwand für die Kontoerstellung und -koordination mit der Bezeichnungskonfiguration.

- Eine weitere Option besteht in der Verwendung der [SharePoint- und #A0 in Azure AD B2B (Vorschau),](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) sodass Gastkonten automatisch erstellt werden, wenn Ihre Benutzer Links freigeben.
    
    Der Vorteil dieser Option ist ein minimaler Verwaltungsaufwand, da die Konten automatisch erstellt werden, und eine einfachere Bezeichnungskonfiguration. Für dieses Szenario müssen Sie die Verschlüsselungsoption [Alle](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) authentifizierten Benutzer hinzufügen auswählen, da Sie die E-Mail-Adressen nicht im Voraus kennen. Der Nachteil ist, dass Sie mit dieser Einstellung die Zugriffsrechte und Nutzungsrechte nicht auf bestimmte Benutzer beschränken können.

Externe Benutzer können auch ein Microsoft-Konto verwenden, um verschlüsselte Dokumente zu öffnen, wenn sie Windows- und Microsoft 365-Apps (früher[Office 365-Apps)](https://docs.microsoft.com/deployoffice/name-change)oder die eigenständige Version von Office 2019 verwenden. Zuletzt für andere Plattformen unterstützte Microsoft-Konten werden auch zum Öffnen verschlüsselter Dokumente unter macOS (Microsoft 365 Apps, Version 16.42+), Android (Version 16.0.13029+) und iOS (Version 2.42+) unterstützt. Beispielsweise teilt ein Benutzer in Ihrer Organisation ein verschlüsseltes Dokument mit einem Benutzer außerhalb Ihrer Organisation, und die Verschlüsselungseinstellungen geben eine Gmail-E-Mail-Adresse für den externen Benutzer an. Dieser externe Benutzer kann ein eigenes Microsoft-Konto erstellen, das seine Gmail-E-Mail-Adresse verwendet. Anschließend können sie nach der Anmeldung mit diesem Konto das Dokument öffnen und entsprechend den für sie angegebenen Verwendungseinschränkungen bearbeiten. Ein exemplarisches Beispiel für dieses Szenario finden Sie unter Öffnen und Bearbeiten [des geschützten Dokuments](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document).

> [!NOTE]
> Die E-Mail-Adresse für das Microsoft-Konto muss mit der angegebenen E-Mail-Adresse übereinstimmen, um den Zugriff für die Verschlüsselungseinstellungen einzuschränken.

Wenn ein Benutzer mit einem Microsoft-Konto ein verschlüsseltes Dokument auf diese Weise öffnet, wird automatisch ein Gastkonto für den Mandanten erstellt, wenn noch kein Gastkonto mit demselben Namen vorhanden ist. Wenn das Gastkonto vorhanden ist, kann es zum Öffnen von Dokumenten in SharePoint und OneDrive mithilfe von Office im Web verwendet werden, zusätzlich zum Öffnen verschlüsselter Dokumente von den unterstützten Desktop- und mobilen #A0 aus.

Das automatische Gastkonto wird in diesem Szenario aufgrund der Replikationslatenz jedoch nicht sofort erstellt. Wenn Sie persönliche E-Mail-Adressen als Teil Ihrer Bezeichnungsverschlüsselungseinstellungen angeben, wird empfohlen, dass Sie entsprechende Gastkonten in Azure Active Directory erstellen. Teilen Sie diesen Benutzern mit, dass sie dieses Konto verwenden müssen, um ein verschlüsseltes Dokument aus Ihrer Organisation zu öffnen.

> [!TIP]
> Da Sie nicht sicher sein können, ob externe Benutzer eine unterstützte #A0 verwenden, ist die Freigabe von Links aus SharePoint und OneDrive nach dem Erstellen von Gastkonten (für bestimmte Benutzer) oder bei Verwendung der SharePoint- und #A1 in [Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) (für jeden authentifizierten Benutzer) eine zuverlässigere Methode, um eine sichere Zusammenarbeit mit externen Benutzern zu unterstützen.

### <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Wenn Ihre Organisation [Azure Active Directory-Richtlinien](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)für bedingten Zugriff implementiert hat, überprüfen Sie die Konfiguration dieser Richtlinien. Wenn die Richtlinien Azure Information Protection enthalten und die Richtlinie auf externe Benutzer erweitert wird, müssen diese externen Benutzer über ein Gastkonto in Ihrem Mandanten verfügen, auch wenn sie über ein Azure AD-Konto in ihrem eigenen Mandanten verfügen.

Ohne dieses Gastkonto können sie das verschlüsselte Dokument nicht öffnen und eine Fehlermeldung anzeigen. Der Nachrichtentext informiert sie möglicherweise darüber, dass ihr Konto als externer Benutzer im Mandanten hinzugefügt werden muss, mit der falschen Anweisung für dieses Szenario, sich abmelden und sich erneut mit einem anderen **Azure Active Directory-Benutzerkonto** anmelden.

Wenn Sie Gastkonten in Ihrem Mandanten nicht für externe Benutzer erstellen und konfigurieren können, die Dokumente öffnen müssen, die von Ihren Bezeichnungen verschlüsselt sind, müssen Sie Azure Information Protection entweder aus den Richtlinien für bedingten Zugriff entfernen oder externe Benutzer aus den Richtlinien ausschließen.

Weitere Informationen zu bedingten Zugriff und Azure Information Protection, dem verschlüsselungsdienst, der von Vertraulichkeitsbezeichnungen verwendet wird, finden Sie in der häufig gestellten Frage: Azure Information Protection ist als verfügbare Cloud-App für bedingten Zugriff aufgeführt – wie funktioniert [das?](https://docs.microsoft.com/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Anwenden von Inhaltskennzeichnung und -verschlüsselung durch Office-Apps

Office-Apps wenden inhaltskennzeichnung und -verschlüsselung mit einer Vertraulichkeitsbezeichnung je nach verwendeter App unterschiedlich an.

| App | Inhaltskennzeichnung | Verschlüsselung |
| --- | --- | --- |
| Word, Excel, PowerPoint auf allen Plattformen | Sofort | Sofort |
| Outlook für PC und Mac | Nachdem Exchange Online die E-Mail gesendet hat | Sofort |
| Outlook im Web, für iOS und Android | Nachdem Exchange Online die E-Mail gesendet hat | Nachdem Exchange Online die E-Mail gesendet hat |
|

Lösungen, die Vertraulichkeitsbezeichnungen auf Dateien außerhalb von Office-Apps anwenden, verwenden dazu Bezeichnungsmetadaten auf die Datei. In diesem Szenario wird die Inhaltskennzeichnung aus der Konfiguration der Bezeichnung nicht in die Datei eingefügt, sondern die Verschlüsselung angewendet. 

Wenn diese Dateien in einer Office-Desktop-App geöffnet werden, werden die Inhaltsmarkierungen automatisch vom Azure Information Protection Unified Labeling-Client angewendet. Die Inhaltsmarkierungen werden nicht automatisch angewendet, wenn Sie die integrierte Bezeichnung für Desktop-, Mobile- oder Web-Apps verwenden.

Folgende Szenarien umfassen das Anwenden einer Vertraulichkeitsbezeichnung außerhalb von Office-Apps:

- Scanner, Datei-Explorer und PowerShell aus dem Azure Information Protection-Client für einheitliche Bezeichnungen 

- Richtlinien für die automatische Bezeichnung für SharePoint und OneDrive

- Exportierte und verschlüsselte Daten aus Power BI

- Microsoft Cloud App Security

In diesen Szenarien kann ein Benutzer mit integrierter Bezeichnung mithilfe seiner Office-Apps die Inhaltsmarkierungen der Bezeichnung anwenden, indem er die aktuelle Bezeichnung vorübergehend entfernt oder ersetzt und dann die ursprüngliche Bezeichnung erneut verwendet.

### <a name="dynamic-markings-with-variables"></a>Dynamische Markierungen mit Variablen

> [!IMPORTANT]
> Derzeit unterstützen nicht alle Apps auf allen Plattformen dynamische Inhaltsmarkierungen, die Sie für Kopfzeilen, Fußzeilen und Wasserzeichen angeben können. Für Apps, die diese Funktion nicht unterstützen, wenden sie die Markierungen als ursprünglichen Text an, der in der Bezeichnungskonfiguration angegeben ist, anstatt die Variablen zu auflösen.
> 
> Der Azure Information Protection Unified Labeling Client unterstützt dynamische Markierungen. Informationen zu in Office integrierten Bezeichnungen finden Sie in den Tabellen im Abschnitt [Funktionen](#support-for-sensitivity-label-capabilities-in-apps) auf dieser Seite.

Wenn Sie eine Vertraulichkeitsbezeichnung für Inhaltsmarkierungen konfigurieren, können Sie die folgenden Variablen in der Textzeichenfolge für Die Kopfzeile, Fußzeile oder Wasserzeichen verwenden:

| Variable | Beschreibung | Beispiel für die Anwendung von Bezeichnungen |
| -------- | ----------- | ------- |
| `${Item.Label}` | Bezeichnungsanzeigename der angewendeten Bezeichnung| **Allgemein**|
| `${Item.Name}` | Dateiname oder E-Mail-Betreff des zu beschriftenen Inhalts | **Sales.docx** |
| `${Item.Location}` | Pfad und Dateiname des dokuments, das beschriftet wird, oder der E-Mail-Betreff für eine E-Mail, die beschriftet wird | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Anzeigename des Benutzers, der die Bezeichnung angewendet hat| **Richard Simone** |
| `${User.PrincipalName}` | Azure AD-Benutzerprinzipalname (UPN) des Benutzers, der die Bezeichnung angewendet hat | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | Datum und Uhrzeit der Bezeichnung des Inhalts in der lokalen Zeitzone des Benutzers, der die Bezeichnung angewendet hat | **10.08.2020 13:30** |

> [!NOTE]
> Bei der Syntax für diese Variablen wird die Zwischenschreibung beachtet.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Festlegen unterschiedlicher visueller Markierungen für Word, Excel, PowerPoint und Outlook

Als zusätzliche Variable können Sie visuelle Markierungen pro Office-Anwendungstyp konfigurieren, indem Sie eine Variable "If.App" in der Textzeichenfolge verwenden und den Anwendungstyp mithilfe der Werte **Word,** **Excel,** **PowerPoint** oder **Outlook identifizieren.** Sie können diese Werte auch abkürzen, was erforderlich ist, wenn Sie mehrere Werte in derselben If.App-Anweisung angeben möchten.

> [!NOTE]
> Aus Gründen der Vollständigkeit sind Anweisungen für Outlook enthalten, die derzeit jedoch nur vom Azure Information Protection Unified Labeling-Client unterstützt werden.

Verwenden Sie die folgende Syntax:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Wie bei den anderen dynamischen visuellen Markierungen wird bei der Syntax die Kleinschreibung beachtet.

Beispiele:

- **Festlegen von Kopfzeilentext nur für Word-Dokumente:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Nur in Word-Dokumentkopfzeilen wendet die Bezeichnung den Kopfzeilentext "Dieses Word-Dokument ist vertraulich" an. Auf andere Office-Anwendungen wird kein Kopfzeilentext angewendet.

- **Festlegen von Fußzeilentext für Word, Excel und Outlook sowie unterschiedlichen Fußzeilentext für PowerPoint:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    In Word, Excel und Outlook wendet die Bezeichnung den Fußzeilentext "Dieser Inhalt ist vertraulich" an. In PowerPoint wendet die Bezeichnung den Fußzeilentext "Diese Präsentation ist vertraulich" an.

- **Legen Sie bestimmten Wasserzeichentext für Word und PowerPoint und dann Wasserzeichentext für Word, Excel und PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    In Word und PowerPoint wendet die Bezeichnung den Wasserzeichentext "Dieser Inhalt ist vertraulich" an. In Excel wendet die Bezeichnung den Wasserzeichentext "Vertraulich" an. In Outlook wird von der Bezeichnung kein Wasserzeichentext angewendet, da Wasserzeichen als visuelle Markierungen für Outlook nicht unterstützt werden.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden

> [!IMPORTANT]
> Auch als obligatorische Bezeichnung bezeichnet, unterstützen derzeit nicht alle Apps auf allen Plattformen die Richtlinieneinstellung Benutzer zum Anwenden einer Bezeichnung auf ihre E-Mails **und Dokumente verpflichten.**
> 
> Der [Azure Information Protection Unified Labeling-Client](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) unterstützt obligatorische Bezeichnungen und für die [](#support-for-sensitivity-label-capabilities-in-apps) in Office-Apps integrierte Bezeichnung. Weitere Informationen finden Sie in den Tabellen im Abschnitt Funktionen auf dieser Seite.

Wenn diese Richtlinieneinstellung ausgewählt ist, müssen Benutzer, denen die Richtlinie zugewiesen ist, eine Vertraulichkeitsbezeichnung in den folgenden Szenarien auswählen und anwenden:

- Für den Azure Information Protection Unified Labeling-Client:
    - For documents (Word, Excel, PowerPoint): When an unlabeled document is saved or users close the document.
    - For emails (Outlook): At the time users send an unlabeled message.

- Für die in Office-Apps integrierte Bezeichnung:
    - Für Dokumente ((Word, Excel, PowerPoint): Wenn ein nicht gekennzeichnetes Dokument geöffnet oder gespeichert wird.
    - For emails (Outlook): At the time users send an unlabeled email message.

Zusätzliche Informationen für die integrierte Bezeichnung:

- Wenn Benutzer aufgefordert werden, eine Vertraulichkeitsbezeichnung hinzuzufügen, weil sie ein nicht gekennzeichnetes Dokument öffnen, können sie eine Bezeichnung hinzufügen oder das Dokument im schreibgeschützten Modus öffnen.

- Wenn die obligatorische Bezeichnung wirksam ist, können Benutzer Keine Vertraulichkeitsbezeichnungen aus Dokumenten entfernen, sondern eine vorhandene Bezeichnung ändern.

Anleitungen zur Verwendung dieser Einstellung finden Sie in den Informationen zu [Richtlinieneinstellungen](sensitivity-labels.md#what-label-policies-can-do).

## <a name="end-user-documentation"></a>Endbenutzerdokumentation

- [Anwenden von Vertraulichkeits-Beschriftungen auf Ihre Dokumente und E-Mails in Office](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Bekannte Probleme beim Anwenden von Vertraulichkeits-Beschriftungen auf Ihren Office-Dateien](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
