---
title: Microsoft 365 SharePoint Online Datenlöschung
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Erfahren Sie, wie das Löschen von Daten in SharePoint Online funktioniert, beispielsweise wo gelöschte Inhalte gespeichert werden und wie lange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e914e84f3679483e5030b7f2a06913cb052e5411
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332724"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a>SharePoint Online Löschen von Daten in Microsoft 365

SharePoint Online speichert Objekte als abstrahierten Code in Anwendungsdatenbanken. Wenn ein Benutzer eine Datei in SharePoint Online hochlädt, wird diese Datei zerlegt und in Anwendungscode übersetzt und in mehreren Tabellen in mehreren Datenbanken gespeichert. In SharePoint Online werden alle Inhalte, die ein Kunde hoch lädt, in Segmente unterteilt, verschlüsselt (potenziell mit mehreren AES 256-Bit-Schlüsseln) und über das Rechenzentrum verteilt. Spezifische Details zum Segmentierungs-und Verschlüsselungsprozess finden Sie unter [Encryption in the Microsoft Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview). 

In SharePoint Online werden Elemente für 93 Tage ab dem Zeitpunkt aufbewahrt, zu dem Sie Sie aus Ihrem ursprünglichen Speicherort löschen. Sie bleiben die gesamte Zeit im Papierkorb der Website, es sei denn, jemand löscht sie von dort oder entleert diesen Papierkorb. In diesem Fall wechseln die Elemente in den Papierkorb der Websitesammlung, wo Sie für die restlichen 93 Tage bleiben. Informationen zum Wiederherstellen gelöschter Elemente finden Sie unter [Wiederherstellen von Elementen im Papierkorb einer SharePoint-Website](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) und [Wiederherstellen gelöschter Elemente aus dem Papierkorb der Websitesammlung](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). Die Aufbewahrungszeit für den Papierkorb kann nicht in SharePoint Online konfiguriert werden.

Wenn Sie eine Websitesammlung löschen, löschen Sie auch die Hierarchie der Websites in der Auflistung und alle darin enthaltenen Inhalte:

- Dokumente und Dokumentbibliotheken
- Listen und Listendaten
- Website Konfigurationseinstellungen
- Rollen-und Sicherheitsinformationen im Zusammenhang mit der Website oder ihren Unterwebsites
- Unterwebsites der Website auf oberster Ebene, deren Inhalte und Benutzerinformationen

Wenn Sie versehentlich eine Websitesammlung löschen, kann Sie von einem globalen oder SharePoint-Administrator mithilfe des SharePoint admin Centers wiederhergestellt werden.

Gelöschte Websitesammlungen werden für 93 Tage aufbewahrt. Nach 93 Tagen werden Websites sowie alle Inhalte und Einstellungen, einschließlich Listen, Bibliotheken, Seiten und Unterwebsites, dauerhaft gelöscht.

Das Löschen von Festplatten erfolgt, wenn ein Benutzer gelöschte Elemente aus dem Papierkorb der Websitesammlung löscht, wenn die Aufbewahrungs-und Sicherungs Zeiträume ablaufen oder wenn ein Administrator eine Websitesammlung mit dem [Cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)dauerhaft löscht. Wenn ein Benutzer Inhalt aus SharePoint Online löscht (dauerhaft löscht oder löscht), werden auch alle Verschlüsselungsschlüssel für die gelöschten Chunks gelöscht. Die Blöcke auf den Datenträgern, die zuvor die gelöschten Segmente gespeichert haben, werden als nicht verwendet gekennzeichnet und können wieder verwendet werden.
