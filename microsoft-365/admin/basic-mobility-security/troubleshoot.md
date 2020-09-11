---
title: Problembehandlung bei grundlegender Mobilität und Sicherheit
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
description: Führen Sie die folgenden Schritte aus, um grundlegende Mobilitäts-und Sicherheitsprobleme zu ermitteln.
ms.openlocfilehash: 43e7533e598f769dd5f2bcae28c4252f96a9be76
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430179"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Problembehandlung bei grundlegender Mobilität und Sicherheit

Wenn Sie beim Versuch, ein Gerät in grundlegender Mobilität und Sicherheit zu registrieren, Probleme haben, führen Sie die Schritte hier aus, um das Problem zu ermitteln. Wenn das Problem durch die allgemeinen Schritte nicht behoben werden kann, lesen Sie einen der nachfolgenden Abschnitte mit bestimmten Schritten für Ihren Gerätetyp.

## <a name="steps-to-try-first"></a>Schritte zum ersten Versuch

Überprüfen Sie zunächst Folgendes:

- Stellen Sie sicher, dass das Gerät nicht bereits mit einem anderen Anbieter für die Verwaltung mobiler Geräte wie InTune registriert ist.
    
- Stellen Sie sicher, dass das Gerät auf das richtige Datum und die korrekte Uhrzeit festgelegt ist.
    
- Wechseln Sie zu einem anderen WLAN-oder Mobilfunknetz auf dem Gerät.
    
- Für Android-oder IOS-Geräte deinstallieren Sie die Intune-Unternehmens Portal-App auf dem Gerät, und installieren Sie Sie erneut. 

## <a name="ios-phone-or-tablet"></a>IOS-Telefon oder-Tablet

- Stellen Sie sicher, dass Sie ein APNs-Zertifikat eingerichtet haben. Weitere Informationen finden Sie unter [Erstellen eines APNs-Zertifikats für IOS-Geräte](create-an-apns-certificate-for-ios-devices.md).
    
-  **Settings**   >  **General**   > Stellen Sie sicher, dass in Einstellungen Allgemeines **Profil (oder Geräteverwaltung)** kein Verwaltungsprofil bereits installiert ist. Wenn dies der Fall ist, entfernen Sie Sie.
    
- Wenn die Fehlermeldung "Gerät konnte nicht registriert werden" angezeigt wird, melden Sie sich bei Microsoft 365 an, und stellen Sie sicher, dass dem Benutzer, der sich am Gerät angemeldet hat, eine Lizenz mit Exchange Online zugewiesen wurde.
    
- Wenn die Fehlermeldung "Profil konnte nicht installiert werden" angezeigt wird, führen Sie einen der folgenden Schritte aus:
    
    - Stellen Sie sicher, dass Safari der Standardbrowser auf dem Gerät ist und dass Cookies nicht deaktiviert sind.
    
    - Starten Sie das Gerät neu, und navigieren Sie dann zu Portal.Manage.Microsoft.com. Melden Sie sich mit Ihrer Microsoft 365-Benutzer-ID und Ihrem Kennwort an, und versuchen Sie, das Profil manuell zu installieren.    

## <a name="windows-rt"></a>Windows RT

- Stellen Sie sicher, dass Ihre Domäne in Microsoft 365 für die Verwendung von grundlegender Mobilität und Sicherheit eingerichtet ist. Weitere Informationen finden Sie unter [Einrichten von Basic Mobility and Security](set-up.md).
    
- Stellen Sie sicher, dass der Benutzer **die Option "Anmelden" wählt,**   anstatt " **beitreten**" auszuwählen.    

## <a name="windows-10-pc"></a>Windows 10-PC

- Stellen Sie sicher, dass Ihre Domäne in Microsoft 365 für die Verwendung von grundlegender Mobilität und Sicherheit eingerichtet ist. Weitere Informationen finden Sie unter [Einrichten von Basic Mobility and Security](set-up.md).
    
- Wenn Sie nicht über Azure Active Directory Premium verfügen, müssen Sie sicherstellen, dass der Benutzer **nur in der Geräteverwaltung registrieren**auswählt,   anstatt **Connect**auszuwählen.

## <a name="android-phone-or-tablet"></a>Android-Telefon oder-Tablet

- Stellen Sie sicher, dass auf dem Gerät Android 4,4 oder höher installiert ist.
    
- Stellen Sie sicher, dass Chrome auf dem neuesten Stand ist und als Standardbrowser festgelegt ist.
    
- Wenn die Fehlermeldung "Wir konnten dieses Gerät nicht registrieren" angezeigt wird, melden Sie sich bei Microsoft 365 an, und stellen Sie sicher, dass dem Benutzer, der sich am Gerät angemeldet hat, eine Lizenz zugewiesen wurde, die Exchange Online enthält.
    
- Überprüfen Sie den Benachrichtigungsbereich auf dem Gerät, um festzustellen, ob alle erforderlichen Endbenutzeraktionen ausstehen, und führen Sie, falls dies der Fall ist, die Aktionen aus.