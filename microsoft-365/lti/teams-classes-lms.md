---
title: Verwenden von Microsoft Teams-Klassen in Ihrem Lernverwaltungssystem
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrieren von Microsoft Teams-Klassen in Ihr Lernverwaltungssystem
ms.openlocfilehash: 18d33225dd57932af20421c6b3b5dc4fe3b397b8
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327787"
---
# <a name="use-microsoft-teams-classes-in-your-learning-management-system"></a>Verwenden von Microsoft Teams-Klassen in Ihrem Lernverwaltungssystem

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Microsoft Teams-Kursteams ist eine LTI-App (Learning Tools Interoperability), die Lehrkräften und Schülern dabei hilft, problemlos zwischen ihrem Lernverwaltungssystem (Learning Management System, LMS) und Teams zu navigieren. Benutzer können direkt in ihrem LMS auf ihre Kursteams zugreifen, die ihrem Kurs zugeordnet sind.

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a>Genehmigen der App im Microsoft Azure-Mandanten

Die folgenden Aufgaben werden vom Microsoft Office 365-Administrator und dem Blackboard Learn Ultra-Administrator ausgeführt.

Vor der Verwaltung der Integration in Blackboard Learn Ultra muss der Microsoft Office 365-Administrator die Blackboard **MSFT Teams for Learn Ultra Azure-App** für den Microsoft Azure-Mandanten der Institution genehmigen.

1. Suchen Sie Nach Ihrer Microsoft-Mandanten-ID. Erfahren [Sie, wie Sie den Mandanten finden.](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)

2. Leiten Sie den Microsoft Identity Platform Admin Consent Endpoint gemäß dem folgenden Beispiel um:

   `https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > Ersetzen Sie {tenant} durch die Microsoft-Mandanten-ID Ihrer Organisation.

## <a name="register-the-integration-apps"></a>Registrieren der Integrations-Apps

Als Blackboard Learn Ultra-Administrator müssen Sie 2 LTI 1.3-Integrations-Apps in Ihrer Testumgebung registrieren:

- Die Blackboard Learn Class Teams-Integration zur Unterstützung der Dienstplansynchronisierung

- Die Microsoft Teams-Team-LTI-App

1. Notieren Sie sich die folgenden LTI-Client-IDs für beide Apps:

    - Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41

    - Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89

2. Greifen Sie auf den Administratorbereich zu, und suchen Sie unter **Integrationen** nach den LTI-Toolanbietern.

   ![Dies ist das Dialogfeld LTI-Toolanbieter, in dem eine Liste der Anbieter angezeigt wird](../media/lti-media/lti-tool-providers.png)

3. Wählen **Sie LTI1.3/Advantage Tool registrieren aus.**

4. Geben Sie die erste der bereitgestellten Client-IDs (Blackboard oder Microsoft) ein, und wählen Sie **Übermitteln aus.**

   ![Das LTI-Registrierungstool mit einem Feld zur Eingabe der Client-ID](../media/lti-media/register-tool.png)

5. Überprüfen Sie die vordefinierten Einstellungen, und stellen Sie sicher, dass der Toolstatus als genehmigt gekennzeichnet ist.

6. Scrollen Sie nach unten, und wählen Sie dann **Absenden aus.**

7. Wiederholen Sie die vorherigen Schritte, um die zweite der LTI-Apps in Ihrer Umgebung zu registrieren.

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a>Einrichten der REST-Anwendung und der ursprungsübergreifenden Ressourcenfreigabe

Der Blackboard Learn Ultra-Administrator muss außerdem die REST-Anwendung und die Konfiguration für die cross Origin Resource Sharing konfigurieren.

Führen Sie die folgenden Schritte aus, um die REST-Anwendung zu einrichten

1. Greifen Sie auf die Lernverwaltungstools zu, und wählen Sie dann **REST-API-Integrationen** im **Abschnitt Integrationen** aus.

2. Wählen **Sie Integrationen erstellen** aus, und geben Sie dieselbe Anwendungs-/Client-ID ein, die Sie für das Blackboard Learn Class Teams Integration LTI-Tool eingegeben haben.

3. Geben Sie den Benutzer lernen ein (dies kann Ihr eigener Benutzername für den Lernadministrator sein), oder wählen Sie **Durchsuchen** aus, um zu suchen.

4. Wählen **Sie Ja** für **Endbenutzerzugriff aus.**

5. Wählen **Sie Ja** für **Autorisiert als Benutzer handeln aus.**

6. Wählen **Sie Senden** aus, sobald sie abgeschlossen ist.

## <a name="set-up-cross-origin-resource-sharing"></a>Einrichten der ursprungsübergreifenden Ressourcenfreigabe

1. Greifen Sie auf die Lernverwaltungstools zu, und wählen Sie im Abschnitt **Integrationen** die Option **Cross-Origin Resource Sharing** aus.

2. Wählen **Sie Konfiguration erstellen aus.**

3. Geben `https://bb-ms-teams-ultra-ext.api.blackboard.com` Sie den Ursprung ein.

4. Fügen Sie das Wort **Autorisierung** in den **zulässigen Kopfzeilen hinzu.**

5. Set **Available** to **Yes**.

6. Wählen **Sie Senden** aus, sobald sie abgeschlossen ist.

## <a name="enable-class-teams-in-blackboard-learn"></a>Aktivieren von Kursteams in Blackboard Learn

Nachdem Sie die LTI-Tools aktiviert haben, besteht Der nächste Schritt in der Einrichtung der Microsoft Class Teams-Integration von Ihrem Microsoft Office 365-Mandanten. Dazu können Sie die folgenden Schritte als Blackboard Learn Ultra Admin ausführen.

1. Wählen **Sie unter Learn Admin** Tools and  >  **Utilities** die Option Microsoft Teams Integration Admin **aus.**

   ![Das Dialogfeld Tools und Dienstprogramme mit einer Liste der verfügbaren Tools](../media/lti-media/tools-utilities.png)

2. Aktivieren Sie das Kontrollkästchen Microsoft **Teams aktivieren.**

3. Geben Sie Ihre Mandanten-ID wie im Abschnitt unter Microsoft O365 Admin referenziert ein.

 > [!NOTE]
 > Sie können die Einstellungen erst speichern, wenn die App vom O365-Administrator genehmigt wurde. Weitere [Informationen finden Sie unter Genehmigen der App im Microsoft Azure-Mandanten](#approve-the-app-in-the-microsoft-azure-tenant).

4. Wenn der globale O365-Administrator die Blackboard Teams-Anwendung in Ihrem Microsoft Mandant genehmigt hat, wählen Sie **Übermitteln aus.**
