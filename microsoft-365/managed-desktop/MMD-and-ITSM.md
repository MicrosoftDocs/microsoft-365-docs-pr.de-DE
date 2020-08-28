---
title: Microsoft Managed Desktop und ITIL
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, itism
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 05bd5a2ee36633b7ccf9ae61e601988a7268bb2c
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289805"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft Managed Desktop und ITIL

Viele Organisationen finden es hilfreich, Ihre IT-Dienste auf der Linie eines formalisierten IT-Dienstmodells (ITSM) wie [ITIL](https://www.axelos.com/best-practice-solutions/itil)zu strukturieren. 

Mit dem Microsoft Managed Desktop kann Ihre Organisation viele wichtige Aspekte solcher formalisierter ITSM-Modelle einhalten. Mithilfe von ITIL als Beispiel können Sie in diesem Thema die Verbindungen zwischen gängigen ITIL-Phasen und-Prozessen und gleichwertigen Microsoft Managed Desktop-Funktionen sehen, sofern zutreffend. Dies gilt nur für den Microsoft Managed Desktop-Teil Ihrer Organisation.

Ausführlichere Informationen zu ITIL und seinen Phasen und Prozessen finden Sie in der [Dokumentation](https://www.axelos.com/best-practice-solutions/itil).


## <a name="service-design"></a>Dienstentwurf

In dieser Tabelle werden die wichtigsten ITIL-Phasen und-Prozesse zu Microsoft Managed Desktop-Funktionen mit Links zu unserer Dokumentation für Details beschrieben:



|ITIL-Prozess |Beschreibung  |Dokumentation |
|---------|---------|---------|
|Verwaltung auf Dienstebene     | Antwortzeiten werden für Anforderungen und Vorfälle von Administrator Unterstützung definiert.  |  [Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)  |
|DIENSTKATALOG Verwaltung     | Dienstbeschreibung Details der Komponenten des Diensts wird auf den Status des Diensts, der allen aktuellen und interessierten Kunden zur Verfügung steht, wahr gehalten.<br><br>Ausführliche Voraussetzungen, um zu verstehen, was zum Betrieb des Diensts erforderlich ist.  | - [Beschreibung des Microsoft Managed Desktop-Diensts](service-description/index.md)<br><br>- [Vorbereiten der Registrierung in Microsoft Managed Desktop](get-ready/index.md)  |
|Verwaltung von Informationssicherheit     | Sicherheitsinformationen, einschließlich Informationssicherheit für den Dienst.<br><br> Sicherheitsbezogene Richtlinien und andere Informationen zur Konfiguration von Geräten.   | - [Sicherheit in Microsoft Managed Desktop](service-description/security.md)<br><br>- [Gerätekonfiguration](service-description/device-policies.md)  |
|Verfügbarkeitsverwaltung     |  Microsoft Managed Desktop gleicht die Verantwortung für Ihre Organisation aus, um die Verfügbarkeit des Diensts sicherzustellen.<br><br>Administratoren und Benutzer haben Routen zur jeweiligen Unterstützung für den Fall von Dienst-oder Verfügbarkeitsproblemen. | - [Microsoft Managed Desktop-Vorgänge und-Überwachung](service-description/operations-and-monitoring.md)<br><br>- [Administrator Unterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)<br>- [Aufrufen von Hilfe für Benutzer](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Dienst Übergang


|ITIL-Prozess |Beschreibung  |Dokumentation |
|---------|---------|---------|
|Change Management     | Definiertes Verantwortungsbewusstsein, Prozessübersicht und Typen im Zusammenhang mit Änderungsverwaltung verfügbar.  | [Microsoft Managed Desktop-Vorgänge und-Überwachung](service-description/operations-and-monitoring.md#change-management) |
|Veröffentlichungs-und Bereitstellungsverwaltung     |  Microsoft Managed Desktop verwaltet Updates für Geräte, die im Dienst registriert sind.  | [Behandlung von Updates in Microsoft Managed Desktop](service-description/updates.md)        |
|Dienst Ressourcen-und Konfigurationsverwaltung     | Informationen zur Microsoft Managed Desktop-Bereitstellung in Ihrer Organisation sind im IT-Verwaltungsportal verfügbar.  | [Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md) |
|Wissensverwaltung     | Informationen im Microsoft Managed Desktop-Dienst werden auf dieser Website auf dem neuesten Stand gehalten.   | [Änderungsverlauf für Microsoft Managed Desktop-Dokumentation](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Dienstvorgang


|ITIL-Prozess |Beschreibung  |Dokumentation  |
|---------|---------|---------|
|Ereignisverwaltung     |  Details zur Überwachung von Geräten werden bereitgestellt.<br><br>Die Standard mäßigen Betriebsverfahren für den Microsoft Managed Desktop-Dienst werden detailliert beschrieben. |  - [Sicherheit in Microsoft Managed Desktop](service-description/security.md)<br>- [Microsoft Managed Desktop-Vorgänge und-Überwachung](service-description/operations-and-monitoring.md)       |
|Vorfallverwaltung  | Microsoft Managed Desktop untersucht und handelt bei Vorfällen pro definierter Schweregrad Definition.  |  [Dringlichkeits Definitionen für Support Anforderungen](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Anforderungs Erfüllungs Verwaltung     |  Prozess für Informationsanfragen und Änderungsanforderungen im Zusammenhang mit dem Microsoft Managed Desktop-Dienst sind definiert.         |[Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)         |
|Problem Verwaltung     | Alle Probleme mit dem Dienst sollten zu diesem Zeitpunkt an Ihr lokales Konto Team weitergeleitet werden. | Dokumentation in der Entwicklung |
|Zugriffsverwaltung     | Zugriffs Verwaltungskomponenten und-Zuständigkeiten für Kunden, um sicherzustellen, dass die Funktionalität detailliert ist.  | [Identitäts- und Zugriffsverwaltung](service-description/security.md#identity-and-access-management)        |
