---
title: Microsoft Teams
description: So wird Teams auf Geräten installiert und anschließend aktualisiert
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, Apps, Branchen-Apps, Branchen-Apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920656"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) ist eine [Messaging-App](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) für Ihre Organisation, die auch einen Arbeitsbereich für Zusammenarbeit und Kommunikation in Echtzeit, Besprechungen sowie Datei- und App-Freigabe bietet.

## <a name="initial-deployment"></a>Erstbereitstellung

Die meisten Hardwareanbieter enthalten teams noch nicht als Teil ihrer Bilder, daher stellt Microsoft Managed Desktop Teams mithilfe von Microsoft Intune auf Ihren Geräten zur Verfügung. Auf allen verwalteten Geräten ist [das Teams .msi installiert,](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) um sicherzustellen, dass alle Benutzer, die sich bei einem Gerät anmelden, Microsoft Teams einsatzbereit sind. Wenn das Paket zum ersten Mal installiert ist, wird Teams automatisch gestartet und dem Desktop eine Verknüpfung hinzugefügt.

### <a name="microsoft-intune-changes"></a>Änderungen an Microsoft Intune

Microsoft Managed Desktop fügt Ihrer Azure AD-Organisation für Microsoft Teams zwei Anwendungen hinzu. Sie werden auf 64-Bit- oder 32-Bit-Clients bereitgestellt, wie für das Gerät geeignet:  

- Moderner Arbeitsplatz – Teams Machine Wide Installer x64  
- Moderner Arbeitsplatz – Teams Machine Wide Installer x32

## <a name="updates"></a>Updates

Teams folgt einem separaten Updatepfad von Microsoft 365 Apps for Enterprise, und der Desktopclient aktualisiert sich automatisch selbst. Teams sucht alle paar Stunden nach Updates, lädt sie herunter und wartet dann, bis sich der Computer im Leerlauf befindet, bevor das Update automatisch installiert wird.  

Die Microsoft Teams-Produktgruppe lässt Administratoren die Kontrolle über Updates nicht zu, sodass Microsoft Managed Desktop den standardmäßigen automatischen [Updatekanal verwendet.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)

### <a name="manually-updating-teams"></a>Manuelles Aktualisieren von Teams

Einzelne Benutzer können updates auch herunterladen, indem Sie im Dropdownmenü Profil oben rechts in der App auf Updates   überprüfen ****   klicken. Wenn ein Update verfügbar ist, wird es heruntergeladen und automatisch installiert, wenn sich der Computer im Leerlauf befindet.

## <a name="delivery-optimization-of-updates"></a>Übermittlungsoptimierung von Updates

Die Übermittlungsoptimierung für Teams-Updates ist standardmäßig aktiviert und erfordert keine Aktion von Administratoren oder Benutzern.