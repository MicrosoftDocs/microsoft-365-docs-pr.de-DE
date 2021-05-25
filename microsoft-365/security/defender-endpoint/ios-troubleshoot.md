---
title: Behandeln von Problemen und Finden von Antworten auf HÄUFIG GESTELLTE Fragen im Zusammenhang mit Microsoft Defender for Endpoint unter iOS
description: Problembehandlung und Häufig gestellte Fragen – Microsoft Defender for Endpoint unter iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, troubleshoot, faq, how to
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13c0a575fd2614f58eb6a2163cda04118c2a391d
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636278"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a>Behandeln von Problemen und Finden von Antworten auf häufig gestellte Fragen zu Microsoft Defender for Endpoint unter iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Dieses Thema enthält Informationen zur Problembehandlung, mit deren Hilfe Sie Probleme beheben können, die bei der Verwendung von Microsoft Defender for Endpoint unter iOS auftreten können.



> [!NOTE]
> Defender for Endpoint unter iOS würde ein VPN verwenden, um das Web Protection-Feature zur Verfügung zu stellen. Dies ist kein normales VPN und ein lokales VPN mit selbstschleifender Schleife, das keinen Datenverkehr außerhalb des Geräts verwendet.

## <a name="apps-dont-work-when-vpn-is-turned-on"></a>Apps funktionieren nicht, wenn VPN aktiviert ist
Es gibt einige Apps, die nicht mehr funktionieren, wenn ein aktives VPN erkannt wird. Sie können das VPN während der Verwendung solcher Apps deaktivieren. 

Standardmäßig enthält und aktiviert Defender for Endpoint unter iOS das Webschutzfeature. [Webschutz trägt](web-protection-overview.md) dazu bei, Geräte vor Webbedrohungen zu schützen und Benutzer vor Phishingangriffen zu schützen. Defender for Endpoint unter iOS verwendet ein VPN, um diesen Schutz zu gewährleisten. Beachten Sie, dass es sich um ein lokales VPN handelt und im Gegensatz zu herkömmlichem VPN kein Netzwerkdatenverkehr außerhalb des Geräts gesendet wird.

Obwohl standardmäßig aktiviert, kann es einige Fälle sein, in denen Sie VPN deaktivieren müssen. Beispielsweise möchten Sie einige Apps ausführen, die nicht funktionieren, wenn ein VPN konfiguriert ist. In solchen Fällen können Sie vpn von der App auf dem Gerät deaktivieren, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie auf Ihrem **iOS-Gerät die Einstellungen** App, klicken oder tippen Sie auf **Allgemein** und dann **auf VPN.**
1. Klicken oder tippen Sie auf die Schaltfläche "i" für Microsoft Defender for Endpoint.
1. Umschalten Verbinden **Bei Bedarf, um** VPN zu deaktivieren.

    > [!div class="mx-imgBorder"]
    > ![VPN config connect on demand](images/ios-vpn-config.png)

> [!NOTE]
> Web Protection ist nicht verfügbar, wenn VPN deaktiviert ist. Öffnen Sie zum erneuten Aktivieren von Web Protection die Microsoft Defender for Endpoint-App auf dem Gerät, und klicken oder tippen **Sie auf VPN starten.**

## <a name="issues-with-multiple-vpn-profiles"></a>Probleme mit mehreren VPN-Profilen

Apple iOS unterstützt nicht mehrere geräteweite VPNs, um gleichzeitig aktiv zu sein. Auf dem Gerät können zwar mehrere VPN-Profile vorhanden sein, aber nur ein VPN kann gleichzeitig aktiv sein.


## <a name="battery-consumption"></a>Akkuverbrauch

Der Akkuverbrauch einer App wird von Apple basierend auf einer Vielzahl von Faktoren wie CPU- und Netzwerknutzung berechnet. Microsoft Defender for Endpoint verwendet ein lokales /Loop-Back-VPN im Hintergrund, um den Webdatenverkehr auf schädliche Websites oder Verbindungen zu überprüfen. Netzwerkpakete von jeder App durchgehen diese Prüfung, was dazu führt, dass der Akkuverbrauch von Microsoft Defender for Endpoint ungenau berechnet wird. Dies gibt dem Benutzer einen falschen Eindruck. Der tatsächliche Akkuverbrauch von Microsoft Defender for Endpoint ist geringer als der, der auf der Seite Battery Einstellungen auf dem Gerät angezeigt wird. Dies basiert auf durchgeführten Tests, die mit der Microsoft Defender for Endpoint-App durchgeführt wurden, um den Akkuverbrauch zu verstehen.

Auch das verwendete VPN ist ein lokales VPN und im Gegensatz zu einem herkömmlichen VPN wird der Netzwerkdatenverkehr nicht außerhalb des Geräts gesendet.

## <a name="data-usage"></a>Datenverwendung

Microsoft Defender for Endpoint verwendet ein lokales /loopback-VPN, um den Webdatenverkehr auf schädliche Websites oder Verbindungen zu überprüfen. Aus diesem Grund macht Apple die Datenverwendung für Microsoft Defender for Endpoint ungenau. Die tatsächliche Datenverwendung durch Microsoft Defender for Endpoint ist nicht signifikant und viel geringer als die Datenverwendungs-Einstellungen auf dem Gerät.

## <a name="report-unsafe-site"></a>Unsichere Website melden

Phishingwebsites geben sich als vertrauenswürdige Websites aus, um Ihre persönlichen oder finanziellen Informationen zu erhalten. Besuchen Sie [die Seite Feedback zum Netzwerkschutz](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) bereitstellen, um eine Website zu melden, bei der es sich um eine Phishingwebsite handelt.

## <a name="malicious-site-detected"></a>Schädliche Website erkannt

Microsoft Defender for Endpoint schützt Sie vor Phishing oder anderen webbasierten Angriffen. Wenn eine schädliche Website erkannt wird, wird die Verbindung blockiert und eine Warnung an das Security Center-Portal der Organisation gesendet. Die Warnung enthält den Domänennamen der Verbindung, die Remote-IP-Adresse und die Gerätedetails.

Darüber hinaus wird auf dem iOS-Gerät eine Benachrichtigung angezeigt. Durch Tippen auf die Benachrichtigung wird der folgende Bildschirm geöffnet, damit der Benutzer die Details überprüfen kann.

> [!div class="mx-imgBorder"]
> ![Abbildung der Website, die als unsichere Benachrichtigung gemeldet wurde](images/ios-phish-alert.png)

## <a name="data-and-privacy"></a>Daten und Datenschutz

Weitere Informationen zu erfassten Daten und zum Datenschutz finden Sie unter [Datenschutzinformationen – Microsoft Defender for Endpoint unter iOS](ios-privacy.md).

