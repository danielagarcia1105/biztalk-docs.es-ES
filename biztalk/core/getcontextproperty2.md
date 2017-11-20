---
title: GetContextProperty2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2554a210-cfb4-4b63-9afa-ffe2a853ba7b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f834bf1271f6706c332123d8b1835e0bd730f069
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getcontextproperty"></a><span data-ttu-id="f4531-102">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="f4531-102">GetContextProperty</span></span>
<span data-ttu-id="f4531-103">Inserta la propiedad de contexto solicitada en la pila.</span><span class="sxs-lookup"><span data-stu-id="f4531-103">Pushes the requested context property onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4531-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4531-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetContextProperty">  
  <wf:Argument>ContextPropertyName</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4531-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4531-105">Parameters</span></span>  
 <span data-ttu-id="f4531-106">Uno de los siguientes nombres de propiedad de contexto:</span><span class="sxs-lookup"><span data-stu-id="f4531-106">One of the following context property names:</span></span>  
  
|<span data-ttu-id="f4531-107">Nombre de propiedad de contexto</span><span class="sxs-lookup"><span data-stu-id="f4531-107">Context property name</span></span>|<span data-ttu-id="f4531-108">Description</span><span class="sxs-lookup"><span data-stu-id="f4531-108">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="f4531-109">EventTime</span><span class="sxs-lookup"><span data-stu-id="f4531-109">EventTime</span></span>|<span data-ttu-id="f4531-110">Fecha y hora actuales.</span><span class="sxs-lookup"><span data-stu-id="f4531-110">Current date and time.</span></span>|  
|<span data-ttu-id="f4531-111">InstanceID</span><span class="sxs-lookup"><span data-stu-id="f4531-111">InstanceId</span></span>|<span data-ttu-id="f4531-112">Id. de instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f4531-112">Workflow instance ID.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="f4531-113">Los nombres de propiedades de contexto distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f4531-113">The context property names are case-sensitive.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="f4531-114">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="f4531-114">Pushed Value</span></span>  
 <span data-ttu-id="f4531-115">Cadena que contiene la propiedad de contexto solicitada.</span><span class="sxs-lookup"><span data-stu-id="f4531-115">String containing the requested context property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4531-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4531-116">Remarks</span></span>  
 <span data-ttu-id="f4531-117">La hora se almacena en formato UTC en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f4531-117">Time is stored in UTC format inside of the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4531-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4531-118">Example</span></span>  
 <span data-ttu-id="f4531-119">En el ejemplo siguiente, una expresión para extraer el **InstanceId** se usa en un bloque correlationID para establecer el identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="f4531-119">In the following sample, an expression for pulling the **InstanceId** is used inside of a correlationID block to set the correlation ID.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>InstanceId</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 <span data-ttu-id="f4531-120">Es un uso común de `GetContextProperty`.</span><span class="sxs-lookup"><span data-stu-id="f4531-120">This is a common use of `GetContextProperty`.</span></span>