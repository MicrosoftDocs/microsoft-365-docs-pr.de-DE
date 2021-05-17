---
title: Gerätekonformitätsrichtlinien für Microsoft 365 für Unternehmenstestumgebung
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
description: Verwenden Sie diese Testumgebungsanleitung, um Intune-Gerätekonformitätsrichtlinien zu Microsoft 365 Unternehmenstestumgebung hinzuzufügen.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367095"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Gerätekonformitätsrichtlinien für Microsoft 365 für Unternehmenstestumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*

In diesem Artikel wird beschrieben, wie Sie eine Intune-Gerätekonformitätsrichtlinie für Windows 10 geräte und Microsoft 365 Apps for Enterprise ihrer Microsoft 365 Unternehmenstestumgebung hinzufügen.

Das Hinzufügen einer Intune-Gerätekonformitätsrichtlinie umfasst zwei Phasen:
- [Phase 1: Build out your Microsoft 365 for Enterprise test environment](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Erstellen einer Gerätekonformitätsrichtlinie für Windows 10 Geräte](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Build out your Microsoft 365 for Enterprise test environment

Wenn Sie MAM-Richtlinien nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie MAM-Richtlinien in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen der automatisierten Lizenzierung und Gruppenmitgliedschaft erfordert keine simulierte Unternehmenstestumgebung, die ein simuliertes Intranet, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory Domain Services (AD DS)-Gesamtstruktur umfasst. Es wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Phase 2: Erstellen einer Gerätekonformitätsrichtlinie für Windows 10 Geräte

In dieser Phase erstellen Sie eine Gerätekonformitätsrichtlinie für Windows 10 Geräte. In dieser Phase werden Microsoft Intune und [das Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) verwendet, um eine Gruppe hinzuzufügen und eine Compliancerichtlinie zu erstellen.

1. Wechseln Sie zum [Microsoft 365 Admin Center,](https://admin.microsoft.com)und melden Sie sich bei Ihrem Microsoft 365 Testumgebungsabonnement mit Ihrem globalen Administratorkonto an. Wählen Sie **Endpoint Manager** Admin Center aus. Das [Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) wird geöffnet.

    Wenn eine Nachricht wie **You haven't enabled device management yet** message angezeigt wird, wählen Sie Intune als MDM-Autorität aus. Die spezifischen Schritte finden Sie unter [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).

    Das Endpoint Manager Admin Center konzentriert sich auf geräteverwaltung und App-Verwaltung. Eine Tour durch dieses Admin Center finden Sie unter [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. Fügen **Sie in** Gruppen eine neue Microsoft 365 oder Sicherheitsgruppe mit dem Namen Managed **Windows 10-Gerätebenutzer** mit dem **Zugewiesenen** Mitgliedschaftstyp hinzu.   In den nächsten Schritten weisen Sie dieser Gruppe Ihre Compliancerichtlinie zu. 

    Die spezifischen Schritte und Informationen  zu Microsoft 365  sicherheitsspezifischen Gruppen finden Sie unter Hinzufügen von Gruppen zum Organisieren [von Benutzern und Geräten.](/mem/intune/fundamentals/groups-add)

3. Erstellen **Sie unter** Geräte eine Windows 10 Compliancerichtlinie. Weisen Sie diese Richtlinie der gruppe Windows 10 **verwalteten** Geräten zu, die Sie erstellt haben.

    In Ihrer Richtlinie können Sie einfache Kennwörter blockieren, eine Firewall benötigen, den Microsoft Defender Antischalwaredienst ausführen lassen und vieles mehr. Eine Compliancerichtlinie enthält in der Regel die Basiseinstellungen oder das Mindestmaß, über das jedes Gerät verfügen sollte.

    Die spezifischen Schritte und Informationen zu den verfügbaren Kompatibilitätseinstellungen, die Sie konfigurieren können, finden Sie unter Verwenden von Compliancerichtlinien zum Festlegen von Regeln für Geräte, die [Sie verwalten.](/mem/intune/protect/device-compliance-get-started)

Wenn Sie fertig sind, verfügen Sie über eine Gerätekonformitätsrichtlinie zum Testen von Mitgliedern in der Gruppe Windows 10 **Verwaltete** Gerätebenutzer.
  
## <a name="next-step"></a>Nächster Schritt

Erkunden Sie [zusätzliche Features und](m365-enterprise-test-lab-guides.md#mobile-device-management) Funktionen für die Verwaltung mobiler Geräte in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Microsoft 365 für Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).
  
[Registrieren von iOS- und Android-Geräten in Microsoft 365 für Unternehmenstestumgebung](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
