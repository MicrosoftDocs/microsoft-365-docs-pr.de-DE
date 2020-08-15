---
title: Automatisieren der Lizenzierung und der Gruppenmitgliedschaft für Ihre Microsoft 365 for Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie die Gruppenbasierte Lizenzierung und die dynamische Gruppenmitgliedschaft in Ihrer Microsoft 365 for Enterprise-Testumgebung.
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685558"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatisieren der Lizenzierung und der Gruppenmitgliedschaft für Ihre Microsoft 365 for Enterprise-Testumgebung

*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*

Bei der gruppenbasierten Lizenzierung werden basierend auf der Gruppenmitgliedschaft automatisch Lizenzen für ein Benutzerkonto zugewiesen oder entfernt. Durch die dynamische Gruppenmitgliedschaft werden Mitglieder einer Gruppe basierend auf den Eigenschaften des Benutzerkontos wie Abteilung oder Land hinzugefügt oder entfernt. In diesem Artikel werden Sie durch eine Demonstration der beiden in Ihrer Microsoft 365 für Enterprise-Testumgebung erläutert.

Es gibt zwei Phasen zum Einrichten der automatischen Lizenzierung und der dynamischen Gruppenmitgliedschaft in Ihrer Microsoft 365 for Enterprise-Testumgebung:

1. Erstellen Sie die Microsoft 365 for Enterprise-Testumgebung.
2. Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung.

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen

Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen der automatischen Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung

Zunächst erstellen Sie eine neue Gruppe "Sales" und fügen eine dynamische Gruppen Mitgliedschaftsregel hinzu, sodass Benutzerkonten mit der Abteilung "Sales" automatisch der Gruppe "Sales" hinzugefügt werden.

1. Melden Sie sich mit einer privaten Instanz Ihres Internet Browsers beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit dem globalen Administratorkonto Ihres Microsoft 365 E5 Test Lab-Abonnements an.
2. Wechseln Sie auf einer separaten Registerkarte Ihres Browsers zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) .
3. Geben Sie im Azure-Portal **Gruppen** in das Suchfeld ein, und klicken Sie dann auf **Gruppen**.
4. Klicken Sie im Bereich **alle Gruppen** auf **neue Gruppe**.
5. Wählen Sie unter **Gruppentyp den Namen** **Microsoft 365**aus.
6. Geben Sie unter **Gruppenname den Namen** **Sales**ein.
7. Wählen Sie im **Typ Mitgliedschaft**die Option **dynamischer Benutzer**aus.
8. Klicken Sie auf **dynamische Benutzer Mitglieder**.
9. Im Bereich **Dynamische Mitgliedschaftsregeln** : 
   - Wählen Sie die Eigenschaft **Department** aus.
   - Wählen Sie den **Equals** -Operator aus.
   - Geben Sie **Umsatz** in **value**ein.
10. Klicken Sie auf **Speichern**.
11. Klicken Sie auf **Erstellen**.

Als Nächstes konfigurieren Sie die Gruppe "Sales" so, dass Mitgliedern automatisch die Microsoft 365 E5-Lizenz zugewiesen wird.

1. Klicken Sie auf die Gruppe **Vertrieb** , und klicken Sie dann auf **Lizenzen**.
2. Wählen Sie im Bereich **Lizenzzuweisungen aktualisieren** die Option **Microsoft 365 E5**aus, und klicken Sie dann auf **Speichern**.
3. Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.

Als nächstes testen Sie die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung für das Benutzerkonto 4. 

1. Klicken Sie auf der Registerkarte **Microsoft Office Start** in Ihrem Browser auf **Administrator**.
2. Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** auf **aktive Benutzer**.
3. Klicken Sie auf der Seite **aktive Benutzer** auf das Konto **Benutzer 4** .
4. Klicken Sie im Bereich **Benutzer 4** auf für **Produktlizenzen** **Bearbeiten** .
5. Deaktivieren Sie im Bereich **Produktlizenzen** die Lizenz **Microsoft 365 E5** , und klicken Sie dann auf **> schließen speichern**.
6. Überprüfen Sie in den Eigenschaften des Benutzerkontos 4, dass keine Produktlizenzen zugewiesen wurden und keine Gruppenmitgliedschaften vorhanden sind.
7. Klicken Sie auf **Bearbeiten** , um **Kontaktinformationen zu erhalten**.
8. Klicken Sie im Bereich **Kontaktinformationen bearbeiten** auf **Kontaktinformationen**.
9. Geben Sie im Feld **Abteilung** den Namen **Sales**ein, und klicken Sie dann auf **> schließen speichern**.
10. Warten Sie einige Minuten, und klicken Sie dann regelmäßig auf das Aktualisierungssymbol in der oberen rechten Ecke des Benutzer-4-Konto Bereichs. 

In der Zeit sollte Folgendes angezeigt werden:

- **Group Memberships** -Eigenschaft mit der Gruppe " **Sales** " aktualisiert.
- Die Eigenschaft " **Produktlizenzen** " wurde mit der **Microsoft 365 E5** -Lizenz aktualisiert.

Lesen Sie diese Artikel, um die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung in der Produktion bereitzustellen:

- Verknüpfungs Anknüpfung
- Verknüpfungs Anknüpfung

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Identity-Roadmap](identity-roadmap-microsoft-365.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
