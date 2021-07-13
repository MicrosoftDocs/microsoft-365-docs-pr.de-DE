---
title: Migrieren von Office 365 E3 zu Microsoft 365 Unternehmen
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: Wenn Sie über ein Office 365 E3 Abonnement verfügen, aber nicht mehr als 300 Mitarbeiter haben, sollten Sie zu Microsoft 365 Business Premium wechseln.
ms.openlocfilehash: c1b4da07b3bf28cce1a48424ab45cde6ea54d367
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394169"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migrieren von Office 365 E3 zu Microsoft 365 Business Premium

Microsoft 365 Business Premium bietet alles, was Sie für Ihr kleines Unternehmen benötigen, und kombiniert die besten cloudbasierten Produktivitäts-Apps mit einfacher Geräteverwaltung und Sicherheit. Wenn Sie derzeit über ein Office 365 E3 Abonnement verfügen, aber nicht mehr als 300 Mitarbeiter haben, sollten Sie für zusätzliche Sicherheitsfeatures zu Microsoft 365 Business Premium wechseln.

Die Migration ist einfach: Zuerst wechseln Sie die Lizenzen, und alle Daten und Benutzerinformationen in Ihrem aktuellen Abonnement werden verwaltet. Nach der Migration müssen Sie die Features einrichten, die in Microsoft 365 Business Premium hinzugefügt werden.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Unterschiede zwischen Office 365 E3 und Microsoft 365 Business Premium

Diese Tabelle zeigt die Unterschiede zwischen Microsoft 365 Business Premium und Office 365 E3.

| Feature    | Unterstützung in Microsoft 365 Business Premium    | Unterstützung in Office 365 E3 |
|:-------|:-----|:-----|
| **Lokal**        | | |
| Office Apps<sup>1</sup>    | Microsoft 365 Apps for Business    | Microsoft 365 Apps for Enterprise |
| **Cloud-Produktivitäts-Apps**        | | |
| Exchange Online und Outlook    | 50 GB Speicherlimit pro Postfach und unbegrenzte Exchange Online-Archivierung    | Speicherlimit von 100 GB pro Postfach und unbegrenzte Exchange Online-Archivierung |
| Microsoft Teams    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Office 365 E3 enthalten](../media/check-mark.png) | 
| OneDrive for Business    | 1 TB Speicherlimit pro Benutzer    | Unbegrenzt | 
| Yammer, SharePoint Online, Planner, Stream    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Office 365 E3 enthalten](../media/check-mark.png) | 
| StaffHub    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Office 365 E3 enthalten](../media/check-mark.png) |
| **Bedrohungsschutz**        | | |
| Microsoft Defender für Office 365 Plan 1 | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | Nicht enthalten, kann aber hinzugefügt werden |
| **Identitätsverwaltung**        | | |
| Self-Service Password Reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    |  |
| **Verwaltung von Geräten und Apps**        | | |
| Microsoft Intune, Windows AutoPilot|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    |  |
| Aktivierung gemeinsam genutzter Computer|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Office 365 E3 enthalten](../media/check-mark.png)| 
| Upgraderechte für Windows 10 Pro von Win 7/8.1-Pro-Lizenzen|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    ||
| **Schutz von Daten**        | | |
|Verhinderung von Datenverlust in Office 365|    ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)|![In Office 365 E3 enthalten](../media/check-mark.png)|
|Azure Information Protection Plan 1, BitLocker-Erzwingung|![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)||
|Azure Information Protection Plan 1, Vertraulichkeitsbezeichnungen|![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)||
|**Clientzugriffslizenz (CAL-Rechte)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![In Office 365 E3 enthalten](../media/check-mark.png)|

<sup>1</sup> Die Microsoft 365 Business Premium Version der Office-Apps umfasst keine Volumenaktivierung über Gruppenrichtlinien, App-Telemetrie, Updatesteuerelemente, Vergleich und Untersuchung von Tabellenkalkulationen oder Business Intelligence.

## <a name="migration"></a>Migration

Anweisungen zum Migrieren Ihres Abonnements finden Sie [unter "Pläne manuell ändern",](../commerce/subscriptions/change-plans-manually.md) wenn Sie nur einige Wenige in Microsoft 365 Business Premium verschieben möchten. Sie können auch [jeden automatisch aktualisieren](../commerce/subscriptions/upgrade-to-different-plan.md)oder mit einem Partner zusammenarbeiten, um Ihr E3-Abonnement und Ihre Lizenzen in ein Microsoft 365 Business Premium Abonnement zu verschieben.
In den folgenden Abschnitten werden die änderungen beschrieben, die Sie vornehmen müssen, falls vorhanden, und was Sie nach der Migration tun können.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3 Abonnementkonfiguration und -daten
Sie müssen vor der Migration keine Änderungen an Ihrem aktuellen Abonnement oder Ihren aktuellen Daten vornehmen, was Folgendes umfasst:

