---
title: Vertraulichkeitsbezeichnungen in Office-Apps
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/20/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Benutzer mit Vertraulichkeits Bezeichnungen in Office-Apps für den Desktop, Office-Apps für Mobilgeräte und Office-Apps für das Internet arbeiten. Finden Sie heraus, welche apps Vertraulichkeits Bezeichnungen unterstützen.
ms.openlocfilehash: 1b472185df2d45717cba6cfca30176768bf9cd4e
ms.sourcegitcommit: 5f96fa472cbdca30c2cfe24d66c9c6fcaedb1a6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "38755593"
---
# <a name="sensitivity-labels-in-office-apps"></a>Vertraulichkeitsbezeichnungen in Office-Apps

Inhalt dieses Artikels

- Anforderungen für Ihre Umgebung, bevor Sie Vertraulichkeits Bezeichnungen auf e-Mails, Dateien und Anlagen anwenden.
- Welche Empfindlichkeits Beschriftungsfunktionen von jeder Office-App unterstützt werden.
- Was geschieht, wenn Sie Sensitivitäts Bezeichnungen mit anderen Microsoft-Sicherheits-und-Konformitäts Technologien kombinieren, die mit Office-apps funktionieren.
- Wie Personen in Ihrer Organisation Sensitivitäts Bezeichnungen verwenden können, wenn Sie mit Office-Apps für Windows und Office-Apps für das Internet arbeiten.
- Wohin Sie gehen, um Personen in Ihrer Organisation mit Sensitivitäts Bezeichnungen zu starten.

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Abonnement-und Lizenzierungsanforderungen für Sensitivitäts Bezeichnungen

Benutzern muss mindestens eine der folgenden Lizenzen zugewiesen sein:

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) oder höher

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software) oder höher

- [Azure Information Protection Premium P1](https://azure.microsoft.com/pricing/details/information-protection/) oder höher

Der integrierte Office-Labeling-Client unterstützt Sensitivitäts Bezeichnungen mit einer Abonnementversion von Office. Der Client unterstützt keine eigenständigen Versionen, beispielsweise Office 2016 oder Office 2019.

Für die Verwendung der automatischen oder empfohlenen Vertraulichkeits Kennzeichnung benötigen die Benutzer eine der folgenden Lizenzen:

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) oder höher

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software) oder höher

