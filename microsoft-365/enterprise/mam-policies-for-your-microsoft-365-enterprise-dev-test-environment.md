---
title: Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung, um InTune-Geräte Konformitätsrichtlinien zu Ihrer Microsoft 365 Enterprise-Testumgebung hinzuzufügen.
ms.openlocfilehash: b0b8bd2d76a3959bbcca749545d9a16e50491d20
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066912"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*

Mit den Anweisungen in diesem Artikel fügen Sie eine InTune-Geräte Konformitätsrichtlinie für Windows 10-Geräte und Office 365 ProPlus zu Ihrer Microsoft 365 Enterprise-Testumgebung hinzu.

![Testumgebungsanleitungen für die Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

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

3. Geben Sie auf der Registerkarte Azure Portal in Ihrem Browser **InTune** in das Suchfeld ein, und klicken Sie dann auf **InTune**.
    
4. Wenn Sie im Bereich **Microsoft InTune** sehen, dass die Meldung **Geräteverwaltung noch nicht aktiviert** ist, klicken Sie darauf. Klicken Sie im Bereich **Verwaltung von mobilen Geräten** auf **InTune MDM Authority**, und klicken Sie dann auf **auswählen**. Aktualisieren Sie die Registerkarte Browser.
    
5. Klicken Sie im linken Navigationsbereich auf **Gruppen**.
    
6. Klicken Sie im Bereich **Gruppen-alle Gruppen** auf **+ neue Gruppe**.
    
7. Wählen Sie im Bereich **Gruppe** **Office 365** oder **Sicherheit** für **Gruppentyp?**, geben Sie **verwaltete Windows 10-Geräte Benutzer** unter **Name**ein, wählen Sie in **Mitgliedschafts** **zugewiesen** aus, und klicken Sie dann auf **Erstellen**. 
    
8. Klicken Sie auf **Microsoft InTune**. Klicken Sie im Bereich **Microsoft InTune** in der Liste **schnell Aufgaben** auf **Konformitätsrichtlinie erstellen**.
    
9. Klicken Sie im Bereich **Konformitätsrichtlinien profile** auf **Richtlinie erstellen**.
    
10. Geben Sie im Bereich **Richtlinie erstellen** unter **Name den Namen** **Windows 10**ein. Wählen Sie unter **Plattform**die Option **Windows 10 und höher**aus, klicken Sie im Bereich **Compliance-Richtlinie von Windows 10** auf **OK** , und klicken Sie dann auf **Erstellen**. 
    
11. Klicken Sie auf **Konformitätsrichtlinien profile**, und klicken Sie dann auf den Richtliniennamen **Windows 10** .
    
12. Klicken Sie im Fensterbereich von **Windows 10** auf **Zuweisungen**, und klicken Sie dann auf **einzubeziehende Gruppen auswählen**.
    
13. Klicken Sie im Bereich **einzuschließende Gruppen auswählen** auf die Gruppe **verwaltete Windows 10-Geräte Benutzer** , und klicken Sie dann auf **auswählen**.
    
14. Klicken Sie auf **Speichern**, klicken Sie auf **Microsoft InTune-Übersicht**, und klicken Sie dann im linken Navigationsbereich auf **Client-apps** .
    
15. Klicken Sie im Bereich **Client apps** auf **apps**, und klicken Sie dann auf **Hinzufügen**. 

16. Wählen Sie im Bereich **app hinzufügen** die Option **App-Typ**aus, und wählen Sie dann unter **Office 365 Suite**die Option **Windows 10** aus.

17. Wählen Sie im Bereich **app hinzufügen** die Option **App Suite-Informationen**aus.
 
18. Geben Sie im Bereich **Informationen der APP-Suite** **Office 365 ProPlus** in **Suite Name** und **Suite Description**ein.
Klicken Sie auf "OK".

19. Wählen Sie im Bereich **app hinzufügen** die Option **App Suite konfigurieren**aus, und klicken Sie dann auf **OK**.

20. Wählen Sie im Bereich **app hinzufügen** die Option **App Suite Settings**aus.

21. Wählen Sie für **Update Kanal** **halbjährliche**aus, und klicken Sie dann auf **OK**.

22. Klicken Sie im Bereich **app hinzufügen** auf **Hinzufügen**.

Sie verfügen nun über eine Geräte Kompatibilitäts Richtlinie zum Testen der ausgewählten apps in der **Windows 10** -Geräte Kompatibilitäts Richtlinie und für Mitglieder der **verwalteten Windows 10-Geräte Benutzer** Gruppe. Beachten Sie, dass beim Auswählen von Office 365 als Gruppentyp zusätzliche Ressourcen erstellt werden. 
  
## <a name="next-step"></a>Nächster Schritt

Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).
  
[Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
