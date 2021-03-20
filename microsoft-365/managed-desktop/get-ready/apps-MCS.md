---
title: Arbeiten mit Microsoft Consulting Services
description: Vorbereitung und schritte für die Arbeit mit MCS zum Packen Ihrer Apps
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, Apps, MCS, Packen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 04b0c7905c83be2afa46abcfb2d4bb5cd9735e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909226"
---
# <a name="working-with-microsoft-consulting-services"></a>Arbeiten mit Microsoft Consulting Services

Sie können sich mit Microsoft Consulting Services (MCS) in Verbindung setzen, um Ihre Apps für die Verwendung mit Microsoft Managed Desktop zu packen. Um genaue Details zu erhalten, arbeiten Sie mit Ihrem Kontomitarbeiter zusammen, um MCS zu kontaktieren und Ihr spezifisches App-Packprojekt zu berücksichtigen.

## <a name="roles-and-responsibilities"></a>Rollen und Zuständigkeiten

Um mit mcS-App-Paketen zu arbeiten, **müssen Sie die folgenden Elemente bereitstellen:**

- Die Quellinstallationsdateien (z. B. setup.exe oder MSI).
- Die Installationsanweisungen, in der Details zum Aussehen der endgültigen Installation angegeben werden. Soll es beispielsweise eine Desktopverknüpfung zur App geben? Wie sollte die Sichtbarkeit der App sein? Sollte die App eine Verbindung mit einem Server herstellen, und falls ja, welcher? Weitere Informationen finden Sie in der [Anwendungs packanforderungsvorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).
- Sie müssen eigene Akzeptanztests durchführen, um sicherzustellen, dass die App so funktioniert, wie sie in Ihrer Umgebung benötigt wird.

**MCS kümmert sich um die folgenden Aktionen:**

- Überprüfen, ob die App in der Microsoft Managed Desktop-Umgebung verboten oder eingeschränkt ist.
- Testen der Installation, des Startens und der Deinstallation der App, um die Kompatibilität mit Windows 10 sicherzustellen. Wenn MCS ein Kompatibilitätsproblem entdeckt, wird die App zur Behebung an das [Desktop App Assure-Programm](/fasttrack/win-10-desktop-app-assure) weitergebe.
- Packen Sie die App nach Ihrer Spezifikation, und testen Sie dann die App-Bereitstellung mithilfe von Microsoft Intune.

## <a name="app-delivery-schedule"></a>Zeitplan für die App-Zustellung

Starten Sie den Packvorgang, indem Sie die App-Informationen in das Microsoft Managed Desktop-Portal hochladen. Das Packteam überprüft jeden Donnerstag neue Übermittlungen. Nach überprüfung und Verpackung werden die verpackten Apps am folgenden Freitag zugestellt. Bis zu fünf Apps pro Woche können zum Starten verpackt werden, aber der Dienst kann nach Ihren Anforderungen skaliert werden.

![Kalender mit dem App-Zufluss an einem Donnerstag (dem 21. in diesem Beispiel), der Medienüberprüfung am nächsten Tag, dem Verpacken am folgenden Montag (dem 25.) und der App-Zustellung am folgenden Freitag (dem 29.)](../../media/MCS-cal.png)

Sie werden benachrichtigt, sobald die App zugestellt wurde. An diesem Punkt haben Sie 21 Tage Zeit, Um Akzeptanztests durchzuführen und die Arbeit im Microsoft Managed Desktop-Portal zu genehmigen. Wenn Sie während der Annahmetests probleme mit der App feststellen, lehnen Sie die App im Microsoft Managed Desktop-Portal ab, und Sie werden per E-Mail mit einem MCS-Paketer verbunden, um das Problem zu verstehen und zu beheben.

## <a name="testing-accounts-and-environment"></a>Testen von Konten und Umgebung

Damit das Paketteam die Migration zu Microsoft Intune abschließen kann, wird empfohlen, bestimmte Berechtigungen bereitzustellen:
 
-   Zugriff auf die App-Bereitstellungsfunktionen von Microsoft Intune, damit der Paketer die App hinzufügen und zuweisen kann 
-   Testen von Gruppen, Benutzerkonten und Lizenzen für die Paketierer, um die Apps testen zu können

MCS verwendet diese Berechtigungen, um die folgenden Aktionen durchzuführen:
 
-   Sicherstellen, dass die App auf einem virtuellen Computer funktioniert, der für Microsoft Managed Desktop konfiguriert ist
-   Hochladen der App in Microsoft Intune für die Bereitstellung für Ihre Benutzer

Ohne diese Berechtigungen kann MCS vorwärts gehen, die Anwendungen können jedoch nicht in Ihre Umgebung hochgeladen werden.