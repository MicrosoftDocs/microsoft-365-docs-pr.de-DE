---
title: Deaktivieren von TLS 1.0 und 1.1 in Office 365 GCC High and DoD
description: Erläutert, wie Microsoft die Unterstützung für TLS 1.1 und 1.0 in GCC High- und DoD-Umgebungen in Microsoft 365 deaktiviert.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: a0b1fecc9991cd7ba4ac915d3d684d43714014af
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233751"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>Deaktivieren von TLS 1.0 und 1.1 in Office 365 GCC High and DoD

## <a name="summary"></a>Zusammenfassung

Um die neuesten Compliancestandards für das Federal Risk and Authorization Management Program (FedRAMP) einzuhalten, deaktivieren wir die Transport Layer Security (TLS)-Versionen 1.1 und 1.0 in Microsoft 365 für GCC High- und DoD-Umgebungen. Diese Änderung wurde zuvor über den Microsoft Support bei der Vorbereitung der obligatorischen Verwendung von [TLS 1.2 in Office 365 angekündigt.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

Die Sicherheit Ihrer Daten ist wichtig, und wir sind bestrebt, Transparenz über Änderungen zu gewährleisten, die sich auf Ihre Nutzung des Diensts auswirken könnten.

Obwohl die [Microsoft TLS 1.0-Implementierung](https://support.microsoft.com/help/3117336) keine bekannten Sicherheitsrisiken hat, bleiben wir bei den FedRAMP-Compliancestandards. Daher haben wir TLS 1.1 und 1.0 in Office 365 in GCC High- und DoD-Umgebungen am 15. Januar 2020 deaktiviert. Informationen zum Entfernen von TLS 1.1- und 1.0-Abhängigkeiten finden Sie im folgenden Whitepaper:

[Beheben des TLS 1.0-Problems](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>Weitere Informationen

Ab dem 15. Januar 2020 wird Office 365 in den GCC High- und DoD-Umgebungen TLS 1.1 und 1.0 nicht mehr unterstützt.

Bis zum 15. Januar 2020 sollten alle Kombinationen von Clientservern und Browserservern TLS Version 1.2 (oder höher) verwenden, um sicherzustellen, dass alle Verbindungen ohne Probleme mit Office 365-Diensten hergestellt werden können. Dies erfordert möglicherweise Updates für bestimmte Kombinationen von Clientservern und Browserservern.

Wenn Sie bis zum 15. Januar 2020 nicht auf TLS Version 1.2 (oder eine spätere Version) aktualisieren, werden Beim Versuch, eine Verbindung mit Office 365 herzustellen, Probleme auftreten. Darüber hinaus müssen Sie im Rahmen der Lösung auf TLS 1.2 (oder eine spätere Version) aktualisieren.

Sie müssen Ihre Clientcomputer aktualisieren, um sicherzustellen, dass Sie unterbrechungsfreien Zugriff auf Office 365 GCC High und DoD erhalten.

Sie müssen Anwendungen aktualisieren, die Microsoft 365-APIs über TLS 1.0 oder TLS 1.1 aufrufen, um TLS 1.2 zu verwenden. .NET 4.5 ist standardmäßig auf TLS 1.1 festgelegt. Informationen zum Aktualisieren der .NET-Konfiguration finden Sie unter Aktivieren [von TLS 1.2 (Transport Layer Security)](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)auf Clients. Weitere Informationen finden Sie unter Vorbereiten der obligatorischen Verwendung von [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

Wir wissen, dass die folgenden Clientanwendungen TLS 1.2 nicht verwenden können:

- Android 4.3 und niedrigere Versionen
- Firefox Version 5.0 und frühere Versionen
- Internet Explorer 8–10 unter Windows 7 und früheren Versionen
- Internet Explorer 10 auf Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 und frühere Versionen

Obwohl die aktuelle Analyse der Verbindungen mit Microsoft Online Services zeigt, dass die meisten Dienste und Endpunkte nur eine sehr geringe TLS 1.1- und 1.0-Nutzung feststellen, wird diese Änderung zur Verfügung gestellt, damit Sie alle betroffenen Clients oder Server nach Bedarf aktualisieren können, bevor die Unterstützung für TLS 1.1 und 1.0 endet. Wenn Sie eine lokale Infrastruktur für Hybridszenarien oder Active Directory Federation Services (AD FS) verwenden, stellen Sie sicher, dass die Infrastruktur sowohl eingehende als auch ausgehende Verbindungen unterstützen kann, die TLS 1.2 (oder höher) verwenden.

Zusätzlich zu den Ausfällen, die bei Verwendung der aufgeführten Clients, die TLS 1.2 nicht verwenden können, möglicherweise ausfälle werden, wird durch das Entfernen von TLS 1.1 und 1.0 verhindert, dass Sie das folgende Produkt von Microsoft verwenden können:

- Lync Phone

## <a name="references"></a>Informationsquellen

Im folgenden Supportartikel werden Anleitungen und Referenzen beschrieben, um sicherzustellen, dass Ihre Clients TLS 1.2 verwenden:

[Vorbereiten der obligatorischen Verwendung von TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
