---
title: Voraussetzungen von Druckressourcen für Microsoft Managed Desktop
description: Wichtige Schritte, um sicherzustellen, dass der Druck reibungslos funktioniert
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1588a2c91bcbe0bd381acb6be4f9bd5562810860
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530247"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Voraussetzungen von Druckressourcen für Microsoft Managed Desktop

Wenn Sie bereit sind, sich für die Registrierung in Microsoft Managed Desktop vorzubereiten, sollten Sie Ihre Druckanforderungen auswerten und den richtigen Ansatz für Ihre Umgebung bestimmen. Sie haben drei Optionen:
 
- Stellen Sie die Microsoft Hybrid Cloud Print Solution bereit, damit Microsoft Managed Desktop-Geräte Drucker leichter entdecken können. Weitere Informationen finden Sie unter [Deploy Windows Server Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
- Stellen Sie Drucker direkt mithilfe eines benutzerdefinierten PowerShell-Skripts bereit. Führen Sie dazu die Schritte im Abschnitt [lokale Drucker einrichten](#set-up-local-printers) aus.
- Verwenden Sie eine nicht von Microsoft bereitgestellte Cloud-Drucklösung, die mit Windows 10-Geräten kompatibel ist, die einer Azure Active Directory Domäne beigetreten sind. Die Lösung muss den Softwareanforderungen für Microsoft Managed Desktop entsprechen. Weitere Informationen finden Sie unter [Microsoft Managed Desktop App Requirements](../service-description/mmd-app-requirements.md).
 
Wenn die Druckertreiber nicht über Microsoft Update oder den Microsoft Store verfügbar sind, müssen Sie Sie in allen Fällen selbst beziehen und für die Bereitstellung auf Ihren Microsoft Managed Desktop-Geräten mit Microsoft InTune verpacken lassen. Weitere Informationen finden Sie unter [InTune Standalone-Win32-App-Verwaltung](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Einrichten von lokalen Druckern

Wenn Sie sich für die Bereitstellung von Druckern mit einem benutzerdefinierten PowerShell-Skript entschieden haben und die Druckressourcen vorbereitet haben, führen Sie die folgenden Schritte aus, um freigegebene Drucker bereitzustellen:

1.  Navigieren Sie zum Microsoft Managed Desktop Portal.
2.  Senden Sie eine Anforderung mit der Bezeichnung *Printer Deployment* im Abschnitt **Support > Supportanfragen** des Administrator Portals mit den folgenden Details:
    - Alle UNC-Pfade zu freigegebenen Druckerstandorten, die für Microsoft Managed Desktop-Geräte bereitgestellt werden müssen
    - Benutzergruppen, die Zugriff auf diese freigegebenen Drucker benötigen
3.  Mithilfe des Verwaltungsportals informieren wir Sie, wann die Anforderung abgeschlossen wurde. Zunächst stellen wir die Konfiguration nur auf Geräten in der Test Bereitstellungsgruppe bereit.
4.  Sie müssen testen und überprüfen, ob die Konfiguration wie erwartet funktioniert. Antworten Sie mithilfe der Registerkarte **Diskussion** in der Support Anfrage, um uns mitzuteilen, wann Sie Ihre Tests abgeschlossen haben.
5.  Anschließend stellen wir die Konfiguration für die anderen Bereitstellungsgruppen bereit.
