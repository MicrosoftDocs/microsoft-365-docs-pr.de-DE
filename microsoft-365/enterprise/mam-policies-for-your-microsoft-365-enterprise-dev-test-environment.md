---
title: Gerät Kompatibilitätsrichtlinien für Ihr Unternehmen der Microsoft 365 test Environment.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie in diesem Test Lab Guide hinzufügen, dass Intune Gerät Kompatibilitätsrichtlinien zu Ihrem Unternehmen der Microsoft 365 test Environment.
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868188"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Gerät Kompatibilitätsrichtlinien für Ihr Unternehmen der Microsoft 365 test Environment.

Mit den Anweisungen in diesem Artikel fügen Sie eine Richtlinie Intune Geräte Kompatibilität in Ihrer testumgebung Microsoft 365 Enterprise.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise

Wenn Sie auf einfache Weise mit den Mindestanforderungen MAM Richtlinien konfigurieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie in einer simulierten Enterprise MAM Richtlinien konfigurieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testen der automatisiert Lizenzierung und Gruppenmitgliedschaft erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Phase 2: Erstellen einer Richtlinie für Geräte Compliance für Windows 10 Geräte

In dieser Phase erstellen Sie eine Richtlinie für Geräte Compliance für Windows 10 Geräte.
  
1. Wechseln Sie zu der Office-Portal unter ([https://office.com](https://office.com)) und melden Sie sich Test Office 365-Abonnement mit Ihrer globalen Administratorkonto an.
    
2. Öffnen Sie auf einer neuen Registerkarte Ihres Browsers das Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).

3. Klicken Sie auf der Azure Portal Registerkarte in Ihrem Browser, klicken Sie im Navigationsbereich klicken Sie auf **alle Dienste**, geben Sie **Intune**, und klicken Sie dann auf **Intune**.
    
4. Wenn Sie auf der **Microsoft-Intune** Blade **Sie noch nicht aktiviert noch Gerätemanagement** Meldung angezeigt wird, klicken Sie darauf. Klicken Sie in der **Verwaltung mobiler Geräte Autorität** Blade auf **Intune MDM Zertifizierungsstelle**, und klicken Sie dann auf **auswählen**. Aktualisieren Sie die Registerkarte Browser.
    
5. Klicken Sie im linken Navigationsbereich auf **Gruppen**.
    
6. Klicken Sie auf das Blade **Gruppen alle Gruppen** auf **+ neue Gruppe**.
    
7. Wählen Sie in der **Gruppe** Blade, **Office 365** für **Gruppentyp?**, geben Sie im Feld **Name** **Gerätebenutzer verwalteten Windows 10** , wählen Sie in **die Mitgliedschaft Typ** **zugewiesen** und dann auf **Erstellen**. 
    
8. Schließen Sie das Blatt **Gruppe**.
    
11. Schließen Sie das Blade **Gruppen alle Gruppen** .
    
12. Klicken Sie auf der **Microsoft Intune** Blade, in der Liste **schnell Aufgaben** **Erstellen einer Compliance-Richtlinie**.
    
13. Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf **Richtlinie erstellen**.
    
14. Geben Sie auf der Blade **-Richtlinie erstellen** im Feld **Name** **Windows 10**. **Plattform**wählen Sie **Windows 10 und höher**, klicken Sie auf **OK** , auf dem **Windows-10-Compliance-Richtlinien** -Blade, und klicken Sie dann auf **Erstellen**. Schließen Sie das **Windows-10** -Blade.
    
15. Klicken Sie auf das Blade **Compliance Richtlinienprofilen** auf den Namen der Richtlinie **Windows 10** .
    
16. Klicken Sie in der **Windows-10** -Blade auf **Aufgaben**, und klicken Sie dann auf **Gruppen enthalten auswählen**.
    
17. Klicken Sie in der Blade **Gruppen enthalten auswählen** auf der **Windows-10 verwaltete Gerät** Benutzergruppe, und klicken Sie dann auf **auswählen**.
    
18. Klicken Sie auf **Speichern**, und schließen Sie das **Windows-10 - Zuordnungen** Blade.
    
19. Schließen Sie das Blatt **Kompatibilitätsrichtlinienprofile**.
    
20. Klicken Sie auf der **Microsoft-Intune** Blade im linken Navigationsbereich auf **Client-apps** .
    
21. Klicken Sie in den **Clientanwendungen** Blade auf **Apps**, und klicken Sie dann auf **Hinzufügen**. 

22. Wählen Sie in der Blade- **app hinzufügen** **App-Typ**aus, und wählen Sie dann **Windows 10** unter **Office 365-Suite**.

23. Klicken Sie auf **App-Suite konfigurieren**, und klicken Sie dann auf **OK**.

24. Klicken Sie auf **Informationen für App-Suite**, geben Sie **Office-Apps für Windows 10** **Suite Name**, **Office-Apps für Windows 10** in **Suite Beschreibung**, und klicken Sie dann auf **OK**.

25. Klicken Sie auf **App-Suite-Einstellungen**, wählen Sie **Semikolons jährlichen** in **Update-Kanal**aus und klicken Sie dann auf **OK**.

26. Klicken Sie auf das Blade **app hinzufügen** auf **Hinzufügen**.

Sie haben nun eine Gerät Compliance-Richtlinie für den ausgewählten apps in die **Windows-10** Gerät Compliance-Richtlinien Tests und Mitglieder der Gruppe **verwaltete Windows 10 Gerätebenutzer** . 
  
## <a name="next-step"></a>Nächster Schritt

Hier finden Sie zusätzliche [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) Features und Funktionen in Ihrer testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).
  
[Registrieren von iOS- und Android-Geräten in Ihrer Testumgebung für Microsoft 365 Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise-Mobilität + Sicherheit (zur Abstimmung)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
