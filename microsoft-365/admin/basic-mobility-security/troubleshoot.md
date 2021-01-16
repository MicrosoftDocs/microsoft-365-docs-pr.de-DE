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
description: Führen Sie die folgenden Schritte aus, um Probleme mit der einfachen Mobilität und Sicherheit nachverfolgt zu werden.
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876852"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Problembehandlung für grundlegende Mobilität und Sicherheit

Wenn beim Versuch, ein Gerät in Basic Mobility and Security zu registrieren, Probleme auftreten, führen Sie die hier gezeigten Schritte aus, um das Problem zu beheben. Wenn das Problem mit den allgemeinen Schritten nicht behoben wird, finden Sie weitere Informationen in einem der späteren Abschnitte mit spezifischen Schritten für Ihren Gerätetyp.

## <a name="steps-to-try-first"></a>Schritte zum ersten Versuch

Überprüfen Sie zunächst Folgendes:

- Stellen Sie sicher, dass das Gerät noch nicht bei einem anderen Anbieter für die Verwaltung mobiler Geräte registriert ist, z. B. Intune.

- Stellen Sie sicher, dass das Gerät auf das richtige Datum und die richtige Uhrzeit festgelegt ist.

- Wechseln Sie auf dem Gerät zu einem anderen WLAN oder Mobilfunknetz.

- Deinstallieren Sie für Android- oder iOS-Geräte die Intune-Unternehmensportal-App auf dem Gerät, und installieren Sie sie erneut. 

## <a name="ios-phone-or-tablet"></a>iOS-Smartphone oder -Tablet

- Stellen Sie sicher, dass Sie ein APNs-Zertifikat eingerichtet haben. Weitere Informationen finden Sie unter [Erstellen eines APNs-Zertifikats für iOS-Geräte.](create-an-apns-certificate-for-ios-devices.md)

- Stellen **Sie in**   >  **den** Einstellungen "Allgemeines   >  **Profil" (oder "Geräteverwaltung")** sicher, dass ein Verwaltungsprofil noch nicht installiert ist. Wenn dies der Benutzer ist, entfernen Sie ihn.

- Wenn die Fehlermeldung "Gerät konnte nicht registriert werden" angezeigt wird, melden Sie sich bei Microsoft 365 an, und stellen Sie sicher, dass dem Benutzer, der am Gerät angemeldet ist, eine Lizenz zugewiesen wurde, die Exchange Online enthält.

- Wenn die Fehlermeldung "Profil konnte nicht installiert werden" angezeigt wird, probieren Sie eine der folgenden Schritte aus:

    - Stellen Sie sicher, dass Safari der Standardbrowser auf dem Gerät ist und cookies nicht deaktiviert sind.

    - Starten Sie das Gerät neu, und navigieren Sie dann zu portal.manage.microsoft.com. Melden Sie sich mit Ihrer Microsoft 365-Benutzer-ID und Ihrem Kennwort an, und versuchen Sie, das Profil manuell zu installieren.

## <a name="windows-rt"></a>Windows RT

- Stellen Sie sicher, dass Ihre Domäne in Microsoft 365 für die Verwendung von Basic Mobility and Security eingerichtet ist. Weitere Informationen finden Sie unter [Einrichten von Basic Mobility and Security](set-up.md).
    
- Stellen Sie sicher, dass **** der Benutzer "Aktivieren" und   nicht "Beitreten" **aus.**

## <a name="windows-10-pc"></a>Windows 10-PC

- Stellen Sie sicher, dass Ihre Domäne in Microsoft 365 für die Verwendung von Basic Mobility and Security eingerichtet ist. Weitere Informationen finden Sie unter [Einrichten von Basic Mobility and Security](set-up.md).
    
- Wenn Sie nicht über Azure Active Directory Premium **** verfügen, stellen Sie sicher, dass der Benutzer nur die Geräteverwaltung registrieren und nicht    **"Verbinden" aus.**

## <a name="android-phone-or-tablet"></a>Smartphone oder Tablet für Android

- Stellen Sie sicher, dass auf dem Gerät Android 4.4 oder höher ausgeführt wird.

- Stellen Sie sicher, dass Chrome auf dem neuesten Stand ist und als Standardbrowser festgelegt ist.

- Wenn die Fehlermeldung "Dieses Gerät konnte nicht registriert werden" angezeigt wird, melden Sie sich bei Microsoft 365 an, und stellen Sie sicher, dass dem Benutzer, der am Gerät angemeldet ist, eine Lizenz mit Exchange Online zugewiesen wurde.

- Überprüfen Sie den Benachrichtigungsbereich auf dem Gerät, um zu sehen, ob erforderliche Endbenutzeraktionen ausstehen, und führen Sie, falls dies der Fall ist, die Aktionen aus.