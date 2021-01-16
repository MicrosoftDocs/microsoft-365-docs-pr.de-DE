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
description: Verwenden Sie die integrierte Basismobilität und -sicherheit, um Informationen von registrierten Geräten zu entfernen.
ms.openlocfilehash: 3bb9bfe55653b021ce5a86dd5d3dbc3de45ed19a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876828"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Wischen eines mobilen Geräts in Basic Mobility and Security

Sie können die integrierte Basismobilität und -sicherheit für Microsoft 365 verwenden, um nur Organisationsinformationen zu entfernen oder eine Zurücksetzung auf die Werkseinstellungen durchzuführen, um alle Informationen von einem mobilen Gerät zu löschen und in den Werkseinstellungen wiederherzustellen.

## <a name="before-you-begin"></a>Vorabinformationen

Mobile Geräte können vertrauliche Unternehmensinformationen speichern und Zugriff auf die Microsoft 365-Ressourcen Ihrer Organisation bereitstellen. Um die Informationen Ihrer Organisation zu schützen, können Sie die Werkseinstellungen zurücksetzen oder Unternehmensdaten entfernen:

- **Zurücksetzen auf** die Werkseinstellungen: Löscht alle Daten auf dem mobilen Gerät eines Benutzers, einschließlich installierter Anwendungen, Fotos und persönlicher Informationen. Nach Abschluss des Zurücksetzens wird das Gerät in den Werkseinstellungen wiederhergestellt.

- **Entfernen von Unternehmensdaten:** Entfernt nur Organisationsdaten und hinterlässt installierte Anwendungen, Fotos und persönliche Informationen auf dem mobilen Gerät eines Benutzers.

- **Wenn ein Gerät zurückgesetzt wird (Werkseinstellungen** zurücksetzen oder Unternehmensdaten entfernen), wird das Gerät aus der Liste der verwalteten Geräte entfernt.
    
- **Automatisches** Zurücksetzen eines Geräts: Sie können eine Standardrichtlinie für Mobilität und Sicherheit einrichten, die ein Gerät automatisch zurückzusetzen versucht, nachdem der Benutzer mehrmals erfolglos versucht hat, das Gerätekennwort einzugeben. Führen Sie dazu die Schritte in "Erstellen von Gerätesicherheitsrichtlinien [für grundlegende Mobilität und Sicherheit" aus.](create-device-security-policies.md)
    
- **Wenn Sie die Benutzeroberfläche** kennen möchten, wenn Sie ihr Gerät löschen, lesen Sie, was die Auswirkungen auf Benutzer   [und Geräte sind.](#whats-the-user-and-device-impact)

## <a name="wipe-a-mobile-device"></a>Wischen eines mobilen Geräts

1. Wechseln Sie zum [Microsoft 365 Admin Center.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)

2. Geben Sie die Verwaltung mobiler Geräte in das Suchfeld ein, und wählen Sie in der Ergebnisliste die Option **"Mobile** Geräteverwaltung" aus.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Option für die verwaltung mobiler Geräte für Mobilität und Secruity":::

3. Wählen **Sie Geräte verwalten aus.**

4. Wählen Sie das Gerät aus, das Sie zurücksetzen möchten.

5. Wählen Sie **"Verwalten"** aus.

6. Wählen Sie die Art der Remotezurücksetzung aus, die Sie durchführen möchten.

    - Wenn Sie eine vollständige Zurücksetzung vornehmen und das Gerät auf die Werkseinstellungen zurücksetzen möchten, wählen Sie **"Zurücksetzen auf Werkseinstellungen" aus.**
    - Wählen Sie "Unternehmensdaten entfernen" aus, um eine selektive Zurücklöschung zu tun und nur Microsoft 365-Organisationsinformationen **zu löschen.**
    - Wählen Sie "Gerät entfernen" aus, um das Gerät **aus Ihrer Organisation zu entfernen.**

7. Wählen Sie zum Bestätigen **Ja** aus.

## <a name="how-do-i-know-it-worked"></a>Wo finde ich, dass es funktioniert hat?

Das mobile Gerät wird nicht mehr in der Liste der verwalteten Geräte angezeigt.

## <a name="why-would-you-want-to-wipe-a-device"></a>Warum sollten Sie ein Gerät wischen?

Löschen Sie ein Gerät aus folgenden Gründen:

- Mobile Geräte wie Smartphones und Tablets werden immer häufiger mit vollem Funktionspensing ausgestattet. Dies bedeutet, dass es für Ihre Benutzer einfacher ist, vertrauliche Unternehmensinformationen wie persönliche Identifikation oder vertrauliche Kommunikation zu speichern und unterwegs darauf zu zugreifen. Wenn eines dieser mobilen Geräte verloren geht oder gestohlen wird, kann das Löschen des Geräts verhindern, dass die Informationen Ihrer Organisation in die falschen Hände geraten.
- Wenn ein Benutzer die Organisation mit einem persönlichen Gerät verlässt, das für Basic Mobility and Security registriert ist, können Sie verhindern, dass Organisationsinformationen mit diesem Benutzer verwendet werden, indem Sie eine Zurücksetzung auf die Werkseinstellungen durchführen.
- Wenn Ihre Organisation Benutzern mobile Geräte zur Verfügung stellt, müssen Sie geräte möglicherweise von Zeit zu Zeit neu zuweisen. Durch das Zurücksetzen auf die Werkseinstellungen auf einem Gerät vor dem Zuweisen zu einem neuen Benutzer wird sichergestellt, dass alle vertraulichen Informationen des vorherigen Besitzers gelöscht werden.

## <a name="whats-the-user-and-device-impact"></a>Welche Auswirkungen haben Benutzer und Geräte?

Die Zurücklöschung wird sofort an das mobile Gerät gesendet, und das Gerät wird in Azure Active Directory als nicht kompatibel gekennzeichnet. Während alle Daten entfernt werden, wenn ein Gerät auf die Werkseinstellungen zurückgesetzt wird, wird in der folgenden Tabelle beschrieben, welche Inhalte für jeden Gerätetyp entfernt werden, wenn Sie Unternehmensdaten entfernen.

|**Inhaltsfeind**|**iOS 10 und höher**|**Android 5 und höher**|
|:-----|:-----|:-----|
|Microsoft 365-App-Daten werden gelöscht, wenn das Gerät durch Intune App Protection-Richtlinien geschützt ist. Die Apps werden nicht entfernt. Bei Geräten, die nicht durch #A0 (Mobile Application Management) geschützt sind, werden zwischengespeicherte Daten von Outlook und OneDrive nicht entfernt.<br/>**Hinweis** Zum Anwenden von Intune-App-Schutzrichtlinien benötigen Sie eine Intune-Lizenz.|Ja|Ja|
|Richtlinieneinstellungen, die von Basic Mobility and Security auf Geräte angewendet werden, werden nicht mehr erzwungen. Benutzer können die Einstellungen ändern.|Ja|Ja|
|Von Basic Mobility and Security erstellte E-Mail-Profile werden entfernt und zwischengespeicherte E-Mails auf dem Gerät gelöscht.|Ja|Nicht zutreffend|
>[!NOTE]
>Die Unternehmensportal-App ist im App Store für iOS und im Play Store für Android verfügbar.

## <a name="related-topics"></a>Verwandte Themen

[Einrichten von grundlegender Mobilität und Sicherheit](set-up.md)