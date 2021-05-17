---
title: Erstellen eines B2B-Extranets mit verwalteten Gästen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Erfahren Sie, wie Sie eine B2B-Extranetwebsite oder ein Team mit verwalteten Gästen aus einer Partnerorganisation erstellen.
ms.openlocfilehash: f9b8d9326f302233ed85c9d168fdf6f343dc6cbf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904756"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Erstellen eines B2B-Extranets mit verwalteten Gästen

Sie können Azure Active Directory [Berechtigungsverwaltung](/azure/active-directory/governance/entitlement-management-overview) verwenden, um ein B2B-Extranet für die Zusammenarbeit mit einer Partnerorganisation zu erstellen, die Azure Active Directory. Auf diese Weise können sich Benutzer selbst für die Extranetwebsite oder das Extranetteam registrieren und über einen Genehmigungsworkflow Zugriff erhalten.

Mit dieser Methode der Freigabe von Ressourcen für die Zusammenarbeit kann die Partnerorganisation dazu beitragen, die Gäste am Ende zu warten und zu genehmigen, die Belastung Für Ihre IT-Abteilung zu reduzieren und denjenigen, die mit der Zusammenarbeitsvereinbarung vertraut sind, die Verwaltung des Benutzerzugriffs zu ermöglichen.

In diesem Artikel werden die Schritte zum Erstellen eines Ressourcenpakets (in diesem Fall einer Website oder eines Teams) erläutert, das Sie über ein Self-Service-Zugriffsregistrierungsmodell für eine Partnerorganisation freigeben können. 

Erstellen Sie vor Beginn die Website oder das Team, die Sie für die Partnerorganisation freigeben möchten, und aktivieren Sie sie für die Gastfreigabe. Weitere [Informationen finden Sie unter Zusammenarbeiten](collaborate-in-site.md) mit Gästen in einer Website oder Zusammenarbeit mit Gästen [in](collaborate-as-team.md) einem Team. Es wird außerdem [](create-secure-guest-sharing-environment.md) empfohlen, dass Sie erstellen eine sichere Umgebung für die Gastfreigabe für Informationen zu Sicherheits- und Compliancefeatures, die Sie verwenden können, um Ihre Steuerungsrichtlinien bei der Zusammenarbeit mit Gästen zu verwalten.

## <a name="license-requirements"></a>Lizenzanforderungen

Die Verwendung dieses Features erfordert eine Azure AD Premium P2-Lizenz. 

Spezielle Clouds wie Azure Deutschland und Azure China 21Vianet stehen derzeit nicht zur Verfügung.

## <a name="video-demonstration"></a>Videodemonstration

In diesem Video werden die in diesem Artikel behandelten Verfahren veranschaulicht.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>Verbinden der Partnerorganisation

Zum Einladen von Gästen aus einer Partnerorganisation müssen Sie die Domäne des Partners als verbundene Organisation in einer Azure Active Directory.

