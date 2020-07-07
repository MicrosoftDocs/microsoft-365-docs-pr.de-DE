---
title: 'Schritt 7: Windows und Office als Dienst'
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zur Vorbereitung für Windows und Office als Dienst in Ihrer Umgebung.
ms.openlocfilehash: e9de339c6bc66e5cd3c02af5f6a53c32b7573b1f
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679002"
---
# <a name="step-7-windows-and-office-servicing"></a>Schritt 7: Windows und Office als Dienst

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong>Schritt 7: Windows und Office als Dienst</strong></p>
<p>Both Windows 10 and Microsoft 365 Apps for enterprise continually add new capabilities to keep bringing user experiences and security forward with the latest innovations. Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Windows und Office als Dienst ist der siebte Schritt in dem von uns empfohlenen Rad für den Bereitstellungsprozess, der die Planungsaspekte der Vorbereitung auf halbjährliche Updates für Features behandelt. Den vollständigen Desktopbereitstellungsprozess finden Sie im [Desktopbereitstellungscenter](https://aka.ms/HowToShift).
>

Sowohl in Windows 10 und als auch in Microsoft 365 Apps for Enterprise werden neue Wartungsoptionen, Supportmodelle und Zeitpläne für Updates eingeführt. Anhand dieser Änderungen können Sie leichter über die neuesten Features auf dem Laufenden bleiben. Neben diesen Updates gibt es neue Konfigurationsoptionen, die Wartungspläne ermöglichen, die Ihren Anforderungen entsprechen. Erfahren Sie, wie Sie sich auf halbjährliche Kanalupdates mit neuen Features und Funktionen in Windows 10 und Microsoft 365 Apps for Enterprise vorbereiten, während Sie neue Features in Microsoft Endpoint Configuration Manager (Current Branch) nutzen.

[Unterstützung für Kunden beim Umstieg auf Windows 10 und Microsoft 365 Apps for Enterprise](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a>Updatetypen

Updates werden in zwei Hauptkategorien unterteilt, und zwar Featureupdates und Qualitäts- und Sicherheitsupdates, die kumulierte Sicherheit, Zuverlässigkeit und Fehlerbehebungen enthalten. Im Hinblick auf den Zeitplan stellen sowohl Windows als auch Office einen halbjährlichen Kanal bereit, der zweimal im Jahr im März und September neue Features liefert, während Qualitäts- und Sicherheitsupdates monatlich veröffentlicht werden. Darüber hinaus bieten wir nur für Office 365-Clientanwendungen einen vollständig unterstützten aktuellen Kanal, bei dem Updates sowohl neue Features als auch Qualitätsupdates enthalten.

Wenn Sie sich an einen längeren Zyklus zwischen Updates für Desktopbetriebssysteme und Apps gewöhnt hatten, fragen Sie sich vielleicht Folgendes:

  - Sind die Updates kompatibel?

  - Muss ich meine Benutzer ständig schulen?

  - Was sind die Risiken?

Zur Beantwortung dieser Fragen und zur Darstellung des Grundgedankens der häufigeren Bereitstellung neuer Funktionen werden nachfolgend einige der Vorteile dieses Ansatzes erläutert:

### <a name="feature-update-benefits"></a>Vorteile von Featureupdates

First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year. Why? With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current. Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.

[Kurzübersicht für Windows as a service](https://docs.microsoft.com/windows/deployment/update/waas-quick-start)

[Risikominimierung mithilfe von Windows 10-Sicherheitsfeatures](https://docs.microsoft.com/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a>Vorteile des Modells mit kumulativen Updates

Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past. It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office. As you can imagine, this creates a nearly impossible set of test matrices for support. Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.

With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced. Each update builds upon updates from previous months and contains all of the fixes that you need to get current. Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.

### <a name="expanded-validation-of-updates"></a>Erweiterte Überprüfung von Updates

Ein weiterer Vorteil besteht darin, dass wir vor der Veröffentlichung von Updates für die allgemeine Bereitstellung zunächst Builds über die Insider-Programme für [Office](https://products.office.com/office-insider?tab=Windows-Desktop) und [Windows](https://insider.windows.com/) veröffentlichen, sodass wir Diagnosedaten und Feedback vor der allgemeinen Veröffentlichung von Updates sammeln können. Die Insider-Programme sind jetzt für alle verfügbar, Sie können sich also schon mit den Updates vertraut machen. Bis Updates veröffentlicht werden, haben wir Diagnosedaten von Millionen von Konfigurationen erhalten, wenn die Updates schließlich eingeführt werden, ist die Qualität viel besser prognostizierbar.

Ein weiterer Punkt: Wenn Sie einen halbjährlichen Kanal für Office zur Bereitstellung von Featureupdates zwei mal pro Jahr in Übereinstimmung mit Windows verwenden, können Sie, da die Insider-Builds von Microsoft 365 Apps for Enterprise monatliche Kanalupdates wiedergeben, diese Builds frühzeitig mithilfe der halbjährlichen Enterprise-Kanal (Vorschau) überprüfen.

### <a name="supporting-management-tools"></a>Unterstützen der Verwaltungstools

We've also thought through how to make the deployment of updates seamless to you. Configuration Manager (Current Branch) is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.

[Bereitstellen von Windows 10-Updates mit Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)

[Verwalten von Microsoft 365 Apps for Enterprise mit Configuration Manager](https://docs.microsoft.com/mem/configmgr/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="overview-of-windows-and-office-channels"></a>Übersicht über Windows und Office-Kanäle

Windows 10 bietet drei Wartungskanäle:

- Das [**Windows-Insider-Programm**](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider) für Organisationen zum Testen und für Feedback zu Features, die im nächsten Featureupdate veröffentlicht werden.
- Der **halbjährliche Kanal** bietet zwei Mal pro Jahr neue Funktionen mit neuen Featureupdates.
- Der **langfristige Wartungskanal** wurde nur für spezielle Geräte entwickelt, die eine längere Wartungsoption benötigen.

Microsoft 365 bietet vier Wartungskanäle:

- [**Office Insider-Programm** ](https://products.office.com/office-insider) für Organisationen zum Testen und für Feedback zu den neuesten Office-Features und Funktionen, die sich noch in der Entwicklung befinden.
- Der **aktuelle Kanal** stellt Benutzern die neuesten Funktionen von Office bereit, sobald diese verfügbar sind.
- Der **halbjährliche Enterprise-Kanal** bietet nur zwei Mal pro Jahr neue Funktionen mit neuen Features.
- Der **halbjährliche Enterprise-Kanal (Vorschau)** ist ein vollständig unterstützter Build von Office, mit dem Pilotbenutzer und Anwendungskompatibilitätstester den nächsten halbjährlichen Enterprise-Kanal testen und überprüfen können.

Ausführliche Informationen zu Windows- und Office-Wartungskanälen finden Sie in der folgenden Dokumentation:

- [Übersicht über Windows als Dienst](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels)
- [Übersicht über die Updatekanäle von Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC).

## <a name="phased-deployment-of-updates"></a>Phasenweise Bereitstellung von Updates

Now let’s shift gears to how you will roll out these updates. For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment. Once you’re up and running on Windows 10 and Microsoft 365 Apps for enterprise, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.

### <a name="monthly-updating"></a>Monatliche Updates

The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates. As mentioned, the cumulative nature of monthly updates means each will increase in size per month.

#### <a name="express-updates"></a>Express-Updates

Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly. In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.

[Erläuterung von Windows 10-Qualitätsupdates und das Ende von Deltaaktualisierungen](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

Windows Update for Business und Windows Server Update Services haben Express-Updates über einen langen Zeitraum unterstützt. Dieser Support wurde nun auf Microsoft Endpoint Configuration Manager (Current Branch) erweitert, sodass auch hier Express-Updates genutzt werden können.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a>Binäre Deltakomprimierung

Binary Delta Compression in Office wird nur verwendet, wenn Sie eine Aktualisierung von der neuesten Version von Microsoft 365 Apps for Enterprise ausführen. Verwenden Sie diesen Ansatz also, wenn Sie eine Aktualisierung vom vorherigen Build ausführen müssen und keine Updates überspringen können.

Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process. Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.

### <a name="semi-annual-updates"></a>Halbjährliche Updates

Da Sie nun die Überlegungen für monatliche Updates kennen, fahren wir mit den größeren, halbjährlichen Updates fort.

Wie bei der Geräte- und App-Bereitschaft behandelt, sollten Sie zur Vorbereitung auf diese größeren Updates die gleichen Bereitschaftstools verwenden, die in Schritt 1 des Bereitstellungsprozesses eingerichtet wurden.

As for tooling, you can use policy settings with Windows Update for Business, software update management via Microsoft Endpoint Configuration Manager (Current Branch), Windows Server Update Services (WSUS), or update policies set by Microsoft Intune. If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[Halbjährlicher Kanal in Windows](https://docs.microsoft.com/windows/deployment/update/waas-overview#semi-annual-channel)

[Halbjährlicher Enterprise-Kanal für Microsoft 365-Apps](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a>Aufgabensequenzen bei Upgrades

Das Installieren der größeren Featureupdates über standardmäßige Routinen der Softwareupdateverwaltung ist eine unterstützte Option, aber viele Organisationen verwenden lieber eine Upgradeaufgabensequenz mit Microsoft Endpoint Configuration Manager (Current Branch) oder das Microsoft Deployment Toolkit.

Mit einer Aufgabensequenz können Sie benutzerdefinierte Prüfungen oder Aufgaben VOR der Installation der Featureupdates erstellen und benutzerdefinierte Aufgaben ausführen, NACHDEM die Installation des Updates selbst abgeschlossen wurde – Aufgaben nach der Aktualisierung beinhalten möglicherweise das vorübergehende Aussetzen von Diensten, wenn dies während des Updates, der Treiberinstallation und des Treiberaustauschs, während Anwendungsupgrades oder Personalisierungseinstellungen für die Taskleiste und Windows 10-Start erforderlich ist.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control. While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences. One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade. This approach ensures that your user productivity is less impacted.

[Erstellen einer Aufgabensequenz für ein Betriebssystemupgrade in Configuration Manager](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a>Halbjährliche Kanalunterstützung für Featureupdates

[Wie im September 2018 angekündigt](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), wird für die Supportzeitskala für halbjährliche Kanalupdates das folgende Modell verwendet.

  - Alle derzeit unterstützten Featureupdates von Windows 10 Enterprise und Education werden ab Version 1607 30 Monate ab dem ursprünglichen Veröffentlichungsdatum unterstützt.

  - Alle zukünftigen Featureupdates (ab Version 1809) mit dem Ziel September werden 30 Monate ab dem Tag ihrer Veröffentlichung unterstützt.

  - Zukünftige Featuresupdates (ab Version 1903), die auf März abzielen, werden weiterhin 18 Monate ab dem Tag ihrer Veröffentlichung unterstützt.

  - Halbjährliche Updates für Microsoft 365 Apps for Enterprise weiterhin 18 Monate lang unterstützt.

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a>Weitere Setup-Automatisierungsoptionen außerhalb von Aufgabensequenzen

Wenn Sie keine Upgradeaufgabensequenzen verwenden, können Sie nun benutzerdefinierte Aktionen ausführen oder Treiberdateien während Featureupdates in der Phase vor der Installation anwenden – bevor Setup die Kompatibilitätsprüfungen ausführt – oder in der Phase vor dem Commit – bevor das Upgrade angewendet wird.

[Neuigkeiten im Windows 10-Setup, Version 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a>Nächster Schritt 

## <a name="step-8-user-communications-and-training"></a>[Schritt 8: Benutzerkommunikation und Schulung](https://aka.ms/mdd8)

## <a name="previous-step"></a>Vorheriger Schritt 

## <a name="step-6-os-deployment-and-feature-updates"></a>[Schritt 6: Bereitstellung des Betriebssystems und Featureupdates](https://aka.ms/mdd6)
