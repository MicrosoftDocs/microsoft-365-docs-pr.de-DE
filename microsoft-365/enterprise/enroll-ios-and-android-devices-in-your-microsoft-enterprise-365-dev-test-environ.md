---
title: Registrieren von iOS-/iPadOS- und Android-Geräten in Microsoft 365 Unternehmenstestumgebung
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
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Verwenden Sie diese Testumgebungsanleitung, um Geräte in Ihrer Microsoft 365 zu registrieren und remote zu verwalten.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367083"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Registrieren von iOS- und Android-Geräten in Microsoft 365 für Unternehmenstestumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*

In diesem Artikel wird beschrieben, wie Sie grundlegende Verwaltungsfunktionen für mobile Geräte für iOS/iPadOS- und Android-Geräte in Ihrer Microsoft 365 Unternehmenstestumgebung registrieren und testen.

Die Registrierung von iOS/iPadOS- und Android-Geräten in Ihrer Testumgebung umfasst drei Phasen:
- [Phase 1: Build out your Microsoft 365 for Enterprise test environment](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Registrieren Ihrer iOS/iPadOS- und Android-Geräte](#phase-2-enroll-your-ios-and-android-devices)
- [Phase 3: Remoteverwaltung Ihrer iOS/iPadOS- und Android-Geräte](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Build out your Microsoft 365 for Enterprise test environment

Wenn Sie iOS/iPadOS- und Android-Geräte auf einfache Weise mit den Mindestanforderungen registrieren möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie iOS/iPadOS- und Android-Geräte in einem simulierten Unternehmen registrieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen der automatisierten Lizenzierung und Gruppenmitgliedschaft erfordert keine simulierte Unternehmenstestumgebung, die ein simuliertes Intranet, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory Domain Services (AD DS)-Gesamtstruktur umfasst. Es wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Phase 2: Registrieren Ihrer iOS- und Android-Geräte

Wenn Sie eine Mobile Device Management (MDM)-Lösung zum Verwalten Ihrer Geräte in Betracht ziehen, können Sie Microsoft Intune. Bei der Arbeit mit einem beliebigen MDM-Anbieter, einschließlich Intune, werden Geräte "registriert". Bei der Registrierung erhalten sie die features und einstellungen, die Sie konfigurieren. 

In Intune gibt es mehrere Möglichkeiten, Ihre iOS/iPadOS- und Android-Geräte zu registrieren. Sie können die Registrierungsoption auswählen, die für Ihre Organisation am besten funktioniert. Weitere Informationen und Anleitungen finden Sie in den folgenden Artikeln:

- [Bereitstellungshandbuch: Registrieren von iOS- und iPadOS-Geräten in Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Bereitstellungshandbuch: Registrieren von Android-Geräten in Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Wenn Sie bereit sind, Intune für die Geräteverwaltung zu verwenden, und einige Anleitungen benötigen, können die folgenden Informationen hilfreich sein:

- [Übersicht über die Geräteverwaltung](/mem/intune/fundamentals/what-is-device-management)
- [Lernprogramm: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Bereitstellungshandbuch: Einrichten oder Verschieben zu Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Phase 3: Remoteverwaltung Ihrer iOS- und Android-Geräte

Microsoft Intune bietet die Funktion zum Zurücksetzen von Remotesperren und Kennungen. Wenn jemand sein Gerät verliert, können Sie das Gerät remote sperren. Wenn jemand seine Kennung vergisst, können Sie ihn remote zurücksetzen.

- Informationen zum Remotesperren eines iOS/iPadOS- oder Android-Geräts finden Sie unter [Remote lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).
- Informationen zum Remote zurücksetzen der Kennung finden Sie unter [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).

Weitere Aufgaben, die Sie remote ausführen können, finden Sie unter [Verfügbare Geräteaktionen](/mem/intune/remote-actions/device-management#available-device-actions).
    
## <a name="next-step"></a>Nächster Schritt

Erkunden Sie [zusätzliche Features und](m365-enterprise-test-lab-guides.md#mobile-device-management) Funktionen für die Verwaltung mobiler Geräte in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)
  
[Gerätekonformitätsrichtlinien für Microsoft 365 für Unternehmenstestumgebung](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)
