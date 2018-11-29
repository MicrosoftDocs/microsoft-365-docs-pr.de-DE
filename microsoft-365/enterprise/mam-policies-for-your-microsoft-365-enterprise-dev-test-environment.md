---
title: MAM-Richtlinien für die Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie in diesem Test Lab Guide hinzufügen, dass Intune mobilen Anwendung (MAM) Informationsverwaltungsrichtlinien in Ihrer Microsoft 365 Enterprise test Environment.
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868188"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a>MAM-Richtlinien für die Microsoft 365 Enterprise-Testumgebung

Mit den Anweisungen in diesem Artikel fügen Sie Intune mobilen Anwendung (MAM) Informationsverwaltungsrichtlinien in Ihrer Microsoft 365 Enterprise test Environment.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise

Wenn Sie auf einfache Weise mit den Mindestanforderungen MAM Richtlinien konfigurieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie in einer simulierten Enterprise MAM Richtlinien konfigurieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testen der automatisiert Lizenzierung und Gruppenmitgliedschaft erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt. 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a>Phase 2: Erstellen und Bereitstellen von MAM-Richtlinien für iOS- und Android-Geräte

In dieser Phase werden zwei verschiedene MAM-Richtlinien erstellt und bereitgestellt: eine für iOS-Geräte und eine für Android-Geräte.
  
