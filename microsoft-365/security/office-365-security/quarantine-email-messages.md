---
title: E-Mail-Nachrichten in Quarantäne
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können Informationen zur Quarantäne in Exchange Online Protection (EoP) erhalten, die potenziell gefährliche oder unerwünschte Nachrichten enthält.
ms.openlocfilehash: d2ccf174ae929c6db14f2a5319e9594495c0778e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826801"
---
# <a name="quarantined-email-messages-in-eop"></a>Isolierte e-Mail-Nachrichten in EoP

In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer steht die Quarantäne zur Verfügung, um potenziell gefährliche oder unerwünschte Nachrichten zu speichern.

Anti-Malware-Richtlinien isolieren eine Nachricht automatisch *, wenn eine* Anlage Schadsoftware enthält. Weitere Informationen finden Sie unter [configure Anti-Malware Policies in EoP](configure-anti-malware-policies.md).

Standardmäßig werden Phishing-Nachrichten von Anti-Spam Policies isoliert und Spam-und Massen-e-Mails an den Junk-e-Mail-Ordner des Benutzers übermittelt. Sie können jedoch auch Anti-Spam-Richtlinien erstellen und anpassen, um Spam und Massen-e-Mails zu isolieren. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

Sowohl Benutzer als auch Administratoren können mit unter Quarantäne gestellten Nachrichten arbeiten:

- Administratoren können mit allen Typen von isolierten Nachrichten für alle Benutzer arbeiten. Nur Administratoren können mit Nachrichten arbeiten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) isoliert wurden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).

- Benutzer können mit isolierten Nachrichten arbeiten, bei denen es sich um einen Empfänger handelt, wenn die Nachricht als Spam, Massen-e-Mails oder (ab April 2020) als Phishing isoliert wurde. Weitere Informationen finden Sie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer in EoP](find-and-release-quarantined-messages-as-a-user.md).

  Um zu verhindern, dass Benutzer ihre eigenen isolierten Phishing-Nachrichten verwalten, können Administratoren eine andere Aktion für das **Phishing-e-Mail-** Filter Urteil in Anti-Spam-Richtlinien konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

- Administratoren und Benutzer können falsch positive Ergebnisse an Microsoft in der Quarantäne melden.

Weitere Informationen zur Quarantäne finden Sie unter [Quarantine FAQ](quarantine-faq.md).
