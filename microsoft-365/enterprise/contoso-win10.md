---
title: Bereitstellung von Windows 10 Enterprise für Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen dazu, wie Contoso Microsoft Endpoint Configuration Manager zur Bereitstellung von direkten Upgrades für Windows 10 Enterprise verwendete.
ms.openlocfilehash: 0543f24665048d0679bc1b099fdd0a2d431c1e54
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754247"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Bereitstellung von Windows 10 Enterprise für Contoso

Vor dem breiten Rollout von Microsoft 365 for Enterprise hatte Contoso Windows-kompatible PCs und Geräte mit einer Kombination aus Windows 7 (10%), Windows 8.1 (65%) und Windows 10 (25%). Contoso wollte ein Upgrade seiner PCs für Windows 10 Enterprise nutzen Sie die erweiterte Sicherheit und senken Sie den IT-Overhead von automatisierten Bereitstellungen von Updates. 

Nach der Bewertung der Infrastruktur und der Geschäftsanforderungen identifizierte Contoso die folgenden Hauptanforderungen für die Bereitstellung:

- Windows 10 Enterprise soll auf so vielen Computern und Geräten wie möglich ausgeführt werden.
- Die Einführung von direkten Upgrades nutzt die vorhandene Configuration Manager-Infrastruktur.
- Die Steuerung, welche Versionen von Windows 10 Enterprise bereitgestellt und aktualisiert werden sollen, erfolgt über Ringe.
- Computer und Geräte sollen mit minimalen IT-Verwaltungskosten und minimalen Auswirkungen auf die Endbenutzer auf dem aktuellen Stand gehalten werden.

„Auf dem neuesten Stand“ wird definiert als die unterstützte Version von Windows 10 Enterprise, die den Geschäftsanforderungen von Contoso entspricht; dabei muss es nicht unbedingt darum gehen, dass auf allen Windows-kompatiblen Computern die neueste Version von Windows 10 Enterprise ausgeführt wird.

## <a name="deployment-tools"></a>Bereitstellungstools

Vor und während direkter Upgrades von Windows 10 Enterprise verwendete Contoso die folgenden Lösungen von Windows Analytics:

- Upgradebereitschaft  

  Es werden System-, Anwedungs- und Treiberdaten für die Analyse erfasst und dann Kompatibilitätsprobleme identifiziert, durch die ein Upgrade und vorgeschlagene Korrekturen blockiert werden können, die Microsoft bekannt sind.

- Update-Compliance  

  Zeigt den Status Ihrer Geräte in Bezug auf die Windows-Updates an, so dass Sie sicherstellen können, dass diese gegebenenfalls auf den aktuellsten Updates sind.

- Geräteintegrität  

  Identifiziert Geräte, die häufig abstürzen und daher möglicherweise neu aufgebaut oder ersetzt werden müssen, und Gerätetreiber, die Geräteabstürze verursachen, mit Vorschlägen für alternative Versionen dieser Treiber, welche die Anzahl der Abstürze reduzieren könnten. Bietet eine Benachrichtigung über Fehlkonfigurationen des Windows Information Protection, die Eingabeaufforderungen an Endbenutzer senden.
 
Contoso verfügt über eine vorhandene Infrastruktur von Configuration Manager (Current Branch). Configuration Manager kann an große Umgebungen angepasst werden und bietet eine umfassende Kontrolle über Installation, Updates und Einstellungen. Er verfügt außerdem über integrierte Features, um die Bereitstellung und Verwaltung von Windows 10 Enterprise zu vereinfachen und effizienter zu gestalten.

## <a name="planning-process"></a>Planungsprozess

Contoso hat die Upgrade-Bereitschaft in Windows Analytics verwendet, um die Gruppe der installierten apps und deren Kompatibilität mit Windows 10 Enterprise zu ermitteln.

## <a name="deployment-process"></a>Bereitstellungsprozess

Um die Bereitstellung des direkten Upgrades von Windows 10 Enterprise abzuschließen, hat Contoso den folgenden Prozess implementiert, der Empfehlungen zu bewährten Vorgehensweisen von Microsoft umfasst:

1. Der Peercache für Configuration Manager wurde aktiviert.
2. Es wurden angepasste Windows-Pakete basierend auf Images aus dem Volume Licensing Service Center erstellt.
3. Verwenden Sie den Konfigurations-Manager, um die Windows-Pakete für Verteilungspunkte in Ihrem Netzwerk bereitzustellen und Builds für die drei Bereitstellungsgruppen für Validierung und Bereitstellung bereitzustellen.
4. Mithilfe der Lösungen für Geräteintegrität und Updatebereitschaft von Windows Analytics wurden der Erfolg von Computern und Geräten in den drei Ringen für Überprüfung und Staging der Bereitstellung bewertet.
5. Basierend auf den Windows Analytics-Informationen hat Contoso die Version von Windows 10 Enterprise festgelegt, die in der breiten Bereitstellungsgruppe bereitgestellt werden soll.
6. Die Configuration Manager-Bereitstellungstasksequenzen wurden ausgeführt, um das ausgewählte Windows-Paket für die Breite Bereitstellungsgruppe bereitzustellen.
7. Überwachte PCs und Geräte in der breiten Bereitstellungsgruppe mithilfe der Geräte Integrität und Update Compliance-Lösungen, um Probleme zu beheben.

Hier ist Contosos Bereitstellungsarchitektur für das direkte Upgrade und fortlaufende Updates.

![Contosos Bereitstellungsinfrastruktur für Windows 10 Enterprise](../media/contoso-win10/contoso-win10-fig1.png)

Diese Infrastruktur besteht aus:

- Configuration Manager, der:
  - Images für Windows 10 Enterprise-Pakete aus dem Microsoft Volume Licensing Center im Microsoft Network abruft.
  - Als zentraler Verwaltungspunkt für Bereitstellungspakete fungiert.
- Regionale Verteilungspunkte befinden sich in der Regel in den regionalen Hub-Büros von Contoso.
- Windows-PCs und-Geräte an verschiedenen Standorten, die die Bereitstellungspakete für das in-Place-Upgrade oder laufende Updates basierend auf der Gruppenmitgliedschaft empfangen und installieren.

## <a name="next-step"></a>Nächster Schritt

Erfahren Sie, wie Contoso seine Configuration Manager-Infrastruktur nutzt, um [aktuelle Microsoft 365-Apps für Unternehmen in Ihrer Organisation bereitzustellen und zu halten](contoso-o365pp.md) . 

## <a name="see-also"></a>Siehe auch

[Windows 10 Enterprise](https://docs.microsoft.com/windows/deployment/)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
