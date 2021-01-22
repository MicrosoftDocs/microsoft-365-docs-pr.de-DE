---
title: Herunterladbare Überprüfung der Bereitschaftsbewertung
description: Überprüft Geräte- und Netzwerkeinstellungen, einschließlich der erforderlichen Endpunkte
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921971"
---
# <a name="downloadable-readiness-assessment-checker"></a>Herunterladbare Überprüfung der Bereitschaftsbewertung

Für eine gute Zusammenarbeit mit Microsoft Managed Desktop müssen Geräte bestimmte Hardware- und Einstellungsanforderungen erfüllen. Außerdem muss jedes Gerät in der Lage sein, wichtige Endpunkte zu erreichen. Laden Sie dieses Tool herunter, und führen Sie es aus, um einen HTML-Bericht zu erhalten, Ergebnisse anzeigen und dann Maßnahmen zu ergreifen. Sie müssen das Tool und die unterstützenden Dateien herunterladen und es dann manuell auf jedem Gerät ausführen, das Sie bei Microsoft Managed Desktop registrieren möchten.

Für jede Prüfung gibt das Tool eines von drei möglichen Ergebnissen aus:


|Ergebnis  |Bedeutung  |
|---------|---------|
|Bereit     | Es ist keine Aktion erforderlich, bevor Sie die Registrierung abschließen.        |
|Empfehlung    | Führen Sie die Schritte im Tool aus, um die beste Erfahrung mit der Registrierung und für Benutzer zu bieten. Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie Ihr erstes Gerät bereitstellen.        |
|Nicht bereit | *Die Registrierung wird fehlschlagen,* wenn Sie diese Probleme nicht beheben. Führen Sie die Schritte im Tool aus, um sie zu beheben.        |

## <a name="obtain-the-checker"></a>Abrufen der Prüfung

Laden Sie die ZIP-Datei von https://aka.ms/mmddratoolv0 herunter.

> [!NOTE]
> Der Benutzer, der das Tool ausgeführt, muss über lokale Administratorrechte auf dem Gerät verfügen, auf dem es ausgeführt wird.

 Führen Sie dann das Tool aus, indem Sie die folgenden Schritte ausführen:

1. Kopieren Sie die heruntergeladene ZIP-Datei auf jedes Gerät, das Sie überprüfen möchten.
2. Extrahieren Sie alle Dateien im komprimierten Download.
3. Führen Sie **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** aus.
4. Wenn die Eingabeaufforderung für die Benutzerzugriffssteuerung angezeigt wird, wählen Sie **"Ja" aus.** Das Tool wird ausgeführt und öffnet einen Bericht im Standardbrowser.

Sie können das ZIP-Archiv auch herunterladen und  an einen freigegebenen Speicherort extrahieren, aufMicrosoft.MMD.DeviceReadinessAssessmentTool.exeGeräte zugreifen und es dann lokal ausführen.


## <a name="checks"></a>Prüfungen

Das herunterladbare Tool überprüft diese geräte- und netzwerkbezogenen Elemente:

### <a name="hardware"></a>Hardware

Geräte müssen bestimmte Hardwareanforderungen erfüllen, um mit Microsoft Managed Desktop arbeiten zu können. Derzeit dürfen nur bestimmte [genehmigte](../service-description/device-list.md) Geräte registriert werden. 

Wenn auf Ihrem Gerät eine der Überprüfungen fehlschlägt, ist es nicht mit Microsoft Managed Desktop kompatibel.

### <a name="network-endpoints"></a>Netzwerkendpunkte

Geräte können viele wichtige Endpunkte [erreichen,](network.md) um mit Microsoft Managed Desktop zu arbeiten.

Wenn das Tool ein Ergebnis meldet, das **nicht** bereit ist, sehen Sie sich den detaillierten Bericht an, um herauszufinden, welche Endpunkte nicht erreichbar waren. Passen Sie dann Ihre Firewall oder andere Netzwerkeinstellungen an, um sicherzustellen, dass diese Endpunkte erreicht werden können.

### <a name="other-settings"></a>Weitere Einstellungen

#### <a name="enterprise-wi-fi-profiles"></a>Unternehmens-WLAN-Profile

Ein **Empfehlungsergebnis** bedeutet, dass Sie einige WLAN-Profile verwenden, die Zertifikate und Profile benötigen, damit sie ordnungsgemäß funktionieren. Weitere Informationen finden Sie unter [Bereitstellen von Zertifikaten und WLAN/VPN-Profil.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)

#### <a name="lan-profiles"></a>LAN-Profile

Ein **Empfehlungsergebnis** bedeutet, dass Sie ÜBER LANs verfügen, die Zertifikate und Profile benötigen, um ordnungsgemäß zu funktionieren. Weitere Informationen finden Sie unter [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md).

#### <a name="vpn-profiles"></a>VPN-Profile

Ein **Empfehlungsergebnis** bedeutet, dass Sie ein virtuelles privates Netzwerk (VPN) verwenden. Erstellen Sie ein VPN-Profil, das in Microsoft Intune integrierte Zertifikate bereitgestellt. Weitere Informationen finden Sie unter [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md).

#### <a name="mapped-drives"></a>Zugeordnete Laufwerke

Ein **Empfehlungsergebnis** bedeutet, dass Sie über einige zugeordnete Laufwerke verfügen, die nicht empfohlen werden. Weitere Informationen finden Sie unter [Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop](mapped-drives.md).

#### <a name="print-queues"></a>Druckwarteschlangen

Ein **Empfehlungsergebnis** bedeutet, dass sie über einige ausstehende Druckwarteschlangen verfügen, die nicht empfohlen werden. Eine Lösung besteht in der Verwendung des Clouddrucks. Weitere Informationen finden Sie unter [Vorbereiten der Druckressourcen für Microsoft Managed Desktop](printing.md).

#### <a name="proxies"></a>Proxys

Ein **Empfehlungsergebnis** bedeutet, dass Sie einen Proxyserver verwenden. Weitere Informationen finden Sie unter [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md).

