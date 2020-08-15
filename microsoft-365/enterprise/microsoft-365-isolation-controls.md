---
title: Microsoft 365-Isolations Steuerelemente
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
description: Erfahren Sie, wie Isolierungs Steuerelemente in Microsoft 365 funktionieren, sodass Dienste bei Bedarf zusammenarbeiten oder autonom bleiben können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15805c2fb57cbcaa33c5ba24dcbcaa378feea4bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690619"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365-Isolations Steuerelemente 

Microsoft arbeitet kontinuierlich daran, sicherzustellen, dass die mehrmandantenfähige Architektur von Microsoft 365 auf Unternehmensebene Sicherheit, Vertraulichkeit, Datenschutz, Integrität, lokale, internationale und Verfügbarkeits [Standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)unterstützt. Die Skalierung und der Umfang der von Microsoft bereitgestellten Dienste machen es schwierig und nicht wirtschaftlich, Microsoft 365 mit erheblicher menschlicher Interaktion zu verwalten. Microsoft 365-Dienste werden über mehrere global verteilte Rechenzentren bereitgestellt, die jeweils hoch automatisiert sind und nur wenige Vorgänge erfordern, die einen menschlichen Touch oder Zugriff auf Kunden Inhalte benötigen. Unsere Mitarbeiter unterstützen diese Dienste und Rechenzentren mithilfe von automatisierten Tools und hochgradig sicherem Remotezugriff. 

Microsoft 365 besteht aus mehreren Diensten, die wichtige Geschäftsfunktionen bereitstellen und zur gesamten Microsoft 365-Erfahrung beitragen. Jeder dieser Dienste ist in sich geschlossen und für die Integration in einen anderen Dienst konzipiert.

Microsoft 365 ist mit den folgenden Grundsätzen konzipiert:

 - ** [Dienstorientierte Architektur](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):** entwerfen und entwickeln von Software in Form von interoperablen Diensten, die eine klar definierte Geschäftsfunktionalität bieten.
 - **[Operational Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872):** ein Framework, in dem das Wissen über die verschiedenen Funktionen von Microsoft integriert wird, einschließlich des Microsoft- [Sicherheits Entwicklungslebenszyklus](https://www.microsoft.com/sdl/default.aspx), des [Microsoft Security Response Centers](https://technet.microsoft.com/library/dn440717.aspx)und des tiefen Bewusstseins für die Cyber-Bedrohungslandschaft.

Microsoft 365-Dienste arbeiten miteinander zusammen, werden jedoch so konzipiert und implementiert, dass Sie unabhängig voneinander als autonome Dienste bereitgestellt und betrieben werden können. Microsoft trennt Aufgaben und Bereiche der Verantwortung für Microsoft 365, um Möglichkeiten für unbefugte oder unbeabsichtigte Änderungen oder den Missbrauch von Ressourcen der Organisation zu verringern. Microsoft 365 Teams haben Rollen als Teil eines umfassenden rollenbasierten Zugriffssteuerungsmechanismus definiert.

## <a name="customer-content-isolation"></a>Isolierung von Kundeninhalten

Alle Kunden Inhalte in einem Mandanten sind von anderen Mandanten und von Betriebs-und Systemdaten isoliert, die in der Verwaltung von Microsoft 365 verwendet werden. In Microsoft 365 werden mehrere Schutzformen implementiert, die das Risiko einer Gefährdung eines Microsoft 365-Diensts oder einer zugehörigen Anwendung minimieren. Mehrere Schutzformen verhindern auch den unbefugten Zugriff auf die Informationen von Mandanten oder das Microsoft 365-System selbst.

Informationen dazu, wie Microsoft die logische Isolierung von Mandantendaten in Microsoft 365 implementiert, finden Sie unter [Mandanten Isolierung in Microsoft 365](microsoft-365-tenant-isolation-overview.md).
