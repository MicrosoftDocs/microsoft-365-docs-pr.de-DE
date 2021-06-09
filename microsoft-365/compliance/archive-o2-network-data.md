---
title: Einrichten eines Connectors zum Archivieren von O2-Netzwerkdaten in Microsoft 365
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
description: Administratoren können einen TeleMessage-Connector einrichten, um SMS- und MMS-Daten aus dem O2-Mobilnetzwerk in Microsoft 365 zu importieren und zu archivieren. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliance-Features wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Daten von Drittanbietern Ihrer Organisation zu verwalten.
ms.openlocfilehash: f2604589fb91d36a8fc4a8d94be88757f198fa58
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822189"
---
# <a name="set-up-a-connector-to-archive-o2-network-data"></a>Einrichten eines Connectors zum Archivieren von O2-Netzwerkdaten

Verwenden Sie einen TeleMessage-Connector im Microsoft 365 Compliance Center, um Nachrichten und Sprachanrufe des Kurznachrichtendiensts (SMS) aus dem O2-Mobilnetzwerk zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er einmal täglich eine Verbindung mit dem O2-Netzwerk Ihrer Organisation her und importiert SMS und Sprachanrufe an Postfächer in Microsoft 365.

Nachdem SMS Nachrichten und Sprachanrufe in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung, Inhaltssuche und Microsoft 365 Aufbewahrungsrichtlinien auf O2-Netzwerkdaten anwenden. Sie können z. B. O2 Network SMS Nachrichten und Sprachanrufe mithilfe der Inhaltssuche durchsuchen oder das Postfach, das O2-Netzwerkdaten enthält, einem Verwahrer in einem Advanced eDiscovery Fall zuordnen. Die Verwendung eines O2-Netzwerkconnectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Behörden- und behördlichen Richtlinien zu halten.

## <a name="overview-of-archiving-o2-network-data"></a>Übersicht über die Archivierung von O2-Netzwerkdaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von O2-Netzwerkdaten in Microsoft 365 erläutert.

![O2-Netzwerkarchivierungsworkflow](../media/O2NetworkConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage und O2 zusammen, um einen O2-Netzwerkconnector einzurichten. Weitere Informationen finden Sie unter [O2 Network Archiver](https://www.telemessage.com/office365-activation-for-o2-network-archiver).

2. Einmal alle 24 Stunden werden SMS Nachrichten und Sprachanrufe aus dem O2-Netzwerk Ihrer Organisation auf die TeleMessage-Website kopiert.

3. Der O2-Netzwerkconnector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der TeleMessage-Website her und überträgt die SMS Nachrichten und Sprachanrufe aus den letzten 24 Stunden an einen sicheren Azure Storage Standort in der Microsoft-Cloud. Der Connector konvertiert auch den Inhalt von SMS Nachrichten und Sprachanrufen in ein E-Mail-Nachrichtenformat.

4. Der Connector importiert die Elemente für die mobile Kommunikation in das Postfach bestimmter Benutzer. Ein neuer Ordner mit dem Namen **O2 SMS und Voice Network Archiver** wird im Postfach eines bestimmten Benutzers erstellt, und die Elemente werden in das Postfach importiert. Der Connector führt diese Zuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft des Benutzers* durch. Jede SMS Nachricht und jeder Sprachanruf enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der Nachricht aufgefüllt wird.

   Zusätzlich zur automatischen Benutzerzuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft* des Benutzers können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei enthält die Mobiltelefonnummer und die entsprechende Microsoft 365 E-Mail-Adresse für Benutzer in Ihrer Organisation. Wenn Sie sowohl die automatische Benutzerzuordnung als auch die benutzerdefinierte Zuordnung aktivieren, überprüft der Connector zunächst für jedes O2-Element die benutzerdefinierte Zuordnungsdatei. Wenn kein gültiger Microsoft 365 Benutzer gefunden wird, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die Werte in der E-Mail-Adresseigenschaft des Elements, das importiert werden soll. Wenn der Connector keinen gültigen Microsoft 365 Benutzer in der benutzerdefinierten Zuordnungsdatei oder in der E-Mail-Adresseigenschaft des O2-Elements findet, wird das Element nicht importiert.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

Einige der zum Archivieren von O2-Netzwerkdaten erforderlichen Implementierungsschritte sind nicht Microsoft 365 und müssen abgeschlossen sein, bevor Sie einen Connector im Compliance Center erstellen können.

- Order the [O2 Network Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization. Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector im Compliance Center erstellen.

- Beziehen Sie Ihre O2-Netzwerkkonto- und Abrechnungskontaktdetails, damit Sie die TeleMessage-Onboardingformulare ausfüllen und den Nachrichtenarchivierungsdienst von O2 bestellen können.

- Registrieren Sie alle Benutzer, die die O2-SMS und die VoIP-Netzwerkarchivierung benötigen, im TeleMessage-Konto. Achten Sie beim Registrieren von Benutzern darauf, die gleiche E-Mail-Adresse zu verwenden, die für ihr Microsoft 365 Konto verwendet wird.

- Ihre Mitarbeiter müssen über unternehmenseigene und unternehmenseigene Mobiltelefone im O2-Mobilnetzwerk verfügen. Archivierungsnachrichten in Microsoft 365 sind für Byod-Geräte (Bring Your Own Devices) für Mitarbeiter nicht verfügbar.

- Dem Benutzer, der einen O2-Netzwerkconnector erstellt, muss die Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Dies ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Dieser Datenkonnektor ist in GCC Umgebungen in der cloud Microsoft 365 US Government verfügbar. Drittanbieteranwendungen und -dienste umfassen möglicherweise das Speichern, Übertragen und Verarbeiten der Kundendaten Ihrer Organisation auf Drittanbietersystemen, die sich außerhalb der Microsoft 365-Infrastruktur befinden und daher nicht unter die Verpflichtungen zur Einhaltung der Microsoft 365 und zum Datenschutz fallen. Microsoft macht keine Darstellung, dass die Verwendung dieses Produkts zum Herstellen einer Verbindung mit Drittanbieteranwendungen impliziert, dass diese Drittanbieteranwendungen FEDRAMP-konform sind.

## <a name="create-an-o2-network-connector"></a>Erstellen eines O2-Netzwerkconnectors

Nachdem Sie die im vorherigen Abschnitt beschriebenen Voraussetzungen erfüllt haben, können Sie einen O2-Netzwerkconnector im Microsoft 365 Compliance Center erstellen. Der Connector verwendet die von Ihnen bereitgestellten Informationen, um eine Verbindung mit der TeleMessage-Website herzustellen und SMS Nachrichten und Sprachanrufe an die entsprechenden Benutzerpostfachfelder in Microsoft 365 zu übertragen.

1. Wechseln [https://compliance.microsoft.com](https://compliance.microsoft.com/) Sie zu **"Datenconnectors** O2 Network", und klicken Sie dann auf \> "Datenconnectors". 

2. Klicken Sie auf der **O2 Network-Produktbeschreibungsseite** auf **"Connector hinzufügen".**

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