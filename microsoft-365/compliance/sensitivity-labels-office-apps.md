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
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informationen für IT-Administratoren zur Verwaltung von Vertraulichkeitsbezeichnungen in Office-Apps für Desktop, Mobilgeräte und das Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a9755542b608c8ed7d3cd93bebbd764fd56b9768
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332714"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Verwalten von Vertraulichkeitsbezeichnungen in Office-Apps

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Wenn Sie Vertraulichkeitsbezeichnungen über das Microsoft 365 Compliance Center oder ein gleichwertiges Bezeichnungszentrum [veröffentlicht](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) haben, werden sie in Office-Apps angezeigt, damit die Benutzer Daten bei der Erstellung oder Bearbeitung klassifizieren und schützen können.

Verwenden Sie die Informationen in diesem Artikel, um Vertraulichkeitsbezeichnungen in Office-Apps erfolgreich zu verwalten. Ermitteln Sie z. B. die Mindestversionen von Apps, die Sie zur Unterstützung der integrierten Kennzeichnung benötigen, und verstehen Sie die Interaktionen mit dem Bezeichnungs-Assistent von Azure Information Protection und die Kompatibilität mit anderen Apps und Diensten.

## <a name="labeling-client-for-desktop-apps"></a>Bezeichnungs-Assistent für Desktop-Anwendungen

Um die in den Office-Desktop-Apps für Windows und Mac integrierten Vertraulichkeitsbezeichnungen zu verwenden, müssen Sie eine Abonnement-Edition von Office verwenden. Dieser Bezeichnungs-Assistent unterstützt keine eigenständige Editionen von Office, wie Office 2016 oder Office 2019.

Um Vertraulichkeitsbezeichnungen mit diesen eigenständigen Editionen von Office auf Windows-Computern zu verwenden, installieren Sie den [Bezeichnungs-Assistent von Azure Information Protection](/azure/information-protection/rms-client/aip-clientv2).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Unterstützung für Vertraulichkeitsbezeichnungen in Apps

