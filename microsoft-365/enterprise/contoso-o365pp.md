---
title: Office 365 ProPlus-Bereitstellung für Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen, wie Contoso System Center Configuration Manager zum Bereitstellen von Office 365 ProPlus verwendet.
ms.openlocfilehash: 0fa0ca1d268dbfd57891804e20959147cd6385e4
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283548"
---
# <a name="office-365-proplus-deployment-for-contoso"></a>Office 365 ProPlus-Bereitstellung für Contoso

**Zusammenfassung:** Verstehen, wie Contoso System Center Configuration Manager zum Bereitstellen von Office 365 ProPlus verwendet.

Contoso hat seine PCs auf Windows 10 Enterprise und Office 365 ProPlus aktualisiert, um eine effektivere Zusammenarbeit zu ermöglichen, bessere Sicherheit zu gewährleisten und eine modernere Desktopoberfläche bereitzustellen. Nach der Bewertung der Infrastruktur- und Geschäftsanforderungen hat Contoso die folgenden wichtigen Anforderungen für die Bereitstellung ermittelt:

- Alle PCs müssen Office 365 ProPlus ausführen.
- Die Bereitstellung muss möglichst die vorhandenen Management-Tools und Infrastruktur nutzen.
- Die Bereitstellung muss mehrere Sprachen und vorhandene Architekturen auf den Endbenutzergeräten unterstützen.
- PCs sollen immer auf dem neuesten Stand und sicher sein, wobei minimale IT-Verwaltungskosten anfallen und minimalen Auswirkungen für die Endbenutzer spürbar werden sollen.

## <a name="deployment-tools"></a>Bereitstellungstools

Basierend auf den Anforderungen entschied sich Contoso für die Bereitstellung von Windows und Office mit System Center Configuration Manager (Current Branch). Configuration Manager kann an große Umgebungen angepasst werden und bietet eine umfassende Kontrolle über Installation, Updates und Einstellungen. Er verfügt außerdem über integrierte Features, um die Bereitstellung und Verwaltung von Office zu vereinfachen und effizienter zu gestalten, darunter:

- Peercache, der bei begrenzter Netzwerkkapazität von Nutzen sein kann, wenn die Bereitstellung für Geräte an Remotestandorten erfolgt
- Das Dashboard zur Office-Clientverwaltungs, mit dem die Bereitstellung von Office vereinfacht wird und das Aktualisierungen überwacht und Administratoren Zugriff auf die neuesten Bereitstellungs- und Verwaltungsfeatures bietet.
- Intelligente Bereitstellung von Language Packs, einschließlich der automatischen Bereitstellung derselben Sprache, die das Betriebssystem verwendet
- Vollständig unterstützte und einfach zu verwendende Methode zum Entfernen vorhandener Versionen von Office auf einem Client während der Bereitstellung

