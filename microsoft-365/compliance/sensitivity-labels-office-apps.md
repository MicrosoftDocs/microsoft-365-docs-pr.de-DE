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
description: Erfahren Sie, wie Benutzer mit Vertraulichkeits Bezeichnungen in Office-Apps für den Desktop, Office-Apps für Mobilgeräte und Office-Apps für das Internet arbeiten. Finden Sie heraus, welche apps Vertraulichkeits Bezeichnungen unterstützen.
ms.openlocfilehash: 858d2be23dcb3c3f2b0794e735ed8ca61d67b74d
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634213"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>Verwenden von Vertraulichkeitsbezeichnungen in Office-Apps

Wenn Sie Sensitivitäts Bezeichnungen aus dem Microsoft 365 Compliance Center oder einem entsprechenden Bezeichnungs Center [veröffentlicht](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) haben, werden diese in Office-Apps angezeigt, damit Benutzerdaten beim Erstellen oder bearbeiten klassifizieren und schützen können.

Verwenden Sie die Informationen in diesem Artikel, um Sie bei der erfolgreichen Verwaltung von Sensitivitäts Bezeichnungen in Office-Apps zu unterstützen. Ermitteln Sie beispielsweise die Mindestversion von apps, die Sie zur Unterstützung der integrierten Kennzeichnung benötigen, und verstehen Sie die Interaktionen mit dem Azure Information Protection Unified Labeling-Client und der Kompatibilität mit anderen apps und Diensten.

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Abonnement-und Lizenzierungsanforderungen für Sensitivitäts Bezeichnungen

Benutzern muss mindestens eine der folgenden Lizenzen zugewiesen sein:

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) oder höher

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software) oder höher

- [Azure Information Protection Premium P1](https://azure.microsoft.com/pricing/details/information-protection/) oder höher

Der integrierte Office-Labeling-Client unterstützt Sensitivitäts Bezeichnungen mit einer Abonnement Edition von Office. Dieser Bezeichnungs Client unterstützt keine eigenständigen Editionen von Office, wie Office 2016 oder Office 2019. Um Sensitivitäts Bezeichnungen mit diesen Editionen von Office auf Windows-Computern zu verwenden, installieren Sie den Azure Information Protection Unified Labeling-Client.

Für die Verwendung der automatischen oder empfohlenen Vertraulichkeits Kennzeichnung benötigen die Benutzer eine der folgenden Lizenzen:

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) oder höher

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software) oder höher

