---
title: Bereitstellungscenter für Desktop
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 08/14/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Übersicht über das Bereitstellungscenter für den Desktop.
ms.openlocfilehash: 3559a32db71d2cceaf3ab4dc67701d5f5f00e7fe
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528108"
---
# <a name="desktop-deployment-center"></a>Bereitstellungscenter für modernen Desktop

<strong>Upgrade von Windows 7 zu Windows 10 </strong>
<p>Der erweiterte Support für Windows 7 endete am 14. Januar 2020. Ein direktes Upgrade von Windows 7 zu Windows 10 ist die schnellste Methode der Bereitstellung. Sie können <a href="https://docs.microsoft.com/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-manual">mit Microsoft Endpoint Configuration Manager ein Upgrade auf einem einzelnen PC</a> oder <a href="https://docs.microsoft.com/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-automated">Tausenden von PCs durchführen</a>. Sie müssen sich bei direkten Upgrades nicht auf die App-Bereitstellung, Dateimigration, benutzerdefinierte Imageerstellung oder Aktivierung von Cloud-basierten Diensten konzentrieren. Sie können Tools verwenden, die Sie bereits für das Upgraden vorhandener PCs besitzen, und sich auf die folgenden Bereitstellungsschritte für Upgrades konzentrieren: </p>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" width="36" height="36" alt="Upgrade ConfigMgr" /> | **[Upgrade von ConfigMgr zu Current Branch](https://docs.microsoft.com/microsoft-365/enterprise/step-2-directory-and-network-readiness)** <p>Teil der Verzeichnis- und Netzwerkbereitschaft für Organisationen, die Configuration Manager verwenden</p> | <img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" width="36" height="36" alt="Device and App Readiness" /> | **[Validieren der Geräte- und App-Bereitschaft](/microsoft-365/enterprise/step-1-device-and-app-readiness)** <p>Teil der Geräte- und App-Bereitschaft; Hilfe ist über Desktop App Assure verfügbar</p> | <img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-9.png" width="36" height="36" alt="Upgrade Windows 7 PCs" /> | **[Upgrade von PCs mit Windows 7 zu Windows 10](/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-automated)** <p>Teil der Geräte- und App-Bereitschaft; Hilfe ist über Desktop App Assure verfügbar</p> |

<img align="middle" src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-2.png" alt="Desktop Deployment Wheel" height="450" width="802" align="middle" style="background-color: #fff;" />


