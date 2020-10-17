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
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487576"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatisieren der Lizenzierung und der Gruppenmitgliedschaft für Ihre Microsoft 365 for Enterprise-Testumgebung

*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*

Bei der gruppenbasierten Lizenzierung werden basierend auf der Gruppenmitgliedschaft automatisch Lizenzen für ein Benutzerkonto zugewiesen oder entfernt. Durch die dynamische Gruppenmitgliedschaft werden Mitglieder einer Gruppe basierend auf den Eigenschaften des Benutzerkontos wie **Abteilung** oder **Land**hinzugefügt oder entfernt. In diesem Artikel werden die Vorführungen für das Hinzufügen und Entfernen von Gruppenmitgliedern in Ihrer Microsoft 365 for Enterprise-Testumgebung erläutert.

Das Einrichten der automatischen Lizenzierung und der dynamischen Gruppenmitgliedschaft in Ihrer Microsoft 365 for Enterprise-Testumgebung umfasst zwei Phasen:

- [Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen

Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Er wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung

Erstellen Sie zuerst eine neue Gruppe mit dem Namen "Sales", und fügen Sie eine dynamische Gruppen Mitgliedschaftsregel hinzu, sodass Benutzerkonten, deren **Abteilung** " **Sales** " festgelegt ist, automatisch der Gruppe "Sales" beitreten.

1. Melden Sie sich in einer privaten Instanz Ihres Internetbrowsers beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit dem globalen Administratorkonto Ihres Microsoft 365 E5 Test Lab-Abonnements an.
2. Wechseln Sie auf einer separaten Registerkarte Ihres Browsers zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) .
3. Geben Sie im Azure-Portal in das Suchfeld **Gruppen** ein, und wählen Sie dann **Gruppen**aus.
4. Wählen Sie im Bereich **alle Gruppen** die Option **neue Gruppe**aus.
5. Wählen Sie unter **Gruppentyp den Namen** **Microsoft 365**aus.
6. Geben Sie unter **Gruppenname den Namen** **Sales**ein.
7. Wählen Sie im **Typ Mitgliedschaft**die Option **dynamischer Benutzer**aus.
8. Wählen Sie **dynamische Benutzer Mitglieder**aus.
9. Im Bereich **Dynamische Mitgliedschaftsregeln** : 
   - Wählen Sie die Eigenschaft **Department** aus.
   - Wählen Sie den **Equals** -Operator aus.
   - Geben Sie im Feld **Wert** die Option **Sales**ein.
10. Klicken Sie auf **Speichern**.
11. Wählen Sie **Erstellen** aus.

Konfigurieren Sie als nächstes die Gruppe "Sales" so, dass Mitgliedern automatisch die Microsoft 365 E5-Lizenz zugewiesen wird.

1. Wählen Sie die Gruppe **Vertrieb** aus, und wählen Sie dann **Lizenzen**aus.
2. Wählen Sie im Bereich **Lizenzzuweisungen aktualisieren** die Option **Microsoft 365 E5**aus, und wählen Sie dann **Speichern**aus.
3. Schließen Sie in Ihrem Browser die Registerkarte Azure-Portal.

Testen Sie als nächstes die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung für das Benutzerkonto 4:

1. Wählen Sie auf der Registerkarte **Microsoft Office Start** in Ihrem Browser **Administrator**aus.
2. Wählen Sie auf der Registerkarte **Microsoft 365 Admin Center** die Option **aktive Benutzer**aus.
3. Wählen Sie auf der Seite **aktive Benutzer** das Konto **Benutzer 4** aus.
4. Wählen Sie im Bereich **Benutzer 4** die Option für **Produktlizenzen** **Bearbeiten** aus.
5. Deaktivieren Sie im Bereich **Produktlizenzen** die **Microsoft 365 E5** -Lizenz, und wählen Sie dann **Speichern**  >  **Schließen**aus.
6. Überprüfen Sie in den Eigenschaften des Benutzerkontos 4, dass keine Produktlizenzen zugewiesen wurden und keine Gruppenmitgliedschaften vorhanden sind.
7. Wählen Sie für **Kontaktinformationen**die Option **Bearbeiten**aus.
8. Wählen Sie im Bereich **Kontaktinformationen bearbeiten** die Option **Kontaktinformationen**aus.
9. Geben Sie im Feld **Abteilung** die Option **Sales**ein, und wählen Sie dann **Speichern**  >  **Schließen**aus.
10. Warten Sie einige Minuten, und wählen Sie dann in regelmäßigen Abständen das **Aktualisierungs** Symbol in der oberen rechten Ecke des Benutzer-4-Konto Bereichs aus.

In der Zeit sollte Folgendes angezeigt werden:

- **Group Memberships** -Eigenschaft mit der Gruppe " **Sales** " aktualisiert.
- Die Eigenschaft " **Produktlizenzen** " wurde mit der **Microsoft 365 E5** -Lizenz aktualisiert.

Lesen Sie diese Artikel, um die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung in der Produktion bereitzustellen:

- [Gruppenbasierte Lizenzierung in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Dynamische Gruppen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Identity-Roadmap](identity-roadmap-microsoft-365.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
