---
title: Konfigurieren von Lerninhaltsquellen für Microsoft Viva Learning (Vorschau) im Microsoft 365 Admin Center
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Erfahren Sie, wie Sie Lerninhaltsquellen für Microsoft Viva Learning (Vorschau) im Microsoft 365 Admin Center konfigurieren.
ms.openlocfilehash: ac9ec6196f758d3ed02d3a102fef80b8a7adeeaa
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288923"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a>Konfigurieren von Lerninhaltsquellen für Microsoft Viva Learning (Vorschau) im Microsoft 365 Admin Center

> [!NOTE]
> Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das vor der kommerziellen Veröffentlichung erheblich geändert werden kann. 

Die Administratoren für die Microsoft 365 Admin Center können Einstellungen im Zusammenhang mit Viva Learning (Vorschau) verwalten und die Lerninhaltsquellen konfigurieren, indem sie die Rolle des Wissensadministrators ausgewählten Personen in Ihrer Organisation zuweisen.

Der Administrator wählt aus, welche anderen Lerninhaltsquellen (z. B. SharePoint oder unterstützte Drittanbieter-Inhaltsquellen) für Benutzer von Viva Learning (Vorschau) zur Verfügung stehen. Der Administrator konfiguriert dann diese Quellen, um sicherzustellen, dass der Inhalt für die Suche und Ermittlung verfügbar ist, und kann von den Mitarbeitern durchsucht werden, die Viva Learning (Vorschau) verwenden.

> [!NOTE]
>  Benutzer melden sich bei Nicht-Microsoft- und LinkedIn-Learning Pro Lernen in einem Browser oder eingebetteten Viewer an. Dieses konfigurierte Lernen unterliegt den separaten Lizenz-, Datenschutz- und Servicebedingungen zwischen Ihrer Organisation und dem Drittanbieter und nicht den Bedingungen für Viva Learning (Vorschau). Bevor Sie diese Art von Lernen auswählen, überprüfen Sie, ob Sie über einen Vertrag für Ihre Organisation und Ihre Benutzer verfügen.

## <a name="assign-the-knowledge-admin-role-optional"></a>Zuweisen der Rolle "Wissensadministrator" (optional)

Sie müssen ein Microsoft 365 globaler Administrator sein, um diese Aufgaben ausführen zu können.

> [!TIP]
> Der Wissensadministrator sollte moderat technisch sein und über vorhandene SharePoint Administratoranmeldeinformationen verfügen, vorzugsweise eine Person, die mit dem Bildungs-, Lern-, Schulungs- oder Mitarbeitererfahrungsteil der Organisation vertraut ist.

### <a name="add-a-knowledge-admin"></a>Hinzufügen eines Wissensadministrators

Führen Sie die folgenden Schritte aus, um einen Wissensadministrator für Viva Learning (Vorschau) hinzuzufügen:

1. Wechseln Sie im linken Navigationsbereich des Microsoft 365 Admin Center zu **"Rollen".**

2. Wählen Sie auf der Seite **"Rollen"** auf der Registerkarte **"Azure AD"** die Option **"Wissensadministrator"** aus.
 
3. Wählen Sie im Bereich **"Wissensadministrator"** die Option **"Zugewiesene Administratoren"** und dann **"Hinzufügen"** aus.

     ![Seite "Rollen" im Microsoft 365 Admin Center mit dem Bereich "Wissensadministrator" zum Hinzufügen eines Benutzers.](../media/learning/learning-add-knowledge-admin-1.png)