Führen Sie die folgenden Schritte aus, um eine umfangreiche Bereitstellung für Windows 10 und Microsoft 365 Apps for Enterprise zu planen und durchzuführen. Jeder der nachfolgenden Schritte ist Teil des allgemeinen Planungs- und Bereitstellungsprozesses, bei dem typischerweise in einer stufenweisen Bereitstellung mehrere Schritte parallel ausgeführt werden. Laden Sie das kostenlose [Lab-Kit für die Desktop-Bereitstellung und -Verwaltung](https://aka.ms/howtoshiftlabs) herunter, um eine praktische Schulung zu den Tools zu erhalten, die im Bereitstellungsprozess besonders wichtig sind. [Hilfe](https://aka.ms/mddhelp) bei Ihrer Desktop-Bereitstellung erhalten Sie außerdem von Microsoft-Partnern und FastTrack-Diensten.

<br>

<table>
<tr class="even">
<td><a href="https://aka.ms/mdd0"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-1.png" alt="Getting Started" height="144" width="144" /></a></td>
<td><p><strong><a href="https://aka.ms/mdd0">Erste Schritte: Leitfaden zu Personen, Prozessen und Technologien</a></strong></p>
<p>Entdecken Sie die Vorteile von einem Wechsel zu Windows 10 und Microsoft 365 Apps for Enterprise, wesentliche Änderungen und Überlegungen im Vergleich zu früheren Bereitstellungen und bewährte Methoden, um einen reibungslosen Übergang zu Windows 10 und Microsoft 365 Apps for Enterprise sicherzustellen.</p></td>
<td><a href="https://aka.ms/ddev0" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-13.png" alt="Getting Started" height="130" width="231" /></a></td>
</tr>
<tbody>
<tr class="odd">
<td><a href="https://aka.ms/mdd1"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="144" width="144" /></a></td>
<td><p><strong><a href="https://aka.ms/mdd1">Schritt 1: Geräte- und App-Bereitschaft</a></strong></p>
<p>Beginnen Sie Ihre Desktopbereitstellung mit einer Bestandsaufnahme Ihrer Geräte und Apps, priorisieren Sie, was Sie für Ihre weitere Arbeit benötigen, testen Sie priorisierte Apps und Geräte, und beheben Sie dann ggf. Probleme, um sich auf die Bereitstellung vorzubereiten.</p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><a href="https://aka.ms/mdd2"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></a></td>
<td><p><strong><a href="https://aka.ms/mdd2">Schritt 2: Verzeichnis- und Netzwerkbereitschaft</a></strong></p>
<p>Mit der Cloud verbundene Dienste in Microsoft 365 Apps for Enterprise und neue Bereitstellungsoptionen wie Windows Autopilot erfordern Azure Active Directory. Netzwerk und Konnektivität sind auch wichtige Bereiche, die beim Verschieben von Windows-Images, Apps, Treibern und zugehörigen Dateien auf Ihre Computer geplant werden müssen. Erfahren Sie, wie Sie mit neuen Tools und Bereitstellungsoptionen den Netzwerkverkehr reduzieren und optimieren können.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><a href="https://aka.ms/mdd3"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="144" width="144" /></a></td>
<td><p><strong><a href="https://aka.ms/mdd3">Schritt 3: Liefern von Office- und Branchen-Apps</a></strong></p>
<p>Stellen Sie sicher, dass Ihre Apps für eine automatische Installation verpackt und bereit sind. Erfahren Sie, wie Sie durch eine Klick-und-Los-Verpackung mit Microsoft 365 Apps for Enterprise neue Optionen erhalten, um Ihre Office-Apps zu konfigurieren, zu liefern und auf dem neuesten Stand zu halten.</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><a href="https://aka.ms/mdd4"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-7.png" alt="Step 4" height="144" width="144" /></a></td>
<td><p><strong><a href="https://aka.ms/mdd4">Schritt 4: Benutzerdateien und -einstellungen</a></strong></p>
<p>Wenn Computer aktualisiert oder ersetzt werden, können Sie Zeit sparen, indem Sie das Sichern und Wiederherstellen des Benutzerstatus automatisieren. Mit neuen Optionen für die Synchronisierung von Clouddateien können Sie die Synchronisierung von Desktop-, Dokument- und Bildordnern mit OneDrive pro Benutzer erzwingen, sodass ein nahtloser Dateizugriff von neuen Windows-Installationen aus gewährleistet ist.</p></td>
<td><a href="https://aka.ms/ddev4" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-17.png" alt="Step 4" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><a href="https://aka.ms/mdd5"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-8.png" alt="Step 5" height="144" width="144" /></a></td>
<td><p><strong><a href="https://aka.ms/mdd5">Schritt 5: Überlegungen zu Sicherheit und Compliance</a></strong></p>
<p>Windows 10 und Microsoft 365 Apps for Enterprise bieten neue Methoden zum Schützen Ihrer Daten, Geräte und Benutzer und zum schnellen Erkennen von und Reagieren auf Bedrohungen. Darüber hinaus erfahren Sie, wie allgemeine Probleme im Zusammenhang mit Datenträgerverschlüsselung, Antischadsoftware-Apps und Richtlinien für den Umstieg auf Windows 10 behandelt werden.</p></td>
<td><a href="https://aka.ms/ddev5" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-18.png" alt="Step 5" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><a href="https://aka.ms/mdd6"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-9.png" alt="Step 6" height="144" width="144" /></a></td>
<td><p><strong><a href="https://aka.ms/mdd6">Schritt 6: Bereitstellung des Betriebssystems und Featureupdates</a></strong></p>
<p>Eine Bereitstellung basierend auf einer Aufgabenfolge wird zum Automatisieren von umfangreichen und stufenweisen Bereitstellungen für Bare-Metal-Installationen, Computeraktualisierungen und eines Computeraustauschs verwendet. Mithilfe von Aktualisierungsaufgabenfolgen können Sie im Hinblick auf größere halbjährliche Updates auf dem Laufenden bleiben. Windows Autopilot ist eine neue Ergänzung, durch die der das Imaging neuer und vorhandener Geräte modernisiert wird.</p></td>
<td><a href="https://aka.ms/ddev6" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-19.png" alt="Step 6" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><a href="https://aka.ms/mdd7"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></a></td>
<td><p><strong><a href="https://aka.ms/mdd7">Schritt 7: Windows und Office als Dienst</a></strong></p>
<p>Sowohl für Windows 10 als auch für Microsoft 365 Apps for Enterprise werden ständig neue Funktionen hinzugefügt, um die Benutzeroberfläche und die Sicherheit mit den neuesten Innovationen nach vorne zu bringen. Erfahren Sie, wie Sie mit halbjährlichen und monatlichen Updates auf dem neusten Stand bleiben, wie das neue Wartungsmodell funktioniert und welche Funktionen und Optionen Ihnen zur Verfügung stehen.</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><a href="https://aka.ms/mdd8"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-11.png" alt="Step 8" height="144" width="144" /></a></td>
<td><p><strong><a href="https://aka.ms/mdd8">Schritt 8: Benutzerkommunikation und Schulung</a></strong></p>
<p>Stellen Sie sicher, dass Ihre Benutzer über neue Oberflächen und neue Arbeitsmethoden informiert sind, wenn Sie Ihre Computer auf Windows 10 und Microsoft 365 Apps for Enterprise umstellen. Erfahren Sie, wie Sie mit Microsoft FastTrack, Schulungsmaterialien und Kommunikationsvorlagen die Akzeptanz beim Endbenutzer beschleunigen können, und lernen Sie neue Möglichkeiten zur Überwachung der Benutzerakzeptanz und -verwendung kennen.</p></td>
<td><a href="https://aka.ms/ddev8" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-21.png" alt="Step 8" height="130" width="231" /></a></td>
</tr>
</tbody>
</table>
