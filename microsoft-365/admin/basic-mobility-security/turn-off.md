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
ms.openlocfilehash: 1d81aed01193fb2ba821ebc055958ac6cd8ac382
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023869"
---
# <a name="turn-off-basic-mobility-and-security"></a>Deaktivieren von grundlegender Mobilität und Sicherheit

Um grundlegende Mobilität und Sicherheit effektiv zu deaktivieren, entfernen Sie Gruppen von Personen, die von Sicherheitsgruppen definiert sind, aus den Geräteverwaltungsrichtlinien, oder entfernen Sie die Richtlinien selbst.

- Entfernen Sie Benutzergruppen, indem Sie Benutzersicherheitsgruppen aus den von Ihnen erstellten Geräterichtlinien entfernen.

- Deaktivieren Sie grundlegende Mobilität und Sicherheit für alle Benutzer, indem Sie alle Geräterichtlinien für Grundlegende Mobilität und Sicherheit entfernen.

Mit diesen Optionen wird die Erzwingung von Basic Mobility and Security für Geräte in Ihrer Organisation entfernt. Leider können Sie grundlegende Mobilität und Sicherheit nach der Einrichtung nicht einfach "unprovision". 

>[!IMPORTANT]
>Beachten Sie die Auswirkungen auf die Geräte von Benutzern, wenn Sie Benutzersicherheitsgruppen aus Richtlinien entfernen oder die Richtlinien selbst entfernen. Je nach Gerät können beispielsweise E-Mail-Profile und zwischengespeicherte E-Mails entfernt werden. Weitere Informationen finden Sie unter Was geschieht, wenn Sie eine Richtlinie löschen oder  [einen Benutzer aus der Richtlinie entfernen?](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Entfernen von Benutzersicherheitsgruppen aus Geräterichtlinien für grundlegende Mobilität und Sicherheit

1. In Ihrem Browsertyp:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Wählen Sie eine Geräterichtlinie aus, und wählen Sie **Richtlinie bearbeiten aus.** 

3. Wählen Sie  **auf der** Seite Bereitstellung die Option   Entfernen **aus.**

4. Wählen  **Sie unter Gruppen** eine Sicherheitsgruppe aus.

5. Wählen  **Sie Entfernen** aus, und wählen Sie Speichern **aus.**

## <a name="remove-basic-mobility-and-security-device-policies"></a>Entfernen grundlegender Mobilitäts- und Sicherheitsgeräterichtlinien

1.  In Ihrem Browsertyp:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Wählen Sie eine Geräterichtlinie aus, und wählen Sie dann  **Richtlinie löschen aus.**
    
3.  Wählen Sie im Dialogfeld Warnung ja **aus.**

>[!NOTE]
>Weitere Schritte zum Aufheben der Blockierung von Geräten, wenn sich Ihre Organisationsgeräte weiterhin in einem blockierten Zustand befinden, finden Sie im Blogbeitrag Entfernen der Zugriffssteuerung aus der Verwaltung mobiler [Geräte für Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).