Zusätzlich zu Configuration Manager verwendete Contoso das [Readiness Toolkit](https://docs.microsoft.com/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro), ein kostenloses Tool von Microsoft, um Kompatibilitätsprobleme mit Office-Makros und -Add-Ins zu bewerten.

## <a name="managing-the-deployment-and-updates"></a>Verwaltung der Bereitstellung und Updates

Office 365 ProPlus hat ein neues Veröffentlichungsmodell: Office als Dienst (Office as a Service). Das Dienstmodell macht es einfache, immer auf dem neusten Stand zu bleiben und von aktuellen Funktionen zu profitieren. Es erfordert jedoch häufig eine Änderung der Vorgehensweise von IT-Abteilungen, wie neue Versionen bereitgestellt und getestet werden. Um Kompatibilitätsprobleme zu minimieren und um sicherzustellen, dass die Computern immer auf dem neuesten Stand sind, hat Contoso Windows und Office in zwei Phasen bereitgestellt: 

- In der ersten Phase hat Contoso Office 365 ProPlus auf einer kleinen Gruppe von repräsentativen Geräten in der gesamten Organisation bereitgestellt. Diese Pilotgruppe wurde verwendet, um Apps, Add-Ins und Hardware mit Office 365 ProPlus zu testen.
- Vier Monate später, nachdem alle kritischen Probleme mit Apps, Add-Ins und Hardware in der Pilotgruppe behandelt wurden, stellte Contoso Office 365 ProPlus für den Rest der Geräte in der Organisation (die allgemeine Gruppe) bereit. 

Anstatt Updates von Office mit Configuration Manager zu verwalten, aktivierte Contoso automatische Updates über die Cloud. Cloudbasierte Updates hatten einen reduzierten Verwaltungsaufwand zur Folge, wobei sichergestellt wurde, dass die Geräte stets auf dem neuesten Stand sind. 

Contoso folgte dem gleichen zweistufigen Ansatz, den das Unternehmen für die Bereitstellung von Office nutzte, für Feature-Updates: Geräte in der Pilotgruppe erhielten Feature-Updates vier Monate vor den Geräten in der restlichen Organisation (die allgemeine Gruppe). Um dies für Office zu aktivieren, verwendete Contoso zwei empfohlene [Updatekanäle](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus): 

- den halbjährlichen Kanal (gezielt) für Updates für die Pilotgruppe 
- den halbjährlichen Kanal für Updates für die allgemeine Gruppe. 

Da der halbjährliche Kanal (gezielt) eine Version von Office 365 ProPlus vier Monate vor den halbjährlichen Kanal veröffentlicht, hat Contoso Zeit, um die Updates zu überprüfen, ohne sie verwalten zu müssen. 

## <a name="deployment-process"></a>Bereitstellungsprozess

Um die Bereitstellung von Office abzuschließen, hat Contoso den folgenden Prozess implementiert, der Empfehlungen zu bewährten Vorgehensweisen von Microsoft umfasst:

1. Vor der Bereitstellung verwendete das Unternehmen das Readiness Toolkit zum Testen der Apps und Office-Add-Ins, um so die Kompatibilität mit Office 365 ProPlus zu bewerten.
2. Contoso aktivierte in Configuration Manager den Peercache auf Clientgeräten, was bei begrenzter Netzwerkkapazität von Nutzen ist, wenn die Bereitstellung auf Clientgeräten an Remotestandorten erfolgt. 
3. Das Unternehmen definierte zwei Bereitstellungsgruppen als Gerätesammlungen in Configuration Manager: eine Pilotgruppe und eine allgemeine Gruppe. Die Pilotgruppe, die eine kleine Gruppe von repräsentativen Geräten in der gesamten Organisation enthielt, wurde für das zusätzliche Testen von Apps, Add-Ins und Hardware mit Windows 10 Enterprise und Office 365 ProPlus verwendet. 
4. Das Unternehmen erstellte Bereitstellungspakete für Office mit dem Office-Clientverwaltungs-Dashboard und dem Office 365-Installationsprogrammassistenten, die beide Teil der Configuration Manager-Konsole sind. Es wurden zwei Office 365 ProPlus-Pakete erstellt, eines für die Pilotgruppe mit dem halbjährlichen Kanal (gezielt) und eines für die allgemeine Gruppe mit dem halbjährlichen Kanal. 
5. Als Teil der einzelnen Office-Pakete wurden Language Packs für Englisch, Französisch und Deutsch einbezogen. Wenn ein Gerät eine Sprache erforderte, die nicht im Office-Paket enthalten war, wurde sie automatisch vom Office Content Delivery Network (CDN) heruntergeladen.
6. Das Unternehmen verwendete das im Office-Paket integrierte Feature zum automatischen Entfernen aller vorhandenen MSI-Versionen von Office vor der Installation von Office 365 ProPlus.
7. Das Unternehmen stellte in Configuration Manager die Windows- und Office-Pakete für Verteilungspunkte im Netzwerk bereit und führte anschließend die Bereitstellung-Aufgabensequenzen von Configuration Manager durch, um die Office 365 ProPlus-Pakete für den Piloten in der Pilotgruppe bereitzustellen.
8. Nachdem Kompatibilitätsprobleme mit der Pilotgruppe behandelt wurden, führte Contoso die Aufgabensequenzen zum Bereitstellen des Office 365 ProPlus-Pakets für die allgemeine Gruppe aus.

Da sich Contoso entschlossen hat, Geräte automatisch aus der Cloud zu aktualisieren, war es nicht erforderlich, den Prozess im Configuration Manager zu verwalten. Die Geräte werden direkt automatisch direkt aus der Cloud und basierend auf dem Updatekanal, den Sie als Teil der ersten Bereitstellung definieren, aktualisiert. 

## <a name="next-step"></a>Nächster Schritt

[Erfahren Sie](contoso-mdm.md), wie Contoso Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise zum Verwalten von Geräten und den darauf ausgeführten Apps im Unternehmen verwendet.

## <a name="see-also"></a>Siehe auch

[Office 365 ProPlus für Microsoft 365 Enterprise](office365proplus-infrastructure.md)

[Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
