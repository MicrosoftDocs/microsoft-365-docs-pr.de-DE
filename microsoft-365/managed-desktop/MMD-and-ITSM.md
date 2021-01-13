---
title: Microsoft Managed Desktop und ITIL
description: Korreliert die Phasen von ITIL mit Microsoft Managed Desktop-Informationen und -Artikeln.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: e545b64670bb92c40465f1c50b2cb46b9fd7a8d8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841435"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft Managed Desktop und ITIL

Viele Organisationen finden es nützlich, ihre IT-Dienste nach dem Muster eines formalisierten IT Service Model (ITSM) wie [ITIL zu strukturieren.](https://www.axelos.com/best-practice-solutions/itil) 

Microsoft Managed Desktop ermöglicht es Ihrer Organisation, viele wichtige Aspekte dieser formalisierten ITSM-Modelle zu berücksichtigen. Anhand von ITIL als Beispiel können Sie in diesem Artikel ggf. die Verbindungen zwischen gängigen ITIL-Phasen und -Prozessen und entsprechenden Microsoft Managed Desktop-Features anzeigen. Diese Informationen gelten nur für den Microsoft Managed Desktop-Teil Ihrer Organisation.

Umfassendere Informationen zu ITIL und deren Phasen und Prozess finden Sie in [der](https://www.axelos.com/best-practice-solutions/itil)dokumentation.


## <a name="service-design"></a>Dienstdesign

Diese Tabelle bezieht sich auf wichtige Phasen und Prozesse von ITIL mit Microsoft Managed Desktop-Features, mit Links zu unserer Dokumentation für Details:



|ITIL-Prozess |Beschreibung  |Dokumentation |
|---------|---------|---------|
|Verwaltung auf Dienstebene     | Antwortzeiten werden für Supportanfragen und Vorfälle von Administratoren definiert.  |  [Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)  |
|Dienstkatalogverwaltung     | Die Dienstbeschreibung, in der Komponenten des Diensts detailliert beschrieben werden, wird auf den Status des Diensts beibehalten, der für alle aktuellen und interessierten Kunden verfügbar ist.<br><br>Voraussetzungen, die ausführlich sind, um zu verstehen, was für den Betrieb des Diensts erforderlich ist.  | - [Beschreibung des Microsoft Managed Desktop-Diensts](service-description/index.md)<br><br>- [Bereiten Sie sich auf die Registrierung in Microsoft Managed Desktop vor](get-ready/index.md)  |
|Verwaltung der Informationssicherheit     | Sicherheitsinformationen, einschließlich Der Informationssicherheit für den Dienst.<br><br> Sicherheitsbezogene Richtlinien und andere Informationen zur Konfiguration von Geräten.   | - [Sicherheit in Microsoft Managed Desktop](service-description/security.md)<br><br>- [Gerätekonfiguration](service-description/device-policies.md)  |
|Verfügbarkeitsverwaltung     |  Microsoft Managed Desktop sorgt dafür, dass die Verfügbarkeit des Diensts sichergestellt ist.<br><br>Administratoren und Benutzer haben Routen zum entsprechenden Support, wenn Dienst- oder Verfügbarkeitsprobleme auftreten. | - [Microsoft Managed Desktop – Vorgänge und Überwachung](service-description/operations-and-monitoring.md)<br><br>- [Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)<br>- [Hilfe für Benutzer erhalten](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Dienstübergang


|ITIL-Prozess |Beschreibung  |Dokumentation |
|---------|---------|---------|
|Change Management     | Definiertes Gleichgewicht zwischen Verantwortlichkeit, Prozessübersicht und Typen im Zusammenhang mit der verfügbaren Änderungsverwaltung.  | [Microsoft Managed Desktop – Vorgänge und Überwachung](service-description/operations-and-monitoring.md#change-management) |
|Release- und Bereitstellungsverwaltung     |  Microsoft Managed Desktop verwaltet Updates für Geräte, die beim Dienst registriert sind.  | [So werden Updates in Microsoft Managed Desktop behandelt](service-description/updates.md)        |
|Dienstinventar- und Konfigurationsverwaltung     | Informationen zur Microsoft Managed Desktop-Bereitstellung Ihrer Organisation finden Sie im IT-Verwaltungsportal.  | [Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md) |
|Wissensverwaltung     | Informationen zum Microsoft Managed Desktop-Dienst werden auf dieser Website auf dem neuesten Stand gehalten.   | [Änderungsverlauf für Microsoft Managed Desktop-Dokumentation](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Dienstvorgang


|ITIL-Prozess |Beschreibung  |Dokumentation  |
|---------|---------|---------|
|Ereignisverwaltung     |  Details zur Überwachung von Geräten werden bereitgestellt.<br><br>Die Standardbetriebsverfahren für den Microsoft Managed Desktop-Dienst sind ausführlich. |  - [Sicherheit in Microsoft Managed Desktop](service-description/security.md)<br>- [Microsoft Managed Desktop – Vorgänge und Überwachung](service-description/operations-and-monitoring.md)       |
|Verwaltung von Sicherheitsvorfällen  | Microsoft Managed Desktop untersucht Vorfälle nach definierten Schweregraddefinitionen und geht auf diese ein.  |  [Unterstützen von Definitionen des Anforderungsschweregrads](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Anforderungserfüllungsverwaltung     |  Der Prozess für Informations- und Änderungsanforderungen im Zusammenhang mit dem Microsoft Managed Desktop Service wird definiert.         |[Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)         |
|Problemverwaltung     | Alle Probleme mit dem Dienst sollten zu diesem Zeitpunkt an Ihr lokales Kontoteam geleitet werden. | Dokumentation in der Entwicklung |
|Zugriffsverwaltung     | Zugriffsverwaltungskomponenten und Zuständigkeiten für Kunden, um sicherzustellen, dass die Funktionalität detailliert ist.  | [Identitäts- und Zugriffsverwaltung](service-description/security.md#identity-and-access-management)        |
