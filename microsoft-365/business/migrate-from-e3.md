---
title: Migrieren zu Microsoft 365 Business von Office 365 E3
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
description: Informationen zum Migrieren Ihres Unternehmens zu Microsoft 365 Business von Office 365 E3.
ms.openlocfilehash: b86a163792aa71f0bca115ab918e0800acc0427d
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409680"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a>Migrieren von Office 365 E3 zu Microsoft 365 Business 

Microsoft 365 Business verfügt über alles, was Sie für Ihr kleines Unternehmen benötigen, und kombiniert die branchenbesten Cloud-basierten Produktivitäts-apps mit einfacher Geräteverwaltung und Sicherheit. Wenn Sie derzeit über ein Office 365 E3-Abonnement verfügen, aber nicht über mehr als 300 Mitarbeiter verfügen, sollten Sie zum Hinzufügen von Sicherheitsfeatures zu Microsoft 365 Business wechseln.

Die Migration ist einfach: zuerst wechseln Sie die Lizenzen, und alle Ihre Daten und Benutzerinformationen in Ihrem aktuellen Abonnement werden beibehalten. Nach der Migration müssen Sie die Features einrichten, die in Microsoft 365 Business hinzugefügt werden.

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a>Unterschiede zwischen Office 365 E3 und Microsoft 365 Business

In dieser Tabelle sind die Unterschiede zwischen Microsoft 365 Business und Office 365 E3 aufgeführt.

| Feature    | Unterstützung in Microsoft 365 Business    | Unterstützung in Office 365 E3 | 
|:-------|:-----|:-----|
| **Lokal**        | | | 
| Office-Apps<sup>1</sup>    | Office 365 Business    | Office 365 ProPlus | 
| **Apps für die Cloud-Produktivität**        | | | 
| Exchange Online und Outlook    | 50 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online Archivierung    | 100 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online Archivierung | 
| Teams    | ![Im Lieferumfang von Microsoft 365 Business enthalten](../media/check-mark.png)    | ![Im Lieferumfang von Office 365 E3 enthalten](../media/check-mark.png) | 
| OneDrive for Business    | 1 TB Speichergrenzwert pro Benutzer    | Unbegrenzt | 
| Jammern, SharePoint Online, Planer, Stream    | ![Im Lieferumfang von Microsoft 365 Business enthalten](../media/check-mark.png)    | ![Im Lieferumfang von Office 365 E3 enthalten](../media/check-mark.png) | 
| StaffHub    | ![Im Lieferumfang von Microsoft 365 Business enthalten](../media/check-mark.png)    | ![Im Lieferumfang von Office 365 E3 enthalten](../media/check-mark.png) | 
| Outlook-Kunden Manager, MileIQ    | ![Im Lieferumfang von Microsoft 365 Business enthalten](../media/check-mark.png)    | | 
| **Bedrohungsschutz**        | | | 
| Office 365 Advanced Threat Protection (ATP) Plan 1 | ![Im Lieferumfang von Microsoft 365 Business enthalten](../media/check-mark.png)    | Nicht enthalten, kann aber hinzugefügt werden | 
| **Identitätsverwaltung**        | | | 
| Self-Service Password Reset für hybride Azure Active Directory (Azure AD)-Konten, Azure Multi-Factor Authentication (MFA), bedingter Zugriff, Kenn Wort Rückschreiben für lokale Identitäten|     ![Im Lieferumfang von Microsoft 365 Business enthalten](../media/check-mark.png)    |  | 
| **Geräte-und App-Verwaltung**        | | |
| Microsoft InTune, Windows Autopilot|     ![Im Lieferumfang von Microsoft 365 Business enthalten](../media/check-mark.png)    |  |
| Aktivierung gemeinsam genutzter Computer|     ![Im Lieferumfang von Microsoft 365 Business enthalten](../media/check-mark.png)    | ![Im Lieferumfang von Office 365 E3 enthalten](../media/check-mark.png)| 
| Aktualisieren von Rechten auf Windows 10 pro von Win 7/8.1 pro-Lizenzen|     ![Im Lieferumfang von Microsoft 365 Business enthalten](../media/check-mark.png)    || 
| **Schutz von Daten**        | | |
|Verhinderung von Datenverlust in Office 365|    ![Im Lieferumfang von Microsoft 365 Business enthalten](../media/check-mark.png)|![Im Lieferumfang von Office 365 E3 enthalten](../media/check-mark.png)|
|Azure Information Protection Plan 1, BitLocker-Erzwingung|![Im Lieferumfang von Microsoft 365 Business enthalten](../media/check-mark.png)||
|Azure Information Protection-Plan 1, Sensitivitäts Bezeichnungen|![Im Lieferumfang von Microsoft 365 Business enthalten](../media/check-mark.png)||
|**Client Zugriffslizenz (CAL-Rechte)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Im Lieferumfang von Office 365 E3 enthalten](../media/check-mark.png)|

