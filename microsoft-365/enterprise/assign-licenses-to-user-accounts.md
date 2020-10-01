---
title: Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Beschreibt, wie Sie Benutzerkonten Microsoft 365-Lizenzen einzeln oder basierend auf einer Gruppenmitgliedschaft zuweisen.
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326507"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Für das nur-Cloud-Identitätsmodell können Sie Microsoft 365-Lizenzen den Benutzerkonten zuweisen, je nachdem, wie Sie erstellt wurden.

Wenn Active Directory-Domänendienste (AD DS) Benutzerkonten zum ersten Mal synchronisiert werden, wird für das hybride Identitätsmodell nicht automatisch ein Standort oder eine Microsoft 365-Lizenz zugewiesen. **Sie müssen jedes Benutzerkonto mit einem Benutzerstandort vor oder zusammen mit dem Zuweisen einer Lizenz konfigurieren.**

In beiden Fällen müssen Sie Benutzerkonten eine Lizenz zuweisen, damit Ihre Benutzer auf Microsoft 365-Dienste wie e-Mail und Microsoft Teams zugreifen können.

Sie können Benutzerkonten entweder einzeln oder automatisch über die Gruppenmitgliedschaft Lizenzen zuweisen.

Wenn Sie Microsoft 365-Lizenzen einzelnen Benutzerkonten zuweisen möchten, können Sie Folgendes verwenden:

- [Das Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Das Azure AD Admin Center

## <a name="group-based-licensing"></a>Gruppenbasierte Lizenzierung

Sie können Sicherheitsgruppen in Azure AD so konfigurieren, dass Lizenzen automatisch aus einer Gruppe von Abonnements für alle Mitglieder der Gruppe zugewiesen werden. Dies wird als *gruppenbasierte Lizenzierung* bezeichnet. Wenn ein Benutzerkonto der Gruppe hinzugefügt oder aus ihr entfernt wird, werden die Lizenzen für die Gruppenabonnements dem Benutzerkonto automatisch zugewiesen, bzw. die Zuweisung wird entfernt.

Stellen Sie sicher, dass Sie genug Lizenzen für alle Gruppenmitglieder haben. Wenn keine Lizenzen mehr vorhanden sind, werden neuen Benutzern keine Lizenzen zugewiesen, bis Lizenzen verfügbar werden.

>[!Note]
>Sie sollten  nicht die gruppenbasierte Lizenzierung für Gruppen konfigurieren, die Azure Business to Business (B2B)-Konten enthalten.
>

Weitere Informationen finden Sie unter [Gruppenbasierte Lizenzierung in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

## <a name="next-steps"></a>Nächste Schritte

Mit den entsprechenden Benutzerkonten, denen Lizenzen zugewiesen wurden, können Sie nun folgende Aufgaben durchsetzen:

- [Implementieren der Sicherheit](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [Bereitstellen von Client Software wie Microsoft 365-apps](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [Einrichten der Geräteverwaltung](device-management-roadmap-microsoft-365.md)
- [Konfigurieren von Diensten und Anwendungen](configure-services-and-applications.md)
