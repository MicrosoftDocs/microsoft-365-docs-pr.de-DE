---
title: Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie dieses Test Labor Handbuch, um der Microsoft 365 Enterprise-Testumgebung InTune-Geräte Konformitätsrichtlinien hinzuzufügen.
ms.openlocfilehash: b8c2fbe437362f72effd5ba550817f847ccbbf74
ms.sourcegitcommit: e15cf5d0d8ff3dfdc457b469992d72ac802e6434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "33467733"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung

Mit den Anweisungen in diesem Artikel fügen Sie Ihrer Microsoft 365 Enterprise-Testumgebung eine InTune-Geräte Konformitätsrichtlinie hinzu.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie MAM-Richtlinien nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie MAM-Richtlinien in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist. Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und die Gruppenmitgliedschaft testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Phase 2: Erstellen einer Geräte Konformitätsrichtlinie für Windows 10-Geräte

In dieser Phase erstellen Sie eine Geräte Konformitätsrichtlinie für Windows 10-Geräte.
  
1. Wechseln Sie zum Office 365-Portal unter[https://portal.office.com](https://portal.office.com)(), und melden Sie sich bei ihrem Office 365-Test Lab-Abonnement mit ihrem globalen Administratorkonto an.
    
2. Öffnen Sie auf einer neuen Registerkarte Ihres Browsers das Azure-Portal [https://portal.azure.com](https://portal.azure.com)unter.

3. Klicken Sie auf der Registerkarte Azure Portal in Ihrem Browser im Navigationsbereich auf **alle Dienste**, geben Sie **InTune**ein, und klicken Sie dann auf **InTune**.
    
4. Wenn Sie auf dem **Microsoft InTune** -Blatt eine Meldung zur **Geräteverwaltung noch nicht aktiviert haben** , klicken Sie darauf. Klicken Sie auf dem Blatt für die **Verwaltung mobiler Geräte** auf **InTune MDM Authority**, und klicken Sie dann auf **auswählen**. Aktualisieren Sie die Registerkarte Browser.
    
5. Klicken Sie im linken Navigationsbereich auf **Gruppen**.
    
6. Klicken Sie auf dem Blatt **Gruppen-alle Gruppen** auf **+ neue Gruppe**.
    
7. wählen sie im **gruppen** blatt **Office 365** oder **sicherheit** für **gruppentyp?**, geben sie **verwaltete Windows 10-geräte benutzer** unter **Name**ein, wählen sie **zugewiesen** unter mitgliedschafts aus, und klicken sie dann auf **erstellen**. **** 
    
8. Schließen Sie das Blatt **Gruppe**.
    
11. Schließt das Blatt **Groups-all Groups** .
    
12. Klicken Sie auf dem **Microsoft InTune** -Blade in der Liste **schnell Aufgaben** auf **Konformitätsrichtlinie erstellen**.
    
13. Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf **Richtlinie erstellen**.
    
14. Geben Sie auf dem Blatt **Richtlinie erstellen** unter **Name den Namen** **Windows 10**ein. Wählen Sie unter **Plattform**die Option **Windows 10 und höher**aus, klicken Sie auf dem Blatt **Windows 10-Konformitätsrichtlinie** auf **OK** , und klicken Sie dann auf **Erstellen**. Schließt das **Windows 10** -Blade.
    
15. Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinien profile** auf den Richtliniennamen **Windows 10** .
    
16. Klicken Sie auf dem Blade **Windows 10** auf **Zuweisungen**, und klicken Sie dann auf einzuschließende **Gruppen auswählen**.
    
17. Klicken Sie auf dem Blade **zu verwendende Gruppen auswählen** auf die Gruppe **verwaltete Windows 10-Geräte Benutzer** , und klicken Sie dann auf **auswählen**.
    
18. Klicken Sie auf **Speichern**, und schließen Sie dann das Blade **Windows 10-Assignments** .
    
19. Schließen Sie das Blatt **Kompatibilitätsrichtlinienprofile**.
    
20. Klicken Sie auf dem **Microsoft InTune** -Blatt im linken navigationsBereich auf **Client-apps** .
    
21. Klicken Sie auf dem Blatt **Client apps** auf **apps**, und klicken Sie dann auf **Hinzufügen**. 

22. Wählen Sie im Blade **app hinzufügen** die Option **App-Typ**aus, und wählen Sie dann **Windows 10** unter **Office 365 Suite**aus.

23. Klicken Sie auf **App-Suite konfigurieren**, und klicken Sie dann auf **OK**.

24. Klicken Sie auf **App-Suite-Informationen**, geben Sie Office- **Apps für Windows 10** unter **Suite Name**, **Office-Apps für Windows 10** in **Suite Description**ein, und klicken Sie dann auf **OK**.

25. Klicken Sie auf **App**-suiteeinstellungen, wählen Sie **halbjährlich** im **Kanal aktualisieren**aus, und klicken Sie dann auf **OK**.

26. Klicken Sie auf dem Blatt **app hinzufügen** auf **Hinzufügen**.

Sie verfügen jetzt über eine Geräte Konformitätsrichtlinie zum Testen der ausgewählten apps in der **Windows 10** -Geräte Konformitätsrichtlinie und für Mitglieder der **verwalteten Windows 10-Geräte Benutzer** Gruppe. Beachten Sie, dass beim Auswählen von Office 365 als Gruppentyp zusätzliche Ressourcen erstellt werden. 
  
## <a name="next-step"></a>Nächster Schritt

Erkunden Sie zusätzliche Features und Funktionen für die [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).
  
[Registrieren von iOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
