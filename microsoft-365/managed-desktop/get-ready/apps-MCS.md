---
title: Arbeiten mit Microsoft Consulting Services
description: Vorbereitung und schritte für die Arbeit mit MCS zum Packen Ihrer Apps
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1441ca3305a5f3e5a83ddd5e1547812f08d7d96b
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445696"
---
# <a name="working-with-microsoft-consulting-services"></a>Arbeiten mit Microsoft Consulting Services

Sie können sich mit Microsoft Consulting Services (MCS) in Verbindung setzen, um Ihre Apps für die Verwendung mit Microsoft Managed Desktop. Um genaue Details zu erhalten, arbeiten Sie mit Ihrem Kontomitarbeiter zusammen, um MCS zu kontaktieren und Ihr spezifisches App-Packprojekt zu berücksichtigen.

## <a name="roles-and-responsibilities"></a>Rollen und Zuständigkeiten

Um mit mcS-App-Paketen zu arbeiten, **müssen Sie die folgenden Elemente bereitstellen:**

- Die Quellinstallationsdateien (z. B. setup.exe oder .msi).
- Die Installationsanweisungen, in der Details zum Aussehen der endgültigen Installation angegeben werden. Soll es beispielsweise eine Desktopverknüpfung zur App geben? Wie sollte die Sichtbarkeit der App sein? Sollte die App eine Verbindung mit einem Server herstellen, und falls ja, welcher? Weitere Informationen finden Sie in der [Anwendungs packanforderungsvorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).
- Sie müssen eigene Akzeptanztests durchführen, um sicherzustellen, dass die App so funktioniert, wie sie in Ihrer Umgebung benötigt wird.

**MCS kümmert sich um die folgenden Aktionen:**

- Überprüfen, ob die App in der Umgebung Microsoft Managed Desktop ist.
- Testen der Installation, des Startens und der Deinstallation der App, um die Kompatibilität mit Windows 10. Wenn MCS ein Kompatibilitätsproblem entdeckt, wird die App zur Behebung an das [App Assure-Programm](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure) weitergebe.
- Packen Sie die App nach Ihrer Spezifikation, und testen Sie dann die App-Bereitstellung mithilfe Microsoft Intune.

## <a name="app-delivery-schedule"></a>Zeitplan für die App-Zustellung

Starten Sie den Packvorgang, indem Sie die App-Informationen in das Microsoft Managed Desktop hochladen. Das Packteam überprüft jeden Donnerstag neue Übermittlungen. Nach überprüfung und Verpackung werden die verpackten Apps am folgenden Freitag zugestellt. Bis zu fünf Apps pro Woche können zum Starten verpackt werden, aber der Dienst kann nach Ihren Anforderungen skaliert werden.

![Kalender mit dem App-Zufluss an einem Donnerstag (dem 21. in diesem Beispiel), der Medienüberprüfung am nächsten Tag, dem Verpacken am folgenden Montag (dem 25.) und der App-Zustellung am folgenden Freitag (dem 29.)](../../media/MCS-cal.png)

Sie werden benachrichtigt, sobald die App zugestellt wurde. An diesem Punkt haben Sie 21 Tage Zeit, um Akzeptanztests durchzuführen und die Arbeit im Microsoft Managed Desktop genehmigen. Wenn Sie während der Annahmetests probleme mit der App feststellen, lehnen Sie die App im Microsoft Managed Desktop-Portal ab, und Sie werden per E-Mail mit einem MCS-Paketer verbunden, um das Problem zu verstehen und zu beheben.

## <a name="testing-accounts-and-environment"></a>Testen von Konten und Umgebung

Damit das Packteam die Migration zu Microsoft Intune, wird empfohlen, bestimmte Berechtigungen zur Verfügung zu stellen:
 
-   Zugriff auf Microsoft Intune App-Bereitstellungsfunktionen für den Paketer zum Hinzufügen und Zuweisen der App 
-   Testen von Gruppen, Benutzerkonten und Lizenzen für die Paketierer, um die Apps testen zu können

MCS verwendet diese Berechtigungen, um die folgenden Aktionen durchzuführen:
 
-   Sicherstellen, dass die App auf einem virtuellen Computer funktioniert, der für die Microsoft Managed Desktop
-   Hochladen der App in Microsoft Intune Bereitstellung für Ihre Benutzer

Ohne diese Berechtigungen kann MCS vorwärts gehen, die Anwendungen können jedoch nicht in Ihre Umgebung hochgeladen werden.
