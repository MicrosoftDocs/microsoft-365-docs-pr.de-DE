---
title: Pilotbewertung von Defender für Endpunkt
description: Aktivieren Sie Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung.
keywords: Microsoft 365 Defender Testversion, testen Sie Microsoft 365 Defender, bewerten Sie Microsoft 365 Defender, Microsoft 365 Defender Evaluierungslabor, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458190"
---
# <a name="pilot-mde-evaluation"></a>MDE-Pilotbewertung

>[!NOTE]
>Um Sie durch eine typische Bereitstellung zu führen, wird in diesem Szenario nur die Verwendung von Microsoft Endpoint Configuration Manager behandelt. Defender für Endpunkt unterstützt die Verwendung anderer Onboarding-Tools, behandelt diese Szenarien jedoch nicht im Bereitstellungshandbuch. Weitere Informationen finden Sie unter [Onboarding von Geräten in Microsoft Defender für Endpunkt.](onboard-configure.md)

## <a name="step-1-check-license-state"></a>Schritt 1. Überprüfen des Lizenzstatus

Die Überprüfung auf den Lizenzstatus und die ordnungsgemäße Bereitstellung kann über das Admin Center oder über das **Microsoft Azure-Portal** erfolgen.

1. Um Ihre Lizenzen anzuzeigen, wechseln Sie zum **Microsoft Azure-Portal,** und navigieren Sie zum [Lizenzabschnitt Microsoft Azure Portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)

   ![Abbildung der Azure-Lizenzierungsseite](images/atp-licensing-azure-portal.png)

1. Navigieren Sie alternativ im Admin Center zu **Abrechnungsabonnements.**  >  

    Auf dem Bildschirm werden alle bereitgestellten Lizenzen und deren aktueller **Status angezeigt.**

    ![Abbildung der Abrechnungslizenzen](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Schritt 2. Integrieren von Endpunkten mithilfe der unterstützten Verwaltungstools

Das Thema ["Planbereitstellung"](deployment-strategy.md) beschreibt die allgemeinen Schritte, die Sie zum Bereitstellen von Defender für Endpunkt ausführen müssen.  

Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Onboardingprozess zu erhalten und mehr über die verfügbaren Tools und Methoden zu erfahren.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

Nachdem Sie Ihre Architektur identifiziert haben, müssen Sie entscheiden, welche Bereitstellungsmethode verwendet werden soll. Das von Ihnen verwendete Bereitstellungstool beeinflusst, wie Sie Endpunkte in den Dienst integrieren.

### <a name="onboarding-tool-options"></a>Onboarding-Tooloptionen

In der folgenden Tabelle sind die verfügbaren Tools aufgeführt, die auf dem Endpunkt basieren, den Sie integrieren müssen.

| Endpunkt     | Tooloptionen                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokales Skript (bis zu 10 Geräte)](../defender-endpoint/configure-endpoints-script.md) <br> [Gruppenrichtlinie](../defender-endpoint/configure-endpoints-gp.md) <br> [Microsoft Endpoint Manager/Mobile Device Manager](../defender-endpoint/configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md) <br> [VDI-Skripts](../defender-endpoint/configure-endpoints-vdi.md) <br> [Integration in Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| **macOS**    | [Lokale Skripts](../defender-endpoint/mac-install-manually.md) <br> [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md) <br> [JAMF-Pro](../defender-endpoint/mac-install-with-jamf.md) <br> [Verwaltung mobiler Geräte - Mobile Device Management](../defender-endpoint/mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokales Skript](../defender-endpoint/linux-install-manually.md) <br> [Puppe](../defender-endpoint/linux-install-with-puppet.md) <br> [Ansible](../defender-endpoint/linux-install-with-ansible.md)|
| **iOS**      | [App-basiert](../defender-endpoint/ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md)               |
