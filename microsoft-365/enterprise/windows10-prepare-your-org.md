---
title: Vorbereiten Ihrer Organisation auf Windows 10 Enterprise
description: Bietet eine ausführliche Anleitung zu den einzelnen Schritten, die im Rahmen von Microsoft 365 Enterprise für die Bereitstellung von Windows 10 Enterprise auf PCs nötig sind.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-Dokumentation, Windows 10 Enterprise, Bereitstellung
author: JoeDavies-MSFT
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
f1.keywords:
- NOCSH
ms.author: josephd
ms.openlocfilehash: 43793a1780542b1825c693030dd9d4dbff4ee3d7
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002343"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>Schritt 1: Vorbereiten Ihrer Organisation auf Windows 10 Enterprise

*Dieser Abschnitt gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![Phase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Beachten Sie vor dem Upgrade Ihrer Geräte auf Windows 10 Enterprise Folgendes:

- **Ihre Domänen müssen hinzugefügt und verifiziert werden** <br>Ein Abonnement von Microsoft 365 umfasst einen Standarddomänennamen, der auf „onmicrosoft.com“ endet (z. B. „contoso.onmicrosoft.com“). Die meisten Organisationen bevorzugen es jedoch, bereits vorhandene Domänen zu nutzen, sodass E-Mail-Adressen auf den eigenen Domänennamen enden (z. B. benutzername@contoso.com). Um Ihre eigene Domäne verwenden zu können, müssen Sie diese zu Microsoft 365 hinzufügen und nachweisen, dass Sie deren Besitzer sind. Wir empfehlen Ihnen, Ihre Domänen jetzt hinzuzufügen und zu bestätigen, sodass diese verfügbar sind, wenn Sie Microsoft 365-Dienste wie E-Mail und Skype for Business einrichten.
- **Sie müssen zu diesem Zeitpunkt noch keine Benutzer hinzufügen.** <br>Um Microsoft 365-Dienste nutzen oder Microsoft 365-Produkte installieren zu können, müssen die Benutzer über Microsoft 365-Konten und entsprechende Produktlizenzen verfügen. Wie Sie Benutzer zu Microsoft 365 hinzufügen, hängt von der Anzahl der Benutzer und davon ab, ob Sie derzeit ein lokales Active Directory einsetzten. Wenn Sie derzeit kein Active Directory nutzen (oder dieses nicht mit Microsoft 365 synchronisieren möchten), können Sie Benutzer direkt zu Microsoft 365 hinzufügen und Lizenzen entweder einzeln oder gruppiert zuweisen.<br>Wenn Sie ein lokales Active Directory einsetzen, können Sie [dieses mit Microsoft 365 synchronisieren](identity-add-user-accounts.md#identity-sync), um Benutzerkonten in Azure AD zu erstellen, dem Cloudverzeichnis von Microsoft 365. Anhand dieser Methode können Sie Konten sowohl für Benutzer als auch für Sicherheitsgruppen erstellen, die Sie zur Verwaltung von Berechtigungen für Ressourcen einsetzen (wie SharePoint Online-Websitesammlungen oder -Dokumente). Durch die Synchronisierung Ihres Active Directory mit Microsoft 365 werden den Benutzern keine Lizenzen zugewiesen.
- **Sie müssen zu diesem Zeitpunkt noch keine Benutzerlizenzen vergeben.** <br>Damit die Benutzer Microsoft 365-Dienste nutzen oder Software vom Microsoft 365-Portal installieren können, benötigen sie Produktlizenzen. Als globaler Administrator oder Benutzerverwaltungsadministrator können Sie einzelne oder gruppierte Produktlizenzen direkt in Microsoft 365 vergeben. Zudem können Sie [die Gruppenlizenzierung](identity-use-group-management.md#identity-group-license) nutzen, die Benutzern automatisch eine Lizenz zuweist, wenn diese einer bestimmten Gruppe hinzugefügt werden. 
- **Sie installieren Microsoft 365-Apps für Enterprise separat.** <br>
  Beim Abrufen einer Microsoft 365-Lizenz werden Microsoft 365-Apps für Enterprise nicht automatisch auf Ihren Clientcomputern installiert. Weitere Informationen finden Sie unter [Phase 4: Microsoft 365 apps for Enterprise](office365proplus-infrastructure.md) . 

## <a name="set-windows-diagnostics-data-level"></a>Windows-Diagnosedaten Ebene festlegen

Microsoft verwendet Diagnosedaten, um die Sicherheit von Windows-Geräten zu schützen, indem Sie Malware Trends und andere Bedrohungen erkennen und uns dabei helfen, die Qualität von Windows und Microsoft-Diensten zu verbessern. Sie müssen sicherstellen, dass der Diagnosedienst auf mindestens einer grundlegenden Ebene auf allen Endpunkten in Ihrer Organisation aktiviert ist. *Dieser Dienst ist standardmäßig aktiviert und wird auf die erweiterte Ebene festgelegt.* Es empfiehlt sich jedoch, zu überprüfen und sicherzustellen, dass Sie Sensordaten empfangen. Das Festlegen von Ebenen über Richtlinien setzt Einstellungen auf Geräteebene außer Kraft. 

**Windows 10-Diagnosedaten Ebenen für das Betriebssystem**

Sie können die Einstellungen für die Diagnosedaten Ihres Betriebssystems mit den Verwaltungstools konfigurieren, die Sie bereits verwenden, wie etwa Gruppenrichtlinien, MDM oder Windows-profundierung. Sie können Ihre Einstellungen auch manuell mithilfe des Registrierungs-Editors ändern. Das Festlegen der Diagnosedaten Ebenen über eine Verwaltungsrichtlinie setzt alle Einstellungen auf Geräteebene außer Kraft.

Verwenden Sie den entsprechenden Wert in der Tabelle unten, wenn Sie die Verwaltungsrichtlinie konfigurieren.

| Ebene | Gesammelte Daten | Wert |
|:--- |:--- |:--- |
| Sicherheit | Nur Sicherheitsdaten. | 0 |
| Basic | Sicherheitsdaten und grundlegende System-und Qualitätsdaten. | 1 |
| Verbesserte | Sicherheitsdaten, grundlegende System-und Qualitätsdaten sowie erweiterte Einblicke und erweiterte Zuverlässigkeitsdaten. | 2 |
| Vollständig | Sicherheitsdaten, grundlegende System-und Qualitätsdaten, erweiterte Einblicke und erweiterte Zuverlässigkeitsdaten sowie vollständige Diagnosedaten. | 3 |

Sie können Diagnosedaten mit einer der folgenden Methoden aktivieren:

* **Microsoft InTune** -Wenn Sie die Verwendung von InTune zum Verwalten Ihrer Geräte planen, können Sie eine Konfigurationsrichtlinie zum Aktivieren von Diagnosedaten erstellen, indem Sie die <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> -Systemrichtlinie konfigurieren.
* **Registrierungs-Editor** : Sie können den Registrierungs-Editor verwenden, um Diagnosedaten auf jedem Gerät in Ihrer Organisation manuell zu aktivieren. Alternativ können Sie ein Skript zum Bearbeiten der Registrierung schreiben. Wenn bereits eine Verwaltungsrichtlinie vorhanden ist, wie etwa Gruppenrichtlinien oder MDM, wird diese Registrierungseinstellung außer Kraft gesetzt.
* **Gruppenrichtlinien** -Wenn Sie keine Geräte in InTune registrieren möchten, können Sie ein Gruppenrichtlinienobjekt verwenden, um die Diagnosedaten Ebene Ihrer Organisation festzulegen.
* **Eingabeaufforderung** -Sie können Windows 10 Diagnostics-Daten und-Dienst so festlegen, dass Sie automatisch mit der Eingabeaufforderung gestartet werden. Diese Methode ist am besten geeignet, wenn Sie den Dienst nur auf einigen Geräten testen. Wenn der Dienst automatisch mit diesem Befehl gestartet werden kann, wird die Diagnosedaten Ebene nicht konfiguriert. Wenn Sie keine Diagnosedaten Ebene mithilfe von Verwaltungstools konfiguriert haben, wird der Dienst mit der standardmäßigen erweiterten Stufe ausgeführt.

Weitere Informationen zu Windows-Diagnosedaten und dazu, wie Sie Sie basierend auf der ausgewählten Methode aktivieren können, finden Sie unter [Konfigurieren von Windows-Diagnosedaten in Ihrer Organisation](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) .

Als Zwischenprüfung können Sie sich die [Beendigungskriterien](windows10-exit-criteria.md#crit-windows10-step1) für diesen Schritt anschauen.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![Schritt 2](../media/stepnumbers/Step2.png)| [Bereitstellen von Windows 10 Enterprise für vorhandene Geräte als direktes Upgrade](windows10-deploy-inplaceupgrade.md) |






