---
title: Erstellen von e-Mail-Regeln für Ransomware
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie e-Mail-Regeln zum Verhindern von Ransomware erstellen.
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701933"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Erstellen von e-Mail-Regeln zum Verhindern von Ransomware

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 hilft, Ihr Unternehmen vor Ransomware zu schützen, indem verhindert wird, dass potenziell gefährliche Dateien wie JavaScript, Batch und ausführbare Dateien in Outlook geöffnet werden. Führen Sie die folgenden Schritte aus, um diesen Schutzgrad zu verbessern, indem Sie Regeln hinzufügen, mit denen Sie zusätzliche Dateitypen blockieren oder warnen.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wählen Sie im Admin Center [https://admin.microsoft.com](https://admin.microsoft.com) unter **Admin** Centers die Option **Exchange** aus.
1. Wählen Sie im Menü auf der linken Seite **Nachrichtenfluss** aus.
1. Klicken Sie auf der Registerkarte Regeln auf den Pfeil neben dem Pluszeichen (+), und wählen Sie dann **neue Regel erstellen** aus.
1. Geben Sie auf der Seite **neue Regel** einen Namen für die Regel ein, Scrollen Sie nach unten, und wählen Sie dann **Weitere Optionen** aus.
1. Wählen Sie unter **diese Regel anwenden, wenn** **eine Anlage** aus, und wählen Sie dann **Dateierweiterung enthält diese Wörter** aus.
1. Geben Sie im Feld unter **Geben Sie Wörter oder Ausdrücke angeben** die Dateierweiterungen ein, auf die die Regel angewendet werden soll, beispielsweise Dateierweiterungen, die Makros enthalten können. Verwenden Sie das Pluszeichen (+), um Sie einzeln hinzuzufügen.

    Erfahren Sie mehr über Dateitypen, indem Sie [Protect gegen Ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)lesen.

1. Scrollen Sie nach unten, um Ihre Liste zu überprüfen, und wählen Sie dann **OK**.
1. Wählen Sie auf der Seite **neue Regel** die Option **Bedingung hinzufügen** aus, und wählen Sie dann unter **gehen Sie folgendermaßen** eine Bedingung aus.
1. Sie haben viele Regeloptionen, aus denen Sie auswählen können, in diesem Beispiel wird **der Empfänger jedoch mit einer Nachricht benachrichtigt**.
1. Geben Sie den Nachrichtentext für Ihre Benachrichtigung ein, und wählen Sie dann **OK** aus.
1. Optional: Wählen Sie auf der Seite **neue Regel** die Option **Ausnahme hinzufügen** aus, und geben Sie alle Details für Ausnahmen für Ihre Regel ein, beispielsweise Nachrichten von vertrauenswürdigen Absendern.
1. Wählen Sie auf der Seite neue Regel die Option **Speichern** aus, und überprüfen Sie die bereitgestellten Informationen zur Regel Zusammenfassung.