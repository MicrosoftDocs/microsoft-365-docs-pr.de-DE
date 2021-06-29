---
title: Behandeln von Problemen und Suchen nach Antworten auf häufig gestellte Fragen im Zusammenhang mit Microsoft Defender für Endpunkt unter iOS
description: Problembehandlung und häufig gestellte Fragen – Microsoft Defender für Endpunkt unter iOS
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, ios, Problembehandlung, häufig gestellte Fragen, Vorgehensweise
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
ms.openlocfilehash: b82b6993ce9ed5a3f0f3e6e13e8a260a185c9730
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194973"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a>Behandeln von Problemen und Suchen nach Antworten auf häufig gestellte Fragen zu Microsoft Defender für Endpunkt unter iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Dieses Thema enthält Informationen zur Problembehandlung, mit denen Sie Probleme beheben können, die bei der Verwendung von Microsoft Defender für Endpunkt unter iOS auftreten können.



> [!NOTE]
> Defender für Endpunkt unter iOS würde ein VPN verwenden, um das Webschutzfeature bereitzustellen. Dies ist kein reguläres VPN und ein lokales/selbstschleifendes VPN, das keinen Datenverkehr außerhalb des Geräts aufnimmt.

## <a name="apps-dont-work-when-vpn-is-turned-on"></a>Apps funktionieren nicht, wenn VPN aktiviert ist
Es gibt einige Apps, die nicht mehr funktionieren, wenn ein aktives VPN erkannt wird. Sie können das VPN während der Verwendung solcher Apps deaktivieren. 

Standardmäßig enthält Defender für Endpunkt unter iOS das Webschutzfeature und aktiviert es. [Webschutz](web-protection-overview.md) hilft dabei, Geräte vor Webbedrohungen zu schützen und Benutzer vor Phishingangriffen zu schützen. Defender für Endpunkt unter iOS verwendet ein VPN, um diesen Schutz bereitzustellen. Bitte beachten Sie, dass es sich um ein lokales VPN handelt und im Gegensatz zu herkömmlichem VPN kein Netzwerkdatenverkehr außerhalb des Geräts gesendet wird.

Obwohl sie standardmäßig aktiviert ist, kann es einige Fälle geben, in denen Sie VPN deaktivieren müssen. Sie möchten beispielsweise einige Apps ausführen, die nicht funktionieren, wenn ein VPN konfiguriert ist. In solchen Fällen können Sie vpn von der App auf dem Gerät deaktivieren, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie auf Ihrem iOS-Gerät die **Einstellungen** App, klicken oder tippen Sie auf **"Allgemein"** und dann auf **"VPN".**
1. Klicken oder tippen Sie auf die Schaltfläche "i" für Microsoft Defender für Endpunkt.
1. Schalten Sie **Verbinden bei Bedarf** aus, um VPN zu deaktivieren.

    > [!div class="mx-imgBorder"]
    > ![VPN config connect on demand](images/ios-vpn-config.png)

> [!NOTE]
> Webschutz ist nicht verfügbar, wenn VPN deaktiviert ist. Um Web Protection erneut zu aktivieren, öffnen Sie die Microsoft Defender für Endpunkt-App auf dem Gerät, und klicken oder tippen Sie auf **"VPN starten".**

## <a name="co-existence-with-multiple-vpn-profiles"></a>Koexistenz mit mehreren VPN-Profilen

Apple iOS unterstützt nicht, dass mehrere **geräteweite** VPNs gleichzeitig aktiv sind. Während mehrere VPN-Profile auf dem Gerät vorhanden sein können, kann jeweils nur ein VPN aktiv sein.

Microsoft Defender für Endpunkt-VPN kann gemeinsam mit anderen VPNs vorhanden sein, die als *pro App* oder *"Persönlich"* konfiguriert sind.

## <a name="battery-consumption"></a>Akkuverbrauch

