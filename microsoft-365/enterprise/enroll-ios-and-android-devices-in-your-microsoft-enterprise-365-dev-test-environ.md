---
title: Registrieren von IOS/iPads und Android-Geräten in Ihrer Microsoft 365 for Enterprise-Testumgebung
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
description: Verwenden Sie diese Test Umgebungs Anleitung, um Geräte in Ihrer Microsoft 365-Testumgebung zu registrieren und Remote zu verwalten.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367083"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 for Enterprise-Testumgebung

*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*

In diesem Artikel wird beschrieben, wie Sie grundlegende Funktionen für die Verwaltung mobiler Geräte für IOS/iPad und Android-Geräte in Ihrer Microsoft 365 for Enterprise-Testumgebung registrieren und testen.

Das Registrieren von IOS/iPads und Android-Geräten in Ihrer Testumgebung umfasst drei Phasen:
- [Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Registrieren Ihrer IOS/iPad-und Android-Geräte](#phase-2-enroll-your-ios-and-android-devices)
- [Phase 3: Remoteverwaltung Ihrer IOS/iPad-und Android-Geräte](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen

Wenn Sie IOS/iPad und Android-Geräte auf einfache Weise mit den Mindestanforderungen registrieren möchten, befolgen Sie die Anweisungen in [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie IOS/iPads und Android-Geräte in einem simulierten Unternehmen registrieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Er wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und Sie können damit in einer Umgebung experimentieren, die eine typische Organisation darstellt.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Phase 2: Registrieren von IOS-und Android-Geräten

Wenn Sie eine MDM-Lösung (Mobile Device Management) zum Verwalten Ihrer Geräte erwägen, können Sie Microsoft InTune verwenden. Bei der Arbeit mit einem MDM-Anbieter, einschließlich InTune, werden Geräte "registriert". Bei der Registrierung erhalten Sie die von Ihnen konfigurierten Features und Einstellungen. 

In InTune gibt es einige Möglichkeiten, um Ihre IOS/iPads und Android-Geräte zu registrieren. Sie können die Registrierungsoption auswählen, die für Ihre Organisation am besten geeignet ist. Weitere Informationen und Anleitungen finden Sie in den folgenden Artikeln:

- [Bereitstellungshandbuch: Registrieren von IOS-und iPad-Geräten in Microsoft InTune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Bereitstellungshandbuch: Registrieren von Android-Geräten in Microsoft InTune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Wenn Sie InTune für die Geräteverwaltung verwenden möchten und einige Anleitungen wünschen, können Ihnen die folgenden Informationen helfen:

- [Geräteverwaltung (Übersicht)](/mem/intune/fundamentals/what-is-device-management)
- [Lernprogramm: Exemplarische Vorgehensweise InTune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Bereitstellungshandbuch: Einrichten oder Migrieren zu Microsoft InTune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Phase 3: Remoteverwaltung von IOS-und Android-Geräten

Microsoft InTune bietet Funktionen für das Zurücksetzen von Remote Sperren und-Codes. Wenn ein Benutzer Ihr Gerät verliert, können Sie das Gerät Remote Sperren. Wenn jemand Ihren Code vergisst, können Sie ihn Remote zurücksetzen.

- Informationen zum Remote Sperren eines IOS/iPad oder Android-Geräts finden Sie unter [Remote Sperr Geräte mit InTune](/mem/intune/remote-actions/device-remote-lock).
- Informationen zum Remote-Zurücksetzen des Codes finden Sie unter [Zurücksetzen oder Entfernen eines Gerätecodes in InTune](/mem/intune/remote-actions/device-passcode-reset).

Weitere Aufgaben, die Sie Remote ausführen können, finden Sie unter [Verfügbare Geräteaktionen](/mem/intune/remote-actions/device-management#available-device-actions).
    
## <a name="next-step"></a>Nächster Schritt

Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)
  
[Geräte Konformitätsrichtlinien für Ihre Microsoft 365 für Enterprise-Testumgebung](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)
