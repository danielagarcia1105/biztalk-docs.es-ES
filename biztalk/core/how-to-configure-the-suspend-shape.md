---
title: Cómo configurar la forma suspender | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Suspend shapes
- Suspend shape [Orchestration Designer], literal strings
- Suspend shape [Orchestration Designer], configuring
- Suspend shape [Orchestration Designer]
- atomic transactions, Suspend shape [Orchestration Designer]
- Suspend shape [Orchestration Designer], atomic transactions
- Suspend shape [Orchestration Designer], about Suspend shape
ms.assetid: 62fbb6d4-78d2-4671-84bb-909cbf6b0ec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c846001b5a2b39a4e23e0d06ed56fb91c8863832
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248524"
---
# <a name="how-to-configure-the-suspend-shape"></a><span data-ttu-id="5a50d-102">Cómo configurar la forma Suspender</span><span class="sxs-lookup"><span data-stu-id="5a50d-102">How to Configure the Suspend Shape</span></span>
![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")  
<span data-ttu-id="5a50d-103">Forma Suspender</span><span class="sxs-lookup"><span data-stu-id="5a50d-103">Suspend shape</span></span>  
  
 <span data-ttu-id="5a50d-104">Cuando se suspende una instancia de orquestación, se registra un error.</span><span class="sxs-lookup"><span data-stu-id="5a50d-104">When an orchestration instance is suspended, an error is logged.</span></span> <span data-ttu-id="5a50d-105">Puede especificar una cadena de mensaje que acompañe al error para ayudar al administrador a diagnosticar la situación.</span><span class="sxs-lookup"><span data-stu-id="5a50d-105">You can specify a message string to accompany the error to help the administrator diagnose the situation.</span></span>  
  
 <span data-ttu-id="5a50d-106">Se guarda toda la información de estado de la instancia de orquestación y se vuelve a establecer cuando el administrador reanude la instancia de orquestación.</span><span class="sxs-lookup"><span data-stu-id="5a50d-106">All of the state information for the orchestration instance is saved, and is reinstated if and when the administrator resumes the orchestration instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a50d-107">Si un **Suspend** forma existe en una orquestación que se ha llamado de forma sincrónica (igual que con la **llamar a** forma) por otra orquestación, la instancia anidada y todas las instancias de orquestación envolvente le se suspende.</span><span class="sxs-lookup"><span data-stu-id="5a50d-107">If a **Suspend** shape exists in an orchestration that has been called synchronously (as with the **Call** shape) by another orchestration, the nested instance and all enclosing orchestration instances will be suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a50d-108">No se puede colocar una **Suspend** forma dentro de una transacción atómica.</span><span class="sxs-lookup"><span data-stu-id="5a50d-108">You cannot place a **Suspend** shape inside an atomic transaction.</span></span>  
  
### <a name="to-configure-a-suspend-shape"></a><span data-ttu-id="5a50d-109">Para configurar una forma Suspender</span><span class="sxs-lookup"><span data-stu-id="5a50d-109">To configure a Suspend shape</span></span>  
  
-   <span data-ttu-id="5a50d-110">Puede usar el **mensaje de Error** propiedad para especificar el texto que desea que estén registrados cuando un **Suspend** forma se encuentra.</span><span class="sxs-lookup"><span data-stu-id="5a50d-110">You can use the **Error Message** property to specify text that you want to be logged when a **Suspend** shape is encountered.</span></span> <span data-ttu-id="5a50d-111">Este texto puede ser una cadena literal o una expresión que se evalúa como un **System.String**.</span><span class="sxs-lookup"><span data-stu-id="5a50d-111">This text may be a literal string, or an expression that evaluates to a **System.String**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="5a50d-112">Si escribe una cadena literal, ésta debe ir entre comillas.</span><span class="sxs-lookup"><span data-stu-id="5a50d-112">If you enter a literal string, you must enclose it in quotation marks.</span></span>