3. Wählen Sie im Bereich **"Administratoren hinzufügen"** die Person aus, die Sie für die Rolle auswählen, und wählen Sie dann **"Hinzufügen"** aus.

     ![Seite "Rollen" im Microsoft 365 Admin Center mit dem Bereich "Administratoren hinzufügen" zum Hinzufügen eines Benutzers.](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a>Entfernen eines Wissensadministrators

Gehen Sie folgendermaßen vor, um einen Wissensadministrator für Viva Learning (Vorschau) zu entfernen:

1. Wechseln Sie im linken Navigationsbereich des Microsoft 365 Admin Center zu **"Rollen".**

2. Wählen Sie auf der Seite **"Rollen"** auf der Registerkarte **"Azure AD"** die Option **"Wissensadministrator"** aus.
 
3. Wählen Sie im Bereich **"Wissensadministrator"** auf der Registerkarte **"Zugewiesene Administratoren"** die Option **"Entfernen"** aus, und wählen Sie dann die Person aus, die Sie aus der Rolle entfernen möchten. Um zu bestätigen, wählen Sie **Entfernen** aus.

     ![Seite "Rollen" im Microsoft 365 Admin Center mit dem Bereich "Zugewiesene Administratoren" zum Entfernen eines Benutzers.](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a>Konfigurieren von Einstellungen für die Lerninhaltsquellen

Sie müssen ein Microsoft 365 globaler Administrator oder Wissensadministrator sein, um diese Aufgaben ausführen zu können.

Gehen Sie folgendermaßen vor, um Einstellungen für Lerninhaltsquellen in Viva Learning zu konfigurieren:

1. Wechseln Sie im linken Navigationsbereich des Microsoft 365 Admin Center zu **Einstellungen**  >  **Organisationseinstellungen.**

2. Wählen Sie auf der Seite **"Organisationseinstellungen"** auf der Registerkarte **"Dienste"** **viva Learning (Vorschau)** aus.

     ![Einstellungen Seite im Microsoft 365 Admin Center, auf der die Learning-App aufgeführt ist.](../media/learning/learning-sharepoint-configure1.png)

3. Wählen Sie im **Bereich "Viva Learning (Vorschau)** die Lerninhaltsquellen aus, die Sie für die Organisation konfigurieren möchten, und wählen Sie dann **Speichern** aus.

     ![Learning Bereich im Microsoft 365 Admin Center, in dem Optionen für Inhaltsquellen angezeigt werden.](../media/learning/learning-sharepoint-configure2.png)

Unter allen vorhandenen Lernquellen sind einige standardmäßig aktiviert. Zu diesen Lernquellen gehören:

- LinkedIn Learning (kostenloser Inhalt)
- Microsoft Learn
- Microsoft 365 Ausbildung

> [!NOTE]
> LinkedIn-kostenlose Inhalte werden Benutzern unter den LinkedIn-Datenschutzrichtlinien und der Benutzervereinbarung bereitgestellt. LinkedIn empfängt die IP-Adresse des Benutzers, alle zuvor von LinkedIn festgelegten Cookies und legt ein neues Cookie fest, um die Verwendung kostenloser Inhalte nachzuverfolgen. Benutzer müssen sich nicht mit LinkedIn anmelden, um kostenlose Inhalte zu erhalten.<br><br>
Für LinkedIn Premium-Inhalte benötigt Ihre Organisation ein Abonnement, damit Ihr Team auf diese Inhalte zugreifen kann. Benutzer müssen sich bei LinkedIn anmelden, um auf dieses Lernen zuzugreifen, das unter den Bedingungen der Nutzungsbedingungen Ihrer Organisation und der Benutzer mit LinkedIn bereitgestellt wird.<br><br> Stellen Sie für Nicht-Microsoft-Inhalte (mit Ausnahme kostenloser LinkedIn-Inhalte) sicher, dass Ihre Organisation über ein Abonnement für Ihre Benutzer verfügt, um mithilfe eines Geschäftskontos auf diese Inhalte zuzugreifen, bevor Sie sie mit Viva Learning (Vorschau) verbinden. Persönliche Abonnements von Benutzern für Nicht-Microsoft-Lernanbieter werden nicht in Viva Learning (Vorschau) integriert. Benutzer melden sich bei Nicht-Microsoft- und LinkedIn-Learning Pro Lernen in einem Browser oder eingebetteten Viewer an. Wenn Benutzer zu Inhalten navigieren, für die sie kein Organisationsabonnement haben, wird möglicherweise eine Anbieterseite angezeigt, auf der sie sich für ein einzelnes Abonnement registrieren können. Alle nicht von Microsoft stammenden Lerninhalte werden unter den Bedingungen des Nicht-Microsoft-Anbieters bereitgestellt und nicht als Teil von Viva Learning. 

Um eine Lerninhaltsquelle zu aktivieren oder zu deaktivieren, aktivieren Sie das Kontrollkästchen neben der Quelle. Wenn eine Quelle aktiviert ist, wird ein Häkchen angezeigt.

## <a name="third-party-content-providers"></a>Drittanbieter für Inhalte 

Die Gruppe der verfügbaren Anbieter für verbundenes Lernen kann sich jederzeit ändern. Weitere Anbieter werden teilnehmen, wenn das Programm wächst. Verfügbare Anbieter können auch ihre Verbindung mit Viva Learning (Vorschau) einstellen.

### <a name="skillsoft-as-a-content-source"></a>Skillsoft als Inhaltsquelle  

Für Viva Learning (Vorschau) landen Benutzer, für die Skillsoft aktiviert ist und sich für die Anzeige von Skillsoft-Inhalten entscheidet, auf einer Percipio-Seite, auf der sie aufgefordert werden, den Percipio-Websitenamen Ihrer Organisation einzugeben. Nachdem Benutzer den Websitenamen Ihrer Organisation eingegeben haben, werden sie zur Seite weitergeleitet, um sich bei der Percipio-Website Ihrer Organisation anzumelden. Benutzer melden sich mit ihren vorhandenen Anmeldeinformationen an und sehen den ursprünglich ausgewählten Inhalt. Benutzer werden aufgefordert, den Namen der Percipio-Website nur einmal einzugeben, bis der Browsercache gelöscht wird. Um diese Erfahrung für Ihre Benutzer zu optimieren, empfehlen wir, den Namen Ihrer Percipio-Website in die interne Kommunikation zu einschließen, die Sie über Viva Learning (Vorschau) senden.

Dies ist als temporäre Benutzeroberfläche für die Vorschau gedacht, und wir arbeiten mit Skillsoft zusammen, um die mandantenspezifische Integration für die allgemeine Verfügbarkeit zu ermöglichen. Dadurch wird der Schritt umgangen, in dem Benutzer den Percipio-Websitenamen Ihrer Organisation angeben müssen. 

### <a name="details-on-microsoft-substrate"></a>Details zum Microsoft- Substrate  

Für Daten, die Sie von einem Nicht-Microsoft-Dienst (Lernanbieter oder Lernverwaltungssystem) in Viva Learning (Vorschau) kopieren, können Sie diese Daten in Viva Learning (Vorschau) nicht direkt extrahieren, korrigieren oder löschen. Wir aktualisieren die Daten, die Sie von Nicht-Microsoft-Anbietern importieren, prompt, um Änderungen und Löschungen in den Nicht-Microsoft-Quelldaten widerzuspiegeln.

Sie müssen mit dem Lieferanten des Nicht-Microsoft-Diensts zusammenarbeiten, um auf Daten unter den Lizenz-, Dienst- oder Datenschutzbedingungen des Nicht-Microsoft-Diensts zuzugreifen, diese zu korrigieren, zu löschen oder zu extrahieren. Die dort vorgenommenen Änderungen werden in den Daten widergespiegelt, die für Ihre Verwendung in Viva Learning (Vorschau) nach Abschluss der Datenaktualisierungszyklen des Nicht-Microsoft-Diensts und viva Learning (Vorschau) verarbeitet werden. Wenn Sie die Verbindung zwischen Viva Learning (Vorschau) und einem Nicht-Microsoft-Dienst deaktivieren, werden alle Daten gelöscht, die Sie zuvor aus diesem Dienst importiert haben. 

## <a name="next-step"></a>Nächster Schritt

[Konfigurieren SharePoint als Lerninhaltsquelle für Microsoft Viva Learning (Vorschau)](configure-sharepoint-content-source.md)