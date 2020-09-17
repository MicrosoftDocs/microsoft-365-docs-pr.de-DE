---
title: Microsoft Teams
description: Wie Teams auf Geräten installiert und anschließend aktualisiert werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, apps, Branchenanwendungen, Lob-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950939"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) ist eine [Messaging-App](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) für Ihre Organisation, die auch einen Arbeitsbereich für die Zusammenarbeit und Kommunikation in Echtzeit, Besprechungen sowie die Datei-und App-Freigabe bereitstellt.

## <a name="initial-deployment"></a>Erstbereitstellung

Die meisten Hardwareanbieter enthalten noch keine Teams als Bestandteil ihrer Images, sodass Microsoft Managed Desktop Teams auf Ihren Geräten mithilfe von Microsoft InTune bereitstellt. Auf allen verwalteten Geräten ist das [Paket "Teams. msi](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) " installiert, um sicherzustellen, dass alle Benutzer, die sich bei einem Gerät anmelden, Microsoft Teams für die Verwendung bereit haben. Wenn das Paket zuerst die Installation abgeschlossen hat, werden die Teams automatisch gestartet und eine Verknüpfung zum Desktop hinzugefügt.

### <a name="microsoft-intune-changes"></a>Änderungen an Microsoft InTune

Microsoft Managed Desktop fügt Ihrer Azure AD Organisation für Microsoft Teams zwei Anwendungen hinzu. Sie werden entweder auf 64-Bit-oder 32-Bit-Clients bereitgestellt, je nach Bedarf des Geräts:  

- Moderner Arbeitsplatz – Teams Machine Wide Installer x64  
- Moderner Arbeitsplatz – Teams Machine Wide Installer x32

## <a name="updates"></a>Updates

Teams folgt einem separaten Aktualisierungspfad von Microsoft 365 apps for Enterprise, und der Desktop Client aktualisiert sich automatisch. Microsoft Teams überprüft alle paar Stunden nach Updates, lädt Sie herunter und wartet dann darauf, dass der Computer im Leerlauf ist, bevor das Update automatisch installiert wird.  

Die Teams-Produktgruppe erlaubt Administratoren nicht, Updates zu steuern, sodass der [standardmäßige automatische Update Kanal](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)von Microsoft Managed Desktop verwendet wird.

### <a name="manually-updating-teams"></a>Manuelles Aktualisieren von Teams

Einzelne Benutzer können Updates auch herunterladen, indem **Sie**im   Dropdownmenü **Profil**auf der   rechten oberen Ecke der APP nach Updates suchen auswählen. Wenn ein Update verfügbar ist, wird es heruntergeladen und automatisch installiert, wenn sich der Computer im Leerlauf befindet.

## <a name="delivery-optimization-of-updates"></a>Zustellungsoptimierung von Updates

Die Zustellungsoptimierung für Microsoft Teams-Updates ist standardmäßig aktiviert und erfordert keine Aktion von Administratoren oder Benutzern. 