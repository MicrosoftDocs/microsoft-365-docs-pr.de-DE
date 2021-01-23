---
title: Verwenden von Vertraulichkeitsbezeichnungen in Office-Apps
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
description: Erfahren Sie, wie Benutzer mit Vertraulichkeitsbezeichnungen in Office-Apps für Desktop, Mobile und das Web arbeiten und welche Apps Vertraulichkeitsbezeichnungen unterstützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d84735cc51b26df6b4c28ffc3bf8fb99f896f1ae
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925695"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>Verwenden von Vertraulichkeitsbezeichnungen in Office-Apps

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Wenn Sie [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) Vertraulichkeitsbezeichnungen aus dem Microsoft 365 Compliance Center oder einem gleichwertigen Bezeichnungscenter veröffentlicht haben, werden sie in den Office-Apps für Benutzer angezeigt, um Daten zu klassifizieren und zu schützen, während sie erstellt oder bearbeitet werden.

Verwenden Sie die Informationen in diesem Artikel, um Sie bei der erfolgreichen Verwaltung von Vertraulichkeitsbezeichnungen in Office-Apps zu unterstützen. Identifizieren Sie beispielsweise die Mindestversionen von Apps, die Sie für die Unterstützung der integrierten Bezeichnung benötigen, und verstehen Sie die Interaktionen mit dem Azure Information Protection-Client für einheitliche Bezeichnungen und die Kompatibilität mit anderen Apps und Diensten.

## <a name="labeling-client-for-desktop-apps"></a>Bezeichnungsclient für Desktop-Apps

Um Vertraulichkeitsbezeichnungen zu verwenden, die in Office-Desktop-Apps für Windows und Mac integrierte sind, müssen Sie eine Abonnementedition von Office verwenden. Dieser Bezeichnungsclient unterstützt keine eigenständigen Editionen von Office, z. B. Office 2016 oder Office 2019.

