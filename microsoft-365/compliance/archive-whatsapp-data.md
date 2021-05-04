---
title: Einrichten eines Connectors zum Archivieren von WhatsApp-Daten in Microsoft 365
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
description: Administratoren können einen TeleMessage-Connector zum Importieren und Archivieren von WhatsApp-Daten in einem Microsoft 365. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 1387351772ccbb17f471c44fcd8d077df18a637e
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2021
ms.locfileid: "52077254"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>Einrichten eines Connectors zum Archivieren von WhatsApp-Daten

Verwenden Sie den TeleMessage-Connector im Microsoft 365 Compliance Center, um WhatsApp-Anrufe, Chats, Anlagen, Dateien und gelöschte Nachrichten zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, verbindet er sich einmal täglich mit dem TeleMessage-Konto Ihrer Organisation und importiert die mobile Kommunikation von Mitarbeitern mit dem TeleMessage WhatsApp Telefon Archiver oder TeleMessage WhatsApp Cloud Archiver in Postfächer in Microsoft 365.

Nachdem WhatsApp-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie z. B. Das Aufbewahrungsverfahren für Rechtsstreitigkeiten, die Inhaltssuche und Microsoft 365 Aufbewahrungsrichtlinien auf WhatsApp-Daten anwenden. Sie können beispielsweise WhatsApp-Nachrichten mithilfe der Inhaltssuche durchsuchen oder das Postfach, das WhatsApp-Nachrichten enthält, einem Custodian in einem Advanced eDiscovery zuordnen. Die Verwendung eines WhatsApp-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 Kann Dazu beitragen, dass Ihre Organisation die Richtlinien von Behörden und Behörden einhalten kann.

## <a name="overview-of-archiving-whatsapp-data"></a>Übersicht über die Archivierung von WhatsApp-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von WhatsApp-Daten in Microsoft 365.

![WhatsApp-Archivierungsworkflow](../media/WhatsAppConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage zusammen, um einen WhatsApp Archiver-Connector zu einrichten. Weitere Informationen finden Sie unter [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver).

2. In Echtzeit werden die WhatsApp-Daten Ihrer Organisation auf die TeleMessage-Website kopiert.

3. Der whatsApp-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit dem TeleMessage-Standort sicher und überträgt WhatsApp-Daten aus den vorherigen 24 Stunden an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud. Der Connector konvertiert auch die WhatsApp-Inhaltsdaten in ein E-Mail-Nachrichtenformat.

4. Der Connector importiert WhatsApp-Daten in das Postfach eines bestimmten Benutzers. Im Postfach des jeweiligen Benutzers wird ein neuer Ordner mit dem Namen **WhatsApp Archiver** erstellt, in den die Elemente importiert werden. Der Connector führt diese Zuordnung mithilfe des Werts der E-Mail-Adresseigenschaft *des Benutzers* aus. Jede WhatsApp-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der Nachricht aufgefüllt wird.

   Neben der automatischen Benutzerzuordnung mithilfe  des Werts der E-Mail-Adresseigenschaft des Benutzers können Sie auch benutzerdefinierte Zuordnungen implementieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei enthält die Mobiltelefonnummer und die Microsoft 365 E-Mail-Adresse für Benutzer in Ihrer Organisation. Wenn Sie sowohl die automatische Benutzerzuordnung als auch die benutzerdefinierte Zuordnung aktivieren, betrachtet der Connector zunächst für jedes WhatsApp-Element die benutzerdefinierte Zuordnungsdatei. Wenn kein gültiger benutzer Microsoft 365, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die Werte in der E-Mail-Adresse-Eigenschaft des Elements, das importiert werden soll. Wenn der Connector keinen gültigen benutzer Microsoft 365 in der benutzerdefinierten Zuordnungsdatei oder in der E-Mail-Adresseigenschaft des WhatsApp-Elements findet, wird das Element nicht importiert.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Einige der Implementierungsschritte, die zum Archivieren von WhatsApp-Kommunikationsdaten erforderlich sind, sind außerhalb von Microsoft 365 und müssen abgeschlossen sein, bevor Sie den Connector im Compliance Center erstellen können.

- Bestellen Sie [den WhatsApp Archiver-Dienst bei TeleMessage,](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) und erhalten Sie ein gültiges Verwaltungskonto für Ihre Organisation. Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector im Compliance Center erstellen.

- Registrieren Sie alle Benutzer, für die die WhatsApp-Archivierung erforderlich ist, im TeleMessage-Konto. Achten Sie beim Registrieren von Benutzern darauf, die gleiche E-Mail-Adresse zu verwenden, die für ihr Konto Microsoft 365 wird.

- Installieren Sie die TeleMessage [WhatsApp Telefon Archiver-App](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) auf den Mobiltelefonen Ihrer Mitarbeiter, und aktivieren Sie sie. Alternativ können Sie die regulären WhatsApp- oder WhatsApp Business-Apps auf den Mobiltelefonen Ihrer Mitarbeiter installieren und den WhatsApp Cloud Archiver-Dienst aktivieren, indem Sie einen QR-Code auf der TeleMessage-Website scannen. Weitere Informationen finden Sie unter [WhatsApp Cloud Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/).

- Dem Benutzer, der einen Verizon-Netzwerkconnector erstellt, muss die Rolle Postfachimportexport in der Exchange Online. Dies ist erforderlich, um Connectors auf der Seite **Datenconnectors** im compliance center Microsoft 365 hinzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="create-a-whatsapp-archiver-connector"></a>Erstellen eines WhatsApp-Archiverconnector

Nachdem Sie die im vorherigen Abschnitt beschriebenen Voraussetzungen erfüllt haben, können Sie den WhatsApp-Connector im Microsoft 365 erstellen. Der Connector verwendet die informationen, die Sie bereitstellen, um eine Verbindung mit der TeleMessage-Website herzustellen und die WhatsApp-Daten an die entsprechenden Benutzerpostfächer in Microsoft 365.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors**  >  **WhatsApp Archiver**.

2. Klicken Sie **auf der Seite WhatsApp Archiver-Produktbeschreibung** auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie **auf der Seite Bei TeleMessage** anmelden unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **Weiter**.

   - **Benutzername:** Ihr TeleMessage-Benutzername.

   - **Kennwort:** Ihr TeleMessage-Kennwort.

5. Nachdem der Connector erstellt wurde, können Sie das Popupfenster schließen und zur nächsten Seite wechseln.

6. Aktivieren Sie **auf der Seite** Benutzerzuordnung die automatische Benutzerzuordnung, und klicken Sie auf **Weiter**. Falls Sie eine benutzerdefinierte Zuordnung benötigen, laden Sie eine CSV-Datei hoch, und klicken Sie auf **Weiter**.

7. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen,** um den Connector zu erstellen.

8. Wechseln Sie auf der Seite **Datenconnectors** zur Registerkarte Connectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
