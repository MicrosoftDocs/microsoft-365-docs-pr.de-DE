---
title: Einrichten eines Connectors zum Archivieren von Verizon-Netzwerkdaten in Microsoft 365
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
description: Administratoren können einen TeleMessage-Connector einrichten, um SMS- und MMS-Daten aus dem Verizon Network in Microsoft 365 zu importieren und zu archivieren. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, damit Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: d73b501fccac9f0f400a267a158379271f0f0d14
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924291"
---
# <a name="set-up-a-connector-to-archive-verizon-network-data"></a>Einrichten eines Connectors zum Archivieren von Verizon-Netzwerkdaten

Verwenden Sie den TeleMessage-Connector im Microsoft 365 Compliance Center, um Short Messaging Service (SMS) und MmS-Daten (Multimedia Messaging Service) aus Verizon Network zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er einmal täglich eine Verbindung mit dem Verizon Network Ihrer Organisation und importiert SMS- und MMS-Daten in Postfächer in Microsoft 365.

Nachdem Verizon-Netzwerkconnectordaten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie das Rechtsstreitigkeiten, die Inhaltssuche und Microsoft 365-Aufbewahrungsrichtlinien auf Verizon-Daten anwenden. Sie können z. B. Verizon-SMS- und MMS-Nachrichten mithilfe der Inhaltssuche durchsuchen oder das Postfach, das Verizon-Netzwerkdaten enthält, einem Custodian in einem Advanced eDiscovery-Fall zuordnen. Die Verwendung eines Verizon-Netzwerkconnector zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Behördlichen und behördlichen Richtlinien einhalten kann.

## <a name="overview-of-archiving-verizon-network-data"></a>Übersicht über die Archivierung von Verizon-Netzwerkdaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Verizon-Netzwerkdaten in Microsoft 365 erläutert.

![Verizon Network-Archivierungsworkflow](../media/VerizonNetworkConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage und Verizon zusammen, um einen Verizon-Netzwerkconnector zu einrichten. Weitere Informationen finden Sie unter [Verizon Network Archiver](https://www.telemessage.com/office365-activation-for-verizon-network-archiver/).

2. Alle 24 Stunden werden SMS- und MMS-Nachrichten aus dem Verizon Network Ihrer Organisation auf die TeleMessage-Website kopiert.

3. Der verizon-Netzwerkconnector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit dem TeleMessage-Standort bereit und überträgt die SMS- und MMS-Nachrichten aus den vorherigen 24 Stunden an einen sicheren Azure Storage-Speicherort in der Microsoft Cloud. Der Connector konvertiert auch den Inhalt von SMS- und MMS-Nachrichten in ein E-Mail-Nachrichtenformat.

4. Der Connector importiert die mobilen Kommunikationselemente in das Postfach eines bestimmten Benutzers. Im Postfach des jeweiligen Benutzers wird ein neuer Ordner mit dem Namen **Verizon SMS/MMS Network Archiver** erstellt, in den die Elemente importiert werden. Der Connector führt diese Zuordnung mithilfe des Werts der E-Mail-Adresseigenschaft *des Benutzers* aus. Jede SMS- und MMS-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der Nachricht aufgefüllt wird.

   Neben der automatischen Benutzerzuordnung mithilfe  des Werts der E-Mail-Adresseigenschaft des Benutzers können Sie auch benutzerdefinierte Zuordnungen implementieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei enthält die Mobiltelefonnummer und die entsprechende Microsoft 365-E-Mail-Adresse für Benutzer in Ihrer Organisation. Wenn Sie sowohl die automatische Benutzerzuordnung als auch die benutzerdefinierte Zuordnung aktivieren, betrachtet der Connector zunächst für jedes Verizon-Element die benutzerdefinierte Zuordnungsdatei. Wenn er keinen gültigen Microsoft 365-Benutzer findet, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die Werte in der E-Mail-Adresseigenschaft des Elements, das importiert werden soll. Wenn der Connector keinen gültigen Microsoft 365-Benutzer in der benutzerdefinierten Zuordnungsdatei oder in der E-Mail-Adresseigenschaft des Verizon-Elements findet, wird das Element nicht importiert.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Einige der Implementierungsschritte, die zum Archivieren von Verizon-Netzwerkdaten erforderlich sind, sind außerhalb von Microsoft 365 und müssen abgeschlossen sein, bevor Sie einen Connector im Compliance Center erstellen können.

- Bestellen Sie [den Verizon Network Archiver-Dienst bei TeleMessage,](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) und erhalten Sie ein gültiges Verwaltungskonto für Ihre Organisation. Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector im Compliance Center erstellen.

- Rufen Sie Ihre Verizon Network-Konto- und Abrechnungskontaktdetails ab, damit Sie die TeleMessage-Onboardingformulare ausfüllen und den Nachrichtenarchivierungsdienst bei Verizon bestellen können.

- Registrieren Sie alle Benutzer, die eine Verizon SMS- und MMS-Archivierung erfordern, im TeleMessage-Konto. Verwenden Sie bei der Registrierung von Benutzern die gleiche E-Mail-Adresse, die für ihr Microsoft 365-Konto verwendet wird.

- Ihre Mitarbeiter müssen über unternehmenseigene und unternehmensverlässige Mobiltelefone im Verizon-Mobilfunknetz verfügen. Archivierungsnachrichten in Microsoft 365 sind nicht für Geräte im Besitz von Mitarbeitern oder Bring Your Own Devices (BYOD) verfügbar.

- Dem Benutzer, der einen Verizon-Netzwerkconnector erstellt, muss die Rolle Postfachimportexport in Exchange Online zugewiesen werden. Dies ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="create-a-verizon-network-connector"></a>Erstellen eines Verizon-Netzwerkconnector

Nachdem Sie die im vorherigen Abschnitt beschriebenen Voraussetzungen erfüllt haben, können Sie verizon Network connector im Microsoft 365 Compliance Center erstellen. Der Connector verwendet die informationen, die Sie bereitstellen, um eine Verbindung mit dem TeleMessage-Standort herzustellen und SMS- und MMS-Nachrichten an die entsprechenden Benutzerpostfächer in Microsoft 365 zu übertragen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie dann auf **Datenconnectors**  >  **Verizon Network**.

2. Klicken Sie **auf der Seite Produktbeschreibung für Verizon Network** auf Connector **hinzufügen.**

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