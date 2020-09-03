---
title: Deaktivieren der grundlegenden Mobilität und Sicherheit
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
description: Entfernen Sie Gruppen oder Richtlinien, um die grundlegende Mobilität und Sicherheit zu deaktivieren.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336886"
---
# <a name="turn-off-basic-mobility-and-security"></a>Deaktivieren der grundlegenden Mobilität und Sicherheit

Um die grundlegende Mobilität und Sicherheit effektiv zu deaktivieren, entfernen Sie Gruppen von Personen, die von Sicherheitsgruppen definiert wurden, aus den Geräteverwaltungsrichtlinien oder entfernen die Richtlinien selbst.

- Entfernen Sie Gruppen von Benutzern, indem Sie Benutzersicherheitsgruppen aus den von Ihnen erstellten Geräterichtlinien entfernen.
    
- Deaktivieren Sie die grundlegenden Mobilitäts-und Sicherheitseinstellungen für alle, indem Sie alle grundlegenden Mobilitäts-und Sicherheitsgeräte Richtlinien entfernen.
    
Diese Optionen entfernen grundlegende Mobilitäts-und Sicherheitsvorkehrungen für Geräte in Ihrer Organisation. Leider können Sie die grundlegende Mobilität und Sicherheit nicht einfach "aufheben", nachdem Sie Sie eingerichtet haben. 

>[!IMPORTANT]
>Beachten Sie die Auswirkungen auf die Geräte der Benutzer, wenn Sie Benutzersicherheitsgruppen aus Richtlinien entfernen oder die Richtlinien selbst entfernen. Beispielsweise können e-Mail-Profile und zwischengespeicherte e-Mails je nach Gerät entfernt werden. Weitere Informationen finden Sie unter  [Was geschieht, wenn Sie eine Richtlinie löschen oder einen Benutzer aus der Richtlinie entfernen?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Entfernen von Benutzersicherheitsgruppen aus grundlegenden Mobilitäts-und Sicherheitsgeräte Richtlinien

1. Geben Sie im Browsertyp Folgendes ein:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Wählen Sie eine Geräterichtlinie aus, und wählen Sie **Richtlinie bearbeiten**aus. 

3. Wählen Sie auf der Seite  **Bereitstellung** die   Option **Entfernen**aus.
    
4. Wählen Sie unter  **Gruppen**eine Sicherheitsgruppe aus.

5. Wählen Sie  **Entfernen**aus, und wählen Sie **Speichern**aus.
    

## <a name="remove-basic-mobility-and-security-device-policies"></a>Entfernen grundlegender Mobilitäts-und Sicherheitsgeräte Richtlinien

1.  Geben Sie im Browsertyp Folgendes ein:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Wählen Sie eine Geräterichtlinie aus, und wählen Sie dann  **Richtlinie löschen**aus.
    
3.  Wählen Sie im Dialogfeldwarnung die Option **Ja**aus.

>[!NOTE] 
>Weitere Schritte zum Entsperren von Geräten, wenn sich Ihre Organisations Geräte noch im Status "blockiert" befinden, finden Sie im Blogbeitrag [Entfernen der Zugriffssteuerung von der Verwaltung mobiler Geräte für Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).
