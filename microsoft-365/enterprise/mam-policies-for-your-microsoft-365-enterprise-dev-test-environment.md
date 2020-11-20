---
title: Geräte Konformitätsrichtlinien für Ihre Microsoft 365 für Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung zum Hinzufügen von InTune-Geräte Konformitätsrichtlinien zu Ihrer Microsoft 365 for Enterprise-Testumgebung.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367095"
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

In dieser Phase erstellen Sie eine Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte. In dieser Phase wird Microsoft InTune und das [Verwaltungskonsole von Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) verwendet, um eine Gruppe hinzuzufügen und eine Konformitätsrichtlinie zu erstellen.

1. Wechseln Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com), und melden Sie sich bei Ihrem Microsoft 365 Test Lab-Abonnement mit ihrem globalen Administratorkonto an. Wählen Sie das Verwaltungskonsole **EndPoint Manager** aus. Das [Administrator Center für Endpunkt Verwaltung](https://go.microsoft.com/fwlink/?linkid=2109431) wird geöffnet.

    Wenn eine Nachricht, die Ihnen ähnlich ist, die **Geräteverwaltung noch nicht aktiviert** hat, wird die Meldung angezeigt, und wählen Sie dann InTune als MDM-Autorität aus. Die einzelnen Schritte finden Sie unter [Festlegen der Verwaltungsautorität für mobile Geräte](/mem/intune/fundamentals/mdm-authority-set).

    Der Schwerpunkt des Endpoint Manager Admin Center liegt auf der Geräteverwaltung und der APP-Verwaltung. Einen Rundgang durch dieses Admin Center finden Sie unter [Tutorial: Walkthrough InTune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. Fügen Sie in **Gruppen** eine neue **Microsoft 365** -oder **Sicherheits** Gruppe mit dem Namen **Managed Windows 10-Geräte Benutzer** mit einem **zugewiesenen** Mitgliedschafts hinzu. In den nächsten Schritten weisen Sie die Konformitätsrichtlinie dieser Gruppe zu. 

    Die einzelnen Schritte sowie Informationen zu **Microsoft 365** oder **Sicherheits** Gruppen finden Sie unter [Hinzufügen von Gruppen zum Organisieren von Benutzern und Geräten](/mem/intune/fundamentals/groups-add).

3. Erstellen Sie unter **Geräte** eine Windows 10-Konformitätsrichtlinie. Weisen Sie diese Richtlinie der **verwalteten Windows 10-Geräte Benutzer** Gruppe zu, die Sie erstellt haben.

    In Ihrer Richtlinie können Sie einfache Kennwörter blockieren, eine Firewall erfordern, die Ausführung des Antischadsoftware-Diensts von Microsoft Defender erfordern und vieles mehr. Eine Konformitätsrichtlinie umfasst normalerweise die Basiseinstellungen oder ein absolutes Minimum, das jedes Gerät aufweisen sollte.

    Informationen zu den einzelnen Schritten und zu den verfügbaren Kompatibilitätseinstellungen, die Sie konfigurieren können, finden Sie unter [use Compliance Policies to Sets Rules for Devices you manage](/mem/intune/protect/device-compliance-get-started).

Wenn Sie fertig sind, verfügen Sie über eine Geräte Kompatibilitäts Richtlinie für das Testen von Mitgliedern in der Gruppe der **verwalteten Windows 10-Geräte Benutzer** .
  
## <a name="next-step"></a>Nächster Schritt

Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Microsoft 365 for Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).
  
[Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 for Enterprise-Testumgebung](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