In der Einstellungen App zeigt iOS nur die Akkunutzung von Apps an, die für einen bestimmten Zeitraum für den Benutzer sichtbar sind. Der Akkuverbrauch von Apps, die auf dem Bildschirm angezeigt werden, gilt nur für diese Zeit und wird von iOS basierend auf einer Vielzahl von Faktoren wie CPU- und Netzwerkauslastung berechnet. Microsoft Defender für Endpunkt verwendet ein lokales/Loop-Back-VPN im Hintergrund, um den Webdatenverkehr auf schädliche Websites oder Verbindungen zu überprüfen. Netzwerkpakete aus einer beliebigen App durchlaufen diese Überprüfung und führen dazu, dass die Akkunutzung von Microsoft Defender für Endpunkt ungenau berechnet wird. Der tatsächliche Akkuverbrauch von Microsoft Defender für Endpunkt ist viel geringer als der, der auf der Seite "Akku Einstellungen" auf dem Gerät angezeigt wird.

Der durchschnittliche Akkuverbrauch von Microsoft Defender für Endpunkt im Hintergrund pro Tag beträgt **ca. 8,81 % des gesamten Akkuverbrauchs an diesem Tag.** Diese Metrik wird von Apple basierend auf der tatsächlichen Nutzung von Microsoft Defender für Endpunkt auf Endbenutzergeräten gemeldet und kann aus den oben genannten Gründen auch auf andere Apps mit Netzwerkaktivität berücksichtigt werden.

Außerdem handelt es sich bei dem verwendeten VPN um ein lokales VPN, und im Gegensatz zu einem herkömmlichen VPN wird kein Netzwerkdatenverkehr außerhalb des Geräts gesendet.

## <a name="data-usage"></a>Datennutzung

Microsoft Defender für Endpunkt verwendet ein lokales/Loopback-VPN, um den Webdatenverkehr auf schädliche Websites oder Verbindungen zu überprüfen. Aus diesem Grund kann die Nutzung von Microsoft Defender für Endpunkt-Daten ungenau berücksichtigt werden. Wir haben auch festgestellt, dass, wenn sich das Gerät nur im Mobilfunknetz befindet, die vom Dienstanbieter gemeldete Datennutzung sehr nahe am tatsächlichen Verbrauch liegt, während Apple in der Einstellungen-App etwa 1,5x bis 2x der tatsächlich verbrauchten Daten anzeigt.

Wir haben ähnliche Beobachtungen auch mit anderen VPN-Diensten und haben dies an Apple gemeldet.

Darüber hinaus ist es wichtig, dass Microsoft Defender für Endpunkt mit unseren Back-End-Diensten auf dem neuesten Stand ist, um einen besseren Schutz zu bieten. Wir arbeiten jedoch daran, die Datennutzung durch Microsoft Defender für Endpunkt zu optimieren.

## <a name="report-unsafe-site"></a>Unsichere Website melden

Phishing-Websites imitieren vertrauenswürdige Websites, um Ihre persönlichen oder finanziellen Informationen zu erhalten. Besuchen Sie die Seite ["Feedback zum Netzwerkschutz",](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) um eine Website zu melden, bei der es sich um eine Phishing-Website handeln könnte.

## <a name="malicious-site-detected"></a>Schadsoftware-Website erkannt

Microsoft Defender für Endpunkt schützt Sie vor Phishing oder anderen webbasierten Angriffen. Wenn eine schädliche Website erkannt wird, wird die Verbindung blockiert, und eine Warnung wird an das Security Center-Portal der Organisation gesendet. Die Warnung enthält den Domänennamen der Verbindung, die Remote-IP-Adresse und die Gerätedetails.

Darüber hinaus wird eine Benachrichtigung auf dem iOS-Gerät angezeigt. Durch Tippen auf die Benachrichtigung wird der folgende Bildschirm geöffnet, auf dem der Benutzer die Details überprüfen kann.

> [!div class="mx-imgBorder"]
> ![Abbildung der Website, die als unsichere Benachrichtigung gemeldet wird](images/ios-phish-alert.png)

## <a name="data-and-privacy"></a>Daten und Datenschutz

Ausführliche Informationen zu gesammelten Daten und zum Datenschutz finden Sie unter [Datenschutzinformationen – Microsoft Defender für Endpunkt unter iOS.](ios-privacy.md)