So fügen Sie eine verbundene Organisation hinzu
1. Klicken [Azure Active Directory](https://aad.portal.azure.com)in diesem Link auf **Identitätsverwaltung**.
2. Klicken Sie **auf Verbundene Organisationen**.
4. Klicken Sie **auf Verbundene Organisation hinzufügen**.
5. Geben Sie einen Namen und eine Beschreibung für die Organisation ein, und klicken Sie dann auf **Weiter: Verzeichnis + Domäne**.
6. Klicken **Sie auf Verzeichnis + Domäne hinzufügen.**
7. Geben Sie die Domäne für die Organisation ein, die Sie verbinden möchten, und klicken Sie dann auf **Hinzufügen**.
8. Klicken **Verbinden**, und klicken Sie dann auf **Weiter: Sponsoren**.
9. Fügen Sie Personen aus Ihrer Organisation oder der Organisation hinzu, mit denen Sie eine Verbindung herstellen, mit der Sie den Zugriff für Gäste genehmigen möchten.
10. Klicken Sie auf **Weiter: Überprüfen + erstellen**.
11. Überprüfen Sie die von Ihnen ausgewählten Einstellungen, und klicken Sie dann auf **Erstellen**.

    ![Screenshot der Seite verbundene Organisationen in Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>Auswählen der ressourcen, die gemeinsam verwendet werden soll

Der erste Schritt bei der Auswahl von Ressourcen, die für eine Partnerorganisation verwendet werden sollen, besteht in der Erstellung eines Katalogs, der sie enthält.

So erstellen Sie einen Katalog
1. Klicken [Azure Active Directory](https://aad.portal.azure.com)in diesem Link auf **Identitätsverwaltung**.
2. Klicken Sie **auf Kataloge**.
3. Klicken Sie **auf Neuer Katalog**.
4. Geben Sie einen Namen und eine Beschreibung für den Katalog ein, und stellen Sie sicher, dass **Enabled** und **Enabled** für externe Benutzer beide auf Ja **festgelegt sind.**
5. Klicken Sie auf **Erstellen**.

   ![Screenshot der Katalogseite in Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

Nachdem der Katalog erstellt wurde, fügen Sie die SharePoint oder das Team hinzu, die Sie für die Partnerorganisation freigeben möchten.

So fügen Sie einem Katalog Ressourcen hinzu
1. Klicken Sie in Azure AD Identity Governance auf **Kataloge,** und klicken Sie dann auf den Katalog, in dem Sie Ressourcen hinzufügen möchten.
2. Klicken Sie **auf Ressourcen,** und klicken Sie dann **auf Ressourcen hinzufügen.**
3. Wählen Sie die Teams oder SharePoint aus, die Sie in Ihr Extranet hinzufügen möchten, und klicken Sie dann auf **Hinzufügen.**

   ![Screenshot der Katalogressourcenseite in Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

Nachdem Sie die Ressourcen definiert haben, die Sie freigeben möchten, besteht der nächste Schritt im Erstellen eines Zugriffspakets, das den Typ des Zugriffs definiert, dem Partnerbenutzer gewährt werden, und den Genehmigungsprozess für neue Partnerbenutzer, die Zugriff anfordern.

So erstellen Sie ein Zugriffspaket
1. Klicken Sie in Azure AD Identity Governance auf **Kataloge,** und klicken Sie dann auf den Katalog, in dem Sie ein Zugriffspaket erstellen möchten.
2. Klicken **Sie auf Access-Pakete,** und klicken Sie dann auf **Neues Zugriffspaket**.
3. Geben Sie einen Namen und eine Beschreibung für das Zugriffspaket ein, und klicken Sie dann auf **Weiter: Ressourcenrollen**.
4. Wählen Sie die Ressourcen aus dem Katalog aus, den Sie für Ihr Extranet verwenden möchten.
5. Wählen Sie für jede Ressource in der Spalte **Rolle** die Benutzerrolle aus, die Sie den Gästen gewähren möchten, die das Extranet verwenden.
6. Klicken **Sie auf Weiter: Anforderungen**.
7. Wählen **Sie unter Benutzer, die Zugriff anfordern können,** die Option **Für Benutzer nicht in Ihrem Verzeichnis aus.**
8. Stellen Sie **sicher, dass die** Option Spezifische verbundene Organisationen ausgewählt ist, und klicken Sie dann auf Verzeichnisse **hinzufügen.**
9. Wählen Sie die verbundene Organisation aus, die Sie zuvor hinzugefügt haben, und klicken Sie dann auf **Auswählen.**
10. Wählen **Sie unter Genehmigung** die Option **Ja** für Genehmigung **erforderlich aus.**
11. Wählen **Sie unter Erster** Genehmiger einen der Sponsoren aus, den Sie zuvor hinzugefügt haben, oder wählen Sie einen bestimmten Benutzer aus.
12. Klicken **Sie auf Fallback hinzufügen,** und wählen Sie eine Fallback genehmigende Benutzer aus.
13. Wählen **Sie unter Aktivieren** die Option Ja **aus.**
14. Klicken **Sie auf Weiter: Lebenszyklus**.
15. Wählen Sie die Einstellungen für Ablauf- und Zugriffsüberprüfung aus, die Sie verwenden möchten, und klicken Sie dann auf **Weiter: Überprüfen + Erstellen**.
16. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Erstellen**.

    ![Screenshot des Zugriffspaketbildschirms in Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

Wenn Sie eine Partnerschaft mit einer großen Organisation haben, sollten Sie das Zugriffspaket ausblenden. Wenn das Paket ausgeblendet ist, wird den Benutzern in der Partnerorganisation das Paket im *Portal My Access nicht* angezeigt. Stattdessen müssen sie einen direkten Link erhalten, um sich für das Paket zu registrieren. Das Ausblenden des Zugriffspakets kann die Anzahl unangemessener Zugriffsanforderungen verringern und auch dazu beitragen, dass verfügbare Zugriffspakete im Portal der Partnerorganisation organisiert bleiben.

So legen Sie ein Zugriffspaket auf ausgeblendet
1. Klicken Sie in Azure AD Identity Governance auf **Access-Pakete,** und klicken Sie dann auf Ihr Zugriffspaket.
2. Klicken Sie **auf der Seite** Übersicht auf **Bearbeiten**.
3. Wählen **Sie unter Eigenschaften** die Option **Ja** für **Ausgeblendet** aus, und klicken Sie dann auf **Speichern**.

   ![Screenshot eines Zugriffspaketeigenschaftenbildschirms für den Bearbeitungszugriff](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Einladen von Partnerbenutzern

Wenn Sie das Zugriffspaket auf ausgeblendet festlegen, müssen Sie einen direkten Link zur Partnerorganisation senden, damit diese Zugriff auf Ihre Website oder Ihr Team anfordern kann.

So suchen Sie den Link zum Zugriffsportal
1. Klicken Sie in Azure AD Identity Governance auf **Access-Pakete,** und klicken Sie dann auf Ihr Zugriffspaket.
2. Klicken Sie **auf der Seite** Übersicht für den Link Mein **Access-Portal** auf In zwischenablage kopieren. 

   ![Screenshot der Zugriffspaketeigenschaften mit Zugriffsportallink](../media/identity-governance-access-portal-link.png)

Nachdem Sie den Link kopiert haben, können Sie ihn für Ihren Kontakt in der Partnerorganisation freigeben und an die Benutzer im Team für die Zusammenarbeit senden.

## <a name="see-also"></a>Siehe auch

[Erstellen einer sicheren Umgebung für die Gastfreigabe](create-secure-guest-sharing-environment.md)