---
title: GetActivityEvent | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fe824c9-4cea-44da-b830-5520d67988e0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fb039c0e9946091214a52fbb605753a212c233c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246252"
---
# <a name="getactivityevent"></a><span data-ttu-id="4b241-102">GetActivityEvent (operación)</span><span class="sxs-lookup"><span data-stu-id="4b241-102">GetActivityEvent</span></span>
<span data-ttu-id="4b241-103">Inserta el nombre del evento de la actividad en curso en la pila.</span><span class="sxs-lookup"><span data-stu-id="4b241-103">Pushes the name of the current activity event onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b241-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b241-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityEvent"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b241-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b241-105">Parameters</span></span>  
 <span data-ttu-id="4b241-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4b241-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="4b241-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="4b241-107">Pushed Value</span></span>  
 <span data-ttu-id="4b241-108">Cadena que contiene el evento de actividad en curso.</span><span class="sxs-lookup"><span data-stu-id="4b241-108">String containing the current activity event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b241-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4b241-109">Remarks</span></span>  
 <span data-ttu-id="4b241-110">Una actividad de flujo de trabajo puede pasar por varios estados durante el período de vida del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4b241-110">A workflow activity can pass through several states during the lifetime of the workflow.</span></span> <span data-ttu-id="4b241-111">El interceptor de BAM de Windows Workflow Foundation es compatible con la mayoría de los valores de estado de ejecución definidos por la enumeración de `System.Workflow.ComponentModel.ActivityExecutionStatus`, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="4b241-111">The Windows Workflow Foundation BAM interceptor supports most of the execution status values defined by the `System.Workflow.ComponentModel.ActivityExecutionStatus` enumeration, as shown in the following table.</span></span>  
  
|<span data-ttu-id="4b241-112">Estado de ejecución</span><span class="sxs-lookup"><span data-stu-id="4b241-112">Execution status</span></span>|<span data-ttu-id="4b241-113">Description</span><span class="sxs-lookup"><span data-stu-id="4b241-113">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="4b241-114">Cancelando</span><span class="sxs-lookup"><span data-stu-id="4b241-114">Canceling</span></span>|<span data-ttu-id="4b241-115">Representa el estado en el que la actividad está siendo cancelada.</span><span class="sxs-lookup"><span data-stu-id="4b241-115">Represents the status when an activity is in the process of being canceled.</span></span>|  
|<span data-ttu-id="4b241-116">Cerrado</span><span class="sxs-lookup"><span data-stu-id="4b241-116">Closed</span></span>|<span data-ttu-id="4b241-117">Representa el estado en el que una actividad se ha cerrado.</span><span class="sxs-lookup"><span data-stu-id="4b241-117">Represents the status when an activity is closed.</span></span>|  
|<span data-ttu-id="4b241-118">Compensando</span><span class="sxs-lookup"><span data-stu-id="4b241-118">Compensating</span></span>|<span data-ttu-id="4b241-119">Representa el estado en el que una actividad se está compensando.</span><span class="sxs-lookup"><span data-stu-id="4b241-119">Represents the status when an activity is compensating.</span></span>|  
|<span data-ttu-id="4b241-120">Ejecutando</span><span class="sxs-lookup"><span data-stu-id="4b241-120">Executing</span></span>|<span data-ttu-id="4b241-121">Representa el estado en el que una actividad se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="4b241-121">Represents the status when an activity is executing.</span></span>|  
|<span data-ttu-id="4b241-122">Con errores</span><span class="sxs-lookup"><span data-stu-id="4b241-122">Faulting</span></span>|<span data-ttu-id="4b241-123">Representa el estado en el que una actividad es errónea.</span><span class="sxs-lookup"><span data-stu-id="4b241-123">Represents the status when an activity is faulting.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="4b241-124">No puede usar `GetActivityEvent` ni `GetWorkflowEvent` en el mismo elemento OnEvent.</span><span class="sxs-lookup"><span data-stu-id="4b241-124">You cannot use both `GetActivityEvent` and `GetWorkflowEvent` in the same OnEvent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b241-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b241-125">Example</span></span>  
 <span data-ttu-id="4b241-126">El siguiente ejemplo contiene una expresión de filtro de eventos configurada para buscar una actividad específica, FoodAndDringPolicy, en un flujo de trabajo cerrado.</span><span class="sxs-lookup"><span data-stu-id="4b241-126">The following sample contains an event filter expression configured to find a specific activity—FoodAndDringPolicy—in a Closed workflow.</span></span> <span data-ttu-id="4b241-127">Para ello, se usa una combinación de operaciones, incluidas `GetActivityEvent`, `GetActivityName` y operaciones lógicas.</span><span class="sxs-lookup"><span data-stu-id="4b241-127">This is done by using a combination of operations including `GetActivityEvent`, `GetActivityName`, and logical operations.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="4b241-128">Este patrón de filtro es habitual con los archivos de configuración del interceptor de Windows Workflow Foundation.</span><span class="sxs-lookup"><span data-stu-id="4b241-128">This filter pattern is common with Windows Workflow Foundation interceptor configuration files.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b241-129">Los argumentos no requieren comillas dobles a menos que intente hacer coincidir, de forma explícita, una cadena que contiene comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="4b241-129">Arguments do not require quotation marks unless you are explicitly trying to match a string that contains quotation marks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b241-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b241-130">See Also</span></span>  
 [<span data-ttu-id="4b241-131">Enumeración System.Workflow.ComponentModel.ActivityExecutionStatus</span><span class="sxs-lookup"><span data-stu-id="4b241-131">System.Workflow.ComponentModel.ActivityExecutionStatus enumeration</span></span>](http://go.microsoft.com/fwlink/?LinkId=119570)