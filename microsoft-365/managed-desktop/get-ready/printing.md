---
title: Voraussetzungen von Druckressourcen für Microsoft Managed Desktop
description: Wichtige Schritte, um sicherzustellen, dass das Drucken reibungslos funktioniert
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: b6e809505fed8b1f84eb502dc08751ad1f0b587c
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841399"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Voraussetzungen von Druckressourcen für Microsoft Managed Desktop

Wenn Sie sich auf die Registrierung bei Microsoft Managed Desktop vorbereitet haben, sollten Sie Ihre Druckanforderungen auswerten und den richtigen Ansatz für Ihre Umgebung bestimmen. Sie haben drei Optionen:
 
- Stellen Sie die Microsoft Universal Print-Lösung zur Verfügung, um es Microsoft Managed Desktop-Geräten zu ermöglichen, Drucker zu finden. Weitere Informationen finden Sie unter ["Universelles Drucken".](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis)
- Stellen Sie Drucker direkt mithilfe eines benutzerdefinierten PowerShell-Skripts zur Verfügung. Führen Sie die Schritte im Abschnitt ["Einrichten lokaler Drucker"](#set-up-local-printers) aus.
- Verwenden Sie eine Nicht-Microsoft-Clouddrucklösung, die mit Windows 10-Geräten kompatibel ist, die mit einer Azure Active Directory-Domäne verbunden sind. Die Lösung muss die Softwareanforderungen für Microsoft Managed Desktop erfüllen. Weitere Informationen finden Sie unter [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).
 
Wenn die Druckertreiber nicht über Microsoft Update oder den Microsoft Store verfügbar sind, müssen Sie diese in allen Fällen selbst abrufen und für die Bereitstellung auf Ihren Microsoft Managed Desktop-Geräten mit Microsoft Intune packen lassen. Weitere Informationen finden Sie unter [Eigenständiges Intune – Win32-App-Verwaltung](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Einrichten lokaler Drucker

Wenn Sie sich für die Bereitstellung von Druckern mit einem benutzerdefinierten PowerShell-Skript entschieden und die Druckressourcen vorbereitet haben, führen Sie die folgenden Schritte aus, um freigegebene Drucker bereitstellen zu können:

1.  Navigieren Sie zum Microsoft Managed Desktop-Portal.
2.  Übermitteln Sie eine Anforderung mit der *Bezeichnung "Druckerbereitstellung"* im Abschnitt **"Support > Supportanfragen"** des Verwaltungsportals, und geben Sie dabei die folgenden Details an:
    - Alle UNC-Pfade zu freigegebenen Druckerstandorten, die für Microsoft Managed Desktop Geräte bereitgestellt werden müssen
    - Benutzergruppen, die Zugriff auf diese freigegebenen Drucker benötigen
3.  Mithilfe des Verwaltungsportals teilen wir Ihnen mit, wann die Anforderung abgeschlossen wurde. Zunächst stellen wir die Konfiguration nur auf Geräten in der Testbereitstellungsgruppe zur Verfügung.
4.  Sie müssen testen und überprüfen, ob die Konfiguration wie erwartet funktioniert. Antworten Sie auf **der** Registerkarte "Diskussion" in der Supportanfrage, um uns zu wissen, wann Sie Ihre Tests abgeschlossen haben.
5.  Die Konfiguration wird dann für die anderen Bereitstellungsgruppen bereitgestellt.
