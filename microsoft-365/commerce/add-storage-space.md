---
title: Hinzufügen von Speicherplatz für Ihr Abonnement
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Dateispeicher in Ihrem Microsoft 365-Abonnement hinzufügen und reduzieren können. Mit zusätzlichem Dateispeicher können Sie mehr Inhalte in SharePoint Online und OneDrive speichern.
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114907"
---
# <a name="add-storage-space-for-your-subscription"></a>Hinzufügen von Speicherplatz für Ihr Abonnement

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Wenn sich im Laufe der Zeit herausstellt, dass Sie nicht mehr über genügend Speicherplatz für Ihre SharePoint Online-Websitesammlungen verfügen, können Sie im Rahmen Ihres Abonnements zusätzlich weiteren Speicherplatz erwerben, wenn Sie gemäß Ihrem Plan dazu berechtigt sind.  Wenn der zusätzliche Dateispeicher für **Office 365** nicht in der Liste der verfügbaren Add-Ons angezeigt wird, bedeutet dies, dass Ihr Plan nicht berechtigt ist. Weitere Informationen finden Sie unter ["Ist mein Plan berechtigt?](#is-my-plan-eligible-for-office-365-extra-file-storage)

> [!NOTE]
> Wenn Sie Ihr Abonnement über Volumenlizenzierung oder einen CSP erworben haben, können Sie **Office 365 Zusätzlichen** Dateispeicher für Ihre Organisation nicht direkt von Microsoft kaufen. Wenden Sie sich an Ihren Vertreter oder Partner, um Hilfe zu finden.

## <a name="before-you-begin"></a>Vorabinformationen

Sie müssen ein globaler oder ein SharePoint-Administrator sein, um die Aufgaben in diesem Artikel ausführen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md).

## <a name="view-available-storage"></a>Anzeigen des verfügbaren Speichers

::: moniker range="o365-worldwide"

1. Wechseln Sie im SharePoint Admin Center zur Seite <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">"Aktive</a> Websites", und melden Sie sich mit einem Konto an, das über Administratorberechtigungen [für](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) Ihre Organisation verfügt.

