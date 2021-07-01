---
title: Zurücksetzen eines mobilen Geräts in Basic Mobility and Security
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
ms.openlocfilehash: c3cc547ce5e135ccdabf9a09b0d572f1b2530f47
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228147"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Zurücksetzen eines mobilen Geräts in Basic Mobility and Security

Sie können die integrierte Grundlegende Mobilität und Sicherheit für Microsoft 365 verwenden, um nur Organisationsinformationen zu entfernen, oder um eine Zurücksetzung auf die Werkseinstellungen durchzuführen, um alle Informationen von einem mobilen Gerät zu löschen und in den Werkseinstellungen wiederherzustellen.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Mobile Geräte können vertrauliche Unternehmensinformationen speichern und Zugriff auf die Microsoft 365 Ressourcen Ihrer Organisation gewähren. Um die Informationen Ihrer Organisation zu schützen, können Sie die Werkseinstellungen zurücksetzen oder Unternehmensdaten entfernen:

- **Zurücksetzung auf die Werkseinstellungen:** Löscht alle Daten auf dem mobilen Gerät eines Benutzers, einschließlich installierter Anwendungen, Fotos und persönlicher Informationen. Nach Abschluss der Zurücksetzung wird das Gerät in den Werkseinstellungen wiederhergestellt.

- **Unternehmensdaten entfernen:** Entfernt nur Organisationsdaten und verlässt installierte Anwendungen, Fotos und persönliche Informationen auf dem mobilen Gerät eines Benutzers.

- **Wenn ein Gerät gelöscht wird (Zurücksetzung auf Werkseinstellungen oder Entfernen von Unternehmensdaten),** wird das Gerät aus der Liste der verwalteten Geräte entfernt.
    
- **Automatisches Zurücksetzen eines Geräts:** Sie können eine Grundlegende Mobilitäts- und Sicherheitsrichtlinie einrichten, die ein Gerät automatisch von der Werkseinstellungen zurücksetzt, nachdem der Benutzer eine bestimmte Anzahl von Malen erfolglos versucht, das Gerätekennwort einzugeben. Führen Sie dazu die Schritte unter [Erstellen von Gerätesicherheitsrichtlinien für grundlegende Mobilität und Sicherheit](create-device-security-policies.md)aus.
    
- **Wenn Sie die Benutzererfahrung beim** Zurücksetzen des Geräts kennen möchten, sehen Sie sich   [an, welche Auswirkungen der Benutzer und das Gerät haben?](#whats-the-user-and-device-impact).

## <a name="wipe-a-mobile-device"></a>Zurücksetzen eines mobilen Geräts

1. Wechseln Sie zum [Microsoft 365 Admin Center](../../admin/admin-overview/about-the-admin-center.md).

2. Geben Sie die Verwaltung mobiler Geräte in das Suchfeld ein, und wählen Sie **"Mobile Geräteverwaltung"** aus der Liste der Ergebnisse aus.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Grundlegende Option für die Verwaltung mobiler Geräte für Mobilität und Secruity":::

3. Wählen Sie **"Geräte verwalten" aus.**

4. Wählen Sie das Gerät aus, das Sie zurücksetzen möchten.

5. Wählen Sie **"Verwalten" aus.**

6. Wählen Sie die Art der Remotezurücksetzung aus, die Sie durchführen möchten.

    - Um eine vollständige Zurücksetzung durchzuführen und das Gerät auf die Werkseinstellungen zurückzusetzen, wählen Sie **"Werkszurücksetzung"** aus.
    - Wenn Sie nur Microsoft 365 Organisationsinformationen selektiv zurücksetzen und löschen möchten, wählen Sie **"Unternehmensdaten entfernen" aus.**
    - Um das Gerät aus Ihrer Organisation zu entfernen, wählen Sie **"Gerät entfernen"** aus.

7. Wählen Sie zum Bestätigen **Ja** aus.

## <a name="how-do-i-know-it-worked"></a>Wie kann ich feststellen, dass es funktioniert hat?

Das mobile Gerät wird nicht mehr in der Liste der verwalteten Geräte angezeigt.

## <a name="why-would-you-want-to-wipe-a-device"></a>Warum sollten Sie ein Gerät zurücksetzen?

Zurücksetzen eines Geräts aus folgenden Gründen:

- Mobile Geräte wie Smartphones und Tablets werden immer umfassender. Dies bedeutet, dass es für Ihre Benutzer einfacher ist, vertrauliche Unternehmensinformationen wie persönliche Identifikation oder vertrauliche Kommunikation zu speichern und unterwegs darauf zuzugreifen. Wenn eines dieser mobilen Geräte verloren geht oder gestohlen wird, kann das Zurücksetzen des Geräts dazu beitragen, dass die Informationen Ihrer Organisation nicht in die falschen Hände gelangen.
- Wenn ein Benutzer die Organisation mit einem persönlichen Gerät verlässt, das bei Basic Mobility and Security registriert ist, können Sie verhindern, dass Unternehmensinformationen mit diesem Benutzer übertragen werden, indem Sie eine Zurücksetzung auf die Werkseinstellungen durchführen.
- Wenn Ihre Organisation Mobilgeräte für Benutzer bereitstellt, müssen Sie geräte von Zeit zu Zeit neu zuweisen. Wenn Sie auf einem Gerät eine Zurücksetzung auf die Werkseinstellungen durchführen, bevor sie einem neuen Benutzer zugewiesen wird, wird sichergestellt, dass alle vertraulichen Informationen des vorherigen Besitzers gelöscht werden.

## <a name="whats-the-user-and-device-impact"></a>Welche Auswirkungen haben Benutzer und Geräte?

Die Zurücksetzung wird sofort an das mobile Gerät gesendet, und das Gerät wird im Azure Active Directory als nicht kompatibel gekennzeichnet. Während alle Daten entfernt werden, wenn ein Gerät auf die Werksstandardeinstellungen zurückgesetzt wird, wird in der folgenden Tabelle beschrieben, welche Inhalte für jeden Gerätetyp entfernt werden, wenn ein Gerät Unternehmensdaten entfernt.

|**Auswirkungen auf den Inhalt**|**iOS 10 und höher**|**Android 5 und höher**|
|:-----|:-----|:-----|
|Microsoft 365 App-Daten werden gelöscht, wenn das Gerät durch Intune App Protection-Richtlinien geschützt ist. Die Apps werden nicht entfernt. Für Geräte, die nicht durch MAM-Richtlinien (Mobile Application Management) geschützt sind, entfernen Outlook und OneDrive keine zwischengespeicherten Daten.<br/>**Hinweis** Zum Anwenden von Intune App-Schutzrichtlinien benötigen Sie eine Intune-Lizenz.|Ja|Ja|
|Richtlinieneinstellungen, die von Basic Mobility and Security auf Geräte angewendet werden, werden nicht mehr erzwungen. Benutzer können die Einstellungen ändern.|Ja|Ja|
|E-Mail-Profile, die von Basic Mobility and Security erstellt wurden, werden entfernt, und zwischengespeicherte E-Mails auf dem Gerät werden gelöscht.|Ja|Nicht zutreffend|

> [!NOTE]
> Unternehmensportal App ist im App-Store für iOS und im Play-Store für Android-Geräte verfügbar.
