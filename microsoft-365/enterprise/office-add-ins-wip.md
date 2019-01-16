---
title: Schützen von Enterprise-Dokumenten mit Microsoft Office-Add-ins - Microsoft 365 Enterprise | Microsoft-Dokumente
description: Beschreibt, wie WIP und Intune verwenden, um Enterprise-Daten in Dokumenten mit Office-Add-ins zu schützen.
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/14/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 6871f288a7e5849b147cbf0aedb056f84575f376
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867853"
---
# <a name="use-wip-and-intune-to-protect-enterprise-data-in-documents-running-office-add-ins"></a>Verwenden von WIP und Intune zum Schutz von Unternehmensdaten in Dokumenten, in denen Office-Add-Ins ausgeführt werden
Wenn Benutzer in einer Organisation Office-Add-Ins zur Interaktion mit Unternehmensdaten verwenden, entsteht dadurch das Risiko von Datenlecks. Zum Schutz von Unternehmensdaten bei der Ausführung von Office-Add-Ins können Sie Windows Information Protection (WIP) und Microsoft Intune verwenden.

Mit [WIP](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip), zuvor unter der Bezeichnung Unternehmensdatenschutz (Enterprise Data Protection, EDP) bekannt, können Unternehmen geistiges Eigentum und Unternehmensdaten schützen. WIP schützt auch Unternehmens-Apps und -Daten vor versehentlichen Datenlecks auf unternehmenseigenen sowie auf persönlichen Geräten, die die Mitarbeiter zur Arbeit mitbringen – ohne dass die Umgebung oder andere Apps geändert werden müssen.

