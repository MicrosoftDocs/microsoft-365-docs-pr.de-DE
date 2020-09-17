---
title: Erstellen eines B2B-Extranets mit verwalteten Gästen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Hier erfahren Sie, wie Sie eine B2B-Extranet-Website oder ein Team mit verwalteten Gastbenutzern aus einer Partnerorganisation erstellen.
ms.openlocfilehash: 83252241833f3dfe663cc70eae28a5df1214cce0
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949384"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Erstellen eines B2B-Extranets mit verwalteten Gästen

Sie können [Azure Active Directory Berechtigungsverwaltung](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) verwenden, um ein B2B-Extranet zur Zusammenarbeit mit einer Partnerorganisation zu erstellen, die Azure-Active Directory verwendet. Dadurch können sich Benutzer selbst im Extranet-Standort oder-Team registrieren und über einen Genehmigungsworkflow Zugriff erhalten.

Mit dieser Methode zum Freigeben von Ressourcen für die Zusammenarbeit kann die Partnerorganisation dabei helfen, die Gastbenutzer zu verwalten und zu genehmigen, wodurch die Belastung Ihrer IT-Abteilung reduziert wird und die Benutzer, die mit der Zusammenarbeitsvereinbarung vertraut sind, den Benutzer Zugriff verwalten.

In diesem Artikel werden die Schritte beschrieben, um ein Ressourcenpaket (in diesem Fall eine Website oder ein Team) zu erstellen, das Sie über ein Self-Service Access-Registrierungsmodell für eine Partnerorganisation freigeben können. 

Bevor Sie beginnen, erstellen Sie die Website oder das Team, die Sie für die Partnerorganisation freigeben möchten, und aktivieren Sie Sie für die Gast Freigabe. Weitere Informationen finden Sie unter [Zusammenarbeit mit Gästen in einer Website](collaborate-in-site.md) oder [Zusammenarbeit mit Gästen in einem Team](collaborate-as-team.md) . Außerdem wird empfohlen, dass Sie [eine Umgebung für sichere Gast Freigaben erstellen](create-secure-guest-sharing-environment.md) , in der Sie Informationen zu Sicherheits-und Kompatibilitätsfeatures erhalten, die Sie bei der Zusammenarbeit mit Gästen zur Verwaltung Ihrer Steuerungsrichtlinien verwenden können.

## <a name="license-requirements"></a>Lizenzanforderungen

Für die Verwendung dieses Features ist eine Azure AD Premium P2-Lizenz erforderlich. 

Spezielle Clouds wie Azure Deutschland und Azure China 21Vianet sind derzeit nicht zur Verwendung verfügbar.

## <a name="video-demonstration"></a>Videodemonstration

In diesem Video werden die in diesem Artikel behandelten Verfahren veranschaulicht.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>Verbinden der Partnerorganisation

Um Gäste aus einer Partnerorganisation einzuladen, müssen Sie die Domäne des Partners als verbundene Organisation in Azure Active Directory hinzufügen.

