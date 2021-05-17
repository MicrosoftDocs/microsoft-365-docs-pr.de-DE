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
ms.openlocfilehash: 760fcb94ec6d84a55fe4b8c3cb3540ae29994ae3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918442"
---
# <a name="adjust-settings-after-enrollment"></a>Anpassen der Einstellungen nach der Registrierung

Nachdem Sie die Registrierung in Microsoft Managed Desktop abgeschlossen haben, müssen möglicherweise einige Verwaltungseinstellungen angepasst werden. Führen Sie die folgenden Schritte aus, um bei Bedarf zu überprüfen und anzupassen:

1. Überprüfen Sie die Microsoft Intune und Azure Active Directory, die im nächsten Abschnitt beschrieben werden.
2. Wenn eines der Elemente für Ihre Umgebung gilt, nehmen Sie die beschriebenen Anpassungen vor.
3. Wenn Sie überprüfen möchten, ob alle Einstellungen korrekt sind, können Sie das Tool für die Bereitschaftsbewertung erneut ausführen, um sicherzustellen, dass keine Konflikte mit Microsoft Managed Desktop. [](https://aka.ms/mmdart)

> [!NOTE]
> Wenn Sie nach der Registrierung an Richtlinien in Microsoft Intune, Azure Active Directory oder Microsoft 365, die sich auf Microsoft Managed Desktop auswirken, Änderungen vornehmen, ist es möglich, dass Microsoft Managed Desktop nicht mehr ordnungsgemäß ausgeführt wird. Um Probleme mit dem Dienst zu vermeiden, überprüfen Sie die spezifischen Einstellungen unter [Beheben](../get-ready/readiness-assessment-fix.md) von Problemen, die vom Tool für die Bereitschaftsbewertung gefunden wurden, bevor Sie die dort aufgeführten Richtlinien ändern. Sie können das Tool für die Bereitschaftsbewertung auch jederzeit erneut ausführen.


## <a name="microsoft-intune-settings"></a>Microsoft Intune Einstellungen

- Autopilot-Bereitstellungsprofil: Wenn Sie autopilot-Richtlinien verwenden, aktualisieren Sie jede, um die Gruppe Moderne Arbeitsplatzgeräte **–Alle** Azure AD auszuschließen. Um sie zu  aktualisieren, wählen Sie im Abschnitt Ausgeschlossene Gruppen unter Zuordnungen die Gruppe Moderne Arbeitsplatzgeräte **–Alle** Azure AD aus, die während der Registrierung Microsoft Managed Desktop wurde. Microsoft Managed Desktop wird auch ein Autopilot-Profil erstellt, das "Modern Workplace" im Namen **(modern Workplace Autopilot Profile) hat.** Achten Sie beim Aktualisieren Ihrer eigenen Autopilot-Profile darauf, dass Sie die Gruppe **Modern Workplace Devices -All** Azure AD nicht aus dem modern Workplace **Autopilot-Profil** ausschließen, das von Microsoft Managed Desktop. 

- Richtlinien für bedingten Zugriff: Wenn Sie neue Richtlinien für bedingten Zugriff im Zusammenhang mit Azure AD,  Microsoft Intune oder Microsoft Defender for Endpoint nach der registrierung Microsoft Managed Desktop erstellen, schließen Sie die Azure AD-Gruppe moderne Arbeitsplatzdienstkonten aus. Weitere Schritte finden Sie unter [Conditional Access: Users and groups](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop verwaltet separate Richtlinien für bedingten Zugriff, um den Zugriff auf diese Konten einzuschränken. Um die Richtlinie für Microsoft Managed Desktop bedingten Zugriff (**Modern Workplace – Secure Workstation**) zu überprüfen, wechseln Sie zu Microsoft Endpoint Manager, und navigieren Sie zu Bedingter Zugriff in Endpoint **Security**.  Ändern Sie keine Azure AD-Richtlinien für bedingten Zugriff, die von Microsoft Managed Desktop erstellt wurden, die "Modern Workplace" im Namen haben.

- Mehrstufige Authentifizierung: Wenn Sie neue mehrstufige Authentifizierungsanforderungen in Richtlinien für bedingten Zugriff im Zusammenhang mit  Azure AD, Intune oder Microsoft Defender for Endpoint nach der registrierung Microsoft Managed Desktop erstellen, schließen Sie die Azure AD-Gruppe moderne Arbeitsplatzdienstkonten aus. Weitere Schritte finden Sie unter [Conditional Access: Users and groups](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop verwaltet separate Richtlinien für bedingten Zugriff, um den Zugriff auf Mitglieder dieser Gruppe einzuschränken. Um die Richtlinie Microsoft Managed Desktop bedingten Zugriff (**Modern Workplace -**) zu überprüfen, wechseln Sie zu Microsoft Endpoint Manager, und navigieren Sie zu Bedingter Zugriff in Endpoint **Security**.  

- Windows 10 Updatering: Schließen Sie für alle Windows 10 erstellten Updateringrichtlinien die Gruppe Moderne Arbeitsplatzgeräte **–Alle** Azure AD aus jeder Richtlinie aus. Weitere Schritte finden Sie unter [Create and assign update rings](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings). Microsoft Managed Desktop werden auch einige Updateringrichtlinien erstellt, die alle "Modern Workplace" im Namen haben (z. B. Modern **Workplace Update Policy [Broad]**, **Modern Workplace Update Policy [Fast]**, **Modern Workplace Update Policy [First]** und **Modern Workplace Update Policy [Test]**). Wenn Sie Ihre eigenen Richtlinien aktualisieren, stellen Sie sicher, dass Sie die Gruppe Moderne Arbeitsplatzgeräte **–Alle** Azure AD nicht von den erstellten Microsoft Managed Desktop ausschließen. 


## <a name="azure-active-directory-settings"></a>Azure Active Directory Einstellungen

Self-Service-Kennwortzurücksetzung: Wenn Sie die Self-Service-Kennwortzurücksetzung für alle Benutzer verwenden, passen Sie die Zuweisung an, um Microsoft Managed Desktop auszuschließen. Um diese Zuordnung anzupassen, erstellen Sie eine  dynamische Azure AD-Gruppe für alle Benutzer mit Ausnahme Microsoft Managed Desktop Dienstkonten, und verwenden Sie diese Gruppe dann für die Zuweisung anstelle von "allen Benutzern".

Um Ihnen beim Suchen und Ausschließen der Dienstkonten zu helfen, finden Sie hier ein Beispiel für eine dynamische Abfrage, die Sie verwenden können:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

Ersetzen Sie in dieser Abfrage @TENANT Durch ihren Mandantendomänennamen.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Schritte zum Einstieg in Microsoft Managed Desktop

1. [Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal](add-admin-contacts.md)
2. Anpassen von Einstellungen nach der Registrierung (in diesem Artikel)
3. [Zuweisen von Lizenzen](assign-licenses.md)
4. [Intune-Unternehmensportal bereitstellen](company-portal.md)
5. [Aktivieren von Enterprise State Roaming](enterprise-state-roaming.md)
6. [Einrichten von Geräten](set-up-devices.md)
7. [Vorbereiten Ihrer Benutzer für die Verwendung von Geräten](get-started-devices.md)
8. [Bereitstellen von Apps](deploy-apps.md)