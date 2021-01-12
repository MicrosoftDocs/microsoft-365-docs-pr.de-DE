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
ms.openlocfilehash: 88a832f6c4e17756bfb25ef5cb7c4c5ecedaf2c0
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794388"
---
# <a name="adjust-settings-after-enrollment"></a>Anpassen der Einstellungen nach der Registrierung

Nachdem Sie die Registrierung in Microsoft Managed Desktop abgeschlossen haben, müssen einige Verwaltungseinstellungen möglicherweise angepasst werden. Führen Sie zum Überprüfen und Anpassen bei Bedarf die folgenden Schritte aus:

1. Überprüfen Sie die im nächsten Abschnitt beschriebenen Microsoft Intune- und Azure Active Directory-Einstellungen.
2. Wenn eines der Elemente für Ihre Umgebung gilt, nehmen Sie die beschriebenen Anpassungen vor.
3. Wenn Sie überprüfen möchten, ob alle Einstellungen korrekt sind, können Sie das Tool für die Bereitschaftsbewertung erneut ausführen, um sicherzustellen, dass nichts mit Microsoft Managed Desktop in Konflikt steht. [](https://aka.ms/mmdart)

> [!NOTE]
> Wenn Sie nach der Registrierung von Richtlinien in Microsoft Intune, Azure Active Directory oder Microsoft 365, die Sich auf Microsoft Managed Desktop auswirken, Änderungen vornehmen, ist es möglich, dass Microsoft Managed Desktop nicht mehr ordnungsgemäß ausgeführt wird. Um Probleme mit dem Dienst zu vermeiden, überprüfen Sie die in ["Beheben](../get-ready/readiness-assessment-fix.md) von Problemen" beschriebenen Einstellungen, die vom Tool für die Bereitschaftsbewertung gefunden wurden, bevor Sie die dort aufgeführten Richtlinien ändern. Sie können das Tool für die Bereitschaftsbewertung auch jederzeit erneut ausführen.


## <a name="microsoft-intune-settings"></a>Microsoft Intune-Einstellungen

- Autopilot-Bereitstellungsprofil: Wenn Sie autopilot-Richtlinien verwenden, aktualisieren Sie jede, um die moderne Workplace Devices -All Azure **AD-Gruppe** auszuschließen. Um sie zu  aktualisieren, wählen Sie im Abschnitt "Ausgeschlossene Gruppen" unter "Aufgaben" die **Gruppe "Moderne** Arbeitsplatzgeräte – Alle Azure AD-Gruppen" **aus,** die während der Microsoft Managed Desktop-Registrierung erstellt wurde. Microsoft Managed Desktop hat außerdem ein Autopilotprofil erstellt, das den Namen "Modern Workplace" **(modern Workplace Autopilot Profile) hat.** Wenn Sie Ihre eigenen **Autopilotprofile** aktualisieren, stellen Sie sicher, dass Sie die Gruppe **"Modern Workplace Devices - All** Azure AD" nicht aus dem modern Workplace Autopilot Profile ausschließen, das von Microsoft Managed Desktop erstellt wurde. 

- Richtlinien für bedingten Zugriff: Schließen Sie für Richtlinien für bedingten Zugriff, die Sie erstellt haben, die Azure AD-Gruppe **"Modern Workplace Service Accounts"** aus. Die Schritte finden Sie unter [Bedingter Zugriff: Benutzer und Gruppen.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop hat außerdem einige Richtlinien für bedingten Zugriff erstellt, die alle "Modern Workplace" im Namen haben (z. B. **"Modern Workplace Secure Workstation").** Wenn Sie Ihre eigenen Richtlinien für  bedingten Zugriff aktualisieren, stellen Sie sicher, dass Sie die Gruppe **"Moderne** Workplace-Geräte – Alle Azure AD"-Gruppen nicht von richtlinien ausschließen, die von Microsoft Managed Desktop erstellt wurden.

- Mehrstufige Authentifizierung: Stellen Sie sicher, dass alle Richtlinien für bedingten Zugriff, die eine mehrstufige Authentifizierung erfordern, die Azure AD-Gruppe **"Modern Workplace Service Accounts"** ausschließen. Weitere Informationen finden Sie unter [Richtlinien für bedingten Zugriff](../get-ready/readiness-assessment-fix.md#conditional-access-policies) und [bedingter Zugriff: MFA für alle Benutzer erforderlich.](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)

- Windows 10-Updatering: Schließen Sie für alle von Ihnen erstellten Windows 10-Updateringrichtlinien die Gruppe **"Moderne** Arbeitsplatzgeräte – Alle Azure AD"-Gruppen aus jeder Richtlinie aus. Weitere Schritte finden Sie unter [Erstellen und Zuweisen von Updateringen.](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings) Microsoft Managed Desktop hat außerdem einige Updateringrichtlinien erstellt, die alle "Modern Workplace" im Namen haben (z. B. **Modern Workplace Update Policy [Broad]**, Modern Workplace Update Policy **[Fast]**, **Modern Workplace Update Policy [First]** und **Modern Workplace Update Policy [Test]**). Wenn Sie Ihre eigenen Richtlinien aktualisieren, stellen Sie sicher, dass Sie die **Gruppe "Moderne** Arbeitsplatzgeräte – Alle Azure AD" nicht von denjenigen ausschließen, die Microsoft Managed Desktop erstellt hat. 


## <a name="azure-active-directory-settings"></a>Azure Active Directory-Einstellungen

Self-Service-Kennwortzurücksetzung: Wenn Sie die Self-Service-Kennwortzurücksetzung für alle Benutzer verwenden, passen Sie die Zuweisung so an, dass Microsoft Managed Desktop -Dienstkonten ausgeschlossen werden. Um diese Zuweisung anzupassen, erstellen Sie eine dynamische Azure AD-Gruppe für alle Benutzer mit Ausnahme von *Microsoft* Managed Desktop-Dienstkonten, und verwenden Sie diese Gruppe dann für die Zuweisung anstelle von "alle Benutzer".

Im Folgenden finden Sie ein Beispiel für eine dynamische Abfrage, die Sie verwenden können, um die Dienstkonten zu finden und auszuschließen:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

Ersetzen Sie in dieser Abfrage @TENANT durch Ihren Mandantendomänennamen.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Schritte für die ersten Schritte mit Microsoft Managed Desktop

1. [Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal](add-admin-contacts.md)
2. Anpassen von Einstellungen nach der Registrierung (dieser Artikel)
3. [Zuweisen von Lizenzen](assign-licenses.md)
4. [Intune-Unternehmensportal bereitstellen](company-portal.md)
5. [Aktivieren von Enterprise State Roaming](enterprise-state-roaming.md)
6. [Einrichten von Geräten](set-up-devices.md)
7. [Vorbereiten Ihrer Benutzer für die Verwendung von Geräten](get-started-devices.md)
8. [Bereitstellen von Apps](deploy-apps.md)
