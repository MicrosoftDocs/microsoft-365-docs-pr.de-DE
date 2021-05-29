---
title: Übersicht über grundlegende Mobilität und Sicherheit für Microsoft 365
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
description: Verwenden Sie Grundlegende Mobilität und Sicherheit zum Festlegen von Gerätesicherheitsrichtlinien und Zugriffsregeln.
ms.openlocfilehash: 37be420a4b9499da3d1290b8b6a898b9fcb09c5b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706310"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Übersicht über grundlegende Mobilität und Sicherheit für Microsoft 365

Sie können mobile Geräte verwalten und sichern, wenn sie mit Ihrer Microsoft 365 verbunden sind, indem Sie Grundlegende Mobilität und Sicherheit verwenden. Mobile Geräte wie Smartphones und Tablets für den Zugriff auf E-Mails, Kalender, Kontakte und Dokumente am Arbeitsplatz spielen eine große Rolle, um sicherzustellen, dass Mitarbeiter jederzeit und überall ihre Arbeit erledigen können. Daher ist es wichtig, dass Sie die Informationen Ihrer Organisation schützen, wenn Personen Geräte verwenden. Sie können grundlegende Mobilität und Sicherheit verwenden, um Gerätesicherheitsrichtlinien und Zugriffsregeln festlegen und mobile Geräte zu löschen, wenn sie verloren gehen oder gestohlen werden.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Grundlegendes Setup für Mobilität und Sicherheit":::

## <a name="what-types-of-devices-can-you-manage"></a>Welche Arten von Geräten können Sie verwalten?

Sie können grundlegende Mobilität und Sicherheit verwenden, um viele Arten von mobilen Geräten wie Windows Phone, Android, iPhone und iPad. Zum Verwalten mobiler Geräte, die von Personen in Ihrer Organisation verwendet werden, muss jede Person über eine Microsoft 365-Lizenz verfügen, und ihr Gerät muss in Basic Mobility and Security registriert sein.

Informationen dazu, was Basic Mobility and Security für jeden Gerätetyp unterstützt, finden Sie unter [Capabilities of Basic Mobility and Security](capabilities.md).

## <a name="setup-steps-for-basic-mobility-and-security"></a>Setupschritte für grundlegende Mobilität und Sicherheit

Ein Microsoft 365 muss die folgenden Schritte zum Aktivieren und Einrichten von Basic Mobility and Security ausführen. Ausführliche Schritte finden Sie unter [Set up Basic Mobility and Security](set-up.md). 

Im Folgenden finden Sie eine Zusammenfassung der Schritte:

**Schritt 1:** Aktivieren Sie Grundlegende Mobilität und Sicherheit, indem Sie die folgenden Schritte unter  [Set up Basic Mobility and Security ausführen.](set-up.md)

**Schritt 2:** Richten Sie Grundlegende Mobilität und Sicherheit ein, indem Sie z. B. ein APNs-Zertifikat zum Verwalten von iOS-Geräten erstellen und einen DNS-Eintrag (Domain Name System) für Ihre Domäne hinzufügen, um Windows unterstützen.

**Schritt 3:** Erstellen Sie Geräterichtlinien, und wenden Sie sie auf Benutzergruppen an. Wenn Sie dies tun, erhalten Ihre Benutzer eine Registrierungsnachricht auf ihrem Gerät, und wenn sie die Registrierung abgeschlossen haben, werden ihre Geräte durch die Richtlinien eingeschränkt, die Sie für sie eingerichtet haben. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mithilfe von Basic Mobility and Security](enroll-your-mobile-device.md). 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Sicherheits- und Mobilitätsrichtlinieneinstellungen":::

## <a name="device-management-tasks"></a>Geräteverwaltungsaufgaben

Nachdem Sie grundlegende Mobilität und Sicherheit eingerichtet haben und Ihre Benutzer ihre Geräte registriert haben, können Sie die Geräte verwalten, den Zugriff blockieren oder bei Bedarf ein Gerät wischen. Weitere Informationen zu einigen allgemeinen Geräteverwaltungsaufgaben, einschließlich der Aufgaben, finden Sie unter [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).

## <a name="other-ways-to-manage-devices-and-apps"></a>Andere Möglichkeiten zum Verwalten von Geräten und Apps

Wenn Sie nur die Verwaltung mobiler Apps (Mobile App Management, MAM) benötigen, z. B. für Personen, die Arbeitsprojekte auf ihren eigenen Geräten aktualisieren, bietet Intune neben der Registrierung und Verwaltung von Geräten eine weitere Option. Mit einem Intune-Abonnement können Sie MAM-Richtlinien mithilfe des Azure-Portals einrichten, auch wenn die Geräte von Personen nicht in Intune registriert sind. Weitere Informationen finden Sie unter [Übersicht über App-Schutzrichtlinien](/mem/intune/apps/app-protection-policy).

## <a name="related-content"></a>Verwandte Inhalte

[Einrichten der grundlegenden Mobilität und Sicherheit](set-up.md) (Artikel)\
[Registrieren Ihres mobilen Geräts mithilfe von Basic Mobility and Security](enroll-your-mobile-device.md) (Artikel)\
[Verwalten von Geräten, die in der Mobile Device Management for Microsoft 365](manage-enrolled-devices.md) registriert sind (Artikel)\
[Details zu Geräten, die von Basic Mobility and Security](get-details-about-managed-devices.md) verwaltet werden (Artikel)