---
title: Bedingten Zugriff anpassen
description: Ausschließen bestimmter Microsoft-Konten
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8844c50f5faba609b3f5f53adc5ab45ba1dbaa74
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529683"
---
# <a name="adjust-conditional-access"></a>Bedingten Zugriff anpassen

Wenn Sie Richtlinien für [bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) in Ihrer Organisation verwenden, müssen Sie diese so festlegen, dass bestimmte Konten ausgeschlossen werden, damit Microsoft Managed Desktop ordnungsgemäß ausgeführt werden kann.

Gehen Sie dazu wie folgt vor:

1. Weitere Informationen finden Sie im Abschnitt "Rollback Steps" unter [Vorgehensweise: Planen der Bereitstellung des bedingten Zugriffs in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).
2. Führen Sie die folgenden Schritte aus, um die Gruppe der *modernen Arbeitsplatz-Dienstkonten* für alle Richtlinien auszuschließen.


Wenn Sie Probleme mit dem bedingten Zugriff haben, wenden Sie sich an den Administrator [Support](../working-with-managed-desktop/admin-support.md).

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Schritte zum Einstieg in Microsoft Managed Desktop

1. [Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal](add-admin-contacts.md)
2. Anpassen des bedingten Zugriffs (dieses Thema)
3. [Zuweisen von Lizenzen](assign-licenses.md)
4. [Intune-Unternehmensportal bereitstellen](company-portal.md)
5. [Aktivieren von Enterprise State Roaming](enterprise-state-roaming.md)
6. [Einrichten von Geräten](set-up-devices.md)
7. [Vorbereiten Ihrer Benutzer für die Verwendung von Geräten](get-started-devices.md)
8. [Bereitstellen von Apps](deploy-apps.md)