In [Intune](https://www.microsoft.com/cloud-platform/microsoft-intune) werden zahlreiche Tools zur Verwaltung Ihrer komplexen mobilen Umgebung bereitgestellt. Die Kombination aus Verwaltungsoptionen für mobile Anwendungen und für Geräte in Intune gibt IT-Administratoren und Benutzern die Möglichkeit, ihre mobile Produktivität flexibel zu verwalten und zu schützen.

Sie können Intune zum [Erstellen und Bereitstellen Ihrer WIP-Richtlinie](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/overview-create-wip-policy) verwenden. Mit Intune können Sie Ihre geschützten Apps und Ihre WIP-Schutzebene auswählen sowie Unternehmensdaten im Netzwerk suchen.

Vorteile von WIP und Intune:

-   Unternehmen können angemessene Richtlinien für Unternehmensdaten durchsetzen, selbst beim Herunterladen von Daten auf persönliche Geräte.

-   Unternehmen können Benutzer kontextbezogen über die Richtlinien informieren, um sich vor einer unbeabsichtigten Offenlegung von Daten für nicht verwaltete Apps und Dienste zu schützen.

-   Benutzer können Unternehmensdatenrichtlinien einhalten, ohne ihre gewohnten Arbeitsabläufe zu unterbrechen.

-   Benutzer können nahtlos zwischen beruflicher und privater Produktivität wechseln.

WIP und Intune werden automatisch im Hintergrund ausgeführt und sind praktisch unsichtbar, solange die Benutzer private und unternehmensbezogene Inhalte nicht vermischen.

[Office-Add-Ins](https://dev.office.com/docs/add-ins/overview/office-add-ins) basieren auf Webtechnologien. Sie nutzen die Leistung und Informationen des Internets für Office-Anwendungen. Add-Ins interagieren mit dem Inhalt einer Office-Anwendung über die APIs, die in „Office.js“ verfügbar sind. Die Kernaspekte von Office-Add-Ins sind folgende:

-   **Sicherheit**: Durch die Plattformarchitektur von Office JavaScript wird sichergestellt, dass der Add-In-Code in einen Sandkasten-Code umgewandelt und als separater Vorgang in Bezug auf die Office-Hostanwendung ausgeführt wird. Dadurch kann die Plattform Korrekturmaßnahmen durchführen, wenn ein Add-In die Leistungsstandards nicht erfüllt oder potenziell schädlich ist. In diesem Fall wird der Benutzer benachrichtigt oder, in seltenen Fällen, das Add-In deaktiviert. Diese Architektur funktioniert auf allen Plattformen, die Office-Add-Ins unterstützen.

-   **Resilienz**: Durch Ausführen der Add-In-Plattform außerhalb des Prozesses wird sichergestellt, dass das Add-In selbst die Leistung oder Benutzerfreundlichkeit der Office-Hostanwendung nicht beeinträchtigt. Dadurch bleibt Office schnell und reagiert weiterhin auf Benutzeraktionen.

-   **Plattformübergreifende Wirkung**: Einmal Geschriebenes kann überall mit Office ausgeführt werden. Add-Ins werden derzeit von Windows, Office Online, Mac und iPad unterstützt. In Kürze wird Add-In-Unterstützung auch auf Android- und Universal-Plattformen verfügbar sein.

Office-Add-Ins können in Dokumenten mit unternehmensbezogenen und potenziell vertraulichen Inhalten verwendet werden. Im Rahmen der Erweiterbarkeit von Anwendungen erben Add-Ins ihren Zugriff von der Hostanwendungsrichtlinie. Verhindern beispielsweise die WIP-Einstellungen, dass Word auf Unternehmensinhalte zugreifen kann, können die Add-Ins nicht auf den Unternehmensinhalt in einem Word-Dokument zugreifen.

Add-Ins sollen u.a. alle Blockierungsprobleme für Benutzer entfernen und gleichzeitig sicherstellen, dass die Administratoren des Unternehmens Add-Ins bei Bedarf blockieren können. Die Hauptprinzipien für Office-Add-Ins hinsichtlich des Datenschutzes beinhalten:

-   Das Bereitstellen einer Möglichkeit für IT-Administratoren, das Laden von Add-Ins zu blockieren

-   Das Minimieren oder Eliminieren des Aufwands für Administratoren, Add-Ins unternehmensfähig zu machen

-   Das Minimieren von Aufforderungen und Nachrichten an Benutzer während der Verwendung von Add-Ins

-   Das Vermeiden von Aufforderungen an Benutzer, wenn Dokument und Add-In denselben Kontext besitzen

## <a name="add-ins-and-wip"></a>Add-Ins und WIP

Wenn Sie WIP in Ihrer Umgebung aktivieren, können Sie die folgenden Szenarios für Ihre Office-Add-Ins aktivieren:

-   Office-Add-Ins werden mithilfe des Dokumentkontexts aktiviert. Bei Outlook basiert der Kontext für das Add-In auf dem aktuell aktiven Postfach. Add-In-Berechtigungen werden in der Vertrauensaufforderung klar definiert, bevor das Add-In aktiviert wird. Der Benutzer entscheidet, ob das Add-In für ein bestimmtes Dokument geeignet ist, und ob es ausgeführt werden darf.

-   Administratoren können Gruppenrichtlinien verwenden, um alle Office Store-Add-Ins oder alle Office-Add-Ins zu blockieren. Das bedeutet, dass Benutzer nur vertrauenswürdige Add-Ins aus einem [SharePoint- oder Office 365-Unternehmenskatalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) aktivieren können.

-   Administratoren können Add-Ins auf Firewall-Ebene mithilfe der mobilen Geräteverwaltung (Mobile Device Management, MDM) blockieren. Beachten Sie, dass dies nicht bei mobilen Szenarios oder BYOD-Szenarios (Bring Your Own Device) funktioniert.

-   Add-Ins wenden den Kopieren-und-Einfügen-Vorgang zwischen unternehmensbezogenen und privaten Kontexten an. Wenn ein Benutzer z.B. aus einem Unternehmenskontext-Add-In kopiert und in ein persönliches Dokument einfügt, wird die Standardaufforderung für unterschiedliche Kontexte angezeigt.

Die folgende Tabelle listet das erwartete Add-In-Verhalten in Unternehmens- und privaten Kontexten und Dokumenten auf, wenn WIP aktiviert ist.

> [!NOTE]
> - Ausschneide-, Kopier- und Einfügevorgänge innerhalb und außerhalb der Hostanwendung funktionieren in allen Szenarios wie erwartet.
> - Die Datenübertragung an Add-In-Dienste wird nicht in allen Szenarios geschützt.

|**Dokument- oder Postfachtyp**|**Add-In im privaten Kontext**|**Add-In im Unternehmenskontext**|
|:----------------|:-------------------------------------------------|:---------------------------------------------------|
|**Privat**     |Add-In wird im privaten Kontext geladen.<br><br>Navigation zu Unternehmens-URLs ist nicht zulässig (selbst in der eigenen Anwendungsdomäne).<br><br>Navigation zu privaten URLs ist zulässig.|Add-In kann nicht geladen oder aktiviert werden.<br><br>Bei erhöhtem Dokumentkontext (z.B. beim Speichern an einem Speicherort des Unternehmens) gilt:<br><br>– Navigation zu Unternehmens-URLs ist zulässig.<br><br>– Navigation zu privaten URLs ist zulässig.|
|**Unternehmen**   |Add-In wird im Unternehmenskontext geladen.<br><br>Navigation zu Unternehmens-URLs ist zulässig.<br><br>Navigation zu privaten URLs ist zulässig.|Add-In wird im Unternehmenskontext geladen.<br><br>Navigation zu Unternehmens-URLs ist zulässig.<br><br>Navigation zu privaten URLs ist zulässig.|
|**Nicht gespeichert**      |Add-In wird im privaten Kontext geladen.<br><br>Navigation zu Unternehmens-URLs ist nicht zulässig (selbst in der eigenen Anwendungsdomäne).<br><br>Navigation zu privaten URLs ist zulässig.|Add-In wird im Unternehmenskontext geladen, und das Dokument wird automatisch in den Unternehmenskontext konvertiert. Das bedeutet, dass das Dokument an einem Speicherort des Unternehmens gespeichert werden muss.<br><br>Navigation zu Unternehmens-URLs ist zulässig. Navigation zu privaten URLs ist zulässig.            |


## <a name="add-ins-and-intune"></a>Add-Ins und Intune

Auf Office für iPad werden die Office-Add-Ins derzeit für Word, Excel und PowerPoint unterstützt. Outlook unterstützt derzeit Add-Ins für iOS (iPad und iPhone). Outlook-Administratoren können Add-Ins standardmäßig deaktivieren, einschließlich die vom Entwickler installierten Add-Ins, und nur die von ihrer Organisation genehmigten Add-Ins einzeln aktivieren. In der folgenden Tabelle wird die Unterstützung für Datenschutzszenarios für Add-Ins veranschaulicht, die auf Office für iOS-Geräten mit Tools für Intune-App-Schutz ausgeführt werden.

> [!NOTE]
> Informationen zu Outlook-Add-Ins, die auf Android- und iOS-Geräten ausgeführt werden, finden Sie unter [Verwalten des Benutzerzugriffs auf Add-Ins für Outlook](https://technet.microsoft.com/library/jj943757(v=exchg.150).aspx) und [Add-Ins für Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).

|**Dokument- oder Postfachtyp**|**Add-Ins im privaten Kontext für iOS mit Intune-App-Schutz<sup>*</sup>**|**Add-Ins im Unternehmenskontext für iOS mit Intune-App-Schutz<sup>*</sup>**|
|:-----|:-----|:-----|
|**Privat**|Die Nutzung von Add-Ins wird durch Intune-App-Schutz in privaten Dokumenten nicht beeinträchtigt.|Die Nutzung von Add-Ins wird durch Intune-App-Schutz in privaten Dokumenten nicht beeinträchtigt.|
|**Unternehmen**|Private Add-Ins dürfen aktiviert werden.<br><br>Intune-App-Schutzrichtlinien können das Ausschneiden, Kopieren und Einfügen sowie Datenübertragungsszenarios zwischen dem Add-In und anderen Anwendungen auf dem Gerät schützen.<br><br>Die Datenübertragung an Add-In-Dienste wird nicht geschützt.|Unternehmens-Add-Ins dürfen aktiviert werden. Administratoren können steuern, welche Add-Ins über Office-Verwaltungstools veröffentlicht werden [(zentralisierte Office 365-Bereitstellung)](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f).<br><br>Intune-App-Schutzrichtlinien können das Ausschneiden, Kopieren und Einfügen sowie Datenübertragungsszenarios zwischen dem Add-In und anderen Anwendungen auf dem Gerät schützen.<br><br>Die Datenübertragung an Add-In-Dienste wird nicht geschützt.|

>**<sup>*</sup>** Administratoren können die [zentralisierte Office 365-Bereitstellung](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f) verwenden, um Word-, Excel- und PowerPoint-Add-Ins für einzelne Benutzer, Gruppen oder eine Organisation direkt über das Office 365 Admin Center oder mithilfe von PowerShell-Skripts bereitzustellen. Beim Öffnen einer Office-Anwendung auf Windows, Mac oder Office Online wird das Add-In automatisch auf dem Menüband des Benutzers installiert.

## <a name="summary"></a>Zusammenfassung

Vor dem Hintergrund der Prinzipien für Office-Add-Ins erhalten Administratoren mit WIP und Intune die Möglichkeit, Unternehmensdaten zu verwalten und Tools bereitzustellen, die Benutzer für ihre Arbeit benötigen. Dadurch entsteht das Risiko, dass es zu Datenlecks von Unternehmensdaten nach außen kommt. Office JavaScript-APIs bieten derzeit keine Möglichkeit für Entwickler, den Typ der Daten zu erkennen, die zwischen Office-Dokument und Add-In übertragen werden. Daher müssen dem Benutzer mehrere Aufforderungen angezeigt werden, und es kann in manchen Fällen zu einer falschen Kennzeichnung von privaten Dateien als Unternehmensdateien kommen. Dies kann sich negativ auf die Benutzerfreundlichkeit auswirken und steht nicht im Einklang mit den Datenschutzprinzipien.

Microsoft setzt sich für den Schutz von Kundendaten ein und investiert weiterhin in die Verbesserung der Kundenfreundlichkeit im Umgang mit Intune- und WIP-Technologien.

## <a name="learn-more"></a>Weitere Informationen

-   [Allgemeine Informationen und bewährte Methoden für Windows Information Protection (WIP)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/guidance-and-best-practices-wip)

-   [Was ist Intune?](https://docs.microsoft.com/intune/introduction-intune)

-   [Übersicht über die Geräteregistrierungsmethoden](https://docs.microsoft.com/sccm/mdm/plan-design/device-enrollment-methods)

-   [Ändern Ihrer MDM-Autorität](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority)

-   [Vorbereitungen zum Konfigurieren von App-Schutzrichtlinien für Windows 10](https://docs.microsoft.com/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10)
