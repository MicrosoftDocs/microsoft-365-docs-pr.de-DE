---
title: Microsoft 365 Apps for Enterprise-Bereitstellung für Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen, wie Contoso Microsoft Endpoint Configuration Manager zum Bereitstellen von Microsoft 365 Apps for Enterprise verwendet.
ms.openlocfilehash: eca3978103ca1e590d747b3549a3c9e393f871ca
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43625254"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Microsoft 365 Apps for Enterprise-Bereitstellung für Contoso

Contoso rüstete seine PCs auf Windows 10 Enterprise und Microsoft 365 Apps for Enterprise auf, um eine effektivere Zusammenarbeit, bessere Sicherheit und ein moderneres Desktopdarstellung zu ermöglichen. Nach einer Bewertung der Infrastruktur und der Geschäftsanforderungen identifizierte Contoso folgende Schlüsselanforderungen für die Bereitstellung:

- Auf allen PCs sollte Microsoft 365 Apps for Enterprise ausgeführt werden
- Die Bereitstellung muss möglichst die vorhandenen Management-Tools und Infrastruktur nutzen.
- Die Bereitstellung muss mehrere Sprachen und vorhandene Architekturen auf den Endbenutzergeräten unterstützen.
- PCs sollen immer auf dem neuesten Stand und sicher sein, wobei minimale IT-Verwaltungskosten anfallen und minimalen Auswirkungen für die Endbenutzer spürbar werden sollen.

## <a name="deployment-tools"></a>Bereitstellungstools

Aufgrund seiner Anforderungen entschied sich Contoso für die Bereitstellung von Windows 10 Enterprise und Microsoft 365 Apps for Enterprise mit Configuration Manager (Current Branch). Configuration Manager ist für große Umgebungen skalierbar und bietet umfassende Kontrolle über Installation, Updates und Einstellungen. Außerdem verfügt er über integrierte Funktionen, die die Bereitstellung und Verwaltung von Office einfacher und effizienter machen, darunter:

- Peercache, der bei begrenzter Netzwerkkapazität von Nutzen sein kann, wenn die Bereitstellung für Geräte an Remotestandorten erfolgt
- Das Dashboard zur Office-Clientverwaltungs, mit dem die Bereitstellung von Office vereinfacht wird und das Aktualisierungen überwacht und Administratoren Zugriff auf die neuesten Bereitstellungs- und Verwaltungsfeatures bietet.
- Intelligente Bereitstellung von Language Packs, einschließlich der automatischen Bereitstellung derselben Sprache, die das Betriebssystem verwendet
- Vollständig unterstützte und einfach zu verwendende Methode zum Entfernen vorhandener Versionen von Office auf einem Client während der Bereitstellung

