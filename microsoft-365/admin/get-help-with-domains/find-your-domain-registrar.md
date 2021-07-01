---
title: Suchen der Domänenregistrierungsstelle
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Erfahren Sie, wie Sie Ihre Domänenregistrierungsstelle und den DNS-Hostinganbieter mithilfe der InterNIC-Suche finden.
ms.openlocfilehash: 77e4776946d51cb4f8dfe1a746e85d74a9e0a700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228027"
---
# <a name="find-your-domain-registrar"></a>Suchen der Domänenregistrierungsstelle

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.

## <a name="domain-registrar"></a>Domänenregistrierungsstelle

### <a name="find-your-domain-name-registrar"></a>Finden Ihrer Domänenregistrierungsstelle

> [!NOTE]
> Nur Domänen, die mit *.COM*, *.NET* und *.EDU* enden, funktionieren mit diesem Tool.

1. Geben Sie auf der [InterNIC-Suchseite](https://go.microsoft.com/fwlink/p/?LinkId=402770) im Feld **Whois-Suche** Ihre Domäne ein, beispielsweise *contoso.com.*

2. Wählen Sie die Option **Domäne** aus, und klicken Sie dann auf **Übermitteln**.

3. Suchen Sie auf der Seite **Whois-Suchergebnisse** nach dem Eintrag **Registrierungsstelle**. Hier finden Sie die Organisation, die den Registrierungsstellendienst für Ihre Domäne bereitstellt.

## <a name="dns-hosting-provider"></a>DNS-Hostinganbieter

### <a name="find-your-dns-hosting-provider"></a>Finden Ihres DNS-Hostinganbieters

> [!NOTE]
> Nur Domänen, die mit *.COM*, *.NET* und *.EDU* enden, funktionieren mit diesem Tool.

1. Geben Sie auf der [InterNIC-Suchseite](https://go.microsoft.com/fwlink/p/?LinkId=402770) im Feld **Whois-Suche** Ihre Domäne ein, beispielsweise contoso.com.

2. Wählen Sie die Option **Domain** aus, und klicken Sie dann auf **Submit**.

3. Suchen Sie auf der Seite **Whois Search Results** nach dem ersten **Name Server**-Eintrag.

4. Kopieren Sie die nach dem Doppelpunkt (:) angezeigten Informationen zum Namensserver (Name Server, NS), und fügen Sie diese oben auf der Seite in das Feld **Suche** ein. Wählen Sie **Namensserver** aus, und klicken Sie dann auf **Übermitteln**.

5. Suchen Sie auf der Seite **Whois Search Results** nach dem Eintrag **Registrar**. Hier finden Sie Ihren DNS-Hostinganbieter, den DNS-Dienstanbieter, dem der Namenserver für Ihre Domäne gehört.

---

