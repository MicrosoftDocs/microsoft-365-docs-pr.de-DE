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
description: Administratoren können einen TeleMessage-Connector einrichten, um SMS und MMS-Daten aus dem Glockennetzwerk zu importieren und zu archivieren. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 8672130fa3f7375dc88241f4a1892e0ce98f23f8
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2021
ms.locfileid: "52077214"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>Einrichten eines Connectors zum Archivieren von Bell Network-Daten

Verwenden Sie einen TeleMessage-Connector im Microsoft 365 Compliance Center, um Nachrichten des Kurznachrichtendiensts (SMS) und des Multimedia Messaging Service (MMS) aus dem Glockennetzwerk zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er einmal täglich eine Verbindung mit dem Bell Network Ihrer Organisation zusammen und importiert SMS- und MMS-Nachrichten in Postfächer in Microsoft 365.

Nachdem die SMS- und MMS-Nachrichten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie z. B. Das Rechtsstreitigkeitensverfahren, die Inhaltssuche und Microsoft 365 Aufbewahrungsrichtlinien auf Bell Network-Daten anwenden. Sie können z. B. bell network SMS/MMS mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die Bell Network Connector-Daten enthält, einem Verwahrer in einem Advanced eDiscovery zuordnen. Die Verwendung eines Bell Network-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Richtlinien von Behörden und Behörden einhalten kann.

## <a name="overview-of-archiving-bell-network-data"></a>Übersicht über die Archivierung von Bell Network-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Bell Network-Daten in Microsoft 365.

![Archivierungsworkflow für das Glockennetzwerk](../media/BellNetworkConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage und Bell zusammen, um einen Bell Network Connector zu einrichten. Weitere Informationen finden Sie unter [Bell Network Archiver](https://www.telemessage.com/office365-activation-for-bell-network-archiver).

2. In Echtzeit werden SMS und MMS-Nachrichten aus dem Bell Network Ihrer Organisation auf die TeleMessage-Website kopiert.

3. Der im Microsoft 365 Compliance Center erstellte Glockennetzwerkconnector stellt täglich eine Verbindung mit dem TeleMessage-Standort sicher und überträgt die SMS- und MMS-Nachrichten aus den vorherigen 24 Stunden an einen sicheren Azure Storage-Standort in der Microsoft-Cloud. Der Connector konvertiert auch den Inhalt von SMS und MMS-Nachrichten in ein E-Mail-Nachrichtenformat.

4. Der Connector importiert die mobilen Kommunikationselemente in das Postfach bestimmter Benutzer. Ein neuer Ordner namens **Bell SMS/MMS Network Archiver** wird im Postfach eines bestimmten Benutzers erstellt, und die Elemente werden in das Postfach importiert. Der Connector führt diese Zuordnung mithilfe des Werts der E-Mail-Adresseigenschaft *des Benutzers* aus. Jede SMS und MMS-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der Nachricht aufgefüllt wird.

   Neben der automatischen Benutzerzuordnung mithilfe  des Werts der E-Mail-Adresseigenschaft des Benutzers können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei enthält die Mobiltelefonnummer und die Microsoft 365 E-Mail-Adresse für Benutzer in Ihrer Organisation. Wenn Sie sowohl die automatische Benutzerzuordnung als auch die benutzerdefinierte Zuordnung aktivieren, betrachtet der Connector zunächst für jedes Bell Network-Element die benutzerdefinierte Zuordnungsdatei. Wenn kein gültiger benutzer Microsoft 365, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die Werte in der E-Mail-Adresse-Eigenschaft des Elements, das importiert werden soll. Wenn der Connector keinen gültigen benutzer Microsoft 365 in der benutzerdefinierten Zuordnungsdatei oder in der E-Mail-Adresseigenschaft des Bell Network-Elements findet, wird das Element nicht importiert.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Einige der Implementierungsschritte, die zum Archivieren von Bell Network-Daten erforderlich sind, sind Microsoft 365 und müssen abgeschlossen sein, bevor Sie einen Connector im Compliance Center erstellen können.

- Bestellen Sie [den Bell Network Archiver-Dienst bei TeleMessage,](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) und erhalten Sie ein gültiges Verwaltungskonto für Ihre Organisation. Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector im Compliance Center erstellen.

- Rufen Sie Ihr Bell Network-Konto und Ihre Abrechnungskontaktdetails ab, damit Sie die TeleMessage-Onboardingformulare ausfüllen und den Nachrichtenarchivierungsdienst bei Bell bestellen können.

- Registrieren Sie alle Benutzer, die eine SMS/MMS-Netzwerkarchivierung erfordern, im TeleMessage-Konto. Achten Sie beim Registrieren von Benutzern darauf, die gleiche E-Mail-Adresse zu verwenden, die für ihr Konto Microsoft 365 wird.

- Ihre Mitarbeiter müssen über unternehmenseigene und unternehmensverlässige Mobiltelefone im Mobilfunknetzwerk Bell verfügen. Archivierungsnachrichten in Microsoft 365 für Mitarbeiter oder "Bring Your Own Devices(BYOD)-Geräte" nicht verfügbar.

- Dem Benutzer, der einen Glockennetzwerkconnector erstellt, muss die Rolle Postfachimportexport in der Exchange Online. Dies ist erforderlich, um Connectors auf der Seite **Datenconnectors** im compliance center Microsoft 365 hinzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="create-a-bell-network-connector"></a>Erstellen eines Glockennetzwerkconnector

Der letzte Schritt besteht im Erstellen eines Bell Network-Connectors im Microsoft 365 Compliance Center. Der Connector verwendet die informationen, die Sie bereitstellen, um eine Verbindung mit dem TeleMessage-Standort herzustellen und SMS/MMS-Nachrichten an die entsprechenden Benutzerpostfächer in Microsoft 365.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie dann auf **Datenconnectors**  >  **Bell SMS/MMS Network Archiver**.

2. Klicken Sie **auf der Seite** Produktbeschreibung des Glockennetzwerks auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie **auf der Seite Bei TeleMessage** anmelden unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **Weiter**.

   - **Benutzername:** Ihr TeleMessage-Benutzername.

   - **Kennwort:** Ihr TeleMessage-Kennwort.

5. Nachdem der Connector erstellt wurde, können Sie das Popupfenster schließen und zur nächsten Seite wechseln.

6. Aktivieren Sie **auf der Seite** Benutzerzuordnung die automatische Benutzerzuordnung. Laden Sie zum Aktivieren der benutzerdefinierten Zuordnung eine CSV-Datei hoch, die die Benutzerzuordnungsinformationen enthält, und klicken Sie dann auf **Weiter**.

7. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen,** um den Connector zu erstellen.

8. Wechseln Sie zur **Registerkarte Connectors** auf der Seite **Datenconnectors** im Compliance Center, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
