---
title: Einrichten eines Connectors zum Archivieren von SMS/MMS-Netzwerkdaten
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
description: Administratoren können einen TeleMessage-Connector einrichten, um SMS- und MMS-Daten aus dem Bell-Netzwerk zu importieren und zu archivieren. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliance-Features wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Daten von Drittanbietern Ihrer Organisation zu verwalten.
ms.openlocfilehash: 7cfdb4556c19261b7e377df72ebe96b9cf20c992
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822214"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>Einrichten eines Connectors zum Archivieren von Klingelnetzwerkdaten

Verwenden Sie einen TeleMessage-Connector im Microsoft 365 Compliance Center, um Nachrichten des Kurznachrichtendiensts (SMS) und des Multimedianachrichtendiensts (MMS) aus dem Klingelnetzwerk zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er einmal täglich eine Verbindung mit dem Klingelnetzwerk Ihrer Organisation her und importiert SMS- und MMS-Nachrichten in Postfächer in Microsoft 365.

Nachdem die SMS- und MMS-Nachrichten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung, Inhaltssuche und Microsoft 365 Aufbewahrungsrichtlinien auf Bell Network-Daten anwenden. Sie können z. B. mithilfe der Inhaltssuche das Klingelnetzwerk SMS/MMS durchsuchen oder das Postfach, das die Connectordaten des Klingelnetzwerks enthält, einem Verwahrer in einem Advanced eDiscovery Fall zuordnen. Die Verwendung eines Bell-Netzwerkconnectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Behörden- und Behördlichen Richtlinien zu halten.

## <a name="overview-of-archiving-bell-network-data"></a>Übersicht über die Archivierung von Bell Network-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Bell Network-Daten in Microsoft 365 erläutert.

![Archivierungsworkflow für das Klingelnetzwerk](../media/BellNetworkConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage und Bell zusammen, um einen Connector für das Klingelnetzwerk einzurichten. Weitere Informationen finden Sie unter ["Bell Network Archiver".](https://www.telemessage.com/office365-activation-for-bell-network-archiver)

2. In Echtzeit werden SMS- und MMS-Nachrichten aus dem Klingelnetzwerk Ihrer Organisation auf die TeleMessage-Website kopiert.

3. Der Von Ihnen im Microsoft 365 Compliance Center erstellte Bell Network-Connector stellt täglich eine Verbindung mit der TeleMessage-Website her und überträgt die SMS- und MMS-Nachrichten aus den letzten 24 Stunden an einen sicheren Azure Storage Standort in der Microsoft-Cloud. Der Connector konvertiert auch den Inhalt von SMS- und MMS-Nachrichten in ein E-Mail-Nachrichtenformat.

4. Der Connector importiert die Elemente für die mobile Kommunikation in das Postfach bestimmter Benutzer. Ein neuer Ordner mit dem Namen **"Bell SMS/MMS Network Archiver"** wird im Postfach eines bestimmten Benutzers erstellt, und die Elemente werden in das Postfach importiert. Der Connector führt diese Zuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft des Benutzers* durch. Jede SMS- und MMS-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der Nachricht aufgefüllt wird.

   Zusätzlich zur automatischen Benutzerzuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft* des Benutzers können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei enthält die Mobiltelefonnummer und die entsprechende Microsoft 365 E-Mail-Adresse für Benutzer in Ihrer Organisation. Wenn Sie sowohl die automatische Benutzerzuordnung als auch die benutzerdefinierte Zuordnung aktivieren, überprüft der Connector zunächst für jedes Element des Klingelnetzwerks die benutzerdefinierte Zuordnungsdatei. Wenn kein gültiger Microsoft 365 Benutzer gefunden wird, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die Werte in der E-Mail-Adresseigenschaft des Elements, das importiert werden soll. Wenn der Connector keinen gültigen Microsoft 365 Benutzer in der benutzerdefinierten Zuordnungsdatei oder in der E-Mail-Adresseigenschaft des Bell Network-Elements findet, wird das Element nicht importiert.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

Einige der zum Archivieren von Klingelnetzwerkdaten erforderlichen Implementierungsschritte befinden sich außerhalb Microsoft 365 und müssen abgeschlossen sein, bevor Sie einen Connector im Compliance Center erstellen können.

- Order the [Bell Network Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization. Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector im Compliance Center erstellen.

- Beziehen Sie Ihr Bell Network-Konto und die Rechnungskontaktdetails, damit Sie die TeleMessage-Onboardingformulare ausfüllen und den Nachrichtenarchivierungsdienst von Bell bestellen können.

- Registrieren Sie alle Benutzer, für die die Archivierung des SMS/MMS-Netzwerks erforderlich ist, im TeleMessage-Konto. Achten Sie beim Registrieren von Benutzern darauf, die gleiche E-Mail-Adresse zu verwenden, die für ihr Microsoft 365 Konto verwendet wird.

- Ihre Mitarbeiter müssen über unternehmenseigene und unternehmenseigene Mobiltelefone im Mobilen Klingelnetzwerk verfügen. Archivierungsnachrichten in Microsoft 365 sind für Byod-Geräte (Bring Your Own Devices) für Mitarbeiter nicht verfügbar.

- Dem Benutzer, der einen Bell Network-Connector erstellt, muss die Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Dies ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Dieser Datenkonnektor ist in GCC Umgebungen in der cloud Microsoft 365 US Government verfügbar. Drittanbieteranwendungen und -dienste umfassen möglicherweise das Speichern, Übertragen und Verarbeiten der Kundendaten Ihrer Organisation auf Drittanbietersystemen, die sich außerhalb der Microsoft 365-Infrastruktur befinden und daher nicht unter die Verpflichtungen zur einhaltung der Microsoft 365 und zum Datenschutz fallen. Microsoft macht keine Darstellung, dass die Verwendung dieses Produkts zum Herstellen einer Verbindung mit Drittanbieteranwendungen impliziert, dass diese Drittanbieteranwendungen FEDRAMP-konform sind.

## <a name="create-a-bell-network-connector"></a>Erstellen eines Bell-Netzwerkconnectors

Der letzte Schritt besteht darin, einen Bell Network-Connector im Microsoft 365 Compliance Center zu erstellen. Der Connector verwendet die von Ihnen bereitgestellten Informationen, um eine Verbindung mit der TeleMessage-Website herzustellen und SMS/MMS-Nachrichten an die entsprechenden Benutzerpostfachfelder in Microsoft 365 zu übertragen.

1. Wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com) "Data Connectors Bell SMS/MMS Network Archiver", und klicken Sie dann auf **"Datenconnectors".**  >  

2. Klicken Sie auf der Produktbeschreibungsseite **des Klingelnetzwerks** auf **"Connector hinzufügen".**

3. Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie auf der Seite **"Bei TeleMessage anmelden"** unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **"Weiter".**

   - **Benutzername:** Ihr TeleMessage-Benutzername.

   - **Kennwort:** Ihr TeleMessage-Kennwort.

5. Nachdem der Connector erstellt wurde, können Sie das Popupfenster schließen und zur nächsten Seite wechseln.

6. Aktivieren Sie auf der Seite **"Benutzerzuordnung"** die automatische Benutzerzuordnung. Laden Sie zum Aktivieren der benutzerdefinierten Zuordnung eine CSV-Datei hoch, die die Benutzerzuordnungsinformationen enthält, und klicken Sie dann auf **"Weiter".**

7. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen,** um den Connector zu erstellen.

8. Wechseln Sie zur Registerkarte **Connectors** auf der Seite **"Datenconnectors"** im Compliance Center, um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
