---
title: Erstellen von Indikatoren für IPs und URLs/Domänen
ms.reviewer: ''
description: Erstellen Sie Indikatoren für IPs und URLs/Domänen, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.
keywords: ip, url, domain, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: 3cfdc226ec5b476a37d15b67ca6158313e508adf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067711"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>Erstellen von Indikatoren für IPs und URLs/Domänen 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


Defender for Endpoint kann das blockieren, was Microsoft als bösartige IPs/URLs bezeichnet, über Windows Defender SmartScreen für Microsoft-Browser und über Netzwerkschutz für Nicht-Microsoft-Browser oder Anrufe außerhalb eines Browsers.

Der Datensatz für Die Bedrohungsintelligenz wurde von Microsoft verwaltet.

Durch das Erstellen von Indikatoren für IPs und URLs oder Domänen können Sie jetzt IPs, URLs oder Domänen basierend auf Ihrer eigenen Bedrohungsintelligenz zulassen oder blockieren. Sie können dies über die Einstellungsseite oder durch Computergruppen tun, wenn Sie bestimmte Gruppen als mehr oder weniger gefährdet als andere personen sehen.

> [!NOTE]
> Klassenlose Inter-Domain (CIDR)-Notation für IP-Adressen wird nicht unterstützt. 

### <a name="before-you-begin"></a>Vorbereitung
Es ist wichtig, vor dem Erstellen von Indikatoren für IPS, URLs oder Domänen die folgenden Voraussetzungen zu kennen:
- URL/IP allow and block basiert darauf, dass die Defender for Endpoint-Komponente Netzwerkschutz im Blockmodus aktiviert wird. Weitere Informationen zu Netzwerkschutz und Konfigurationsanweisungen finden Sie unter [Enable network protection](enable-network-protection.md).
- Die Antischalware-Clientversion muss 4.18.1906.x oder höher sein. 
- Unterstützt auf Computern unter Windows 10, Version 1709 oder höher. 
- Stellen Sie **sicher, dass** benutzerdefinierte Netzwerkindikatoren in **Microsoft Defender Security Center > Einstellungen > Erweiterten Features aktiviert sind.** Weitere Informationen finden Sie unter [Erweiterte Features](advanced-features.md).
- Informationen zur Unterstützung von Indikatoren unter iOS finden Sie unter [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).


> [!IMPORTANT]
> Der Indikatorliste können nur externe IPs hinzugefügt werden. Indikatoren können nicht für interne IPs erstellt werden.
> Für Webschutzszenarien wird die Verwendung der integrierten Funktionen in Microsoft Edge empfohlen. Microsoft Edge nutzt [Network Protection zum](network-protection.md) Überprüfen des Netzwerkdatenverkehrs und ermöglicht Blöcke für TCP, HTTP und HTTPS (TLS). Für alle anderen Prozesse nutzen Webschutzszenarien Network Protection für die Überprüfung und Durchsetzung: <br>
> HINWEIS:
> - IP wird für alle drei Protokolle unterstützt
> - Es werden nur einzelne IP-Adressen unterstützt (keine CIDR-Blöcke oder IP-Bereiche)
> - Verschlüsselte URLs (vollständiger Pfad) können nur in Browsern erster Partei (Internet Explorer, Edge) blockiert werden.
> - Verschlüsselte URLs (nur FQDN) können außerhalb von Browsern von Drittanbietern blockiert werden (Internet Explorer, Edge)
> - Vollständige URL-Pfadblöcke können auf Domänenebene und alle unverschlüsselten URLs angewendet werden.
 
> [!NOTE]
> Es kann bis zu 2 Stunden Wartezeit (in der Regel weniger) zwischen dem Zeitpunkt, zu dem die Aktion ergriffen wird, und der URL und der BLOCKIERTen IP liegen. 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>Erstellen eines Indikators für IPs, URLs oder Domänen auf der Einstellungsseite

1. Wählen Sie im Navigationsbereich **Einstellungsindikatoren**  >  **aus.**  

2. Wählen Sie die **Registerkarte IP-Adressen oder URLs/Domänen** aus.

3. Wählen **Sie Element hinzufügen aus.**

4. Geben Sie die folgenden Details an:
   - Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.
   - Aktion – Geben Sie die zu ergreifende Aktion an, und geben Sie eine Beschreibung an.
   - Bereich : Definieren Sie den Bereich der Computergruppe.

5. Überprüfen Sie die Details auf der Registerkarte Zusammenfassung, und klicken Sie dann auf **Speichern**.

## <a name="related-topics"></a>Verwandte Themen
- [Erstellen von Indikatoren](manage-indicators.md)
- [Erstellen von Indikatoren für Dateien](indicator-file.md)
- [Erstellen von Indikatoren basierend auf Zertifikaten](indicator-certificates.md)
- [Verwalten von Indikatoren](indicator-manage.md)
