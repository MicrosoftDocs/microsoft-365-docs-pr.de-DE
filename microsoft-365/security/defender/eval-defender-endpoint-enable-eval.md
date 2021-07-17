---
title: Aktivieren der Microsoft Defender für Endpunkt-Auswertung, Aktivieren der Auswertung für MDE
description: Aktivieren Sie Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung, einschließlich der Überprüfung des Lizenzstatus und des Onboardings von enpoints
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458097"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a>Aktivieren der Evaluierungsumgebung von Microsoft Defender für Endpunkt


Dieser Artikel führt Sie durch die Schritte zum Einrichten der Evaluierungsumgebung für Microsoft Defender für Endpunkt unter Verwendung von Produktionsgeräten. 


>[!TIP]
>Microsoft Defender für Endpunkt enthält auch ein Produktbewertungslabor, in dem Sie vorkonfigurierte Geräte hinzufügen und Simulationen ausführen können, um die Funktionen der Plattform zu bewerten. Die Übung bietet eine vereinfachte Einrichtungsoberfläche, die ihnen dabei helfen kann, den Nutzen von Microsoft Defender für Enpdoint schnell zu demonstrieren, einschließlich Anleitungen für viele Features wie erweiterte Suche und Bedrohungsanalyse. Weitere Informationen finden Sie unter ["Auswerten von Funktionen".](/defender-endpoint/evaluation-lab.md) <br> Der Hauptunterschied zwischen den Anleitungen in diesem Artikel und dem Evaluierungslabor besteht in der Evaluierungsumgebung, in der Produktionsgeräte verwendet werden, während das Evaluierungslabor Nicht-Produktionsgeräte verwendet. 

Führen Sie die folgenden Schritte aus, um die Auswertung für Microsoft Defender für Endpunkt zu aktivieren.

![Schritte zum Aktivieren von Microsoft Defender für Endpunkt in der Microsoft Defender-Evaluierungsumgebung](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [Schritt 1. Überprüfen des Lizenzstatus](#step-1-check-license-state)
- [Schritt 2. Integrieren von Endpunkten](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a>Schritt 1. Überprüfen des Lizenzstatus

Zunächst müssen Sie den Lizenzstatus überprüfen, um sicherzustellen, dass er ordnungsgemäß bereitgestellt wurde. Sie können dies über das Admin Center oder über das **Microsoft Azure-Portal** tun.


1. Um Ihre Lizenzen anzuzeigen, wechseln Sie zum **Microsoft Azure-Portal,** und navigieren Sie zum [Lizenzabschnitt Microsoft Azure Portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)

   ![Abbildung der Azure-Lizenzierungsseite](../../media/defender/atp-licensing-azure-portal.png)

1. Navigieren Sie alternativ im Admin Center zu **Abrechnungsabonnements.**  >  

    Auf dem Bildschirm werden alle bereitgestellten Lizenzen und deren aktueller **Status angezeigt.**

    ![Abbildung der Abrechnungslizenzen](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Schritt 2. Integrieren von Endpunkten mithilfe der unterstützten Verwaltungstools

Nachdem Sie überprüft haben, ob der Lizenzstatus ordnungsgemäß bereitgestellt wurde, können Sie mit dem Onboarding von Geräten in den Dienst beginnen. 

Für die Bewertung von Microsoft Defender für Endpunkt empfehlen wir, ein paar Windows 10 Geräte auszuwählen, auf denen die Bewertung durchgeführt werden soll. 

Das Thema ["Planbereitstellung"](../defender-endpoint/deployment-strategy.md) beschreibt die allgemeinen Schritte, die Sie zum Bereitstellen von Defender für Endpunkt ausführen müssen.  

Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Onboardingprozess zu erhalten und mehr über die verfügbaren Tools und Methoden zu erfahren.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a>Onboarding-Tooloptionen

In der folgenden Tabelle sind die verfügbaren Tools aufgeführt, die auf dem Endpunkt basieren, den Sie integrieren müssen.

Endpunkt | Tooloptionen
:---|:---
**Windows** | [Lokales Skript (bis zu 10 Geräte),](../defender-endpoint/configure-endpoints-script.md) [Gruppenrichtlinie,](../defender-endpoint/configure-endpoints-gp.md) [Microsoft Endpoint Manager/Mobile Device Manager,](../defender-endpoint/configure-endpoints-mdm.md) [Microsoft Endpoint Configuration Manager,](../defender-endpoint/configure-endpoints-sccm.md) [VDI-Skripts,](../defender-endpoint/configure-endpoints-vdi.md) [Integration in Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)
**macOS** | [Lokale Skripts,](../defender-endpoint/mac-install-manually.md) [Microsoft Endpoint Manager,](../defender-endpoint/mac-install-with-intune.md) [JAMF-Pro,](../defender-endpoint/mac-install-with-jamf.md) [Verwaltung mobiler Geräte](../defender-endpoint/mac-install-with-other-mdm.md)
**Linux Server** | [Lokales Skript,](../defender-endpoint/linux-install-manually.md)  [Überzeichen,](../defender-endpoint/linux-install-with-puppet.md)  [Ansible](../defender-endpoint/linux-install-with-ansible.md)
**iOS** | [App-basiert](../defender-endpoint/ios-install.md)
**Android** | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md)



## <a name="next-step"></a>Nächster Schritt
[Einrichten des Pilotprojekts für Microsoft Defender für Endpunkt](eval-defender-endpoint-pilot.md)
 
Kehren Sie zur Übersicht für ["Auswerten von Microsoft Defender für Endpunkt"](eval-defender-endpoint-overview.md) zurück.

Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)