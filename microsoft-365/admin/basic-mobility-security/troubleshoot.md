---
title: Problembehandlung für grundlegende Mobilität und Sicherheit
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
description: Führen Sie diese Schritte aus, um grundlegende Mobilitäts- und Sicherheitsprobleme zu verfolgen.
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876852"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Problembehandlung für grundlegende Mobilität und Sicherheit

Wenn beim Versuch, ein Gerät in Basic Mobility and Security zu registrieren, Probleme auftreten, führen Sie die hier gezeigten Schritte aus, um das Problem nach zu verfolgen. Wenn das Problem durch die allgemeinen Schritte nicht behoben werden kann, lesen Sie einen der späteren Abschnitte mit bestimmten Schritten für Ihren Gerätetyp.

## <a name="steps-to-try-first"></a>Erste Schritte

Überprüfen Sie zu Beginn Folgendes:

- Stellen Sie sicher, dass das Gerät noch nicht bei einem anderen Anbieter für die Verwaltung mobiler Geräte registriert ist, z. B. Intune.

- Stellen Sie sicher, dass das Gerät auf das richtige Datum und die richtige Uhrzeit festgelegt ist.

- Wechseln Sie zu einem anderen WLAN oder Mobilfunknetzwerk auf dem Gerät.

- Deinstallieren und installieren Sie für Android- oder iOS-Geräte die Intune-Unternehmensportal app auf dem Gerät. 

## <a name="ios-phone-or-tablet"></a>iOS-Smartphone oder -Tablet

- Stellen Sie sicher, dass Sie ein APNs-Zertifikat eingerichtet haben. Weitere Informationen finden Sie unter [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).

- Stellen **Einstellungen**   >  ****   >  **Allgemeines Profil (oder Geräteverwaltung)** sicher, dass ein Verwaltungsprofil noch nicht installiert ist. Wenn dies der Benutzer ist, entfernen Sie ihn.

- Wenn die Fehlermeldung "Gerät konnte sich nicht registrieren" angezeigt wird, melden Sie sich bei Microsoft 365 an, und stellen Sie sicher, dass dem Benutzer, der beim Gerät angemeldet ist, eine Lizenz zugewiesen wurde, die Exchange Online enthält.

- Wenn die Fehlermeldung "Profil konnte nicht installiert werden" angezeigt wird, führen Sie eine der folgenden Schritte aus:

    - Stellen Sie sicher, dass Safari der Standardbrowser auf dem Gerät ist und cookies nicht deaktiviert sind.

    - Starten Sie das Gerät neu, und navigieren Sie dann zu portal.manage.microsoft.com. Melden Sie sich mit Microsoft 365 Benutzer-ID und Kennwort an, und versuchen Sie, das Profil manuell zu installieren.

## <a name="windows-rt"></a>Windows RT

- Stellen Sie sicher, dass Ihre Domäne in der Microsoft 365 für die Grundlegende Mobilität und Sicherheit eingerichtet ist. Weitere Informationen finden Sie unter [Set up Basic Mobility and Security](set-up.md).
    
- Stellen Sie sicher, dass der Benutzer **"Aktivieren"**   statt **"Beitreten" wählt.**

## <a name="windows-10-pc"></a>Windows 10 PC

- Stellen Sie sicher, dass Ihre Domäne in der Microsoft 365 für die Grundlegende Mobilität und Sicherheit eingerichtet ist. Weitere Informationen finden Sie unter [Set up Basic Mobility and Security](set-up.md).
    
- Stellen Sie sicher, Azure Active Directory Premium, dass der Benutzer **** nur für die Geräteverwaltung registrieren anstatt sich für    **Verbinden.**

## <a name="android-phone-or-tablet"></a>Android-Smartphone oder -Tablet

- Stellen Sie sicher, dass auf dem Gerät Android 4.4 oder höher ausgeführt wird.

- Stellen Sie sicher, dass Chrome auf dem neuesten Stand ist und als Standardbrowser festgelegt ist.

- Wenn die Fehlermeldung "Wir konnten dieses Gerät nicht registrieren" angezeigt wird, melden Sie sich bei Microsoft 365 an, und stellen Sie sicher, dass dem Benutzer, der beim Gerät angemeldet ist, eine Lizenz zugewiesen wurde, die Exchange Online enthält.

- Überprüfen Sie den Benachrichtigungsbereich auf dem Gerät, um zu sehen, ob erforderliche Endbenutzeraktionen ausstehen, und führen Sie, falls dies der Fall ist, die Aktionen aus.