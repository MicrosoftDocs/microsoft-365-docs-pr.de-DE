---
title: Deaktivieren von grundlegender Mobilität und Sicherheit
f1.keywords: NOCSH
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Entfernen Sie Gruppen oder Richtlinien, um grundlegende Mobilität und Sicherheit zu deaktivieren.
ms.openlocfilehash: 7ec4ec0d47668c21824d8e01e3845d637b9b0922
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228135"
---
# <a name="turn-off-basic-mobility-and-security"></a>Deaktivieren von grundlegender Mobilität und Sicherheit

Um grundlegende Mobilität und Sicherheit effektiv zu deaktivieren, entfernen Sie gruppen von Sicherheitsgruppen definierte Personen aus den Geräteverwaltungsrichtlinien oder entfernen die Richtlinien selbst.

- Entfernen Sie Benutzergruppen, indem Sie Benutzersicherheitsgruppen aus den von Ihnen erstellten Geräterichtlinien entfernen.

- Deaktivieren Sie die grundlegende Mobilität und Sicherheit für alle Benutzer, indem Sie alle Geräterichtlinien für grundlegende Mobilität und Sicherheit entfernen.

Diese Optionen entfernen die Basic Mobility and Security-Erzwingung für Geräte in Ihrer Organisation. Leider können Sie die Grundlegende Mobilität und Sicherheit nicht einfach "aufheben", nachdem Sie sie eingerichtet haben.

> [!IMPORTANT]
> Beachten Sie die Auswirkungen auf die Geräte der Benutzer, wenn Sie Benutzersicherheitsgruppen aus Richtlinien entfernen oder die Richtlinien selbst entfernen. Beispielsweise können E-Mail-Profile und zwischengespeicherte E-Mails je nach Gerät entfernt werden. Weitere Informationen finden Sie unter  [Was geschieht, wenn Sie eine Richtlinie löschen oder einen Benutzer aus der Richtlinie entfernen?](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Entfernen von Benutzersicherheitsgruppen aus grundlegenden Mobilitäts- und Sicherheitsgeräterichtlinien

1. In Ihrem Browsertyp:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Wählen Sie eine Geräterichtlinie und dann **"Richtlinie bearbeiten"** aus.

3. Wählen Sie auf der Seite  **"Bereitstellung"** die   Option **"Entfernen" aus.**

4. Wählen Sie unter  **"Gruppen"** eine Sicherheitsgruppe aus.

5. Wählen Sie  **"Entfernen"** und dann **"Speichern"** aus.

## <a name="remove-basic-mobility-and-security-device-policies"></a>Entfernen grundlegender Mobilitäts- und Sicherheitsgeräterichtlinien

1. In Ihrem Browsertyp:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Wählen Sie eine Geräterichtlinie und dann  **"Richtlinie löschen"** aus.

3. Wählen Sie im Dialogfeld "Warnung" die Option **"Ja"** aus.

> [!NOTE]
> Weitere Schritte zum Aufheben der Blockierung von Geräten, wenn sich Ihre Unternehmensgeräte weiterhin in einem blockierten Zustand befinden, finden Sie im Blogbeitrag ["Entfernen der Zugriffssteuerung aus Verwaltung mobiler Geräte für Office 365."](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)
