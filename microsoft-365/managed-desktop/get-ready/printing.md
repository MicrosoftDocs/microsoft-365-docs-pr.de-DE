---
title: Vorbereiten der Druckressourcen für Microsoft Managed Desktop
description: Wichtige Schritte, um sicherzustellen, dass das Drucken reibungslos funktioniert
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 3f77074aa11e9dc82c8fac9763fdebfd2fc49d99
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287209"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Vorbereiten der Druckressourcen für Microsoft Managed Desktop

Wenn Sie sich für Microsoft Managed Desktop registrieren möchten, sollten Sie Ihre Druckanforderungen auswerten und den richtigen Ansatz für Ihre Umgebung bestimmen. Sie haben drei Optionen:

- Stellen Sie die Microsoft Universal Print-Lösung bereit, um Microsoft Managed Desktop Geräten das Auffinden von Druckern zu erleichtern. Weitere Informationen finden Sie unter [What is Universal Print](/universal-print/fundamentals/universal-print-whatis).
- Stellen Sie Drucker direkt mithilfe eines benutzerdefinierten PowerShell-Skripts bereit. Führen Sie die Schritte im Abschnitt ["Einrichten lokaler Drucker"](#set-up-local-printers) aus.
- Verwenden Sie eine nicht von Microsoft stammende Clouddrucklösung, die mit Windows 10 Geräten kompatibel ist, die mit einer Azure Active Directory Domäne verbunden sind. Die Lösung muss die Softwareanforderungen für Microsoft Managed Desktop erfüllen. Weitere Informationen finden Sie unter [Microsoft Managed Desktop App-Anforderungen.](../service-description/mmd-app-requirements.md)
 
Wenn die Druckertreiber nicht über Microsoft Update oder die Microsoft Store verfügbar sind, müssen Sie diese selbst abrufen und sie für die Bereitstellung auf Ihren Microsoft Managed Desktop Geräten mit Microsoft Intune verpacken lassen. Weitere Informationen finden Sie unter [Intune Standalone – Win32-App-Verwaltung](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Einrichten lokaler Drucker

Wenn Sie sich entschieden haben, Drucker mithilfe eines benutzerdefinierten PowerShell-Skripts bereitzustellen und die Druckressourcen vorbereitet haben, führen Sie die folgenden Schritte aus, um freigegebene Drucker bereitzustellen:

1. Navigieren Sie zum Microsoft Managed Desktop-Portal.
2. Übermitteln Sie eine Anforderung mit der Bezeichnung *"Druckerbereitstellung"* im Abschnitt **"Support > Supportanfragen"** des Verwaltungsportals, und geben Sie diese Details an:
    - Alle UNC-Pfade zu freigegebenen Druckerstandorten, die für Microsoft Managed Desktop Geräte bereitgestellt werden müssen
    - Benutzergruppen, die Zugriff auf diese freigegebenen Drucker benötigen
3. Über das Verwaltungsportal teilen wir Ihnen mit, wann die Anforderung abgeschlossen wurde. Zunächst stellen wir die Konfiguration nur auf Geräten in der Testbereitstellungsgruppe bereit.
4. Sie müssen testen und überprüfen, ob die Konfiguration wie erwartet funktioniert. Antworten Sie mithilfe der Registerkarte **"Diskussion"** in der Supportanfrage, um uns mitzuteilen, wann Sie Ihre Tests abgeschlossen haben.
5. Anschließend stellen wir die Konfiguration für die anderen Bereitstellungsgruppen bereit.

## <a name="steps-to-get-ready"></a>Schritte zum Vorbereiten

1. Überprüfen Sie [die Voraussetzungen für Microsoft Managed Desktop.](prerequisites.md)
2. Verwenden Sie [Bereitschaftsbewertungstools.](readiness-assessment-tool.md)
3. [Voraussetzungen für Gastkonten](guest-accounts.md)
4. [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md)
5. [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop](authentication.md)
7. [Apps im Microsoft Managed Desktop](apps.md)
8. [Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop](mapped-drives.md)
9. [Vorbereiten der Druckressourcen für Microsoft Managed Desktop](printing.md) (dieser Artikel)
