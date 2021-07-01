---
title: Konfigurieren von Microsoft Defender für Endpunkt unter iOS-Features
description: Beschreibt, wie Microsoft Defender für Endpunkt unter iOS-Features bereitgestellt wird
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, ios, konfigurieren, Features, ios
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
ms.openlocfilehash: 749e03cb9d14476245baea82c21d322d4d726aad
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230007"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>Konfigurieren von Microsoft Defender für Endpunkt unter iOS-Features

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> Defender für Endpunkt unter iOS würde ein VPN verwenden, um das Webschutzfeature bereitzustellen. Dies ist kein reguläres VPN und ein lokales/selbstschleifendes VPN, das keinen Datenverkehr außerhalb des Geräts aufnimmt.

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>Bedingter Zugriff mit Defender für Endpunkt unter iOS  
Microsoft Defender für Endpunkt unter iOS zusammen mit Microsoft Intune und Azure Active Directory ermöglicht das Erzwingen von Gerätecompliance und Richtlinien für bedingten Zugriff basierend auf der Geräterisikobewertung. Defender für Endpunkt ist eine MTD-Lösung (Mobile Threat Defense), die Sie bereitstellen können, um diese Funktion über Intune zu nutzen.

Weitere Informationen zum Einrichten des bedingten Zugriffs mit Defender für Endpunkt unter iOS finden Sie unter [Defender für Endpunkt und Intune.](/mem/intune/protect/advanced-threat-protection)

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Jailbreak-Erkennung durch Microsoft Defender für Endpunkt
Microsoft Defender für Endpunkt verfügt über die Möglichkeit, nicht verwaltete und verwaltete Geräte zu erkennen, die ohne Jailbreak sind. Wenn festgestellt wird, dass ein Gerät im Jailbreak ist, wird eine Warnung mit **hohem** Risiko an das Security Center gemeldet. Wenn der bedingte Zugriff basierend auf der Geräterisikobewertung eingerichtet wird, wird der Zugriff auf Unternehmensdaten für das Gerät blockiert.

## <a name="web-protection-and-vpn"></a>Webschutz und VPN

Standardmäßig enthält Defender für Endpunkt unter iOS das Webschutzfeature und aktiviert es. [Webschutz](web-protection-overview.md) hilft dabei, Geräte vor Webbedrohungen zu schützen und Benutzer vor Phishingangriffen zu schützen. Defender für Endpunkt unter iOS verwendet ein VPN, um diesen Schutz bereitzustellen. Bitte beachten Sie, dass es sich um ein lokales VPN handelt und im Gegensatz zu herkömmlichem VPN kein Netzwerkdatenverkehr außerhalb des Geräts gesendet wird.

Obwohl sie standardmäßig aktiviert ist, kann es einige Fälle geben, in denen Sie VPN deaktivieren müssen. Sie möchten beispielsweise einige Apps ausführen, die nicht funktionieren, wenn ein VPN konfiguriert ist. In solchen Fällen können Sie vpn von der App auf dem Gerät deaktivieren, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie auf Ihrem iOS-Gerät die **Einstellungen** App, klicken oder tippen Sie auf **"Allgemein"** und dann auf **"VPN".**
1. Klicken oder tippen Sie auf die Schaltfläche "i" für Microsoft Defender für Endpunkt.
1. Schalten Sie **Verbinden bei Bedarf** aus, um VPN zu deaktivieren.

    > [!div class="mx-imgBorder"]
    > ![VPN config connect on demand](images/ios-vpn-config.png)

> [!NOTE]
> Webschutz ist nicht verfügbar, wenn VPN deaktiviert ist. Um Web Protection erneut zu aktivieren, öffnen Sie die Microsoft Defender für Endpunkt-App auf dem Gerät, und klicken oder tippen Sie auf **"VPN starten".**

## <a name="co-existence-of-multiple-vpn-profiles"></a>Koexistenz mehrerer VPN-Profile

Apple iOS unterstützt nicht, dass mehrere geräteweite VPNs gleichzeitig aktiv sind. Während mehrere VPN-Profile auf dem Gerät vorhanden sein können, kann jeweils nur ein VPN aktiv sein.

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a>Konfigurieren des Microsoft Defender für Endpunkt-Risikosignals in der App-Schutzrichtlinie (MAM)

Microsoft Defender für Endpunkt kann so konfiguriert werden, dass Bedrohungssignale gesendet werden, die in App-Schutzrichtlinien (APP, auch als MAM bezeichnet) unter iOS/iPadOS verwendet werden. Mit dieser Funktion können Sie Microsoft Defender für Endpunkt verwenden, um den Zugriff auf Unternehmensdaten auch von nicht registrierungierten Geräten aus zu schützen.

Schritte zum Einrichten von App-Schutzrichtlinien mit Microsoft Defender für Endpunkt sind wie folgt:

1. Richten Sie die Verbindung von Ihrem Microsoft Endpoint Manager-Mandanten zu Microsoft Defender für Endpunkt ein. Wechseln Sie [im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu **Mandantenverwaltungsconnectors**  >  **und -token**  >  **Microsoft Defender für Endpunkt** (plattformübergreifend) oder **Endpunktsicherheit**  >  **Microsoft Defender für Endpunkt** (unter Setup), und aktivieren Sie die Umschaltflächen unter **App-Schutzrichtlinie Einstellungen für iOS.**
1. Wählen Sie "Speichern" aus. Es sollte angezeigt werden, dass der **Verbindungsstatus** jetzt auf **"Aktiviert"** festgelegt ist.
1. Erstellen einer App-Schutzrichtlinie: Navigieren Sie nach Abschluss des Setups des Microsoft Defender für Endpunkt-Connectors zu **den**  >  **App-Schutzrichtlinien** (unter "Richtlinie"), um eine neue Richtlinie zu erstellen oder eine vorhandene zu aktualisieren.
1. Wählen Sie die Plattform, **Apps, Datenschutz, Zugriffsanforderungseinstellungen aus,** die Ihre Organisation für Ihre Richtlinie benötigt.
1. Unter Bedingungen des Geräts für **bedingten Start** finden Sie die Einstellung  >   **"Maximale Gerätegefährdungsstufe"**. Dies muss entweder auf "Niedrig", "Mittel", "Hoch" oder "Gesichert" konfiguriert werden. Die verfügbaren Aktionen sind **"Zugriff blockieren"** oder **"Daten zurücksetzen".** Möglicherweise wird ein Informationsdialogfeld angezeigt, um sicherzustellen, dass Ihr Connector eingerichtet ist, bevor diese Einstellung wirksam wird. Wenn Ihr Connector bereits eingerichtet ist, können Sie dieses Dialogfeld ignorieren.
1. Schließen Sie die Aufgaben ab, und speichern Sie Ihre Richtlinie.

Weitere Informationen zur MAM- oder App-Schutzrichtlinie finden Sie unter [iOS-App-Schutzrichtlinieneinstellungen.](/mem/intune/apps/app-protection-policy-settings-ios)

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>Bereitstellen von Microsoft Defender für Endpunkt für MAM oder auf nicht angemeldeten Geräten

Microsoft Defender für Endpunkt unter iOS aktiviert das App Protection Policy-Szenario und ist im Apple App Store verfügbar.

Endbenutzer sollten die neueste Version der App direkt aus dem Apple App Store installieren.

## <a name="configure-compliance-policy-against-jailbroken-devices"></a>Konfigurieren der Compliancerichtlinie für Geräte mit Jailbreak

Um den Zugriff auf Unternehmensdaten auf iOS-Geräten mit Jailbreak zu schützen, empfehlen wir, dass Sie die folgende Compliancerichtlinie in Intune einrichten.

> [!NOTE]
> Die Jailbreak-Erkennung ist eine Funktion, die von Microsoft Defender für Endpunkt unter iOS bereitgestellt wird. Es wird jedoch empfohlen, diese Richtlinie als zusätzliche Schutzebene gegen Jailbreak-Szenarien einzurichten.

Führen Sie die folgenden Schritte aus, um eine Compliancerichtlinie für Geräte mit Jailbreak zu erstellen.

1. Wechseln [Sie in Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu **"Gerätecompliancerichtlinien**  ->    ->  **erstellen".** Wählen Sie "iOS/iPadOS" als Plattform aus, und klicken Sie auf **"Erstellen".**

    > [!div class="mx-imgBorder"]
    > ![Richtlinie erstellen](images/ios-jb-policy.png)

2. Geben Sie einen Namen der Richtlinie an, z. B. "Compliancerichtlinie für Jailbreak".
3. Klicken Sie auf der Seite "Complianceeinstellungen" auf den Abschnitt **"Geräteintegrität",** und klicken Sie auf das Feld **"Für** **Jailbroken** blockieren".

    > [!div class="mx-imgBorder"]
    > ![Richtlinien-Einstellungen](images/ios-jb-settings.png)

4. Wählen Sie im Abschnitt **"Aktion für Nichtkonformität"** die Aktionen gemäß Ihren Anforderungen aus, und wählen Sie **"Weiter"** aus.

    > [!div class="mx-imgBorder"]
    > ![Richtlinienaktionen](images/ios-jb-actions.png)

5. Wählen Sie im Abschnitt **"Aufgaben"** die Benutzergruppen aus, die Sie für diese Richtlinie einschließen möchten, und wählen Sie dann **"Weiter"** aus.
6. Überprüfen Sie im Abschnitt **"Überprüfen und Erstellen",** ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann **"Erstellen"** aus.

## <a name="configure-custom-indicators"></a>Konfigurieren von benutzerdefinierten Indikatoren

Mit Defender für Endpunkt unter iOS können Administratoren auch benutzerdefinierte Indikatoren auf iOS-Geräten konfigurieren. Weitere Informationen zum Konfigurieren von benutzerdefinierten Indikatoren finden Sie unter [Verwalten von Indikatoren.](/microsoft-365/security/defender-endpoint/manage-indicators)

> [!NOTE]
> Defender für Endpunkt unter iOS unterstützt das Erstellen benutzerdefinierter Indikatoren nur für IP-Adressen und URLs/Domänen.

## <a name="report-unsafe-site"></a>Unsichere Website melden

Phishing-Websites imitieren vertrauenswürdige Websites, um Ihre persönlichen oder finanziellen Informationen zu erhalten. Besuchen Sie die Seite ["Feedback zum Netzwerkschutz",](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) wenn Sie eine Website melden möchten, bei der es sich um eine Phishing-Website handeln könnte.

