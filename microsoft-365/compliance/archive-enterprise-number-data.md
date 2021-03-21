---
title: Einrichten eines Connectors zum Archivieren von Daten aus dem TeleMessage Enterprise Number Archiver
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
description: Administratoren können einen Connector zum Importieren und Archivieren von SMS- und MMS-Daten aus dem TeleMessage Enterprise Number Archiver einrichten. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, damit Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 1322cafad94c8b2163c38e3c988feefc4ff1221a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921745"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>Einrichten eines Connectors zum Archivieren von Unternehmensnummerdaten

Verwenden Sie einen TeleMessage-Connector im Microsoft 365 Compliance Center zum Importieren und Archivieren von Sms- und MmS-Nachrichten (Multimedia Messaging Service), Chatnachrichten, Sprachanrufaufzeichnungen und Sprachanrufprotokollen aus dem Enterprise Number Archiver. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, verbindet er sich einmal täglich mit dem TeleMessage-Konto Ihrer Organisation und importiert die mobilen Kommunikationsdaten von Mitarbeitern, die das TeleMessage Enterprise Number Archiver verwenden, in Postfächer in Microsoft 365.

Nachdem die Daten des TeleMessage Enterprise Number Archiver-Connectors in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. Das Aufbewahrungsverfahren für Rechtsstreitigkeiten, die Inhaltssuche, In-Place-Archivierung, Überwachung, Kommunikationskonformität und Microsoft 365-Aufbewahrungsrichtlinien auf Enterprise Number Archiver-Daten anwenden. Sie können beispielsweise die TeleMessage Enterprise Number Archiver SMS, MMS und Voice Call mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die Daten des Enterprise Number Archiver-Connectors enthält, einem Custodian in einem Advanced eDiscovery-Fall zuordnen. Die Verwendung eines Enterprise Number Archiver-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Behördlichen und behördlichen Richtlinien einhalten kann.

## <a name="overview-of-archiving-enterprise-number-data"></a>Übersicht über die Archivierung von Enterprise Number-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Unternehmensnetzwerkdaten in Microsoft 365 erläutert.

![Enterprise Number-Archivierungsworkflow](../media/EnterpriseNumberConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage zusammen, um einen Enterprise Number Archiver-Connector zu einrichten. Weitere Informationen finden Sie [hier](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/).

2. Der im Microsoft 365 Compliance Center erstellte Enterprise Number Archiver-Connector stellt täglich eine Verbindung mit der TeleMessage-Website bereit und überträgt die E-Mail-Nachrichten aus den vorherigen 24 Stunden an einen sicheren Azure Storage-Bereich in der Microsoft Cloud.

3. Der Connector importiert die mobilen Kommunikationselemente in das Postfach eines bestimmten Benutzers. Im Postfach des jeweiligen Benutzers wird ein neuer Ordner mit dem Namen Enterprise Number Archiver erstellt, in den die Elemente importiert werden. Der Connector wird mithilfe des Werts der E-Mail-Adresseigenschaft des *Benutzers zugeordnet.* Jede E-Mail-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der E-Mail-Nachricht gefüllt wird. Neben der automatischen Benutzerzuordnung mithilfe  des Werts der E-Mail-Adresseigenschaft des Benutzers können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei sollte die mobile Nummer des Benutzers und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird für jedes E-Mail-Element zunächst die benutzerdefinierte Zuordnungsdatei vom Connector angezeigt. Wenn er keinen gültigen Microsoft 365-Benutzer findet, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die E-Mail-Adresseigenschaft des E-Mail-Elements des Benutzers. Wenn der Connector keinen gültigen Microsoft 365-Benutzer in der  benutzerdefinierten Zuordnungsdatei oder der E-Mail-Adresseigenschaft des Benutzers des E-Mail-Elements findet, wird das Element nicht importiert.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Einige der Implementierungsschritte, die zum Archivieren von Enterprise Number Archiver-Daten erforderlich sind, sind außerhalb von Microsoft 365 und müssen abgeschlossen sein, bevor Sie den Connector im Compliance Center erstellen können.

- Order the [Enterprise Number Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization. Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector im Compliance Center erstellen.

- Registrieren Sie alle Benutzer, für die die Enterprise Number SMS/MMS Network-Archivierung erforderlich ist, im TeleMessage-Konto. Verwenden Sie bei der Registrierung von Benutzern die gleiche E-Mail-Adresse, die für ihr Microsoft 365-Konto verwendet wird.

- Installieren und aktivieren Sie die TeleMessage Enterprise Number Archiver-App auf den Mobiltelefonen Ihrer Mitarbeiter.

- Dem Benutzer, der einen Enterprise Number Archiver-Connector erstellt, muss die Rolle Postfachimportexport in Exchange Online zugewiesen werden. Dies ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="create-an-enterprise-number-archiver-connector"></a>Erstellen eines Enterprise Number Archiver-Connectors

Nachdem Sie die im vorherigen Abschnitt beschriebenen Voraussetzungen erfüllt haben, können Sie einen Enterprise Number Archiver-Connector im Microsoft 365 Compliance Center erstellen. Der Connector verwendet die informationen, die Sie bereitstellen, um eine Verbindung mit dem TeleMessage-Standort herzustellen und SMS-, MMS- und Sprachanrufnachrichten an die entsprechenden Benutzerpostfächer in Microsoft 365 zu übertragen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors** \> **Enterprise Number Archiver**.

2. Klicken Sie **auf der Seite Enterprise Number Archiver-Produktbeschreibung** auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie **auf der Seite Bei TeleMessage** anmelden unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **Weiter**.

   - **Benutzername:** Ihr TeleMessage-Benutzername.

   - **Kennwort:** Ihr TeleMessage-Kennwort.

5. Nachdem der Connector erstellt wurde, können Sie das Popupfenster schließen und zur nächsten Seite wechseln.

6. Aktivieren Sie **auf der Seite** Benutzerzuordnung die automatische Benutzerzuordnung. Laden Sie zum Aktivieren der benutzerdefinierten Zuordnung eine CSV-Datei hoch, die die Benutzerzuordnungsinformationen enthält, und klicken Sie dann auf **Weiter**.

7. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen,** um den Connector zu erstellen.

8. Wechseln Sie auf der Seite **Datenconnectors** zur Registerkarte Connectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.