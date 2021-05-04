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
description: Administratoren können einen TeleMessage-Connector einrichten, um SMS, MMS und Sprachanrufe von Android-Mobiltelefonen zu importieren und zu archivieren. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 92dcfbebaeb9f138b5a057d36e328967c43c9544
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2021
ms.locfileid: "52077234"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a>Einrichten eines Connectors zum Archivieren mobiler Android-Daten

Verwenden Sie einen TeleMessage-Connector im Microsoft 365 Compliance Center, um SMS, MMS, Sprachanrufe und Anrufprotokolle von Android-Mobiltelefonen zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, verbindet er sich einmal täglich mit dem TeleMessage-Konto Ihrer Organisation und importiert die mobile Kommunikation von Mitarbeitern mit dem TeleMessage Android Archiver in Postfächer in Microsoft 365.

Nachdem Daten von Android-Mobiltelefonen in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie z. B. Das Aufbewahrungsverfahren für Rechtsstreitigkeiten, die Inhaltssuche und Microsoft 365 Aufbewahrungsrichtlinien auf Android Archiver-Daten anwenden. Sie können z. B. die mobile Android Archiver-Kommunikation mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die Daten des Android Archiver-Connectors enthält, einem Verwahrer in einem Advanced eDiscovery zuordnen. Die Verwendung eines Android Archiver-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Richtlinien von Behörden und Behörden einhalten kann.

## <a name="overview-of-archiving-android-mobile-data"></a>Übersicht über die Archivierung mobiler Android-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren mobiler Android-Daten in Microsoft 365.

![Android Archiver Connector-Workflow](../media/AndroidArchiverConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage zusammen, um einen Android Archiver-Connector zu einrichten. Weitere Informationen finden Sie unter [Android Archiver](https://www.telemessage.com/office365-activation-for-android-archiver/).

2. In Echtzeit werden SMS, MMS, Sprachanrufe und Anrufprotokolle von den Android-Mobiltelefonen Ihrer Organisation auf die TeleMessage-Website kopiert.

3. Der im Microsoft 365 Compliance Center erstellte Android Archiver-Connector stellt täglich eine Verbindung mit der TeleMessage-Website sicher und überträgt die Android-Daten aus den vorherigen 24 Stunden an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud. Der Connector konvertiert auch die Android-Daten in ein E-Mail-Nachrichtenformat.

4. Der Connector importiert die mobilen Kommunikationselemente in das Postfach eines bestimmten Benutzers. Im Postfach des jeweiligen Benutzers wird ein neuer Ordner mit dem Namen Android Archiver erstellt, in den die Elemente importiert werden. Der Connector wird mithilfe des Werts der E-Mail-Adresseigenschaft des *Benutzers zugeordnet.* Jede E-Mail-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der E-Mail-Nachricht gefüllt wird. Neben der automatischen Benutzerzuordnung mithilfe  des Werts der E-Mail-Adresseigenschaft des Benutzers können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei sollte die Mobiltelefonnummer und die Microsoft 365 Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird für jedes E-Mail-Element zunächst die benutzerdefinierte Zuordnungsdatei vom Connector angezeigt. Wenn kein gültiger Benutzer Microsoft 365, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die E-Mail-Adresseigenschaft des Benutzers des E-Mail-Elements. Wenn der Connector keinen gültigen benutzer Microsoft 365 in der benutzerdefinierten  Zuordnungsdatei oder der E-Mail-Adresseigenschaft des E-Mail-Elements des Benutzers findet, wird das Element nicht importiert.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Einige der Implementierungsschritte, die zum Archivieren von Android-Kommunikationsdaten erforderlich sind, sind Microsoft 365 und müssen abgeschlossen werden, bevor Sie den Connector im Compliance Center erstellen können.

- Bestellen Sie [den Android Archiver-Dienst bei TeleMessage,](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) und erhalten Sie ein gültiges Verwaltungskonto für Ihre Organisation. Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector erstellen.

- Registrieren Sie alle Benutzer, die den Android Archiver-Dienst benötigen, im TeleMessage-Konto. Achten Sie beim Registrieren von Benutzern darauf, die gleiche E-Mail-Adresse zu verwenden, die für ihr Konto Microsoft 365 wird.

- Installieren und aktivieren Sie die TeleMessage Android Archiver-App auf den Mobiltelefonen Ihrer Mitarbeiter.

- Dem Benutzer, der einen Android Archiver-Connector erstellt, muss die Rolle Postfachimportexport in der Exchange Online. Dies ist erforderlich, um Connectors auf der Seite **Datenconnectors** im compliance center Microsoft 365 hinzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="create-an-android-archiver-connector"></a>Erstellen eines Android Archiver-Connectors

Der letzte Schritt besteht im Erstellen eines Android Archiver-Connectors im Microsoft 365 Compliance Center. Der Connector verwendet die informationen, die Sie bereitstellen, um eine Verbindung mit der TeleMessage-Website herzustellen und die Android-Kommunikation an die entsprechenden Benutzerpostfächer in Microsoft 365.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu Und klicken Sie auf **Datenconnectors** Android  >  **Archiver**.

2. Klicken Sie **auf der Seite Android Archiver-Produktbeschreibung** auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie **auf der Seite Bei TeleMessage** anmelden unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **Weiter**.

   - **Benutzername:** Ihr TeleMessage-Benutzername.

   - **Kennwort:** Ihr TeleMessage-Kennwort.

5. Nachdem der Connector erstellt wurde, schließen Sie das Popupfenster, und klicken Sie auf **Weiter**.

6. Aktivieren Sie **auf der Seite** Benutzerzuordnung die automatische Benutzerzuordnung, und klicken Sie auf **Weiter**. Falls Sie eine benutzerdefinierte Zuordnung benötigen, laden Sie eine CSV-Datei hoch, und klicken Sie auf **Weiter**.

7. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen,** um den Connector zu erstellen.

8. Wechseln Sie auf der Seite **Datenconnectors** zur Registerkarte Connectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
