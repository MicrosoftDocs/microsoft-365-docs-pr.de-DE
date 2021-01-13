---
title: Arbeiten mit Microsoft Consulting Services
description: Vorbereitung und die folgenden Schritte für die Arbeit mit MCS zum Packen Ihrer Apps
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, Apps, MCS, Verpacken
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841423"
---
# <a name="working-with-microsoft-consulting-services"></a>Arbeiten mit Microsoft Consulting Services

Sie können sich mit Microsoft Consulting Services (MCS) in Verbindung setzen, um Ihre Apps für die Verwendung mit Microsoft Managed Desktop zu packen. Wenden Sie sich an Ihren Kontomitarbeiter, um mcS zu kontaktieren und den Umfang Ihres spezifischen App-Paketprojekts zu berücksichtigen.

## <a name="roles-and-responsibilities"></a>Rollen und Zuständigkeiten

Um mit MCS-App-Paketen arbeiten zu **können, müssen Sie die folgenden Elemente bereitstellen:**

- Die Quellinstallationsdateien (z. B. setup.exe oder MSI).
- Die Installationsanweisungen, in der Details zum Aussehen der endgültigen Installation angegeben werden. Sollte es beispielsweise eine Desktopverknüpfung für die App geben? Wie sollte die Sichtbarkeit der App sein? Sollte die App eine Verbindung mit einem Server herstellen, und wenn ja, welcher? Weitere Informationen finden Sie in der [Anforderungsvorlage zum Packen von Anwendungen.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)
- Sie müssen eigene Akzeptanztests durchführen, um zu überprüfen, ob die App so funktioniert, wie sie in Ihrer Umgebung benötigt wird.

**MCS kümmert sich um die folgenden Aktionen:**

- Überprüfen, ob die App in der Microsoft Managed Desktop-Umgebung verboten oder eingeschränkt ist.
- Testen der Installation, des Startes und der Deinstallation der App, um die Kompatibilität mit Windows 10 sicherzustellen. Wenn MCS ein Kompatibilitätsproblem entdeckt, wird die App zur Problembehebung an das [Desktop App Assure-Programm](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) übergabet.
- Packen der App nach Ihrer Spezifikation und anschließendes Testen der App-Bereitstellung mithilfe von Microsoft Intune.

## <a name="app-delivery-schedule"></a>Zeitplan für die App-Übermittlung

Starten Sie den Verpackungsprozess, indem Sie die App-Informationen in das Microsoft Managed Desktop-Portal hochladen. Das Verpackungsteam überprüft jeden Donnerstag neue Übermittlungen. Nach überprüfung und Verpackung werden die verpackten Apps am folgenden Freitag zugestellt. Bis zu fünf Apps pro Woche können gepackt werden, um zu starten, aber der Dienst kann an Ihre Anforderungen angepasst werden.

![kalender showing app inflow on a Thursday (the 21st in this example), media validation the next day, packaging on the following Monday (the 25th), and app delivery on the subsequent Friday (the 29th)](../../media/MCS-cal.png)

Sie werden benachrichtigt, nachdem die App zugestellt wurde. An diesem Punkt haben Sie 21 Tage Zeit, um Akzeptanztests durchzuführen und die Arbeit im Microsoft Managed Desktop Portal zu genehmigen. Wenn Sie während der Akzeptanztests probleme mit der App feststellen, lehnen Sie die App im Microsoft Managed Desktop-Portal ab, und Sie werden per E-Mail mit einem MCS-Packager verbunden, um das Problem zu verstehen und zu beheben.

## <a name="testing-accounts-and-environment"></a>Testen von Konten und Umgebungen

Damit das Paketteam die Migration zu Microsoft Intune abschließen kann, sollten Sie bestimmte Berechtigungen bereitstellen:
 
-   Zugriff auf die App-Bereitstellungsfunktionen von Microsoft Intune, damit der Packager die App hinzufügen und zuweisen kann 
-   Testgruppen, Benutzerkonten und Lizenzen für die Paketer, um die Apps testen zu können

MCS verwendet diese Berechtigungen, um die folgenden Aktionen durchzuführen:
 
-   Sicherstellen, dass die App auf einem virtuellen Computer funktioniert, der für Microsoft Managed Desktop konfiguriert ist
-   Hochladen der App in Microsoft Intune für die Bereitstellung für Ihre Benutzer

Ohne diese Berechtigungen kann MCS vorankommen, die Anwendungen können jedoch nicht in Ihre Umgebung hochgeladen werden.


