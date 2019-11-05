---
title: Schützen von Dateien in Teams mit Vertraulichkeitsbezeichnungen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Zusammenfassung: Wenden Sie Vertraulichkeitsbezeichnungen zum Schutz von Dateien in einem streng vertraulichen Team an.'
ms.openlocfilehash: f52b864087d22e14bb3e9bfe1eb38d088f6f981a
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925793"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a><span data-ttu-id="07762-103">Schützen von Dateien in Teams mit Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="07762-103">Protect files in teams with sensitivity labels</span></span>


<span data-ttu-id="07762-104">Im Gegensatz zu einer Vertraulichkeitsbezeichnung für streng regulierte Daten, die von jedem auf eine beliebige Datei angewendet werden kann, benötigt ein streng vertrauliches Team eine eigene Bezeichnung oder Unterbezeichnung, damit für Dateien, denen diese Bezeichnung oder Unterbezeichnung zugeordnet ist, Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="07762-104">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="07762-105">Die Dateien werden einzeln verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="07762-105">Are individually encrypted.</span></span>
- <span data-ttu-id="07762-106">Die Dateien enthalten benutzerdefinierte Berechtigungen, sodass sie nur von Mitgliedern des Teams geöffnet werden können.</span><span class="sxs-lookup"><span data-stu-id="07762-106">Contain custom permissions so that only members of the Team Group can open it.</span></span>

<span data-ttu-id="07762-107">Um diese zusätzliche Sicherheitsstufe für die in der zugrunde liegenden SharePoint-Website gespeicherten Dateien zu erreichen, müssen Sie eine benutzerdefinierte Vertraulichkeitsbezeichnung konfigurieren, bei der es sich entweder um eine eigene Bezeichnung oder um eine Unterbezeichnung der allgemeinen Bezeichnung für stark regulierte Daten handelt.</span><span class="sxs-lookup"><span data-stu-id="07762-107">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="07762-108">Nur Teammitglieder können die benutzerdefinierte Bezeichnung oder Unterbezeichnung in der Liste der Bezeichnungen sehen.</span><span class="sxs-lookup"><span data-stu-id="07762-108">Only team members will see the customized label or sublabel in their list of labels.</span></span>

<span data-ttu-id="07762-109">Verwenden Sie eine Vertraulichkeitsbezeichnung, wenn Sie nur eine kleine Anzahl von Bezeichnungen für die globale Nutzung und für einzelne private Teams benötigen.</span><span class="sxs-lookup"><span data-stu-id="07762-109">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> 

<span data-ttu-id="07762-110">Verwenden Sie eine Vertraulichkeitsunterbezeichnung, wenn Sie über eine große Anzahl von Bezeichnungen verfügen oder Bezeichnungen für streng vertrauliche Teams unter der streng regulierten Bezeichnung organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="07762-110">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams under the highly regulated label.</span></span>

<span data-ttu-id="07762-111">Verwenden Sie [diese Anweisungen ](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) zum Konfigurieren einer separaten Bezeichnung oder einer Unterbezeichnung mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="07762-111">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="07762-112">Der Name der Bezeichnung oder Unterbezeichnung enthält den Namen des Teams.</span><span class="sxs-lookup"><span data-stu-id="07762-112">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="07762-113">Die Verschlüsselung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="07762-113">Encryption is enabled</span></span>
- <span data-ttu-id="07762-114">Die Office 365-Gruppe für das Team verfügt über Berechtigungen für die gemeinsame Dokumenterstellung.</span><span class="sxs-lookup"><span data-stu-id="07762-114">The Office 365 group for the team has Co-Author permissions</span></span>

<span data-ttu-id="07762-115">Veröffentlichen Sie nach dem Erstellen die neue Bezeichnung oder die neue Unterbezeichnung für Ihre Benutzer, die diese dann auf Dateien entweder lokal vor dem Hochladen in das Team oder später nach dem Speichern der Datei im Team anwenden können.</span><span class="sxs-lookup"><span data-stu-id="07762-115">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>

<span data-ttu-id="07762-116">Hier ist die Konfiguration des streng vertraulichen Teams, das Vertraulichkeitsbezeichnungen für Dateiverschlüsselung und-Berechtigungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="07762-116">Here is the configuration of the highly confidential team that uses sensitivity labels for file encryption and permissions.</span></span>

![Grundlegender Schutz für ein öffentliches Team.](../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a><span data-ttu-id="07762-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07762-118">See Also</span></span>

[<span data-ttu-id="07762-119">Sichern von Dateien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07762-119">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="07762-120">Cloudakzeptanz und Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="07762-120">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
