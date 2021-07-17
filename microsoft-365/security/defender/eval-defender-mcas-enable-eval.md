---
title: Aktivieren der Evaluierungsumgebung für Microsoft Cloud App Security
description: Lernen Sie die Architektur von MCAS in Microsoft Defender für Office 365 kennen und verstehen Sie die Interaktionen zwischen den Microsoft 365 Defender Produkten.
keywords: Microsoft 365 Defender Testversion, testen Sie Microsoft 365 Defender, bewerten Sie Microsoft 365 Defender, Microsoft 365 Defender Evaluierungslabor, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458049"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a>Aktivieren der Evaluierungsumgebung für Microsoft Cloud App Security


**Gilt für:**

- Microsoft 365 Defender

Dieser Artikel ist [Schritt 2 von 2](eval-defender-mcas-overview.md) beim Einrichten der Evaluierungsumgebung für Microsoft Cloud App Security. Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-mcas-overview.md)

Dieser Artikel führt Sie durch den Prozess des Zugriffs auf das Cloud App Security-Portal und der Konfiguration der erforderlichen Integration zum Sammeln von Datenverkehrsdaten für Cloud-Apps.

Um die in Ihrer Umgebung verwendeten Cloud-Apps zu ermitteln, können Sie eine oder beide der folgenden Aktionen ausführen:

- Beginnen Sie schnell mit Cloud Discovery, indem Sie sich in Microsoft Defender für Endpunkt integrieren. Diese systemeigene Integration ermöglicht es Ihnen, sofort mit der Erfassung von Daten im Clouddatenverkehr über Ihre Windows 10 Geräte hinweg, in und außerhalb Ihres Netzwerks zu beginnen.
- Um alle Cloud-Apps zu ermitteln, auf die von allen Geräten zugegriffen wird, die mit Ihrem Netzwerk verbunden sind, stellen Sie den Cloud App Security Protokollsammler in Ihren Firewalls und anderen Proxys bereit. Dadurch werden Daten von Ihren Endpunkten gesammelt und zur Analyse an Cloud App Security gesendet. Cloud App Security kann nativ in einige Proxys von Drittanbietern integriert werden, um noch mehr Funktionen zu bieten.

Dieser Artikel enthält Anleitungen für beide Methoden.

Führen Sie die folgenden Schritte aus, um Microsoft Cloud App Security einzurichten.

![Schritte zum Aktivieren von Microsoft Microsoft Cloud App Security in der Microsoft Defender-Evaluierungsumgebung](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [Schritt 1. Verbinden zum Cloud App Security-Portal](#step-1-connect-to-the-cloud-app-security-portal)
- [Schritt 2. Integration in Microsoft Defender für Endpunkt](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [Schritt 3. Bereitstellen des Cloud App Security Protokollsammlers in Ihren Firewalls und anderen Proxys](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [Schritt 4. Anzeigen des Cloud Discovery-Dashboards, um zu sehen, welche Apps in Ihrer Organisation verwendet werden](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a>Schritt 1. Verbinden zum Cloud App Security-Portal

Informationen zum Überprüfen der Lizenzierung und zum Herstellen einer Verbindung mit dem Cloud App Security-Portal finden Sie unter [Schnellstart: Erste Schritte mit Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security). 

Wenn Sie nicht sofort eine Verbindung mit dem Portal herstellen können, müssen Sie möglicherweise die IP-Adresse zur Zulassungsliste Ihrer Firewall hinzufügen. Grundlegendes [Setup für Cloud App Security](/cloud-app-security/general-setup).

Wenn Sie weiterhin Probleme haben, überprüfen Sie die [Netzwerkanforderungen.](/cloud-app-security/network-requirements)

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>Schritt 2. Integration in Microsoft Defender für Endpunkt

Microsoft Cloud App Security kann systemintern in Microsoft Defender für Endpunkt integriert werden. Die Integration vereinfacht den Rollout von Cloud Discovery, erweitert die Cloud Discovery-Funktionen über Ihr Unternehmensnetzwerk hinaus und ermöglicht die gerätebasierte Untersuchung. Diese Integration zeigt, dass auf Cloud-Apps und -Dienste von IT-verwalteten Windows 10 Geräten zugegriffen wird. 

Wenn Sie Microsoft Defender für Endpunkt bereits eingerichtet haben, ist das Konfigurieren der Integration mit Cloud App Security ein Umschalter in Microsoft 365 Defender. Nachdem die Integration aktiviert ist, können Sie zum Cloud App Security-Portal zurückkehren und umfangreiche Daten im Cloud Discovery-Dashboard anzeigen.

Informationen zum Ausführen dieser Aufgaben finden Sie unter [Microsoft Defender für Endpunkt-Integration in Microsoft Cloud App Security.](/cloud-app-security/mde-integration) 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a>Schritt 3: Bereitstellen des Cloud App Security Protokollsammlers in Ihren Firewalls und anderen Proxys

Um die Abdeckung auf allen Geräten zu gewährleisten, die mit Ihrem Netzwerk verbunden sind, stellen Sie den Cloud App Security Protokollsammler in Ihren Firewalls und anderen Proxys bereit, um Daten von Ihren Endpunkten zu sammeln und zur Analyse an Cloud App Security zu senden. 

Wenn Sie eines der folgenden Secure Web Gateways (SWG) verwenden, bietet Cloud App Security eine nahtlose Bereitstellung und Integration:
- Zscaler
- iboss
- Corrata
- Menlo Security

Weitere Informationen zur Integration in diese Netzwerkgeräte finden Sie unter ["Einrichten von Cloud Discovery".](/cloud-app-security/set-up-cloud-discovery) 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>Schritt 4. Anzeigen des Cloud Discovery-Dashboards, um zu sehen, welche Apps in Ihrer Organisation verwendet werden

Das Cloud Discovery-Dashboard ist so konzipiert, dass Sie mehr Einblick in die Verwendung von Cloud-Apps in Ihrer Organisation erhalten. Es bietet einen Überblick darüber, welche Arten von Apps verwendet werden, welche warnungen geöffnet werden und welche Risikostufen apps in Ihrer Organisation aufweisen. 

Informationen zu den ersten Schritten mit dem Cloud Discovery-Dashboard finden Sie unter [Arbeiten mit ermittelten Apps.](/cloud-app-security/discovered-apps)

## <a name="next-steps"></a>Nächste Schritte

Schritt 3 von 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)

Kehren Sie zur Übersicht für ["Auswerten Microsoft Cloud App Security"](eval-defender-mcas-overview.md) zurück.

Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)