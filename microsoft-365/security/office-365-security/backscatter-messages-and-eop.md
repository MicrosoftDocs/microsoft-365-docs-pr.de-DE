---
title: Backscatter in EoP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie mehr über Backscatter und Microsoft Exchange Online Schutz (EoP).
ms.openlocfilehash: e30fa27ac359ad28e042b2d4bd446d34a2e4f1e9
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209631"
---
# <a name="backscatter-in-eop"></a>Backscatter in EoP

Bei *Backscatter* handelt es sich um Unzustellbarkeitsberichte (auch als NDR-oder Unzustellbarkeitsnachrichten bezeichnet), die Sie für Nachrichten erhalten, die Sie nicht gesendet haben. Spammer fälschen die von:-Adresse Ihrer Nachrichten, und Sie verwenden häufig reale e-Mail-Adressen, um Ihren Nachrichten Glaubwürdigkeit zu verleihen. Wenn Spammer unweigerlich Nachrichten an nicht vorhandene Empfänger senden (Spam ist ein Vorgang mit hohem Volumen), wird der Ziel-e-Mail-Server im Wesentlichen dazu verleitet, die unzustellbare Nachricht in einem Unzustellbarkeitsbericht an den gefälschten Absender in der from:-Adresse zurückzugeben.

In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer ist EoP bemüht, Nachrichten aus fragwürdigen Quellen zu identifizieren und automatisch zu löschen, ohne einen Unzustellbarkeitsbericht zu generieren. Aber basierend auf den lauter Volumen-e-Mails, die durch den Dienst fließen, besteht immer die Möglichkeit, dass EoP unbeabsichtigt Backscatter sendet.

BACKSCATTERER.org verwaltet eine Sperrliste (auch als DNS-Sperrliste oder DNSBL bezeichnet) von e-Mail-Servern, die für das Senden von Backscatter zuständig waren, und EOP-Server werden möglicherweise in dieser Liste angezeigt. Wir versuchen jedoch nicht, uns aus der BACKSCATTERER.org-Sperrliste zu entfernen, da es sich nicht um eine Liste von Spammern (nach eigenem Eingeständnis) handelt.

> [!TIP]
> Die Backscatter.org-Website ( <http://www.backscatterer.org/?target=usage> ) empfiehlt die Verwendung Ihres Diensts zum Überprüfen eingehender e-Mails im abgesicherten Modus anstelle des ablehnen-Modus (große e-Mail-Dienste senden fast immer einige Backscatter).
