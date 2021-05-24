---
title: Migrieren zu Microsoft 365 Business von Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Wenn Sie über ein Office 365 E3-Abonnement verfügen, aber nicht mehr als 300 Mitarbeiter haben, sollten Sie zu Microsoft 365 Business Premium.
ms.openlocfilehash: d139d07c946ff3efed3db3a73eb5e1a4ae66c190
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623603"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migrieren von Office 365 E3 zu Microsoft 365 Business Premium

Microsoft 365 Business Premium bietet alles, was Sie für Ihr kleines Unternehmen benötigen, und kombiniert die erstklassigen cloudbasierten Produktivitäts-Apps mit einfacher Geräteverwaltung und Sicherheit. Wenn Sie derzeit über ein Office 365 E3-Abonnement verfügen, aber nicht mehr als 300 Mitarbeiter haben, sollten Sie für zusätzliche Sicherheitsfeatures zu Microsoft 365 Business Premium wechseln.

Die Migration ist einfach: Zuerst wechseln Sie die Lizenzen, und alle Ihre Daten und Benutzerinformationen in Ihrem aktuellen Abonnement werden verwaltet. Nach der Migration müssen Sie die Features einrichten, die in der Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Unterschiede zwischen Office 365 E3 und Microsoft 365 Business Premium

Diese Tabelle zeigt die Unterschiede zwischen Microsoft 365 Business Premium und Office 365 E3.

| Feature    | Support in Microsoft 365 Business Premium    | Support in Office 365 E3 |
|:-------|:-----|:-----|
| **Lokal**        | | |
| Office Apps<sup>1</sup>    | Microsoft 365 Apps for Business    | Microsoft 365 Apps for Enterprise |
| **Cloud-Produktivitäts-Apps**        | | |
| Exchange Online und Outlook    | 50 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online-Archivierung    | 100 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online-Archivierung |
| Teams    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Office 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | Speichergrenzwert von 1 TB pro Benutzer    | Unbegrenzt | 
| Yammer, SharePoint Online, Planner, Stream    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Office 365 E3](../media/check-mark.png) |
| **Bedrohungsschutz**        | | |
| Microsoft Defender für Office 365 Plan 1 | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | Nicht enthalten, kann aber hinzugefügt werden |
| **Identitätsverwaltung**        | | |
| Self-Service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities|     ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| **Verwaltung von Geräten und Apps**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Aktivierung gemeinsam genutzter Computer|     ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Office 365 E3](../media/check-mark.png)| 
| Upgraderechte auf Windows 10 Pro von Win 7/8.1-Pro|     ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    ||
| **Schutz von Daten**        | | |
|Verhinderung von Datenverlust in Office 365|    ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)|![Enthalten in Office 365 E3](../media/check-mark.png)|
|Azure Information Protection Plan 1, BitLocker Erzwingung|![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)||
|Azure Information Protection Plan 1, Vertraulichkeitsbezeichnungen|![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)||
|**Clientzugriffslizenz (CAL-Rechte)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Enthalten in Office 365 E3](../media/check-mark.png)|

<sup>1</sup> Die Microsoft 365 Business Premium der Office-Apps umfasst keine Volumenaktivierung über Gruppenrichtlinien, App-Telemetrie, Updatesteuerelemente, Tabellenvergleich und -abfragen oder Business Intelligence.

## <a name="migration"></a>Migration

Anweisungen zum Migrieren [](../commerce/subscriptions/change-plans-manually.md) Ihres Abonnements finden Sie unter Manuelles Ändern von Plänen für Anweisungen, wenn Sie nur wenige Personen in die Microsoft 365 Business Premium. Sie können auch [alle Benutzer automatisch aktualisieren](../commerce/subscriptions/upgrade-to-different-plan.md)oder mit einem Partner zusammenarbeiten, um Ihr E3-Abonnement und Ihre Lizenzen in ein Microsoft 365 Business Premium verschieben.
In den folgenden Abschnitten werden die Änderungen beschrieben, die Sie gegebenenfalls vornehmen müssen, und was Sie nach der Migration tun können.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 Konfiguration und Daten des E3-Abonnements
Sie müssen vor der Migration keine Änderungen an Ihrem aktuellen Abonnement oder Ihren Daten vornehmen. Dazu gehören:

- Abonnementkonfiguration, z. B. DNS-Einträge und Domänennamen.
- Benutzer- und Gruppenkonten und Authentifizierungseinstellungen, z. B. mehrstufige Authentifizierung oder Richtlinien für bedingten Zugriff.
- Produktivitätsdienstkonfigurationen und ihre Daten, z. B. Teams, Exchange Online Postfächer, SharePoint Onlinewebsites, OneDrive for Business Ordner und OneNote Notizbücher.
- Office Anwendungen werden automatisch skaliert. Office 365 moderne Lizenzierung überprüft alle 72 Stunden die Lizenzzuweisung des Benutzers und konvertiert Office-Anwendungen in die Version, die dem Benutzerabonnement entspricht.

