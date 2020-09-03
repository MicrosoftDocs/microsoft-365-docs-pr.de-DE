---
title: Wischen eines mobilen Geräts in grundlegender Mobilität und Sicherheit
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
description: Verwenden Sie die integrierte grundlegende Mobilität und Sicherheit, um Informationen von registrierten Geräten zu entfernen.
ms.openlocfilehash: 4d854c7d4d81cd0b49ec7f81a49de5478b08f049
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336891"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Wischen eines mobilen Geräts in grundlegender Mobilität und Sicherheit

Mithilfe von integrierter grundlegender Mobilität und Sicherheit für Microsoft 365 können Sie nur organisatorische Informationen entfernen oder ein Factory-Reset durchführen, um alle Informationen von einem mobilen Gerät zu löschen und in den Werkseinstellungen wiederherzustellen.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Mobile Geräte können vertrauliche Organisationsinformationen speichern und den Zugriff auf die Microsoft 365-Ressourcen Ihrer Organisation ermöglichen. Um die Informationen Ihrer Organisation zu schützen, können Sie Firmendaten zurücksetzen oder entfernen:
    
- **Factory Reset**: Löscht alle Daten auf dem mobilen Gerät eines Benutzers, einschließlich installierter Anwendungen, Fotos und persönlicher Informationen. Wenn die Zurücksetzung abgeschlossen ist, wird das Gerät in den Werkseinstellungen wiederhergestellt.
    
- **Entfernen von Unternehmensdaten**: entfernt nur Organisationsdaten und hinterlässt installierte Anwendungen, Fotos und persönliche Informationen auf dem mobilen Gerät eines Benutzers.   

- **Wenn ein Gerät gelöscht wird (Factory zurücksetzen oder Entfernen von Unternehmensdaten)**, wird das Gerät aus der Liste der verwalteten Geräte entfernt.
    
- **Automatisches Zurücksetzen eines Geräts**: Sie können eine grundlegende Mobilitäts-und Sicherheitsrichtlinie einrichten, mit der ein Gerät automatisch zurückgesetzt wird, nachdem der Benutzer erfolglos versucht hat, das Gerätekennwort eine bestimmte Anzahl von Malen einzugeben. Führen Sie dazu die Schritte unter [Create Device Security Policies in Basic Mobility and Security](create-device-security-policies-in-basic-mmobility-and-security.md)aus.
    
- **Wenn Sie die Benutzeroberfläche kennen möchten** , wenn Sie Ihr Gerät löschen, lesen Sie  [Was ist der Einfluss von Benutzern und Geräten?](#whats-the-user-and-device-impact).   

## <a name="wipe-a-mobile-device"></a>Wischen eines mobilen Geräts

1. Wechseln Sie zum [Microsoft 365 Admin Center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).
    
2. Geben Sie die Verwaltung mobiler Geräte in das Suchfeld ein, und wählen Sie in der Ergebnisliste die **Verwaltung mobiler Geräte** aus. 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Einfache Mobilitäts-und secruity-Option für die Mobile Geräteverwaltung":::

3. Wählen Sie **Geräte verwalten**aus.

4. Wählen Sie das Gerät aus, das Sie zurücksetzen möchten.

5. Wählen Sie **Manage**aus.

6. Wählen Sie die Art der Remotezurücksetzung aus, die Sie durchführen möchten.

    - Um eine vollständige Zurücksetzung durchführen und das Gerät in den Werkseinstellungen wiederherstellen zu können, wählen Sie **Factory Reset**aus.
    - Um eine selektive Zurücksetzung durchführen und nur Informationen zu Microsoft 365-Organisationen zu löschen, wählen Sie **Unternehmensdaten entfernen**aus.
    - Wenn Sie das Gerät aus Ihrer Organisation entfernen möchten, wählen Sie **Gerät entfernen**aus.

7. Wählen Sie zum Bestätigen **Ja** aus.

## <a name="how-do-i-know-it-worked"></a>Woher weiß ich, dass es funktioniert hat?

Das Mobile Gerät wird in der Liste der verwalteten Geräte nicht mehr angezeigt.

## <a name="why-would-you-want-to-wipe-a-device"></a>Warum sollten Sie ein Gerät löschen?

Wischen Sie ein Gerät aus folgenden Gründen ab:

- Mobile Geräte wie Smartphones und Tablets werden immer umfangreichere Features. Dies bedeutet, dass es für Ihre Benutzer einfacher ist, vertrauliche Unternehmensinformationen wie persönliche Identifikation oder vertrauliche Kommunikation zu speichern und unterwegs darauf zuzugreifen. Wenn eines dieser mobilen Geräte verloren geht oder gestohlen wird, kann das Abwischen des Geräts dazu beitragen, dass die Informationen Ihrer Organisation nicht in die falschen Hände geraten.
- Wenn ein Benutzer die Organisation mit einem persönlichen Gerät verlässt, das in Basic Mobility and Security registriert ist, können Sie verhindern, dass organisatorische Informationen mit dem betreffenden Benutzer ausgeführt werden, indem Sie einen Factory-Reset durchführen.
- Wenn Ihre Organisation Benutzern Mobile Geräte zur Verfügung stellt, müssen Sie möglicherweise von Zeit zu Zeit Geräte neu zuweisen. Wenn Sie ein Factory-Reset auf einem Gerät durchführen, bevor Sie es einem neuen Benutzer zuweisen, wird sichergestellt, dass vertrauliche Informationen des vorherigen Besitzers gelöscht werden.

## <a name="whats-the-user-and-device-impact"></a>Was ist der Einfluss von Benutzern und Geräten?

Die Löschung wird sofort an das Mobile Gerät gesendet, und das Gerät ist in Azure Active Directory als nicht kompatibel gekennzeichnet. Während alle Daten entfernt werden, wenn ein Gerät auf die Werkseinstellungen zurückgesetzt wird, wird in der folgenden Tabelle beschrieben, welche Inhalte für die einzelnen Gerätetypen entfernt werden, wenn ein Gerät beim Entfernen von Unternehmensdaten verwendet wird.

|**Inhalt unpaced**|**IOS 10 und höher**|**Android 5 und höher**|
|:-----|:-----|:-----|
|Microsoft 365 App-Daten werden gelöscht, wenn das Gerät durch InTune-App-Schutzrichtlinien geschützt ist. Die apps werden nicht entfernt. Für Geräte, die nicht durch MAM-Richtlinien (Mobile Application Management) geschützt sind, entfernen Outlook und OneDrive zwischengespeicherte Daten nicht.<br/>**Hinweis:** Zum Anwenden von InTune-App-Schutzrichtlinien benötigen Sie eine InTune-Lizenz.|Ja|Ja|
|Richtlinieneinstellungen, die von grundlegender Mobilität und Sicherheit auf Geräte angewendet werden, werden nicht mehr erzwungen; Benutzer können die Einstellungen ändern.|Ja|Ja|
|Von Basic Mobility and Security erstellte e-Mail-Profile werden entfernt, und zwischengespeicherte e-Mails auf dem Gerät werden gelöscht.|Ja|Nicht zutreffend|
>[!NOTE] 
>Die Unternehmens Portal-App steht im App Store für IOS und den Play Store für Android-Geräte zur Verfügung.

## <a name="related-topics"></a>Verwandte Themen

[Einrichten von grundlegender Mobilität und Sicherheit](set-up-basic-mobility-and-security.md)