---
title: Rückläufernachrichten und EOP
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
description: Backscatter-Nachrichten sind automatische Bounce-Nachrichten, die an gefälschte e-Mail-Adressen gesendet werden. Die Rückläufer-DNSBL identifiziert Server, die Rück Streu Nachrichten senden (die viele legitime e-Mail-Quellen enthalten können). Da es sich nicht um eine Spammer-Liste handelt, versuchen wir nicht, uns selbst aus dem BACKSCATTERER-DNSBL zu entfernen.
ms.openlocfilehash: f6e8398565837f7a380c8a6a5c4cd8de422cc215
ms.sourcegitcommit: ca4ce9e8c7e4b433608cd059857740ffd5a472c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2019
ms.locfileid: "40840164"
---
# <a name="backscatter-messages-and-eop"></a>Rückläufernachrichten und EOP

Bei Rück *Läufer Nachrichten* handelt es sich um Unzustellbarkeitsberichte (auch als NDR oder Unzustellbarkeitsnachrichten bezeichnet), die Sie für Nachrichten erhalten, die Sie nicht gesendet haben. Spammer fälschen die von:-Adresse Ihrer Nachrichten, und Sie verwenden häufig reale e-Mail-Adressen, um Ihren Nachrichten Glaubwürdigkeit zu verleihen. Wenn Sie also unweigerlich Nachrichten an nicht vorhandene Empfänger senden (Spam ist ein Vorgang mit hohem Volumen), antwortet der Ziel-e-Mail-Server möglicherweise pflichtgemäß mit einem NDR, der an den gefälschten Absender in der von: address gesendet wird.

Exchange Online Protection (EoP) unternimmt alle Anstrengungen, um Nachrichten aus fragwürdigen Quellen zu identifizieren und automatisch zu löschen, ohne einen Unzustellbarkeitsbericht zu generieren. Aber basierend auf der reinen Volumen-e-Mail, die den Dienst durchläuft, besteht immer die Möglichkeit, dass EoP unbeabsichtigt Rück Streu Nachrichten sendet.

BACKSCATTERER.org verwaltet eine Sperrliste (auch als DNS-Sperrliste oder DNSBL bezeichnet) von e-Mail-Servern, die für das Senden von Backscatter-Nachrichten zuständig waren, und EOP-Server werden möglicherweise in dieser Liste angezeigt. Wir versuchen jedoch nicht, uns aus der BACKSCATTERER.org-Sperrliste zu entfernen, da es sich nicht um eine Liste von Spammern (nach eigenem Eingeständnis) handelt.

> [!TIP]
> Entsprechend der Backscatter. or-Website (`http://www.backscatterer.org/?target=usage`) empfehlen Sie, ihren Dienst zu verwenden, um eingehende e-Mails im abgesicherten Modus anstelle des ablehnen-Modus zu überprüfen (große e-Mail-Dienste senden fast immer einige Backscatter-Nachrichten).
