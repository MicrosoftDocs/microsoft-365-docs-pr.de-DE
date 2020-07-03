---
title: Veraltern von TLS 1,0 und 1,1 in Office 365 gcc High und DoD
description: Erläutert, wie Microsoft das Datum vorwärts verschiebt, um die Unterstützung für TLS 1,1 und 1,0 in gcc-High-und DoD-Umgebungen in Office 365 zu beenden und die Verwendung von TLS 1,2 vorzubereiten.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
ms.reviewer: lobrion
appliesto:
- Office 365 Business
ms.openlocfilehash: f61c0a809c4666981ee0f2d67eea21474b83a675
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024825"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>Veraltern von TLS 1,0 und 1,1 in Office 365 gcc High und DoD

> [!IMPORTANT]
> Die Welt befindet sich mitten in einer Pandemie, und wir bei Microsoft sind uns der Auswirkungen auf unsere Kunden und Partner bewusst. Um unsere gewerblichen Kunden zu entlasten, haben wir jede Abschreibungserzwingung von TLS 1.0 und 1.1 vorübergehend ausgesetzt. Nach der Stabilisierung der aktuellen Krise wird ein Update auf einem überarbeiteten Zeitplan gesendet. (Dieser Artikel wird überarbeitet, um die Änderung widerzuspiegeln.)

## <a name="summary"></a>Zusammenfassung

Um die neuesten Compliance-Standards für das Federal Risk and Authorization Management Program (FedRAMP) einzuhalten, werden Transport Layer Security (TLS)-Versionen 1,1 und 1,0 in Microsoft Office 365 für gcc-High-und DoD-Umgebungen veraltet. Diese Änderung wurde zuvor über den Microsoft-Support [zur Vorbereitung der obligatorischen Verwendung von TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)angekündigt.

Wir verstehen, dass die Sicherheit Ihrer Daten wichtig ist, und wir setzen uns für Transparenz bei Änderungen ein, die sich auf Ihre Nutzung des Diensts auswirken könnten.

Obwohl die [Microsoft TLS 1,0-Implementierung](https://support.microsoft.com/help/3117336) keine bekannten Sicherheitsrisiken aufweist, werden wir weiterhin den FedRAMP-Konformitätsstandards verpflichtet. Daher werden TLS 1,1 und 1,0 in Office 365 in gcc High-und DoD-Umgebungen ab dem 15. Januar 2020 veraltet sein. Informationen zum Entfernen von TLS 1,1-und 1,0-Abhängigkeiten finden Sie in folgendem Whitepaper:

[Lösen des TLS 1,0-Problems](https://www.microsoft.com/download/details.aspx?id=55266)

Bei der Vorbereitung auf diese Änderung für TLS 1,1 und 1,0 sollten Sie stattdessen die TLS-Version 1,2 verwenden. Weitere Informationen finden Sie unter [vorbereiten auf die obligatorische Verwendung von TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

## <a name="more-information"></a>Weitere Informationen

Ab dem 15. Januar 2020 werden Office 365 in der gcc-hoch-und der DoD-Umgebung TLS 1,1 und 1,0 veraltet.

Bis zum 15. Januar 2020 sollten alle Kombinationen von Clientservern und Browser Servern TLS-Version 1,2 (oder eine höhere Version) verwenden, um sicherzustellen, dass alle Verbindungen ohne Probleme für Office 365 Dienste ausgeführt werden können. Dies erfordert möglicherweise Aktualisierungen für bestimmte Kombinationen von Clientservern und Browser Servern.

Wenn Sie nicht auf TLS-Version 1,2 (oder eine höhere Version) bis zum 15. Januar 2020 aktualisieren, treten Probleme auf, wenn Sie versuchen, eine Verbindung mit Office 365 herzustellen. Darüber hinaus müssen Sie als Teil der Lösung auf TLS 1,2 (oder eine höhere Version) aktualisieren.

Wir wissen, dass die folgenden Clients TLS 1,2 nicht verwenden können:

- Android 4.3 und niedrigere Versionen
- Firefox Version 5.0 und frühere Versionen
- Internet Explorer 8 – 10 auf Windows 7 und früheren Versionen
- Internet Explorer 10 auf Windows Phone 8,0
- Safari 6.0.4/OS X 10.8.4 und frühere Versionen

Es wird empfohlen, dass Sie Ihre Clients aktualisieren, um sicherzustellen, dass Sie einen unterbrechungsfreien Zugriff auf Office 365 gcc High und DoD gewährleisten.

Obwohl die aktuelle Analyse der Verbindungen mit Microsoft Online Services zeigt, dass die meisten Dienste und Endpunkte nur sehr wenig TLS 1,1 und 1,0 verwenden, wird diese Änderung mitgeteilt, sodass Sie alle betroffenen Clients oder Server bei Bedarf aktualisieren können, bevor die Unterstützung für TLS 1,1 und 1,0 endet. Wenn Sie eine lokale Infrastruktur für Hybrid Szenarien oder Active Directory Verbunddienste (AD FS) verwenden, stellen Sie sicher, dass die Infrastruktur sowohl eingehende als auch ausgehende Verbindungen unterstützenkann, die TLS 1,2 (oder eine höhere Version) verwenden.

Zusätzlich zu den Ausfällen, die bei der Verwendung der aufgeführten Clients auftreten, die TLS 1,2 nicht verwenden können, wird das Entfernen von TLS 1,1 und 1,0 verhindert, dass Sie das folgende Microsoft-Produkt verwenden können:

- Lync-Telefon

## <a name="references"></a>Informationsquellen

Im folgenden Support Artikel werden Anleitungen und Verweise beschrieben, mit denen Sie sicherstellen können, dass Ihre Clients TLS 1,2 verwenden:

[Vorbereiten der obligatorischen Verwendung von TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
