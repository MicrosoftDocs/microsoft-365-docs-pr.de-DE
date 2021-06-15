---
title: Microsoft Managed Desktop und ITIL
description: Korreliert ITIL-Phasen mit Microsoft Managed Desktop Informationen und Artikeln
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: f51c99ed39e9f647f3e069c22eb3e37441f57be5
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924479"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft Managed Desktop und ITIL

Viele Organisationen finden es hilfreich, ihre IT-Dienste gemäß einem formalisierten IT-Dienstmodell (ITSM) zu strukturieren, z. B. [ITIL.](https://www.axelos.com/best-practice-solutions/itil) 

Microsoft Managed Desktop ermöglicht Es Ihrer Organisation, viele wichtige Aspekte solcher formalisierten ITSM-Modelle einzuhalten. Anhand von ITIL als Beispiel können Sie in diesem Artikel die Verbindungen zwischen gängigen ITIL-Phasen und -Prozessen sowie ggf. entsprechende Microsoft Managed Desktop-Features erkennen. Diese Informationen gelten nur für den Microsoft Managed Desktop Teil Ihrer Organisation.

Umfassendere Informationen zu ITIL und seinen Phasen und Prozessen finden Sie in der [Dokumentation.](https://www.axelos.com/best-practice-solutions/itil)


## <a name="service-design"></a>Dienstdesign

Diese Tabelle verknüpft wichtige ITIL-Phasen und -Prozesse mit Microsoft Managed Desktop Features, mit Links zu unserer Dokumentation für Details:



|ITIL-Prozess |Beschreibung  |Dokumentation |
|---------|---------|---------|
|Verwaltung auf Dienstebene     | Antwortzeiten werden für Supportanfragen und Vorfälle von Administratoren definiert.  |  [Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)  |
|Dienstkatalogverwaltung     | Die Dienstbeschreibung, in der die Komponenten des Diensts angegeben werden, wird dem Status des Diensts entsprechend beibehalten, der für alle aktuellen und interessierten Kunden verfügbar ist.<br><br>Voraussetzungen, die detailliert sind, um zu verstehen, was für den Betrieb des Diensts erforderlich ist.  | - [Microsoft Managed Desktop Dienstbeschreibung](service-description/index.md)<br><br>- [Vorbereiten der Registrierung in Microsoft Managed Desktop](get-ready/index.md)  |
|Verwaltung der Informationssicherheit     | Sicherheitsinformationen, einschließlich Informationssicherheit für den Dienst.<br><br> Sicherheitsbezogene Richtlinien und andere Informationen zur Konfiguration von Geräten.   | - [Sicherheit in Microsoft Managed Desktop](service-description/security.md)<br><br>- [Gerätekonfiguration](service-description/device-policies.md)  |
|Verfügbarkeitsverwaltung     |  Microsoft Managed Desktop übernimmt die Verantwortung mit Ihrer Organisation, um die Verfügbarkeit des Diensts sicherzustellen.<br><br>Administratoren und Benutzer haben Routen zum jeweiligen Support, wenn Es Probleme mit Diensten oder Verfügbarkeit gibt. | - [Microsoft Managed Desktop Vorgänge und Überwachung](service-description/operations-and-monitoring.md)<br><br>- [Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)<br>- [Hilfe für Benutzer erhalten](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Dienstübergang


|ITIL-Prozess |Beschreibung  |Dokumentation |
|---------|---------|---------|
|Change Management     | Definiertes Gleichgewicht zwischen Verantwortlichkeit, Prozessübersicht und Typen im Zusammenhang mit der Änderungsverwaltung verfügbar.  | [Microsoft Managed Desktop Vorgänge und Überwachung](service-description/operations-and-monitoring.md#change-management) |
|Release- und Bereitstellungsverwaltung     |  Microsoft Managed Desktop verwaltet Updates für Geräte, die im Dienst registriert sind.  | [Umgang mit Updates in Microsoft Managed Desktop](service-description/updates.md)        |
|Verwaltung von Dienstressourcen und -konfigurationen     | Informationen zur Microsoft Managed Desktop Bereitstellung Ihrer Organisation finden Sie im IT-Verwaltungsportal.  | [Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md) |
|Wissensmanagement     | Informationen zum Microsoft Managed Desktop-Diensts werden auf dieser Website auf dem neuesten Stand gehalten.   | [Änderungsverlauf für Microsoft Managed Desktop-Dokumentation](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Dienstvorgang


|ITIL-Prozess |Beschreibung  |Dokumentation  |
|---------|---------|---------|
|Ereignisverwaltung     |  Details zur Überwachung von Geräten werden bereitgestellt.<br><br>Die Standardvorgehensweisen für den Microsoft Managed Desktop-Dienst sind detailliert. |  - [Sicherheit in Microsoft Managed Desktop](service-description/security.md)<br>- [Microsoft Managed Desktop Vorgänge und Überwachung](service-description/operations-and-monitoring.md)       |
|Verwaltung von Sicherheitsvorfällen  | Microsoft Managed Desktop untersucht Vorfälle gemäß den definierten Schweregraddefinitionen und reagiert darauf.  |  [Support-Schweregraddefinitionen für Anforderungen](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Anforderungserfüllungsverwaltung     |  Der Prozess für Anforderungen für Informationen und Änderungsanforderungen im Zusammenhang mit dem Microsoft Managed Desktop Dienst wird definiert.         |[Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)         |
|Problemverwaltung     | Alle Probleme mit dem Dienst sollten zu diesem Zeitpunkt an Ihr lokales Kontoteam weitergeleitet werden. | Dokumentation in der Entwicklung |
|Zugriffsverwaltung     | Zugriffsverwaltungskomponenten und Zuständigkeiten für Kunden, um sicherzustellen, dass die Funktionalität detailliert ist.  | [Identitäts- und Zugriffsverwaltung](service-description/security.md#identity-and-access-management)        |
