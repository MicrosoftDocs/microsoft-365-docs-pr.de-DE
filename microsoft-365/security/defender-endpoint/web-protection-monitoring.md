---
title: Überwachen der Sicherheit des Browsens im Web in Microsoft Defender ATP
description: Verwenden von Webschutz in Microsoft Defender ATP zum Überwachen der Sicherheit des Webbrowsers
keywords: Webschutz, Schutz vor Webbedrohungen, Browsen im Web, Überwachung, Berichte, Karten, Domänenliste, Sicherheit, Phishing, Schadsoftware, Exploit, Websites, Netzwerkschutz, Edge, Internet Explorer, Chrome, Firefox, Webbrowser
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5d5cb89bccb0d7ea0fa4891c3b5b0d11a7244cf8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063704"
---
# <a name="monitor-web-browsing-security"></a>Überwachen der Sicherheit des Browsens im Web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Mit Dem Webschutz können Sie die Sicherheit des Webbrowsens Ihrer Organisation mithilfe von Berichten unter **Berichte > Webschutz** im Microsoft Defender Security Center überwachen. Der Bericht enthält Karten, die Statistiken zur Erkennung von Webbedrohungen bereitstellen.

- **Erkennungen** von Webbedrohungen im Laufe der Zeit – diese Trendkarte zeigt die Anzahl von Webbedrohungen an, die während des ausgewählten Zeitraums vom Typ erkannt wurden (Letzte 30 Tage, Letzte 3 Monate, letzte 6 Monate)
 
    ![Abbildung der Karte mit Erkennungen von Webbedrohungen im Laufe der Zeit](images/wtp-blocks-over-time.png)

- **Zusammenfassung zum** Schutz von Webbedrohungen – diese Karte zeigt die gesamten Erkennungen von Webbedrohungen in den letzten 30 Tagen an und zeigt die Verteilung auf die verschiedenen Arten von Webbedrohungen an. Durch Auswählen eines Datenschnitts wird die Liste der Domänen geöffnet, die mit schädlichen oder unerwünschten Websites gefunden wurden.

    ![Abbildung der Karte mit der Zusammenfassung des Schutzes von Webbedrohungen](images/wtp-summary.png)

>[!Note]
>Es kann bis zu 12 Stunden dauern, bis ein Block in den Karten oder in der Domänenliste angezeigt wird.

## <a name="types-of-web-threats"></a>Arten von Webbedrohungen

Der Webschutz kategorisiert schädliche und unerwünschte Websites wie folgt:

- **Phishing** – Websites mit gefälschten Webformularen und anderen Phishingmechanismen, die Benutzer dazu verleiten sollen, Anmeldeinformationen und andere vertrauliche Informationen zu verleiten
- **Bösartig** – Websites, die Schadsoftware und Exploitcode hosten
- **Benutzerdefinierter** Indikator – Websites, deren URLs oder Domänen Sie Ihrer benutzerdefinierten Indikatorliste zum Blockieren [hinzugefügt](manage-indicators.md) haben

## <a name="view-the-domain-list"></a>Anzeigen der Domänenliste

Wählen Sie auf der Sammelkarte web threat protection eine bestimmte Kategorie für **Webbedrohungen** aus, um die Seite **Domänen zu** öffnen. Auf dieser Seite wird die Liste der Domänen unter dieser Bedrohungskategorie angezeigt. Die Seite enthält die folgenden Informationen für jede Domäne:

- **Zugriffsanzahl** – Anzahl der Anforderungen für URLs in der Domäne
- **Blöcke** – Anzahl der blockierten Anforderungen
- **Zugriffstrend** – Änderung der Anzahl der Zugriffsversuche
- **Bedrohungskategorie** – Typ der Webbedrohung
- **Geräte** – Anzahl der Geräte mit Zugriffsversuchen

Wählen Sie eine Domäne aus, um die Liste der Geräte, die versucht haben, auf URLs in dieser Domäne zu zugreifen, und die Liste der URLs anzeigen.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über den Webschutz](web-protection-overview.md)
- [Filtern von Webinhalten](web-content-filtering.md)
- [Schutz vor Webbedrohungen](web-threat-protection.md)
- [Reagieren auf Webbedrohungen](web-protection-response.md)
