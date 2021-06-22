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
description: Administratoren können einen TeleMessage-Connector einrichten, um WhatsApp-Daten in Microsoft 365 zu importieren und zu archivieren. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliance-Features wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Daten von Drittanbietern Ihrer Organisation zu verwalten.
ms.openlocfilehash: 0f4759eeb26190d7fdfc92cbf986efecd017eda5
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054791"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>Einrichten eines Connectors zum Archivieren von WhatsApp-Daten

Verwenden Sie den TeleMessage-Connector im Microsoft 365 Compliance Center, um WhatsApp-Anrufe, Chats, Anlagen, Dateien und gelöschte Nachrichten zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er einmal täglich eine Verbindung mit dem TeleMessage-Konto Ihrer Organisation her und importiert die mobile Kommunikation von Mitarbeitern mithilfe der TeleMessage WhatsApp Telefon Archiver oder TeleMessage WhatsApp Cloud Archiver in Postfächer in Microsoft 365.

Nachdem WhatsApp-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherungsverfahren, Inhaltssuche und Microsoft 365 Aufbewahrungsrichtlinien auf WhatsApp-Daten anwenden. Sie können beispielsweise WhatsApp-Nachrichten mithilfe der Inhaltssuche durchsuchen oder das Postfach, das WhatsApp-Nachrichten enthält, einem Verwahrer in einem Advanced eDiscovery Fall zuordnen. Die Verwendung eines WhatsApp-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Regierungsrichtlinien und behördlichen Richtlinien zu halten.

## <a name="overview-of-archiving-whatsapp-data"></a>Übersicht über die Archivierung von WhatsApp-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von WhatsApp-Daten in Microsoft 365 erläutert.

![WhatsApp-Archivierungsworkflow](../media/WhatsAppConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage zusammen, um einen WhatsApp Archiver-Connector einzurichten. Weitere Informationen finden Sie unter [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver).

2. In Echtzeit werden die WhatsApp-Daten Ihrer Organisation auf die TeleMessage-Website kopiert.

3. Der WhatsApp-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der TeleMessage-Website her und überträgt WhatsApp-Daten aus den letzten 24 Stunden an einen sicheren Azure Storage Standort in der Microsoft-Cloud. Der Connector konvertiert auch die WhatsApp-Inhaltsdaten in ein E-Mail-Nachrichtenformat.

4. Der Connector importiert WhatsApp-Daten in das Postfach eines bestimmten Benutzers. Ein neuer Ordner mit dem Namen **WhatsApp Archiver** wird im Postfach des bestimmten Benutzers erstellt, und die Elemente werden in das Postfach importiert. Der Connector führt diese Zuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft des Benutzers* durch. Jede WhatsApp-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der Nachricht aufgefüllt wird.

   Zusätzlich zur automatischen Benutzerzuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft* des Benutzers können Sie auch eine benutzerdefinierte Zuordnung implementieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei enthält die Mobiltelefonnummer und die entsprechende Microsoft 365 E-Mail-Adresse für Benutzer in Ihrer Organisation. Wenn Sie sowohl die automatische Benutzerzuordnung als auch die benutzerdefinierte Zuordnung aktivieren, überprüft der Connector zunächst für jedes WhatsApp-Element die benutzerdefinierte Zuordnungsdatei. Wenn kein gültiger Microsoft 365 Benutzer gefunden wird, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die Werte in der E-Mail-Adresseigenschaft des Elements, das importiert werden soll. Wenn der Connector keinen gültigen Microsoft 365 Benutzer in der benutzerdefinierten Zuordnungsdatei oder in der E-Mail-Adresseigenschaft des WhatsApp-Elements findet, wird das Element nicht importiert.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

Einige der Implementierungsschritte, die zum Archivieren von WhatsApp-Kommunikationsdaten erforderlich sind, befinden sich außerhalb Microsoft 365 und müssen abgeschlossen sein, bevor Sie den Connector im Compliance Center erstellen können.

- Order the [WhatsApp Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization. Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector im Compliance Center erstellen.

- Registrieren Sie alle Benutzer, die eine WhatsApp-Archivierung benötigen, im TeleMessage-Konto. Achten Sie beim Registrieren von Benutzern darauf, die gleiche E-Mail-Adresse zu verwenden, die für ihr Microsoft 365 Konto verwendet wird.

- Installieren Sie die TeleMessage [WhatsApp Telefon Archiver-App](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) auf den Mobiltelefonen Ihrer Mitarbeiter, und aktivieren Sie sie. Alternativ können Sie die regulären WhatsApp- oder WhatsApp Business-Apps auf den Mobiltelefonen Ihrer Mitarbeiter installieren und den WhatsApp Cloud Archiver-Dienst aktivieren, indem Sie einen QR-Code auf der TeleMessage-Website scannen. Weitere Informationen finden Sie unter [WhatsApp Cloud Archiver.](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/)

- Dem Benutzer, der einen Verizon-Netzwerkconnector erstellt, muss die Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Dies ist erforderlich, um Connectors auf der **Seite "Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Dieser Datenkonnektor ist in GCC Umgebungen in der Microsoft 365 US Government-Cloud verfügbar. Drittanbieteranwendungen und -dienste umfassen möglicherweise das Speichern, Übertragen und Verarbeiten der Kundendaten Ihrer Organisation auf Drittanbietersystemen, die sich außerhalb der Microsoft 365-Infrastruktur befinden und daher nicht unter die Verpflichtungen zur Einhaltung der Microsoft 365 und zum Datenschutz fallen. Microsoft macht keine Darstellung, dass die Verwendung dieses Produkts zum Herstellen einer Verbindung mit Drittanbieteranwendungen impliziert, dass diese Drittanbieteranwendungen FEDRAMP-konform sind.

## <a name="create-a-whatsapp-archiver-connector"></a>Erstellen eines WhatsApp Archiver-Connectors

Nachdem Sie die im vorherigen Abschnitt beschriebenen Voraussetzungen erfüllt haben, können Sie den WhatsApp-Connector im Microsoft 365 Compliance Center erstellen. Der Connector verwendet die von Ihnen angegebenen Informationen, um eine Verbindung mit der TeleMessage-Website herzustellen und die WhatsApp-Daten an die entsprechenden Benutzerpostfachfelder in Microsoft 365 zu übertragen.

1. Wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com/) **"Datenconnectors** WhatsApp Archiver", und klicken Sie dann auf  >  **"Datenconnectors".**

2. Klicken Sie auf der Seite **"WhatsApp** Archiver"-Produktbeschreibung auf **"Connector hinzufügen".**

3. Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie auf der Seite **"Bei TeleMessage anmelden"** unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **"Weiter".**

   - **Benutzername:** Ihr TeleMessage-Benutzername.

   - **Kennwort:** Ihr TeleMessage-Kennwort.

5. Nachdem der Connector erstellt wurde, können Sie das Popupfenster schließen und zur nächsten Seite wechseln.

6. Aktivieren Sie auf der Seite **"Benutzerzuordnung"** die automatische Benutzerzuordnung, und klicken Sie auf **"Weiter".** Falls Sie eine csv-Datei mit benutzerdefinierter Zuordnung hochladen möchten, klicken Sie auf **"Weiter".**

7. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen,** um den Connector zu erstellen.

8. Wechseln Sie zur Registerkarte Connectors auf der Seite **"Datenconnectors",** um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
