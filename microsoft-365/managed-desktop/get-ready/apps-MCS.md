---
title: Arbeiten mit Microsoft Consulting Services
description: Vorbereitung und Schritte zur Zusammenarbeit mit MCS zum Verpacken Ihrer Apps
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
ms.openlocfilehash: 7a967f5e4b2678b55ed87f2eaa68590703c55805
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840886"
---
# <a name="working-with-microsoft-consulting-services"></a>Arbeiten mit Microsoft Consulting Services

Sie können mit Microsoft Consulting Services (MCS) zusammenarbeiten, um Ihre Apps für die Verwendung mit Microsoft Managed Desktop zu verpacken. Wenden Sie sich an MCS, um genaue Details zu erhalten, und wenden Sie sich an Ihren Kontomitarbeiter, um Ihr spezifisches App-Paketprojekt zu beschränken.

## <a name="roles-and-responsibilities"></a>Rollen und Zuständigkeiten

Zum Arbeiten mit MCS-App-Paketen **müssen Sie die folgenden Elemente bereitstellen:**

- Die Quellinstallationsprogrammdateien (z. B. setup.exe oder .msi).
- In den Installationsanweisungen werden Details zum Aussehen der endgültigen Installation angegeben. Sollte es beispielsweise eine Desktopverknüpfung zur App geben? Wie sollte die Sichtbarkeit der App sein? Sollte die App eine Verbindung mit einem Server herstellen und wenn ja, welcher? Ausführliche Informationen finden Sie in der [Anforderungsvorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)zum Packen von Anwendungen.
- Sie müssen Ihre eigenen Akzeptanztests durchführen, um zu überprüfen, ob die App in Ihrer Umgebung wie erforderlich funktioniert.

**MCS übernimmt die folgenden Aktionen:**

- Überprüfen, ob die App in der Microsoft Managed Desktop-Umgebung verboten oder eingeschränkt ist.
- Testen der Installation, des Startes und der Deinstallation der App, um die Kompatibilität mit Windows 10 sicherzustellen. Wenn MCS ein Kompatibilitätsproblem feststellt, wird die App zur Behebung an das [App Assure-Programm](/fasttrack/products-and-capabilities#app-assure) übergeben.
- Packen Sie die App nach Ihren Spezifikationen, und testen Sie dann die App-Bereitstellung mithilfe von Microsoft Intune.

## <a name="app-delivery-schedule"></a>Zeitplan für die App-Übermittlung

Starten Sie den Verpackungsvorgang, indem Sie die App-Informationen in das Microsoft Managed Desktop-Portal hochladen. Das Verpackungsteam überprüft jeden Donnerstag neue Übermittlungen. Nach der Überprüfung und Verpackung werden die verpackten Apps am folgenden Freitag übermittelt. Bis zu fünf Apps pro Woche können für den Start gepackt werden, aber der Dienst kann entsprechend Ihren Anforderungen skaliert werden.

![Kalender mit App-Zufluss an einem Donnerstag (21. in diesem Beispiel), Medienüberprüfung am nächsten Tag, Verpacken am folgenden Montag (25.) und App-Zustellung am nachfolgenden Freitag (29.)](../../media/MCS-cal.png)

Sie werden benachrichtigt, nachdem die App übermittelt wurde. An diesem Punkt haben Sie 21 Tage Zeit, um Akzeptanztests durchzuführen und die Arbeit im Microsoft Managed Desktop Portal zu genehmigen. Wenn Sie während der Annahmetests ein Problem mit der App feststellen, weisen Sie die App im Microsoft Managed Desktop-Portal zurück, und Sie werden per E-Mail mit einem MCS-Packager verbunden, um das Problem zu verstehen und zu beheben.

## <a name="testing-accounts-and-environment"></a>Testen von Konten und Umgebung

Damit das Verpackungsteam die Migration zu Microsoft Intune abschließen kann, empfehlen wir Ihnen, bestimmte Berechtigungen bereitzustellen:

- Zugriff auf die App-Bereitstellungsfunktionen Microsoft Intune für den Packager zum Hinzufügen und Zuweisen der App
- Testen von Gruppen, Benutzerkonten und Lizenzen für die Packager, um die Apps testen zu können

MCS verwendet diese Berechtigungen, um die folgenden Aktionen auszuführen:

- Sicherstellen, dass die App auf einem virtuellen Computer funktioniert, der für Microsoft Managed Desktop
- Hochladen der App in Microsoft Intune für die Bereitstellung für Ihre Benutzer

Ohne diese Berechtigungen ist es möglich, dass MCS vorwärts geht, aber sie können die Anwendungen nicht in Ihre Umgebung hochladen.
