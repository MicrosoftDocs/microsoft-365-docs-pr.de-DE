---
title: Microsoft 365 jammern von Unternehmens Zugriffs Steuerelementen
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
description: Dieser Artikel enthält eine kurze Zusammenfassung über das Jammern von Enterprise-Zugriffs Steuerelementen in der Produktionsumgebung.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e1ceae1b7ddda4c2eac96cd581a612768f1461
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332664"
---
# <a name="yammer-enterprise-access-controls"></a>Jammern von Enterprise-Zugriffs Steuerelementen 

Der physische und logische Zugriff auf die Produktionsumgebung jammern ist auf eine kleine Gruppe von Personen (Infrastruktur und Betrieb) beschränkt. Wie bei anderen Microsoft 365-Ingenieuren haben Jammer Techniker keine ständigen Zugriff auf Kundendaten. Der Zugriff muss mithilfe eines Genehmigungs basierten Just-in-Time-Zugriffs Steuerungssystems angefordert werden, ähnlich wie Lockbox mit einer begrenzten Anzahl von genehmigenden Personen. Genehmigende Personen überprüfen die Anforderung (beispielsweise überprüfen, ob die Anforderung aufgrund von Bedarf, Geschäftsfall, Zeit usw. legitim ist), und genehmigen oder verweigern die Anforderung. Wenn die Anforderung genehmigt wird, wird der JIT-Zugriff für eine definierte und beschränkte Zeit gewährt. Nach Überschreiten der Zugriffszeit läuft der Zugriff automatisch ab.

Wie bei anderen Microsoft 365-Diensten verwendet jeder Zugriff auf die Produktionsumgebung von jammern mehrstufige Authentifizierung. Der gesamte Zugriffs-und Befehlsverlauf wird einem Benutzer zugeschrieben und regelmäßig vom Sicherheitsteam "jammern" protokolliert und überprüft.

Weitere Informationen zur Verwaltung und Verwaltung von jammern finden Sie unter [jammern der Administratorhilfe](https://docs.microsoft.com/yammer/yammer-landing-page).