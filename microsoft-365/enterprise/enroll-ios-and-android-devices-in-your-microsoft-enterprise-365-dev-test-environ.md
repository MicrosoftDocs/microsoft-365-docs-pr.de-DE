---
title: Registrieren von iOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Verwenden Sie dieses Test Labor Handbuch, um Geräte in Ihrer Microsoft 365-Testumgebung zu registrieren und Remote zu verwalten.
ms.openlocfilehash: e653b3e6cafb6ee2eb492709a2d060c7b92a6904
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281247"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Registrieren von iOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung

Durch Befolgen der Anweisungen in diesem Artikel können Sie die grundlegenden Funktionen für die Verwaltung mobiler Geräte für iOS-und Android-Geräte in Ihrer Microsoft 365 Enterprise-Testumgebung registrieren und testen.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie nur iOS-und Android-Geräte mit den Mindestanforderungen auf einfache Weise registrieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie iOS-und Android-Geräte in einem simulierten Unternehmen registrieren möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist. Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und die Gruppenmitgliedschaft testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Phase 2: Registrieren der iOS-und Android-Geräte

Verwenden Sie zunächst die Anweisungen unter [Installieren und Anmelden bei der Unternehmensportal-App](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) , um die Microsoft InTune-Unternehmensportal-App für Ihre Testumgebung anzupassen.

Verwenden Sie als nächstes die Anweisungen unter [Einrichten des Zugriffs auf Ihre Unternehmensressourcen](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) , um ein IOS-Gerät einzuschreiben.

Verwenden Sie als nächstes die Anweisungen unter [Registrieren Ihres Android-Geräts in InTune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) , um ein Android-Gerät zu registrieren.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Phase 3: Remoteverwaltung von iOS-und Android-Geräten

Microsoft Intune bietet sowohl Funktionen für eine Remotesperre und das Zurücksetzen der Kennung. Wenn jemand sein Gerät verliert, können Sie das Gerät remote sperren. Wenn Ihr Kennwort von einem Benutzer vergessen wird, können Sie es Remote zurücksetzen.
  
So sperren Sie ein iOS-oder Android-Gerät Remote

1. Melden Sie sich beim Azure-Portal [https://portal.azure.com](https://portal.azure.com) unter mit den Anmeldeinformationen des globalen Administratorkontos an.
2. Klicken Sie auf **alle Dienste**, geben Sie **InTune**ein, und klicken Sie dann auf **InTune**.
3. Klicken Sie auf **Geräte _GT_ alle Geräte**.
4. Klicken Sie in der Liste der Geräte auf ein iOS-oder Android-Gerät, und klicken Sie dann auf die **Remote Sperr** Aktion.

    
So setzen Sie den Zugangscode remote zurück

1. Melden Sie sich bei Bedarf im Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit den Anmeldeinformationen des globalen Administratorkontos an.
2. Klicken Sie auf **alle Dienste**, geben Sie **InTune**ein, und klicken Sie dann auf **InTune**.
3. Klicken Sie auf **Geräte _GT_ alle Geräte**.
4. Klicken Sie in der Liste der Geräte, die Sie verwalten, auf ein iOS-oder Android-Gerät, und wählen Sie dann **... Mehr**. Wählen Sie dann die Remote Aktion "Kenncode-Gerät **Entfernen** " aus.

Weitere Tests finden Sie unter [Verfügbare Geräteaktionen](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Nächster Schritt

Erkunden Sie zusätzliche Features und Funktionen für die [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)
  
[Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