Zusätzlich zu Configuration Manager verwendete Contoso das [Readiness Toolkit](https://docs.microsoft.com/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro), ein kostenloses Tool von Microsoft, um Kompatibilitätsprobleme mit Office-Makros und -Add-Ins zu bewerten.

## <a name="managing-the-deployment-and-updates"></a>Verwaltung der Bereitstellung und Updates

Microsoft 365 Apps for Enterprise hat ein neues Release-Modell: Office als Dienstleistung. Das Servicemodell macht es einfach, mit neuen Funktionen auf dem Laufenden zu bleiben, erfordert jedoch häufig eine Änderung der Vorgehensweise der IT-Abteilungen bei der Bereitstellung und dem Testen neuer Versionen. Um Kompatibilitätsprobleme zu minimieren und sicherzustellen, dass seine Computer auf dem neuesten Stand bleiben, hat Contoso Windows und Office in zwei Phasen bereitgestellt: 

- In der ersten Phase wurden Microsoft 365-Apps für Unternehmen auf einer kleinen Anzahl repräsentativer Geräte im gesamten Unternehmen bereitgestellt. Diese Pilotgruppe wurde eingesetzt, um Anwendungen, Add-Ins und Hardware mit Microsoft 365 Apps for Enterprise zu testen.
- Vier Monate später, nachdem alle kritischen Probleme mit Anwendungen, Add-Ins und Hardware in der Pilotgruppe gelöst waren, stellte Contoso Microsoft 365 Apps for Enterprise für die restlichen Geräte in der Organisation (die breite Gruppe) bereit. 

Anstatt Updates von Office mit Configuration Manager zu verwalten, aktivierte Contoso automatische Updates über die Cloud. Cloudbasierte Updates hatten einen reduzierten Verwaltungsaufwand zur Folge, wobei sichergestellt wurde, dass die Geräte stets auf dem neuesten Stand sind. 

Contoso folgte dem gleichen zweistufigen Ansatz für Feature-Updates, den das Unternehmen für die Bereitstellung von Office nutzte: Geräte in der Pilotgruppe erhielten Feature-Updates vier Monate vor den Geräten in der restlichen Organisation (die allgemeine Gruppe). Um dies für Office zu aktivieren, verwendete Contoso zwei empfohlene [Updatekanäle](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus): 

- den halbjährlichen Kanal (gezielt) für Updates für die Pilotgruppe 
- den halbjährlichen Kanal für Updates für die allgemeine Gruppe. 

Da der halbjährliche (gezielt) Kanal vier Monate früher als der halbjährliche Kanal eine Version von Microsoft 365 Apps for Enterprise veröffentlicht, hat Contoso Zeit, die Updates zu validieren, ohne sie verwalten zu müssen. 

## <a name="deployment-process"></a>Bereitstellungsprozess

Um die Bereitstellung von Office abzuschließen, hat Contoso den folgenden Prozess implementiert, der Empfehlungen zu bewährten Vorgehensweisen von Microsoft umfasst:

1. Vor der Bereitstellung testete das Unternehmen unter Verwendung des Readiness Toolkits ihre Anwendungen und Office-Add-Ins, um ihre Kompatibilität mit Microsoft 365 Apps for Enterprise zu bewerten.
2. Contoso aktivierte in Configuration Manager den Peercache auf Clientgeräten, was bei begrenzter Netzwerkkapazität von Nutzen ist, wenn die Bereitstellung auf Clientgeräten an Remotestandorten erfolgt. 
3. Das Unternehmen definierte im Configuration Manager zwei Bereitstellungsgruppen als Gerätesammlungen: eine Pilotgruppe und eine breite Gruppe. Die Pilotgruppe, die eine kleine Gruppe repräsentativer Geräte in der gesamten Organisation umfasste, wurde dazu verwendet, zusätzliche Tests von Anwendungen, Add-Ins und Hardware mit Windows 10 Enterprise und Microsoft 365 Apps for Enterprise durchzuführen. 
4. Das Unternehmen erstellte mithilfe des Office Client Management-Dashboards und des Office 365-Installationsassistenten Bereitstellungspakete für Office, die beide Teil der Konfigurationsmanager-Konsole sind. Es wurden zwei Microsoft 365 Apps for Enterprise-Pakete erstellt, eins für die Pilotgruppe im halbjährlichen Kanal (gezielt) und eins für die breite Gruppe im halbjährlichen Kanal. 
5. Als Teil der einzelnen Office-Pakete wurden Language Packs für Englisch, Französisch und Deutsch einbezogen. Wenn ein Gerät eine Sprache erforderte, die nicht im Office-Paket enthalten war, wurde sie automatisch vom Office Content Delivery Network (CDN) heruntergeladen.
6. Das Unternehmen nutzte die integrierte Funktion im Office-Paket, um automatisch alle vorhandenen MSI-Versionen von Office zu entfernen, bevor Microsoft 365 Apps for Enterprise installiert wurde.
7. In Configuration Manager stellte das Unternehmen die Windows- und Office-Pakete an Verteilungspunkten in seinem Netzwerk bereit und führte dann die Configuration Manager-Bereitstellungsaufgabensequenzen aus, um das Microsoft 365 Apps for Enterprise-Pilotpaket für die Pilotgruppe bereitzustellen.
8. Nachdem alle Kompatibilitätsprobleme mit der Pilotgruppe behandelt waren, führte Contoso die Aufgabensequenzen aus, um das breite Microsoft 365 Apps for Enterprise-Paket für die breite Gruppe bereitzustellen.

Da sich Contoso entschlossen hat, Geräte automatisch aus der Cloud zu aktualisieren, war es nicht erforderlich, den Prozess im Configuration Manager zu verwalten. Die Geräte werden direkt automatisch direkt aus der Cloud und basierend auf dem Updatekanal, den Sie als Teil der ersten Bereitstellung definieren, aktualisiert. 

Hier finden Sie die Bereitstellungsarchitektur von Contoso für die Unternehmensinstallation und laufende Updates für Microsoft 365 Apps for Enterprise.

![Die Bereitstellungsinfrastruktur von Contoso für Microsoft 365 Apps for Enterprise](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Nächster Schritt

[Erfahren Sie](contoso-mdm.md), wie Contoso Microsoft Intune in Microsoft 365 Enterprise zum Verwalten von Geräten und den darauf ausgeführten Apps im Unternehmen verwendet.

## <a name="see-also"></a>Siehe auch

[Microsoft 365 Apps for Enterprise für Microsoft 365 Enterprise](office365proplus-infrastructure.md)

[Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
