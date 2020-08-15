---
title: Office 365-Verwaltungsaktivitäts-API
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie eine kurze Zusammenfassung der API für die Office 365-Verwaltungsaktivität und der Informationen, die Sie in Aktivitätsprotokollen bereitstellt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea08673f4c26c9ee4b7093ba420b69bed91abc81
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690761"
---
# <a name="office-365-management-activity-api"></a>Office 365-Verwaltungsaktivitäts-API

Microsoft stellt Reporting Services bereit, die Sie zum Abrufen aggregierter Transaktionsinformationen zu Ihrem Office 365 Mandanten verwenden können. Die [Office 365-Verwaltungs Aktivitäts-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview#office-365-management-activity-api) verwendet einen branchenüblichen Rest-Entwurf und OAuth v2 für die Authentifizierung. Auf diese Weise wird das Experimentieren mit dem Abrufen von Daten und der Einnahme in Visualisierungstools und-Anwendungen vereinfacht. Die API stellt einen Datenfeed mit Informationen zu Benutzern, Administratoren, Vorgängen und Sicherheitsaktivitäten in Office 365 bereit. Die Daten können zu behördlichen Zwecken aufbewahrt werden oder in Kombination mit Protokolldaten, die über eine lokale Infrastruktur oder andere Quellen beschafft werden. Auf diese Weise können Sie eine Überwachungslösung für Vorgänge, Sicherheit und Compliance im gesamten Unternehmen erstellen.

Die Office 365-Verwaltungsaktivitäts-API bietet Informationen über verschiedene Benutzer-, Verwaltungs-, System- und Richtlinienaktionen und -ereignisse aus Office 365 und Azure Active Directory-Aktivitätsprotokollen. Die API bietet ein konsistentes Überwachungsschema mit mehr als 10 Feldern, die für alle Dienste gemeinsam sind. Die API ermöglicht es Organisationen, einfache Verbindungen zwischen Ereignissen herzustellen, und ermöglicht neue Wege zur Begründung der Daten.

Dutzende von unabhängigen Software Anbietern (Independent Software Vendors, ISVs) haben mit Microsoft zusammenarbeiten und Lösungen basierend auf der API entwickelt. Einige Lösungen konzentrieren sich ausschließlich auf Office 365 Daten und andere Quelldaten von mehreren Cloud-Anbietern und lokalen Systemen, um eine einheitliche Ansicht der Vorgänge, der Sicherheit und der Konformitäts bezogenen Aktivitäten zu erstellen. 

Weitere Informationen finden Sie in der [API-Referenz zur Office 365-Verwaltungsaktivität](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).
