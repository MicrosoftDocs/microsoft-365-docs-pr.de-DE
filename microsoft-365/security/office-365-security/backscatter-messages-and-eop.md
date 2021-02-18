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
description: In diesem Artikel erfahren Sie mehr über Backscatter and Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286969"
---
# <a name="backscatter-in-eop"></a>Rückläufer in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*Rückläufer sind* Unzustellbarkeitsberichte (auch NDRs oder Unzustellbarkeitsnachrichten bezeichnet), die Sie für Nachrichten erhalten, die Sie nicht gesendet haben. Spammer forieren die "Von"-Adresse ihrer Nachrichten (spoofing) und verwenden häufig echte E-Mail-Adressen, um ihre Nachrichten zu täuschen. Wenn Spammer also unausweichlich Nachrichten an nicht vorhandene Empfänger senden (Spam ist ein Vorgang mit hohem Volumen), wird der Ziel-E-Mail-Server im Wesentlichen dazu verfälscht, die nicht zustellbare Nachricht in einem Unzustellbarkeitsbericht an den gefälschten Absender in der "Von:"-Adresse zurücksendet.

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer unterniert EOP alle Anstrengungen, Nachrichten aus ungernen Quellen zu identifizieren und im Hintergrund zu löschen, ohne einen NDR zu generieren. Aber basierend auf der schr en Volume-E-Mail, die über den Dienst fließt, besteht immer die Möglichkeit, dass EOP versehentlich einen Rückscatter sendet.

Backscatterer.org verwaltet eine Sperrliste (auch als DNS-Sperrliste oder DNSBL bezeichnet) von E-Mail-Servern, die für das Senden von Rückscattern verantwortlich waren, und die EOP-Server werden möglicherweise in dieser Liste angezeigt. Wir versuchen jedoch nicht, uns selbst aus der Backscatterer.org-Sperrliste zu entfernen, da es sich nicht um eine Liste von Spammern handelt (nach eigenem Eingeständnis).

> [!TIP]
> Die Backscatter.org Website ( ) empfiehlt die Verwendung ihres Diensts, um eingehende E-Mails im abgesicherten Modus anstelle des Zurückweisens zu überprüfen (große E-Mail-Dienste senden fast immer einen <http://www.backscatterer.org/?target=usage> Rückscatter).
