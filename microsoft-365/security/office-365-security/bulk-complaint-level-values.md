---
title: Massenwerte für Reklamations Ebenen, Massenversender, BCL-Ebenen, Funktionsweise von BCL, BCL-Bewertungen, Antispam, Antispam-Header, Massen-e-Mail-Filterung, Massen-e-Mail-Stopp
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Informationen zu BCL-Werten (Bulk Complaint Level) in Office 365.
ms.openlocfilehash: 6f9314a5b96dbd641e461dfb564ed8605372a949
ms.sourcegitcommit: b0396171d24c6298b809b43bb109d3afed4de5b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37451097"
---
# <a name="bulk-complaint-level-values"></a>BCL-Werte (Bulk Complaint Level)

Versender von Massen-E-Mails arbeiten mit verschiedenen Sendemustern, Inhalterstellungsverfahren und Listenbeschaffungsarten. Einige von ihnen sind gute Absender, die erwünschte Nachrichten mit relevantem Inhalt an Ihre Abonnenten senden. Diese Nachrichten führen zu wenigen Beschwerden von Empfängern. Andere Absender verwenden unerwünschte Nachrichten, die den Kriterien für Spam sehr nahekommen und zu vielen Beschwerden von Empfängern führen.

Um zwischen diesen Typen von Massen-E-Mail-Absendern zu unterscheiden, werden ihren Nachrichten BCL-Bewertungen (Bulk Complaint Level) zugewiesen. BCL-Bewertungen können zwischen 1 und 9 liegen - je nachdem, wie wahrscheinlich es ist, dass die Massen-E-Mail zu Beschwerden führen. Ein Absender mit dem BCL-Wert 9 wird wahrscheinlich mehr Beschwerden von Empfängern erhalten, was mit einem BCL-Wert von 3 wahrscheinlich nicht der Fall ist. Microsoft arbeitet sowohl mit internen Quellen als auch mit Quellen von Drittanbietern, um die Absender von Massen-E-Mails zu identifizieren und den passenden BCL-Wert zu bestimmen. Weitere Informationen zu dieser Nachrichtenkopfzeile finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md).

Da eine Massenwerbung mit einer Bewertung von 9 wahrscheinlich zu Reklamationen führen wird, ist die Standard-BCL 7. Dies bedeutet, dass Massen-e-Mails erst dann akzeptiert werden, wenn die Reklamations Stufe 7 und die e-Mail danach nicht mehr akzeptiert werden. Je niedriger die Bewertung, desto weniger Massen-e-Mails werden akzeptiert. Wenn Ihre Benutzer sind und ihre Arbeit für Massen-e-Mails vertraulich ist und ihre BCL auf 4 festgelegt ist, werden keine Massen-e-Mails mit einer höheren BCL als 4 akzeptiert.

Sie können BCL-Werte verwenden, um die für Ihre Organisation gewünschte Massenfilterungsebene festzulegen, indem Sie die Schritte unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md) befolgen.

In der folgenden Tabelle werden die derzeit verwendeten BCL-Werte beschrieben.

|||
|:-----|:-----|
|**BCL-Wert**|**Beschreibung**|
|0|Die Nachricht stammt nicht von einem Massen-E-Mail-Absender.|
|1, 2, 3|Die Nachricht stammt von einem Massen-E-Mail-Absender, aber führt zu wenigen Beschwerden.|
|4, 5, 6, 7|Die Nachricht stammt von einem Massen-E-Mail-Absender und führt zu einer gemischten Anzahl von Beschwerden.|
|8, 9|Die Nachricht stammt von einem Massen-E-Mail-Absender und führt zu einer hohen Anzahl von Beschwerden.|
