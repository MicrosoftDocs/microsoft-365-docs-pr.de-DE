---
title: Registrieren von iOS- und Android-Geräten in Ihrer Testumgebung für Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Verwenden Sie diese Test Lab Guide zum Registrieren von Geräten in Ihrer Microsoft 365 Test-Umgebung und Remote zu verwalten.
ms.openlocfilehash: 98696104ee8453adb7449980cf439eeb152aeea9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867696"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Registrieren von iOS- und Android-Geräten in Ihrer Testumgebung für Microsoft 365 Enterprise

Gemäß die Anweisungen in diesem Artikel müssen Sie möglicherweise zum Registrieren und Testen grundlegende Mobilgerät Management-Funktionen für iOS und Android-Geräte in Ihrer testumgebung Microsoft 365 Enterprise.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise

Wenn Sie auf einfache Weise mit den Mindestanforderungen iOS und Android-Geräte registrieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie iOS und Android-Geräte in einem simulierten Unternehmen registrieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testen der automatisiert Lizenzierung und Gruppenmitgliedschaft erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Phase 2: Registrieren Sie Ihre iOS und Android-Geräte

Verwenden Sie zunächst die Anweisungen in [Installieren und melden Sie sich die app Unternehmensportal](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) zum Anpassen von Microsoft Intune Unternehmensportal-app für Ihre testumgebung.

Im nächsten Schritt verwenden Sie die Anweisungen in [Richten Sie Ihre Unternehmensressourcen zugreifen,](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) einer iOS-Geräte zu registrieren.

Im nächsten Schritt verwenden Sie die Anweisungen in [Registrieren Ihrer Android-Gerät im Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) Android-Gerät zu registrieren.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Phase 3: Verwalten Sie Ihrer iOS und Android-Geräte Remote

Bietet Microsoft Intune remote sperren und die Kennung Funktionen zurückgesetzt. Wenn eine Person ihr Gerät verliert, können Sie das Gerät Remote sperren. Wenn eine Person ihre Kennung vergisst, können Sie es Remote zurücksetzen.
  
Um eine IOS- oder Android-Gerät remote zu sperren:

1. Melden Sie sich bei der Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit den Anmeldeinformationen Ihres Kontos globaler Administrator.
2. Klicken Sie auf **alle Dienste**, geben Sie **Intune**, und klicken Sie dann auf **Intune**.
3. Klicken Sie auf **Geräte > alle Geräte**.
4. Klicken Sie in der Liste der Geräte auf eine IOS- oder Android-Gerät, und klicken Sie dann auf die Aktion **Remote Sperren** .

    
So setzen Sie den Zugangscode remote zurück

1. Falls erforderlich, melden Sie sich bei der Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit den Anmeldeinformationen Ihres Kontos globaler Administrator.
2. Klicken Sie auf **alle Dienste**, geben Sie **Intune**, und klicken Sie dann auf **Intune**.
3. Klicken Sie auf **Geräte > alle Geräte**.
4. Aus der Liste der Geräte verwalten, klicken Sie auf eine IOS- oder Android-Gerät und wählen Sie **... Weitere**. Wählen Sie dann die **Kennung entfernen** Gerät remote-Aktion aus.

Weitere Versuche finden Sie unter [verfügbare Gerät Aktionen](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Nächster Schritt

Hier finden Sie zusätzliche [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) Features und Funktionen in Ihrer testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)
  
[MAM-Richtlinien für die Microsoft 365 Enterprise-Testumgebung](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise-Mobilität + Sicherheit (zur Abstimmung)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
