---
title: Migrieren von Office 365 E3 zu Microsoft 365 Business
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
description: Erfahren Sie, wie Sie Ihr Unternehmen von Office 365 E3 zu Microsoft 365 Business Premium verschieben.
ms.openlocfilehash: f2b7962918186f4a1063c5a66596135c2972ec71
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51749998"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migrieren von Office 365 E3 zu Microsoft 365 Business Premium

Microsoft 365 Business Premium bietet alles, was Sie für Ihr kleines Unternehmen benötigen, und kombiniert die erstklassigen cloudbasierten Produktivitäts-Apps mit einfacher Geräteverwaltung und -sicherheit. Wenn Sie derzeit über ein Office 365 E3-Abonnement verfügen, aber nicht mehr als 300 Mitarbeiter haben, sollten Sie für zusätzliche Sicherheitsfeatures zu Microsoft 365 Business Premium wechseln.

Die Migration ist einfach: Zuerst wechseln Sie die Lizenzen, und alle Ihre Daten und Benutzerinformationen in Ihrem aktuellen Abonnement werden verwaltet. Nach der Migration müssen Sie die Features einrichten, die in Microsoft 365 Business Premium hinzugefügt werden.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Unterschiede zwischen Office 365 E3 und Microsoft 365 Business Premium

Diese Tabelle zeigt die Unterschiede zwischen Microsoft 365 Business Premium und Office 365 E3.

| Feature    | Support in Microsoft 365 Business Premium    | Support in Office 365 E3 | 
|:-------|:-----|:-----|
| **Lokal**        | | | 
| Office Apps<sup>1</sup>    | Microsoft 365 Apps for Business    | Microsoft 365 Apps for Enterprise | 
| **Cloud-Produktivitäts-Apps**        | | | 
| Exchange Online und Outlook    | 50 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online-Archivierung    | 100 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online-Archivierung | 
| Teams    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Office 365 E3 enthalten](../media/check-mark.png) | 
| OneDrive for Business    | Speichergrenzwert von 1 TB pro Benutzer    | Unbegrenzt | 
| Yammer, SharePoint Online, Planner, Stream    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Office 365 E3 enthalten](../media/check-mark.png) | 
| StaffHub    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Office 365 E3 enthalten](../media/check-mark.png) | 
| MileIQ    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | | 
| **Bedrohungsschutz**        | | | 
| Microsoft Defender für Office 365 Plan 1 | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | Nicht enthalten, kann aber hinzugefügt werden | 
| **Identitätsverwaltung**        | | | 
| Self-Service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    |  | 
| **Verwaltung von Geräten und Apps**        | | |
| Microsoft Intune, Windows AutoPilot|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    |  |
| Aktivierung gemeinsam genutzter Computer|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Office 365 E3 enthalten](../media/check-mark.png)| 
| Upgraderechte auf Windows 10 Pro von Win 7/8.1 Pro-Lizenzen|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    || 
| **Schutz von Daten**        | | |
|Verhinderung von Datenverlust in Office 365|    ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)|![In Office 365 E3 enthalten](../media/check-mark.png)|
|Azure Information Protection Plan 1, BitLocker-Erzwingung|![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)||
|Azure Information Protection Plan 1, Vertraulichkeitsbezeichnungen|![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)||
|**Clientzugriffslizenz (CAL-Rechte)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![In Office 365 E3 enthalten](../media/check-mark.png)|

<sup>1</sup> Die Microsoft 365 Business Premium-Version der Office-Apps umfasst keine Volumenaktivierung über Gruppenrichtlinien, App-Telemetrie, Updatesteuerelemente, Tabellenkalkulationsvergleiche und -abfragen oder Business Intelligence.

## <a name="migration"></a>Migration

Anweisungen zum Migrieren [](../commerce/subscriptions/change-plans-manually.md) Ihres Abonnements finden Sie unter Manuelles Ändern von Plänen, wenn Sie nur wenige Personen zu Microsoft 365 Business Premium verschieben möchten. Sie können auch [alle Benutzer automatisch aktualisieren](../commerce/subscriptions/upgrade-to-different-plan.md)oder mit einem Partner zusammenarbeiten, um Ihr E3-Abonnement und Ihre Lizenzen in ein Microsoft 365 Business Premium-Abonnement zu verschieben.
In den folgenden Abschnitten werden die Änderungen beschrieben, die Sie gegebenenfalls vornehmen müssen, und was Sie nach der Migration tun können.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3-Abonnementkonfiguration und -daten
Sie müssen vor der Migration keine Änderungen an Ihrem aktuellen Abonnement oder Ihren Daten vornehmen. Dazu gehören:

- Abonnementkonfiguration, z. B. DNS-Einträge und Domänennamen.
- Benutzer- und Gruppenkonten und Authentifizierungseinstellungen, z. B. mehrstufige Authentifizierung oder Richtlinien für bedingten Zugriff.
- Produktivitätsdienstkonfigurationen und deren Daten, z. B. Teams, Exchange Online-Postfächer, SharePoint #A0, OneDrive for #A1 und OneNote-Notizbücher.
- Office-Anwendungen werden automatisch skaliert. Moderne Office 365-Lizenzierung überprüft alle 72 Stunden die Lizenzzuweisung des Benutzers und konvertiert Office-Anwendungen in die Version, die dem Benutzerabonnement entspricht.

### <a name="windows-10"></a>Windows 10

Wenn Ihre Windows noch nicht unter Windows Pro Creator Update sind, aktualisieren Sie sie [auf Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Einrichten von Richtlinien zum Schutz von Benutzergeräten und -dateien

> [!NOTE]
> Wenn Sie Office 365-MDM-Richtlinien und -Geräte einrichten, werden diese Geräte auf der Seite Geräte im Microsoft 365 Admin Center aufgeführt.  Alle von Ihnen eingerichteten Richtlinien werden in der Liste der klassischen Richtlinien im [Intune-Portal angezeigt.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

Nachdem Sie Microsoft 365 Business Premium Lizenzen zugewiesen haben, können Sie mit dem Schutz der Geräte und Dateien der Benutzer beginnen.

Wenn Sie alle Benutzer in Ihrer Organisation auf Microsoft 365 Business Premium aktualisiert haben, wird der Setup-Assistent auf der Startseite angezeigt, und Sie können die Schritte zum Einrichten von [Microsoft 365 Business Premium in](set-up.md) den Schritten des Setup-Assistenten befolgen, um Dateien und mobile Geräte zu schützen.

Sie können die folgenden Schritte auch auf der Seite Geräte ausführen:
  
1. Wechseln Sie im Admin Center im  linken Navigations navi zu \> **Geräterichtlinien**.
    
2. Wählen Sie **auf der Seite** Geräterichtlinien die Option Hinzufügen **aus.**
    
3. Geben Sie **der Richtlinie im** Bereich Richtlinie hinzufügen  einen Namen zu, und wählen Sie dann in der Dropdownliste einen Richtlinientyp aus. 
    
     Sie können Anwendungsrichtlinien zum Schutz von Dateien auf Android- und iPhone-Geräten sowie Windows 10 einrichten und Gerätekonfigurationsrichtlinien für Windows 10-Geräte im Besitz des Unternehmens einrichten. Weitere Informationen finden Sie unter den folgenden Links:
    
  - [Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte](app-protection-settings-for-android-and-ios.md)
    
  - [Festlegen von Anwendungsschutzeinstellungen für Windows 10-Geräte](protection-settings-for-windows-10-devices.md)
    
  - [Festlegen von Geräteschutzeinstellungen für Windows 10-PCs](protection-settings-for-windows-10-pcs.md)
  
4. Nachdem Sie Richtlinien eingerichtet haben, können Sie und Ihre Mitarbeiter Geräte einrichten:
    
  - Schritte für Windows-Geräte finden Sie unter Einrichten von Windows-Geräten für [Microsoft 365 Business](set-up-windows-devices.md) Premium-Benutzer. 
    
  - Unter [Einrichten mobiler Geräte für Microsoft 365 Business Premium-Benutzer](set-up-mobile-devices.md) finden Sie Schritte für Android-Smartphones und iPhones. 
  
### <a name="mailbox-size"></a>Postfachgröße

Microsoft 365 Business Premium verfügt bei Verwendung von Exchange Online Plan 1 über einen Speichergrenzwert von 50 GB. Bei der Migration zu Microsoft 365 Business Premium wird empfohlen, diesem Benutzer einen Exchange Online Plan 2 zuzuordnen und den Exchange Online Plan 1 zu entfernen, da beides nicht möglich ist.


### <a name="threat-protection"></a>Bedrohungsschutz

Nach der Migration zu Microsoft 365 Business Premium haben Sie Defender für Office 365. Eine [Übersicht finden Sie unter Microsoft Defender for Office 365.](../security/office-365-security/defender-for-office-365.md) Informationen zum Einrichten finden Sie [](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)unter [Einrichten sicherer Links,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)Einrichten sicherer Anlagen und Einrichten [von Antiphishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Informationen zur Verwendung von Vertraulichkeitsbezeichnungen finden Sie unter Übersicht über [Vertraulichkeitsbezeichnungen](../compliance/sensitivity-labels.md) und [Erstellen und Verwalten von Vertraulichkeitsbezeichnungen.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)