- [Azure Information Protection Premium P2](https://azure.microsoft.com/pricing/details/information-protection/)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Unterstützung für Sensitivitäts Bezeichnungs Funktionen in apps

Für jede Funktion wird in den folgenden Tabellen die minimale Version aufgelistet, die Sie benötigen, um die Vertraulichkeits Bezeichnungen mithilfe der integrierten Beschriftung zu unterstützen. Oder, wenn die Bezeichnungs Funktion in der öffentlichen Vorschau oder unter Review für eine zukünftige Version ist.

Neue Versionen der apps werden zu unterschiedlichen Zeiten für unterschiedliche Aktualisierungs Kanäle zur Verfügung gestellt. Weitere Informationen, einschließlich der Vorgehensweise zum Konfigurieren des Update Kanals, damit Sie eine neue Bezeichnungs Funktion testen können, die Sie interessieren, finden Sie unter [Overview of Update Channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus). Neue Funktionen in der privaten Vorschau sind nicht in der Tabelle enthalten, Sie können jedoch möglicherweise an diesen Vorschaubildern teilnehmen, indem Sie Ihre Organisation für das [private Preview-Programm für Microsoft Information Protection](https://aka.ms/mip-preview)nominieren.

Zusätzliche Funktionen sind verfügbar, wenn Sie den Azure Information Protection Unified Labeling-Client installieren, der nur auf Windows-Computern ausgeführt wird. Weitere Informationen finden Sie unter [vergleichen der Bezeichnungs Clients für Windows-Computer](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Funktionen zur Sensitivitäts Bezeichnung in Word, Excel und PowerPoint

|Funktion                                                                                                        |Windows Desktop |Mac-Desktop |iOS    |Android      |Netz                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Manuelles zuweisen, ändern oder Entfernen von Bezeichnungen](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Standardbezeichnung anwenden](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | Unter Review                                                        |
|[Begründung zum Ändern einer Bezeichnung erforderlich](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Hilfe Link zu einer benutzerdefinierten Hilfeseite bereitstellen](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Inhalt markieren](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Berechtigungen sofort zuweisen](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Benutzern die Zuweisung von Berechtigungen überlassen](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | Vorschau: im [monatlichen Kanal (gezielt)](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus#monthly-channel-for-office-365-proplus)            | Vorschau: in [Office Insider](https://office.com/insider)        | Unter Review   | Unter Review         | Unter Review                                                        |
|[Anzeigen der Bezeichnungs Verwendung mit Label Analytics](label-analytics.md) und Senden von Daten für Administratoren                      | Unter Review            | Unter Review        | Unter Review   | Unter Review         | Unter Review                                                        |
|[Festlegen, dass Benutzer eine Bezeichnung auf Ihre e-Mails und Dokumente anwenden müssen](sensitivity-labels.md#what-label-policies-can-do)   | Unter Review            | Unter Review        | Unter Review   | Unter Review         | Unter Review                                                        |
|[Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)                    | Vorschau: in [Office Insider](https://office.com/insider)                                  | Unter Review | Unter Review | Unter Review | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|Unterstützen des [automatischen Speicherns](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) und der gemeinsamen [Dokumenterstellung](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) für beschriftete und geschützte Dokumente | Unter Review | Unter Review | Unter Review | Unter Review | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>Sensitivitäts Bezeichnungs Funktionen in Outlook

|Funktion                                                                                                        |Outlook auf Windows-Desktop |Outlook auf dem Mac-Desktop  |Outlook unter iOS |Outlook unter Android |Outlook im Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Manuelles zuweisen, ändern oder Entfernen von Bezeichnungen](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Ja               |
|[Standardbezeichnung anwenden](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Ja               |
|[Begründung zum Ändern einer Bezeichnung erforderlich](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Ja               |
|[Hilfe Link zu einer benutzerdefinierten Hilfeseite bereitstellen](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Ja               |
|[Inhalt markieren](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Ja               |
|[Berechtigungen sofort zuweisen](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Ja               |
|[Benutzern die Zuweisung von Berechtigungen überlassen](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Ja               |
|[Anzeigen der Bezeichnungs Verwendung mit Label Analytics](label-analytics.md) und Senden von Daten für Administratoren                      | Unter Review                       | Unter Review                    | Unter Review           | Unter Review               | Unter Review               |
|[Festlegen, dass Benutzer eine Bezeichnung auf Ihre e-Mails und Dokumente anwenden müssen](sensitivity-labels.md#what-label-policies-can-do)   | Unter Review                       | Unter Review                    | Unter Review           | Unter Review               | Unter Review               |
|[Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)                    | Vorschau: Rollout für [Office Insider](https://office.com/insider)                       | Unter Review                    | Unter Review           | Unter Review               | Ja |
|

## <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Integrierter Office-Labeling-Client und Azure Information Protection-Client

Der integrierte Office-Bezeichnungs Client lädt Vertraulichkeits Bezeichnungen und Richtlinieneinstellungen für die Sensitivitäts Bezeichnung aus den folgenden Verwaltungszentren herunter:

- Microsoft 365 Compliance Center
- Microsoft 365 Security Center
- Office 365 Security & Compliance Center

Um den integrierten Office-Labeling-Client verwenden zu können, müssen Sie mindestens eine [Bezeichnungsrichtlinie](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) haben, die von einem der aufgelisteten Admin Center für Benutzer veröffentlicht wurde.

Wenn Benutzer jedoch einen der Azure Information Protection-Clients installiert haben ([Unified Labeling Client](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) oder [Classic Client](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)), ist der integrierte Bezeichnungs Clientstandard mäßig in Ihren Office-Apps deaktiviert. Um die integrierte Kennzeichnung anstelle des Azure Information Protection-Clients für Office-Apps zu verwenden, deaktivieren oder deinstallieren Sie das Office-Add-in für Azure Information Protection:

1. Führen Sie eine der folgenden Optionen aus:
    
    - **Für mehrere Computer:** Konfigurieren Sie die Gruppenrichtlinieneinstellung **verwenden Sie die Empfindlichkeits Funktion in Office, um Sie zu übernehmen und Sensitivitäts Bezeichnungen anzuzeigen** . Suchen Sie diese Einstellung unter **Benutzerkonfiguration/Administrative Vorlagen/Microsoft Office 2016/Sicherheitseinstellungen**. Stellen Sie diese Einstellung über Gruppenrichtlinien oder mithilfe des [Office-Cloud-Richtlinien Diensts](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)bereit.
    
    - **Für einen einzelnen Computer:** Informationen zum [permanenten deaktivieren oder entfernen](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) des Azure Information Protection-Add-Ins auf einem einzelnen Computer finden Sie unter "anzeigen, verwalten und Installieren von Add-Ins in Office-Programmen".

2. Starten Sie alle Office-Anwendungen neu.

Wenn Sie dieses Office-Add-in deaktivieren oder deinstallieren, bleibt der Azure Information Protection-Client installiert, sodass Sie weiterhin Dateien außerhalb Ihrer Office-Apps beschriften können. Beispielsweise mithilfe von Datei-Explorer oder PowerShell.

Informationen darüber, welche Features von den Azure Information Protection-Clients und dem integrierten Office-Labeling-Client unterstützt werden, finden Sie unter [choose the Labeling Client to use for Windows Computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) from the Azure Information Protection Documentation.

## <a name="protection-templates-and-sensitivity-labels"></a>Schutz Vorlagen und Sensitivitäts Bezeichnungen

Vom Administrator definierte [Schutz Vorlagen](https://docs.microsoft.com/azure/information-protection/configure-policy-templates), wie Sie für Office 365 Nachrichtenverschlüsselung definiert sind, werden in Office-Apps nicht angezeigt, wenn Sie die integrierte Beschriftung verwenden. Diese vereinfachte Darstellung zeigt, dass keine Schutz Vorlage ausgewählt werden muss, da die gleichen Einstellungen in Vertraulichkeits Bezeichnungen mit aktivierter Verschlüsselung enthalten sind.

Wenn Sie vorhandene Schutz Vorlagen in Bezeichnungen konvertieren müssen, verwenden Sie das Azure-Portal und die folgenden Anweisungen: [So konvertieren Sie Vorlagen in Bezeichnungen](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>IRM-Optionen (Information Rights Management) und Sensitivitäts Bezeichnungen

Vertraulichkeits Bezeichnungen, die Sie für die Verschlüsselung konfigurieren, entfernen die Komplexität von Benutzern, um Ihre eigenen Verschlüsselungseinstellungen anzugeben. In vielen Office-Apps können diese einzelnen Verschlüsselungseinstellungen weiterhin von Benutzern mithilfe von IRM-Optionen (Information Rights Management, Verwaltung von Informationsrechten) manuell konfiguriert werden. Beispielsweise für Windows-apps:

- Für ein Dokument: **Datei** > **Informationen** > **schützen** > des**Zugriffs auf Dokumente einschränken**
- für eine e-Mail: auf der Registerkarte " **Optionen** " > **verschlüsseln** 
  
Wenn Benutzer ein Dokument oder eine e-Mail anfänglich bezeichnen, können Sie Ihre Bezeichnungs Konfigurationseinstellungen immer mit ihren eigenen Verschlüsselungseinstellungen außer Kraft setzen. Zum Beispiel:

- Ein Benutzer wendet die **vertrauliche Bezeichnung alle Mitarbeiter** auf ein Dokument an, und diese Bezeichnung ist so konfiguriert, dass Verschlüsselungseinstellungen für alle Benutzer in der Organisation angewendet werden. Dieser Benutzer konfiguriert dann die IRM-Einstellungen manuell, um den Zugriff auf einen Benutzer außerhalb Ihrer Organisation einzuschränken. Das Endergebnis ist ein Dokument mit dem Namen " **vertraulich" alle Mitarbeiter** und verschlüsselt, aber Benutzer in Ihrer Organisation können Sie nicht wie erwartet öffnen.

- Ein Benutzer wendet die **vertrauliche Bezeichnung "nur Empfänger** " auf eine e-Mail an, und diese e-Mail ist so konfiguriert, dass die Verschlüsselungseinstellung " **nicht weiterleiten**" angewendet wird. Dieser Benutzer konfiguriert dann die IRM-Einstellungen manuell so, dass die e-Mail-Adresse uneingeschränkt ist. Das Endergebnis ist, dass die e-Mail-Adresse von Empfängern weitergeleitet werden kann, obwohl die **vertrauliche Bezeichnung "nur Empfänger** " angegeben ist.

- Ein Benutzer wendet die **Allgemeine** Bezeichnung auf ein Dokument an, und diese Bezeichnung ist nicht für die Anwendung der Verschlüsselung konfiguriert. Dieser Benutzer konfiguriert dann die IRM-Einstellungen manuell, um den Zugriff auf das Dokument einzuschränken. Das Endergebnis ist ein Dokument mit der Bezeichnung " **Allgemein** ", das aber auch Verschlüsselung anwendet, sodass einige Benutzer es nicht erwartungsgemäß öffnen können.

Wenn das Dokument oder die e-Mail-Adresse bereits beschriftet ist, kann ein Benutzer eine dieser Aktionen ausführen, wenn der Inhalt noch nicht verschlüsselt ist, oder wenn er den [Verwendungsrechten](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Export oder den Vollzugriff besitzt. 

Für eine einheitlichere Bezeichnungs Oberfläche mit aussagekräftiger Berichterstellung sollten Sie geeignete Bezeichnungen und Anleitungen für Benutzer bereitstellen, die nur Beschriftungen zum Schutz von Dokumenten anwenden. Zum Beispiel:

- Für Ausnahmefälle, in denen Benutzer eigene Berechtigungen zuweisen müssen, geben Sie Bezeichnungen an, mit denen [Benutzer ihre eigenen Berechtigungen zuweisen können](encryption-sensitivity-labels.md#let-users-assign-permissions). 

- Anstelle von Benutzern, die die Verschlüsselung manuell entfernen, nachdem Sie eine Bezeichnung ausgewählt haben, die die Verschlüsselung anwendet, stellen Sie eine Alternative unter Bezeichnung bereit, wenn Benutzer eine Bezeichnung mit derselben Klassifizierung, aber keine Verschlüsselung benötigen. Wie:
    - **Vertraulich \ alle Mitarbeiter**
    - **Vertraulich \ anyone (keine Verschlüsselung)**

> [!NOTE]
> Wenn Benutzer die Verschlüsselung manuell aus einem beschrifteten Dokument entfernen, das in SharePoint oder OneDrive gespeichert ist, und Sie die [Vertraulichkeits Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert](sensitivity-labels-sharepoint-onedrive-files.md)haben, wird die Bezeichnungs Verschlüsselung beim nächsten Zugriff oder Herunterladen des Dokuments automatisch wiederhergestellt. 

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Anwenden von Sensitivitäts Bezeichnungen auf Dateien, e-Mails und Anlagen

Benutzer können jeweils nur eine Bezeichnung für jedes Dokument oder jede e-Mail anwenden.

Wenn Sie eine e-Mail-Nachricht mit Anlagen bezeichnen, erben die Anlagen die Bezeichnung nicht mit einer Ausnahme:

- Bei der Anlage handelt es sich um ein Office-Dokument mit einer Bezeichnung, die keine Verschlüsselung zulässt, und die auf die e-Mail-Nachricht angewendete Bezeichnung wendet die Verschlüsselung an. In diesem Fall erbt das e-Mail-Office-Dokument das Label der e-Mail mit seinen Verschlüsselungseinstellungen.

Andernfalls: 

- Wenn die Anlagen eine Bezeichnung aufweisen, behalten Sie Ihre ursprünglich angewendete Bezeichnung bei.
- Wenn die Anlagen ohne Bezeichnung verschlüsselt sind, bleibt die Verschlüsselung erhalten, aber Sie werden nicht beschriftet.
- Wenn die Anlagen keine Bezeichnung haben, bleiben Sie nicht gekennzeichnet.

## <a name="sensitivity-label-compatibility"></a>Kompatibilität mit Vertraulichkeits Bezeichnungen

**Mit RMS-aufgeklärten apps**: Wenn Sie ein beschriftetes und verschlüsseltes Dokument oder eine e-Mail in einer [RMS-aufgeklärten Anwendung](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) öffnen, die keine Vertraulichkeits Bezeichnungen unterstützt, erzwingt die APP weiterhin Verschlüsselung und Rechteverwaltung.

**Mit dem Azure Information Protection-Client**: Sie können anzeigen und Ändern von Vertraulichkeits Bezeichnungen, die Sie für Dokumente und e-Mails mit dem Office-integrierten Labelling-Client mithilfe des Azure Information Protection-Clients und umgekehrt anwenden.

**Bei anderen Office-Versionen**: Jeder autorisierte Benutzer kann beschriftete Dokumente und e-Mails in anderen Office-Versionen öffnen. Sie können die Bezeichnung jedoch nur in unterstützten Office-Versionen oder mithilfe des Azure Information Protection-Clients anzeigen oder ändern. Unterstützte Office-App-Versionen sind im [vorherigen Abschnitt](#support-for-sensitivity-label-capabilities-in-apps)aufgeführt.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Unterstützung für SharePoint-und OneDrive-Dateien, die durch Sensitivitäts Bezeichnungen geschützt sind

Wenn Sie den integrierten Office-Bezeichnungs Client mit Office im Internet für Dokumente in OneDrive für Unternehmen oder SharePoint Online verwenden möchten, stellen Sie sicher, dass Sie sich für die Vorschau entschieden haben, um [Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive zu aktivieren](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="when-office-365-applies-content-marking-and-encryption"></a>Wenn Office 365 Inhalts Markierung und-Verschlüsselung anwendet

Office 365 wendet die Inhalts Markierung und-Verschlüsselung mit einer Sensitivitäts Bezeichnung unterschiedlich an, abhängig von der verwendeten app.

| App | Inhaltskennzeichnung | Verschlüsselung |
| --- | --- | --- |
| Word, Excel, PowerPoint auf allen Plattformen | Sofort | Sofort |
| Outlook für PC und Mac | Nachdem Exchange Online die e-Mail gesendet hat | Sofort |
| Outlook im Web, für iOS und Android | Nachdem Exchange Online die e-Mail gesendet hat | Nachdem Exchange Online die e-Mail gesendet hat |
|

## <a name="end-user-documentation"></a>Endbenutzerdokumentation

- [Anwenden von Vertraulichkeits-Beschriftungen auf Ihre Dokumente und E-Mails in Office](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Bekannte Probleme beim Anwenden von Vertraulichkeits-Beschriftungen auf Ihren Office-Dateien](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)