- Abonnementkonfiguration, z. B. DNS-Einträge und Domänennamen.
- Benutzer- und Gruppenkonten und Authentifizierungseinstellungen, z. B. mehrstufige Authentifizierung oder Richtlinien für bedingten Zugriff.
- Produktivitätsdienstkonfigurationen und deren Daten, z. B. Teams, Exchange Online Postfächer, SharePoint Onlinewebsites, OneDrive for Business Ordner und OneNote Notizbücher.
- Office Anwendungen werden automatisch skaliert. Office 365 moderne Lizenzierung überprüft alle 72 Stunden die Lizenzzuweisung des Benutzers und konvertiert Office Anwendungen in die Version, die dem Benutzerabonnement entspricht.

### <a name="windows-10"></a>Windows 10

Wenn Ihre Windows noch nicht auf Windows Pro Creator-Update sind, aktualisieren Sie [sie auf Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Einrichten von Richtlinien zum Schutz von Benutzergeräten und Dateien

> [!NOTE]
> Wenn Sie Office 365 MDM-Richtlinien und -Geräte einrichten, werden diese Geräte auf der Seite **"Geräte"** im Microsoft 365 Admin Center aufgeführt. Alle von Ihnen eingerichteten Richtlinien werden in der Liste der klassischen Richtlinien im [Intune-Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)angezeigt.

Nachdem Sie Microsoft 365 Business Premium Lizenzen zugewiesen haben, können Sie damit beginnen, die Geräte und Dateien der Benutzer zu schützen.

Wenn Sie alle Benutzer in Ihrer Organisation auf Microsoft 365 Business Premium aktualisiert haben, wird der Setup-Assistent auf der Startseite angezeigt, und Sie können den [Setup-Microsoft 365 Business Premium in den Schritten des Setup-Assistenten](set-up.md) befolgen, um Dateien und mobile Geräte zu schützen.

Sie können auch die folgenden Schritte auf der Seite "Geräte" ausführen:
  
1. Wechseln Sie im Admin Center im linken Navigationsbereich zu **"Geräterichtlinien".** \> 

2. Wählen Sie auf der Seite **"Geräterichtlinien"** die Option **"Hinzufügen"** aus.

3. Geben Sie der Richtlinie im Bereich **"Richtlinie hinzufügen"** einen Namen, und wählen Sie dann in der Dropdownliste einen **Richtlinientyp** aus.

     Sie können Anwendungsrichtlinien zum Schutz von Dateien auf Android- und iPhone-Geräten sowie Windows 10 einrichten und Gerätekonfigurationsrichtlinien für unternehmenseigene Windows 10 Geräte einrichten. Weitere Informationen finden Sie unter den folgenden Links:

  - [Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte](app-protection-settings-for-android-and-ios.md)

  - [Festlegen von Anwendungsschutzeinstellungen für Windows 10 Geräte](protection-settings-for-windows-10-devices.md)

  - [Festlegen von Geräteschutzeinstellungen für Windows 10 PCs](protection-settings-for-windows-10-pcs.md)
  
4. Nachdem Sie Richtlinien eingerichtet haben, können Sie und Ihre Mitarbeiter Geräte einrichten:

  - Unter ["Einrichten Windows Geräte für Microsoft 365 Business Premium Benutzer"](set-up-windows-devices.md) finden Sie Schritte für Windows Geräte. 

  - Unter ["Einrichten mobiler Geräte für Microsoft 365 Business Premium Benutzer"](set-up-mobile-devices.md) finden Sie Schritte für Android-Smartphones und iPhones. 
  
### <a name="mailbox-size"></a>Postfachgröße

Microsoft 365 Business Premium verfügt über einen Speichergrenzwert von 50 GB, da Exchange Online Plan 1 verwendet wird. Bei der Migration zu Microsoft 365 Business Premium wird empfohlen, diesem Benutzer einen Exchange Online Plan 2 zuzuweisen und den Exchange Online Plan 1 zu entfernen, da es nicht möglich ist, beide zuzuweisen, wenn einer Ihrer Benutzer 50 GB Postfachspeicher überschreitet.

### <a name="threat-protection"></a>Bedrohungsschutz

Nach der Migration zu Microsoft 365 Business Premium haben Sie Defender für Office 365. Eine Übersicht finden Sie [unter Microsoft Defender für Office 365.](../security/office-365-security/defender-for-office-365.md) Informationen zum Einrichten finden Sie unter [Einrichten Tresor Links,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa) [Einrichten Tresor Anlagen](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)und Einrichten von [Antiphishing in Defender für Office 365.](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Informationen zum Verwenden von Vertraulichkeitsbezeichnungen finden Sie im Video ["Übersicht über Vertraulichkeitsbezeichnungen"](../compliance/sensitivity-labels.md) und [zum Erstellen und Verwalten von Vertraulichkeitsbezeichnungen.](../business-video/create-sensitivity-labels.md)

## <a name="related-content"></a>Verwandte Inhalte

[Pläne manuell ändern](../commerce/subscriptions/change-plans-manually.md) (Artikel)\
[Upgrade Windows Geräte auf Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (Video)\
[Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte](app-protection-settings-for-android-and-ios.md) (Artikel)\
Festlegen oder Bearbeiten von [Anwendungsschutzeinstellungen für Windows 10 Geräte](protection-settings-for-windows-10-devices.md) (Artikel)\
[]