In den folgenden Tabellen ist für jede Funktion die minimale Office-Version aufgeführt, die Sie benötigen, um Vertraulichkeitsbezeichnungen mithilfe der integrierten Beschriftung zu unterstützen. Oder, wenn die Bezeichnungsfunktion in der öffentlichen Vorschau ist oder für eine zukünftige Version geprüft wird. Verwenden Sie die [Microsoft 365-Roadmap](https://aka.ms/MIPC/Roadmap) für Details zu zukünftigen Versionen.

Neue Versionen von Office-Apps werden zu unterschiedlichen Zeiten für verschiedene Updatekanäle zur Verfügung gestellt. Weitere Informationen, u. a. wie Sie Ihren Updatekanal so konfigurieren, dass Sie eine neue Bezeichnungsfunktion, die Sie interessiert, testen können, finden Sie unter [Übersicht der Updatekanäle für Microsoft 365 Apps](/DeployOffice/overview-update-channels). Neue Funktionen, die sich in der privaten Vorschau befinden, sind in der Tabelle nicht enthalten, aber Sie können möglicherweise an diesen Vorschauen teilnehmen, indem Sie Ihre Organisation für das [private Vorschau-Programm von Microsoft Information Protection nominieren](https://aka.ms/mip-preview).

> [!NOTE]
> Die Namen der Updatekanäle für Office-Apps haben sich kürzlich geändert. Zum Beispiel ist der monatliche Kanal jetzt der aktuelle Kanal und der Office Insider ist jetzt der Betakanal. Weitere Informationen finden Sie unter [Änderungen an den Updatekanälen für Microsoft 365 Apps](/deployoffice/update-channels-changes).

Office für iOS und Office für Android: Vertraulichkeitsbezeichnungen sind in die [Office-App](https://www.microsoft.com/de-DE/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/) integriert.

Zusätzliche Funktionen sind verfügbar, wenn Sie den Bezeichnungs-Assistent von Azure Information Protection installieren, der nur auf Windows-Computern läuft. Weitere Informationen finden Sie unter [Vergleichen der Bezeichnungs-Assistenten für Windows-Computer](/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Funktionen für Vertraulichkeitsbezeichnungen in Word, Excel und PowerPoint

Die aufgelisteten Zahlen sind die minimale Office-Anwendungsversion, die für jede Funktion erforderlich ist.

|Funktion                                                                                                        |Windows |Mac |iOS    |Android      |Netz                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Manuelles Anwenden, Ändern oder Entfernen einer Bezeichnung](https://support.microsoft.com/de-DE/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – teilnehmen](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Anwenden einer Standardbezeichnung](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – teilnehmen](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Eine Begründung für die Änderung einer Beschriftung verlangen](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – teilnehmen](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Link zu einer benutzerdefinierten Hilfeseite bereitstellen](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – teilnehmen](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Inhalt markieren](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – teilnehmen](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Dynamische Markierungen mit Variablen](#dynamic-markings-with-variables)                                              | 2010+           | 16.42+     | 2.42+ | 16.0.13328+ | Wird überprüft |
|[Berechtigungen sofort zuweisen](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – teilnehmen](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Benutzern das Zuweisen von Berechtigungen gestatten: <br /> – Benutzer auffordern](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | Wird überprüft   | Wird überprüft         | Wird überprüft                                                        |
|[Überwachung bezeichnungsbezogener Benutzeraktivitäten](data-classification-activity-explorer.md)                      | 2011+ | 16.43+ | 2.46+ | Rollout: 16.0.13628+ | Ja <sup>\*</sup>                                                        |
|[Von Benutzern fordern, dass sie eine Bezeichnung auf ihre E-Mails und Dokumente anwenden](#require-users-to-apply-a-label-to-their-email-and-documents)   | 2101+             | Rollout: 16.45+         | Rollout: 2.47+ | Rollout: 16.0.13628+ | Rollout                                            
|[Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)                    | 2009+                                  | Rollout: 16.44+ | Wird überprüft | Wird überprüft | [Ja – teilnehmen](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Unterstützung von gemeinsame Erstellung und AutoSpeichern](sensitivity-labels-coauthoring.md) für beschriftete und verschlüsselte Dokumente | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider) | Vorschau: [Aktueller Kanal (Vorschau)](https://office.com/insider) | Wird überprüft | Wird überprüft | [Ja – teilnehmen](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Fußnote:**

<sup>\*</sup> Enthält derzeit keinen Rechtfertigungstext zum Entfernen einer Bezeichnung oder zum Absenken der Klassifizierungsstufe

### <a name="sensitivity-label-capabilities-in-outlook"></a>Funktionen der Vertraulichkeitsbezeichnungen in Outlook

Die aufgelisteten Zahlen sind die minimale Office-Anwendungsversion, die für jede Funktion erforderlich ist.

|Funktion                                                                                                        |Outlook für Windows |Outlook für Mac |Outlook unter iOS |Outlook unter Android |Outlook im Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Manuelles Anwenden, Ändern oder Entfernen einer Bezeichnung](https://support.microsoft.com/de-DE/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Anwenden einer Standardbezeichnung](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Eine Begründung für die Änderung einer Beschriftung verlangen](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Link zu einer benutzerdefinierten Hilfeseite bereitstellen](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Inhalt markieren](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Dynamische Markierungen mit Variablen](#dynamic-markings-with-variables)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Berechtigungen sofort zuweisen](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Benutzern das Zuweisen von Berechtigungen gestatten: <br /> – Nicht weiterleiten](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Benutzern das Zuweisen von Berechtigungen gestatten: <br /> – Nur verschlüsseln](encryption-sensitivity-labels.md#let-users-assign-permissions)  |2011+ | 16.48+ | 4.2112.0+  | 4.2112.0+ | Ja |
|[Von Benutzern fordern, dass sie eine Bezeichnung auf ihre E-Mails und Dokumente anwenden](#require-users-to-apply-a-label-to-their-email-and-documents)   | 2101+                        | 16.43+ <sup>\*</sup>                    | 4.2111+            | 4.2111+                | Ja                |
|[Überwachung bezeichnungsbezogener Benutzeraktivitäten](data-classification-activity-explorer.md) | 2011+ | Wird überprüft | Wird überprüft           | Wird überprüft               | Wird überprüft |
|[Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16.44+ <sup>\*</sup>                    | Wird überprüft           | Wird überprüft               | Ja |
|[Verschiedene Einstellungen für Standardbezeichnungen und obligatorische Bezeichnungen](#outlook-specific-options-for-default-label-and-mandatory-labeling)                    | Rollout in der Vorschau: [Betakanal](https://office.com/insider)                      | 16.43.1108+                   | 4.2111+           | 4.2111+               | Ja |
|

**Fußnoten:**

<sup>\*</sup> Erfordert das [neue Outlook für Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office-integrierter Bezeichnungs-Assistent und andere Bezeichnungslösungen

Der in Office integrierte Bezeichnungs-Assistent lädt Vertraulichkeitsbezeichnungen und Richtlinieneinstellungen für Vertraulichkeitsbezeichnungen von den folgenden Verwaltungszentren herunter:

- Microsoft 365 Compliance Center
- Office 365 Security & Compliance Center (das ältere Verwaltungsportal)

Um den in Office integrierten Bezeichnungs-Assistent zu verwenden, müssen Sie über eine oder mehrere [Bezeichnungsrichtlinien](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) verfügen, die von einem der aufgeführten Admin-Centern für Benutzer veröffentlicht wurden, sowie über eine [unterstützte Version von Office](#support-for-sensitivity-label-capabilities-in-apps).

Wenn beide Bedingungen erfüllt sind, Sie aber den in Office integrierten Bezeichnungs-Assistent deaktivieren müssen, verwenden Sie die folgende Gruppenrichtlinieneinstellung:

1. Navigieren Sie zu **Benutzerkonfiguration/Administrative Vorlagen/Microsoft Office 2016/Sicherheitseinstellungen**.

2. Stellen Sie **Verwenden Sie die Vertraulichkeitsfunktion in Office, um Vertraulichkeitsbezeichnungen anzuwenden und anzuzeigen,** auf **0** ein. 
 
Stellen Sie diese Einstellung mithilfe der Gruppenrichtlinie oder des [Office-Cloudrichtliniendienstes bereit](/DeployOffice/overview-office-cloud-policy-service). Die Einstellung wird beim Neustart von Office-Apps wirksam.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office integrierter Bezeichnungs-Assistent und der Azure Information Protection-Client

Wenn Benutzer den [Azure Information Protection-Client installiert](/azure/information-protection/rms-client/aip-clientv2) haben, ist der integrierte Bezeichnungsassistent in ihren Office-Apps standardmäßig deaktiviert. 

Um die integrierte Bezeichnung anstelle des Azure Information Protection-Clients für Office-Apps zu verwenden, empfehlen wir, dass Sie die Gruppenrichtlinieneinstellung **Liste der verwalteten Add-Ins** verwenden, die unter [Keine Add-Ins geladen aufgrund von Gruppenrichtlinieneinstellungen für Office 2013- und Office 2016-Programme](https://support.microsoft.com/help/2733070/no-add-ins-loaded-due-to-group-policy-settings-for-office-2013-and-off) dokumentiert ist.

Geben Sie für Microsoft Word 2016, Excel 2016, PowerPoint 2016 und Outlook 2016 die folgenden programmgesteuerten Kennungen (ProgID) für den Azure Information Protection-Client an, und setzen Sie die Option auf **0: Das Add-In ist immer deaktiviert (blockiert)**

|Anwendung  |ProgID  |
|---------|---------|
|Word     |     `MSIP.WordAddin`    |
|Excel     |  `MSIP.ExcelAddin`       |
|PowerPoint     |   `MSIP.PowerPointAddin`      |
|Outlook | `MSIP.OutlookAddin` |
| | | 


Stellen Sie diese Einstellung unter Verwendung der Gruppenrichtlinie oder dem [Office-Cloudrichtliniendienst](/DeployOffice/overview-office-cloud-policy-service) bereit.

> [!NOTE]
> Wenn Sie die Gruppenrichtlinieneinstellung **Verwenden der Vertraulichkeitsfunktion in Office zum Anwenden und Anzeigen von Vertraulichkeitsbezeichnungen** verwenden und diese auf **1** setzen, kann es Situationen geben, in denen der Azure Information Protection-Client in Office-Apps trotzdem noch geladen wird. Das Blockieren des Ladens des Add-Ins in jeder App verhindert dies.

Alternativ können Sie das Office-Add-In **Microsoft Azure Information Protection** interaktiv in Word, Excel, PowerPoint und Outlook deaktivieren oder es daraus entfernen. Diese Methode ist für einen einzelnen Computer und für Ad-hoc-Tests geeignet. Eine Anleitung finden Sie unter [Anzeigen, Verwalten und Installieren von Add-Ins in Office-Programmen](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d). 

Unabhängig von der gewählten Methode werden die Änderungen beim Neustart der Office-Apps wirksam. Durch Deaktivieren oder Entfernen dieses Office-Add-Ins bleibt der Azure Information Protection-Client auf dem Computer installiert, sodass Sie weiterhin Dateien außerhalb Ihrer Office-Apps bezeichnen können. Zum Beispiel mit dem Datei-Explorer oder der PowerShell.

Informationen darüber, welche Funktionen von den Azure Information Protection-Clients und dem in Office integrierten Bezeichnungs-Assistent unterstützt werden, finden Sie unter [Wählen Sie Ihre Windows-Bezeichnungslösung](/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution) in der Azure Information Protection-Dokumentation.

## <a name="office-file-types-supported"></a>Unterstützte Office-Dateitypen

Office-Anwendungen mit integrierter Bezeichnung für Word-, Excel- und PowerPoint-Dateien unterstützen das Open XML-Format (z. B. .docx und .xlsx), nicht aber das Microsoft Office 97-2003-Format (z. B. .doc und .xls), das Open Document-Format (z. B. .odt und .ods) oder andere Formate. Wenn ein Dateityp für die integrierte Bezeichnung nicht unterstützt wird, ist die Schaltfläche **Vertraulichkeit** in der Office-App nicht verfügbar.

Der Bezeichnungs-Assistent von Azure Information Protection unterstützt sowohl das Open XML-Format als auch das Microsoft Office 97-2003-Format. Weitere Informationen finden Sie unter [Dateitypen, die vom Bezeichnungs-Assistent von Azure Information Protection unterstützt werden](/azure/information-protection/rms-client/clientv2-admin-guide-file-types), im Administrationshandbuch des Clients.

Bei anderen Bezeichnungslösungen prüfen Sie deren Dokumentation auf unterstützte Dateitypen.

## <a name="protection-templates-and-sensitivity-labels"></a>Schutzvorlagen und Vertraulichkeitsbezeichnungen

Administratordefinierte [Schutzvorlagen](/azure/information-protection/configure-policy-templates), wie die, die Sie für Office 365-Nachrichtenverschlüsselung definieren, sind in Office-Apps nicht sichtbar, wenn Sie die integrierte Bezeichnung verwenden. Diese Vereinfachung spiegelt wider, dass es nicht notwendig ist, eine Schutzvorlage auszuwählen, da die gleichen Einstellungen bei Vertraulichkeitsbezeichnungen mit aktivierter Verschlüsselung enthalten sind.

Wenn Sie vorhandene Schutzvorlagen in Bezeichnungen konvertieren müssen, verwenden Sie das Azure-Portal und die folgenden Anweisungen: [So konvertieren Sie Vorlagen in Bezeichnungen](/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Information Rights Management (IRM)-Optionen und Vertraulichkeitsbezeichnungen

Vertraulichkeitsbezeichnungen, die Sie für die Anwendung der Verschlüsselung konfigurieren, nehmen dem Benutzer die Komplexität, seine eigenen Verschlüsselungseinstellungen festzulegen. In vielen Office-Apps können diese individuellen Verschlüsselungseinstellungen von den Anwendern noch manuell über die Optionen des Information Rights Management (IRM) konfiguriert werden. Zum Beispiel für Windows-Apps:

- Für ein Dokument:  **Datei** > **-Info** > **Dokument schützen** > **Zugriff einschränken**
- für eine E-Mail: Auf der Registerkarte **Optionen** > **Verschlüsseln** 
  
Wenn Benutzer ein Dokument oder eine E-Mail zum ersten Mal mit einer Bezeichnung versehen, können sie Ihre Konfigurationseinstellungen für die Bezeichnung mit ihren eigenen Verschlüsselungseinstellungen überschreiben. Zum Beispiel:

- Ein Benutzer wendet die Bezeichnung **Vertraulich \ Alle Mitarbeiter** auf ein Dokument an und diese Bezeichnung ist so konfiguriert, dass die Verschlüsselungseinstellungen für alle Benutzer in der Organisation gelten. Dieser Benutzer konfiguriert dann manuell die IRM-Einstellungen, um den Zugriff auf einen Benutzer außerhalb Ihrer Organisation zu beschränken. Das Endergebnis ist ein Dokument, das als **Vertraulich \ für alle Mitarbeiter** gekennzeichnet und verschlüsselt ist, aber die Benutzer in Ihrer Organisation können es nicht wie erwartet öffnen.

- Ein Benutzer versieht eine E-Mail mit der Bezeichnung **Vertraulich\ Nur Empfänger** und diese E-Mail ist so konfiguriert, dass die Verschlüsselungseinstellung **Nicht weiterleiten** gilt. In der Outlook-App konfiguriert dieser Benutzer dann manuell die IRM-Einstellungen, sodass die E-Mail nicht eingeschränkt ist. Das Endergebnis ist, dass die E-Mail von den Empfängern weitergeleitet werden kann, obwohl sie die Bezeichnung **Vertraulich \ Nur Empfänger** trägt.
    
    Ausnahmsweise stehen Benutzern bei Outlook im Web die Optionen aus dem Menü **Verschlüsseln** nicht zur Auswahl, wenn die aktuell ausgewählte Bezeichnung Verschlüsselung anwendet.

- Ein Benutzer wendet das Etikett **Allgemein** auf ein Dokument an, und diese Bezeichnung ist nicht für die Anwendung von Verschlüsselung konfiguriert. Dieser Benutzer konfiguriert dann manuell die IRM-Einstellungen, um den Zugriff auf das Dokument zu beschränken. Das Endergebnis ist ein Dokument, das als **Allgemein** bezeichnet ist, aber auch verschlüsselt wird, so dass einige Benutzer es nicht wie erwartet öffnen können.

Wenn das Dokument oder die E-Mail bereits bezeichnet ist, kann ein Benutzer jede dieser Aktionen durchführen, wenn der Inhalt nicht bereits verschlüsselt ist oder er das [Nutzungsrecht](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Export oder Vollzugriff hat. 

Um eine einheitlichere Bezeichnung mit aussagekräftigen Berichten zu erreichen, sollten Sie geeignete Bezeichnungen und Anleitungen für Benutzer bereitstellen, damit diese nur Bezeichnungen zum Schutz von Dokumenten anbringen. Zum Beispiel:

- Für Ausnahmefälle, in denen Benutzer ihre eigenen Berechtigungen zuweisen müssen, stellen Sie Bezeichnungen bereit, mit denen [Benutzer ihre eigenen Berechtigungen](encryption-sensitivity-labels.md#let-users-assign-permissions) zuweisen können. 

- Anstatt dass Benutzer die Verschlüsselung manuell entfernen, nachdem sie eine Bezeichnung ausgewählt haben, das die Verschlüsselung anwendet, bieten Sie eine Alternative für untergeordnete Bezeichnungen an, wenn Benutzer eine Bezeichnung mit der gleichen Klassifizierung, aber ohne Verschlüsselung benötigen. Zum Beispiel:
    - **Vertraulich \ Alle Mitarbeiter**
    - **Vertraulich \ Jeder (keine Verschlüsselung)** 

> [!NOTE]
> Wenn Benutzer die Verschlüsselung eines mit einer Bezeichnung versehenen Dokuments, das in SharePoint oder OneDrive gespeichert ist, manuell entfernen und Sie [Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) aktiviert haben, wird die Bezeichnungsverschlüsselung automatisch wiederhergestellt, wenn das Dokument das nächste Mal aufgerufen oder heruntergeladen wird. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Anwenden von Vertraulichkeitsbezeichnungen auf Dateien, E-Mails und Anhänge

Benutzer können für jedes Dokument oder jede E-Mail jeweils nur eine Bezeichnung anwenden.

Wenn Sie eine E-Mail-Nachricht mit Anlagen bezeichnen, erben die Anlagen die Bezeichnung nur, wenn die Bezeichnung, die Sie auf die E-Mail-Nachricht anwenden, Verschlüsselung anwendet und die Anlage ein Office-Dokument ist, das nicht bereits verschlüsselt ist. Da die geerbte Bezeichnung die Verschlüsselung anwendet, wird der Anhang neu verschlüsselt.

Ein Anhang erbt nicht die Bezeichnung aus der E-Mail-Nachricht, wenn die auf die E-Mail-Nachricht angewendete Bezeichnung keine Verschlüsselung vorsieht oder der Anhang bereits verschlüsselt ist.

Beispiele für die Vererbung von Bezeichnungen, wobei die Bezeichnung **Vertraulich** die Verschlüsselung anwendet und die Bezeichnung **Allgemein** die Verschlüsselung nicht anwendet:

- Ein Benutzer erstellt eine neue E-Mail-Nachricht und versieht diese mit der Bezeichnung **Vertraulich**. Sie fügen dann ein Word-Dokument hinzu, das nicht bezeichnet oder verschlüsselt ist. Als Ergebnis der Vererbung wird das Dokument neu als **Vertraulich** bezeichnet und hat nun eine Verschlüsselung, die von dieser Bezeichnung ausgeht.

- Ein Benutzer erstellt eine neue E-Mail-Nachricht und versieht diese mit der Bezeichnung **Vertraulich**. Sie fügen dann ein Word-Dokument hinzu, das mit **Allgemein** bezeichnet ist, und diese Datei ist nicht verschlüsselt. Als Ergebnis der Vererbung wird das Dokument nochmal als **Vertraulich** bezeichnet und hat nun eine Verschlüsselung, die von dieser Bezeichnung ausgeht.

## <a name="sensitivity-label-compatibility"></a>Kompatibilität des Vertraulichkeitsbezeichnungen

**Mit RMS-erweiterten Anwendungen**: Wenn Sie ein bezeichnetes und verschlüsseltes Dokument oder eine E-Mail in einer [RMS-erweiterten Anwendung](/azure/information-protection/requirements-applications#rms-enlightened-applications) öffnen, die keine Vertraulichkeitsbezeichnungen unterstützt, erzwingt die Anwendung dennoch die Verschlüsselung und Rechteverwaltung.

**Mit dem Azure Information Protection-Client**: Können Sie Vertraulichkeitsbezeichnungen, die Sie mit dem in Office integrierten Bezeichnungs-Assistent auf Dokumente und E-Mails anwenden, mit dem Azure Information Protection-Client anzeigen und ändern und umgekehrt.

**Mit anderen Versionen von Office**: Jeder berechtigte Benutzer kann bezeichnete Dokumente und E-Mails in anderen Versionen von Office öffnen. Sie können die Bezeichnung jedoch nur in unterstützten Office-Versionen oder mit dem Azure Information Protection-Client anzeigen oder ändern. Die unterstützten Office-App-Versionen sind im [vorherigen Abschnitt](#support-for-sensitivity-label-capabilities-in-apps) aufgeführt.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Unterstützung für SharePoint- und OneDrive-Dateien, die durch Vertraulichkeitsbezeichnungen geschützt sind

Um den in Office integrierten Bezeichnungs-Assistent mit Office im Web für Dokumente in SharePoint oder OneDrive zu verwenden, stellen Sie sicher, dass Sie [Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) aktiviert haben.

## <a name="support-for-external-users-and-labeled-content"></a>Unterstützung für externe Benutzer und bezeichnete Inhalte

Wenn Sie ein Dokument oder eine E-Mail bezeichnen, wird die Bezeichnung als Metadaten gespeichert, die Ihren Mandanten und eine Bezeichnungs-GUID enthalten. Wenn ein bezeichnetes Dokument oder eine E-Mail von einer Office-App geöffnet wird, die Vertraulichkeitsbezeichnungen unterstützt, werden diese Metadaten ausgelesen, und nur wenn der Benutzer demselben Mandanten angehört, wird die Bezeichnung in dessen App angezeigt. Bei den integrierten Bezeichnungen für Word, PowerPoint und Excel wird der Bezeichnungsname beispielsweise in der Statusleiste angezeigt. 

Das bedeutet, dass, wenn Sie Dokumente mit einer anderen Organisation teilen, die andere Bezeichnungsnamen verwendet, jede Organisation ihre eigene Bezeichnung auf das Dokument anwenden und sehen kann. Die folgenden Elemente einer angelegten Bezeichnung sind jedoch für Benutzer außerhalb Ihrer Organisation sichtbar:

- Inhaltliche Markierungen. Wenn eine Bezeichnung eine Kopf- oder Fußzeile oder ein Wasserzeichen anlegt, werden diese direkt zum Inhalt hinzugefügt und bleiben sichtbar, bis jemand sie ändert oder löscht.

- Der Name und die Beschreibung der zugrundeliegenden Schutzvorlage aus einer Bezeichnung, das die Verschlüsselung angewendet hat. Diese Informationen werden in einer Meldungsleiste am oberen Rand des Dokuments angezeigt, um Auskunft darüber zu geben, wer berechtigt ist, das Dokument zu öffnen, und welche Nutzungsrechte er für dieses Dokument hat.

### <a name="sharing-encrypted-documents-with-external-users"></a>Teilen verschlüsselter Dokumente mit externen Benutzern

Zusätzlich zur Beschränkung des Zugriffs auf Benutzer in Ihrer eigenen Organisation können Sie den Zugriff auf jeden anderen Benutzer erweitern, der ein Konto in Azure Active Directory hat. Wenn Ihr Unternehmen jedoch Richtlinien für bedingten Zugriff verwendet, finden Sie im [nächsten Abschnitt](#conditional-access-policies) zusätzliche Überlegungen.

Alle Office-Apps und andere [RMS-erweiterte Anwendungen](/azure/information-protection/requirements-applications#rms-enlightened-applications) können verschlüsselte Dokumente öffnen, nachdem sich der Benutzer erfolgreich authentifiziert hat. 

Wenn externe Benutzer nicht über ein Konto in Azure Active Directory verfügen, können sie sich über Gastkonten in Ihrem Mandanten authentifizieren. Diese Gastkonten können auch verwendet werden, um auf freigegebene Dokumente in SharePoint oder OneDrive zuzugreifen, wenn Sie [Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert haben](sensitivity-labels-sharepoint-onedrive-files.md):

- Eine Möglichkeit ist, diese Gastkonten selbst zu erstellen. Sie können eine beliebige E-Mail-Adresse angeben, die diese Benutzer bereits verwenden. Zum Beispiel ihre Gmail-Adresse.
    
    Der Vorteil dieser Option ist, dass Sie den Zugriff und die Rechte auf bestimmte Benutzer beschränken können, indem Sie deren E-Mail-Adresse in den Verschlüsselungseinstellungen angeben. Der Nachteil ist der Verwaltungsaufwand für die Kontoerstellung und die Koordination mit der Bezeichnungskonfiguration.

- Eine weitere Möglichkeit ist die [SharePoint- und OneDrive-Integration mit Azure AD B2B (Vorschau)](/sharepoint/sharepoint-azureb2b-integration-preview), so dass Gastkonten automatisch erstellt werden, wenn Ihre Benutzer Links teilen.
    
    Der Vorteil dieser Option ist ein minimaler Verwaltungsaufwand, da die Konten automatisch erstellt werden, und eine einfachere Bezeichnungskonfiguration. Für dieses Szenario müssen Sie die Verschlüsselungsoption [Jeden authentifizierten Benutzer](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) hinzufügen auswählen, da Sie die E-Mail-Adressen nicht im Voraus kennen. Der Nachteil ist, dass Sie mit dieser Einstellung die Zugriffs- und Nutzungsrechte nicht auf bestimmte Benutzer beschränken können.

Externe Benutzer können auch ein Microsoft-Konto verwenden, um verschlüsselte Dokumente zu öffnen, wenn sie Windows und Microsoft 365 Apps ([früher Office 365 Apps](/deployoffice/name-change)) oder die eigenständige Edition von Office 2019 verwenden. Seit kurzem werden Microsoft-Konten auch für andere Plattformen unterstützt, um verschlüsselte Dokumente auf macOS (Microsoft 365 Apps, Version 16.42+), Android (Version 16.0.13029+) und iOS (Version 2.42+) zu öffnen. Beispiel: Ein Benutzer in Ihrer Organisation gibt ein verschlüsseltes Dokument für einen Benutzer außerhalb Ihrer Organisation frei, und in den Verschlüsselungseinstellungen ist eine Gmail-E-Mail-Adresse für den externen Benutzer angegeben. Dieser externe Benutzer kann sein eigenes Microsoft-Konto erstellen, das seine Gmail-E-Mail-Adresse verwendet. Nachdem sie sich mit diesem Konto angemeldet haben, können sie das Dokument öffnen und bearbeiten, entsprechend den für sie festgelegten Nutzungsbeschränkungen. Ein ausführliches Beispiel für dieses Szenario finden Sie unter [Öffnen und Bearbeiten des geschützten Dokuments](/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document).

> [!NOTE]
> Die E-Mail-Adresse für das Microsoft-Konto muss mit der E-Mail-Adresse übereinstimmen, die zur Zugriffsbeschränkung für die Verschlüsselungseinstellungen angegeben ist.

Wenn ein Benutzer mit einem Microsoft-Konto ein verschlüsseltes Dokument auf diese Weise öffnet, wird automatisch ein Gastkonto für den Mandanten erstellt, wenn nicht bereits ein Gastkonto mit demselben Namen existiert. Wenn das Gastkonto existiert, kann es dann verwendet werden, um Dokumente in SharePoint und OneDrive zu öffnen, indem Office im Web verwendet wird, zusätzlich zum Öffnen verschlüsselter Dokumente aus den unterstützten Desktop- und mobilen Office-Apps.

Allerdings wird das automatische Gastkonto in diesem Szenario aufgrund der Replikationslatenz nicht sofort erstellt. Wenn Sie persönliche E-Mail-Adressen als Teil Ihrer Verschlüsselungseinstellungen für Bezeichnungen angeben, empfehlen wir, dass Sie entsprechende Gastkonten in Azure Active Directory erstellen. Teilen Sie diesen Benutzern dann mit, dass sie dieses Konto verwenden müssen, um ein verschlüsseltes Dokument Ihrer Organisation zu öffnen.

> [!TIP]
> Da Sie nicht sicher sein können, dass externe Benutzer eine unterstützte Office-Clientanwendung verwenden, ist die Freigabe von Links aus SharePoint und OneDrive nach dem Erstellen von Gastkonten (für bestimmte Benutzer) oder bei Verwendung der [SharePoint- und OneDrive-Integration mit Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) (für jeden authentifizierten Benutzer) eine zuverlässigere Methode zur Unterstützung der sicheren Zusammenarbeit mit externen Benutzern.

### <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Wenn Ihr Unternehmen [Richtlinien für den bedingten Zugriff in Azure Active Directory](/azure/active-directory/conditional-access/overview) implementiert hat, überprüfen Sie die Konfiguration dieser Richtlinien. Wenn die Richtlinien **Microsoft Azure Information Protection** umfassen und sich die Richtlinie auf externe Benutzer erstreckt, müssen diese externen Benutzer ein Gastkonto in Ihrem Mandanten haben, auch wenn sie ein Azure AD-Konto in ihrem eigenen Mandanten haben.

Ohne dieses Gastkonto können sie das verschlüsselte Dokument nicht öffnen und sehen eine Fehlermeldung. Der Nachrichtentext informiert sie möglicherweise darüber, dass ihr Konto als externer Benutzer im Mandanten hinzugefügt werden muss, mit der für dieses Szenario falschen Anweisung, sich **Abzumelden und mit einem anderen Azure Active Directory-Benutzerkonto** erneut anzumelden.

Wenn Sie in Ihrem Mandanten keine Gastkonten für externe Benutzer erstellen und konfigurieren können, die Dokumente öffnen müssen, die von Ihren Bezeichnungen verschlüsselt werden, müssen Sie entweder Azure Information Protection aus den Richtlinien für bedingten Zugriff entfernen oder externe Benutzer von den Richtlinien ausschließen.

Weitere Informationen zu bedingter Zugriff und Azure Information Protection, dem von Vertraulichkeitsbezeichnungen verwendeten Verschlüsselungsdienst, finden Sie in der häufig gestellten Frage [Ich sehe, dass Azure Information Protection als verfügbare Cloud-App für bedingten Zugriff aufgeführt ist – wie funktioniert das?](/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Wenn Office-Apps Markierungen und Verschlüsselungen auf Inhalte anwenden.

Office-Apps wenden die Inhaltsmarkierung und die Verschlüsselung mit einem Vertraulichkeitsbezeichnungen je nach App unterschiedlich an.

| App | Inhaltskennzeichnung | Verschlüsselung |
| --- | --- | --- |
| Word, Excel, PowerPoint auf allen Plattformen | Sofort | Sofort |
| Outlook für PC und Mac | Nachdem Exchange Online die E-Mail gesendet hat | Sofort |
| Outlook im Web, für iOS und Android | Nachdem Exchange Online die E-Mail gesendet hat | Nachdem Exchange Online die E-Mail gesendet hat |
|

Lösungen, die Vertraulichkeitsbezeichnungen auf Dateien außerhalb von Office-Anwendungen anwenden, tun dies, indem sie Bezeichnungsmetadaten auf die Datei anwenden. In diesem Szenario wird die Inhaltsmarkierung aus der Konfiguration der Bezeichnung nicht in die Datei eingefügt, sondern die Verschlüsselung wird angewendet. 

Werden diese Dateien in einer Office-Desktop-App geöffnet, werden die Inhaltsmarkierungen automatisch durch den Azure Information Protection-Client für einheitliche Bezeichnungen angewendet, wenn die Datei zum ersten Mal gespeichert wird. Die Inhaltsmarkierungen werden nicht automatisch angewendet, wenn Sie die integrierte Bezeichnung für Desktop-, Mobil- oder Web-Apps verwenden.

Zu den Szenarien, die das Anwenden einer Vertraulichkeitsbezeichnungen außerhalb von Office-Apps beinhalten, gehören:

- Der Scanner, Datei-Explorer und PowerShell vom einheitlichen Bezeichnungs-Assistent von Azure Information Protection 

- Auto-Bezeichnungsrichtlinien für SharePoint und OneDrive

- Exportierte bezeichnete und verschlüsselte Daten aus Power BI

- Microsoft Cloud App Security

Für diese Szenarien kann ein Benutzer mit seinen Office-Apps die Inhaltsmarkierungen der Bezeichnung anwenden, indem er die aktuelle Bezeichnung vorübergehend entfernt oder ersetzt und dann die ursprüngliche Bezeichnung wieder anbringt.

### <a name="dynamic-markings-with-variables"></a>Weitere Informationen finden Sie unter Dynamische Markierungen mit Variablen.

> [!IMPORTANT]
> Derzeit unterstützen nicht alle Apps auf allen Plattformen dynamische Inhaltsmarkierungen, die Sie für Ihre Kopf- und Fußzeilen sowie Wasserzeichen festlegen können. Bei Apps, welche diese Fähigkeit nicht unterstützen, wenden sie die Markierungen als den in der Bezeichnungskonfiguration angegebenen Originaltext an, anstatt die Variablen aufzulösen.
> 
> Der Azure Information Protection-Client für einheitliche Bezeichnungen unterstützt dynamische Markierungen. Für die in Office integrierten Bezeichnungen finden Sie in den Tabellen im Abschnitt [Funktionen](#support-for-sensitivity-label-capabilities-in-apps) auf dieser Seite Informationen zu den unterstützten Mindestversionen.

Wenn Sie eine Vertraulichkeitsbezeichnungen für Inhaltsmarkierungen konfigurieren, können Sie die folgenden Variablen in der Textzeichenfolge für Ihre Kopf- und Fußzeile oder Ihr Wasserzeichen verwenden:

| Variable | Beschreibung | Beispiel beim Aufbringen der Bezeichnung |
| -------- | ----------- | ------- |
| `${Item.Label}` | Bezeichnungs-Anzeigename der angewendeten Bezeichnung | **Allgemein**|
| `${Item.Name}` | Dateiname oder E-Mail-Betreff des zu bezeichnenden Inhalts | **Sales.docx** |
| `${Item.Location}` | Pfad und Dateiname des zu bezeichnenden Dokuments bzw. der E-Mail-Betreff für eine zu bezeichnenden E-Mail | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Anzeigename des Benutzers, der die Bezeichnung anbringt | **Richard Simone** |
| `${User.PrincipalName}` | Azure AD-Benutzerprinzipalname (UPN) des Benutzers, der die Bezeichnung anwendet | **rsimone\@contoso.com** |
| `${Event.DateTime}` | Datum und Uhrzeit, zu der der Inhalt bezeichnet wird, in der lokalen Zeitzone des Benutzers, der die Bezeichnung anbringt | **10.08.2020 13:30 UHR** |

> [!NOTE]
> Bei der Syntax für diese Variablen wird zwischen Groß- und Kleinschreibung unterschieden.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Setzen unterschiedlicher visueller Markierungen für Word, Excel, PowerPoint und Outlook

Als zusätzliche Variable können Sie visuelle Markierungen pro Office-Anwendungstyp konfigurieren, indem Sie eine "If.App"-Variablenanweisung in der Textzeichenfolge verwenden und den Anwendungstyp durch die Werte **Word**, **Excel**, **PowerPoint** oder **Outlook** identifizieren. Sie können diese Werte auch abkürzen, was notwendig ist, wenn Sie mehrere Werte in derselben If.App-Anweisung angeben möchten.

Verwenden Sie die folgende Syntax:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Wie bei den anderen dynamischen visuellen Markierungen muss bei der Syntax die Groß-/Kleinschreibung beachtet werden. Dies gilt auch für die Abkürzungen für die einzelnen Anwendungstypen (WEPO).

Beispiele:

- **Kopfzeilentext nur für Word-Dokumente einstellen:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Nur in Word-Dokumentenkopfzeilen übernimmt die Bezeichnung den Kopfzeilentext "Dieses Word-Dokument ist vertraulich". Für andere Office-Anwendungen wird kein Kopfzeilentext übernommen.

- **Legen Sie Fußzeilentext für Word, Excel und Outlook und einen anderen Fußzeilentext für PowerPoint fest:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    In Word, Excel und Outlook übernimmt die Bezeichnung den Fußtext "Dieser Inhalt ist vertraulich". In PowerPoint wendet die Bezeichnung den Fußzeilentext "Diese Präsentation ist vertraulich" an.

- **Legen Sie einen bestimmten Wasserzeichentext für Word und PowerPoint fest, und dann einen Wasserzeichentext für Word, Excel und PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    In Word und PowerPoint wird die Bezeichnung mit dem Wasserzeichentext "Dieser Inhalt ist vertraulich" versehen. In Excel wird die Bezeichnung mit dem Wasserzeichentext "Vertraulich" versehen. In Outlook trägt die Bezeichnung keinen Wasserzeichentext auf, da Wasserzeichen als visuelle Markierungen für Outlook nicht unterstützt werden.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden

> [!IMPORTANT]
> 
> Der [Azure Information Protection-Client für einheitliche Bezeichnungen](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) unterstützt diese Konfiguration, die auch obligatorisches Bezeichnen genannt wird. Für die in Office-Apps integrierten Bezeichnungen finden Sie in den Tabellen im Abschnitt [Funktionen](#support-for-sensitivity-label-capabilities-in-apps) auf dieser Seite Informationen zu den Mindestversionen.
>
> Wenn Sie obligatorische Bezeichnungen für Dokumente, aber nicht für E-Mails verwenden möchten, lesen Sie die Anweisungen im nächsten Abschnitt, in dem erklärt wird, wie Sie Outlook-spezifische Optionen konfigurieren.

Wenn die Richtlinieneinstellung **Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden** ausgewählt ist, müssen Benutzer, denen die Richtlinie zugewiesen ist, in den folgenden Szenarien eine Vertraulichkeitsbezeichnungen auswählen und anwenden:

- Für den einheitlichen Bezeichnungs-Assistent von Azure Information Protection:
    - Für Dokumente (Word, Excel, PowerPoint): Wenn ein nicht bezeichnetes Dokument gespeichert wird oder Benutzer das Dokument schließen.
    - Für Emails (Outlook): Zu dem Zeitpunkt, an dem Benutzer eine nicht bezeichnete Nachricht senden.

- Für die in Office-Apps integrierte Bezeichnung:
    - Für Dokumente (Word, Excel, PowerPoint): Wenn ein nicht bezeichnetes Dokument geöffnet oder gespeichert wird.
    - Für E-Mails (Outlook): Zu dem Zeitpunkt, an dem Benutzer eine nicht bezeichnete E-Mail-Nachricht senden.

Zusätzliche Informationen für die integrierte Bezeichnung:

- Wenn Benutzer aufgefordert werden, eine Vertraulichkeitsbezeichnungen hinzuzufügen, weil sie ein nicht bezeichnetes Dokument öffnen, können sie eine Bezeichnung hinzufügen oder wählen, dass das Dokument im schreibgeschützten Modus geöffnet wird.

- Wenn die Bezeichnungspflicht in Kraft ist, können Benutzer keine Vertraulichkeitsbezeichnungen von Dokumenten entfernen, aber eine vorhandene Bezeichnung ändern.

Eine Anleitung, wann diese Einstellung verwendet werden sollte, finden Sie in den Informationen zu [Richtlinieneinstellungen](sensitivity-labels.md#what-label-policies-can-do).

> [!NOTE]
> Wenn Sie die standardmäßige Richtlinieneinstellung für Bezeichnungen für Dokumente und E-Mails zusätzlich zur obligatorischen Bezeichnung verwenden: 
>
> Die Standardbezeichnung hat immer Vorrang vor der obligatorischen Bezeichnung. Bei Dokumenten wendet der Assistent für einheitliche Bezeichnungen von Azure Information Protection die Standardbezeichnung jedoch auf alle Dokumente ohne Bezeichnung an, während die integrierte Bezeichnung die Standardbezeichnung auf neue Dokumente und nicht auf vorhandene Dokumente ohne Bezeichnung anwendet. Dieser Verhaltensunterschied bedeutet, dass Benutzer bei der Verwendung einer obligatorischen Bezeichnung mit der standardmäßigen Bezeichnungseinstellung aufgefordert werden, häufiger eine Vertraulichkeitsbezeichnung anzuwenden, wenn sie integrierte Bezeichnungen verwenden, als wenn sie den Assistenten für einheitliche Bezeichnungen von Azure Information Protection verwenden.

## <a name="outlook-specific-options-for-default-label-and-mandatory-labeling"></a>Outlook-spezifische Optionen für Standardbezeichnungen und obligatorische Bezeichnungen

Für integrierte Bezeichnungen ermitteln Sie die Mindestversionen von Outlook, die diese Features unterstützen, anhand der [Funktionstabelle für Outlook](#sensitivity-label-capabilities-in-outlook) auf dieser Seite und der Zeile **Verschiedene Einstellungen für Standardbezeichnungen und obligatorische Bezeichnungen**.

Wenn Sie die Bezeichnungsrichtlinieneinstellungen **Diese Bezeichnung standardmäßig auf Dokumente und E-Mails anwenden** und **Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden** auswählen, gilt Ihre Konfigurationsauswahl standardmäßig sowohl für E-Mails als auch für Dokumente.

Wenn Sie unterschiedliche Einstellungen auf E-Mails anwenden möchten, verwenden Sie die erweiterten PowerShell-Einstellungen:

- **OutlookDefaultLabel**: Verwenden Sie diese Einstellung, wenn Sie möchten, dass Outlook eine andere Standardbezeichnung oder keine Bezeichnung anwendet.

- **DisableMandatoryInOutlook**: Verwenden Sie diese Einstellung, wenn Sie möchten, dass Outlook die Benutzer nicht auffordert, eine Bezeichnung für nicht bezeichnete E-Mail-Nachrichten auszuwählen.

Weitere Informationen zum Konfigurieren dieser Einstellungen mithilfe von PowerShell finden Sie im nächsten Abschnitt.

### <a name="powershell-advanced-settings-outlookdefaultlabel-and-disablemandatoryinoutlook"></a>Erweiterte PowerShell-Einstellungen „OutlookDefaultLabel“ und „DisableMandatoryInOutlook“

Diese Einstellungen werden unter Verwendung von PowerShell mit dem Parameter *AdvancedSettings* sowie den Cmdlets [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) und [New-LabelPolicy](/powershell/module/exchange/new-labelpolicy) aus [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell) unterstützt. Diese beiden erweiterten Einstellungen wurden zuvor nur vom Azure Information Protection-Client für einheitliche Bezeichnungen unterstützt, werden jetzt jedoch auch für integrierte Bezeichnungen unterstützt.

PowerShell-Beispiele mit der Bezeichnungsrichtlinie namens **Global**:

- So legen Sie fest, dass Outlook keine Standardbezeichnung festlegen muss:
    
    ````powershell
    Set-LabelPolicy -Identity Global -AdvancedSettings @{OutlookDefaultLabel="None"}
    ````

- So legen Sie fest, dass Outlook keine obligatorischen Bezeichnungen verwenden muss:
    
    ````powershell
    Set-LabelPolicy -Identity Global -AdvancedSettings @{DisableMandatoryInOutlook="True"}
    ````

Derzeit sind „OutlookDefaultLabel“ und „DisableMandatoryInOutlook“ die einzigen erweiterten PowerShell-Einstellungen, die sowohl für integrierte Bezeichnungen als auch den Azure Information Protection-Client unterstützt werden.

Die anderen erweiterten PowerShell-Einstellungen werden nur für den Azure Information Protection-Client unterstützt. Weitere Informationen zur Verwendung erweiterter Einstellungen für den Azure Information Protection-Client finden Sie im [Handbuch für Administratoren: Benutzerdefinierte Konfigurationen für den Azure Information Protection-Client für einheitliche Bezeichnungen](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#configuring-advanced-settings-for-the-client-via-powershell).

#### <a name="powershell-tips-for-specifying-the-advanced-settings"></a>PowerShell-Tipps zum Festlegen der erweiterten Einstellungen

Um eine andere Standardbezeichnung für Outlook festzulegen, müssen Sie die Bezeichnungs-GUID angeben. Diesen Wert können Sie mit dem folgenden Befehl abrufen:

````powershell
Get-Label | Format-Table -Property DisplayName, Name, Guid
````

Wenn Sie eine dieser erweiterten Einstellungen aus einer Bezeichnungsrichtlinie entfernen möchten, verwenden Sie die gleiche AdvancedSettings-Parametersyntax, allerdings mit einem leeren Zeichenfolgenwert. Zum Beispiel:

````powershell
Set-LabelPolicy -Identity Global -AdvancedSettings @{OutlookDefaultLabel=""}
````


## <a name="end-user-documentation"></a>Dokumentation für Endbenutzer

- [Verwenden von Vertraulichkeitsbezeichnungen auf Ihre Dateien und E-Mails in Office](https://support.microsoft.com/de-DE/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Bekannte Probleme mit Vertraulichkeitsbezeichnungen in Office](https://support.microsoft.com/de-DE/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Automatisches Anwenden oder Empfehlen von Vertraulichkeitsbezeichnungen für Ihre Dateien und E-Mails in Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Bekannte Probleme beim automatischen Anwenden oder Empfehlen von Vertraulichkeitsbezeichnungen](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)
