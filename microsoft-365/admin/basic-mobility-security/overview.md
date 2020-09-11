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
description: Verwenden Sie die grundlegende Mobilität und Sicherheit, um Gerätesicherheitsrichtlinien und Zugriffsregeln festzulegen.
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430177"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Übersicht über grundlegende Mobilität und Sicherheit für Microsoft 365

Sie können mobile Geräte verwalten und sichern, wenn Sie mit der Microsoft 365-Organisation über grundlegende Mobilität und Sicherheit verbunden sind. Mobile Geräte wie Smartphones und Tablets für den Zugriff auf E-Mails, Kalender, Kontakte und Dokumente am Arbeitsplatz spielen eine große Rolle, um sicherzustellen, dass Mitarbeiter jederzeit und überall ihre Arbeit erledigen können. Daher ist es wichtig, dass Sie die Informationen Ihrer Organisation schützen, wenn Personen Geräte verwenden. Sie können grundlegende Mobilitäts-und Sicherheitseinstellungen zum Festlegen von Gerätesicherheitsrichtlinien und Zugriffsregeln sowie zum Abwischen mobiler Geräte verwenden, wenn diese verloren gehen oder gestohlen werden.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Grundlegendes Mobilitäts-und Sicherheits Setup":::

## <a name="what-types-of-devices-can-you-manage"></a>Welche Arten von Geräten können Sie verwalten?

Sie können die grundlegende Mobilität und Sicherheit verwenden, um viele Arten von mobilen Geräten wie Windows Phone, Android, iPhone und iPad zu verwalten. Zum Verwalten von mobilen Geräten, die von Personen in Ihrer Organisation verwendet werden, muss jede Person über eine gültige Microsoft 365-Lizenz verfügen, und Ihr Gerät muss in Basic Mobility and Security registriert sein.

Informationen zu den grundlegenden Mobilitäts-und Sicherheitseinstellungen für die einzelnen Gerätetypen finden Sie unter [Features of Basic Mobility and Security](capabilities.md).

## <a name="setup-steps-for-basic-mobility-and-security"></a>Setup Schritte für grundlegende Mobilität und Sicherheit

Ein globaler Administrator von Microsoft 365 muss die folgenden Schritte ausführen, um grundlegende Mobilität und Sicherheit zu aktivieren und einzurichten. Ausführliche Schritte finden Sie in den Anweisungen unter [Einrichten von grundlegender Mobilität und Sicherheit](set-up.md). 

Im folgenden finden Sie eine Zusammenfassung der Schritte:

**Schritt 1:** Aktivieren Sie die grundlegende Mobilität und Sicherheit, indem Sie die folgenden Schritte im [Einrichten von Basic Mobility and Security](set-up.md)durchführen.

**Schritt 2:** Richten Sie grundlegende Mobilität und Sicherheit ein, indem Sie beispielsweise ein APNs-Zertifikat erstellen, um IOS-Geräte zu verwalten und einen Domain Name System (DNS)-Eintrag für Ihre Domäne zur Unterstützung von Windows phones hinzuzufügen.

**Schritt 3:** Erstellen Sie Geräterichtlinien, und wenden Sie Sie auf Benutzergruppen an. Wenn Sie dies tun, erhalten Ihre Benutzer eine Registrierungsnachricht auf Ihrem Gerät, und wenn Sie die Registrierung abgeschlossen haben, werden Ihre Geräte durch die Richtlinien eingeschränkt, die Sie für Sie eingerichtet haben. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device.md). 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Sicherheits-und mobilitätsrichtlinien Einstellungen":::

## <a name="device-management-tasks"></a>Geräte Verwaltungsaufgaben

Nachdem Sie grundlegende Mobilitäts-und Sicherheitseinstellungen eingerichtet haben und Ihre Benutzer ihre Geräte registriert haben, können Sie die Geräte verwalten, den Zugriff blockieren oder ein Gerät löschen, falls erforderlich. Weitere Informationen zu einigen gängigen Geräte Verwaltungsaufgaben, einschließlich der Stelle, an der die Aufgaben durchgeführt werden können, finden Sie unter [Verwalten von Geräten, die in der mobilen Geräteverwaltung für Microsoft 365 registriert](manage-enrolled-devices.md)sind.

## <a name="other-ways-to-manage-devices-and-apps"></a>Andere Methoden zum Verwalten von Geräten und Apps

Wenn Sie nur Mobile App Verwaltung (MAM) benötigen, möglicherweise für Personen, die Arbeitsprojekte auf Ihren eigenen Geräten aktualisieren, bietet InTune neben der Registrierung und Verwaltung von Geräten eine weitere Option. Mit einem InTune-Abonnement können Sie MAM-Richtlinien mithilfe des Azure-Portals einrichten, selbst wenn die Geräte der Benutzer nicht in InTune registriert sind. Weitere Informationen finden Sie unter [App Protection Policies Overview](https://go.microsoft.com/fwlink/?LinkId=2132517).

## <a name="related-topics"></a>Verwandte Themen

[Einrichten von grundlegender Mobilität und Sicherheit](set-up.md)

[Registrieren Ihres mobilen Geräts mit grundlegender Mobilität und Sicherheit](enroll-your-mobile-device.md)

[Verwalten von Geräten, die in der Verwaltung mobiler Geräte für Microsoft 365 registriert sind](manage-enrolled-devices.md)

[Abrufen von Details zu Geräten, die von Basic Mobility and Security verwaltet werden](get-details-about-managed-devices.md)