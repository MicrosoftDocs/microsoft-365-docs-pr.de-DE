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
ms.openlocfilehash: e78f0123c909c90ff90be913e8775cc1e5b30313
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777099"
---
# <a name="adjust-settings-after-enrollment"></a>Anpassen der Einstellungen nach der Registrierung

Nachdem Sie die Registrierung in Microsoft Managed Desktop abgeschlossen haben, müssen Sie die in diesem Artikel angegebenen Einstellungen für Microsoft InTune und Azure Active Directory (Azure AD) anpassen, um die Verwaltung zu ermöglichen und die Sicherheit aufrechtzuerhalten. Legen Sie die folgenden Einstellungen fest, um bestimmte Azure Ad Gruppen auszuschließen, die Microsoft Managed Desktop-Geräte und-Benutzer enthalten. Schritte zum Ausschließen von Gruppen finden Sie unter [Conditional Access: users and Groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).

> [!NOTE]
> Wenn Sie Änderungen nach der Registrierung für Richtlinien in Microsoft InTune, Azure Active Directory oder Microsoft 365 vornehmen, kann es sein, dass der Microsoft Managed Desktop möglicherweise nicht mehr ordnungsgemäß funktioniert. Um Probleme mit Microsoft Managed Desktop-Vorgängen zu vermeiden, überprüfen Sie die spezifischen Einstellungen, die unter [Beheben von Problemen mit dem Readiness Assessment Tool](../get-ready/readiness-assessment-fix.md) beschrieben wurden, bevor Sie Richtlinien ändern.


## <a name="microsoft-intune-settings"></a>Microsoft InTune-Einstellungen

- Autopilot-Bereitstellungsprofil: für Autopilot-Profile, die von Administratoren in Ihrem Unternehmen erstellt werden, schließen Sie die **modernen Arbeitsplatz Geräte aus – alle** Azure Ad Gruppe. Schritte finden Sie unter [Registrieren von Windows-Geräten in InTune mithilfe von Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Schließen Sie nicht die **modernen Arbeitsplatz Geräte aus – alle** Azure Ad Gruppe aus allen von Microsoft Managed Desktop erstellten Bereitstellungsrichtlinien, die über den Namen "moderner Arbeitsplatz" verfügen (beispielsweise ein **modernes Arbeitsplatz-Autopilot-Profil**). 
- Richtlinien für bedingten Zugriff: für von Administratoren in Ihrem Unternehmen erstellte Richtlinien für den bedingten Zugriff schließen Sie die **Dienstkonten für moderne Arbeitsplatz Dienste** Azure Ad Gruppe aus. Schritte finden Sie unter [bedingter Zugriff: Benutzer und Gruppen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Schließen Sie nicht die **modernen Arbeitsplatz Geräte aus – alle** Azure Ad Gruppe von Richtlinien, die von Microsoft Managed Desktop erstellt wurden und die den Namen "moderner Arbeitsplatz" aufweisen (beispielsweise " **moderne Arbeitsplatz sichere Arbeitsstation**").
- Mehrstufige Authentifizierung: Stellen Sie sicher, dass von Administratoren in Ihrem Unternehmen erstellte bedingte Zugriffsrichtlinien, die mehrstufige Authentifizierung erfordern, die Azure Ad Gruppe für **moderne Arbeitsplatz Dienstkonten** ausschließen. Weitere Informationen finden Sie unter [bedingter Zugriffsrichtlinien](../get-ready/readiness-assessment-fix.md#conditional-access-policies) und [bedingter Zugriff: MFA für alle Benutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).
- Sicherheitsbasislinie: für von Administratoren in Ihrem Unternehmen erstellte Sicherheitsbasis Richtlinien schließen Sie die **modernen Arbeitsplatz Geräte aus – alle**  Azure Ad Gruppe. Eine schrittweise Anleitung finden Sie unter [use Security Baselines to configure Windows 10 Devices in InTune](https://docs.microsoft.com/mem/intune/protect/security-baselines). Schließen Sie nicht die **modernen Arbeitsplatz Geräte aus – alle** Azure Ad Gruppe von Richtlinien, die von Microsoft Managed Desktop erstellt wurden und die den Namen "moderner Arbeitsplatz" aufweisen (beispielsweise " **moderne Arbeitsplatz-Sicherheitsbasis**").
- Windows 10-Update-Ring: für Windows 10 Update Ring Policies, die von Administratoren in Ihrem Unternehmen erstellt wurden, schließen Sie die **modernen Arbeitsplatz Geräte aus – alle**  Azure Ad Gruppe. Eine schrittweise Anleitung finden Sie unter [Manage Windows 10 Softwareupdates in InTune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure). Schließen Sie nicht die **modernen Arbeitsplatz Geräte aus – alle** Azure Ad Gruppe von Richtlinien, die von Microsoft Managed Desktop erstellt wurden und die den Namen "moderner Arbeitsplatz" aufweisen (beispielsweise die Update Richtlinie für **moderne Arbeitsplätze** ).


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
