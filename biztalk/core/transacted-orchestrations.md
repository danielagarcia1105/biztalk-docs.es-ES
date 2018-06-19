---
title: Transacciones orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- orchestrations, transactional
- Transaction Type property
ms.assetid: c4f0b6ca-d939-4d3a-b7ef-53c6aafdea9c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8c6fb466e0c3cc5cae4a076237d1dbc970b5794
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278740"
---
# <a name="transacted-orchestrations"></a><span data-ttu-id="143d8-102">Orquestaciones configuradas como transacciones</span><span class="sxs-lookup"><span data-stu-id="143d8-102">Transacted Orchestrations</span></span>
<span data-ttu-id="143d8-103">Las orquestaciones pueden ser transaccionales, al igual que los ámbitos.</span><span class="sxs-lookup"><span data-stu-id="143d8-103">Orchestrations can be transactional, just like scopes.</span></span> <span data-ttu-id="143d8-104">De hecho, una orquestación puede considerarse un ámbito.</span><span class="sxs-lookup"><span data-stu-id="143d8-104">In fact, an orchestration can itself be considered a scope.</span></span> <span data-ttu-id="143d8-105">Por lo general, se aplican las mismas reglas a las orquestaciones configuradas como transacciones que para los ámbitos configurados como orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="143d8-105">In general, the same rules apply for transacted orchestrations as for transacted scopes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="143d8-106">Una diferencia entre las orquestaciones y otros ámbitos es que las orquestaciones no tienen controladores de excepciones.</span><span class="sxs-lookup"><span data-stu-id="143d8-106">One difference between orchestrations and other scopes is that orchestrations do not have exception handlers.</span></span>  
  
## <a name="orchestration-compensation"></a><span data-ttu-id="143d8-107">Compensación de orquestación</span><span class="sxs-lookup"><span data-stu-id="143d8-107">Orchestration compensation</span></span>  
 <span data-ttu-id="143d8-108">Si el **tipo de transacción** propiedad para la orquestación está establecida en larga ejecución o atómica, también puede seleccionar un valor para el **compensación** propiedad, que puede ser predeterminado o personalizado.</span><span class="sxs-lookup"><span data-stu-id="143d8-108">If the **Transaction Type** property for your orchestration is set to long-running or atomic, you can also select a value for the **Compensation** property, which can be Default or Custom.</span></span>  
  
 <span data-ttu-id="143d8-109">Si selecciona **personalizado** para la compensación, un **compensación** ficha aparecerá junto a la superficie de diseño de orquestación.</span><span class="sxs-lookup"><span data-stu-id="143d8-109">If you select **Custom** for the compensation, a **Compensation** tab will appear alongside the Orchestration Design Surface.</span></span> <span data-ttu-id="143d8-110">Tiene la misma apariencia que la superficie de diseño de orquestación y puede agregar formas y puertos a ella de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="143d8-110">It will look the same as the Orchestration Design Surface, and you can add shapes and ports to it in the same way.</span></span>  
  
 <span data-ttu-id="143d8-111">Las compensaciones solo tienen lugar en las orquestaciones a las que llaman otras orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="143d8-111">Compensations only take place on orchestrations that are called by other orchestrations.</span></span> <span data-ttu-id="143d8-112">Puede compensar una instancia de orquestación específica mediante el uso de la **identificador** propiedad en el **orquestación de llamada** forma.</span><span class="sxs-lookup"><span data-stu-id="143d8-112">You can compensate a specific orchestration instance by using the **Identifier** property on the **Call Orchestration** shape.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="143d8-113">Si existe una compensación en una orquestación de nivel superior, el motor de tiempo de ejecución la omitirá.</span><span class="sxs-lookup"><span data-stu-id="143d8-113">If a compensation exists on a top-level orchestration, it will be ignored by the runtime engine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="143d8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="143d8-114">See Also</span></span>  
 <span data-ttu-id="143d8-115">[Realizar orquestaciones transaccionales](../core/making-orchestrations-transactional.md) </span><span class="sxs-lookup"><span data-stu-id="143d8-115">[Making Orchestrations Transactional](../core/making-orchestrations-transactional.md) </span></span>  
 [<span data-ttu-id="143d8-116">Uso de transacciones y control de excepciones</span><span class="sxs-lookup"><span data-stu-id="143d8-116">Using Transactions and Handling Exceptions</span></span>](../core/using-transactions-and-handling-exceptions.md)