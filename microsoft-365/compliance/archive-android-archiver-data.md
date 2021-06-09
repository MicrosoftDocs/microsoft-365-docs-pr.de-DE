---
title: Einrichten eines Connectors zum Archivieren mobiler Android-Daten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Administratoren können einen TeleMessage-Connector einrichten, um SMS, MMS und Sprachanrufe von Android-Mobiltelefonen zu importieren und zu archivieren. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliance-Features wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Daten von Drittanbietern Ihrer Organisation zu verwalten.
ms.openlocfilehash: 6a70d57c5728b5e69df09a523f865d7e8beb8130
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822226"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a>Einrichten eines Connectors zum Archivieren mobiler Android-Daten

Verwenden Sie einen TeleMessage-Connector im Microsoft 365 Compliance Center, um SMS, MMS, Sprachanrufe und Anrufprotokolle von Android-Mobiltelefonen zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er einmal täglich eine Verbindung mit dem TeleMessage-Konto Ihrer Organisation her und importiert die mobile Kommunikation von Mitarbeitern mithilfe des TeleMessage Android Archiver in Postfächer in Microsoft 365.

Nachdem Daten von Android-Mobiltelefonen in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung, Inhaltssuche und Microsoft 365 Aufbewahrungsrichtlinien auf Android-Archivdaten anwenden. Sie können z. B. die mobile Kommunikation von Android Archiver mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die Android Archiver-Connectordaten enthält, einem Verwahrer in einem Advanced eDiscovery Fall zuordnen. Die Verwendung eines Android Archiver-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Behörden- und behördlichen Richtlinien zu halten.

## <a name="overview-of-archiving-android-mobile-data"></a>Übersicht über die Archivierung mobiler Android-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren mobiler Android-Daten in Microsoft 365 erläutert.

![Android Archiver Connector-Workflow](../media/AndroidArchiverConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage zusammen, um einen Android Archiver-Connector einzurichten. Weitere Informationen finden Sie unter [Android Archiver](https://www.telemessage.com/office365-activation-for-android-archiver/).

2. In Echtzeit werden SMS, MMS, Sprachanrufe und Anrufprotokolle von den Android-Mobiltelefonen Ihrer Organisation auf die TeleMessage-Website kopiert.

3. Der Android Archiver-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der TeleMessage-Website her und überträgt die Android-Daten aus den letzten 24 Stunden an einen sicheren Azure Storage Standort in der Microsoft-Cloud. Der Connector konvertiert auch die Android-Daten in ein E-Mail-Nachrichtenformat.

4. Der Connector importiert die Mobilen Kommunikationselemente in das Postfach eines bestimmten Benutzers. Ein neuer Ordner mit dem Namen "Android Archiver" wird im Postfach des bestimmten Benutzers erstellt, und die Elemente werden in das Postfach importiert. Der Connector verwendet die Zuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft des Benutzers.* Jede E-Mail-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der E-Mail-Nachricht aufgefüllt wird. Zusätzlich zur automatischen Benutzerzuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft* des Benutzers können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei sollte die Mobiltelefonnummer und die entsprechende Microsoft 365 Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird der Connector für jedes E-Mail-Element zuerst die benutzerdefinierte Zuordnungsdatei betrachten. Wenn kein gültiger Microsoft 365 Benutzer gefunden wird, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die E-Mail-Adresseigenschaft des Benutzers des E-Mail-Elements. Wenn der Connector keinen gültigen Microsoft 365 Benutzer in der benutzerdefinierten Zuordnungsdatei oder in der *E-Mail-Adresseigenschaft des E-Mail-Elements* des Benutzers findet, wird das Element nicht importiert.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

Einige der Implementierungsschritte, die zum Archivieren von Android-Kommunikationsdaten erforderlich sind, sind nicht Microsoft 365 und müssen abgeschlossen sein, bevor Sie den Connector im Compliance Center erstellen können.

- Order the [Android Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization. Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector erstellen.

- Registrieren Sie alle Benutzer, die den Android-Archivdienst benötigen, im TeleMessage-Konto. Achten Sie beim Registrieren von Benutzern darauf, die gleiche E-Mail-Adresse zu verwenden, die für ihr Microsoft 365 Konto verwendet wird.

- Installieren und aktivieren Sie die TeleMessage Android Archiver-App auf den Mobiltelefonen Ihrer Mitarbeiter.

- Dem Benutzer, der einen Android Archiver-Connector erstellt, muss die Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Dies ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Dieser Datenkonnektor ist in GCC Umgebungen in der cloud Microsoft 365 US Government verfügbar. Drittanbieteranwendungen und -dienste umfassen möglicherweise das Speichern, Übertragen und Verarbeiten der Kundendaten Ihrer Organisation auf Drittanbietersystemen, die sich außerhalb der Microsoft 365-Infrastruktur befinden und daher nicht unter die Verpflichtungen zur einhaltung der Microsoft 365 und zum Datenschutz fallen. Microsoft macht keine Darstellung, dass die Verwendung dieses Produkts zum Herstellen einer Verbindung mit Drittanbieteranwendungen impliziert, dass diese Drittanbieteranwendungen FEDRAMP-konform sind.

## <a name="create-an-android-archiver-connector"></a>Erstellen eines Android Archiver-Connectors

Der letzte Schritt besteht darin, einen Android Archiver-Connector im Microsoft 365 Compliance Center zu erstellen. Der Connector verwendet die informationen, die Sie angeben, um eine Verbindung mit der TeleMessage-Website herzustellen und die Android-Kommunikation an die entsprechenden Benutzerpostfachfelder in Microsoft 365 zu übertragen.

1. Wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com) **"Datenconnectors"** und klicken Sie auf  >  **"Android Archiver".**

2. Klicken Sie auf der Produktbeschreibungsseite für **Android Archiver** auf **Connector hinzufügen.**

3. Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie auf der Seite **"Bei TeleMessage anmelden"** unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **"Weiter".**

   - **Benutzername:** Ihr TeleMessage-Benutzername.

   - **Kennwort:** Ihr TeleMessage-Kennwort.

5. Schließen Sie nach dem Erstellen des Connectors das Popupfenster, und klicken Sie auf **"Weiter".**

6. Aktivieren Sie auf der Seite **"Benutzerzuordnung"** die automatische Benutzerzuordnung, und klicken Sie auf **"Weiter".** Falls Sie eine csv-Datei mit benutzerdefinierter Zuordnung hochladen möchten, klicken Sie auf **"Weiter".**

7. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen,** um den Connector zu erstellen.

8. Wechseln Sie zur Registerkarte Connectors auf der Seite **"Datenconnectors",** um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
