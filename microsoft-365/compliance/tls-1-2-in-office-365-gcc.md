---
title: Deaktivieren von TLS 1.0 und 1.1 in Microsoft 365 GCC High and DoD
description: Erläutert, wie Microsoft die Unterstützung für TLS 1.1 und 1.0 in GCC High- und DoD-Umgebungen in Microsoft 365 deaktiviert.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919341"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a>Deaktivieren von TLS 1.0 und 1.1 in Microsoft 365 GCC High and DoD

## <a name="summary"></a>Zusammenfassung

Um die neuesten Compliancestandards für das Federal Risk and Authorization Management Program (FedRAMP) zu erfüllen, deaktivieren wir die Transport Layer Security (TLS)-Versionen 1.1 und 1.0 in Microsoft 365 für GCC High- und DoD-Umgebungen. Diese Änderung wurde zuvor über den Microsoft Support in Vorbereitung auf die obligatorische Verwendung von [TLS 1.2 in Office 365 angekündigt.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

Die Sicherheit Ihrer Daten ist wichtig, und wir setzen uns für Transparenz bei Änderungen ein, die sich auf Ihre Nutzung des Diensts auswirken könnten.

Obwohl die [Microsoft TLS 1.0-Implementierung](https://support.microsoft.com/help/3117336) keine bekannten Sicherheitsrisiken hat, bleiben wir den FedRAMP-Compliancestandards verpflichtet. Daher haben wir TLS 1.1 und 1.0 in Microsoft 365 in GCC High- und DoD-Umgebungen am 15. Januar 2020 deaktiviert. Informationen zum Entfernen von TLS 1.1- und 1.0-Abhängigkeiten finden Sie im folgenden Whitepaper:

[Beheben des TLS 1.0-Problems](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>Weitere Informationen

Ab dem 15. Januar 2020 deaktiviert Microsoft 365 in den GCC High- und DoD-Umgebungen TLS 1.1 und 1.0.

Bis zum 15. Januar 2020 sollten alle Kombinationen von Clientservern und Browserservern TLS Version 1.2 (oder höher) verwenden, um sicherzustellen, dass alle Verbindungen ohne Probleme mit Microsoft 365 hergestellt werden können. Dies kann Updates für bestimmte Kombinationen von Clientservern und Browserservern erfordern.

Für SharePoint und OneDrive müssen Sie .NET aktualisieren und konfigurieren, um TLS 1.2 zu unterstützen. Weitere Informationen finden Sie unter [Aktivieren von TLS 1.2 auf Clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

Sie müssen Ihre Clientcomputer aktualisieren, um sicherzustellen, dass Sie den unterbrechungsfreien Zugriff auf Office 365 GCC High und DoD beibehalten.

Sie müssen Anwendungen aktualisieren, die Microsoft 365-APIs über TLS 1.0 oder TLS 1.1 aufrufen, um TLS 1.2 zu verwenden. .NET 4.5 ist standardmäßig auf TLS 1.1 festgelegt. Informationen zum Aktualisieren der .NET-Konfiguration finden Sie unter [Aktivieren von Transport Layer Security (TLS) 1.2 auf Clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client). Weitere Informationen finden Sie unter [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

Wir wissen, dass die folgenden Clientanwendungen TLS 1.2 nicht verwenden können:

- Android 4.3 und niedrigere Versionen
- Firefox Version 5.0 und frühere Versionen
- Internet Explorer 8–10 unter Windows 7 und früheren Versionen
- Internet Explorer 10 auf Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 und frühere Versionen

Obwohl die aktuelle Analyse von Verbindungen mit Microsoft Online-Diensten zeigt, dass die Meisten Dienste und Endpunkte nur sehr wenig TLS 1.1 und 1.0 verwenden, wird diese Änderung zur Verfügung gestellt, damit Sie alle betroffenen Clients oder Server nach Bedarf aktualisieren können, bevor die Unterstützung für TLS 1.1 und 1.0 endet. Wenn Sie eine lokale Infrastruktur für Hybridszenarien oder Active Directory Federation Services (AD FS) verwenden, stellen Sie sicher, dass die Infrastruktur sowohl eingehende als auch ausgehende Verbindungen unterstützen kann, die TLS 1.2 (oder eine neuere Version) verwenden.

Zusätzlich zu den Ausfällen, die bei Verwendung der aufgeführten Clients, die TLS 1.2 nicht verwenden können, möglicherweise zu einem Ausfall kommen, wird durch das Entfernen von TLS 1.1 und 1.0 verhindert, dass Sie das folgende Microsoft-Produkt verwenden können:

- Lync-Telefon

## <a name="references"></a>Informationsquellen

Anleitungen und Verweise, mit deren Hilfe Sie sicherstellen können, dass Ihre Clients TLS 1.2 verwenden, finden Sie unter [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).