So fügen Sie eine verbundene Organisation hinzu
1. Klicken Sie in [Azure Active Directory](https://aad.portal.azure.com)auf **Identity Governance**.
2. Klicken Sie auf **verbundene Organisationen**.
4. Klicken Sie auf **verbundene Organisation hinzufügen**.
5. Geben Sie einen Namen und eine Beschreibung für die Organisation ein, und klicken Sie dann auf **Weiter: Verzeichnis + Domäne**.
6. Klicken Sie auf **Verzeichnis + Domäne hinzufügen**.
7. Geben Sie die Domäne für die Organisation ein, mit der Sie eine Verbindung herstellen möchten, und klicken Sie dann auf **Hinzufügen**.
8. Klicken Sie auf **verbinden**, und klicken Sie dann auf **Weiter: Sponsoren**.
9. Hinzufügen von Personen aus Ihrer Organisation oder der Organisation, der Sie eine Verbindung herstellen möchten, für die Sie den Zugriff für Gastbenutzer genehmigen möchten.
10. Klicken Sie auf **Weiter: Review + Create**.
11. Überprüfen Sie die Einstellungen, die Sie ausgewählt haben, und klicken Sie dann auf **Erstellen**.

    ![Screenshot der Seite "verbundene Organisationen" in Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>Auswählen der freizugebenden Ressourcen

Der erste Schritt bei der Auswahl von Ressourcen, die für eine Partnerorganisation freigegeben werden sollen, ist das Erstellen eines Katalogs, der diese enthalten soll.

So erstellen Sie einen Katalog
1. Klicken Sie in [Azure Active Directory](https://aad.portal.azure.com)auf **Identity Governance**.
2. Klicken Sie auf **Kataloge**.
3. Klicken Sie auf **neuer Katalog**.
4. Geben Sie einen Namen und eine Beschreibung für den Katalog ein, und stellen Sie sicher, dass **für externe Benutzer** **aktiviert** und aktiviert beide auf **Ja**festgelegt sind.
5. Klicken Sie auf **Erstellen**.

   ![Screenshot der Seite "Kataloge" in Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

Nachdem der Katalog erstellt wurde, fügen Sie die SharePoint-Website oder das Team hinzu, die Sie für die Partnerorganisation freigeben möchten.

So fügen Sie einem Katalogressourcen hinzu
1. Klicken Sie in Azure AD Identitäts Steuerung auf **Kataloge**, und klicken Sie dann auf den Katalog, in dem Sie Ressourcen hinzufügen möchten.
2. Klicken Sie auf **Ressourcen** , und klicken Sie dann auf **Ressourcen hinzufügen**.
3. Wählen Sie die Teams oder SharePoint-Websites aus, die Sie in Ihr Extranet einbeziehen möchten, und klicken Sie dann auf **Hinzufügen**.

   ![Screenshot der Seite "Katalogressourcen" in Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

Nachdem Sie die Ressourcen definiert haben, die Sie freigeben möchten, müssen Sie im nächsten Schritt ein Access-Paket erstellen, das die Art des Zugriffs für Partnerbenutzer und den Genehmigungsprozess für neue Partnerbenutzer definiert, die Zugriff anfordern.

So erstellen Sie ein Access-Paket
1. Klicken Sie in Azure AD Identitäts Steuerung auf **Kataloge**, und klicken Sie dann auf den Katalog, in dem Sie ein Access-Paket erstellen möchten.
2. Klicken Sie auf **Access-Pakete**, und klicken Sie dann auf **Neues Zugriffs Paket**.
3. Geben Sie einen Namen und eine Beschreibung für das Access-Paket ein, und klicken Sie dann auf **Weiter: Ressourcen Rollen**.
4. Wählen Sie die Ressourcen aus dem Katalog aus, die Sie für Ihr Extranet verwenden möchten.
5. Wählen Sie für jede Ressource in der Spalte **Rolle** die Benutzerrolle aus, die Sie den Gastbenutzern gewähren möchten, die das Extranet verwenden.
6. Klicken Sie auf **Weiter: Anfragen**.
7. Wählen Sie unter **Benutzer, die Zugriff anfordern können** **aus für Benutzer, die sich nicht in Ihrem Verzeichnis**befinden.
8. Stellen Sie sicher, dass die Option **bestimmte verbundene Organisationen** ausgewählt ist, und klicken Sie dann auf **Verzeichnisse hinzufügen**.
9. Wählen Sie die verbundene Organisation aus, die Sie zuvor hinzugefügt haben, und klicken Sie dann auf **auswählen**
10. Wählen Sie unter **Genehmigung**die Option **Ja** für **Genehmigung erforderlich**aus.
11. Wählen Sie unter **erste genehmigende Person**einen der Sponsoren aus, die Sie zuvor hinzugefügt haben, oder wählen Sie einen bestimmten Benutzer aus.
12. Klicken Sie auf **Fallback hinzufügen** und wählen Sie eine Fallback genehmigende Person aus.
13. Wählen Sie unter **aktivieren**die Option **Ja**aus.
14. Klicken Sie auf **Weiter: Lebenszyklus**.
15. Wählen Sie die Einstellungen für Ablauf und Zugriffsüberprüfung aus, die Sie verwenden möchten, und klicken Sie dann auf **Weiter: Überprüfen + Erstellen**.
16. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Erstellen**.

    ![Screenshot des Access Packages-Bildschirms in Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

Wenn Sie eine Partnerschaft mit einer großen Organisation ausführen möchten, können Sie das Access-Paket ausblenden. Wenn das Paket ausgeblendet ist, werden Benutzer in der Partnerorganisation das Paket nicht auf Ihrem *My Access* -Portal sehen. Stattdessen muss Ihnen ein direkter Link zur Anmeldung für das Paket gesendet werden. Das Ausblenden des Access-Pakets kann die Anzahl unangemessener Zugriffsanforderungen verringern und auch dazu beitragen, dass verfügbare Zugriffs Pakete im Portal der Partnerorganisation organisiert werden.

So legen Sie ein Access-Paket auf ausgeblendet fest
1. Klicken Sie in Azure AD Identitäts Steuerung auf **Access-Pakete**, und klicken Sie dann auf Ihr Zugriffs Paket.
2. Klicken Sie auf der Seite **Übersicht** auf **Bearbeiten**.
3. Wählen Sie unter **Eigenschaften**die Option **Ja** für **ausgeblendet**aus, und klicken Sie dann auf **Speichern**.

   ![Screenshot des Bildschirms Eigenschaften des Bearbeitungs Zugriffs Pakets](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Einladen von Partnerbenutzern

Wenn Sie das Access-Paket auf ausgeblendet festlegen, müssen Sie einen direkten Link zur Partnerorganisation senden, damit Sie Zugriff auf Ihre Website oder Ihr Team anfordern können.

So suchen Sie den Access Portal-Link
1. Klicken Sie in Azure AD Identitäts Steuerung auf **Access-Pakete**, und klicken Sie dann auf Ihr Zugriffs Paket.
2. Klicken Sie auf der Übersichts **Seite auf den Link** **in Zwischenablage kopieren** für den **Link My Access Portal**.

   ![Screenshot der Access-Paketeigenschaften mit Access Portal Link](../media/identity-governance-access-portal-link.png)

Nachdem Sie den Link kopiert haben, können Sie ihn für Ihren Kontakt in der Partnerorganisation freigeben, und er kann ihn an die Benutzer im Team für die Zusammenarbeit senden.

## <a name="see-also"></a>Siehe auch

[Erstellen einer sicheren Umgebung für die Gastfreigabe](create-secure-guest-sharing-environment.md)
