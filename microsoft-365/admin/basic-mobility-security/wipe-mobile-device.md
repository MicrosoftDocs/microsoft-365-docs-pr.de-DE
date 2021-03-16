---
title: Wischen eines mobilen Geräts in Basic Mobility and Security
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Verwenden Sie integrierte Grundlegende Mobilität und Sicherheit, um Informationen von registrierten Geräten zu entfernen.
ms.openlocfilehash: ddf13ef6627d70128064e2d8bd185203244b12e4
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819808"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Wischen eines mobilen Geräts in Basic Mobility and Security

Sie können die integrierte Grundlegende Mobilität und Sicherheit für Microsoft 365 verwenden, um nur Organisationsinformationen zu entfernen oder eine Werkszurücksetzung durchzuführen, um alle Informationen von einem mobilen Gerät zu löschen und in den Werkseinstellungen wiederherzustellen.

## <a name="before-you-begin"></a>Bevor Sie loslegen

Mobile Geräte können vertrauliche Organisationsinformationen speichern und Zugriff auf die Microsoft 365-Ressourcen Ihrer Organisation bieten. Um die Informationen Ihrer Organisation zu schützen, können Sie die Werkseinstellungen zurücksetzen oder Unternehmensdaten entfernen:

- **Werkseinstellung:** Löscht alle Daten auf dem mobilen Gerät eines Benutzers, einschließlich installierter Anwendungen, Fotos und personenbezogener Informationen. Nach Abschluss des Zurücksetzens wird das Gerät in den Werkseinstellungen wiederhergestellt.

- **Entfernen von Unternehmensdaten**: Entfernt nur Organisationsdaten und hinterlässt installierte Anwendungen, Fotos und persönliche Informationen auf dem mobilen Gerät eines Benutzers.

- **Wenn ein Gerät zurückgesetzt wird (Werkseinstellungen zurücksetzen oder Unternehmensdaten entfernen)** wird das Gerät aus der Liste der verwalteten Geräte entfernt.
    
- **Automatisches** Zurücksetzen eines Geräts: Sie können eine Grundlegende Mobilitäts- und Sicherheitsrichtlinie einrichten, die ein Gerät automatisch in der Fabrik zurück setzt, nachdem der Benutzer erfolglos versucht hat, das Gerätekennwort mehrmals einzugeben. Führen Sie dazu die Schritte unter Erstellen von [Gerätesicherheitsrichtlinien in grundlegenden Mobilitäts- und Sicherheitsrichtlinien aus.](create-device-security-policies.md)
    
- **Wenn Sie die Benutzeroberfläche beim** Wischen des Geräts kennen möchten, lesen Sie Was sind die Auswirkungen auf Benutzer   [und Geräte?](#whats-the-user-and-device-impact).

## <a name="wipe-a-mobile-device"></a>Wischen eines mobilen Geräts

1. Wechseln Sie zum [Microsoft 365 Admin Center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).

2. Geben Sie mobile Geräteverwaltung in das Suchfeld ein, und wählen Sie **mobile Geräteverwaltung** in der Liste der Ergebnisse aus.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Grundlegende Option zur Verwaltung mobiler Geräte für Mobilität und Secruity":::

3. Wählen **Sie Geräte verwalten aus.**

4. Wählen Sie das Gerät aus, das Sie zurücksetzen möchten.

5. Wählen Sie **Verwalten aus.**

6. Wählen Sie die Art der Remotezurücksetzung aus, die Sie durchführen möchten.

    - Wählen Sie Factory reset aus, um ein vollständiges Zurücksetzen zu durchführen und das Gerät in den Werkseinstellungen **wiederherzustellen.**
    - Wenn Sie eine selektive Löschung und nur Microsoft 365-Organisationsinformationen löschen möchten, wählen Sie **Unternehmensdaten entfernen aus.**
    - Um das Gerät aus Ihrer Organisation zu entfernen, wählen Sie **Gerät entfernen aus.**

7. Wählen Sie zum Bestätigen **Ja** aus.

## <a name="how-do-i-know-it-worked"></a>Wo kann ich wissen, dass es funktioniert hat?

Das mobile Gerät wird nicht mehr in der Liste der verwalteten Geräte angezeigt.

## <a name="why-would-you-want-to-wipe-a-device"></a>Warum möchten Sie ein Gerät wischen?

Wischen Sie ein Gerät aus folgenden Gründen:

- Mobile Geräte wie Smartphones und Tablets werden immer mehr voll funktionsfähig. Dies bedeutet, dass Ihre Benutzer vertrauliche Unternehmensinformationen wie persönliche Identifikation oder vertrauliche Kommunikation leichter speichern und unterwegs darauf zugreifen können. Wenn eines dieser mobilen Geräte verloren geht oder gestohlen wird, kann das Wischen des Geräts dazu beitragen, zu verhindern, dass die Informationen Ihrer Organisation in die falschen Hände geraten.
- Wenn ein Benutzer die Organisation mit einem persönlichen Gerät verlässt, das in Basic Mobility and Security registriert ist, können Sie verhindern, dass Organisationsinformationen mit diesem Benutzer verwendet werden, indem Sie eine Werkszurücksetzung durchführen.
- Wenn Ihre Organisation benutzern mobile Geräte zur Verfügung stellt, müssen Sie Geräte möglicherweise von Zeit zu Zeit neu zuweisen. Wenn Sie ein Factory Reset auf einem Gerät durchführen, bevor sie einem neuen Benutzer zugewiesen werden, wird sichergestellt, dass alle vertraulichen Informationen des vorherigen Besitzers gelöscht werden.

## <a name="whats-the-user-and-device-impact"></a>Welche Auswirkungen haben Benutzer und Geräte?

Die Löschung wird sofort an das mobile Gerät gesendet, und das Gerät ist in Azure Active Directory als nicht kompatibel gekennzeichnet. Während alle Daten entfernt werden, wenn ein Gerät auf die Werkseinstellungen zurückgesetzt wird, wird in der folgenden Tabelle beschrieben, welche Inhalte für jeden Gerätetyp entfernt werden, wenn ein Gerät beim Entfernen von Unternehmensdaten entfernt wird.

|**Auswirkungen auf Inhalte**|**iOS 10 und höher**|**Android 5 und höher**|
|:-----|:-----|:-----|
|Microsoft 365-App-Daten werden gelöscht, wenn das Gerät durch Intune App Protection-Richtlinien geschützt ist. Die Apps werden nicht entfernt. Für Geräte, die nicht durch #A0 (Mobile Application Management) geschützt sind, entfernen Outlook und OneDrive keine zwischengespeicherten Daten.<br/>**Hinweis** Zum Anwenden von Intune-App-Schutzrichtlinien benötigen Sie eine Intune-Lizenz.|Ja|Ja|
|Richtlinieneinstellungen, die von Basic Mobility and Security auf Geräte angewendet werden, werden nicht mehr erzwungen. Benutzer können die Einstellungen ändern.|Ja|Ja|
|Von Basic Mobility and Security erstellte E-Mail-Profile werden entfernt und zwischengespeicherte E-Mails auf dem Gerät gelöscht.|Ja|Nicht zutreffend|
>[!NOTE]
>Die Unternehmensportal-App ist im App Store für iOS und im Play Store für Android-Geräte verfügbar.

## <a name="related-topics"></a>Verwandte Themen

[Einrichten von grundlegender Mobilität und Sicherheit](set-up.md)
