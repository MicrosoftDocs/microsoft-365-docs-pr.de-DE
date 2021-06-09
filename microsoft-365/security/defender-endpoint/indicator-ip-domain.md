---
title: Erstellen von Indikatoren für IPs und URLs/Domänen
ms.reviewer: ''
description: Erstellen Von Indikatoren für IP-Adressen und URLs/Domänen, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.
keywords: IP, URL, Domäne, verwalten, zulässig, blockiert, blockieren, sauber, bösartig, Dateihash, IP-Adresse, URLs, Domäne
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7dc11fe709a6d04b6309706df90f0ebbc177e25
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841066"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>Erstellen von Indikatoren für IPs und URLs/Domänen 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


Defender für Endpunkt kann blockieren, was Microsoft als bösartige IPs/URLs angibt, über Windows Defender SmartScreen für Microsoft-Browser und über Netzwerkschutz für Nicht-Microsoft-Browser oder Anrufe außerhalb eines Browsers.

Der dafür festgelegte Datensatz für die Bedrohungserkennung wurde von Microsoft verwaltet.

Durch das Erstellen von Indikatoren für IPs und URLs oder Domänen können Sie jetzt IPs, URLs oder Domänen basierend auf Ihrer eigenen Bedrohungserkennung zulassen oder blockieren. Sie können dies über die Einstellungsseite oder nach Computergruppen tun, wenn Sie bestimmte Gruppen als mehr oder weniger gefährdet betrachten als andere.

> [!NOTE]
> Die CiDR-Notation (Classless Inter-Domain Routing) für IP-Adressen wird nicht unterstützt. 

### <a name="before-you-begin"></a>Bevor Sie beginnen
Es ist wichtig, die folgenden Voraussetzungen zu verstehen, bevor Sie Indikatoren für IPS, URLs oder Domänen erstellen:
- Die URL/IP-Zulassung und -Blockierung basiert darauf, dass der Netzwerkschutz der Defender für Endpunktkomponente im Blockierungsmodus aktiviert wird. Weitere Informationen zu Netzwerkschutz und Konfigurationsanweisungen finden Sie unter Aktivieren des [Netzwerkschutzes.](enable-network-protection.md)
- Die Antischadsoftware-Clientversion muss 4.18.1906.x oder höher sein. 
- Unterstützt auf Computern mit Windows 10, Version 1709 oder höher. 
- Stellen Sie sicher, dass **benutzerdefinierte Netzwerkindikatoren** in **Microsoft Defender Security Center > Einstellungen > Erweiterten Features** aktiviert sind. Weitere Informationen finden Sie unter ["Erweiterte Features".](advanced-features.md)
- Informationen zur Unterstützung von Indikatoren unter iOS finden Sie unter [Konfigurieren benutzerdefinierter Indikatoren.](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)


> [!IMPORTANT]
> Der Indikatorliste können nur externe IPs hinzugefügt werden. Indikatoren können nicht für interne IPs erstellt werden.
> Für Webschutzszenarien empfehlen wir die Verwendung der integrierten Funktionen in Microsoft Edge. Microsoft Edge verwendet Network [Protection,](network-protection.md) um Netzwerkdatenverkehr zu überprüfen, und lässt Blöcke für TCP, HTTP und HTTPS (TLS) zu. Wenn es widersprüchliche URL-Indikatorrichtlinien gibt, wird der längere Pfad angewendet. Beispielsweise hat die URL-Indikatorrichtlinie `https:\\support.microsoft.com/en-us/office` Vorrang vor der URL-Indikatorrichtlinie. `https:\\support.microsoft.com`

> [!NOTE]
> Für alle anderen Prozesse nutzen Webschutzszenarien Den Netzwerkschutz zur Überprüfung und Durchsetzung: 
> - IP wird für alle drei Protokolle unterstützt.
> - Es werden nur einzelne IP-Adressen unterstützt (keine CIDR-Blöcke oder IP-Bereiche)
> - Verschlüsselte URLs (vollständiger Pfad) können nur in Erstanbieterbrowsern (Internet Explorer, Edge) blockiert werden.
> - Verschlüsselte URLS (nur FQDN) können außerhalb von Erstanbieterbrowsern (Internet Explorer, Edge) blockiert werden.
> - Vollständige URL-Pfadblöcke können auf Domänenebene und alle unverschlüsselten URLs angewendet werden.
 
> [!NOTE]
> Es kann bis zu 2 Stunden Wartezeit (in der Regel weniger) zwischen dem Zeitpunkt, zu dem die Aktion ausgeführt wird, und der URL und der IP-Adresse, die blockiert wird, geben. 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>Erstellen eines Indikators für IPs, URLs oder Domänen auf der Einstellungsseite

1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Indikatoren** aus.  

2. Wählen Sie die Registerkarte **"IP-Adressen" oder "URLs/Domänen"** aus.

3. Wählen Sie **"Element hinzufügen"** aus.

4. Geben Sie die folgenden Details an:
   - Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.
   - Aktion – Geben Sie die auszuführende Aktion an, und geben Sie eine Beschreibung an.
   - Bereich: Definieren Sie den Bereich der Computergruppe.

5. Überprüfen Sie die Details auf der Registerkarte "Zusammenfassung", und klicken Sie dann auf **"Speichern".**

## <a name="related-topics"></a>Verwandte Themen
- [Indikatoren erstellen](manage-indicators.md)
- [Erstellen von Indikatoren für Dateien](indicator-file.md)
- [Erstellen von Indikatoren basierend auf Zertifikaten](indicator-certificates.md)
- [Indikatoren verwalten](indicator-manage.md)
