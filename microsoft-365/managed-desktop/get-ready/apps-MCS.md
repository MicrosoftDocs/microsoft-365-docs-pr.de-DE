---
title: Arbeiten mit Microsoft Consulting Services
description: Vorbereitung und Schritte zur Zusammenarbeit mit MCS zum Verpacken Ihrer Apps
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, apps, MCS, Packaging
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4491504616eb4bb447f12d08dddb12c73c2a88ac
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962622"
---
# <a name="working-with-microsoft-consulting-services"></a>Arbeiten mit Microsoft Consulting Services

Sie können sich mit Microsoft Consulting Services (MCS) beschäftigen, um Ihre apps für die Verwendung mit Microsoft Managed Desktop zu verpacken. Um genaue Details zu erhalten, wenden Sie sich an Ihren Konto Vertreter, um Kontakt mit MCS aufzunehmen und Ihr spezielles App-Paket Projekt zu besprechen.

## <a name="roles-and-responsibilities"></a>Rollen und Verantwortlichkeiten

Um mit MCS App Packaging arbeiten zu können, **müssen Sie diese Elemente bereitstellen**:

- Die Quellinstallationsdateien (beispielsweise Setup. exe oder. msi).
- Die Installationsanweisungen, in denen Details zum Aussehen der endgültigen Installation angegeben werden. Soll beispielsweise eine Desktopverknüpfung mit der app vorhanden sein? Was sollte die APP-Sichtbarkeit sein? Sollte sich die APP mit einem Server verbinden und wenn ja, welche? Ausführliche Informationen finden Sie in der [Vorlage "Application Packaging Request](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)".
- Sie müssen ihre eigenen Akzeptanztests durchführen, um sicherzustellen, dass die APP so funktioniert, wie Sie Sie in Ihrer Umgebung benötigen.

**Diese Aktionen werden von MCS übernommen:**

- Überprüfen, ob die app in der Microsoft Managed Desktop-Umgebung verboten oder eingeschränkt ist.
- Testen der Installation, des Starts und der Deinstallation der APP, um die Kompatibilität mit Windows 10 sicherzustellen. Wenn MCS ein Kompatibilitätsproblem feststellt, wird die APP an das Programm für die Desktop-App zur Verfügung gestellt, um die Korrektur zu [gewährleisten](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) .
- Verpacken der app in ihrer Spezifikation und Testen der APP-Bereitstellung mithilfe von Microsoft InTune.

## <a name="app-delivery-schedule"></a>Zeitplan für die APP-Zustellung

Starten Sie den Verpackungsprozess, indem Sie die APP-Informationen in das Microsoft Managed Desktop Portal hochladen. Das Packaging-Team prüft jeden Donnerstag neue Übermittlungen. Nach Überprüfung und Verpackung werden die gepackten apps am nächsten Freitag ausgeliefert. Es können bis zu fünf apps pro Woche gepackt werden, aber der Dienst kann entsprechend Ihren Anforderungen skaliert werden.

![Kalender mit App-Zufluss an einem Donnerstag (dem 21. in diesem Beispiel), Medienüberprüfung am nächsten Tag, Verpacken am folgenden Montag (25.) und App-Zustellung am darauffolgenden Freitag (29.)](images/MCS-cal.png)

Sobald die APP zugestellt wurde, werden Sie benachrichtigt. An diesem Ort haben Sie 21 Tage Zeit, um Akzeptanztests durchzuführen und sich bei der Arbeit im Microsoft Managed Desktop Portal abzumelden. Wenn Sie während der Akzeptanztests ein Problem mit der APP entdecken, lehnen Sie die APP im Microsoft Managed Desktop Portal ab, und Sie werden über e-Mail mit einem MCS-paketor verbunden, um das Problem zu verstehen und zu beheben.

## <a name="testing-accounts-and-environment"></a>Testen von Konten und Umgebung

Damit das Packaging-Team die Migration zu Microsoft InTune abgeschlossen hat, wird empfohlen, bestimmte Berechtigungen bereitzustellen:
 
-   Zugriff auf die APP-Bereitstellungsfunktionen von Microsoft InTune für den Paket Besitzer zum Hinzufügen und Zuweisen der APP 
-   Testgruppen, Benutzerkonten und Lizenzen für die Packager, um die Apps testen zu können

MCS verwendet diese Berechtigungen, um die folgenden Aktionen auszuführen:
 
-   Sicherstellen, dass die APP auf dem für Microsoft Managed Desktop konfigurierten virtuellen Computer funktioniert
-   Hochladen der APP an Microsoft InTune für die Bereitstellung für Ihre Benutzer

Ohne diese Berechtigungen ist es für MCS möglich, sich vorwärts zu bewegen, aber die Anwendungen können nicht in Ihre Umgebung hochgeladen werden.