- [Azure Information Protection Premium P2](https://azure.microsoft.com/pricing/details/information-protection/) oder höher

## <a name="support-for-sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Unterstützung für Sensitivitäts Bezeichnungs Funktionen in Word, Excel und PowerPoint

Für jede Funktion enthält die folgende Tabelle die Mindestversion, die Sie für diese APP benötigen. Das bedeutet, dass Sie diese Funktion nicht auf dieser Plattform verwenden können.

|Funktion                                                                                                        |Windows Desktop |Mac-Desktop |iOS    |Android      |Netz                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Manuelles zuweisen, ändern oder Entfernen von Bezeichnungen](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Standardbezeichnung anwenden](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | Noch nicht festgelegt                                                        |
|[Begründung zum Ändern einer Bezeichnung erforderlich](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Hilfelinks zu einer benutzerdefinierten Hilfeseite bereitstellen](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Inhalt markieren](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Berechtigungen sofort zuweisen](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Benutzern die Zuweisung von Berechtigungen überlassen](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | Noch nicht festgelegt            | Noch nicht festgelegt        | Noch nicht festgelegt   | Noch nicht festgelegt         | Noch nicht festgelegt                                                        |
|[Anzeigen der Bezeichnungs Verwendung mit Label Analytics](label-analytics.md) und Senden von Daten für Administratoren                      | Noch nicht festgelegt            | Noch nicht festgelegt        | Noch nicht festgelegt   | Noch nicht festgelegt         | Noch nicht festgelegt                                                        |
|
  [Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden](sensitivity-labels.md#what-label-policies-can-do)   | Noch nicht festgelegt            | Noch nicht festgelegt        | Noch nicht festgelegt   | Noch nicht festgelegt         | Noch nicht festgelegt                                                        |
|[Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)                    | Vorschau: in Rollout für [Office Insider](https://office.com/insider)                                  | Noch nicht festgelegt | Noch nicht festgelegt | Noch nicht festgelegt | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|Unterstützen des [automatischen Speicherns](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) und der gemeinsamen [Dokumenterstellung](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) für beschriftete und geschützte Dokumente | Noch nicht festgelegt | Noch nicht festgelegt | Noch nicht festgelegt | Noch nicht festgelegt | [Preview](sensitivity-labels-sharepoint-onedrive-files.md) |
|

## <a name="support-for-sensitivity-label-capabilities-in-outlook"></a>Unterstützung für Sensitivitäts Bezeichnungs Funktionen in Outlook

Für jede Funktion enthält die folgende Tabelle die Mindestversion, die Sie für diese APP benötigen. Das bedeutet, dass Sie diese Funktion nicht auf dieser Plattform verwenden können.

|Funktion                                                                                                        |Outlook auf Windows-Desktop |Outlook auf dem Mac-Desktop  |Outlook unter iOS |Outlook unter Android |Outlook im Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Manuelles zuweisen, ändern oder Entfernen von Bezeichnungen](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Ja               |
|[Standardbezeichnung anwenden](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Ja               |
|[Begründung zum Ändern einer Bezeichnung erforderlich](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Ja               |
|[Hilfelinks zu einer benutzerdefinierten Hilfeseite bereitstellen](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Ja               |
|[Inhalt markieren](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Ja               |
|[Berechtigungen sofort zuweisen](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Ja               |
|[Benutzern die Zuweisung von Berechtigungen überlassen](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Ja               |
|[Anzeigen der Bezeichnungs Verwendung mit Label Analytics](label-analytics.md) und Senden von Daten für Administratoren                      | Noch nicht festgelegt                       | Noch nicht festgelegt                    | Noch nicht festgelegt           | Noch nicht festgelegt               | Noch nicht festgelegt               |
|
  [Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden](sensitivity-labels.md#what-label-policies-can-do)   | Noch nicht festgelegt                       | Noch nicht festgelegt                    | Noch nicht festgelegt           | Noch nicht festgelegt               | Noch nicht festgelegt               |
|[Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)                    | Noch nicht festgelegt                       | Noch nicht festgelegt                    | Noch nicht festgelegt           | Noch nicht festgelegt               | Vorschau: in Rollout zur [zielgerichteten Veröffentlichung](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide) |
|

## <a name="about-the-office-built-in-labeling-client"></a>Informationen zum integrierten Labeling-Client für Office

Der integrierte Office-Bezeichnungs Client lädt Bezeichnungen und Richtlinieneinstellungen aus den folgenden Verwaltungszentren herunter:

- Office 365 Security & Compliance Center

- Microsoft 365 Security Center

- Microsoft 365 Compliance Center

Der integrierte Office-Labeling-Client wird automatisch für Benutzer aktiviert, die eine oder mehrere [Bezeichnungsrichtlinien](sensitivity-labels.md#what-label-policies-can-do) für Sie veröffentlicht haben.

Wenn Sie den integrierten Labeling-Client in Office unter Windows verwenden möchten, können Sie das Azure Information Protection-Add-in in Office nicht gleichzeitig ausführen. Sie können den Azure Information Protection-Client vorübergehend oder endgültig deinstallieren oder ihn installiert lassen und Office so konfigurieren, dass er nicht mehr funktioniert.

1. Führen Sie eine der folgenden Optionen aus:

    **Für mehrere Computer:** Konfigurieren Sie die Gruppenrichtlinieneinstellung **verwenden Sie die Empfindlichkeits Funktion in Office, um Sie zu übernehmen und Sensitivitäts Bezeichnungen anzuzeigen** . Suchen Sie diese Einstellung unter **Benutzerkonfiguration/Administrative Vorlagen/Microsoft Office 2016/Sicherheitseinstellungen**. Stellen Sie diese Einstellung über Gruppenrichtlinien oder mithilfe des [Office-Cloud-Richtlinien Diensts](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)bereit.

    **Für einen einzelnen Computer:** Siehe "anzeigen, verwalten und Installieren von Add-Ins in Office-Programmen" und [dauerhaftes deaktivieren oder entfernen](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) des Azure Information Protection-Add-Ins auf einem einzelnen Computer.

2. Starten Sie alle Office-Anwendungen neu.

Weitere Informationen zu Client-Apps für den Schutz von Informationen finden Sie auf [der Clientseite von Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/use-client).

## <a name="protection-templates-and-sensitivity-labels"></a>Schutz Vorlagen und Sensitivitäts Bezeichnungen

Vom Administrator definierte [Schutz Vorlagen](https://docs.microsoft.com/azure/information-protection/configure-policy-templates), wie Sie für Office 365 Nachrichtenverschlüsselung definiert sind, werden aus der Office-Benutzeroberfläche ausgeblendet, wenn Vertraulichkeits Bezeichnungen aktiviert sind, da Sie mit Sensitivitäts Bezeichnungen mit aktivierter Verschlüsselung redundant sind.

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Anwenden von Sensitivitäts Bezeichnungen auf Dateien, e-Mails und Anlagen

Benutzer können jeweils nur eine Bezeichnung für jedes Dokument oder jede e-Mail anwenden.

Wenn Sie eine e-Mail-Nachricht mit Anlagen bezeichnen, erben die Anlagen nicht die Bezeichnung. Wenn die Anlagen eine Bezeichnung aufweisen, behalten Sie diese separat angewendete Bezeichnung bei. Wenn die Anlagen keine Bezeichnung hatten, verbleiben die Anlagen ohne Beschriftung. Wenn die Bezeichnung für die E-Mail-Adresse aber Schutz anwendet, wird dieser Schutz für Office-Anlagen übernommen.

## <a name="sensitivity-label-compatibility"></a>Kompatibilität mit Vertraulichkeits Bezeichnungen

**Mit RMS-aufgeklärten apps**. Wenn Sie ein beschriftetes _und verschlüsseltes_ Dokument oder eine e-Mail in einer [RMS-aufgeklärten Anwendung](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) öffnen, die keine Vertraulichkeits Bezeichnungen unterstützt, erzwingt die APP weiterhin Verschlüsselung und Rechteverwaltung.

**Mit Azure Information Protection-Client**. Sie können Vertraulichkeits Bezeichnungen, die Sie auf Dokumente und e-Mails anwenden, mit dem integrierten Office-Bezeichnungs Client mit dem Azure Information Protection-Client anzeigen und ändern und umgekehrt.

**Mit anderen Versionen von Office**. Jeder autorisierte Benutzer kann beschriftete Dokumente und e-Mails in anderen Office-Versionen öffnen. Sie können die Bezeichnung jedoch nur in unterstützten Office-Versionen oder im Azure Information Protection-Client anzeigen oder ändern. Unterstützte Office-App-Versionen werden in den Tabellen in diesem Artikel aufgeführt.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Unterstützung für SharePoint-und OneDrive-Dateien, die durch Sensitivitäts Bezeichnungen geschützt sind

Um den integrierten Office-Bezeichnungs Client in Office im Internet verwenden zu können, muss sich das Dokument in einer OneDrive für Unternehmen-oder SharePoint Online-Instanz befinden, die sich für die [Aktivierung von Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)entschieden hat.

## <a name="when-office-365-applies-marks-and-encryption-to-content"></a>Wenn Office 365 Marken und Verschlüsselung auf Inhalte anwendet

Office 365 wendet Inhalts Markierungen oder die Verschlüsselung mit einer Sensitivitäts Bezeichnung je nach verwendeter Anwendung unterschiedlich an.

| Anwendung | Inhaltskennzeichnung | Verschlüsselung |
| --- | --- | --- |
| Word, Excel, PowerPoint auf allen Plattformen | Sofort | Sofort |
| Outlook für PC und Mac | Nachdem Exchange Online die e-Mail gesendet hat | Sofort |
| Outlook im Web, für iOS und Android | Nachdem Exchange Online die e-Mail gesendet hat | Nachdem Exchange Online die e-Mail gesendet hat |
|

## <a name="more-resources"></a>Weitere Ressourcen

[Häufig gestellte Fragen zur Klassifizierung und zu Bezeichnungen in Azure Information Protection](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)

[Anwenden von Vertraulichkeitsbezeichnungen auf Ihre Dokumente und E-Mails in Office](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
