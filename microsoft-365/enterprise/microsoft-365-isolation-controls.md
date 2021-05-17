---
title: Microsoft 365-Isolationssteuerelemente
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
description: Erfahren Sie, wie Isolationssteuerelemente innerhalb Microsoft 365 funktionieren, sodass Dienste bei Bedarf zusammenarbeiten oder eigenständig bleiben können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918942"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365-Isolationssteuerelemente 

Microsoft arbeitet kontinuierlich daran, sicherzustellen, dass die mehrstufige Architektur von Microsoft 365 Sicherheits-, Vertraulichkeits-, Datenschutz-, Integritäts-, lokalen, internationalen und Verfügbarkeitsstandards auf [Unternehmensebene unterstützt.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) Die Skalierung und der Umfang der von Microsoft bereitgestellten Dienste machen es schwierig und nicht wirtschaftlicher, die Microsoft 365 mit erheblichen menschlichen Interaktionen zu verwalten. Microsoft 365 dienste werden über mehrere global verteilte Rechenzentren bereitgestellt, die jeweils hochautomatisiert sind und nur wenige Vorgänge erfordern, die eine menschliche Note oder zugriff auf Kundeninhalte erfordern. Unsere Mitarbeiter unterstützen diese Dienste und Rechenzentren mit automatisierten Tools und hochgradig sicherem Remotezugriff. 

Microsoft 365 besteht aus mehreren Diensten, die wichtige Geschäftsfunktionen bereitstellen und zur gesamten Microsoft 365 beitragen. Jeder dieser Dienste ist eigenständiger und so konzipiert, dass er miteinander integriert wird.

Microsoft 365 ist mit den folgenden Prinzipien entworfen:

 - **[Serviceorientierte Architektur:](/previous-versions/aa480021(v=msdn.10))Entwerfen** und Entwickeln von Software in Form von interoperablen Diensten, die definierte Geschäftsfunktionen bereitstellen.
 - **Betriebssicherheitssicherung: [](https://www.microsoft.com/download/details.aspx?id=40872)** ein Framework, das das wissen, das durch verschiedene Funktionen gewonnen wird, die für Microsoft einzigartig sind, z. B. den Microsoft [Security Development Lifecycle,](https://www.microsoft.com/sdl/default.aspx)das [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)und ein tiefes Bewusstsein für die Bedrohungslandschaft der Cybersicherheit.

Microsoft 365 dienste arbeiten miteinander, sind jedoch so konzipiert und implementiert, dass sie unabhängig voneinander als autonome Dienste bereitgestellt und betrieben werden können. Microsoft trennt Aufgaben und Verantwortungsbereiche für Microsoft 365, um die Möglichkeiten für nicht autorisierte oder unbeabsichtigte Änderungen oder Missbrauch der Ressourcen der Organisation zu verringern. Microsoft 365 Teams haben Rollen als Teil eines umfassenden rollenbasierten Zugriffssteuerungsmechanismus definiert.

## <a name="customer-content-isolation"></a>Isolation von Kundeninhalten

Alle Kundeninhalte in einem Mandanten sind von anderen Mandanten und von Betriebs- und Systemdaten isoliert, die in der Verwaltung von Microsoft 365. In Microsoft 365 werden mehrere Schutzformen implementiert, die das Risiko einer Gefährdung eines Microsoft 365-Diensts oder einer zugehörigen Anwendung minimieren. Mehrere Schutzformen verhindern außerdem den nicht autorisierten Zugriff auf die Informationen von Mandanten oder Microsoft 365 System selbst.

Informationen dazu, wie Microsoft die logische Isolation von Mandantendaten innerhalb von Microsoft 365 implementiert, finden Sie unter [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).