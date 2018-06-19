---
title: Getuserkey (operación) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9353a7f0-9bbd-4cfa-92e6-ed2b86e3a88e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0701ff1df912cc113205bad573b6cebc0f02a13a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246124"
---
# <a name="getuserkey"></a><span data-ttu-id="c4fac-102">GetUserKey (operación)</span><span class="sxs-lookup"><span data-stu-id="c4fac-102">GetUserKey</span></span>
<span data-ttu-id="c4fac-103">Inserta la clave usuario actual en la pila.</span><span class="sxs-lookup"><span data-stu-id="c4fac-103">Pushes the current user key onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4fac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4fac-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserKey" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4fac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4fac-105">Parameters</span></span>  
 <span data-ttu-id="c4fac-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c4fac-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="c4fac-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="c4fac-107">Pushed Value</span></span>  
 <span data-ttu-id="c4fac-108">Cadena que contiene la clave del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="c4fac-108">String containing the current user key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4fac-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c4fac-109">Remarks</span></span>  
 <span data-ttu-id="c4fac-110">Esta operación sólo es válida en las puntos de seguimiento del usuario.</span><span class="sxs-lookup"><span data-stu-id="c4fac-110">This operation is valid only in user track points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4fac-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4fac-111">Example</span></span>  
 <span data-ttu-id="c4fac-112">El siguiente ejemplo contiene un filtro de evento que se evaluará como `true` cuando la clave del usuario es igual a "DocumentUrl".</span><span class="sxs-lookup"><span data-stu-id="c4fac-112">The following sample contains an event filter expression that will evaluate to `true` when the user key is equal to "DocumentUrl".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>DocumentUrl</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```