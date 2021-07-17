---
title: Microsoft Managed Desktop und Windows 11
description: Wie und wann Windows 11 im Dienst verfügbar ist
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1c5f2a7f60097bb02cb11eaabd66cad88657c505
ms.sourcegitcommit: 2abc6bf9939b14a427647e88f319dbb70de49ca6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458484"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Microsoft Managed Desktop und Windows 11

Nach der Ankündigung von Windows 11 haben Sie möglicherweise mit der Planung Windows 11-Migrationen begonnen, um Windows 10 Geräte auf dem neuesten Stand zu halten. Dieser Artikel beschreibt wichtige Überlegungen und wie Microsoft Managed Desktop reibungslose Übergänge in Ihren Umgebungen unterstützen. Informationen zu Windows 11 selbst finden Sie unter [Windows 11 Overview](/windows/whats-new/windows-11).

Spezifische Schritte zum Installieren von Windows 11 auf Ihren Microsoft Managed Desktop Geräten finden Sie unter [Vorschau und Testen Windows 11 mit Microsoft Managed Desktop.](../working-with-managed-desktop/test-win11-mmd.md)

## <a name="timeline-for-windows-11"></a>Zeitachse für Windows 11

Windows 11 Preview-Builds sind ab dem 28. Juni 2021 über das [Windows-Insider-Programm](/windows-insider/)verfügbar. Wir gehen davon aus, dass Releasebuilds bis zum Ende des Kalenders 2021 allgemein verfügbar sein werden.

Sie können Vorschaubuilds auf Geräten installieren, unabhängig davon, ob sie von Microsoft Managed Desktop verwaltet werden oder nicht. Wir werden weiterhin Windows 10 parallel unterstützen, bis das Ende des Supports erreicht ist.

Wenn Windows 11 allgemein verfügbar ist, führen wir weitere Überprüfungstests durch. Wir gehen davon aus, dass Januar 2022 demnächst Windows 11 für Microsoft Managed Desktop Produktionsgeräte über unsere Standardbereitstellungsgruppen angeboten wird.

Wir beraten Administratoren bei der Entwicklung und Implementierung von Migrationsplänen für jeden Mandanten basierend auf der technischen Bereitschaft und Ihren geschäftlichen Überlegungen.

## <a name="assessing-pre-release-versions-of-windows-11"></a>Bewerten von Vorabversionen von Windows 11

Mehr als 95 % der Microsoft Managed Desktop Geräte sind für Windows 11 berechtigt. Daher sollten Sie vor der Produktionsbereitstellung eine Vorschau des Upgrades auf Testgeräten anzeigen. Weitere Informationen zu Windows 11 Systemanforderungen finden Sie unter [Windows 11-Anforderungen.](/windows/whats-new/windows-11-requirements) Sie können Details zum Berechtigungsstatus Ihrer Geräte von Microsoft Managed Desktop anfordern.

Für Microsoft Managed Desktop Geräte können Sie anfordern, der Gerätegruppe **\[ "Modern Workplace \] Windows 11 Pre-Release Test Devices"** Testgeräte hinzuzufügen. Diese Gruppe empfängt Windows 11 Preview-Builds zusammen mit einer Microsoft Managed Desktop Basisplankonfiguration. Microsoft Managed Desktop verwaltet den Versionsrhythmus von Windows 11-Vorschaubuilds nicht, sodass Mitglieder dieser Gerätegruppe möglicherweise häufiger Updates erhalten als Windows 10 Gerätegruppen.

Für Ihre Geräte, die nicht von Microsoft Managed Desktop verwaltet werden, können Sie am [Windows Insider-Programm](/windows-insider/) teilnehmen, um Vorschaubuilds herunterzuladen und Anleitungen zur Bereitstellung von Windows 11 selbst zu erhalten. Wenn Sie Geräte Windows 11 Pre-Release-Builds ausführen und diese später in Microsoft Managed Desktop registrieren, werden sie nicht auf Windows 10 zurückgesetzt.

## <a name="support-for-pre-release-windows-11-devices"></a>Unterstützung für Geräte mit Vorabversion Windows 11

Vorabversionsbuilds jeder Plattform enthalten voraussichtlich Fehler und Kompatibilitätsprobleme, die vor der allgemeinen Verfügbarkeit identifiziert und behoben werden können. Daher betrachten wir Geräte, auf denen Vorabversionen von Windows 11 ausgeführt werden, als Testgeräte, überwachen sie jedoch zusammen mit der restlichen Umgebung auf Sicherheitsbedrohungen und unterliegen der gleichen Sicherheitswarnungsantwort wie andere Microsoft Managed Desktop Geräte.

Da wir ihnen helfen möchten, zu Windows 11 zu migrieren und gleichzeitig produktiv zu bleiben, empfehlen wir Ihnen, Fehler zu melden, die bei Vorabversionen auftreten. Wir priorisieren Fehler, die die Benutzerproduktivität bei der umfassenden Bereitstellung von Windows 11 blockieren, und Fehler, die die Produktivität der Benutzer auf Windows 10 Geräten blockieren.

## <a name="testing-application-compatibility"></a>Testen der Anwendungskompatibilität

Die Anwendungskompatibilität ist aufgrund des Potenziellen für Produktivitätsunterbrechungen eines der häufigsten Probleme bei jeder Plattformmigration. Wir verwenden mehrere proaktive und reaktive Maßnahmen, damit Sie sich bei reibungslosen App-Übergängen zu Windows 11 sicher fühlen können.

### <a name="proactive-measures"></a>Proaktive Maßnahmen

**Allgemeine Apps:** Microsoft testet die gängigsten Unternehmensanwendungen und -suites, die auf Builds von Windows 11 bereitgestellt werden, umfassend. Wir arbeiten mit externen Software-Herausgebern und internen Produktteams an der Lösung von Problemen, die während der Tests entdeckt wurden. Weitere Informationen zu unseren proaktiven Kompatibilitätstests finden Sie im Blog zur [Anwendungskompatibilität.](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/)

**Branchenspezifische Apps:** [Die Testbasis](https://www.microsoft.com/testbase) ist eine Ressource, die App-Herausgeber und IT-Administratoren verwenden können, um Apps und Testfälle zu übermitteln, damit Microsoft auf einem virtuellen Computer ausgeführt wird, auf dem Windows 11-Builds in einer sicheren Azure-Umgebung ausgeführt werden. Ergebnisse, Testerkenntnisse und Regressionsanalyse für jede Testausführung stehen Ihnen in einem privaten Azure-Portal zur Verfügung. Microsoft Managed Desktop helfen Ihnen bei der Priorisierung Ihrer Branchen-Apps für die Validierung basierend auf app-Nutzungs- und Zuverlässigkeitsdaten. Weitere Informationen zur Testbasis finden Sie unter [TestBasis für Microsoft 365](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566).

### <a name="reactive-measures"></a>Reaktive Messwerte

Wenn in Test- oder Produktionsumgebungen Probleme mit der App-Kompatibilität auftreten, können Sie Support erhalten, indem Sie App [Assure](/fasttrack/products-and-capabilities) oder FastTrack je nach Bedarf einbinden. Für Windows 11 umfasst dies alle Funktionen mit Office, Microsoft Edge und Teams Anwendungen, die auf den neuesten Betriebssystembuilds ausgeführt werden. App Assure bindet App-Herausgeber direkt ein, um Probleme mit der App-Kompatibilität zu priorisieren und zu beheben.