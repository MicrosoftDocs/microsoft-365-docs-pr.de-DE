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
description: Beschreibt das Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten, entweder einzeln oder basierend auf der Gruppenmitgliedschaft.
ms.openlocfilehash: 6bba3cd767787f450840c5cae6c30f2be21bed1b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905440"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Für das Nur-Cloud-Identitätsmodell können Sie Microsoft 365-Lizenzen Benutzerkonten bei der Erstellung zuweisen, je nachdem, wie Sie sie erstellen.

Wenn für das Hybrididentitätsmodell Benutzerkonten der Active Directory Domain Services (AD DS) zum ersten Mal synchronisiert werden, wird ihnen nicht automatisch ein Speicherort oder eine Microsoft 365-Lizenz zugewiesen. **Sie müssen jedes Benutzerkonto mit einem Benutzerspeicherort vor oder zusammen mit dem Zuweisen einer Lizenz konfigurieren.**

In beiden Fällen müssen Sie Benutzerkonten eine Lizenz zuweisen, damit Ihre Benutzer auf Microsoft 365-Dienste wie E-Mails und Microsoft Teams zugreifen können.

Sie können Benutzerkonten Lizenzen entweder einzeln oder automatisch über die Gruppenmitgliedschaft zuweisen.

Zum Zuweisen von Microsoft 365-Lizenzen zu einzelnen Benutzerkonten können Sie verwenden:

- [Das Microsoft 365 Admin Center](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Azure AD Admin Center

## <a name="group-based-licensing"></a>Gruppenbasierte Lizenzierung

Sie können Sicherheitsgruppen in Azure AD konfigurieren, um allen Mitgliedern der Gruppe automatisch Lizenzen aus einer Reihe von Abonnements zuzuordnen. Dies wird als *gruppenbasierte Lizenzierung* bezeichnet. Wenn ein Benutzerkonto der Gruppe hinzugefügt oder aus ihr entfernt wird, werden die Lizenzen für die Gruppenabonnements dem Benutzerkonto automatisch zugewiesen, bzw. die Zuweisung wird entfernt.

Stellen Sie sicher, dass Sie genug Lizenzen für alle Gruppenmitglieder haben. Wenn keine Lizenzen mehr vorhanden sind, werden neuen Benutzern keine Lizenzen zugewiesen, bis Lizenzen verfügbar werden.

>[!Note]
>Sie sollten  nicht die gruppenbasierte Lizenzierung für Gruppen konfigurieren, die Azure Business to Business (B2B)-Konten enthalten.
>

Weitere Informationen finden Sie unter [gruppenbasierte](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)Lizenzierung in Azure AD .

## <a name="next-steps"></a>Nächste Schritte

Mit dem entsprechenden Satz von Benutzerkonten, denen Lizenzen zugewiesen wurden, sind Sie jetzt bereit für:

- [Implementieren der Sicherheit](../security/office-365-security/security-roadmap.md)
- [Bereitstellen von Clientsoftware, z. B. Microsoft 365 Apps](/DeployOffice/deployment-guide-microsoft-365-apps)
- [Einrichten der Geräteverwaltung](device-management-roadmap-microsoft-365.md)
- [Konfigurieren von Diensten und Anwendungen](configure-services-and-applications.md)