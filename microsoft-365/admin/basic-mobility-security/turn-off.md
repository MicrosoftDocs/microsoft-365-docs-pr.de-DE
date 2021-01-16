---
title: Deaktivieren von Basic Mobility and Security
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
description: Entfernen Sie Gruppen oder Richtlinien, um "Basic Mobility and Security" zu deaktivieren.
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876840"
---
# <a name="turn-off-basic-mobility-and-security"></a>Deaktivieren von Basic Mobility and Security

Um basic Mobility and Security effektiv zu deaktivieren, entfernen Sie gruppen von Personen, die von Sicherheitsgruppen definiert sind, aus den Geräteverwaltungsrichtlinien oder entfernen die Richtlinien selbst.

- Entfernen Sie Benutzergruppen, indem Sie Benutzersicherheitsgruppen aus den von Ihnen erstellten Geräterichtlinien entfernen.

- Deaktivieren Sie "Basic Mobility and Security" für alle Benutzer, indem Sie alle Richtlinien für Grundlegende Mobilität und Sicherheit entfernen.

Diese Optionen entfernen die Erzwingung von Basic Mobility and Security für Geräte in Ihrer Organisation. Leider können Sie die Grundlegende Mobilität und Sicherheit nicht einfach "entsprovisionen", nachdem Sie sie eingerichtet haben. 

>[!IMPORTANT]
>Beachten Sie die Auswirkungen auf die Geräte der Benutzer, wenn Sie Benutzersicherheitsgruppen aus Richtlinien entfernen oder die Richtlinien selbst entfernen. Je nach Gerät können beispielsweise E-Mail-Profile und zwischengespeicherte E-Mails entfernt werden. Weitere Informationen finden Sie unter Was geschieht, wenn Sie eine Richtlinie löschen oder  [einen Benutzer aus der Richtlinie entfernen?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Entfernen von Benutzersicherheitsgruppen aus den Geräterichtlinien für grundlegende Mobilität und Sicherheit

1. In Ihrem Browsertyp:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Wählen Sie eine Geräterichtlinie aus, und wählen Sie **"Richtlinie bearbeiten" aus.** 

3. Wählen Sie  **auf der Seite "Bereitstellung"**   **"Entfernen" aus.**

4. Wählen  **Sie unter "Gruppen"** eine Sicherheitsgruppe aus.

5. Wählen Sie  **"Entfernen"** und **"Speichern" aus.**

## <a name="remove-basic-mobility-and-security-device-policies"></a>Entfernen grundlegender Mobilitäts- und Sicherheitsgeräterichtlinien

1.  In Ihrem Browsertyp:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Wählen Sie eine Geräterichtlinie aus, und wählen Sie dann  **"Richtlinie löschen" aus.**
    
3.  Wählen Sie im Dialogfeld "Warnung" die Option **"Ja" aus.**

>[!NOTE]
>Weitere Schritte zum Aufheben der Blockierung von Geräten, wenn geräte in Ihrer Organisation weiterhin blockiert sind, finden Sie im Blogbeitrag ["Removing Access Control from Mobile Device Management for Office 365 "Removing Access Control from Mobile Device Management for Office 365".](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)
