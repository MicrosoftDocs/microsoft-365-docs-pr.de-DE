---
title: Anheften von apps an das App-Startfeld Ihrer Benutzer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Als globaler Administrator können Sie bis zu drei apps an das App-Startfeld Ihrer Benutzer anheften.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310875"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Anheften von apps an das App-Startfeld Ihrer Benutzer

Sie können Steuerelemente im Azure Active Directory-Portal verwenden, um bis zu drei apps an Office.com und das App-Startfeld für alle Benutzer in Ihrer Organisation zu fixieren. Sie können auch Gruppen von Anwendungen organisieren. Alle hinzugefügten Apps können später vom Benutzer jederzeit wieder aufgehoben werden. Um eine APP für Ihre Benutzer zu fixieren, müssen Sie ein Cloud-Anwendungsadministrator oder Anwendungsadministrator in Azure Active Directory oder ein globaler Administrator in Office 365 sein. Weitere Informationen zu Administratorrollen finden Sie unter [Administratorrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) und [Administratorrollen in Microsoft 365](../add-users/about-admin-roles.md). 

Weitere Informationen zum App-Startfeld und Office.com finden Sie unter [Meet the App Launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) und [Updates to Office.com and the-Office 365 App Launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) Blog article.

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Verwenden des Azure Active Directory-Portals zum Anheften von apps

1. Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .
2. Wählen Sie im linken Navigationsbereich **Alle anzeigen**aus, und wählen Sie unter **Admin Center**die Option **Azure Active Directory**aus.
3. Wählen Sie in **Azure Active Directory**die Option **Enterprise Applications**  >  **Users Settings**aus.
4. Wählen Sie im Abschnitt **Office 365 Einstellungen** die Option **Anwendung hinzufügen**aus.
5. Wählen Sie die Anwendungen aus, die Sie an das App-Startfeld von Benutzern anheften möchten, und wählen Sie dann **Hinzufügen**aus.

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365-Einstellungen zum Anheften von apps.":::

### <a name="pin-a-custom-app"></a>Anheften einer benutzerdefinierten App

> [!NOTE]
> Auf der Benutzeroberfläche wird angegeben, ob Sie zusätzliche Azure AD Lizenzen erwerben müssen, um diese Funktion nutzen zu können. Weitere Informationen finden Sie unter [Azure Active Directory Pricing](https://azure.microsoft.com/pricing/details/active-directory/).

1. Wählen Sie in **Azure Active Directory**unter **Enterprise Applications**  >  **New Application** oben auf der Seite **alle Anwendungen** .
2. Wählen Sie auf der Seite **Anwendung hinzufügen** die Option **nicht-Kataloganwendung** aus, oder erstellen Sie eine **eigene Anwendung** , wenn Sie sich in der Vorschauversion von Azure Active Directory befinden. 
3. Geben Sie einen Namen für die Anwendung ein, und weisen Sie dann den Benutzer auf der Registerkarte **Benutzer und Gruppen** zu.
4. Verwenden Sie die Registerkarte **Eigenschaften** , um ein Symbol für die APP hochzuladen.
5. Um der App eine URL zuzuweisen, wählen Sie auf der Registerkarte **einmaliges Anmelden** die Option **verknüpft** aus, und geben Sie dann eine URL ein.
6. Wählen Sie **Speichern** aus.

## <a name="create-application-collections"></a>Erstellen von Anwendungssammlungen

Sie können auch Anwendungssammlungen für die Benutzer in Ihrer Organisation erstellen. Anweisungen finden Sie unter [Erstellen von Sammlungen im Portal "meine apps" im Azure-Portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).