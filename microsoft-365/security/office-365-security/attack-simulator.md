---
title: Angriffssimulator in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Als Office 365 globaler Administrator können Sie mit dem Angriffs Simulator realistische Angriffsszenarien in Ihrer Organisation ausführen. Dies kann Sie dabei unterstützen, gefährdete Benutzer zu identifizieren und zu finden, bevor ein echter Angriff auf Ihr Unternehmen trifft.
ms.openlocfilehash: e5f304a7c706875216c58330b1225d341b2b59df
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971933"
---
# <a name="attack-simulator-in-office-365"></a>Angriffssimulator in Office 365

**Zusammenfassung** Wenn Sie ein Office 365 globaler Administrator oder Sicherheitsadministrator sind und Ihre Organisation Office 365 Advanced Threat Protection Plan 2, einschließlich der Funktionen zur [Ermittlung und Reaktion von Bedrohungen](office-365-ti.md), verwendet, können Sie mit dem Angriffs Simulator realistische Angriffsszenarien in Ihrer Organisation ausführen. Auf diese Weise können Sie Benutzer mit Sicherheitslücken leichter identifizieren und finden, bevor ein echter Angriff passiert. Lesen Sie diesen Artikel, um mehr zu erfahren.

## <a name="the-attacks"></a>Die Angriffe

Derzeit stehen drei Arten von Angriffssimulationen zur Verfügung:

- [Speer-Phishing-Angriff (Anzeigename)](#display-name-spear-phishing-attack)

- [Kennwort-Spray-Angriff](#password-spray-attack)

- [Brute-Force-Kennwortangriff](#brute-force-password-attack)

Damit ein Angriff erfolgreich gestartet werden kann, müssen Sie sicherstellen, dass das Konto, mit dem Simulierte Angriffe ausgeführt werden, die mehrstufige Authentifizierung verwendet. Darüber hinaus müssen Sie ein Office 365 globaler Administrator oder Sicherheitsadministrator sein. (Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Office 365 Security #a0 Compliance Center](permissions-in-the-security-and-compliance-center.md).)

Um auf &amp; den Angriffs Simulator zuzugreifen, wählen Sie im Security Compliance Center **Threat Management** \> **Attack Simulator**aus.

## <a name="before-you-begin"></a>Bevor Sie beginnen...

Stellen Sie sicher, dass Sie und Ihre Organisation die folgenden Anforderungen für den Angriffs Simulator erfüllen:

- Die e-Mail-Adresse Ihrer Organisation wird in Exchange Online gehostet. (Der Angriffs Simulator steht für lokale e-Mail-Server nicht zur Verfügung.)

- Sie sind ein Office 365 globaler Administrator oder Sicherheitsadministrator

- [Mehrstufige Authentifizierung/bedingter Zugriff](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) ist aktiviert, für mindestens das Office 365 globales Administratorkonto und Sicherheitsadministratoren, die den Angriffs Simulator verwenden werden. (Im Idealfall ist mehrstufige Authentifizierung/bedingter Zugriff für alle Benutzer in Ihrer Organisation aktiviert.)

- Ihre Organisation verfügt über [Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), in dem der Angriffs &amp; Simulator im Security Compliance Center sichtbar ist (zu **Threat Management** \> **Attack Simulator**wechseln).

    ![Threat Management – Angriffs Simulator](../media/ThreatMgmt-AttackSimulator.png)

## <a name="display-name-spear-phishing-attack"></a>Spear-Phishing-Angriff (Anzeigename)

Phishing ist ein generischer Ausdruck für eine große Sammlung von Angriffen, die als Angriffs für soziale Technik bezeichnet werden. Dieser Angriff konzentriert sich auf Speer-Phishing, einen gezielteren Angriff, der auf eine bestimmte Gruppe von Personen oder eine Organisation abzielt. Normalerweise wird ein benutzerdefinierter Angriff mit einiger Aufklärung durchgeführt und ein Anzeigename verwendet, der eine Vertrauensstellung für den Empfänger generiert, beispielsweise eine e-Mail-Nachricht, die aussieht, als käme sie von einer Führungskraft in Ihrer Organisation.

Dieser Angriff konzentriert sich darauf, dass Sie den Anzeigenamen und die Quelladresse ändern können, aus dem die Nachricht anscheinend entstanden ist. Wenn Speer-Phishing-Angriffe erfolgreich sind, erhalten cyberattackers Zugriff auf die Anmeldeinformationen von Benutzern.

### <a name="to-simulate-a-spear-phishing-attack"></a>So simulieren Sie einen Speer-Phishing-Angriff

![E-Mail-Textkörper erstellen](../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

Sie können den Rich-HTML-Editor direkt im Feld **e-Mail-Textkörper** selbst oder mit HTML-Quelle arbeiten.

1. Wählen Sie [im &amp; Security Compliance Center](https://protection.office.com) **Threat Management** \> **Attack Simulator**aus.

2. Geben Sie einen aussagekräftigen Kampagnennamen für den Angriff an, oder wählen Sie eine Vorlage aus.

   ![Phishing-Start Seite](../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

3. Geben Sie die Zielempfänger an. Hierbei kann es sich um Einzelpersonen oder Gruppen in Ihrer Organisation handeln. Jeder Zielempfänger muss über ein Exchange Online Postfach verfügen, damit der Angriff erfolgreich verläuft.

   ![Empfängerauswahl](../media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)

4. Konfigurieren Sie die Phishing-e-Mail-Details.

   ![Konfigurieren von e-Mail-Details](../media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)

   Die HTML-Formatierung kann so komplex oder einfach sein, wie Ihre Kampagne benötigt. Da das e-Mail-Format HTML ist, können Sie Bilder und Text einfügen, um die Glaubwürdigkeit erhöhen zu verbessern. Sie haben die Kontrolle darüber, wie die empfangene Nachricht im empfangenden e-Mail-Client aussehen wird.

5. Geben Sie den Text für das Feld **from (Name)** an. Dies ist das Feld, das im empfangenden e-Mail-Client im **Anzeigenamen** angezeigt wird.

6. Geben Sie Text oder das Feld **von** an. Dies ist das Feld, das als e-Mail-Adresse des Absenders im empfangenden e-Mail-Client angezeigt wird.

   Sie können in Ihrer Organisation einen vorhandenen e-Mail-Namespace eingeben (Dadurch wird die e-Mail-Adresse tatsächlich im empfangenden Client aufgelöst, wodurch ein sehr hohes Vertrauensmodell erleichtert wird), oder Sie können eine externe e-Mail-Adresse eingeben. Die angegebene e-Mail-Adresse muss nicht tatsächlich vorhanden sein, Sie muss jedoch dem Format einer gültigen SMTP-Adresse wie `user@domainname.extension`.

7. Wählen Sie mithilfe der Dropdownauswahl eine URL für den Phishing-Anmeldeserver aus, die die Art der Inhalte widerspiegelt, die Sie in ihrem Angriff haben werden. Es werden mehrere Themen-URLs bereitgestellt, aus denen Sie auswählen können, beispielsweise Dokumentzustellung, technische, Lohnbuchhaltung usw. Dies ist effektiv die URL, auf die Zielbenutzer klicken müssen.

8. Geben Sie eine benutzerdefinierte URL für die Zielseiten an. Mit dieser Methode werden Benutzer zu einer URL umgeleitet, die Sie am Ende eines erfolgreichen Angriffs angegeben haben. Wenn Sie beispielsweise ein internes Bewusstseinstraining haben, können Sie dies hier angeben.

9. Geben Sie den Text für das Feld **Betreff** an. Dies ist das Feld, das als **Antragsteller Name** im empfangenden e-Mail-Client angezeigt wird.

10. Erstellen Sie den **e-Mail-Text** , den das Ziel empfangen soll.

    `${username}`Fügt den Namen Targets in den e-Mail-Text ein.

    `${loginserverurl}`Fügt die URL ein, auf die die Zielbenutzer klicken sollen.

11. Klicken Sie auf **weiter und** anschließend auf **Fertig stellen** , um den Angriff zu starten. Die Phishing-e-Mail-Nachricht wird an die Postfächer ihrer Zielempfänger übermittelt.

## <a name="password-spray-attack"></a>Kennwort-Spray-Angriff

Ein Kenn Wort Sprüh Angriff auf eine Organisation wird in der Regel verwendet, nachdem ein schlechter Akteur eine Liste gültiger Benutzer aus dem Mandanten erfolgreich erworben hat. Der fehlerhafte Akteur weiß um häufige Kennwörter, die von Benutzern verwendet werden. Dies ist ein weit verbreiteter Angriff, da es sich um einen günstigen Angriff handelt und schwerer zu erkennen ist als Brute-Force-Ansätze.

Dieser Angriff konzentriert sich darauf, dass Sie ein gemeinsames Kennwort für eine große Zieldatenbank von Benutzern angeben können.

### <a name="to-simulate-a-password-spray-attack"></a>So simulieren Sie einen Kenn Wort Sprüh Angriff

1. Wählen Sie [im &amp; Security Compliance Center](https://protection.office.com) **Threat Management** \> **Attack Simulator**aus.

2. Geben Sie einen aussagekräftigen Kampagnennamen für den Angriff an.

3. Geben Sie die Zielempfänger an. Hierbei kann es sich um Einzelpersonen oder Gruppen in Ihrer Organisation handeln. Ein Zielempfänger muss über ein Exchange Online Postfach verfügen, damit der Angriff erfolgreich verläuft.

4. Geben Sie ein Kennwort an, das für den Angriff verwendet werden soll. Beispielsweise ist ein gemeinsames, relevantes Kennwort, das `Summer2019`Sie ausprobieren können. Ein anderer könnte `Fall2019`sein, `Password1`oder.

5. Wählen Sie **Fertig stellen** aus, um den Angriff zu starten.

## <a name="brute-force-password-attack"></a>Brute-Force-Kennwortangriff

Ein Brute-Force-Kennwortangriff auf eine Organisation wird in der Regel verwendet, nachdem ein schlechter Akteur erfolgreich eine Liste mit wichtigen Benutzern aus dem Mandanten abgerufen hat. Dieser Angriff konzentriert sich auf das Ausprobieren einer Gruppe von Kennwörtern für das Konto eines einzelnen Benutzers.

### <a name="to-simulate-a-brute-force-password-attack"></a>So simulieren Sie einen Brute-Force-Kennwortangriff

1. Wählen Sie [im &amp; Security Compliance Center](https://protection.office.com) **Threat Management** \> **Attack Simulator**aus.

2. Geben Sie einen aussagekräftigen Kampagnennamen für den Angriff an.

3. Geben Sie den Zielempfänger an. Ein Zielempfänger muss über ein Exchange Online Postfach verfügen, damit der Angriff erfolgreich verläuft.

4. Geben Sie eine Gruppe von Kennwörtern an, die für den Angriff verwendet werden sollen. Zu diesem Zweck können Sie eine Textdatei (txt-Datei) für die Liste der Kennwörter verwenden. Die Textdatei darf die Dateigröße von 10 MB nicht überschreiten. Verwenden Sie ein Kennwort pro Zeilen, und stellen Sie sicher, dass Sie nach dem letzten Kennwort in Ihrer Liste eine harte Rückgabe einschließen.

5. Wählen Sie **Fertig stellen** aus, um den Angriff zu starten.

## <a name="new-features-in-attack-simulator"></a>Neue Features in Attack Simulator

Neue Features wurden kürzlich dem Angriffs Simulator hinzugefügt. Zu diesen zählen:

- Erweiterte Berichtsfunktionen. Die Möglichkeit, Daten wie die schnellste (oder langsamste) Zeit anzuzeigen, um eine e-Mail-Nachricht zur Angriffssimulation zu öffnen, die schnellste (oder langsamste) Zeit zum Klicken auf einen Link in der Nachricht und weitere Visualisierungen.

- E-Mail-Vorlageneditor. Die Möglichkeit zum Erstellen einer benutzerdefinierten, wiederverwendbaren e-Mail-Vorlage, die Sie für zukünftige Angriffssimulationen verwenden können.

- CSV-Empfänger Import. Die Möglichkeit, eine CSV-Datei zu verwenden, um Ihre Zielempfänger Liste zu importieren, anstatt die Adressbuch Auswahl zu verwenden.

Weitere neue Features kommen in Kürze zum Angriff Simulator. Zu diesen zählen:

- Phishing-Simulation für Anlagen Nutzlast. Die Möglichkeit, eine Anlage als Nutzlast für die Phishing-Simulation anstelle einer URL zu verwenden.

Besuchen Sie die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap) , um zu sehen, was sich in der Entwicklung befindet, was sich ausrollt und was bereits gestartet wurde.

## <a name="see-also"></a>Siehe auch

[Office 365 Advanced Threat Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[Office 365 Advanced Threat Protection](office-365-atp.md)
