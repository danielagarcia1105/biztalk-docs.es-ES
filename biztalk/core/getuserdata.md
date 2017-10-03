---
title: GetUserData | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c243555b-109f-47e3-8084-ab13a8e22ac5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57bc0ffcefc00e9fae20c7b2c8449c21c549b377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getuserdata"></a><span data-ttu-id="b7f4b-102">GetUserData (operación)</span><span class="sxs-lookup"><span data-stu-id="b7f4b-102">GetUserData</span></span>
<span data-ttu-id="b7f4b-103">Inserta los datos del usuario actual en la pila.</span><span class="sxs-lookup"><span data-stu-id="b7f4b-103">Pushes the current user data onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7f4b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7f4b-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserData" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7f4b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7f4b-105">Parameters</span></span>  
 <span data-ttu-id="b7f4b-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b7f4b-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="b7f4b-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="b7f4b-107">Pushed Value</span></span>  
 <span data-ttu-id="b7f4b-108">Cadena que contiene los datos del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="b7f4b-108">String containing the current user data.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7f4b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7f4b-109">Remarks</span></span>  
 <span data-ttu-id="b7f4b-110">Esta operación no es válida dentro de un filtro.</span><span class="sxs-lookup"><span data-stu-id="b7f4b-110">This operation is not valid inside of a filter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7f4b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7f4b-111">Example</span></span>  
 <span data-ttu-id="b7f4b-112">El ejemplo siguiente contiene una expresión de actualización para el elemento de datos "UserData" mediante la operación `GetUserData`.</span><span class="sxs-lookup"><span data-stu-id="b7f4b-112">The following sample contains an update expression for the data item "UserData" using the `GetUserData` operation.</span></span>  
  
```  
<ic:Update DataItemName="UserData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetUserData" />  
  </ic:Expression>  
</ic:Update>  
```