### <a name="windows-10"></a>Windows 10

Wenn Ihre Windows noch nicht auf Windows Pro Creator-Update installiert sind, aktualisieren Sie sie auf [Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Einrichten von Richtlinien zum Schutz von Benutzergeräten und -dateien

> [!NOTE]
> Wenn Sie die Office 365 und Geräte einrichten, werden diese Geräte  auf der Seite Geräte im Microsoft 365 admin center aufgeführt. Alle von Ihnen eingerichteten Richtlinien werden in der Liste der klassischen Richtlinien im [Intune-Portal angezeigt.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

Nachdem Sie Lizenzen für Microsoft 365 Business Premium zugewiesen haben, können Sie mit dem Schutz der Geräte und Dateien der Benutzer beginnen.

Wenn Sie alle Benutzer in Ihrer Organisation auf Microsoft 365 Business Premium aktualisiert haben, wird der Setup-Assistent auf der Startseite angezeigt, und Sie können die Schritte [einrichten Microsoft 365 Business Premium in](set-up.md) den Schritten des Setup-Assistenten zum Schutz von Dateien und mobilen Geräten ausführen.

Sie können die folgenden Schritte auch auf der Seite Geräte ausführen:
  
1. Wechseln Sie im Admin Center im  linken Navigations navi zu \> **Geräterichtlinien**.

2. Wählen Sie **auf der Seite** Geräterichtlinien die Option Hinzufügen **aus.**

3. Geben Sie **der Richtlinie im** Bereich Richtlinie hinzufügen  einen Namen zu, und wählen Sie dann in der Dropdownliste einen Richtlinientyp aus.

     Sie können Anwendungsrichtlinien für den Schutz von Dateien auf Android- und iPhone-Geräten sowie Windows 10 einrichten und Gerätekonfigurationsrichtlinien für Unternehmenseigene Windows 10 einrichten. Weitere Informationen finden Sie unter den folgenden Links:

  - [Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte](app-protection-settings-for-android-and-ios.md)

  - [Festlegen von Anwendungsschutzeinstellungen für Windows 10 Geräte](protection-settings-for-windows-10-devices.md)

  - [Festlegen von Geräteschutzeinstellungen für Windows 10 PCs](protection-settings-for-windows-10-pcs.md)
  
4. Nachdem Sie Richtlinien eingerichtet haben, können Sie und Ihre Mitarbeiter Geräte einrichten:

  - Unter [Einrichten von Windows für Microsoft 365 Business Premium finden](set-up-windows-devices.md) Sie Schritte für Windows Geräte. 

  - Unter [Einrichten mobiler Geräte für Microsoft 365 Business Premium finden Sie](set-up-mobile-devices.md) Schritte für Android-Smartphones und iPhones. 
  
### <a name="mailbox-size"></a>Postfachgröße

Microsoft 365 Business Premium hat einen Speichergrenzwert von 50 GB, während er Exchange Online Plan 1 verwendet. Bei der Migration zu Microsoft 365 Business Premium wird empfohlen, diesem Benutzer einen Exchange Online Plan 2 zuzuordnen und den Exchange Online Plan 1 zu entfernen, da beides nicht möglich ist.

### <a name="threat-protection"></a>Bedrohungsschutz

Nach der Migration zu Microsoft 365 Business Premium haben Sie Defender für Office 365. Eine Übersicht finden Sie Office 365 Microsoft [Defender.](../security/office-365-security/defender-for-office-365.md) Informationen zum Einrichten finden Sie [](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)unter [Einrichten sicherer Links,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)Einrichten sicherer Anlagen und Einrichten von [Antiphishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Informationen zur Verwendung von Vertraulichkeitsbezeichnungen finden Sie unter Übersicht über [Vertraulichkeitsbezeichnungen](../compliance/sensitivity-labels.md) und [Erstellen und Verwalten von Vertraulichkeitsbezeichnungen.](../business-video/create-sensitivity-labels.md)

## <a name="related-content"></a>Verwandte Inhalte

[Pläne manuell ändern](../commerce/subscriptions/change-plans-manually.md) (Artikel)\
[Aktualisieren Windows Geräte auf Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (Video)\
[Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte](app-protection-settings-for-android-and-ios.md) (Artikel)\
[Festlegen oder Bearbeiten von Anwendungsschutzeinstellungen für Windows 10 Geräte](protection-settings-for-windows-10-devices.md) (Artikel)\
[]

