---
title: Verwenden der Interoperabilität von OneDrive-Lerntools
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Erstellen und Notieren von Aufgaben, Erstellen und Kurieren von Kursinhalten und Zusammenarbeit an Dateien in Echtzeit mit der neuen OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 97baf3e524e483e879d00f5e0c8495b450e13c92
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327739"
---
# <a name="use-microsoft-onedrive-with-your-learning-management-system"></a>Verwenden von Microsoft OneDrive mit Ihrem Lernverwaltungssystem

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Erfahren Sie mehr über die Vorteile der Verwendung von Microsoft OneDrive mit Ihrem Learning Management System (LMS).

**Bringt Microsoft Office 365 direkt in Ihre Workflows**

Die Microsoft OneDrive Learning Tools Interoperability (LTI)-App ist in Ihr LMS integriert, um Microsoft OneDrive und Microsoft Office 365 direkt in Ihre wichtigsten Workflows zu integrieren, die Folgendes umfassen:

- Anfügen von Ressourcen und Organisieren von Inhalten.
- Starten von gemeinsamen Dokumenten.
- Erstellen und Benoten von Zuordnungen.

**Sicher und vollständig kompatibel mit den neuesten LTI-Standards**

Die Microsoft OneDrive #A0 ist mit LTI 1.3 und LTI Advantage kompatibel. Dieser Vorteil ermöglicht eine hochgradig sichere und eng integrierte Benutzeroberfläche.

**Moderne und reichhaltige Benutzeroberfläche**

Die Microsoft OneDrive LTI App bringt das Beste von Microsoft direkt in Ihre #A0 ein. Wir verbessern die vorhandene Office 365-Integration in Ihrem LMS, indem wir eine modernere Benutzeroberfläche mit einer neuen und erweiterten Microsoft OneDrive-Dateiauswahl und einer erweiterten Bearbeitungserfahrung für #A0 bereitstellen. Microsoft wird auch die Microsoft OneDrive LTI App in Zukunft vollständig besitzen, was bedeutet, dass Sie immer automatisch das neueste und beste von Microsoft erhalten.

Mit der Microsoft OneDrive LTI App können Sie:

- Fügen Sie Office 365-Dateien einschließlich Word-Dokumenten, PowerPoint-Präsentationen und Excel aus dem Rich Content Editor an.

- Verteilen von Office 365-Cloudzuweisungen.

- Anzeigen und Organisieren Ihrer persönlichen Und Kurs Microsoft OneDrive-Dateien.

- Erstellen Sie Zusammenarbeiten, in denen Kursmitglieder gemeinsam an freigegebenen Dokumenten in Echtzeit arbeiten können.

- Greifen Sie auf mehrere Microsoft #A0 zu, einschließlich persönlicher und Schulkonten.

- Integrieren Sie Office 365-Dateien in Ihre Kursmodule.

- Verwenden Sie Ihr Microsoft-Konto für einmaliges Anmelden mit Ihrem LMS.

## <a name="integrate-with-canvas"></a>Integration in Canvas

Die Person, die diese Integration ausführt, sollte ein Administrator von Canvas und ein Administrator des Microsoft 365-Mandanten sein.

1. Melden Sie sich mit dem Mandantenadministratorkonto beim Microsoft Azure-Portal an. Der Azure-Mandantenadministrator sollte auch die Rolle des Gruppenadministrators haben.

    ![Gruppenadministrator hervorgehoben](../media/lti-media/lti-group-admin.png)

2. Melden Sie sich beim Microsoft [OneDrive#A0 an.](https://odltiappnl.azurewebsites.net/admin)

3. Akzeptieren Sie die Berechtigungen zum Abschließen der Anmeldung.

    ![Akzeptieren von Berechtigungen](../media/lti-media/lti-permissions.png)

4. Wählen **Sie LTI-Mandanten hinzufügen aus.**

     ![Hinzufügen eines LTI-Mandanten](../media/lti-media/lti-add-tenant.png)

5. Wählen **Sie im Dropdownmenü LTI Consumer Platform** as **Canvas** aus.

6. Wählen **Sie Canvas-Basis-URL** aus, und wählen Sie dann **Weiter aus.**

    ![Auswählen von Canvas und Hinzufügen der Basis-URL](../media/lti-media/lti-canvas-base-url.png)

   Auf dem nächsten Bildschirm werden Felder angezeigt, die für Sie vertraulich sind.

7. Wählen **Sie Weiter** aus ?? aus. den Link für resend the email auswählen. KÖNNEN PRÜFER HIER DAS LEERE AUSFÜLLEN?

8. Wählen **Sie weiter** auf dem Bildschirm aus, auf dem Informationen angezeigt werden, die für Sie vertraulich sind.

   Der letzte Bildschirm des Azure-Portals zeigt die nächsten Schritte zum Hinzufügen Ihrer Canvas-Instanz.

9. Kopieren Sie die Entwicklerschlüssel von diesem Bildschirm. Sie werden beim Erstellen der Canvas-Instanz verwendet.

## <a name="add-the-canvas-instance"></a>Hinzufügen der Canvas-Instanz

1. Deaktivieren Sie in Ihrer Canvas-Instanz die Option **Admin**  >  **Developer Keys**.

2. Wählen **Sie LTI Key** im Dropdown unter Developer Key **aus.**

   ![Erhalten der LTI-Entwicklerschlüssel](../media/lti-media/lti-developer-keys.png)

3. Fügen Sie hier die Entwicklerschlüssel ein.

     ![Einfügen der Entwicklerschlüssel](../media/lti-media/lti-developer-keys.png)

   Der Schlüssel wird im **AUS-Modus** erstellt

   ![Die erstellten Entwicklerschlüssel im Aus-Modus](../media/lti-media/lti-copy-developer-keys.png)

4. Kopieren Sie den hervorgehobenen Text.
    Dies dient als Client-ID im Microsoft OneDrive-LTI-Portal.

5. Fügen Sie den Text in das **Feld Client-ID** im Microsoft OneDrive#A0 ein, und wählen Sie dann **Weiter aus.**

6. Wählen Sie **Speichern** aus.

7. Zeigen Sie die Einstellungen an, indem **Sie LTI-Mandanten anzeigen auswählen.**
