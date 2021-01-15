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
ms.openlocfilehash: ca919798480698f92bba094c3755b3eccce30888
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867970"
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

- Richtlinien für bedingten Zugriff: Wenn Sie neue Richtlinien für bedingten Zugriff im Zusammenhang mit Azure AD, Microsoft Intune oder Microsoft Defender for Endpoint nach der Registrierung von Microsoft Managed Desktop erstellen, schließen Sie die Azure AD-Gruppe "Modern **Workplace Service Accounts"** aus. Die Schritte finden Sie unter [Bedingter Zugriff: Benutzer und Gruppen.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop verwaltet separate Richtlinien für bedingten Zugriff, um den Zugriff auf diese Konten einzuschränken. Um die Microsoft Managed Desktop-Richtlinie für bedingten Zugriff (**Modern Workplace – Secure Workstation)** zu überprüfen, wechseln Sie zu Microsoft Endpoint Manager, und navigieren Sie zu bedingten **Zugriff** in **Endpoint Security.** Ändern Sie keine Azure AD-Richtlinien für bedingten Zugriff, die von Microsoft Managed Desktop erstellt wurden und deren Name "Moderner Arbeitsplatz" ist.

- Mehrstufige Authentifizierung: Wenn Sie neue mehrstufige Authentifizierungsanforderungen in Richtlinien für bedingten Zugriff im Zusammenhang mit Azure AD, Intune oder Microsoft Defender für Endpoint nach der Registrierung von Microsoft Managed Desktop erstellen, schließen Sie die Azure AD-Gruppe "Modern **Workplace Service Accounts"** aus. Die Schritte finden Sie unter [Bedingter Zugriff: Benutzer und Gruppen.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop verwaltet separate Richtlinien für bedingten Zugriff, um den Zugriff auf Mitglieder dieser Gruppe einzuschränken. Um die Microsoft Managed Desktop-Richtlinie für bedingten Zugriff (**Modern Workplace -**) zu überprüfen, wechseln Sie zu Microsoft Endpoint Manager, und navigieren Sie zu **bedingten Zugriff** in Endpoint **Security.** 

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
