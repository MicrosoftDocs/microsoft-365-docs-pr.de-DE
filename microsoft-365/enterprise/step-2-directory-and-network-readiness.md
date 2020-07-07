---
title: 'Schritt 2: Verzeichnis- und Netzwerkbereitschaft'
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen dazu, wie Sie die Verzeichnis- und Netzwerkbereitschaft in der Umgebung bewerten.
ms.openlocfilehash: 78087b7e0c1cb7031954d3a9ac4188b59879db20
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679014"
---
# <a name="step-2-directory-and-network-readiness"></a>Schritt 2: Verzeichnis- und Netzwerkbereitschaft

Ensure your directory and the network are configured and ready to support to your shift to Windows 10 and Microsoft 365 Apps for enterprise. This will require Azure Active Directory Services to be in place for users, and your network must have the capacity to handle both its regular traffic and the movement of potentially vast amounts of data as PCs are upgraded, and users’ files, settings and applications are restored.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong>Schritt 2: Verzeichnis- und Netzwerkbereitschaft</strong></p>
<p>Cloud connected services in Microsoft 365 Apps for enterprise and new deployment options like Windows Autopilot require Azure Active Directory. Your network and connectivity are also important areas to plan when moving Windows images, apps, drivers and related files to your PCs. Learn how new tools and deployment options reduce and streamline network traffic.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Die Verzeichnis- und Netzwerkbereitschaft ist der zweite Schritt in unserem empfohlenem Bereitstellungsprozess, der sich auf Azure Active Directory und die Netzwerkoptimierung konzentriert. Den vollständigen Desktopbereitstellungsprozess finden Sie im [Desktopbereitstellungscenter](https://aka.ms/HowToShift).
>

Directory and Network readiness is fundamental to ensuring a smooth OS and desktop deployment. As with any automated deployment, it is important to ensure your file shares can be reached, and your network will need to be able to support the transfer of very large files, possibly to hundreds or even thousands of PCs at a time.

With your shift to Windows 10 and Microsoft 365 Apps for enterprise you also now need to make sure that cloud-based identity is set up with Azure Active Directory. This is key not only to activating Microsoft 365 Apps for enterprise, it also allows you to take advantage of modern provisioning solutions like Windows Autopilot.

In diesem Artikel erfahren Sie mehr über die Tools und Optionen zum Vorbereiten der Verzeichnisdienste sowie Benutzer- und Geräteberechtigungen für die Bereitstellung in Windows 10 und Microsoft 365 Apps for Enterprise.

## <a name="adding-azure-active-directory"></a>Hinzufügen von Azure Active Directory

Wenn Ihre Organisation bereits Office 365, Exchange Online, Microsoft Intune oder andere Microsoft Online-Dienste verwendet, ist die gute Nachricht, dass Sie bereits Azure Active Directory verwenden. Wenn dies der Fall ist, müssen Sie nur sicherzustellen, dass die Benutzer, für die Sie die Desktopbereitstellung vornehmen möchten, in Ihrem Azure Active Directory vorhanden sind, und dass Lizenzen zugewiesen wurden.

Wenn Sie Azure Active Directory noch nicht verwenden, gibt es [zahlreiche Ressourcen](https://docs.microsoft.com/azure/active-directory/), die Ihnen bei der Einrichtung helfen. Sie sind möglicherweise zu persönlicher Unterstützung über Microsoft FastTrack berechtigt, als Teil Ihrer Lizenz. Weitere Informationen über Microsoft FastTrack erhalten Sie [hier](https://fasttrack.microsoft.com).

Sobald Sie Azure Active Directory eingerichtet haben, können sich die Benutzer anmelden und ihre Microsoft 365 Apps for Enterprise-Apps aktivieren, und Sie können die Microsoft Intune- oder Windows Autopilot-Bereitstellung für die automatisierte Bereitstellung von Apps und Richtlinien verwenden.

## <a name="network-readiness"></a>Netzwerkbereitschaft

Sie müssen bei der Planung der Bereitstellung die Anforderungen an die Netzwerkbandbreite berücksichtigen. Es gibt drei Hauptkomponenten in einer Bereitstellung, die sich auf das Netzwerk auswirken: PC-Imaging, Softwareupdates und Benutzerpersonalisierung. Zusammen können sie mehr als 20 GB pro PC für die anfängliche Migration beanspruchen sowie oft mindestens 1 GB pro Monat und PC, um den PC auf dem neuesten Stand zu halten.

Sehen wir uns zunächst die Anforderungen jeder einzelnen dieser drei Hauptkomponenten an:

### <a name="pc-imaging"></a>PC-Imageerstellung

Bei Windows-Images ohne Anpassungen sollten Sie in der Regel 3 GB pro PC einplanen, während Sie für angepasste Images mit Apps möglicherweise 6 GB oder mehr benötigen. Sie müssen möglicherweise auch Treiberpakete berücksichtigen. Diese können einige Hundert Megabyte pro PC, manchmal bis zu 1GB groß sein.

### <a name="software-updates"></a>Softwareupdates

Sie müssen nach Netzwerkbandbreite für Softwareupdates einplanen. Windows 10 und Microsoft 365 Apps for Enterprise verwenden ein neues Wartungsmodell mit monatlichen und halbjährlichen Updates. Wenn Sie mit diesem Modell noch nicht vertraut sind, erfahren Sie [hier](https://docs.microsoft.com/windows/deployment/update/waas-overview) mehr zu seiner Funktionsweise.

The new servicing model includes Feature Updates for Windows twice a year, Office Semi-Annual Enterprise Channel Updates, and monthly Quality Updates. Feature Updates are typically 2 – 4GB in size, and Office Semi-Annual Enterprise Channel updates are 300 – 400 MB per update. Then there are the monthly Quality Updates. These may range from a few hundred megabytes to over a gigabyte. This is because monthly updates are cumulative, so these increase in size over the servicing lifetime for each Windows 10 version. That said, there are tools that can help reduce the amount of data that must pass over the network to implement updates. We will cover this in more detail below.

### <a name="user-personalization"></a>Benutzerpersonalisierung

The third component to consider is user personalization. Here you need to plan network bandwidth to accommodate the restoring of user files, their settings, and their applications as part of the PC refresh or replacement process. Together, these items often exceed 20 GB per PC; for some users these may exceed 100 GB.

## <a name="limiting-bandwidth"></a>Beschränken der Bandbreite

One way to limit the impact of deployment-related traffic on the network is to throttle it using the BITS (Background Intelligent Transfer Service) setting on clients. BITS uses an Adaptive Bit Rate (ABR) to adjust bandwidth available for deployment purposes; it can be configured on clients using Group Policy.

[Informationen zu BITS](https://docs.microsoft.com/windows/desktop/bits/about-bits)

Wenn Sie Microsoft Endpoint Configuration Manager (Current Branch) verwenden, können Sie auch BITS-fähige Verteilungspunkte konfigurieren oder Multicast mit WDS aktivieren.

Throttling specific traffic means that normal network traffic is less impacted by PCs downloading updates and applications. But carving out a certain percentage of bandwidth for these tasks helps ensure productivity isn’t impacted by Windows or Office deployment and processes continue to run as needed, it can worsen deployment-related downtime, with users locked out of their PCs while a deployment runs.

Glücklicherweise gibt es neue Tools, die es Ihnen erleichtern, die Auswirkungen umfangreicher Desktopbereitstellung auf das Netzwerk zu verwalten, einschließlich LEDBAT zur Optimierung der Nutzung der verfügbaren Bandbreite sowie Peer-zu-Peer-Optionen (P2P), mit denen der Bereitstellungsverkehr vom Zentrum des Netzwerks an die Peripherie verlagert wird.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-3.png)

## <a name="scavenging-bandwidth"></a>Aufräumen der Bandbreite

LEDBAT (Low Extra Delay Background Transport), das in Windows Server 2019 and Microsoft Endpoint Configuration Manager (Current Branch) unterstützt wird, ist auf die Optimierung des Netzwerkdatenverkehrs für Windows-Clients ausgelegt.

[Top 10 Netzwerkfeatures in Windows Server 2019: \#9 LEDBAT – Latency Optimized Background Transport](https://blogs.technet.microsoft.com/networking/2018/07/25/ledbat/)

Unlike traditional throttling, LEDBAT can use all available network bandwidth as a background task, instantly yielding bandwidth when other traffic requests it. Unlike BITS there is no delay; everything is automated – no manual tuning or scheduling required, and everything is setup server side. This affords potentially massive performance gains.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-4.png)

## <a name="peer-to-peer-options"></a>Peer-zu-Peer-Optionen

Peer-to-Peer options are increasingly being used in Windows 10 migrations, for PC imaging, software updates and user personalization. They are also valuable in facilitating build-to-build upgrades after your initial Windows 10 deployment. Here we will cover several examples to help move Windows 10 and Office-related traffic away from the center of the network, reducing the need for classic throttling approaches, and allowing PCs to find the update files they need on peers in their local network rather than downloading them from a distribution point or the internet.

**BranchCache** can help you download content in distributed environments without saturating the network. It comes in two options: Hosted Cache Mode, which lets you use local servers to cache content, and Distributed Cache Mode (a mode supported in Configuration Manager), which lets clients share already downloaded content with each other.

**Peercache** Clients, die von Configuration Manager unterstützt werden, können darüber hinaus den Peercache verwenden. Dies ermöglicht PCs, die zuverlässig im Netzwerk verfügbar sind, Quellen für die Inhaltsverteilung zu hosten.  Sie sollten diese Option nicht für alle PCs aktivieren, sondern nur für Geräte mit einer zuverlässigen Netzwerkverbindung als Hosts (z. B. Desktop, Minitower- oder Tower-PCs). Der Peercache kann möglicherweise sogar für Bereitstellungsaufgaben funktionieren, die beim Setup in Windows PE-Phasen ausgeführt werden.

Hinweis: BranchCache and Peercache ergänzen sich und können zusammen in derselben Umgebung ausgeführt werden.

[Branch-Cache und Peer-Cache](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**Übermittlungsoptimierung** Die Übermittlungsoptimierung ist eine weitere Peer-zu-Peer Technologie für die Zwischenspeicherung, die auf dem Netzwerk basierende Steuerungen für Bereitstellungen bietet. Verwenden Sie die Windows 10-Übermittlungsoptimierung, um integrierte UWP-Apps zu aktualisieren und um Anwendungen aus dem Microsoft Store sowie Softwareupdates mit Express-Updates zu installieren. Sie ist seit den frühen Versionen von Windows 10 verfügbar, wurde jedoch erst kürzlich mit Microsoft Endpoint Configuration Manager (Current Branch) integriert. Seit Windows 10 Version 1803 bedeuten neue Konfigurationsoptionen, dass Sie jetzt unabhängig voneinander Bandbreitengrenzwerte für die Aktualisierung im Hintergrund und Vordergrundaufgaben wie das Installieren einer App aus dem Store festlegen können. Die Windows-Übermittlungsoptimierung unterstützt nun auch Microsoft 365 Apps for Enterprise bei Clientupdates, verfügbar in allen unterstützten Clientupdatekanälen. Unterstützung für Windows-Übermittlungsoptimierung bei der Erstinstallation von Clients ist in Kürze verfügbar.  

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-5.png)

**Zusätzliche Überlegungen zu Microsoft 365 Apps for Enterprise**

Zusätzlich zur Nutzung der Übermittlungsoptimierung finden Sie hier drei Elemente, die Ihnen helfen, Ihre Netzwerklast durch die Microsoft 365 Apps for Enterprise-Bereitstellungen zu reduzieren.

**Binary Delta Compression** Microsoft 365 Apps for enterprise uses Binary Delta Compression to reduce bandwidth consumed by software updates when updating from the most recent release of Microsoft 365 Apps for enterprise to the next release. By only pulling the binary level changes from the previous release, the impact from month-over-month growth of cumulative updates is minimized. This has the potential of saving several hundred megabytes of data, per PC, each month. In order to use this capability though, you cannot skip releases. If you do, then the full cumulative update must be downloaded.

[Herunterladen von Updates für Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-process-microsoft-365-apps#download-the-updates-for-microsoft-365-apps)

**Outlook-Datendateien** Outlook wird oft so konfiguriert, dass es das gesamte Postfach der Benutzer für die Offlineverwendung lokal zwischenspeichert. Dies gilt für alle Windows-Bereitstellungen, mit Ausnahme direkter Upgrades. Diese erfordern, dass sich die Outlook-Datendateien der Benutzer nach dem Upgrade selbst neu erstellen. Dies ist ein automatisierter Prozess, aber bei den Outlook-Postfachbeschränkungen, die normalerweise auf maximal 100 GB festgelegt sind, bedeutet das erneute lokale Zwischenspeichern des gesamten Postfachs für alle Benutzer eine Menge Datentransfer. Zum Reduzieren der Netzwerklast können Sie beispielsweise die Gruppenrichtlinie verwenden, um die Einstellung für "E-Mail im Offlinemodus" zu verringern. In Microsoft 365 Apps for Enterprise oder Office 2016 ist der Standardwert für Outlook auf 12 Monate festgelegt. Um die Auswirkungen auf das Netzwerk zu reduzieren, sollten Sie für den Offlinecache eine Dauer von 1 bis 6 Monaten festlegen. Das Ändern dieser Einstellung hat keinen Einfluss auf die Größe des Onlinepostfachs, und das gesamte Postfach kann weiterhin über Outlook durchsucht werden, wenn es online ist.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-6.png)

**OneDrive-Dateien bei Bedarf und Verschieben von bekannten Ordnern** OneDrive ist eine hervorragende Möglichkeit zum Synchronisieren und Schützen von Benutzerdateien auf PCs und anderen Geräten in der Cloud. Mit der Option zum Verschieben von bekannten Ordnern können Sie die Synchronisierung von Dateien aus den Ordnern "Desktop", "Dokumente" und "Bilder" in OneDrive erzwingen, sodass diese Dateien zur Verfügung stehen, wenn der Benutzer sich bei einem neuen Gerät oder auf einem PC mit neuem Image anmeldet. Beachten Sie jedoch, dass Sie aufgrund der umfangreichen Größe an Dateien, die in den Ordnern "Desktop", "Dokumente" und "Bilder" gespeichert sind, das Rollout von Richtlinien, die OneDrive auf den PCs aktivieren und erzwingen, genau planen müssen. Eine Option besteht darin, die Gruppenrichtlinie-Netzwerksteuerungen zu verwenden, um die von OneDrive-Synchronisierungsdienst verwendete Bandbreite zu drosseln.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-7.png)

[Einrichten der Verschiebung bekannter Ordner](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/Migrate-Your-Files-to-OneDrive-Easily-with-Known-Folder-Move/ba-p/207076)

[OneDrive-Dateien nach Bedarf](https://www.microsoft.com/microsoft-365/blog/2017/05/11/introducing-onedrive-files-on-demand-and-additional-features-making-it-easier-to-access-and-share-files/)

Wenn Sie OneDrive noch nicht bereitgestellt haben, ist der Übergang von Windows 7 zu Windows 10 eine gute Gelegenheit, um OneDrive zu aktivieren, und es kann problemlos in Microsoft 365 Apps for Enterprise integriert werden. Ziehen Sie den Beginn dieses Rollouts in Betracht, wenn Sie die App- und Gerätebereitschaft bearbeiten. Hierdurch erhalten Sie bei der Dateisynchronisierung einen Vorsprung, bevor Sie mit dem Verschieben von Windows-Images und dem Bereitstellen von Apps über das Netzwerk beginnen.

## <a name="next-step"></a>Nächster Schritt 

## <a name="step-3-office-and-lob-app-delivery"></a>[Schritt 3: Liefern von Office- und Branchen-Apps](https://aka.ms/mdd3)

## <a name="previous-step"></a>Vorheriger Schritt:

## <a name="step-1-device-and-app-readiness"></a>[Schritt 1: Geräte- und App-Bereitschaft](https://aka.ms/mdd1)

## <a name="feedback"></a>Feedback

We'd love to hear your thoughts. Choose the type you'd like to provide:

Feedback zu Produkten – Melden Sie sich an, um Feedback zur Dokumentation zu geben

Our new feedback system is built on GitHub Issues. Read about this change in our blog post.
