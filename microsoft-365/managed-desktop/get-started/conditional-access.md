---
title: Anpassen der Einstellungen nach der Registrierung
description: Ausschließen bestimmter Microsoft-Konten
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 76a73372cc7517c3241390e58c28b0b02bffd664
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527697"
---
# <a name="adjust-settings-after-enrollment"></a>Anpassen der Einstellungen nach der Registrierung

Nachdem Sie die Registrierung in Microsoft Managed Desktop abgeschlossen haben, müssen Sie bestimmte Einstellungen für Microsoft InTune und Azure Active Directory (Azure AD) anpassen, um die Verwaltung zu ermöglichen und die Sicherheit aufrechtzuerhalten. Legen Sie die folgenden Einstellungen fest, um die Azure Ad Gruppen auszuschließen, die Microsoft Managed Desktop-Geräte und-Benutzer enthalten. Schritte zum Ausschließen von Gruppen finden Sie unter [Conditional Access: users and Groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).

## <a name="microsoft-intune-settings"></a>Microsoft InTune-Einstellungen

- Autopilot-Bereitstellungsprofil: schließt die **modernen Arbeitsplatz Geräte aus – alle**  Azure Ad Gruppe. Schritte finden Sie unter [Registrieren von Windows-Geräten in InTune mithilfe von Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).
- Richtlinien für bedingten Zugriff: schließt die **modernen Dienstkonten für den Arbeitsplatz** Azure Ad Gruppe aus. Schritte finden Sie unter [bedingter Zugriff: Benutzer und Gruppen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).
- Mehrstufige Authentifizierung: Stellen Sie sicher, dass alle bedingten Zugriffsrichtlinien, die mehrstufige Authentifizierung erfordern, die Azure Ad Gruppe für **moderne Arbeitsplatz Dienstkonten** ausschließen. Weitere Informationen finden Sie unter [bedingter Zugriffsrichtlinien](../get-ready/readiness-assessment-fix.md#conditional-access-policies) und [bedingter Zugriff: MFA für alle Benutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).
- Sicherheitsbasis: schließt die **modernen Arbeitsplatz Geräte aus – alle**  Azure Ad Gruppe. Eine schrittweise Anleitung finden Sie unter [use Security Baselines to configure Windows 10 Devices in InTune](https://docs.microsoft.com/mem/intune/protect/security-baselines).
- Windows 10-Update Ring: schließt die **modernen Arbeitsplatz Geräte aus – alle**  Azure Ad Gruppe. Eine schrittweise Anleitung finden Sie unter [Manage Windows 10 Softwareupdates in InTune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).


## <a name="azure-active-directory-settings"></a>Azure Active Directory-Einstellungen

Self-Service Password Reset: Wählen Sie **ausgewählte** Einstellung aus, und wählen Sie dann **moderne Arbeitsplatz Geräte – alle** Azure Ad Gruppe aus. Weitere Informationen finden Sie unter [Lernprogramm: Aktivieren von Benutzern zum Entsperren Ihres Kontos oder Zurücksetzen von Kennwörtern mithilfe von Azure Active Directory Self-Service Password Reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Schritte zum Einstieg in Microsoft Managed Desktop

1. [Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal](add-admin-contacts.md)
2. Anpassen von Einstellungen nach der Registrierung (dieser Artikel)
3. [Zuweisen von Lizenzen](assign-licenses.md)
4. [Intune-Unternehmensportal bereitstellen](company-portal.md)
5. [Aktivieren von Enterprise State Roaming](enterprise-state-roaming.md)
6. [Einrichten von Geräten](set-up-devices.md)
7. [Vorbereiten Ihrer Benutzer für die Verwendung von Geräten](get-started-devices.md)
8. [Bereitstellen von Apps](deploy-apps.md)
