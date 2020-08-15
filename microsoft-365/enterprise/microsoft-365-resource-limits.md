---
title: Microsoft 365-Ressourcengrenzwerte
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
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie Informationen zu den Ressourcen Grenzwerten für die verschiedenen Anwendungen in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6053740d41b02461432243c8527391a4f8ae22ea
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690709"
---
# <a name="resource-limits"></a>Ressourcenbeschränkungen

Ressourcengrenzwerte werden mithilfe von Kontingenten (Limits) und Drosselung erzwungen. Azure Active Directory (Azure AD) und die einzelnen Microsoft 365-Dienste verwenden beide. Grenzen sind Dienst spezifisch und ändern sich im Laufe der Zeit, wenn neue Funktionen hinzugefügt werden. Ausführliche Informationen zu den aktuellen Grenzwerten für die verschiedenen Dienste finden Sie in den folgenden Themen:

- [Azure Ad Service Limits und-Einschränkungen](https://docs.microsoft.com/azure/azure-resource-manager/management/azure-subscription-service-limits)
- [Exchange Online-Begrenzungen](https://technet.microsoft.com/library/exchange-online-limits.aspx)
- [Beschränkungen von Exchange Online Protection](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)
- [Grenzen und Grenzwerte für SharePoint Online Software](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [Skype for Business Grenzen](https://technet.microsoft.com/library/skype-for-business-online-limits.aspx)
- [Jammern der Rest-API und Raten Begrenzungen](https://developer.yammer.com/docs/rest-api-rate-limits)
- [Dateigrößenbeschränkungen in Sway](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

Zusätzlich zu diesen Grenzwerten werden mehrere Einschränkungs Mechanismen in Azure AD und in Microsoft 365 verwendet. Die Drosselung innerhalb des Diensts ist besonders wichtig, da Netzwerkressourcen in Microsoft-Rechenzentren für die breite Palette von Kunden optimiert sind, die die Dienste nutzen. Zu den Einschränkungs Mechanismen gehören:

- Azure AD-und Microsoft 365-Einschränkung auf Benutzerebene, die die Anzahl von Transaktionen oder gleichzeitigen anrufen (durch Skript oder Code) begrenzen, die von einem einzelnen Benutzer ausgeführt werden können.
- Jedem Mandanten wird bei der Mandanten Erstellung eine standardmäßige PowerShell-Einschränkungsrichtlinie zugewiesen. Diese Einstellungen wirken sich auf andere Elemente aus, beispielsweise die maximale Anzahl gleichzeitiger PowerShell-Sitzungen, die von einem einzelnen Administrator geöffnet werden können.
- Jeder Exchange Online-Kunde verfügt über eine standardmäßige Exchange-Webdienste-Richtlinie, die für EWS-Client Vorgänge optimiert ist, sowie für Einschränkungen, die für alle Outlook-Clients gelten.
