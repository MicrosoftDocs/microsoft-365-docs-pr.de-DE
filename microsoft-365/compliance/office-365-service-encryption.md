---
title: Office 365-Dienstverschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Zusammenfassung: Grundlegendes zur Datenverschlüsselung auf der Dienstebene in Microsoft Office 365.'
ms.openlocfilehash: fb6bf87fbd51bcb4383e9eb595ef11f081989d86
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211942"
---
# <a name="office-365-service-encryption"></a>Office 365-Dienstverschlüsselung

Zusätzlich zur Verwendung von BitLocker für die Verschlüsselung auf Volumen Ebene verwenden Exchange Online, Skype for Business, SharePoint Online, OneDrive für Unternehmen und Teams auch die Dienst Verschlüsselung zum Verschlüsseln von Kundendaten. Die Dienst Verschlüsselung ermöglicht zwei wichtige Verwaltungsoptionen:

- Microsoft verwaltet alle kryptografischen Schlüssel. Diese Option ist derzeit in SharePoint Online-, OneDrive für Unternehmen-, Skype for Business-und Microsoft Teams-Chats verfügbar. Ihre Daten werden standardmäßig mit von Microsoft verwalteten Schlüsseln verschlüsselt.

- Ihre Organisation stellt die Stammschlüssel zur Verfügung. Sie verwalten diese Schlüssel mithilfe von Azure Key Vault. Diese Option wird als Kundenschlüssel bezeichnet. Der Kundenschlüssel steht derzeit für Exchange Online-, SharePoint Online-, OneDrive für Unternehmen-, Skype for Business-und Microsoft Teams-Dateien zur Verfügung. Wenn Sie den Kundenschlüssel verwenden, ersetzen diese Tasten die von Microsoft verwalteten Schlüssel, um Ihre Daten zu verschlüsseln.

Unabhängig von der gewählten Option bietet die Dienst Verschlüsselung mehrere Vorteile:

- Erzwingt die Benutzerauthentifizierung zum Abrufen und Entschlüsseln von Daten, die von einem autorisierten Benutzer angefordert wurden.

- Ermöglicht die Trennung von Administratoren des Windows-Betriebssystems vom Zugriff auf Kundendaten, die vom Betriebssystem gespeichert oder verarbeitet werden.

- Erhöht die Fähigkeit von Office 365, die Anforderungen von Kunden zu erfüllen, die Compliance-Anforderungen bezüglich Verschlüsselung haben.

Informationen zum Einrichten des Kunden Schlüssels für Office 365 für Exchange Online-, Skype for Business-, SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien finden Sie in den folgenden Artikeln:

- [Dienst Verschlüsselung mit Kundenschlüssel in Office 365](customer-key-overview.md)

- [Einrichten des Kunden Schlüssels für Office 365](customer-key-set-up.md)

- [Verwalten des Kunden Schlüssels für Office 365](customer-key-manage.md)

- [Rollen oder Drehen eines Kunden Schlüssels oder eines Verfügbarkeits Schlüssels](customer-key-availability-key-roll.md)

- [Grundlegendes zum Verfügbarkeits Schlüssel](customer-key-availability-key-understand.md)
