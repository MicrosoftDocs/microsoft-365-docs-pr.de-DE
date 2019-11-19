---
title: Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung, um InTune-Geräte Konformitätsrichtlinien zu Ihrer Microsoft 365 Enterprise-Testumgebung hinzuzufügen.
ms.openlocfilehash: c323779399f6f440e1f9104e6611023a18ffe59e
ms.sourcegitcommit: ea48c86c727dcd9d4b3b970b14a4260337f158f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2019
ms.locfileid: "38694102"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*

Mit den Anweisungen in diesem Artikel fügen Sie eine InTune-Geräte Konformitätsrichtlinie zu Ihrer Microsoft 365 Enterprise-Testumgebung hinzu.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie MAM-Richtlinien nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie MAM-Richtlinien in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen der automatischen Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Phase 2: Erstellen einer Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte

In dieser Phase erstellen Sie eine Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte.
  
1. Wechseln Sie zum Office 365 Portal unter ([https://portal.office.com](https://portal.office.com)), und melden Sie sich bei Ihrem Office 365 Test Lab-Abonnement mit ihrem globalen Administratorkonto an.
    
2. Öffnen Sie auf einer neuen Registerkarte Ihres Browsers das Azure-Portal [https://portal.azure.com](https://portal.azure.com)unter.

3. Klicken Sie auf der Registerkarte Azure Portal in Ihrem Browser im Navigationsbereich auf **alle Dienste**, geben Sie **InTune**ein, und klicken Sie dann auf **InTune**.
    
4. Wenn Sie auf dem **Microsoft InTune** -Blade sehen, dass die Meldung **Geräteverwaltung noch nicht aktiviert** ist, klicken Sie darauf. Klicken Sie auf dem Blatt der **Verwaltungsautorität der mobilen Geräte** auf **InTune-MDM-Autorität**und dann auf **auswählen**. Aktualisieren Sie die Registerkarte Browser.
    
5. Klicken Sie im linken Navigationsbereich auf **Gruppen**.
    
6. Klicken Sie auf dem Blatt **Gruppen-alle Gruppen** auf **+ neue Gruppe**.
    
7. Wählen Sie auf dem **Gruppen** Blatt **Office 365** oder **Sicherheit** für **Gruppentyp?**, geben Sie **verwaltete Windows 10-Geräte Benutzer** unter **Name**ein, wählen Sie in **Mitgliedschafts** **zugewiesen** aus, und klicken Sie dann auf **Erstellen**. 
    
8. Schließen Sie das Blatt **Gruppe**.
    
11. Schließen Sie das Blade **Gruppen – alle Gruppen** .
    
12. Klicken Sie auf dem **Microsoft InTune** -Blade in der Liste **schnell Aufgaben** auf **Konformitätsrichtlinie erstellen**.
    
13. Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf **Richtlinie erstellen**.
    
14. Geben Sie auf dem Blatt **Richtlinien erstellen** unter **Name den Namen** **Windows 10**ein. Wählen Sie unter **Plattform**die Option **Windows 10 und höher**aus, klicken Sie auf dem Blade **Windows 10-Konformitätsrichtlinie** auf **OK** , und klicken Sie dann auf **Erstellen**. Schließen Sie das **Windows 10** -Blade.
    
15. Klicken Sie auf dem Blatt **Konformitätsrichtlinien profile** auf den Richtliniennamen **Windows 10** .
    
16. Klicken Sie auf dem **Windows 10** -Blade auf **Zuweisungen**, und klicken Sie dann auf **einzubeziehende Gruppen auswählen**.
    
17. Klicken Sie auf der Gruppe **zum einschließen** von Blade-Gruppen auswählen auf die Gruppe **verwaltete Windows 10-Geräte Benutzer** , und klicken Sie dann auf **auswählen**.
    
18. Klicken Sie auf **Speichern**, und schließen Sie dann das Blade **Windows 10-Assignments** .
    
19. Schließen Sie das Blatt **Kompatibilitätsrichtlinienprofile**.
    
20. Klicken Sie auf dem **Microsoft InTune** -Blade im linken Navigationsbereich auf **Client-apps** .
    
21. Klicken Sie auf dem Blade **Client apps** auf **apps**, und klicken Sie dann auf **Hinzufügen**. 

22. Wählen Sie im App-Blade **Hinzufügen** die Option **App-Typ**aus, und wählen Sie dann unter **Office 365 Suite**die Option **Windows 10** aus.

23. Klicken Sie auf **App-Suite konfigurieren**, und klicken Sie dann auf **OK**.

24. Klicken Sie auf **App Suite-Informationen**, geben Sie **Office-Apps für Windows 10** in **Suite Name**, **Office-Apps für Windows 10** in **Suite Description**ein, und klicken Sie dann auf **OK**.

25. Klicken Sie auf **App Suite-Einstellungen**, wählen Sie **halbjährlich** in **Update Kanal**aus, und klicken Sie dann auf **OK**.

26. Klicken Sie auf dem Blatt **app hinzufügen** auf **Hinzufügen**.

Sie verfügen nun über eine Geräte Kompatibilitäts Richtlinie zum Testen der ausgewählten apps in der **Windows 10** -Geräte Kompatibilitäts Richtlinie und für Mitglieder der **verwalteten Windows 10-Geräte Benutzer** Gruppe. Beachten Sie, dass beim Auswählen von Office 365 als Gruppentyp zusätzliche Ressourcen erstellt werden. 
  
## <a name="next-step"></a>Nächster Schritt

Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).
  
[Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
