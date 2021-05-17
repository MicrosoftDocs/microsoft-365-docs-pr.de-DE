---
title: Erstellen von E-Mail-Regeln für Ransomware
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie E-Mail-Regeln erstellen, um Ransomware zu verhindern.
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580498"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Erstellen von E-Mail-Regeln zur Verhinderung von Ransomware

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 schützt Ihr Unternehmen vor Ransomware, indem verhindert wird, dass potenziell gefährliche Dateien wie JavaScript, Batch und ausführbare Dateien in einem Outlook. Führen Sie die folgenden Schritte aus, um dieses Schutzniveau zu erhöhen, indem Sie Regeln hinzufügen, die Sie vor zusätzlichen Dateitypen blockieren oder warnen.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wählen Sie im Admin Center unter [https://admin.microsoft.com](https://admin.microsoft.com) die **Exchange** unter Admin **Center aus.**
1. Wählen Sie im Menü auf der linken Seite **E-Mail-Fluss aus.**
1. Wählen Sie auf der Registerkarte Regeln den Pfeil neben dem Pluszeichen (+) aus, und wählen Sie dann **Neue Regel erstellen aus.**
1. Geben Sie **auf** der Seite neue Regel einen Namen für Ihre Regel ein, scrollen Sie nach unten, und wählen Sie **dann Weitere Optionen aus.**
1. Wählen **Sie unter Diese Regel anwenden, wenn**, alle Anlagen **aus,** und wählen Sie dann **Dateierweiterung mit den folgenden Wörtern aus.**
1. Geben Sie im Feld unter Angeben von Wörtern oder Ausdrücken die Dateierweiterungen **ein,** auf die die Regel angewendet werden soll, z. B. Dateierweiterungen, die Makros enthalten können. Verwenden Sie das Pluszeichen (+), um sie eins nach dem anderen hinzuzufügen.

    Weitere Informationen zu Dateitypen finden Sie unter [Schützen vor Ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).

1. Scrollen Sie nach unten, um Ihre Liste zu überprüfen, und wählen Sie dann **OK aus.**
1. Wählen Sie **auf der** Seite neue Regel **bedingung** hinzufügen aus, und wählen Sie dann eine Bedingung unter Do **the following** aus.
1. Sie haben viele Regeloptionen zur Auswahl, aber in diesem Beispiel wählen wir den Empfänger mit einer **Nachricht benachrichtigen aus.**
1. Geben Sie den Nachrichtentext für Ihre Benachrichtigung ein, und wählen Sie dann **OK aus.**
1. Optional: Wählen Sie auf der **Neuen** Regelseite Ausnahme hinzufügen **aus,** und geben Sie alle Details für Ausnahmen zu Ihrer Regel ein, z. B. Nachrichten von vertrauenswürdigen Absendern.
1. Wählen Sie auf der Seite neue Regel **Speichern** aus, und überprüfen Sie die bereitgestellten Regelzusammenfassungsinformationen.