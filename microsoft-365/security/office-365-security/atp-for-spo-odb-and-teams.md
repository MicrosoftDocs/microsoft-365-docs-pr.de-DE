---
title: ATP für SharePoint, OneDrive und Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Erfahren Sie mehr über Microsoft Defender für Office 365 für Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams.
ms.openlocfilehash: 7b007671a7fecb3ae074fd07ce38d17fb025f6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844332"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP für SharePoint, OneDrive und Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

ATP für SharePoint, OneDrive und Microsoft Teams in [Microsoft Defender für Office 365](office-365-atp.md) bietet eine zusätzliche Schutzschicht für Dateien, die bereits zum Zeitpunkt des Uploads durch das [Allgemeine Viruserkennungsmodul in Microsoft 365](virus-detection-in-spo.md)überprüft wurden. ATP für SharePoint, OneDrive und Microsoft Teams unterstützt das erkennen und blockieren vorhandener Dateien, die als bösartig identifiziert werden, in Teamwebsites und Dokumentbibliotheken.

ATP für SharePoint, OneDrive und Microsoft Teams ist standardmäßig nicht aktiviert. Weitere Informationen zum Aktivieren finden Sie unter [Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Funktionsweise von ATP für SharePoint, OneDrive und Microsoft Teams

Wenn ATP für SharePoint, OneDrive und Microsoft Teams aktiviert ist und eine Datei als bösartig identifiziert, wird die Datei mithilfe der direkten Integration mit den Datei speichern gesperrt. In der folgenden Abbildung ist ein Beispiel für eine in einer Bibliothek erkannte schädliche Datei dargestellt.

![Dateien in OneDrive für Unternehmen mit einem als bösartig erkannt](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Obwohl die blockierte Datei weiterhin in der Dokumentbibliothek und in den Webanwendungen, mobilen oder Desktopanwendungen aufgeführt ist, können die Benutzer die Datei nicht öffnen, kopieren, weiterleiten oder freigeben. Die blockierte Datei kann jedoch gelöscht werden.

Hier sehen Sie ein Beispiel dafür, wie eine blockierte Datei auf einem mobilen Gerät aussieht:

![Löschen einer gesperrten Datei aus OneDrive für Unternehmen aus dem OneDrive-Mobile App](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Standardmäßig können Benutzer eine blockierte Datei herunterladen. Hier sehen Sie, was das Herunterladen einer gesperrten Datei auf einem mobilen Gerät aussieht:

![Herunterladen einer gesperrten Datei in OneDrive für Unternehmen](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online Administratoren können verhindern, dass Benutzer schädliche Dateien herunterladen. Anweisungen finden Sie unter [use SharePoint Online PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

Weitere Informationen zur Benutzerfreundlichkeit, wenn eine Datei als bösartig erkannt wurde, finden Sie unter [Vorgehensweise, wenn eine schädliche Datei in SharePoint Online, OneDrive oder Microsoft Teams gefunden wird](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Anzeigen von Informationen zu bösartigen Dateien, die von ATP für SharePoint, OneDrive und Microsoft Teams erkannt wurden

Dateien, die von Microsoft Defender für Office 365 als bösartig identifiziert werden, werden in [Berichten für Microsoft Defender für Office 365](view-reports-for-atp.md) und in [Explorer (und Echtzeiterkennung)](threat-explorer.md)angezeigt.

Ab dem 2018. Mai wird die Datei auch in der Quarantäne zur Verfügung gestellt, wenn eine Datei von Microsoft Defender für Office 365 als bösartig gekennzeichnet wird. Weitere Informationen finden Sie unter [Verwenden des Security & Compliance Center zum Verwalten von isolierten Dateien](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="keep-these-points-in-mind"></a>Beachten Sie diese Punkte

- Defender für Office 365 überprüft nicht jede einzelne Datei in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams. Es handelt sich hierbei um ein beabsichtigtes Verhalten. Dateien werden asynchron gescannt. Der Prozess verwendet Freigabe-und Gast Aktivitätsereignisse zusammen mit intelligenten Heuristiken und Bedrohungs Signalen, um bösartige Dateien zu identifizieren.

- Stellen Sie sicher, dass Ihre SharePoint-Websites so konfiguriert sind, dass Sie die [moderne Benutzeroberfläche](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)verwenden. Defender für Office 365 Schutz gilt, ob die moderne Erfahrung oder die klassische Ansicht verwendet wird; visuelle Indikatoren, die eine Datei blockiert, sind jedoch nur in der modernen Benutzeroberfläche verfügbar.

- ATP für SharePoint, OneDrive und Microsoft Teams ist Teil der allgemeinen Bedrohungsschutz Strategie Ihrer Organisation, die den Schutz vor Spam und Antischadsoftware in Exchange Online Protection (EoP) sowie sichere Links und sichere Anlagen in Microsoft Defender für Office 365 enthält. Weitere Informationen finden Sie unter [Protect Against Threats in Office 365](protect-against-threats.md).
