---
title: Erstellen von E-Mail-Regeln für Ransomware
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie E-Mail-Regeln erstellen, um Ransomware zu verhindern.
ms.openlocfilehash: 3b45af71aa26beb31e21f5db662091f46343f97d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926114"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Erstellen von E-Mail-Regeln, um Ransomware zu verhindern

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 schützt Ihr Unternehmen vor Ransomware, indem es verhindert, dass potenziell gefährliche Dateien wie JavaScript, Batch und ausführbare Dateien in Outlook geöffnet werden. Führen Sie die folgenden Schritte aus, um diese Schutzebene durch Hinzufügen von Regeln zu erhöhen, die zusätzliche Dateitypen blockieren oder warnen.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wählen Sie im Admin Center unter Admin Center [https://admin.microsoft.com](https://admin.microsoft.com) **Exchange** **aus.**
1. Wählen Sie im Menü auf der linken Seite den **Nachrichtenfluss aus.**
1. Wählen Sie auf der Registerkarte "Regeln" den Pfeil neben dem Pluszeichen (+) aus, und wählen Sie dann **"Neue Regel erstellen" aus.**
1. Geben Sie **auf der Seite "Neue** Regel" einen Namen für die Regel ein, scrollen Sie nach unten, und wählen Sie dann **"Weitere Optionen" aus.**
1. Under **Apply this rule if**, select Any **attachment**, and then select file extension includes **these words**.
1. Geben Sie in das Feld **unter**"Wörter oder Ausdrücke angeben" die Dateierweiterungen ein, auf die die Regel angewendet werden soll, z. B. Dateierweiterungen, die Makros enthalten können. Verwenden Sie das Pluszeichen (+), um sie eins nach dem anderen hinzuzufügen.

    Weitere Informationen zu Dateitypen finden Sie unter ["Schutz vor Ransomware".](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)

1. Scrollen Sie nach unten, um Ihre Liste zu überprüfen, und wählen Sie dann **OK aus.**
1. On the **new rule** page, choose **add condition**, and then choose a condition under Do **the following**.
1. Sie haben viele Regeloptionen zur Auswahl, aber in diesem Beispiel wird der Empfänger mit einer **Nachricht benachrichtigt.**
1. Geben Sie den Nachrichtentext für Ihre Benachrichtigung ein, und wählen Sie dann **OK aus.**
1. Optional: Wählen Sie auf der **Seite** "Neue Regel" die Option "Ausnahme hinzufügen" **aus,** und geben Sie alle Details für Ausnahmen zu Ihrer Regel ein, z. B. Nachrichten von vertrauenswürdigen Absendern.
1. Wählen Sie auf der Seite "Neue Regel" die Option **"Speichern"** aus, und überprüfen Sie die bereitgestellten Regelzusammenfassungsinformationen.