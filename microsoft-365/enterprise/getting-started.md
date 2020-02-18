---
title: Erste Schritte – Desktopbereitstellung
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
description: Einführung in den Desktopbereitstellungsprozess.
ms.openlocfilehash: 62d18f23df55783c8b1f0c01f9f803a1d4bca0f0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067488"
---
# <a name="getting-started---desktop-deployment"></a>Erste Schritte – Desktopbereitstellung

![](../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-2.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-1.png" alt="Getting Started" height="130" width="130" /></td>
<td><p><strong>Erste Schritte: Leitfaden zu Personen, Prozessen und Technologien</strong></p>
<p>Entdecken Sie die Vorteile von Windows 10 und Office 365 ProPlus, von wesentlichen Änderungen und Überlegungen im Vergleich zu früheren Bereitstellungen und von bewährten Methoden, um einen reibungslosen Übergang zu Windows 10 und Office 365 ProPlus sicherzustellen.</p></td>
<td><a href="https://aka.ms/ddev0" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-13.png" alt="Getting Started" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>In dieser Reihe werden die besten Methoden zur Verwendung vorhandener Tools erläutert, und Sie erhalten eine Einführung in neue Technologien, Dienste und Methoden, die durch die Cloud ermöglicht werden.  Den vollständigen Desktopbereitstellungsprozess finden Sie im [Desktopbereitstellungscenter](https://aka.ms/HowToShift).
>

Willkommen beim Desktopbereitstellungscenter, dem zentralen Ort für Informationen zur Planung und zum Übergang zu Windows 10 und Office 365 ProPlus. Dadurch können Sie von einem sicheren Arbeitsbereich sowie von der aktuellen Produktivität, Teamarbeit und Zusammenarbeit profitieren.

Wenn Sie schon länger keine neue Desktopumgebung bereitgestellt haben, können Sie sich über einen verbesserten Bereitstellungsprozess freuen. Die Herausforderung aus der Vergangenheit, z. B. Anwendungskompatibilität, sind heute weniger ein Problem. Neue Tools sowie Informationen aus der Cloud ermöglichen es Ihnen, schneller und effizienter voranzukommen als je zuvor.

In dieser Einführung wird veranschaulicht, was sich geändert hat, und Sie erhalten eine Demonstration des Rads der Desktopbereitstellung. Sie werden durch die empfohlenen Schritte für Ihren Umstieg auf Windows 10 und Office 365 ProPlus geführt, und Sie erfahren, wie Sie vorhandene Tools und Prozesse nutzen, aber gleichzeitig eine moderne Verwaltungstechnologie und neue Ansätze einführen können.

## <a name="why-upgrade"></a>Warum Upgrade?

Durch Windows 10 in Kombination mit der Microsoft Intelligence Cloud können Sie Ihren Benutzern einen äußerst leistungsstarken und sicheren Arbeitsplatz bereitstellen und dabei gleichzeitig Ihre Supportinfrastruktur vereinfachen.

Einer der wichtigsten Mandanten der modernen Verwaltungsmethoden sind Geräte, die immer auf dem neuesten Stand sind. Diese Reihe enthält Informationen zu neuen Funktionen, die für einen einfacheren Wechsel zu Windows 10 und Office 365 ProPlus bereitgestellt wurden, damit Sie immer die aktuelle halbjährliche Version für beide nutzen können.

[Windows 10 für IT-Experten](https://www.microsoft.com/itpro/windows-10)

[Informationen zu Office 365 ProPlus im Unternehmen](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)

## <a name="what-has-changed"></a>Was wurde geändert?

Sehen wir uns zunächst an, was sich seit Ihrer letzten Desktopbereitstellung geändert und verbessert hat. Wenn Sie Ihre Desktopumgebung schon länger nicht mehr umgestellt haben, verwenden Sie wahrscheinlich Windows 7 und Office 2010 oder Office 2013. In diesem Fall werden Sie feststellen, dass sich seit Ihrem letzten größeren Upgrade einiges verändert hat. Nachfolgend finden Sie einige der wichtigsten Änderungen:

**Identität und Zugriff:** Windows 10 und Office 365 ProPlus verfügt in Verbindung mit Diensten für Cloudproduktivität, Sicherheit und Verwaltung über einen neuen Dienst für die Identitäts- und Zugriffsverwaltung: Azure Active Directory (Azure AD). Dies ermöglicht einmaliges Anmelden und sichere Verbindung zwischen Ihren Clouddiensten, das bedeutet Sie benötigen Azure AD, um von den Vorteilen von Microsoft 365-Diensten wie Office 365, Intune oder Windows Autopilot zu profitieren.

[Microsoft 365](https://www.microsoft.com/microsoft-365/default.aspx)

**Sichere Pre-Boot-Umgebung:** 64-Bit-UEFI-Firmware ersetzt das BIOS. Dies sorgt nicht nur für einen schnelleren Start, sondern ist auch erforderlich, um viele moderne Sicherheitsfunktionen in Windows 10 zu aktivieren. Obwohl Windows 10 unter BIOS ausgeführt werden kann, wird UEFI dringend empfohlen. Wenn Sie noch nicht vom BIOS zu UEFI gewechselt haben und eine 64-Bit-Version verwenden, ist es nun an der Zeit dies zu tun. Es gibt Tools, mit denen dieser Wechsel entweder während eines Upgrades auf Windows 10 oder danach erfolgen kann.

**Cloudbasierte Geräteverwaltung:** Dienste wie Microsoft Intune helfen Ihnen dabei, Windows 10-Geräte wie andere Mobilgeräte von einem zentralen Ort zu verwalten. Was Microsoft Intune einzigartig macht, ist die Möglichkeit, Windows 10-Geräte mit Microsoft Endpoint Configuration Manager gemeinsam zu verwalten. Sie können Configuration Manager verwenden, um zu Windows 10 zu wechseln und dann Microsoft Intune hinzuzufügen. Bei der Zusammenarbeit wird Microsoft Endpoint Configuration Manager zum intelligenten Edge in Ihrer Organisation, der mit der intelligenten Microsoft Cloud verbunden ist. Dadurch können Sie die Geräte Ihrer Benutzer sicher verwalten, egal, wo sie sich befinden und ob sie mit der Infrastruktur der Organisation verbunden oder mit der öffentlichen Cloud verbunden sind.

[Mitverwaltung für Windows 10-Geräte](https://docs.microsoft.com/configmgr/core/clients/manage/co-management-overview)

**Cloudbasierter Bereitstellungsdienst:** Wenn Sie neue PCs kaufen, wurde bei diesen ein neuer Clouddienst namens Windows Autopilot-Bereitstellungsdienst eingeführt, mit dem Sie Microsoft 365-Geräte verwalten können. Autopilot ist bei Hardwareanbietern integriert, und neue PCs werden automatisch in Autopilot registriert, sodass sie direkt an den Endbenutzer gesendet werden können. Wenn der Computer das erste Mal eingeschaltet wird, ist die gewünschte Konfiguration Ihrer Organisation schnell konfiguriert und an die Bedürfnisse des Benutzers angepasst.

[Windows Autopilot](https://www.microsoft.com/windowsforbusiness/windows-autopilot)

**Klick-und-Los-Bereitstellungen:** Bei der Bereitstellung von Office-Desktop-Apps ist Office 365 ProPlus die bevorzugte Option. Mit dieser Option erhalten Sie Zugriff auf die neuesten Innovationen in Office, sobald sie entwickelt sind, und müssen nicht Jahre lang warten, um neue Funktionen zu erhalten. Sie verwenden auch eine neue Installation, die als Klick-und-Los bezeichnet wird.

Klick-und-Los unterscheidet sich stark von den MSI-basierten Paketen in der Vergangenheit. Klick-und-Los ist schneller und einfacher und unterstützt die Aktualisierung im Hintergrund ohne Auswirkungen auf die Benutzer. Es ist weiterhin eine lokale Kopie von Office, und Sie können weiterhin für die Bereitstellung und Konfiguration der Apps Ihre vorhandenen Bereitstellungstools wie Microsoft Endpoint Configuration Manager verwenden.

[Bereitstellungshandbuch für Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus)

**Halbjährliche Updates:** Nach dem Umstieg auf Windows 10 und Office 365 ProPlus werden Updates mit neuen Funktionen halbjährlich bereitgestellt. Dank der Einblicke aus der Cloud von Microsoft können Sie diese Updates schnell und sicher für Hunderte oder Tausende von Geräten bereitstellen. Wie bei einem direkten Upgrade werden beim Featureupdate Apps, Daten und Konfigurationen aus der vorherigen Version beibehalten.

## <a name="the-deployment-process-wheel"></a>Der Bereitstellungsprozess

Bevor Sie beginnen, sollten Sie einen allgemeinen Plan erstellen und die erforderlichen Sponsoren ins Boot holen. Unser Bereitstellungsprozess beschreibt wichtige Schritte, anhand der Sie die wichtigsten Teammitglieder und Ressourcen in den folgenden Bereitstellungsbereichen verwalten können.

**[Schritt 1: Geräte- und App-Bereitschaft](https://aka.ms/mdd1)** Für eine erfolgreiche Bereitstellung müssen Sie zunächst wissen, was Sie haben. Das bedeutet, dass eine Bestandsaufnahme Ihrer Geräte und Apps und eine Überprüfung der Kompatibilität erforderlich ist. Zur Unterstützung können Sie dabei die Tools nutzen, die in unserem cloudbasierten Dienst, Desktop Analytics, verfügbar sind. Mit Desktop Analytics können Sie auf Kompatibilitätsintelligenz und Diagnosedaten von Hunderten von Millionen Computern zugreifen, um die auf Ihrem Gerät ausgeführten Apps und Treiber zu bewerten, damit Sie die Bereitschaft Ihres Desktops sicherstellen können. Sie können aus Desktop Analytics eine Liste der Computer, die für die Bereitstellung bereit sind, in Configuration Manager exportieren, wenn Sie es verwenden, sodass Sie datengesteuerte Sammlungen der entsprechenden Computer erstellen können, sobald diese bereit sind.

[Erste Schritte mit der Upgradebereitschaft](https://docs.microsoft.com/windows/deployment/upgrade/upgrade-readiness-get-started)

**[Schritt 2: Verzeichnis- und Netzwerkbereitschaft](https://aka.ms/mdd2) ** Wenn noch nicht geschehen, müssen Sie als Nächstes Azure Active Directory für die Identitäts- und Zugriffsverwaltung implementieren. Sie müssen auch das Netzwerk für die Verschiebung der Systemabbilder, Anwendungspakete, Benutzerdateien und Updates vorbereiten. Das bedeutet eine große Menge an zusätzlichen Daten; Ihr Netzwerk muss über die Kapazität für diese zusätzliche Auslastung verfügen, ohne dass sich dies auf die tägliche Arbeit Ihrer Organisation auswirkt. Es sind zahlreiche Netzwerkoptimierungen verfügbar, von Bandbreitendrosselungs- und Peer-to-Peer-Optionen bis hin zum dynamischen Aufräumen der Bandbreite und differenzieller Aktualisierung.

[Branch-Cache und Peer-Cache](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**[Schritt 3: Bereitstellung von Office und Branchen-Apps](https://aka.ms/mdd3)** Neben der Unterstützung von MSI-basierten Installationen bietet Windows nun auch Unterstützung für neue Installationsmechanismen, die für die automatisierte Bereitstellung und kontinuierliche Updates optimiert sind. Office 365 ProPlus und Office 2019-Clients verwenden die Klick-und-Los-Installationstechnologie. Möglicherweise möchten Sie neben zahlreichen UPW-Apps auch Drittanbieter-Apps und intern entwickelte Branchen-Apps bereitstellen, die die MSIX-basierten Verpackungs-Apps verwenden. In diesem Schritt wird sichergestellt, dass Ihre Apps für automatisierte Bereitstellungen bereit sind und dass sie erfolgreich bereitgestellt werden können, unabhängig davon, ob Apps mithilfe von Klick-und-Los, MSIX oder MSI-basiert bereitgestellt werden oder ob es sich dabei um UWP-Apps handelt, die über einen von Ihnen eingerichteten Microsoft Store bereitgestellt werden.

[Einführung in MSIX](https://blogs.msdn.microsoft.com/sgern/2018/06/15/msix-intro/)

**[Schritt 4: Migration von Benutzerdateien und -einstellungen](https://aka.ms/mdd4)** Dies ist bei jedem PC-Austausch oder Aktualisierungszyklus ein entscheidender Schritt: Sie müssen sicherstellen, dass die Dateien, Daten und Einstellungen von Benutzern erfolgreich verschoben und bei der Migration beibehalten werden. Dieser Schritt enthält die verfügbaren Optionen für manuelle oder automatisierte Migrationen, einschließlich bekannter und neuer Optionen.

Wie in vorherigen Upgrades ist das Migrationstool für den Benutzerstatus (USMT) weiterhin hilfreich, um diesen Prozess zu automatisieren, und bleibt ein wesentlicher Bestandteil der Migrationen, die mit Microsoft Endpoint Configuration Manager oder dem Microsoft Deployment Toolkit koordiniert werden. Das Verschieben all dieser Daten bei der Migration kann jedoch einen zeitlichen Engpass für den PC-Austausch bedeuten, da Hunderte von Gigabyte pro Computer zwei mal übertragen werden müssen, erst vom vorhandenen Desktop und dann auf den neuen Desktop. Eine neue Option von OneDrive ist die Verschiebung bekannter Ordner, die zum Synchronisieren von Benutzerdokumenten, Bildern und Desktopdateien, in der Cloud und vor der Bereitstellung verwendet wird.

[Umleiten und Verschieben von bekannten Windows-Ordnern in OneDrive](https://docs.microsoft.com/onedrive/redirect-known-folders)

**[Schritt 5: Sicherheit und Compliance](https://aka.ms/mdd5)** Sicherheit und Compliance ist ein Bereich, der beim Umstieg auf Windows 10 und Office 365 ProPlus viele Vorteile bietet. Es ist wichtig, dass Sie sich mit den neuen integrierten Funktionen vertraut machen und diese mit den bereits vorhandenen Funktionen vergleichen. Neue Funktionen in Windows 10, die eine virtualisierungsbasierte Sicherheit bieten, können beispielsweise den Diebstahl von Anmeldeinformationen verhindern, Schutz vor browserbasierten Angriffen bieten und das Ausführen von bösartigem Code verhindern, indem Kernprozesse und Geheimnisse vom Betriebssystem isoliert werden. Außerdem erhalten Sie durch Clouddienste wie Advanced Threat Protection eine einheitliche Plattform für die Absicherung, die Erkennung nach einer Sicherheitsverletzung, die Überprüfung und die Reaktion. Advanced Threat Protection bietet auch Schutz vor bösartigen E-Mail-Anlagen, nicht sicheren Hyperlinks usw.

[Microsoft-Sicherheit](https://www.microsoft.com/security/default.aspx)

**[Schritt 6: Bereitstellung des Betriebssystems und Featureupdates](https://aka.ms/mdd6)** Wenn alles vorbereitet ist, besteht der nächste Schritt darin, die Betriebssystemabbilder bereitzustellen. Ein Großteil der Arbeit kann mithilfe der Aufgabensequenzen und der Infrastruktur von System Center Configuration Manager erledigt werden. Der empfohlene Ansatz besteht in einer stufenweisen Bereitstellung, bei der Sie sich zuerst auf eine Gruppe von „Early Adoptern“ konzentrieren, die einen repräsentativen Satz von Hardware und Apps verwenden. Sie können dann die Daten von diesen Geräten und Benutzern verwenden, um sich schrittweise immer mehr PCs vorzunehmen.

[Einführung in die Betriebssystembereitstellung in Configuration Manager](https://docs.microsoft.com/configmgr/osd/understand/introduction-to-operating-system-deployment)

**[Schritt 7: Windows und Office-as-a-Service](https://aka.ms/mdd7)** Dies steht für eine bedeutende Änderung in der Weise, wie Desktops verwaltet werden. Mit diesem Umstieg auf Windows 10 und Office 365 ProPlus können Sie zur Windows und Office-as-a-Service-Verwaltung wechseln. Anstelle eines großen Technologiewechsel alle paar Jahre können Sie Benutzern kontinuierlich neue Funktionen, Erfahrungen und Schutzfunktionen bereitstellen. Halbjährliche Featureupdates liefern neue Funktionen im Herbst und Frühling eines jeden Jahres, während monatliche kumulative Updates weiterhin Sicherheit, Zuverlässigkeit und Fehlerbehebungen enthalten. Sie können zwar den Office 2019-Client bereitstellen, es wird jedoch dringend ein Wechsel zu Office 365 ProPlus empfohlen. Dies folgt einem ähnlichen Serviceplan wie Windows, sodass Benutzer Updates für die Office-Apps in regelmäßigen Abständen erhalten.

![](../media/getting-started-media/getting-started-media-2.png)

[Übersicht über Windows-as-a-Service](https://docs.microsoft.com/windows/deployment/update/waas-overview)
[Übersicht über Office-as-a-Service](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

**[Schritt 8: Benutzerkommunikation und Schulung](https://aka.ms/mdd8) ** Dieser letzte Schritt ist entscheidend für die Verwendung der neuen Funktionen zur Verbesserung der Zusammenarbeit, Kommunikation, Sicherheit und mehr. Vor der allgemeinen Bereitstellung für reguläre Benutzer wird ein Rollout der Benutzerkommunikation und Schulung empfohlen. Dadurch können die gewünschten Änderungen bei der Verwendung neuer Funktionen in Office, Windows oder anderen Branchen-Apps und Diensten bewirkt werden. Zur Unterstützung bieten wir kostenlose Schulungen über Microsoft FastTrack an. Außerdem haben wir kostenlose Beispielkommunikationspläne und Zeitachsen und Vorlagen für E-Mails, soziale Netzwerke und Intranet veröffentlicht, die Sie beim der Einführung von Windows 10 unterstützen sollen. Als Microsoft 365- oder Office 365-Organisation kann Ihre Organisation auch für direkte Unterstützung berechtigt sein.

## <a name="next-step"></a>Nächster Schritt

Nun kennen Sie die Neuerungen und Änderungen bei Windows 10 und Office 365 ProPlus und sind am Ende des empfohlenen Bereitstellungsprozesses angekommen. Mit dieser umfassenden Anleitung und den verfügbaren Tools, können Sie mit dem Umstieg auf Windows 10 und Office 365 ProPlus beginnen.

## <a name="step-1-device-and-app-readinesshttpsakamsmdd1"></a>[Schritt 1: Geräte- und App-Bereitschaft](https://aka.ms/mdd1)

