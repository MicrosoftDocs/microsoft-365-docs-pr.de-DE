---
title: Vorbereiten Ihrer Organisation auf Windows 10 Enterprise
description: Bietet eine ausführliche Anleitung zu den einzelnen Schritten, die im Rahmen von Microsoft 365 Enterprise für die Bereitstellung von Windows 10 Enterprise auf PCs nötig sind.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-Dokumentation, Windows 10 Enterprise, Bereitstellung
author: JoeDavies-MSFT
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: 21a4198c688e1865a029f18ff3ceeb2155d419e4
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868093"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>Schritt 1: Vorbereiten Ihrer Organisation auf Windows 10 Enterprise

*Dieser Abschnitt gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Beachten Sie vor dem Upgrade Ihrer Geräte auf Windows 10 Enterprise Folgendes:

- **Ihre Domänen müssen hinzugefügt und verifiziert werden** <br>Ein Abonnement von Microsoft 365 umfasst einen Standarddomänennamen, der auf „onmicrosoft.com“ endet (z. B. „contoso.onmicrosoft.com“). Die meisten Organisationen bevorzugen es jedoch, bereits vorhandene Domänen zu nutzen, sodass E-Mail-Adressen auf den eigenen Domänennamen enden (z. B. benutzername@contoso.com). Um Ihre eigene Domäne verwenden zu können, müssen Sie diese zu Microsoft 365 hinzufügen und nachweisen, dass Sie deren Besitzer sind. Wir empfehlen Ihnen, Ihre Domänen jetzt hinzuzufügen und zu bestätigen, sodass diese verfügbar sind, wenn Sie Microsoft 365-Dienste wie E-Mail und Skype for Business einrichten.
- **Sie müssen zu diesem Zeitpunkt noch keine Benutzer hinzufügen.** <br>Um Microsoft 365-Dienste nutzen oder Microsoft 365-Produkte installieren zu können, müssen die Benutzer über Microsoft 365-Konten und entsprechende Produktlizenzen verfügen. Wie Sie Benutzer zu Microsoft 365 hinzufügen, hängt von der Anzahl der Benutzer und davon ab, ob Sie derzeit ein lokales Active Directory einsetzten. Wenn Sie derzeit kein Active Directory nutzen (oder dieses nicht mit Microsoft 365 synchronisieren möchten), können Sie Benutzer direkt zu Microsoft 365 hinzufügen und Lizenzen entweder einzeln oder gruppiert zuweisen.<br>Wenn Sie ein lokales Active Directory einsetzen, können Sie [dieses mit Microsoft 365 synchronisieren](identity-azure-ad-connect-health.md), um Benutzerkonten in Azure AD zu erstellen, dem Cloudverzeichnis von Microsoft 365. Anhand dieser Methode können Sie Konten sowohl für Benutzer als auch für Sicherheitsgruppen erstellen, die Sie zur Verwaltung von Berechtigungen für Ressourcen einsetzen (wie SharePoint Online-Websitesammlungen oder -Dokumente). Durch die Synchronisierung Ihres Active Directory mit Microsoft 365 werden den Benutzern keine Lizenzen zugewiesen.
- **Sie müssen zu diesem Zeitpunkt noch keine Benutzerlizenzen vergeben.** <br>Damit die Benutzer Microsoft 365-Dienste nutzen oder Software vom Microsoft 365-Portal installieren können, benötigen sie Produktlizenzen. Als globaler Administrator oder Benutzerverwaltungsadministrator können Sie einzelne oder gruppierte Produktlizenzen direkt in Microsoft 365 vergeben. Zudem können Sie [die Gruppenlizenzierung](identity-group-based-licensing.md) nutzen, die Benutzern automatisch eine Lizenz zuweist, wenn diese einer bestimmten Gruppe hinzugefügt werden. 
- **Sie installieren Office 365 ProPlus separat** <br>Beim Erwerb einer Microsoft 365-Lizenz wird Office 365 ProPlus nicht automatisch auf den Clientcomputern installiert. Weitere Einzelheiten finden Sie unter [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md). 

## <a name="set-windows-diagnostics-data-level"></a>Windows-Diagnose Datenebene festlegen

