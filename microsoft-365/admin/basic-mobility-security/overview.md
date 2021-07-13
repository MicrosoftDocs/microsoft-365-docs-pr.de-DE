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
- AdminTemplateSet
search.appverid:
- MET150
description: Verwenden Sie Basic Mobility and Security, um Gerätesicherheitsrichtlinien und Zugriffsregeln festzulegen.
ms.openlocfilehash: 1d1376ec39f7249dfffb94c666b2fdcfa07641a0
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394075"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Übersicht über grundlegende Mobilität und Sicherheit für Microsoft 365

Sie können mobile Geräte verwalten und schützen, wenn sie mit Ihrer Microsoft 365 Organisation verbunden sind, indem Sie grundlegende Mobilität und Sicherheit verwenden. Mobile Geräte wie Smartphones und Tablets für den Zugriff auf E-Mails, Kalender, Kontakte und Dokumente am Arbeitsplatz spielen eine große Rolle, um sicherzustellen, dass Mitarbeiter jederzeit und überall ihre Arbeit erledigen können. Daher ist es wichtig, dass Sie die Informationen Ihrer Organisation schützen, wenn Benutzer Geräte verwenden. Sie können basic Mobility and Security verwenden, um Gerätesicherheitsrichtlinien und Zugriffsregeln festzulegen und mobile Geräte zu löschen, wenn sie verloren gehen oder gestohlen werden.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Grundlegendes Setup für Mobilität und Sicherheit":::

## <a name="what-types-of-devices-can-you-manage"></a>Welche Arten von Geräten können Sie verwalten?

Sie können basic Mobility and Security verwenden, um viele Arten von mobilen Geräten wie Windows Phone, Android, iPhone und iPad zu verwalten. Um mobile Geräte zu verwalten, die von Personen in Ihrer Organisation verwendet werden, muss jede Person über eine entsprechende Microsoft 365-Lizenz verfügen, und ihr Gerät muss in Basic Mobility and Security registriert sein.

Informationen dazu, was Basic Mobility and Security für jeden Gerätetyp unterstützt, finden Sie unter ["Funktionen der grundlegenden Mobilität und Sicherheit".](capabilities.md)

## <a name="setup-steps-for-basic-mobility-and-security"></a>Einrichtungsschritte für grundlegende Mobilität und Sicherheit

Ein Microsoft 365 globaler Administrator muss die folgenden Schritte ausführen, um grundlegende Mobilität und Sicherheit zu aktivieren und einzurichten. Ausführliche Schritte finden Sie unter "Einrichten der [grundlegenden Mobilität und Sicherheit".](set-up.md) 

Hier ist eine Zusammenfassung der Schritte:

**Schritt 1:** Aktivieren Sie Die grundlegende Mobilität und Sicherheit, indem Sie die folgenden Schritte im  [Abschnitt "Grundlegende Mobilität und Sicherheit einrichten"](set-up.md)ausführen.

**Schritt 2:** Richten Sie basic Mobility and Security ein, indem Sie beispielsweise ein APNs-Zertifikat zum Verwalten von iOS-Geräten erstellen und einen DNS-Eintrag (Domain Name System) für Ihre Domäne hinzufügen, um Windows Telefone zu unterstützen.

**Schritt 3:** Erstellen Sie Geräterichtlinien, und wenden Sie sie auf Benutzergruppen an. Wenn Sie dies tun, erhalten Ihre Benutzer eine Registrierungsnachricht auf ihrem Gerät, und wenn sie die Registrierung abgeschlossen haben, werden ihre Geräte durch die Richtlinien eingeschränkt, die Sie für sie eingerichtet haben. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit basic Mobility and Security.](enroll-your-mobile-device.md) 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Sicherheits- und Mobilitätsrichtlinieneinstellungen":::

## <a name="device-management-tasks"></a>Geräteverwaltungsaufgaben

Nachdem Sie Basic Mobility and Security eingerichtet haben und Ihre Benutzer ihre Geräte registriert haben, können Sie die Geräte verwalten, den Zugriff blockieren oder ein Gerät bei Bedarf zurücksetzen. Weitere Informationen zu einigen allgemeinen Aufgaben der Geräteverwaltung, einschließlich der Aufgaben, finden Sie unter Verwalten von Geräten, die bei der [mobilen Geräteverwaltung für Microsoft 365 registriert sind.](manage-enrolled-devices.md)

## <a name="other-ways-to-manage-devices-and-apps"></a>Weitere Möglichkeiten zum Verwalten von Geräten und Apps

Wenn Sie nur die Verwaltung mobiler Apps (Mobile App Management, MAM) benötigen, bietet Intune vielleicht für Personen, die Arbeitsprojekte auf ihren eigenen Geräten aktualisieren, eine weitere Option neben der Registrierung und Verwaltung von Geräten. Mit einem Intune-Abonnement können Sie MAM-Richtlinien über das Azure-Portal einrichten, auch wenn die Geräte der Benutzer nicht in Intune registriert sind. Weitere Informationen finden Sie unter [Übersicht über App-Schutzrichtlinien.](/mem/intune/apps/app-protection-policy)

## <a name="related-content"></a>Verwandte Inhalte

[Einrichten der grundlegenden Mobilität und Sicherheit](set-up.md) (Artikel)\
[Registrieren Ihres mobilen Geräts mit basic Mobility and Security](enroll-your-mobile-device.md) (Artikel)\
[Verwalten von Geräten,](manage-enrolled-devices.md) die für die Verwaltung mobiler Geräte für Microsoft 365 registriert sind (Artikel)\
[Abrufen von Details zu Geräten, die von Basic Mobility and Security verwaltet werden](get-details-about-managed-devices.md) (Artikel)