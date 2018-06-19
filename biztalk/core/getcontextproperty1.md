---
title: GetContextProperty1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8867c29-63de-4a13-9ef9-8c6ab8ea3443
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65b7ffffe4b21e3317b920ac50cdc27b12d708d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246268"
---
# <a name="getcontextproperty"></a><span data-ttu-id="c76a4-102">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="c76a4-102">GetContextProperty</span></span>
<span data-ttu-id="c76a4-103">Inserta la propiedad de contexto solicitada en la pila.</span><span class="sxs-lookup"><span data-stu-id="c76a4-103">Pushes the requested context property onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c76a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c76a4-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name ="GetContextProperty">  
  <wcf:Argument>EventTime</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c76a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c76a4-105">Parameters</span></span>  
 <span data-ttu-id="c76a4-106">Uno de los siguientes nombres de propiedad de contexto:</span><span class="sxs-lookup"><span data-stu-id="c76a4-106">One of the following context property names:</span></span>  
  
|<span data-ttu-id="c76a4-107">Nombre de propiedad de contexto</span><span class="sxs-lookup"><span data-stu-id="c76a4-107">Context property name</span></span>|<span data-ttu-id="c76a4-108">Description</span><span class="sxs-lookup"><span data-stu-id="c76a4-108">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="c76a4-109">EventTime</span><span class="sxs-lookup"><span data-stu-id="c76a4-109">EventTime</span></span>|<span data-ttu-id="c76a4-110">Fecha y hora actuales.</span><span class="sxs-lookup"><span data-stu-id="c76a4-110">Current date and time.</span></span>|  
|<span data-ttu-id="c76a4-111">SessionId</span><span class="sxs-lookup"><span data-stu-id="c76a4-111">SessionId</span></span>|<span data-ttu-id="c76a4-112">Id. de sesión de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c76a4-112">Workflow session id.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c76a4-113">Los nombres de propiedades de contexto distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c76a4-113">The context property names are case-sensitive.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="c76a4-114">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="c76a4-114">Pushed Value</span></span>  
 <span data-ttu-id="c76a4-115">Cadena que contiene la propiedad de contexto solicitada.</span><span class="sxs-lookup"><span data-stu-id="c76a4-115">String containing the requested context property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c76a4-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c76a4-116">Remarks</span></span>  
 <span data-ttu-id="c76a4-117">La hora se almacena en formato UTC en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c76a4-117">Time is stored in UTC format inside of the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c76a4-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c76a4-118">Example</span></span>  
 <span data-ttu-id="c76a4-119">En la siguiente expresión de actualización de ejemplo, la fecha de aprobación se obtiene al recuperar la hora del evento actual.</span><span class="sxs-lookup"><span data-stu-id="c76a4-119">In the following sample update expression, the approval date is retrieved by retrieving the event time of the current event.</span></span>  
  
```  
<ic:Update DataItemName ="Approval Date" Type ="DATETIME">  
  <ic:Expression>  
    <wcf:Operation Name ="GetContextProperty">  
      <wcf:Argument>EventTime</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
 <span data-ttu-id="c76a4-120">Es un uso común de `GetContextProperty`.</span><span class="sxs-lookup"><span data-stu-id="c76a4-120">This is a common use of `GetContextProperty`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c76a4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c76a4-121">See Also</span></span>  
 [<span data-ttu-id="c76a4-122">Operaciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="c76a4-122">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)