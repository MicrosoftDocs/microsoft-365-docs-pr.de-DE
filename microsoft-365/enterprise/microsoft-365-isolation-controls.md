---
title: Microsoft 365-Isolierungssteuerungen
ms.author: robmazz
author: robmazz
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
description: Erfahren Sie, wie Isolationssteuerelemente innerhalb Microsoft 365 funktionieren, sodass Dienste je nach Bedarf interaktiv oder autonom bleiben können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464097"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365-Isolierungssteuerungen 

Microsoft arbeitet kontinuierlich daran, sicherzustellen, dass die mehrinstanzenfähige Architektur von Microsoft 365 Sicherheit, Vertraulichkeit, Datenschutz, Integrität, lokale, internationale und [Verfügbarkeitsstandards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)auf Unternehmensebene unterstützt. Aufgrund des Umfangs und des Umfangs der von Microsoft bereitgestellten Dienste ist es schwierig und nicht unzuverwaltend, Microsoft 365 mit erheblichen menschlichen Interaktionen zu verwalten. Microsoft 365 Dienste werden über mehrere global verteilte Rechenzentren bereitgestellt, die jeweils hochgradig automatisiert sind und nur wenige Vorgänge erfordern, die eine menschliche Berührung erfordern, oder jeden Zugriff auf Kundeninhalte. Unsere Mitarbeiter unterstützen diese Dienste und Rechenzentren mit automatisierten Tools und äußerst sicherem Remotezugriff. 

Microsoft 365 besteht aus mehreren Diensten, die wichtige Geschäftsfunktionen bereitstellen und zur gesamten Microsoft 365 Erfahrung beitragen. Jeder dieser Dienste ist eigenständig und für die Integration ineinander konzipiert.

Microsoft 365 ist auf die folgenden Prinzipien ausgelegt:

 - **[Dienstorientierte Architektur:](/previous-versions/aa480021(v=msdn.10))** Entwerfen und Entwickeln von Software in Form von interoperablen Diensten, die eine gut definierte Geschäftsfunktionalität bereitstellen.
 - **[Operational Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872):** ein Framework, das das Wissen enthält, das durch verschiedene Funktionen gewonnen wurde, die für Microsoft einzigartig sind, einschließlich des Microsoft Security Development [Lifecycle,](https://www.microsoft.com/sdl/default.aspx)des [Microsoft Security Response Centers](https://technet.microsoft.com/library/dn440717.aspx)und des tiefen Bewusstseins für die Bedrohungslandschaft im Zusammenhang mit der Cybersicherheit.

Microsoft 365 Dienste arbeiten miteinander, sind jedoch so konzipiert und implementiert, dass sie unabhängig voneinander als autonome Dienste bereitgestellt und betrieben werden können. Microsoft trennt Aufgaben und Zuständigkeitsbereiche für Microsoft 365, um Möglichkeiten für nicht autorisierte oder unbeabsichtigte Änderungen oder Missbrauch der Ressourcen der Organisation zu verringern. Microsoft 365 Teams haben Rollen als Teil eines umfassenden rollenbasierten Zugriffssteuerungsmechanismus definiert.

## <a name="customer-content-isolation"></a>Kundeninhaltsisolation

Alle Kundeninhalte in einem Mandanten sind von anderen Mandanten und von Vorgängen und Systemdaten isoliert, die für die Verwaltung von Microsoft 365 verwendet werden. In Microsoft 365 werden mehrere Schutzformen implementiert, die das Risiko einer Gefährdung eines Microsoft 365-Diensts oder einer zugehörigen Anwendung minimieren. Mehrere Schutzformen verhindern auch nicht autorisierten Zugriff auf die Informationen von Mandanten oder das Microsoft 365 System selbst.

Informationen dazu, wie Microsoft die logische Isolierung von Mandantendaten innerhalb Microsoft 365 implementiert, finden Sie unter [Mandantenisolation in Microsoft 365.](microsoft-365-tenant-isolation-overview.md)