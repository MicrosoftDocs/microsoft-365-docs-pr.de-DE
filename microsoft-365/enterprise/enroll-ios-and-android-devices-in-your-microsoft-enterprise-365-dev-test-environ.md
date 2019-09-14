---
title: Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Verwenden Sie diese Test Umgebungs Anleitung, um Geräte in Ihrer Microsoft 365-Testumgebung zu registrieren und Remote zu verwalten.
ms.openlocfilehash: 0dde7acd10ad78327adb4862346639e05a276b4e
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981996"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie die Anweisungen in diesem Artikel befolgen, können Sie die grundlegenden Funktionen der mobilen Geräteverwaltung für IOS-und Android-Geräte in Ihrer Microsoft 365 Enterprise-Testumgebung registrieren und testen.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen der Microsoft 365 Enterprise-Testumgebung

Wenn Sie IOS-und Android-Geräte nur auf einfache Weise mit den Mindestanforderungen registrieren möchten, befolgen Sie die Anweisungen in [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie IOS-und Android-Geräte in einem simulierten Unternehmen registrieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen der automatischen Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Phase 2: Registrieren von IOS-und Android-Geräten

Verwenden Sie zunächst die Anweisungen unter [Install, und melden Sie sich bei der Unternehmensportal-App](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) an, um die Microsoft InTune-Unternehmensportal-App für Ihre Testumgebung anzupassen.

Verwenden Sie als nächstes die Anweisungen unter [Einrichten des Zugriffs auf Ihre Unternehmensressourcen](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) , um ein IOS-Gerät zu registrieren.

Verwenden Sie als nächstes die Anweisungen unter [Registrieren Ihres Android-Geräts in InTune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) , um ein Android-Gerät zu registrieren.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Phase 3: Remoteverwaltung von IOS-und Android-Geräten

Microsoft Intune bietet sowohl Funktionen für eine Remotesperre und das Zurücksetzen der Kennung. Wenn jemand sein Gerät verliert, können Sie das Gerät remote sperren. Wenn jemand Ihren Code vergisst, können Sie ihn Remote zurücksetzen.
  
So sperren Sie ein IOS-oder Android-Gerät Remote:

1. Melden Sie sich beim Azure-Portal [https://portal.azure.com](https://portal.azure.com) unter mit den Anmeldeinformationen Ihres globalen Administratorkontos an.
2. Klicken Sie auf **alle Dienste**, geben Sie **InTune**ein, und klicken Sie dann auf **InTune**.
3. Klicken Sie auf **Geräte #a0 alle Geräte**.
4. Klicken Sie in der Liste der Geräte auf ein IOS-oder Android-Gerät, und klicken Sie dann auf die Aktion **Remote Sperre** .

    
So setzen Sie den Zugangscode remote zurück

1. Melden Sie sich bei Bedarf im Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit den Anmeldeinformationen Ihres globalen Administratorkontos an.
2. Klicken Sie auf **alle Dienste**, geben Sie **InTune**ein, und klicken Sie dann auf **InTune**.
3. Klicken Sie auf **Geräte #a0 alle Geräte**.
4. Klicken Sie in der Liste der Geräte, die Sie verwalten, auf ein IOS-oder Android-Gerät, und wählen Sie **... Mehr**. Klicken Sie dann auf die Remote Aktion Kennwort-Gerät **Entfernen** .

Weitere Experimente finden Sie unter [Verfügbare Geräteaktionen](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Nächster Schritt

Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)
  
[Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

