---
title: Herunterladbare Bereitschaftsbewertungsüberprüfung
description: Überprüft Geräte- und Netzwerkeinstellungen, einschließlich erforderlicher Endpunkte
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581034"
---
# <a name="downloadable-readiness-assessment-checker"></a>Herunterladbare Bereitschaftsbewertungsüberprüfung

Um mit Microsoft Managed Desktop gut arbeiten zu können, müssen Geräte bestimmte Anforderungen an Hardware und Einstellungen erfüllen. Außerdem muss jedes Gerät in der Lage sein, wichtige Endpunkte zu erreichen. Laden Sie dieses Tool herunter, und führen Sie es aus, um einen HTML-Bericht zu erhalten, Ergebnisse anzeigen und dann Maßnahmen zu ergreifen. Sie müssen das Tool und die unterstützenden Dateien herunterladen und dann manuell auf jedem Gerät ausführen, das Sie bei Microsoft Managed Desktop registrieren möchten.

Für jede Prüfung berichtet das Tool eines von drei möglichen Ergebnissen:


|Ergebnis  |Bedeutung  |
|---------|---------|
|Bereit     | Es ist keine Aktion erforderlich, bevor Sie die Registrierung abschließen.        |
|Empfehlung    | Führen Sie die Schritte im Tool aus, um eine optimale Erfahrung mit der Registrierung und für Benutzer zu erhalten. Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie Ihr erstes Gerät bereitstellen.        |
|Nicht bereit | *Wenn Sie diese Probleme* nicht beheben, wird bei der Registrierung ein Fehler auftreten. Führen Sie die Schritte im Tool aus, um sie zu beheben.        |

## <a name="obtain-the-checker"></a>Abrufen der Überprüfung

Laden Sie die .zip aus https://aka.ms/mmddratoolv0 herunter.

> [!NOTE]
> Der Benutzer, der das Tool ausgeführt hat, muss über lokale Administratorrechte auf dem Gerät verfügen, auf dem es ausgeführt wird.

 Führen Sie dann das Tool aus, indem Sie die folgenden Schritte ausführen:

1. Kopieren Sie die heruntergeladene .zip auf jedes Gerät, das Sie überprüfen möchten.
2. Extrahieren Sie alle Dateien im komprimierten Download.
3. Führen Sie **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** aus.
4. Wenn die Eingabeaufforderung für die Benutzerzugriffssteuerung angezeigt wird, wählen Sie **Ja aus.** Das Tool wird im Standardbrowser ausgeführt und geöffnet.

Sie können auch das .zip an einen freigegebenen Speicherort  herunterladen und extrahieren, aufMicrosoft.MMD.DeviceReadinessAssessmentTool.exeGeräte zugreifen und es dann lokal ausführen.


## <a name="checks"></a>Prüfungen

Das herunterladbare Tool überprüft die folgenden geräte- und netzwerkbezogenen Elemente:

### <a name="hardware"></a>Hardware

Geräte müssen bestimmte Hardwareanforderungen erfüllen, um mit Microsoft Managed Desktop arbeiten zu können. Derzeit dürfen nur bestimmte [genehmigte](../service-description/device-list.md) Geräte registriert werden. 

Wenn auf Ihrem Gerät eine der Prüfungen fehlschlägt, ist es nicht mit Microsoft Managed Desktop kompatibel.

### <a name="network-endpoints"></a>Netzwerkendpunkte

Geräte können viele wichtige Endpunkte erreichen, [um](network.md) mit Microsoft Managed Desktop zu arbeiten.

Wenn das Tool ein **Nicht bereites** Ergebnis meldet, finden Sie im ausführlichen Bericht informationen, welche Endpunkte nicht erreichbar waren. Passen Sie dann Ihre Firewall oder andere Netzwerkeinstellungen an, um sicherzustellen, dass diese Endpunkte erreicht werden können.

### <a name="other-settings"></a>Weitere Einstellungen

#### <a name="enterprise-wi-fi-profiles"></a>Enterprise-WLAN-Profile

Ein **Empfehlungsergebnis** bedeutet, dass Sie einige WLAN-Profile verwenden, für die Zertifikate und Profile ordnungsgemäß funktionieren müssen. Weitere Informationen finden Sie unter [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).

#### <a name="lan-profiles"></a>LAN-Profile

Ein **Empfehlungsergebnis** bedeutet, dass Sie ÜBER LANs verfügen, für die Zertifikate und Profile ordnungsgemäß funktionieren müssen. Weitere Informationen finden Sie unter [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).

#### <a name="vpn-profiles"></a>VPN-Profile

Ein **Empfehlungsergebnis** bedeutet, dass Sie ein virtuelles privates Netzwerk (VPN) verwenden. Erstellen Sie ein VPN-Profil, das in Microsoft Intune integrierte Zertifikate bereitgestellt. Weitere Informationen finden Sie unter [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).

#### <a name="mapped-drives"></a>Zugeordnete Laufwerke

Ein **Empfehlungsergebnis** bedeutet, dass Sie über einige zugeordnete Laufwerke verfügen, die nicht empfohlen werden. Weitere Informationen finden Sie unter [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).

#### <a name="print-queues"></a>Drucken von Warteschlangen

Ein **Empfehlungsergebnis** bedeutet, dass sie über einige ausstehende Druckwarteschlangen verfügen, die nicht empfohlen werden. Eine Lösung ist die Verwendung des Clouddrucks. Weitere Informationen finden Sie unter [Prepare printing resources for Microsoft Managed Desktop](printing.md).

#### <a name="proxies"></a>Proxys

Ein **Empfehlungsergebnis** bedeutet, dass Ein Proxyserver verwendet wird. Weitere Informationen finden Sie unter [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md).