Um Vertraulichkeitsbezeichnungen mit diesen eigenständigen Editionen von Office auf Windows-Computern zu verwenden, installieren Sie den [Azure Information Protection-Client für einheitliche Bezeichnungen.](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Unterstützung für Vertraulichkeitsbezeichnungsfunktionen in Apps

Für jede Funktion sind in den folgenden Tabellen die Mindestversion von Office aufgeführt, die Sie benötigen, um Vertraulichkeitsbezeichnungen mithilfe integrierter Bezeichnungen zu unterstützen. Oder wenn sich die Bezeichnungsfunktion in der öffentlichen Vorschau befindet oder für eine zukünftige Version überprüft wird. Verwenden Sie [die Microsoft 365-Roadmap](https://aka.ms/MIPC/Roadmap) für Details zu zukünftigen Versionen.

Neue Versionen von Office-Apps werden zu unterschiedlichen Zeiten für verschiedene Updatekanäle zur Verfügung stellen. Weitere Informationen, einschließlich der Konfiguration Ihres Updatekanals, damit Sie eine neue Bezeichnungsfunktion testen können, die Sie interessieren, finden Sie unter Übersicht über Updatekanäle für [Microsoft 365-Apps.](https://docs.microsoft.com/DeployOffice/overview-update-channels) Neue Funktionen, die sich in der privaten Vorschau befinden, sind nicht in der Tabelle enthalten, aber Sie können möglicherweise an diesen Vorschauen teilnehmen, indem Sie Ihre Organisation für das private Vorschauprogramm von [Microsoft Information Protection nominieren.](https://aka.ms/mip-preview)

> [!NOTE]
> Die Namen der Updatekanäle für Office-Apps wurden kürzlich geändert. Beispielsweise ist monatlicher Kanal jetzt aktueller Kanal, und Office Insider ist jetzt Beta-Kanal. Weitere Informationen finden Sie unter ["Änderungen am Aktualisieren von Kanälen für Microsoft 365-Apps".](https://docs.microsoft.com/deployoffice/update-channels-changes)

Office für iOS und Office für Android: Vertraulichkeitsbezeichnungen sind in die [Office-App integrierte.](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)

Zusätzliche Funktionen sind verfügbar, wenn Sie den Azure Information Protection-Client für einheitliche Bezeichnungen installieren, der nur auf Windows-Computern ausgeführt wird. Weitere Informationen finden Sie unter [Vergleichen der Bezeichnungsclients für Windows-Computer.](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Vertraulichkeitsbezeichnungsfunktionen in Word, Excel und PowerPoint

Die aufgeführten Zahlen sind die mindestversion der Office-Anwendung, die für jede Funktion erforderlich ist.

|Funktion                                                                                                        |Windows |Mac |iOS    |Android      |Netz                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Bezeichnung manuell anwenden, ändern oder entfernen](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Anwenden einer Standardbezeichnung](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Opt-in](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Erfordern einer Begründung zum Ändern einer Bezeichnung](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Bereitstellen eines Hilfelinks zu einer benutzerdefinierten Hilfeseite](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Inhalt markieren](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Dynamische Markierungen mit Variablen](#dynamic-markings-with-variables)                                              | 2010+           | 16,42+     | 2,42+ | 16.0.13328+ | Derzeit überprüft |
|[Berechtigungen sofort zuweisen](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Benutzern die Zuweisung von Berechtigungen überlassen](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16,35+   | Derzeit überprüft   | Derzeit überprüft         | Überprüft                                                        |
|[Anzeigen der Bezeichnungsverwendung mit Bezeichnungsanalysen](label-analytics.md) und Senden von Daten für Administratoren                      | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider)            | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider)        | Überprüft   | Derzeit überprüft         | Ja <sup>\*</sup>                                                        |
|[Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden](sensitivity-labels.md#what-label-policies-can-do)   | Vorschau: Roll out to [Current Channel (Vorschau)](https://office.com/insider)             | Vorschau: Roll out to [Current Channel (Vorschau)](https://office.com/insider)         | Derzeit überprüft   | Vorschau: [Betakanal](https://office.com/insider)         | Derzeit überprüft                                            
|[Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)                    | 2009+                                  | Roll out: 16.44+ | Derzeit überprüft | Derzeit überprüft | [Ja – Opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|Unterstützung [der automatischen](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) Dokumentverfassung und [gemeinsamen](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) Dokumentautorisierung für mit Bezeichnungen versehene und verschlüsselte Dokumente | Überprüft | Überprüft | Überprüft | Derzeit überprüft | [Ja – Opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Fußnote:**

<sup>\*</sup> Enthält derzeit keinen Begründungstext, um eine Bezeichnung zu entfernen oder die Klassifizierungsstufe zu senken.

### <a name="sensitivity-label-capabilities-in-outlook"></a>Funktionen für Vertraulichkeitsbezeichnungen in Outlook

Die aufgeführten Zahlen sind die mindestversion der Office-Anwendung, die für jede Funktion erforderlich ist.

|Funktion                                                                                                        |Outlook für Windows |Outlook für Mac |Outlook unter iOS |Outlook unter Android |Outlook im Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Bezeichnung manuell anwenden, ändern oder entfernen](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Anwenden einer Standardbezeichnung](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Erfordern einer Begründung zum Ändern einer Bezeichnung](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Bereitstellen eines Hilfelinks zu einer benutzerdefinierten Hilfeseite](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Inhalt markieren](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Dynamische Markierungen mit Variablen](#dynamic-markings-with-variables)                                              | Derzeit überprüft                     | Derzeit überprüft                 | Derzeit überprüft         | Derzeit überprüft           | Derzeit überprüft               |
|[Berechtigungen sofort zuweisen](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Benutzern die Zuweisung von Berechtigungen überlassen](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden](#require-users-to-apply-a-label-to-their-email-and-documents)   | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider))                        | 16,43+                     | Überprüft            | Derzeit überprüft                | Ja                |
|[Anzeigen der Bezeichnungsverwendung mit Bezeichnungsanalysen](label-analytics.md) und Senden von Daten für Administratoren                      | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider)                       | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider)                    | Derzeit überprüft           | Derzeit überprüft               | Ja               |
|[Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16,44+                    | Derzeit überprüft           | Derzeit überprüft               | Ja |
|


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Integrierter Office-Bezeichnungsclient und andere Bezeichnungslösungen

Der integrierte Office-Bezeichnungsclient lädt Vertraulichkeitsbezeichnungen und Richtlinieneinstellungen für Vertraulichkeitsbezeichnungen aus den folgenden Admin Centern herunter:

- Microsoft 365 Compliance Center
- Microsoft 365 Security Center
- Office 365 Security & Compliance Center

Um den integrierten Office-Bezeichnungsclient zu verwenden, [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) müssen Sie eine oder mehrere Bezeichnungsrichtlinien für Benutzer aus einem der aufgelisteten Admin Center und eine unterstützte Version von [Office veröffentlichen.](#support-for-sensitivity-label-capabilities-in-apps)

Wenn beide Bedingungen erfüllt sind, Sie jedoch den integrierten Office-Bezeichnungsclient deaktivieren müssen, verwenden Sie die folgende Gruppenrichtlinieneinstellung:

1. Navigieren Sie **zu Benutzerkonfiguration/Administrative Vorlagen/Microsoft Office 2016/Sicherheitseinstellungen.**

2. Legen **Sie die Vertraulichkeitsfunktion in Office zum Anwenden und Anzeigen von Vertraulichkeitsbezeichnungen** auf **0 .** 
 
Stellen Sie diese Einstellung mithilfe von Gruppenrichtlinien oder mithilfe des [Office-Cloudrichtliniendiensts zur Verfügung.](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service) Die Einstellung wird beim Neustart von Office-Apps wirksam.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Integrierter Office-Bezeichnungsclient und der Azure Information Protection-Client

Wenn Benutzer einen der Azure Information Protection-Clients[installiert](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) haben (Client mit einheitlichen Bezeichnungen oder klassischer [Client),](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)ist der integrierte Bezeichnungsclient in ihren Office-Apps standardmäßig deaktiviert. 

Um integrierte Bezeichnungen anstelle des Azure Information Protection-Clients für Office-Apps zu verwenden, befolgen Sie die Anweisungen aus dem vorherigen Abschnitt, legen Sie jedoch die Gruppenrichtlinieneinstellung "Vertraulichkeitsfeature **in Office** verwenden" zum Anwenden und Anzeigen von Vertraulichkeitsbezeichnungen auf **1**. 

Alternativ können Sie das Office-Add-In Azure Information Protection deaktivieren **oder entfernen.** Diese Methode eignet sich für einen einzelnen Computer und Ad-hoc-Tests. Anweisungen finden Sie unter Anzeigen, Verwalten und [Installieren von Add-Ins in Office-Programmen.](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) 

Wenn Sie dieses Office-Add-In deaktivieren oder entfernen, bleibt der Azure Information Protection-Client installiert, sodass Sie weiterhin Dateien außerhalb Ihrer Office-Apps beschriften können. Beispielsweise mithilfe des Datei-Explorers oder powerShell.

Informationen dazu, welche Features von den Azure Information Protection-Clients und dem [](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) integrierten Office-Bezeichnungsclient unterstützt werden, finden Sie in der Azure Information Protection-Dokumentation unter "Auswählen des für Windows-Computer zu verwendenden Bezeichnungsclients".

## <a name="office-file-types-supported"></a>Unterstützte Office-Dateitypen

Office-Apps mit integrierter Bezeichnung für Word-, Excel- und PowerPoint-Dateien unterstützen das Open XML-Format (z. B. DOCX und XLSX), aber nicht das Microsoft Office 97-2003-Format (z. B. DOC und XLS). Wenn ein Dateityp für die integrierte Bezeichnung  nicht unterstützt wird, ist die Schaltfläche "Vertraulichkeit" in der Office-App nicht verfügbar.

Der Azure Information Protection-Client für einheitliche Bezeichnungen unterstützt sowohl das Open XML-Format als auch das Microsoft Office 97-2003-Format. Weitere Informationen finden Sie im Administratorhandbuch dieses Clients unter Dateitypen, die vom [Azure Information Protection-Client](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) für einheitliche Bezeichnungen unterstützt werden.

Weitere Bezeichnungslösungen finden Sie in der Dokumentation zu unterstützten Dateitypen.

## <a name="protection-templates-and-sensitivity-labels"></a>Schutzvorlagen und Vertraulichkeitsbezeichnungen

Vom Administrator definierte [Schutzvorlagen,](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)z. B. die, die Sie für die Office 365-Nachrichtenverschlüsselung definieren, sind in Office-Apps nicht sichtbar, wenn Sie integrierte Bezeichnungen verwenden. Diese vereinfachte Erfahrung zeigt, dass keine Schutzvorlage ausgewählt werden muss, da die gleichen Einstellungen in Vertraulichkeitsbezeichnungen mit aktivierter Verschlüsselung enthalten sind.

Wenn Sie vorhandene Schutzvorlagen in Bezeichnungen konvertieren müssen, verwenden Sie das Azure-Portal und die folgenden Anweisungen: Um Vorlagen in [Bezeichnungen zu konvertieren.](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Optionen und Vertraulichkeitsbezeichnungen für die Verwaltung von Informationsrechten (Information Rights Management, IRM)

Vertraulichkeitsbezeichnungen, die Sie zum Anwenden der Verschlüsselung konfigurieren, entfernen die Komplexität der Benutzer, ihre eigenen Verschlüsselungseinstellungen anzugeben. In vielen Office-Apps können diese einzelnen Verschlüsselungseinstellungen weiterhin manuell von Benutzern mithilfe von Information Rights Management (IRM)-Optionen konfiguriert werden. Beispiel für Windows-Apps:

- For a document: **File**  >  **Info**  >  **Protect Document** Restrict  >  **Access**
- für eine E-Mail: Auf der Registerkarte **"Optionen"** > **Verschlüsseln** 
  
Wenn Benutzer ein Dokument oder eine E-Mail anfänglich mit Bezeichnungen versehen, können sie ihre Bezeichnungskonfigurationseinstellungen immer mit ihren eigenen Verschlüsselungseinstellungen überschreiben. Zum Beispiel:

- Ein Benutzer wendet die Bezeichnung **"Vertraulich \** Alle Mitarbeiter" auf ein Dokument an, und diese Bezeichnung ist so konfiguriert, dass Verschlüsselungseinstellungen für alle Benutzer in der Organisation angewendet werden. Dieser Benutzer konfiguriert dann manuell die IRM-Einstellungen, um den Zugriff auf einen Benutzer außerhalb Ihrer Organisation einzuschränken. Das Endergebnis ist ein Dokument mit der Bezeichnung "Vertraulich **\** Alle Mitarbeiter und verschlüsselt", aber Benutzer in Ihrer Organisation können es nicht wie erwartet öffnen.

- Ein Benutzer wendet die Bezeichnung **"Vertraulich \** Empfänger nur" auf eine E-Mail an, und diese E-Mail ist so konfiguriert, dass die Verschlüsselungseinstellung **"Nicht weiterleiten" angewendet wird.** Dieser Benutzer konfiguriert dann manuell die IRM-Einstellungen, sodass die E-Mail uneingeschränkt ist. Das Endergebnis ist, dass die E-Mail von Empfängern weitergeleitet werden kann, obwohl die Bezeichnung "Vertraulich **\ Empfänger nur" angegeben** ist.

- Ein Benutzer wendet die **Bezeichnung "Allgemein"** auf ein Dokument an, und diese Bezeichnung ist nicht für die Verschlüsselung konfiguriert. Dieser Benutzer konfiguriert dann manuell die IRM-Einstellungen, um den Zugriff auf das Dokument einzuschränken. Das Endergebnis ist ein Dokument  mit der Bezeichnung "Allgemein", das aber auch Verschlüsselung verwendet, sodass einige Benutzer es nicht wie erwartet öffnen können.

Wenn das Dokument oder die E-Mail bereits mit bezeichnungen versehen ist, kann ein Benutzer eine dieser Aktionen ausführen, wenn der Inhalt noch nicht verschlüsselt ist oder wenn er über das Verwendungsrecht ["Exportieren"](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) oder "Vollschutz" verfügen. 

Stellen Sie für eine konsistentere Bezeichnungserfahrung mit aussagekräftiger Berichterstellung geeignete Bezeichnungen und Anleitungen für Benutzer zur Verfügung, um nur Bezeichnungen zum Schutz von Dokumenten anzuwenden. Zum Beispiel:

- Stellen Sie für Ausnahmefälle, in denen Benutzer eigene Berechtigungen zuweisen müssen, Bezeichnungen zur Verfügung, mit denen Benutzer [ihre eigenen Berechtigungen zuweisen können.](encryption-sensitivity-labels.md#let-users-assign-permissions) 

- Anstatt Benutzer die Verschlüsselung manuell zu entfernen, nachdem sie eine Bezeichnung mit Verschlüsselung ausgewählt haben, stellen Sie eine Alternative zu Einerbezeichnungen zur Verfügung, wenn Benutzer eine Bezeichnung mit derselben Klassifizierung, aber ohne Verschlüsselung benötigen. Beispiel:
    - **Vertraulich \ Alle Mitarbeiter**
    - **Vertraulich \ Jeder (keine Verschlüsselung)**

> [!NOTE]
> Wenn Benutzer die Verschlüsselung manuell aus einem mit Bezeichnungen versehenen Dokument entfernen, das in SharePoint oder OneDrive gespeichert ist, und Sie Vertraulichkeitsbezeichnungen für #A0 [in SharePoint](sensitivity-labels-sharepoint-onedrive-files.md)und OneDrive aktiviert haben, wird die Bezeichnungsverschlüsselung automatisch wiederhergestellt, wenn das Dokument das nächste Mal zugegriffen oder heruntergeladen wird. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Anwenden von Vertraulichkeitsbezeichnungen auf Dateien, E-Mails und Anlagen

Benutzer können für jedes Dokument oder jede E-Mail jeweils nur eine Bezeichnung anwenden.

Wenn Sie eine E-Mail-Nachricht mit Anlagen beschriften, erben die Anlagen die Bezeichnung nicht mit einer Ausnahme:

- Die Anlage ist ein Office-Dokument mit einer Bezeichnung, die keine Verschlüsselung angewendet hat, und die Bezeichnung, die Sie auf die E-Mail-Nachricht anwenden, wendet Verschlüsselung an. In diesem Fall erbt das per E-Mail gesendete Dokument die Bezeichnung der E-Mail mit den Verschlüsselungseinstellungen.

Andernfalls: 

- Wenn die Anlagen über eine Bezeichnung verfügen, behalten sie ihre ursprünglich angewendete Bezeichnung bei.
- Wenn die Anlagen ohne Bezeichnung verschlüsselt werden, bleibt die Verschlüsselung erhalten, sie werden jedoch nicht mit Bezeichnungen versehen.
- Wenn die Anlagen keine Bezeichnung haben, bleiben sie unbeschriftet.

## <a name="sensitivity-label-compatibility"></a>Kompatibilität von Vertraulichkeitsbezeichnungen

Mit RMS-enaktivierten Apps: Wenn Sie ein mit Bezeichnungen versehenes und verschlüsseltes Dokument oder eine verschlüsselte [E-Mail](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) in einer RMS-enaktivierten Anwendung öffnen, die Vertraulichkeitsbezeichnungen nicht unterstützt, erzwingt die App weiterhin Verschlüsselung und Rechteverwaltung. 

Mit dem **Azure Information Protection-Client:** Sie können Vertraulichkeitsbezeichnungen anzeigen und ändern, die Sie mit dem integrierten Office-Bezeichnungsclient auf Dokumente und E-Mails anwenden, indem Sie den Azure Information Protection-Client verwenden und umgekehrt.

**Mit anderen Versionen von Office:** Jeder autorisierte Benutzer kann mit Bezeichnungen versehene Dokumente und E-Mails in anderen Versionen von Office öffnen. Sie können die Bezeichnung jedoch nur in unterstützten Versionen von Office oder mithilfe des Azure Information Protection-Clients anzeigen oder ändern. Unterstützte Office-App-Versionen sind im [vorherigen Abschnitt aufgeführt.](#support-for-sensitivity-label-capabilities-in-apps)

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Unterstützung für SharePoint- und OneDrive-Dateien, die durch Vertraulichkeitsbezeichnungen geschützt sind

Um den integrierten #A0 mit Office im Web für Dokumente in SharePoint oder OneDrive zu verwenden, stellen Sie sicher, dass Sie Vertraulichkeitsbezeichnungen für #A1 in SharePoint und [OneDrive aktiviert haben.](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="support-for-external-users-and-labeled-content"></a>Unterstützung für externe Benutzer und mit Bezeichnungen versehene Inhalte

Wenn Sie ein Dokument oder eine E-Mail beschriften, wird die Bezeichnung als Metadaten gespeichert, die Ihren Mandanten und eine Bezeichnungs-GUID enthalten. Wenn ein mit Bezeichnungen versehenes Dokument oder eine E-Mail von einer Office-App geöffnet wird, die Vertraulichkeitsbezeichnungen unterstützt, werden diese Metadaten gelesen, und nur wenn der Benutzer demselben Mandanten angehört, wird die Bezeichnung in der App angezeigt. Beispielsweise wird für die integrierte Bezeichnung für Word, PowerPoint und Excel der Bezeichnungsname auf der Statusleiste angezeigt. 

Wenn Sie Also Dokumente für eine andere Organisation freigeben, die unterschiedliche Bezeichnungsnamen verwendet, kann jede Organisation eine eigene Bezeichnung anwenden und sehen, die auf das Dokument angewendet wird. Die folgenden Elemente einer angewendeten Bezeichnung sind jedoch für Benutzer außerhalb Ihrer Organisation sichtbar:

- Inhaltsmarkierungen. Wenn eine Bezeichnung eine Kopfzeile, Fußzeile oder ein Wasserzeichen hinzuf?scht, werden diese direkt dem Inhalt hinzugefügt und bleiben sichtbar, bis sie von jemandem geändert oder gelöscht werden.

- Der Name und die Beschreibung der zugrunde liegenden Schutzvorlage aus einer Bezeichnung, die Verschlüsselung angewendet hat. Diese Informationen werden in einer Meldungsleiste am oberen Rand des Dokuments angezeigt, um Informationen darüber, wer zum Öffnen des Dokuments autorisiert ist, sowie deren Nutzungsrechte für dieses Dokument zur Verfügung zu stellen.

### <a name="sharing-encrypted-documents-with-external-users"></a>Freigeben verschlüsselter Dokumente für externe Benutzer

Zusätzlich zur Einschränkung des Zugriffs auf Benutzer in Ihrer eigenen Organisation können Sie den Zugriff auf alle anderen Benutzer erweitern, die über ein Konto in Azure Active Directory verfügen. Alle Office-Apps und andere [RMS-freundliche](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) Anwendungen können verschlüsselte Dokumente öffnen, nachdem der Benutzer sich erfolgreich authentifiziert hat.

Wenn externe Benutzer kein Konto in Azure Active Directory haben, können sie sich mithilfe von Gastkonten in Ihrem Mandanten authentifizieren. Diese Gastkonten können auch für den Zugriff auf freigegebene Dokumente in SharePoint oder OneDrive verwendet werden, wenn Sie Vertraulichkeitsbezeichnungen für #A0 [in SharePoint und OneDrive aktiviert haben:](sensitivity-labels-sharepoint-onedrive-files.md)

- Eine Möglichkeit ist, diese Gastkonten selbst zu erstellen. Sie können eine beliebige E-Mail-Adresse angeben, die diese Benutzer bereits verwenden. Beispiel: ihre Gmail-Adresse.
    
    Der Vorteil dieser Option besteht in der Einschränkung des Zugriffs und der Rechte auf bestimmte Benutzer, indem Sie ihre E-Mail-Adresse in den Verschlüsselungseinstellungen angeben. Der Nachteil ist der Verwaltungsaufwand für die Kontoerstellung und -koordination mit der Bezeichnungskonfiguration.

- Eine weitere Option besteht in der Verwendung der SharePoint- und #A0 [in Azure AD B2B (Vorschau),](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) sodass Gastkonten automatisch erstellt werden, wenn Ihre Benutzer Links freigeben.
    
    Der Vorteil dieser Option ist ein minimaler Verwaltungsaufwand, da die Konten automatisch erstellt werden, und eine einfachere Bezeichnungskonfiguration. In diesem Szenario müssen Sie [](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) die Verschlüsselungsoption "Authentifizierten Benutzer hinzufügen" auswählen, da Sie die E-Mail-Adressen nicht im Voraus kennen. Der Nachteil ist, dass Sie mit dieser Einstellung die Zugriffsrechte und Nutzungsrechte nicht auf bestimmte Benutzer beschränken können.

Externe Benutzer können auch ein Microsoft-Konto für verschlüsselte Dokumente verwenden, wenn sie Microsoft 365-Apps (früher[Office 365-Apps)](https://docs.microsoft.com/deployoffice/name-change)unter Windows verwenden und neu unter macOS (Version 16.42+ unterstützt), Android (Version 16.0.13029+) und iOS (Version 2.42+ ) verwenden. Beispielsweise gibt jemand ein verschlüsseltes Dokument für sie weiter, und die Verschlüsselungseinstellungen geben ihre Gmail-E-Mail-Adresse an. Dieser Benutzer kann ein eigenes Microsoft-Konto erstellen, das seine Gmail-E-Mail-Adresse verwendet. Nach der Anmeldung mit diesem Konto können sie dann das Dokument öffnen und entsprechend den für diesen Benutzer angegebenen Verwendungseinschränkungen bearbeiten. Ein Exemplarische Vorgehensweisenbeispiel für dieses Szenario finden Sie unter [Öffnen und Bearbeiten des geschützten Dokuments.](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)

> [!NOTE]
> Die E-Mail-Adresse für das Microsoft-Konto muss mit der angegebenen E-Mail-Adresse übereinstimmen, um den Zugriff auf die Verschlüsselungseinstellungen einzuschränken.

Wenn ein Benutzer mit einem Microsoft-Konto ein verschlüsseltes Dokument auf diese Weise öffnet, wird automatisch ein Gastkonto für den Mandanten erstellt, wenn noch kein Gastkonto mit demselben Namen vorhanden ist. Wenn das Gastkonto vorhanden ist, kann es zum Öffnen von Dokumenten in SharePoint und OneDrive mithilfe eines Browsers (Office im Web) sowie zum Öffnen verschlüsselter Dokumente aus der Windows-Desktop-App verwendet werden. 

Das automatische Gastkonto wird in diesem Szenario aufgrund der Replikationslatenz jedoch nicht sofort erstellt. Wenn Sie persönliche E-Mail-Adressen als Teil der Verschlüsselungseinstellungen für Bezeichnungen angeben, wird empfohlen, dass Sie entsprechende Gastkonten in Azure Active Directory erstellen. Teilen Sie diesen Benutzern dann mit, dass sie dieses Konto verwenden müssen, um ein verschlüsseltes Dokument aus Ihrer Organisation zu öffnen.

> [!TIP]
> Da Sie nicht sicher sein können, dass externe Benutzer eine unterstützte #A0 verwenden, ist die Freigabe von Links aus SharePoint und OneDrive nach dem Erstellen von Gastkonten (für bestimmte Benutzer) oder bei Verwendung der SharePoint- und #A1 in [Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) (für jeden authentifizierten Benutzer) eine zuverlässigere Methode zur Unterstützung der sicheren Zusammenarbeit mit externen Benutzern.

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Anwenden von Inhaltskennzeichnung und -verschlüsselung durch Office-Apps

In Office-Apps wird die Inhaltskennzeichnung und -verschlüsselung mit einer Vertraulichkeitsbezeichnung je nach verwendeter App unterschiedlich angewendet.

| App | Inhaltskennzeichnung | Verschlüsselung |
| --- | --- | --- |
| Word, Excel, PowerPoint auf allen Plattformen | Sofort | Sofort |
| Outlook für PC und Mac | Nachdem Exchange Online die E-Mail gesendet hat | Sofort |
| Outlook im Web, für iOS und Android | Nachdem Exchange Online die E-Mail gesendet hat | Nachdem Exchange Online die E-Mail gesendet hat |
|

Lösungen, die Vertraulichkeitsbezeichnungen auf Dateien außerhalb von Office-Apps anwenden, wenden bezeichnungsmetadaten auf die Datei an. In diesem Szenario wird die Inhaltskennzeichnung aus der Konfiguration der Bezeichnung nicht in die Datei eingefügt, sondern die Verschlüsselung angewendet. 

Wenn diese Dateien in einer Office-Desktop-App geöffnet werden, werden die Inhaltsmarkierungen automatisch vom Azure Information Protection-Client für einheitliche Bezeichnungen angewendet. Die Inhaltskennzeichnungen werden nicht automatisch angewendet, wenn Sie integrierte Bezeichnungen für Desktop-, Mobile- oder Web-Apps verwenden.

Folgende Szenarien umfassen das Anwenden einer Vertraulichkeitsbezeichnung außerhalb von Office-Apps:

- Scanner, Datei-Explorer und PowerShell aus dem Azure Information Protection-Client für einheitliche Bezeichnungen 

- Richtlinien für die automatische Bezeichnung für SharePoint und OneDrive

- Exportierte mit Bezeichnungen versehene und verschlüsselte Daten aus Power BI

- Microsoft Cloud App-Sicherheit

In diesen Szenarien kann ein Benutzer mit integrierter Bezeichnung mithilfe seiner Office-Apps die Inhaltskennzeichnungen der Bezeichnung anwenden, indem er die aktuelle Bezeichnung vorübergehend entfernt oder ersetzt und dann die ursprüngliche Bezeichnung erneut anwenden.

### <a name="dynamic-markings-with-variables"></a>Dynamische Markierungen mit Variablen

> [!IMPORTANT]
> Derzeit unterstützen nicht alle Apps auf allen Plattformen dynamische Inhaltsmarkierungen, die Sie für Ihre Kopf-, Fuß- und Wasserzeichen angeben können. Für Apps, die diese Funktion nicht unterstützen, wenden sie die Markierungen als originalen Text an, der in der Bezeichnungskonfiguration angegeben ist, anstatt die Variablen auflösbar zu machen.
> 
> Der Azure Information Protection-Client für einheitliche Bezeichnungen unterstützt dynamische Markierungen. Informationen zu in Office integrierten Bezeichnungen finden Sie in den Tabellen im Abschnitt ["Funktionen"](#support-for-sensitivity-label-capabilities-in-apps) auf dieser Seite.

Wenn Sie eine Vertraulichkeitsbezeichnung für Inhaltsmarkierungen konfigurieren, können Sie die folgenden Variablen in der Textzeichenfolge für Die Kopfzeile, Fußzeile oder Wasserzeichen verwenden:

| Variable | Beschreibung | Beispiel für angewendete Bezeichnung |
| -------- | ----------- | ------- |
| `${Item.Label}` | Bezeichnungsanzeigename der angewendeten Bezeichnung| **Allgemein**|
| `${Item.Name}` | Dateiname oder E-Mail-Betreff des Mitbeschriftungsinhalts | **Sales.docx** |
| `${Item.Location}` | Pfad und Dateiname des Dokuments, das mit bezeichnungen versehen wird, oder der E-Mail-Betreff für eine E-Mail, die mit einer Bezeichnung versehen wird | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Anzeigename des Benutzers, der die Bezeichnung angewendet hat| **Richard Simone** |
| `${User.PrincipalName}` | Azure AD User Principal Name (UPN) des Benutzers, der die Bezeichnung angewendet hat | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | Datum und Uhrzeit der Bezeichnung des Inhalts in der lokalen Zeitzone des Benutzers, der die Bezeichnung angewendet hat | **10.8.2020 13:30** |

> [!NOTE]
> Bei der Syntax für diese Variablen wird die Kleinschreibung beachtet.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Festlegen unterschiedlicher visueller Markierungen für Word, Excel, PowerPoint und Outlook

Als zusätzliche Variable können Sie visuelle Markierungen pro Office-Anwendungstyp konfigurieren, indem Sie eine "If.App"-Variable-Anweisung in der Textzeichenfolge verwenden und den Anwendungstyp mithilfe der Werte **Word,** **Excel,** **PowerPoint** oder **Outlook** identifizieren. Sie können diese Werte auch abkürzen, was erforderlich ist, wenn Sie mehrere Werte in derselben If.App-Anweisung angeben möchten.

> [!NOTE]
> Der Vollständigkeit halber sind Anweisungen für Outlook enthalten, die derzeit jedoch nur vom Azure Information Protection-Client für einheitliche Bezeichnungen unterstützt werden.

Verwenden Sie die folgende Syntax:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Wie bei den anderen dynamischen visuellen Markierungen wird bei der Syntax die Kleinschreibung beachtet.

Beispiele:

- **Festlegen von Kopfzeilentext nur für Word-Dokumente:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Nur in Word-Dokumentkopfzeilen wendet die Beschriftung den Kopfzeilentext "Dieses Word-Dokument ist vertraulich" an. Auf andere Office-Anwendungen wird kein Kopfzeilentext angewendet.

- **Festlegen von Fußzeilentext für Word, Excel und Outlook sowie unterschiedlichen Fußzeilentext für PowerPoint:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    In Word, Excel und Outlook wendet die Bezeichnung den Fußzeilentext "Dieser Inhalt ist vertraulich" an. In PowerPoint wendet die Bezeichnung den Fußzeilentext "Diese Präsentation ist vertraulich" an.

- **Legen Sie bestimmten Wasserzeichentext für Word und PowerPoint und dann wasserzeichentext für Word, Excel und PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    In Word und PowerPoint wendet die Bezeichnung den Wasserzeichentext "Dieser Inhalt ist vertraulich" an. In Excel wendet die Bezeichnung den Wasserzeichentext "Vertraulich" an. In Outlook wird für die Bezeichnung kein Wasserzeichentext angewendet, da Wasserzeichen als visuelle Markierungen für Outlook nicht unterstützt werden.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden

> [!IMPORTANT]
> Auch als obligatorische Bezeichnung bezeichnet, unterstützen nicht alle Apps auf allen Plattformen derzeit die Richtlinieneinstellung "Benutzer zum Anwenden einer Bezeichnung auf ihre E-Mails und **Dokumente verpflichten".**
> 
> Der [Azure Information Protection-Client](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) für einheitliche Bezeichnungen unterstützt obligatorische Bezeichnungen und für [](#support-for-sensitivity-label-capabilities-in-apps) in Office-Apps integrierte Bezeichnungen. Weitere Informationen finden Sie in den Tabellen im Abschnitt "Funktionen" auf dieser Seite.

Wenn diese Richtlinieneinstellung ausgewählt ist, müssen benutzer, denen die Richtlinie zugewiesen ist, in den folgenden Szenarien eine Vertraulichkeitsbezeichnung auswählen und anwenden:

- Für den Azure Information Protection-Client für einheitliche Bezeichnungen:
    - Für Dokumente (Word, Excel, PowerPoint): Wenn ein unbeschriftetes Dokument gespeichert wird oder Benutzer das Dokument schließen.
    - Für E-Mails (Outlook): Zu dem Zeitpunkt, zu dem Benutzer eine unbeschriftete Nachricht senden.

- Für in Office-Apps integrierte Bezeichnungen:
    - Für Dokumente (Word, Excel, PowerPoint): Wenn ein unbeschriftetes Dokument geöffnet oder gespeichert wird.
    - Für E-Mails (Outlook): Zu dem Zeitpunkt, zu dem Benutzer eine unbeschriftete E-Mail-Nachricht senden.

Zusätzliche Informationen für integrierte Bezeichnungen:

- Wenn Benutzer aufgefordert werden, eine Vertraulichkeitsbezeichnung hinzuzufügen, weil sie ein unbeschriftetes Dokument öffnen, können sie eine Bezeichnung hinzufügen oder das Dokument im schreibgeschützten Modus öffnen.

- Wenn die obligatorische Bezeichnung in Kraft ist, können Benutzer Vertraulichkeitsbezeichnungen nicht aus Dokumenten entfernen, sondern eine vorhandene Bezeichnung ändern.

## <a name="end-user-documentation"></a>Dokumentation für Endbenutzer

- [Anwenden von Vertraulichkeits-Beschriftungen auf Ihre Dokumente und E-Mails in Office](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Bekannte Probleme beim Anwenden von Vertraulichkeits-Beschriftungen auf Ihren Office-Dateien](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
