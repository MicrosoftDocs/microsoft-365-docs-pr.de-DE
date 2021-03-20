---
title: Microsoft 365 Apps for Enterprise-Bereitstellung für Contoso
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
description: Verstehen, wie Contoso Microsoft Endpoint Configuration Manager zum Bereitstellen von Microsoft 365 Apps for Enterprise verwendet.
ms.openlocfilehash: 71958b2e87882e478a852db1f906f61207837854
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907674"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Microsoft 365 Apps for Enterprise-Bereitstellung für Contoso

Contoso hat seine PCs auf Windows 10 Enterprise und Microsoft 365 Apps for Enterprise aktualisiert, um eine effektivere Zusammenarbeit, eine bessere Sicherheit und eine modernere Desktopumgebung zu ermöglichen. Nachdem sie ihre Infrastruktur- und Geschäftsanforderungen bewertet haben, hat Contoso die folgenden zentralen Anforderungen für die Bereitstellung identifiziert:

- Auf allen PCs sollten Microsoft 365 Apps for Enterprise ausgeführt werden.
- Die Bereitstellung sollte nach Möglichkeit vorhandene Verwaltungstools und Infrastruktur verwenden.
- Die Bereitstellung muss mehrere Sprachen und vorhandene Architekturen auf den Geräten der Benutzer unterstützen.
- PCs sollten mit minimalen IT-Verwaltungskosten und minimalen Auswirkungen für Benutzer auf dem neuesten Stand bleiben und sicher bleiben.

## <a name="deployment-tools"></a>Bereitstellungstools

Basierend auf ihren Anforderungen entschied sich Contoso für die Bereitstellung von Windows 10 Enterprise und Microsoft 365 Apps for Enterprise über Configuration Manager (Current Branch). Configuration Manager skaliert für große Umgebungen und bietet umfassende Kontrolle über Installation, Updates und Einstellungen. Es verfügt auch über integrierte Features, um die Bereitstellung und Verwaltung von Office zu vereinfachen und effizienter zu gestalten, einschließlich:

- Peercache, der bei der Bereitstellung auf Geräten an Remotestandorten mit eingeschränkter Netzwerkkapazität helfen kann.
- Das Office-Clientverwaltungsdashboard, das die Bereitstellung von Office und die Überwachung von Updates erleichtert und Administratoren Zugriff auf die neuesten Bereitstellungs- und Verwaltungsfeatures bietet.
- Intelligente Language Pack-Bereitstellung, einschließlich der automatischen Bereitstellung derselben Sprache wie das Betriebssystem.
- Eine vollständig unterstützte und einfach zu verwendende Methode zum Entfernen vorhandener Versionen von Office von einem Client während der Bereitstellung.

Zusätzlich zu Configuration Manager verwendete Contoso das [Readiness Toolkit für Office-Add-Ins und VBA,](/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)ein kostenloses Tool von Microsoft, um Kompatibilitätsprobleme mit ihren Office-Makros und -Add-Ins zu bewerten.

## <a name="managing-deployment-and-updates"></a>Verwalten von Bereitstellung und Updates

Microsoft 365 Apps for Enterprise verfügt über ein neues Veröffentlichungsmodell: Office as a service. Das Dienstmodell macht es einfach, mit neuen Features auf dem neuesten Stand zu bleiben. It often requires IT departments to change how they deploy and test new releases. Um Kompatibilitätsprobleme zu minimieren und sicherzustellen, dass ihre Computer auf dem neuesten Stand sind, hat Contoso Windows und Office in zwei Phasen bereitgestellt:

- Zunächst haben sie Microsoft 365 Apps for Enterprise auf einer kleinen Gruppe repräsentativer Geräte in der gesamten Organisation bereitgestellt. Diese Pilotgruppe wurde zum Testen von Apps, Add-Ins und Hardware mit Microsoft 365 Apps for Enterprise verwendet.
- Vier Monate später, nachdem alle kritischen Probleme mit Anwendungen, Add-Ins und Hardware in der Pilotgruppe gelöst waren, stellte Contoso Microsoft 365 Apps for Enterprise für die restlichen Geräte in der Organisation (die breite Gruppe) bereit.

Anstatt Updates für Office mithilfe von Configuration Manager zu verwalten, aktivierte Contoso automatische Updates aus der Cloud. Cloudbasierte Updates reduzieren den Verwaltungsaufwand und stellen sicher, dass Geräte auf dem neuesten Stand bleiben.

