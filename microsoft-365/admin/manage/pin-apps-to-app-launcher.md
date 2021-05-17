---
title: Anheften von Apps an das App-Startfeld Ihrer Benutzer
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Als globaler Administrator können Sie bis zu drei Apps an das App-Startfeld Ihrer Benutzer anheften.
ms.openlocfilehash: 786368f1236c7a86a6fbd0dd863ad0296cb65fac
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579266"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Anheften von Apps an das App-Startfeld Ihrer Benutzer

Sie können Steuerelemente im Azure Active Directory-Portal verwenden, um bis zu drei Apps an Office.com und das App-Startfeld für alle Benutzer in Ihrer Organisation anheften. Sie können auch Gruppen von Anwendungen organisieren. Jede app, die Sie hinzufügen, kann später vom Benutzer jederzeit entpinned werden. Zum Anheften einer App für Ihre Benutzer müssen Sie ein Cloudanwendungsadministrator oder Anwendungsadministrator in Azure Active Directory oder ein globaler Administrator in Office 365. Weitere Informationen zu Administratorrollen finden Sie unter [Administratorrollen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) und [Administratorrollen in Microsoft 365](../add-users/about-admin-roles.md). 

Weitere Informationen zum App-Startfeld und zu Office.com finden Sie unter Meet [the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) [and updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Verwenden des Azure Active Directory zum Anheften von Apps

1. Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .
2. Wählen Sie im linken Navigations navi die Option **Alle anzeigen** aus, und wählen Sie unter **Admin Center** die Option **Azure Active Directory**.
3. Wählen **Azure Active Directory** in den **Enterprise**  >  **Benutzereinstellungen aus.**
4. Wählen Sie **Office 365 Einstellungen** im Abschnitt "Anwendung **hinzufügen" aus.**
5. Wählen Sie die Anwendungen aus, die Sie an das App-Startfeld der Benutzer anheften möchten, und wählen Sie dann **Hinzufügen aus.**

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365 Einstellungen zum Anheften von Apps.":::

### <a name="pin-a-custom-app"></a>Anheften einer benutzerdefinierten App

> [!NOTE]
> Die Benutzeroberfläche gibt an, ob Sie zusätzliche Azure AD-Lizenzen erwerben müssen, um dieses Feature zu verwenden. Weitere Informationen finden Sie [unter Azure Active Directory Preise](https://azure.microsoft.com/pricing/details/active-directory/).

1. Wählen **Azure Active Directory** auf **der Seite Alle** Anwendungen Enterprise Neue  >   **Anwendung** aus.
2. Wählen Sie auf der **Seite** Anwendung hinzufügen die Option **Nicht kataloganwendung** oder **Erstellen** Einer eigenen Anwendung aus, wenn Sie sich in der Vorschauversion von Azure Active Directory. 
3. Geben Sie einen Namen für die Anwendung ein, und weisen Sie dann auf der Registerkarte Benutzer **und Gruppen einen Benutzer** zu.
4. Verwenden Sie die **Registerkarte** Eigenschaften, um ein Symbol für die App hochzuladen.
5. Um der App eine URL  zuzuordnen, wählen Sie auf der Registerkarte Einmaliges Anmelden die Option **Verknüpft** aus, und geben Sie dann eine URL ein.
6. Wählen Sie **Speichern** aus.

## <a name="create-application-collections"></a>Erstellen von Anwendungssammlungen

Sie können auch Anwendungssammlungen für die Benutzer in Ihrer Organisation erstellen. Anweisungen finden Sie unter [Erstellen von Sammlungen im Portal "Meine Apps" im Azure-Portal](/azure/active-directory/manage-apps/access-panel-collections).