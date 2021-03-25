---
title: Rückläufer in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie mehr über Backscatter und Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204024"
---
# <a name="backscatter-in-eop"></a>Rückläufer in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* sind Unzustellbarkeitsberichte (auch als Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bezeichnet), die Sie für Nachrichten erhalten, die Sie nicht gesendet haben. Spammer fälschen (spoofen) die Absender-Adresse ihrer Nachrichten und verwenden häufig echte E-Mail-Adressen, um ihren Nachrichten Glaubwürdigkeit zu verleihen. Wenn Spammer also unausweichlich Nachrichten an nicht vorhandene Empfänger senden (Spam ist ein Vorgang mit hohem Volumen), wird der Ziel-E-Mail-Server im Wesentlichen dazu verheddert, die nicht zustellbare Nachricht in einem Unzustellbarkeitsbericht an den gefälschten Absender in der Absenderadresse zurückzusendet.

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer ist EOP bemüht, Nachrichten aus zweifelhaften Quellen zu identifizieren und automatisch zu löschen, ohne einen Unndr zu generieren. Basierend auf dem volumenbasierten E-Mail-Fluss über den Dienst besteht jedoch immer die Möglichkeit, dass EOP versehentlich zurückscatter sendet.

Backscatterer.org verwaltet eine Sperrliste (auch als DNS-Sperrliste oder DNSBL bezeichnet) von E-Mail-Servern, die für das Senden von Rückscatter verantwortlich waren, und EOP-Server werden möglicherweise in dieser Liste angezeigt. Wir versuchen jedoch nicht, uns selbst aus der Backscatterer.org-Sperrliste zu entfernen, da es sich nicht um eine Liste von Spammern (nach eigenem Eingeständnis) handelt.

> [!TIP]
> Die Backscatter.org Website ( ) empfiehlt die Verwendung ihres Diensts, um eingehende E-Mails im abgesicherten Modus anstelle des Ablehnungsmodus zu überprüfen (große E-Mail-Dienste senden fast immer ein paar <http://www.backscatterer.org/?target=usage> Zurückscatter).