Contoso verfolgte den gleichen zweistufigen Ansatz für Featureupdates wie für die Bereitstellung von Office: Geräte in der Pilotgruppe erhielten Featureupdates vier Monate früher als Geräte in der restlichen Organisation (die breite Gruppe). Um dies für Office zu aktivieren, verwendete Contoso zwei empfohlene [Updatekanäle:](/DeployOffice/overview-update-channels)

- Halbjährlicher Enterprise-Kanal (Vorschau) für Updates für die Pilotgruppe
- Semi-Annual Enterprise Channel für Updates für die breite Gruppe

Da der halbjährliche Enterprise-Kanal (Vorschau) vier Monate früher als der halbjährliche Enterprise-Kanal eine Version von Microsoft 365 Apps for Enterprise veröffentlicht, hat Contoso Zeit, die Updates zu validieren, ohne sie verwalten zu müssen.

## <a name="deployment-process"></a>Bereitstellungsprozess

Um die Bereitstellung von Office abzuschließen, hat Contoso den folgenden Prozess implementiert, der Empfehlungen zu bewährten Vorgehensweisen von Microsoft umfasst:

1. Vor der Bereitstellung verwendete Contoso das Readiness Toolkit für Office-Add-In und VBA, um seine Apps und Office-Add-Ins zu testen, um die Kompatibilität mit Microsoft 365 Apps for Enterprise zu bewerten.
1. In Configuration Manager haben sie den Peercache auf ihren Clientgeräten aktiviert, was bei der Bereitstellung auf Clientgeräten an Remotestandorten mit eingeschränkter Netzwerkkapazität hilft. 
1. Contoso definierte zwei Bereitstellungsgruppen als Gerätesammlungen im Configuration Manager: eine Pilotgruppe und eine breite Gruppe. Die Pilotgruppe, die eine kleine Gruppe repräsentativer Geräte in der gesamten Organisation umfasste, wurde für zusätzliche Tests von Apps, Add-Ins und Hardware mit Windows 10 Enterprise und Microsoft 365 Apps for Enterprise verwendet.
1. Sie haben Bereitstellungspakete für Office mithilfe des Office Client Management Dashboards und des Office 365 Installer-Assistenten erstellt, die beide Teil der Configuration Manager-Konsole sind. Sie haben zwei Microsoft 365 Apps for Enterprise-Pakete erstellt, eine für die Pilotgruppe im Semi-Annual Enterprise Channel (Preview) und eine für die breite Gruppe im Semi-Annual Enterprise Channel.
2. Jedes Office-Paket enthielt englische, französische und deutsche Sprachpakete. Wenn für ein Gerät eine Sprache erforderlich war, die nicht im Office-Paket enthalten war, wurde dieses Sprachpaket automatisch aus dem Office Content Delivery Network (CDN) heruntergeladen.
3. Das Unternehmen nutzte die integrierte Funktion im Office-Paket, um automatisch alle vorhandenen MSI-Versionen von Office zu entfernen, bevor Microsoft 365 Apps for Enterprise installiert wurde.
4. In Configuration Manager stellten sie die Windows- und Office-Pakete an Verteilungspunkten im netzwerk bereitgestellt. Anschließend haben sie die Configuration Manager-Bereitstellungs-Tasksequenzen ausgeführt, um das Microsoft 365 Apps for Enterprise-Pilotpaket für die Pilotgruppe zu bereitstellen.
5. Nachdem sie Kompatibilitätsprobleme mit der Pilotgruppe behoben haben, führte Contoso die Tasksequenzen aus, um das Microsoft 365 Apps for Enterprise-Paket für die breite Gruppe zu bereitstellen.

Da sich Contoso entschlossen hat, Geräte automatisch aus der Cloud zu aktualisieren, war es nicht erforderlich, den Prozess im Configuration Manager zu verwalten. Ihre Geräte werden automatisch direkt aus der Cloud basierend auf dem Updatekanal aktualisiert, der in der anfänglichen Bereitstellung definiert wurde.

Hier finden Sie die Bereitstellungsarchitektur von Contoso Microsoft 365 Apps for Enterprise und fortlaufende Updates.

![Die Contoso-Bereitstellungsinfrastruktur für Microsoft 365 Apps for Enterprise](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Nächster Schritt

Erfahren Sie, wie Contoso [Microsoft Intune](contoso-mdm.md) in Microsoft 365 Enterprise verwendet, um seine Geräte und die Apps zu verwalten, die in der gesamten Organisation ausgeführt werden.

## <a name="see-also"></a>Siehe auch

[Microsoft 365 Apps for Enterprise](/deployoffice/deployment-guide-microsoft-365-apps)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)