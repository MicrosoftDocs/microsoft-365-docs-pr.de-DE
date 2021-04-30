---
title: Konfigurieren von Lerninhaltsquellen für Microsoft Viva Learning (Vorschau) im Microsoft 365 Admin Center
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Erfahren Sie, wie Sie Lerninhaltsquellen für Microsoft Viva Learning (Preview) im Microsoft 365 konfigurieren.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a1bbe65db9dee028f57849de8a5538c996c3e2a4
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100973"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a>Konfigurieren von Lerninhaltsquellen für Microsoft Viva Learning (Vorschau) im Microsoft 365 Admin Center

> [!NOTE]
> Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das möglicherweise erheblich geändert wird, bevor es kommerziell veröffentlicht wird. 

Die Administratoren für das Microsoft 365 Admin Center – entweder allein oder durch Zuweisen der Rolle "Wissensadministrator" zu ausgewählten Personen in Ihrer Organisation – können Einstellungen im Zusammenhang mit "Viva Learning" (Vorschau) verwalten und die Lerninhaltsquellen konfigurieren.

Der Administrator wählt aus, welche anderen Lerninhaltsquellen (z. B. SharePoint oder unterstützte Inhaltsanbieterquellen von Drittanbietern) benutzern von Viva Learning (Vorschau) zur Verfügung stehen. Der Administrator konfiguriert dann diese Quellen, um sicherzustellen, dass die Inhalte für die Suche und Ermittlung verfügbar sind und von den Mitarbeitern durchsucht werden können, die "Viva Learning" (Vorschau) verwenden.

> [!NOTE]
>  Benutzer melden sich bei Nicht-Microsoft- und LinkedIn Learning-Pro in einem Browser oder eingebetteten Viewer an. Dieses konfigurierte Lernen unterliegt den separaten Lizenz-, Datenschutz- und Dienstbedingungen zwischen Ihrer Organisation und dem Drittanbieter und nicht den Bedingungen von Viva Learning (Preview). Vergewissern Sie sich vor der Auswahl dieser Art von Lernprozess, dass eine Vereinbarung für Ihre Organisation und Ihre Benutzer vor sich geht.

## <a name="assign-the-knowledge-admin-role-optional"></a>Zuweisen der Rolle "Wissensadministrator" [Optional]

Sie müssen ein globaler Administrator Microsoft 365, um diese Aufgaben ausführen zu können.

> [!TIP]
> Der Wissensadministrator sollte moderat technisch sein und über vorhandene SharePoint Administratoranmeldeinformationen verfügen, vorzugsweise eine Person, die sich mit dem Bildungs-, Lern-, Schulungs- oder Mitarbeitererfahrungsteil der Organisation auskennt.

### <a name="add-a-knowledge-admin"></a>Hinzufügen eines Wissensadministrators

Führen Sie die folgenden Schritte aus, um einen Wissensadministrator für Viva Learning (Preview) hinzuzufügen:

1.  Wechseln Sie in der linken Navigation des Microsoft 365 Admin Center zu **Rollen**.

2.  Wählen Sie **auf der** Seite Rollen auf der Registerkarte **Azure AD** die Option Knowledge **Administrator aus.**
 
3.  Wählen Sie **im Bereich Wissensadministrator** die Option **Zugewiesene Administratoren** aus, und wählen Sie dann Hinzufügen **aus.**

     ![Rollenseite im Microsoft 365 Admin Center mit dem Bereich Wissensadministrator, um einen Benutzer hinzuzufügen.](../media/learning/learning-add-knowledge-admin-1.png)