Microsoft verwendet Diagnosedaten, um Windows-Geräte zu schützen, indem Malwaretrends und andere Bedrohungen identifiziert werden, und unterstützt uns zudem dabei, die Qualität von Windows- und Microsoft-Diensten zu verbessern. Sie müssen sicherstellen, dass die Standardstufe des Diagnosediensts an allen Endpunkten in Ihrer Organisation aktiviert ist. *Dieser Dienst ist standardmäßig aktiviert und auf „Erweitert“ eingestellt.* Es empfiehlt sich jedoch zu überprüfen und sicherzustellen, dass Sensordaten empfangen werden. Nehmen Richtlinien die Einstellungen von Stufen vor, werden die Einstellungen auf Geräteebene überschrieben. 

**Windows 10-Betriebssystem-Diagnosedatenebenen**

Sie können die Standardeinstellungen des Betriebssystems Diagnosedaten mithilfe der Verwaltungstools verwenden, die Sie bereits, die wie Gruppenrichtlinien, MDM oder Bereitstellen von Windows verwenden konfigurieren. Sie können die Einstellungen mit dem Registrierungs-Editor auch manuell ändern. Festlegen der Diagnosedaten Level durch eine Richtlinie zur Verwaltung überschreibt alle geräteeinstellungen auf Poolebene.

Verwenden Sie den entsprechenden Wert in der nachfolgenden Tabelle, wenn Sie die Verwaltungsrichtlinie konfigurieren.

| Ebene | Gesammelte Daten | Wert |
|:--- |:--- |:--- |
| Sicherheit | Nur Sicherheitsdaten. | 0 |
| Standard | Sicherheitsdaten sowie grundlegende System- und Qualitätsdaten. | 1  |
| Erweitert | Sicherheitsdaten, grundlegende System- und Qualitätsdaten, erweiterte Einblicke sowie erweiterte Zuverlässigkeitsdaten. | 2  |
| Vollständig | Sicherheitsdaten, grundlegende System- und Qualitätsdaten, erweiterte Einblicke und erweiterte Zuverlässigkeitsdaten sowie vollständige Diagnosedaten. | 3  |

Sie können die Diagnosedaten über eine der folgenden Methoden aktivieren:

* 
  **Microsoft Intune** – Wenn Sie beabsichtigen, Intune zur Verwaltung Ihrer Geräte einzusetzen, können Sie eine Konfigurationsrichtlinie zur Aktivierung von Diagnosedaten erstellen, indem Sie die Systemrichtlinie <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> konfigurieren. Weitere Einzelheiten zum Einrichten der Konfigurationsrichtlinie finden Sie unter [Verwalten von Einstellungen und Eigenschaften auf Ihren Geräten mit Microsoft Intune-Richtlinien](https://aka.ms/intuneconfigpolicies).
* **Registry-Editor** – Sie können den Registrierungs-Editor verwenden, um Diagnosedaten manuell auf jedem Gerät in Ihrer Organisation zu aktivieren. Alternativ können Sie ein Skript zur Bearbeitung der Registrierung programmieren. Wenn bereits eine Verwaltungsrichtlinie, wie z. B. eine Gruppenrichtlinie oder MDM, existiert, wird diese die Registrierungseinstellung überschreiben.
* **Gruppenrichtlinien** - Wenn Sie nicht vorhaben, Geräte in Intune registrieren, können Sie ein Gruppenrichtlinienobjekt verwenden, zu Ihrer Organisation Diagnosedaten Level festgelegt.
* **Eingabeaufforderung** – Sie können die Windows 10-Diagnosedaten und -dienste so einstellen, dass diese automatisch über die Eingabeaufforderung gestartet werden. Diese Methode eignet sich besonders, wenn Sie den Dienst auf einzelnen Geräten testen möchten. Ein automatisches Starten des Dienstes mittels dieser Eingabeaufforderung hat keine Konfiguration der Diagnosedatenebene zur Folge. Haben Sie anhand der Verwaltungstools noch keine Diagnosedatenebene konfiguriert, wird der Dienst auf der standardmäßigen Ebene „Erweitert“ ausgeführt.

Weitere Informationen zu Windows-Diagnosedaten und deren Aktivierung entsprechend der von Ihnen gewählten Methode finden Sie unter [Konfigurieren von Windows-Diagnosedaten in Ihrer Organisation](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization).

Als Zwischenprüfung können Sie sich die [Beendigungskriterien](windows10-exit-criteria.md#crit-windows10-step1) für diesen Schritt anschauen.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [Bereitstellen von Windows 10 Enterprise für vorhandene Geräte als direktes Upgrade](windows10-deploy-inplaceupgrade.md) |