1. Wechseln Sie zu der Office 365-Portal unter ([https://portal.office.com](https://portal.office.com)) und melden Sie sich Test Office 365-Abonnement mit Ihrer globalen Administratorkonto an.
    
2. Öffnen Sie auf einer neuen Registerkarte Ihres Browsers das Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).

3. Klicken Sie auf der Azure Portal Registerkarte in Internet Explorer im Navigationsbereich klicken Sie auf **alle Dienste**, geben Sie **Intune**, und klicken Sie dann auf **Intune**.
    
4. Wenn Sie auf der **Microsoft-Intune** Blade **Sie noch nicht aktiviert noch Gerätemanagement** Meldung angezeigt wird, klicken Sie darauf. Klicken Sie in der **Verwaltung mobiler Geräte Autorität** Blade auf **Intune MDM Zertifizierungsstelle**, und klicken Sie dann auf **auswählen**. Aktualisieren Sie die Registerkarte Browser.
    
5. Klicken Sie im linken Navigationsbereich auf **Gruppen**.
    
6. Klicken Sie auf das Blade **Gruppen alle Gruppen** auf **+ neue Gruppe**.
    
7. Wählen Sie in der **Gruppe** Blade, **Office 365** für **Gruppentyp?**, geben Sie im Feld **Name** **iOS Gerätebenutzer verwaltet** , wählen Sie in **die Mitgliedschaft Typ** **zugewiesen** und dann auf **Erstellen**. 
    
8. Schließen Sie das Blatt **Gruppe**.
    
9. Klicken Sie auf das Blade **Gruppen alle Gruppen** auf **Hinzufügen**.
    
10. Wählen Sie in der **Gruppe** Blade, **Office 365** für **Gruppentyp?**, geben Sie im Feld **Name** **Android verwaltete Benutzer des Geräts** , wählen Sie in **die Mitgliedschaft Typ** **zugewiesen** und dann auf **Erstellen**.
    
11. Schließen Sie das Blade **Gruppen alle Gruppen** .
    
12. Klicken Sie auf dem Blatt **Intune** in der Liste **Schnelle Aufgaben** auf **Erstellen Sie eine Konformitätsrichtlinie**.
    
13. Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf **Richtlinie erstellen**.
    
14. Geben Sie auf dem Blatt **Richtlinie erstellen** im Feld **Name**, den Text **iOS** ein. Wählen Sie für **Plattform** die Option **iOS** aus, klicken Sie auf dem Blatt ** 	iOS-Kompatibilitätsrichtlinie** auf **OK**, und klicken Sie dann auf **Erstellen**.
    
15. Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf **Richtlinie erstellen**.
    
16. Geben Sie auf dem Blatt **Richtlinie erstellen** im Feld **Name**, den Text **Android** ein. Wählen Sie für **Plattform** die Option **Android** aus, klicken Sie auf dem Blatt **Android-Kompatibilitätsrichtlinie** auf **OK**, und klicken Sie dann auf **Erstellen**.
    
17. Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf den Richtliniennamen **Android**.
    
18. Klicken Sie im linken Navigationsbereich des Blatts **Android - Eigenschaften** auf **Zuweisungen**, und klicken Sie dann auf **Gruppen auswählen**.
    
19. Klicken Sie auf dem Blatt **Gruppen auswählen** auf die Gruppe **Verwaltete Android-Gerätebenutzer**, und klicken Sie dann auf **Auswählen**.
    
20. Klicken Sie auf **Speichern**, und schließen Sie das Blade **Android - Zuordnungen** .
    
21. Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf den Richtliniennamen **iOS**.
    
22. Klicken Sie im linken Navigationsbereich des Blatts **iOS - Eigenschaften** auf **Zuweisungen**, und klicken Sie dann auf **Gruppen auswählen**.
    
23. Klicken Sie auf dem Blatt **Gruppen auswählen** auf die Gruppe **Verwaltete iOS-Gerätebenutzer**, und klicken Sie dann auf **Auswählen**.
    
24. Klicken Sie auf **Speichern**, und schließen Sie das Blade **iOS - Zuordnungen** .
    
25. Schließen Sie das Blatt **Kompatibilitätsrichtlinienprofile**.
    
26. Klicken Sie auf dem Blatt **Intune** im linken Navigationsbereich auf **Apps verwalten**.
    
27. Klicken Sie auf dem Blatt **Mobile Apps** auf **Apps**.
    
28. Klicken Sie in der Liste der Apps auf **PowerPoint**.  
    
29. Klicken Sie auf dem Blatt **PowerPoint-Übersicht** auf **Zuweisungen > Gruppen auswählen > Verwaltete iOS-Geräte > Auswählen**. Wählen Sie im Feld **Typ** die Option **Verfügbar** aus, und klicken Sie dann auf **Speichern**.
    
30. Wiederholen Sie Schritt 29 für die folgenden apps:
    
    - Outlook für Android
    
    - Word für iOS
    
    - Excel für iOS
    
    - Outlook für iOS
    
    - Microsoft Dynamics CRM auf iPad für iOS
    
    - Microsoft Dynamics CRM auf iPhone für iOS
    
    - Dynamics CRM für Smartphones für Android
    
    - Dynamics CRM für Tablets für Android
    
    - Excel für Android
    
    - Word für Android
    
    - OneNote für iOS
    
31. Schließen Sie das Blatt **Mobile Apps - Apps**.
    
32. Klicken Sie auf dem Blatt **Mobile Apps** auf **App-Schutzrichtlinien**.
    
33. Klicken Sie auf dem Blatt **App-Schutzrichtlinien** auf **Richtlinie hinzufügen**.
    
34. Geben Sie auf dem Blatt **Richtlinie hinzufügen** den Namen **iOS** ein, und klicken Sie dann auf **Erforderliche Apps auswählen**.
    
35. Klicken Sie auf dem Blatt **Apps** auf **PowerPoint**, **Microsoft Dynamics CRM auf iPhone**, **Excel**, **Microsoft Dynamics CRM auf iPhone**, **Word**, **OneNote** und **Outlook**, und klicken Sie dann auf **Auswählen**.
    
36. Klicken Sie auf dem Blatt **Richtlinie hinzufügen** auf **Erstellen**.
    
37. Klicken Sie auf dem Blatt **App-Schutzrichtlinien** auf **Richtlinie hinzufügen**.
    
38. Geben Sie auf dem Blatt **Richtlinie hinzufügen** den Namen **Android** ein, wählen Sie unter **Plattform** die Option **Android** aus, und klicken Sie dann auf **Erforderliche Apps auswählen**.
    
39. Klicken Sie auf dem Blatt **Apps** auf **PowerPoint**, **Dynamics CRM für Tablets**, **Excel**, **Word**, **Outlook** und **Dynamics CRM für Smartphones**, und klicken Sie dann auf **Auswählen**.
    
40. Klicken Sie auf dem Blatt **Richtlinie hinzufügen** auf **Erstellen**.
    
Sie nun verfügen über zwei MAM-Richtlinien, eine für iOS-Geräte und eine für Android-Geräte, und können nun mit verschiedenen Einstellungen für die ausgewählten Apps experimentieren. 
  
## <a name="next-step"></a>Nächster Schritt

Hier finden Sie zusätzliche [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) Features und Funktionen in Ihrer testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).
  
[Registrieren von iOS- und Android-Geräten in Ihrer Testumgebung für Microsoft 365 Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise-Mobilität + Sicherheit (zur Abstimmung)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
