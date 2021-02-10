---
title: Isolierte E-Mail-Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Quarantäne in Exchange Online Protection (EOP) informieren, die potenziell gefährliche oder unerwünschte Nachrichten enthält.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4b111ea0d07453ef4280ec9e57247c8215420074
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167407"
---
# <a name="quarantined-email-messages-in-eop"></a>Isolierte E-Mail-Nachrichten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
-   [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
-   [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer steht die Quarantäne für potenziell gefährliche oder unerwünschte Nachrichten zur Verfügung.

An malware policies automatically quarantine a message if *any* attachment is found to contain malware. Weitere Informationen finden Sie unter [Konfigurieren von An malware-Richtlinien in EOP](configure-anti-malware-policies.md).

Standardmäßig isolieren Antispampoliden Phishingnachrichten und stellen Spam- und Massen-E-Mail-Nachrichten an den Junk-E-Mail-Ordner des Benutzers zu. Sie können jedoch auch Antispamrichtlinien erstellen und anpassen, um Spam- und Massen-E-Mail-Nachrichten zu isolieren. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

Sowohl Benutzer als auch Administratoren können mit Nachrichten in Quarantäne arbeiten:

- Administratoren können mit allen Arten von isolierten Nachrichten für alle Benutzer arbeiten. Nur Administratoren können mit Nachrichten arbeiten, die als Schadsoftware, Phishing mit hoher Sicherheit oder als Folge von Nachrichtenflussregeln (auch als Transportregeln bekannt) isoliert wurden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).

- Benutzer können mit isolierten Nachrichten arbeiten, bei denen sie Empfänger sind, wenn die Nachricht als Spam, Massen-E-Mail oder (ab April 2020) Phishing isoliert wurde. Weitere Informationen finden Sie unter "Suchen und Veröffentlichen von Nachrichten in Quarantäne [als Benutzer in EOP".](find-and-release-quarantined-messages-as-a-user.md)

  Um zu verhindern, dass Benutzer ihre eigenen Phishingnachrichten in Quarantäne  verwalten, können Administratoren eine andere Aktion für die Phishing-E-Mail-Filterungs-Filterung in Antispamrichtlinien konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

- Administratoren und Benutzer können falsch positive Ergebnisse in Quarantäne an Microsoft melden.

Weitere Informationen zum Isolieren finden Sie unter ["Häufig gestellte Fragen zur Quarantäne".](quarantine-faq.md)
