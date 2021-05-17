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
ms.openlocfilehash: 971644aafabda733bf745fae278bdfeeed3282e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574547"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Vorbereiten der Druckressourcen für Microsoft Managed Desktop

Wenn Sie sich für die Registrierung Microsoft Managed Desktop, sollten Sie Ihre Druckanforderungen auswerten und den richtigen Ansatz für Ihre Umgebung bestimmen. Sie haben drei Optionen:
 
- Stellen Sie die Microsoft Universal Print-Lösung zur Verfügung, damit Microsoft Managed Desktop Drucker leichter erkennen können. Weitere Informationen finden Sie unter [Was ist Universal Print](/universal-print/fundamentals/universal-print-whatis).
- Stellen Sie Drucker mithilfe eines benutzerdefinierten PowerShell-Skripts direkt zur Verfügung. Führen Sie die Schritte im [Abschnitt Einrichten lokaler Drucker](#set-up-local-printers) aus.
- Verwenden Sie eine Nicht-Microsoft-Cloud-Drucklösung, die mit Windows 10 Geräten kompatibel ist, die einer Azure Active Directory sind. Die Lösung muss die Softwareanforderungen für die Microsoft Managed Desktop. Weitere Informationen finden Sie unter [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).
 
Wenn die Druckertreiber nicht über Microsoft Update oder die Microsoft Store verfügbar sind, müssen Sie sie in allen Fällen selbst abrufen und für die Bereitstellung auf Ihren Microsoft Managed Desktop-Geräten mit Microsoft Intune. Weitere Informationen finden Sie unter [Intune Standalone – Win32 App Management](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Einrichten lokaler Drucker

Wenn Sie sich für die Bereitstellung von Druckern mithilfe eines benutzerdefinierten PowerShell-Skripts entschieden haben und die Druckressourcen vorbereitet haben, führen Sie die folgenden Schritte aus, um freigegebene Drucker bereitstellen zu können:

1.  Navigieren Sie zum Microsoft Managed Desktop Portal.
2.  Senden Sie eine Anforderung mit der Bezeichnung *Druckerbereitstellung* im Abschnitt **Support > Supportanfragen** des Admin Portals, und geben Sie die folgenden Details an:
    - Alle UNC-Pfade zu freigegebenen Druckerstandorten, die für Microsoft Managed Desktop bereitgestellt werden müssen
    - Benutzergruppen, die Zugriff auf diese freigegebenen Drucker benötigen
3.  Mithilfe des Administratorportals teilen wir Ihnen mit, wann die Anforderung abgeschlossen wurde. Zunächst stellen wir die Konfiguration nur auf Geräten in der Testbereitstellungsgruppe zur Verfügung.
4.  Sie müssen testen und bestätigen, ob die Konfiguration wie erwartet funktioniert. Antworten Sie auf der Registerkarte **Diskussion** in der Supportanfrage, um uns zu sagen, wann Sie Ihre Tests abgeschlossen haben.
5.  Anschließend wird die Konfiguration für die anderen Bereitstellungsgruppen bereitgestellt.

## <a name="steps-to-get-ready"></a>Schritte für die ersten Schritte

1. Überprüfen [Sie Voraussetzungen für Microsoft Managed Desktop](prerequisites.md).
2. Verwenden [Sie Die Bereitschaftsbewertungstools](readiness-assessment-tool.md).
3. [Voraussetzungen für Gastkonten](guest-accounts.md)
4. [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md)
5. [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop](authentication.md)
7. [Apps im Microsoft Managed Desktop](apps.md)
8. [Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop](mapped-drives.md)
9. [Vorbereiten von Druckressourcen für Microsoft Managed Desktop](printing.md) (Dieser Artikel)
