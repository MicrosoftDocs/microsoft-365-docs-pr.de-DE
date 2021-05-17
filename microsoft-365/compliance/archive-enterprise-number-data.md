---
title: Einrichten eines Connectors zum Archivieren von Daten aus der TeleMessage Enterprise Number Archiver
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
description: Administratoren können einen Connector zum Importieren und Archivieren von SMS und MMS-Daten aus TeleMessage Enterprise Number Archiver einrichten. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 1322cafad94c8b2163c38e3c988feefc4ff1221a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921745"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>Einrichten eines Connectors zum Archivieren Enterprise Nummerndaten

Verwenden Sie einen TeleMessage-Connector im Microsoft 365 Compliance SMS Center, um Nachrichten, Chatnachrichten, Sprachanrufaufzeichnungen und Sprachanrufprotokolle aus dem Enterprise Number Archiver zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, verbindet er sich einmal täglich mit dem TeleMessage-Konto Ihrer Organisation und importiert die mobilen Kommunikationsdaten von Mitarbeitern mithilfe des TeleMessage Enterprise Number Archivers in Postfächer in Microsoft 365.

Nachdem die Daten des TeleMessage Enterprise Number Archiver-Connectors in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie z. B. Das Aufbewahrungsverfahren für Rechtsstreitigkeiten, die Inhaltssuche, In-Place Archivierung, Überwachung, Kommunikationskonformität und Microsoft 365 Aufbewahrungsrichtlinien auf Enterprise Number Archiver-Daten anwenden. Sie können beispielsweise die TeleMessage Enterprise Number Archiver SMS, MMS und Voice Call mithilfe der Inhaltssuche durchsuchen oder das Postfach zuordnen, das die Enterprise Number Archiver-Connectordaten in einem Advanced eDiscovery-Fall enthält. Die Verwendung Enterprise Nummernarchivierungsconnector zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Richtlinien von Behörden und Behörden erfüllt.

## <a name="overview-of-archiving-enterprise-number-data"></a>Übersicht über archivierungs- Enterprise Zahlendaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren Enterprise Netzwerkdaten in Microsoft 365.

![Enterprise Workflow für die Nummernarchivierung](../media/EnterpriseNumberConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage zusammen, um einen Enterprise Number Archiver-Connector zu erstellen. Weitere Informationen finden Sie [hier](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/).

2. Der Enterprise Number Archiver-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der TeleMessage-Website sicher und überträgt die E-Mail-Nachrichten aus den vorherigen 24 Stunden an einen sicheren Azure Storage-Bereich in der Microsoft Cloud.

3. Der Connector importiert die mobilen Kommunikationselemente in das Postfach eines bestimmten Benutzers. Ein neuer Ordner mit Enterprise Nummerarchiver wird im Postfach des bestimmten Benutzers erstellt, und die Elemente werden in das Postfach importiert. Der Connector wird mithilfe des Werts der E-Mail-Adresseigenschaft des *Benutzers zugeordnet.* Jede E-Mail-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der E-Mail-Nachricht gefüllt wird. Neben der automatischen Benutzerzuordnung mithilfe  des Werts der E-Mail-Adresseigenschaft des Benutzers können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei sollte die mobile Nummer des Benutzers und die Microsoft 365 Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird für jedes E-Mail-Element zunächst die benutzerdefinierte Zuordnungsdatei vom Connector angezeigt. Wenn er keinen gültigen Benutzer Microsoft 365, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die E-Mail-Adresseigenschaft des E-Mail-Elements des Benutzers. Wenn der Connector keinen gültigen benutzer Microsoft 365 in der benutzerdefinierten Zuordnungsdatei oder der E-Mail-Adresseigenschaft des Benutzers des E-Mail-Elements findet, wird das Element nicht importiert. 

## <a name="before-you-begin"></a>Bevor Sie beginnen

Einige der Implementierungsschritte, die zum Archivieren Enterprise Nummernarchivierungsdaten erforderlich sind, sind außerhalb von Microsoft 365 und müssen abgeschlossen sein, bevor Sie den Connector im Compliance Center erstellen können.

- Order the [Enterprise Number Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization. Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector im Compliance Center erstellen.

- Registrieren Sie alle Benutzer, Enterprise die SMS/MMS-Netzwerkarchivierung benötigen, im TeleMessage-Konto. Achten Sie beim Registrieren von Benutzern darauf, die gleiche E-Mail-Adresse zu verwenden, die für ihr Konto Microsoft 365 wird.

- Installieren und aktivieren Sie die TeleMessage Enterprise Number Archiver-App auf den Mobiltelefonen Ihrer Mitarbeiter.

- Dem Benutzer, der einen Enterprise Nummerarchivierconnector erstellt, muss die Rolle Postfachimportexport in der Exchange Online. Dies ist erforderlich, um Connectors auf der Seite **Datenconnectors** im compliance center Microsoft 365 hinzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="create-an-enterprise-number-archiver-connector"></a>Erstellen eines Enterprise Nummernarchivierungsconnector

Nachdem Sie die im vorherigen Abschnitt beschriebenen Voraussetzungen erfüllt haben, können Sie einen Enterprise Nummernarchiverconnector im Microsoft 365 erstellen. Der Connector verwendet die informationen, die Sie bereitstellen, um eine Verbindung mit dem TeleMessage-Standort herzustellen und SMS-, MMS- und Sprachanrufnachrichten an die entsprechenden Benutzerpostfächer in Microsoft 365.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors** \> **Enterprise Number Archiver**.

2. Klicken Sie **auf Enterprise Seite "Produktbeschreibung für Nummerarchiver"** auf Connector **hinzufügen.**

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