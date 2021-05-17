---
title: Microsoft Managed Desktop und ITIL
description: Korreliert ITIL-Phasen mit Microsoft Managed Desktop und Artikeln
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, ITISM
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

Viele Organisationen finden es wertvoll, ihre IT-Dienste nach einem formalisierten IT Service Model (ITSM) zu [strukturieren,](https://www.axelos.com/best-practice-solutions/itil)z. B. ITIL . 

Microsoft Managed Desktop ermöglicht Es Ihrer Organisation, viele wichtige Aspekte solcher formalisierten ITSM-Modelle zu erfüllen. Anhand von ITIL als Beispiel hilft ihnen dieser Artikel, die Verbindungen zwischen allgemeinen ITIL-Phasen und -Prozessen und entsprechenden Microsoft Managed Desktop zu sehen, sofern zutreffend. Diese Informationen gelten nur für Microsoft Managed Desktop Teil Ihrer Organisation.

Umfassendere Informationen zu ITIL und deren Phasen und Prozess finden Sie in [der](https://www.axelos.com/best-practice-solutions/itil)Dokumentation .


## <a name="service-design"></a>Dienstentwurf

In dieser Tabelle werden die wichtigsten ITIL-Phasen und -Prozesse mit den Microsoft Managed Desktop verknüpft, mit Links zu unserer Dokumentation, um details zu erhalten:



|ITIL-Prozess |Beschreibung  |Dokumentation |
|---------|---------|---------|
|Verwaltung auf Dienstebene     | Antwortzeiten werden für Anfragen und Vorfälle des Administratorsupports definiert.  |  [Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)  |
|Dienstkatalogverwaltung     | Die Dienstbeschreibung, in der Komponenten des Diensts detailliert beschrieben werden, bleibt dem Status des Diensts treu, der allen aktuellen und interessierten Kunden zur Verfügung steht.<br><br>Voraussetzungen, die detailliert sind, um zu verstehen, was für den Betrieb des Diensts erforderlich ist.  | - [Microsoft Managed Desktop Dienstbeschreibung](service-description/index.md)<br><br>- [Bereiten Sie sich auf die Registrierung in Microsoft Managed Desktop](get-ready/index.md)  |
|Verwaltung der Informationssicherheit     | Sicherheitsinformationen, einschließlich Informationssicherheit für den Dienst.<br><br> Sicherheitsbezogene Richtlinien und andere Informationen zur Konfiguration von Geräten.   | - [Sicherheit in Microsoft Managed Desktop](service-description/security.md)<br><br>- [Gerätekonfiguration](service-description/device-policies.md)  |
|Verfügbarkeitsverwaltung     |  Microsoft Managed Desktop die Verantwortung mit Ihrer Organisation ab, um die Verfügbarkeit des Diensts sicherzustellen.<br><br>Administratoren und Benutzer haben Routen zu entsprechendem Support, wenn Dienst- oder Verfügbarkeitsprobleme auftreten. | - [Microsoft Managed Desktop und Überwachung](service-description/operations-and-monitoring.md)<br><br>- [Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)<br>- [Hilfe für Benutzer erhalten](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Dienstübergang


|ITIL-Prozess |Beschreibung  |Dokumentation |
|---------|---------|---------|
|Change Management     | Definiertes Gleichgewicht zwischen Verantwortlichkeit, Prozessübersicht und Typen im Zusammenhang mit der Änderungsverwaltung verfügbar.  | [Microsoft Managed Desktop und Überwachung](service-description/operations-and-monitoring.md#change-management) |
|Release- und Bereitstellungsverwaltung     |  Microsoft Managed Desktop verwaltet Updates für Geräte, die im Dienst registriert sind.  | [So werden Updates in Microsoft Managed Desktop](service-description/updates.md)        |
|Dienstinventar- und Konfigurationsverwaltung     | Informationen zur Bereitstellung Microsoft Managed Desktop Organisation finden Sie im IT-Administratorportal.  | [Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md) |
|Wissensverwaltung     | Informationen zum Microsoft Managed Desktop werden auf dieser Website auf dem neuesten Stand gehalten.   | [Änderungsverlauf für Microsoft Managed Desktop-Dokumentation](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Dienstvorgang


|ITIL-Prozess |Beschreibung  |Dokumentation  |
|---------|---------|---------|
|Ereignisverwaltung     |  Details zur Überwachung von Geräten werden bereitgestellt.<br><br>Die Standardbetriebsverfahren für den Microsoft Managed Desktop werden ausführlich ausgeführt. |  - [Sicherheit in Microsoft Managed Desktop](service-description/security.md)<br>- [Microsoft Managed Desktop und Überwachung](service-description/operations-and-monitoring.md)       |
|Verwaltung von Sicherheitsvorfällen  | Microsoft Managed Desktop untersucht und handelt bei Vorfällen nach definierten Schweregraddefinitionen.  |  [Unterstützung von Definitionen für den Schweregrad von Anfragen](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Anforderungserfüllungsverwaltung     |  Der Prozess für Informations- und Änderungsanforderungen im Zusammenhang mit dem dienstbezogenen Microsoft Managed Desktop definiert.         |[Administratorunterstützung für Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)         |
|Problemverwaltung     | Alle Probleme mit dem Dienst sollten zu diesem Zeitpunkt an Ihr lokales Kontoteam geleitet werden. | Dokumentation in der Entwicklung |
|Zugriffsverwaltung     | Zugriffsverwaltungskomponenten und Zuständigkeiten für Kunden, um sicherzustellen, dass die Funktionalität detailliert ist.  | [Identitäts- und Zugriffsverwaltung](service-description/security.md#identity-and-access-management)        |
