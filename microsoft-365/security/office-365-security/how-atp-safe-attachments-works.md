---
title: Funktionsweise Office 365 sicherer ATP-Anlagen
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Das Feature "sichere Anlagen" bietet eine Zeit-für-Klick-Überprüfung von e-Mail-Anlagen. Verwenden Sie sichere Anlagen, um Ihre Organisation vor böswilligen Dateien zu schützen, die Personen in e-Mails senden oder empfangen.
ms.openlocfilehash: 14db6bc51f2017388639eb4270d7c5fc67b4ff7d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081252"
---
# <a name="how-ffice-365-atp-safe-attachments-works"></a>Funktionsweise von ffice 365 ATP-Sicherheitsanlagen

## <a name="how-it-works"></a>Funktionsweise

Das Feature "ATP-sichere Anlagen" prüft e-Mail-Anlagen für Personen in Ihrer Organisation. Wenn eine Richtlinie für ATP-sichere Anlagen vorhanden ist und von dieser Richtlinie erfasste Personen Ihre e-Mails in Office 365 anzeigen, werden Ihre e-Mail-Anlagen überprüft, und es werden entsprechende Aktionen basierend auf Ihren Richtlinien für ATP-sichere Anlagen ausgeführt. Je nachdem, wie Ihre Richtlinien definiert sind, können Personen weiter arbeiten, ohne jemals zu wissen, dass Sie bösartige Dateien gesendet haben.
  
Hier sind zwei Beispiele für sichere ATP-Anhänge bei der Arbeit.
  
- **Beispiel 1: e-Mail-Anlage** Angenommen, Lee erhält eine e-Mail-Nachricht mit einer Anlage. Es ist für Lee nicht offensichtlich, ob diese Anlage sicher ist oder tatsächlich Schadsoftware enthält, die die Benutzeranmeldeinformationen von Lee stehlen soll. In der Organisation von Lees hat ein Sicherheitsadministrator vor einigen Tagen eine Richtlinie für ATP-sichere Anlagen definiert. Mit dem Feature "ATP-sichere Anlagen" wird die e-Mail-Anlage geöffnet und in einer virtuellen Umgebung getestet, bevor Sie von Lee empfangen wird. Wenn die Anlage als bösartig eingestuft wird, wird Sie automatisch entfernt. Wenn die Anlage sicher ist, wird sie erwartungsgemäß geöffnet, wenn Lee darauf klickt.

- **Beispiel 2: Datei in SharePoint Online** Angenommen, Jean hat eine Datei erhalten und in SharePoint Online in eine Bibliothek hochgeladen. Jean teilt den Link mit der Datei mit dem Rest des Teams, ohne zu wissen, dass es sich bei der Datei tatsächlich um bösartige Dateien handelt. Glücklicherweise erkennt [ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md) die bösartige Datei und blockiert Sie. Einige Tage später wechselt Chris zum Öffnen des Dokuments. Obwohl Chris sehen kann, dass die Datei vorhanden ist, kann Chris Sie nicht öffnen oder freigeben, wodurch der Computer von Chris und andere Personen vor der schädlichen Datei geschützt werden.

Richtlinien für ATP-sichere Anlagen können auf bestimmte Personen oder Gruppen in Ihrer Organisation oder auf Ihre gesamte Domäne angewendet werden. Darüber hinaus können Richtlinien für ATP-sichere Anlagen so konfiguriert werden, dass Platzhalter Anlagen verwendet werden, während tatsächliche Anlagen gescannt werden. Weitere Informationen finden Sie unter **[Einrichten von Richtlinien für sichere ATP-Anlagen in Office 365](set-up-atp-safe-attachments-policies.md)**.

> [!NOTE]
> Die Überprüfung der ATP-Tresoranlagen erfolgt in derselben Region, in der sich Ihre Office 365 Daten befinden. Weitere Informationen zur Geografie des Rechenzentrums finden Sie unter [wo befinden sich Ihre Daten?](https://products.office.com/where-is-your-data-located?geo=All) 

