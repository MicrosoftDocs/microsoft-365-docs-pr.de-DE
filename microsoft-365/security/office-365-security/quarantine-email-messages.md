---
title: Quarantäne in Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
description: Quarantäne in Office 365 hält potenziell gefährliche oder unerwünschte Nachrichten. Administratoren und Endbenutzer können auf die Quarantäne zugreifen.
ms.openlocfilehash: 29f9fcbed83e9019118bb8b37c19cad1199c4c45
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895299"
---
# <a name="quarantine-in-office-365"></a>Quarantäne in Office 365

Wenn Sie ein Office 365 Kunde mit Postfächern in Exchange Online oder einem eigenständigen Exchange Online Schutz-Kunden (EoP) ohne Exchange Online Postfächer sind, ist die Quarantäne verfügbar, um potenziell gefährliche oder unerwünschte Nachrichten zu speichern.

Anti-Malware-Richtlinien isolieren eine Nachricht automatisch *, wenn eine* Anlage Schadsoftware enthält. Weitere Informationen finden Sie unter [configure Anti-Malware Policies in Office 365](configure-anti-malware-policies.md).

Standardmäßig werden Phishing-Nachrichten von Anti-Spam Policies isoliert und Spam-und Massen-e-Mails an den Junk-e-Mail-Ordner des Benutzers übermittelt. Sie können jedoch auch Anti-Spam-Richtlinien erstellen und anpassen, um Spam und Massen-e-Mails zu isolieren. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

Sowohl Benutzer als auch Administratoren können mit unter Quarantäne gestellten Nachrichten arbeiten:

- Administratoren können mit allen Typen von isolierten Nachrichten für alle Benutzer arbeiten. Nur Administratoren können mit Nachrichten arbeiten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) isoliert wurden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365](manage-quarantined-messages-and-files.md).

- Benutzer können mit isolierten Nachrichten arbeiten, bei denen es sich um einen Empfänger handelt, wenn die Nachricht als Spam, Massen-e-Mails oder (ab April 2020) als Phishing isoliert wurde. Weitere Informationen finden Sie unter [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Office 365](find-and-release-quarantined-messages-as-a-user.md).

  Um zu verhindern, dass Benutzer ihre eigenen isolierten Phishing-Nachrichten verwalten, können Administratoren eine andere Aktion für das **Phishing-e-Mail-** Filter Urteil in Anti-Spam-Richtlinien konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

- Administratoren und Benutzer können falsch positive Ergebnisse an Microsoft in der Quarantäne melden.

Weitere Informationen zur Quarantäne finden Sie unter [Quarantine FAQ](quarantine-faq.md).