3.  Wählen Sie **im Bereich** Administrator hinzufügen die Person aus, die Sie für die Rolle auswählen, und wählen Sie dann **Hinzufügen aus.**

     ![Rollenseite im Microsoft 365 Admin Center, auf der der Bereich Administratoren hinzufügen angezeigt wird, um einen Benutzer hinzuzufügen.](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a>Entfernen eines Wissensadministrators

Führen Sie die folgenden Schritte aus, um einen Wissensadministrator für Viva Learning (Preview) zu entfernen:

1.  Wechseln Sie in der linken Navigation des Microsoft 365 Admin Center zu **Rollen**.

2.  Wählen Sie **auf** der Seite Rollen auf der **Registerkarte Azure AD** die Option Knowledge Administrator **aus.**
 
3.  Wählen Sie im Bereich **Wissensadministrator** auf der Registerkarte Zugewiesene **Administratoren** die Option **Entfernen** aus, und wählen Sie dann die Person aus, die Sie aus der Rolle entfernen möchten. Wählen Sie entfernen aus, um dies **zu bestätigen.**

     ![Rollenseite im Microsoft 365 Admin Center mit dem Bereich Zugewiesene Administratoren, um einen Benutzer zu entfernen.](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a>Konfigurieren von Einstellungen für die Lerninhaltsquellen

Sie müssen ein Microsoft 365 oder Wissensadministrator sein, um diese Aufgaben ausführen zu können.

Führen Sie die folgenden Schritte aus, um Einstellungen für Lerninhaltsquellen in Viva Learning zu konfigurieren:

1.  Wechseln Sie in der linken Navigation des Microsoft 365 Admin Center zu **Einstellungen**  >  **Organisationseinstellungen**.

2.  Wählen Sie **auf der** Seite Organisationseinstellungen auf der Registerkarte **Dienste** die Option **Lern-App (Vorschau)** aus.

     ![Einstellungen seite im Microsoft 365 Admin Center mit der aufgelisteten Lern-App.](../media/learning/learning-sharepoint-configure1.png)

3.  Wählen Sie **im Bereich Lern-App (Vorschau)** die Lerninhaltsquellen aus, die Sie für die Organisation konfigurieren möchten, und wählen Sie dann **Speichern aus.**

     ![Lernbereich im Microsoft 365 Admin Center mit Optionen für Inhaltsquellen.](../media/learning/learning-sharepoint-configure2.png)

Unter allen vorhandenen Lernquellen werden einige standardmäßig aktiviert. Zu diesen Lernquellen gehören:

- LinkedIn Learning (kostenloser Inhalt)
- Microsoft Learn
- Microsoft 365 Schulung

> [!NOTE]
> Kostenlose Inhalte von LinkedIn werden Benutzern im Rahmen der LinkedIn-Datenschutzrichtlinien und der Benutzervereinbarung zur Verfügung gestellt. LinkedIn erhält die IP-Adresse des Benutzers, alle zuvor von LinkedIn festgelegten Cookies und setzt ein neues Cookie, um die Verwendung kostenloser Inhalte nachverfolgt zu werden. Benutzer müssen sich nicht mit LinkedIn anmelden, um kostenlose Inhalte zu erhalten.<br><br>
Für LinkedIn Premium-Inhalte benötigt Ihre Organisation ein Abonnement für Ihr Team, um auf diese Inhalte zu zugreifen. Benutzer müssen sich bei LinkedIn anmelden, um auf dieses Lernen zu zugreifen, das unter den Bedingungen der Nutzungsbedingungen Ihrer Organisation und der Benutzer mit LinkedIn bereitgestellt wird.<br><br> Stellen Sie für Nicht-Microsoft-Inhalte (mit Ausnahme von kostenlosen LinkedIn-Inhalten) sicher, dass Ihre Organisation über ein Abonnement verfügt, mit dem Ihre Benutzer über ein Arbeitskonto auf diese Inhalte zugreifen können, bevor Sie eine Verbindung mit Viva Learning (Vorschau) herstellen. Die persönlichen Abonnements von Benutzern bei Nicht-Microsoft-Lernanbietern werden nicht in Viva Learning (Preview) integriert. Benutzer melden sich bei Nicht-Microsoft- und LinkedIn Learning-Pro in einem Browser oder eingebetteten Viewer an. Wenn Benutzer zu Inhalten navigieren, für die sie kein Organisationsabonnement haben, wird möglicherweise eine Anbieterseite angezeigt, auf der sie sich für ein einzelnes Abonnement registrieren können. Alle Nicht-Microsoft-Lernprozesse werden unter den Bedingungen des Nicht-Microsoft-Anbieters und nicht als Teil von Viva Learning bereitgestellt. 

Um eine Lerninhaltsquelle zu aktivieren oder zu deaktivieren, aktivieren Sie das Kontrollkästchen neben der Quelle. Wenn eine Quelle aktiviert ist, wird ein Häkchen angezeigt.

## <a name="third-party-content-providers"></a>Inhaltsanbieter von Drittanbietern 

Der Satz der verfügbaren verbundenen Lernanbieter kann sich jederzeit ändern. Wenn das Programm wächst, werden weitere Anbieter beitreten. Verfügbare Anbieter können auch ihre Verbindung mit Viva Learning (Preview) beenden.

### <a name="skillsoft-as-a-content-source"></a>Skillsoft als Inhaltsquelle  

Für Viva Learning (Preview) landen Benutzer, die Skillsoft aktiviert haben und skillsoft-Inhalte anzeigen möchten, auf einer Percipio-Seite, auf der sie zur Eingabe des Percipio-Websitenamens Ihrer Organisation gefragt werden. Nachdem Benutzer den Websitenamen Ihrer Organisation eingegeben haben, werden sie zur Seite weitergeleitet, um sich bei der Percipio-Website Ihrer Organisation zu registrieren. Benutzer melden sich mit ihren vorhandenen Anmeldeinformationen an und sehen die inhalte, die sie ursprünglich ausgewählt haben. Benutzer werden aufgefordert, den Namen der Percipio-Website nur einmal ein eingaben, bis der Browsercache gelöscht ist. Um diese Benutzererfahrung zu optimieren, empfehlen wir, Ihren Percipio-Websitenamen in die interne Kommunikation ein, die Sie zu Viva Learning (Vorschau) senden.

Dies soll eine temporäre Vorschauerfahrung sein, und wir arbeiten mit Skillsoft zusammen, um die mandantenspezifische Integration für die allgemeine Verfügbarkeit zu ermöglichen, wodurch der Schritt umgangen wird, bei dem Benutzer den Percipio-Websitenamen Ihrer Organisation bereitstellen müssen. 

### <a name="details-on-microsoft-substrate"></a>Details zum Microsoft-Substrate  

Für Daten, die Sie aus einem Nicht-Microsoft-Dienst (Lernanbieter oder Lernverwaltungssystem) in Viva Learning (Vorschau) kopieren, können Sie diese Daten in Viva Learning (Vorschau) nicht direkt extrahieren, korrigieren oder löschen. Wir aktualisieren die von Nicht-Microsoft-Anbietern importierten Daten prompt, um Änderungen und Löschungen in den Nicht-Microsoft-Quelldaten widerspiegeln zu können.

Sie müssen mit dem Lieferanten des Nicht-Microsoft-Diensts zusammenarbeiten, um auf Daten zu zugreifen, sie zu korrigieren, zu löschen oder zu extrahieren, die unter den Lizenz-, Dienst- oder Datenschutzbedingungen des Nicht-Microsoft-Diensts enthalten sind. Die dort vorgenommenen Änderungen werden in den Daten widergespiegelt, die für Ihre Verwendung in Viva Learning (Preview) nach Abschluss der Datenaktualisierungszyklen des Nicht-Microsoft-Diensts und von Viva Learning (Preview) verarbeitet wurden. Wenn Sie die Verbindung zwischen Viva Learning (Preview) und einem Nicht-Microsoft-Dienst deaktivieren, werden alle Daten, die Sie zuvor aus diesem Dienst importiert haben, gelöscht. 

## <a name="next-step"></a>Nächster Schritt

[Konfigurieren SharePoint als Lerninhaltsquelle für Microsoft Viva Learning (Vorschau)](configure-sharepoint-content-source.md)