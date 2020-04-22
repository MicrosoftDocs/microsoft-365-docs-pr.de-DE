---
title: Quarantäne in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Quarantäne in Microsoft 365 hält potenziell gefährliche oder unerwünschte Nachrichten. Administratoren und Endbenutzer können auf die Quarantäne zugreifen.
ms.openlocfilehash: 2e2a83bc2ff2d57cf3310e2cb17a656683dbed47
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634436"
---
# <a name="quarantine-email-messages"></a>E-Mail-Nachrichten isolieren

Wenn Sie ein Microsoft 365-Kunde mit Postfächern in Exchange Online oder ein eigenständiger Exchange Online Schutz-Kunde (EoP) ohne Exchange Online Postfächer sind, ist die Quarantäne verfügbar, um potenziell gefährliche oder unerwünschte Nachrichten zu speichern.

Anti-Malware-Richtlinien isolieren eine Nachricht automatisch *, wenn eine* Anlage Schadsoftware enthält. Weitere Informationen finden Sie unter [configure Anti-Malware Policies in Office 365](configure-anti-malware-policies.md).

Standardmäßig werden Phishing-Nachrichten von Anti-Spam Policies isoliert und Spam-und Massen-e-Mails an den Junk-e-Mail-Ordner des Benutzers übermittelt. Sie können jedoch auch Anti-Spam-Richtlinien erstellen und anpassen, um Spam und Massen-e-Mails zu isolieren. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

Sowohl Benutzer als auch Administratoren können mit unter Quarantäne gestellten Nachrichten arbeiten:

- Administratoren können mit allen Typen von isolierten Nachrichten für alle Benutzer arbeiten. Nur Administratoren können mit Nachrichten arbeiten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) isoliert wurden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365](manage-quarantined-messages-and-files.md).

- Benutzer können mit isolierten Nachrichten arbeiten, bei denen es sich um einen Empfänger handelt, wenn die Nachricht als Spam, Massen-e-Mails oder (ab April 2020) als Phishing isoliert wurde. Weitere Informationen finden Sie unter [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Office 365](find-and-release-quarantined-messages-as-a-user.md).

  Um zu verhindern, dass Benutzer ihre eigenen isolierten Phishing-Nachrichten verwalten, können Administratoren eine andere Aktion für das **Phishing-e-Mail-** Filter Urteil in Anti-Spam-Richtlinien konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

- Administratoren und Benutzer können falsch positive Ergebnisse an Microsoft in der Quarantäne melden.

Weitere Informationen zur Quarantäne finden Sie unter [Quarantine FAQ](quarantine-faq.md).