2. Oben rechts auf der Seite sehen Sie die Menge des verwendeten Speichers für alle Websites und den Gesamtspeicher für Ihr Abonnement. Wenn Ihre Organisation Multi-Geo in Office 365 konfiguriert hat, zeigt die Leiste auch die Menge an Speicherplatz an, die an allen geografischen Standorten verwendet wird.

   ![Speicherleiste auf der Seite „Aktive Websites“](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > Der verwendete Speicher enthält keine Änderungen, die innerhalb der letzten 24–48 Stunden vorgenommen wurden.

::: moniker-end

::: moniker range="o365-germany"

1. Melden Sie sich als globaler Administrator oder Als SharePoint-Administrator an, und wählen Sie dann die Kachel https://portal.office.de "Admin" aus, um das Admin Center zu öffnen. Wenn eine Meldung angezeigt wird, dass Sie nicht über die Berechtigung zum Zugriff auf die Seite verfügen, bedeutet dies, dass Sie nicht über Microsoft 365-Administratorberechtigungen in Ihrer Organisation verfügen.

2. Wählen Sie im linken Bereich unter **Admin Center** **SharePoint aus.** Wenn das klassische SharePoint Admin Center angezeigt wird, wählen Sie **Jetzt öffnen** am oberen Rand der Seite aus, um das neue SharePoint Admin Center zu öffnen.

3. Wählen Sie im linken Bereich des neuen SharePoint Admin Center **Aktive Websites** aus.

4. Oben rechts auf der Seite sehen Sie die Menge des verwendeten Speichers für alle Websites und den Gesamtspeicher für Ihr Abonnement.

   ![Speicherleiste auf der Seite „Aktive Websites“](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > Der verwendete Speicher enthält keine Änderungen, die innerhalb der letzten 24–48 Stunden vorgenommen wurden.

::: moniker-end

::: moniker range="o365-21vianet"

1. Melden Sie sich als globaler Administrator oder Als SharePoint-Administrator an, und wählen Sie dann die Kachel https://login.partner.microsoftonline.cn/ "Admin" aus, um das Admin Center zu öffnen. (Wenn eine Meldung angezeigt wird, dass Sie nicht über die Berechtigung zum Zugriff auf die Seite verfügen, bedeutet dies, dass Sie nicht über Microsoft 365-Administratorberechtigungen in Ihrer Organisation verfügen.

2. Wählen Sie im linken Bereich unter **Admin Center** **SharePoint aus.** Wenn das klassische SharePoint Admin Center angezeigt wird, wählen Sie **Jetzt öffnen** am oberen Rand der Seite aus, um das neue SharePoint Admin Center zu öffnen.

3. Wählen Sie im linken Bereich des neuen SharePoint Admin Center **Aktive Websites** aus.

4. Oben rechts auf der Seite sehen Sie die Menge des verwendeten Speichers für alle Websites und den Gesamtspeicher für Ihr Abonnement.  

   ![Speicherleiste auf der Seite „Aktive Websites“](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > Der verwendete Speicher enthält keine Änderungen, die innerhalb der letzten 24–48 Stunden vorgenommen wurden.

::: moniker-end

Nachdem Sie festgestellt haben, wie viel Speicherplatz Sie verwenden, können Sie Speicherplatz für Ihr Abonnement hinzufügen oder entfernen. Um herauszufinden, wie viel das Hinzufügen von Speicherplatz kosten wird, führen Sie die Schritte in diesem Artikel aus, und überprüfen Sie die Preisinformationen, bevor Sie den Kauf durchführen.
  
Informationen zum Festlegen von Speichergrenzwerte für Websitesammlungen finden Sie unter ["Verwalten von Speichergrenzwerte für Websitesammlungen".](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)
  
## <a name="add-storage-to-your-subscription"></a>Hinzufügen von Speicher zu Ihrem Abonnement

Wenn Sie noch keinen zusätzlichen Speicher für Ihr Abonnement erworben haben, können Sie dies tun.

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur **Seite** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">"Abrechnungskaufdienste".</a>
2. Wählen Sie unten auf der **Seite "Dienste** kaufen" die **Option "Add-Ons" aus.**
3. Wählen **Sie Office 365 Zusätzlichen Dateispeicher aus.**
4. Wählen Sie auf der **Seite "Zusätzlicher Dateispeicher für Office 365"** (falls angezeigt) das Basisabonnement aus, und geben Sie dann die Anzahl der Gigabyte an Speicher ein, die Sie hinzufügen möchten.
5. Wählen **Sie "Jetzt auschecken" aus.**
6. Überprüfen Sie auf der Seite "Wie sieht dies **aus?",** wie viele Gigabyte Speicherplatz Sie ausgewählt haben, überprüfen Sie die Preisinformationen, und wählen Sie dann **"Weiter" aus.**
7. Überprüfen Sie **auf der Seite "Bestellung** abschließen" den Gesamtwert. Wenn Sie Änderungen vornehmen müssen, wählen Sie **"Bearbeiten" aus.** Wenn für die Bestellung eine Bonitätsprüfung erforderlich ist, aktivieren Sie das Kontrollkästchen. Wenn Sie fertig sind, wählen Sie **"Bestellung bestellen"** \> **auf "Admin Home" aus.**

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin  Center zur Seite "Abrechnungsabonnements". \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank"></a>  

2. Wählen Sie **auf der** Seite "Abonnements" das Abonnement aus, dem Sie Speicherplatz hinzufügen möchten, und wählen Sie dann **"Add-Ons" aus.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Wenn Sie keine **Add-Ons** sehen und Ihr Abonnement über einen Partner erworben wurde, wählen Sie Volume **Licensing Service Center (VLSC) aus.**
  
3. Wählen **Sie "Add-Ons kaufen" aus.**

    ![Kaufen Sie den Link "Add-Ons" auf der Seite "Abonnements" im Admin Center.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. Bewegen Oder tippen **Sie auf** der Seite "Dienste kaufen" mit der Maus auf den zusätzlichen Dateispeicher für **Office 365,** und wählen Sie dann **"Jetzt kaufen" aus.**
  
5. Geben Sie die Anzahl der benötigten Benutzerlizenzen ein, und wählen Sie, falls angezeigt, ein Basisabonnement aus. Wählen **Sie "Jetzt auschecken" aus.**
  
6. Überprüfen Sie auf der Seite "Wie sieht dies **aus?",** wie viele Gigabyte Speicherplatz Sie ausgewählt haben, überprüfen Sie die Preisinformationen, und wählen Sie dann **"Weiter" aus.**

7. Wählen Sie **auf der Seite "Bestellung abschließen"** die Option **"Bestellung bestellen" aus.**

::: moniker-end

::: moniker range="o365-21vianet"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnements</a>.

2. Wählen Sie **auf der** Seite "Abonnements" das Abonnement aus, dem Sie Speicherplatz hinzufügen möchten, und wählen Sie dann **"Add-Ons" aus.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Wenn Sie keine **Add-Ons** sehen und Ihr Abonnement über einen Partner erworben wurde, wählen Sie Volume **Licensing Service Center (VLSC) aus.**
  
3. Wählen **Sie "Add-Ons kaufen" aus.**

    ![Kaufen Sie den Link "Add-Ons" auf der Seite "Abonnements" im Admin Center.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. Bewegen Oder tippen **Sie auf** der Seite "Dienste kaufen" mit der Maus auf den zusätzlichen Dateispeicher für **Office 365,** und wählen Sie dann **"Jetzt kaufen" aus.**
  
5. Geben Sie die Anzahl der benötigten Benutzerlizenzen ein, und wählen Sie, falls angezeigt, ein Basisabonnement aus. Wählen **Sie "Jetzt auschecken" aus.**
  
6. Überprüfen Sie auf der Seite "Wie sieht dies **aus?",** wie viele Gigabyte Speicherplatz Sie ausgewählt haben, überprüfen Sie die Preisinformationen, und wählen Sie dann **"Weiter" aus.**

7. Wählen Sie **auf der Seite "Bestellung abschließen"** die Option **"Bestellung bestellen" aus.**

::: moniker-end

## <a name="increase-or-decrease-storage"></a>Vergrößern oder Verkleinern des Speicherplatzes

Wenn Sie bereits zusätzlichen Dateispeicher über das **Office 365-Add-On** "Zusätzlicher Dateispeicher" erworben haben, können Sie die folgenden Schritte ausführen, um den zusätzlichen Speicherplatz für Ihr Abonnement zu vergrößern oder zu verringern. Sie können den Speicher auf bis zu 1 Gigabyte reduzieren. Wenden Sie sich an den Support, um den zusätzlichen Speicherplatz [zu entfernen.](../admin/contact-support-for-business-products.md)

::: moniker range="o365-worldwide"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Wählen Sie **auf der** Registerkarte "Produkte" das Abonnement aus, das das **Office 365-Add-On "Zusätzlicher Dateispeicher"** enthält.
3. Wählen Sie auf der Seite "Produktdetails" im Abschnitt **"Add-Ons"** die Option **"Add-Ons verwalten" aus.**
4. Wählen Sie **im Bereich "Add-Ons** verwalten" in der **Add-On-Liste** die Option **"Office 365 Zusätzlicher Dateispeicher" aus.**
5. Geben Sie **im** Textfeld "Menge" die Anzahl der GBs an Speicherplatz ein, die Sie für das Abonnement wünschen.
6. Klicken Sie auf **Speichern**.

::: moniker-end

::: moniker range="o365-germany"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnements</a>.

2. Wählen Sie **auf der** Seite "Abonnements" die **Option "Add-Ons" aus.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Wenn Sie keine **Add-Ons** sehen und Ihr Abonnement über einen Partner erworben wurde, wählen Sie Volume **Licensing Service Center (VLSC) aus.**
  
3. Wählen **Sie unter Office 365 Zusätzlicher Dateispeicher** die Option **"Menge ändern" aus.**

    ![Link "Menge ändern"](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. Geben Sie im rechten Bereich die Gesamtzahl der benötigten Gigabyte ein, und wählen Sie **"Absenden" aus.**

    Wenn Sie derzeit über 200 Gigabyte an zusätzlichen Dateispeicher verfügen, jedoch nur 100 Gigabyte benötigen, geben Sie **100** in das Feld ein.

5. Wählen Sie **Schließen** aus.

::: moniker-end

::: moniker range="o365-21vianet"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnements</a>.

2. Wählen Sie **auf der** Seite "Abonnements" die **Option "Add-Ons" aus.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Wenn Sie keine **Add-Ons** sehen und Ihr Abonnement über einen Partner erworben wurde, wählen Sie Volume **Licensing Service Center (VLSC) aus.**
  
3. Wählen **Sie unter Office 365 Zusätzlicher Dateispeicher** die Option **"Menge ändern" aus.**

    ![Link "Menge ändern"](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. Geben Sie im rechten Bereich die Gesamtzahl der benötigten Gigabyte ein, und wählen Sie **"Absenden" aus.**

    Wenn Sie derzeit über 200 Gigabyte an zusätzlichen Dateispeicher verfügen, jedoch nur 100 Gigabyte benötigen, geben Sie **100** in das Feld ein.

5. Wählen Sie **Schließen** aus.

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a>Bin ich im Rahmen meines Plans für Office 365 Extra File Storage berechtigt?

Office 365 Extra File Storage steht im Rahmen der folgenden Abonnements zur Verfügung:
  
- Office 365 Enterprise E1

- Office 365 Enterprise E2

- Office 365 Enterprise E3

- Office 365 Enterprise E4

- Office 365 Enterprise E5

- Office für das Web mit SharePoint Plan 1

- Office für das Web mit SharePoint Plan 2

- SharePoint Online Plan 1

- SharePoint Online Plan 2

- Microsoft 365 Business Basic

- Microsoft 365 Business Standard

- Microsoft 365 Business Premium

- Microsoft 365 E3

- Microsoft 365 E5

- Microsoft 365 F1

> [!NOTE]
> Office 365 Zusätzlicher Dateispeicher ist auch für GCC-, GCC High- und DOD-Pläne verfügbar.

## <a name="related-content"></a>Verwandte Inhalte

[Verwalten von Websitespeichergrenzwerte](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (Artikel)\
[Festlegen des Standardspeicherplatzes für #A0](https://docs.microsoft.com/onedrive/set-default-storage-space)(Artikel)
