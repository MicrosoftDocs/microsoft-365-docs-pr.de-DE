---
title: Geräte Konformitätsrichtlinien für Ihre Microsoft 365 für Enterprise-Testumgebung
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
description: Verwenden Sie diese Test Umgebungs Anleitung zum Hinzufügen von InTune-Geräte Konformitätsrichtlinien zu Ihrer Microsoft 365 for Enterprise-Testumgebung.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487412"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Geräte Konformitätsrichtlinien für Ihre Microsoft 365 für Enterprise-Testumgebung

*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*

In diesem Artikel wird beschrieben, wie Sie der Microsoft 365 für Enterprise-Testumgebung eine InTune-Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte und Microsoft 365-Apps für Enterprise hinzufügen.

Das Hinzufügen einer InTune-Geräte Konformitätsrichtlinie umfasst zwei Phasen:
- [Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Erstellen einer Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen

Wenn Sie MAM-Richtlinien nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie MAM-Richtlinien in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Er wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Phase 2: Erstellen einer Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte

Erstellen Sie in dieser Phase eine Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte.
  
1. Wechseln Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com) , und melden Sie sich bei Ihrem Microsoft 365 Test Lab-Abonnement mit ihrem globalen Administratorkonto an.
1. Öffnen Sie auf einer neuen Registerkarte Ihres Browsers das Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) .
1. Geben Sie im Suchfeld des Azure-Portals **InTune**ein, und wählen Sie dann **InTune**aus.
1. Wenn Sie im Bereich " **Microsoft InTune** " die Meldung " **Geräteverwaltung noch nicht aktiviert** " angezeigt haben, wählen Sie Sie aus. Wählen Sie im Bereich **Verwaltung mobiler Geräte** die Option **InTune-MDM-Autorität**aus, und wählen Sie dann auswählen aus. **Choose**
1. Aktualisieren Sie die Registerkarte Browser.
1. Wählen Sie im linken Navigationsbereich **Gruppen**aus.
1. Wählen Sie im Bereich **Gruppen-alle Gruppen** die Option **+ neue Gruppe**aus.
1. Wählen Sie im Bereich **Gruppe** die Option **Microsoft 365** oder **Sicherheit** für **Gruppentyp?**, geben Sie **verwaltete Windows 10-Geräte Benutzer** unter **Name**ein, wählen Sie **zugewiesen** in **Mitgliedschafts**aus, und wählen Sie dann **Erstellen**aus.
1. Wählen Sie **Microsoft InTune**aus.
1. Wählen Sie im Bereich **Microsoft InTune** in der Liste **Quick Tasks** die Option **Compliance Policy erstellen**aus.
1. Wählen Sie im Bereich **Konformitätsrichtlinien profile** die Option **Richtlinie erstellen**aus.
1. Geben Sie im Bereich **Richtlinie erstellen** unter **Name den Namen** **Windows 10**ein. Wählen Sie unter **Plattform**die Option **Windows 10 und höher**aus, wählen Sie im Bereich **Windows 10-Konformitätsrichtlinie** die Option **OK** aus, und wählen Sie dann **Erstellen**aus.
1. Wählen Sie **Konformitätsrichtlinien profile**aus, und wählen Sie dann den Richtliniennamen **Windows 10** aus.
1. Wählen Sie im Fensterbereich von **Windows 10** die Option **Zuweisungen**aus, und wählen Sie dann **einzubeziehende Gruppen**auswählen aus.
1. Wählen Sie im Bereich **einzubeziehende Gruppen auswählen** die Gruppe **verwaltete Windows 10-Geräte Benutzer** aus, und wählen Sie dann **auswählen**aus.
1. Wählen Sie **Speichern**aus, wählen Sie **Microsoft InTune-Übersicht**aus, und wählen Sie dann im linken Navigationsbereich **Client-apps** aus.
1. Wählen Sie im Bereich **Client apps** die Option **apps**aus, und wählen Sie dann **Hinzufügen**aus.
1. Wählen Sie im Bereich **app hinzufügen** die Option **App-Typ**aus, und wählen Sie dann **Windows 10** unter **Microsoft 365 Suite**aus.
1. Wählen Sie im Bereich **app hinzufügen** die Option **App Suite-Informationen**aus.
1. Geben Sie im Bereich **Informationen zur APP-Suite** **Microsoft 365 apps for Enterprise** in **Suite Name** und **Suite Description**ein, und wählen Sie dann **OK**aus.
1. Wählen Sie im Bereich **app hinzufügen** die Option **App Suite konfigurieren**aus, und wählen Sie dann **OK**aus.
1. Wählen Sie im Bereich **app hinzufügen** die Option **App Suite Settings**aus.
1. Wählen Sie für **Update Kanal** **halbjährliche Enterprise**aus, und wählen Sie dann **OK**aus.
1. Wählen Sie im Bereich **app hinzufügen** die Option **Hinzufügen**aus.

Sie verfügen nun über eine Geräte Kompatibilitäts Richtlinie zum Testen der ausgewählten apps in der **Windows 10** -Geräte Kompatibilitäts Richtlinie und für Mitglieder der **verwalteten Windows 10-Geräte Benutzer** Gruppe. Beachten Sie, dass beim Auswählen von **Microsoft 365** als Gruppentyp zusätzliche Ressourcen erstellt werden.
  
## <a name="next-step"></a>Nächster Schritt

Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Microsoft 365 for Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).
  
[Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 for Enterprise-Testumgebung](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