<sup>1</sup> die Microsoft 365 Business-Version der Office-Apps umfasst keine Volumenaktivierung über Gruppenrichtlinien, App-Telemetrie, Update Steuerelemente, Arbeitsblatt Vergleich und erkundigen oder Business Intelligence.

## <a name="migration"></a>Migration

Informationen zum Migrieren Ihres Abonnements finden Sie unter [Ändern von Plänen manuell](../commerce/subscriptions/change-plans-manually.md) für Anweisungen, wenn Sie nur einige wenige Personen zu Microsoft 365 Business verschieben möchten. Sie können auch [alle automatisch aktualisieren](../commerce/subscriptions/upgrade-to-different-plan.md)oder mit einem Partner zusammenarbeiten, um Ihr E3-Abonnement und ihre Lizenzen in ein Microsoft 365 Business-Abonnement zu migrieren.
In den folgenden Abschnitten werden die Änderungen beschrieben, die Sie vornehmen müssen, falls vorhanden, und was Sie nach der Migration tun können.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3-Abonnementkonfiguration und-Daten
Sie müssen keine Änderungen am aktuellen Abonnement oder an den Daten vor der Migration vornehmen, einschließlich:

- Abonnementkonfiguration, wie DNS-Einträge und Domänennamen.
- Benutzer-und Gruppenkonten und Authentifizierungseinstellungen, beispielsweise mehrstufige Authentifizierung oder Richtlinien für bedingten Zugriff.
- Produktivitäts Dienstkonfigurationen und deren Daten wie Teams, Exchange Online Postfächern, SharePoint Online Websites, OneDrive für Unternehmen Ordnern und OneNote-Notizbüchern.

### <a name="windows-10"></a>Windows 10

Wenn sich Ihre Windows-Version nicht bereits auf dem Windows pro Creator-Update befindet, führen [Sie ein Upgrade auf Windows pro Creators Update durch](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Einrichten von Richtlinien zum Schutz von Benutzergeräten und-Dateien

> [!NOTE]
> Wenn Sie Office 365 MDM-Richtlinien und-Geräte einrichten, werden diese Geräte auf der Seite **Geräte** im Microsoft 365 Admin Center aufgeführt. Alle Richtlinien, die Sie einrichten, werden in der Liste der klassischen Richtlinien im [InTune-Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)angezeigt.

Nachdem Sie Microsoft 365 Business Lizenzen zugewiesen haben, können Sie mit dem Schutz der Geräte und Dateien der Benutzer beginnen.

Wenn Sie alle in Ihrer Organisation auf Microsoft 365 Business aktualisiert haben, wird der Setup-Assistent auf der Startseite angezeigt, und Sie können die Schritte zum [Einrichten von Microsoft 365 Business im Setup-Assistenten](set-up.md) ausführen, um Dateien und mobile Geräte zu schützen.

Sie können diese Schritte auch auf der Seite Geräte ausführen:
  
1. Wechseln Sie im Admin Center im linken Navigationsbereich zu **Geräte** \> **Richtlinien**.
    
2. Klicken Sie auf der Seite **Geräterichtlinien** auf **Hinzufügen**.
    
3. Geben Sie im Bereich **Richtlinie hinzufügen** der Richtlinie einen Namen, und wählen Sie dann einen **Richtlinientyp** aus der Dropdownliste aus. 
    
     Sie können Anwendungsrichtlinien zum Schützen von Dateien auf Android-und iPhone-Geräten sowie Windows 10 einrichten, und Sie können Geräte Konfigurationsrichtlinien für Windows 10-Geräte im Unternehmen einrichten. Weitere Informationen finden Sie unter den folgenden Links:
    
  - [Festlegen von App-Schutzeinstellungen für Android-oder IOS-Geräte](app-protection-settings-for-android-and-ios.md)
    
  - [Festlegen von Anwendungsschutz Einstellungen für Windows 10-Geräte](protection-settings-for-windows-10-devices.md)
    
  - [Festlegen von Geräteschutz Einstellungen für Windows 10-PCs](protection-settings-for-windows-10-pcs.md)
  
4. Nachdem Sie Richtlinien eingerichtet haben, können Sie und ihre mitarbeitergeräte einrichten:
    
  - Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365 Business Users](set-up-windows-devices.md) für Schritte für Windows-Geräte. 
    
  - Weitere Informationen finden Sie unter [Einrichten von mobilen Geräten für Microsoft 365 Business-Benutzer](set-up-mobile-devices.md) für Schritte für Android-Telefone und iPhones. 

### <a name="threat-protection"></a>Bedrohungsschutz

Nach der Migration zu Microsoft 365 Business haben Sie Office 365 ATP. Eine Übersicht finden Sie unter [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) . Informationen zum Einrichten finden Sie unter [Einrichten von ATP-Safe-Links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), einrichten [von ATP-Tresoranlagen](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)und [Einrichten von ATP-Anti-Phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Informationen zur Verwendung von Sensitivitäts Bezeichnungen finden Sie unter [Übersicht über Sensitivitäts Bezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) und [Erstellen und Verwalten von Sensitivitäts Beschriftungen](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) (Video).
