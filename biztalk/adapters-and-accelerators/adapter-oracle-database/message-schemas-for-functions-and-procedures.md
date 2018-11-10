---
title: Los esquemas de mensajes para las funciones y procedimientos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functions and procedures, message structure of
- functions and procedures, message actions of
ms.assetid: 90b77b15-a4c6-487d-a09e-a078ceddfd1e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0d44d12bab47aba1335261970a11199b86803a2
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752884"
---
# <a name="message-schemas-for-functions-and-procedures"></a><span data-ttu-id="c2ff4-102">Esquemas de mensaje para funciones y procedimientos</span><span class="sxs-lookup"><span data-stu-id="c2ff4-102">Message Schemas for Functions and Procedures</span></span>
<span data-ttu-id="c2ff4-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] funciones y procedimientos almacenados como operaciones de base de datos Oracle superficies.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces Oracle database functions and stored procedures as operations.</span></span> <span data-ttu-id="c2ff4-104">En esta sección se describe la estructura de mensaje y acciones que se usan para invocar funciones y procedimientos.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-104">This section describes the message structure and actions used to invoke functions and procedures.</span></span>  

## <a name="message-structure-of-functions-and-procedures"></a><span data-ttu-id="c2ff4-105">Estructura de los mensajes de funciones y procedimientos</span><span class="sxs-lookup"><span data-stu-id="c2ff4-105">Message Structure of Functions and Procedures</span></span>  
 <span data-ttu-id="c2ff4-106">Las operaciones se exponen para las funciones y procedimientos almacenados siguen un patrón de intercambio de mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-106">The operations surfaced for functions and stored procedures follow a request-response message exchange pattern.</span></span> <span data-ttu-id="c2ff4-107">En la tabla siguiente se muestra la estructura de estos mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-107">The following table shows the structure of these request and response messages.</span></span>  

|<span data-ttu-id="c2ff4-108">Operación</span><span class="sxs-lookup"><span data-stu-id="c2ff4-108">Operation</span></span>|<span data-ttu-id="c2ff4-109">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="c2ff4-109">XML Message</span></span>|<span data-ttu-id="c2ff4-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2ff4-110">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="c2ff4-111">Solicitud de procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="c2ff4-111">Stored Procedure Request</span></span>|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|<span data-ttu-id="c2ff4-112">Admite parámetros IN de Oracle y en espera en el cuerpo del mensaje</span><span class="sxs-lookup"><span data-stu-id="c2ff4-112">Supports Oracle IN and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="c2ff4-113">Respuesta de procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="c2ff4-113">Stored Procedure Response</span></span>|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|<span data-ttu-id="c2ff4-114">Admite los parámetros OUT de Oracle y en espera en el cuerpo del mensaje</span><span class="sxs-lookup"><span data-stu-id="c2ff4-114">Supports Oracle OUT and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="c2ff4-115">Solicitud de función</span><span class="sxs-lookup"><span data-stu-id="c2ff4-115">Function Request</span></span>|`<[FN_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|<span data-ttu-id="c2ff4-116">Admite parámetros IN de Oracle y en espera en el cuerpo del mensaje</span><span class="sxs-lookup"><span data-stu-id="c2ff4-116">Supports Oracle IN and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="c2ff4-117">Respuesta de la función</span><span class="sxs-lookup"><span data-stu-id="c2ff4-117">Function Response</span></span>|`<[FN_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|<span data-ttu-id="c2ff4-118">Admite los parámetros OUT de Oracle y en espera en el cuerpo del mensaje</span><span class="sxs-lookup"><span data-stu-id="c2ff4-118">Supports Oracle OUT and IN OUT parameters in the message body</span></span><br /><br /> <span data-ttu-id="c2ff4-119">-El valor devuelto de función se devuelve en el `<[FN_NAME]Result\>` elemento.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-119">- The function return value is returned in the `<[FN_NAME]Result\>` element.</span></span> <span data-ttu-id="c2ff4-120">Este es el primer elemento en el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-120">This is the first element in the response message.</span></span> <span data-ttu-id="c2ff4-121">Viene antes que los parámetros.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-121">It comes before any parameters.</span></span>|  
|<span data-ttu-id="c2ff4-122">Procedimiento empaquetada o solicitud de función</span><span class="sxs-lookup"><span data-stu-id="c2ff4-122">Packaged Procedure or Function Request</span></span>|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|<span data-ttu-id="c2ff4-123">Igual que la función o procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="c2ff4-123">Same as Function or Stored Procedure</span></span>|  
|<span data-ttu-id="c2ff4-124">Procedimiento empaquetada o respuesta de la función</span><span class="sxs-lookup"><span data-stu-id="c2ff4-124">Packaged Procedure or Function Response</span></span>|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|<span data-ttu-id="c2ff4-125">Igual que la función o procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="c2ff4-125">Same as Function or Stored Procedure</span></span>|  

 <span data-ttu-id="c2ff4-126">`[SCHEMA]` = La recopilación de artefactos de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-126">`[SCHEMA]` = Collection of Oracle artifacts; for example, SCOTT.</span></span>  

 <span data-ttu-id="c2ff4-127">`[SP_NAME]` = El procedimiento almacenado que se ejecutará; Por ejemplo, SP_INSERT.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-127">`[SP_NAME]` = The stored procedure to be executed; for example, SP_INSERT.</span></span>  

 <span data-ttu-id="c2ff4-128">`[FN_NAME]` = La función que se ejecutará; Por ejemplo, FN_GETID.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-128">`[FN_NAME]` = The function to be executed; for example, FN_GETID.</span></span>  

 <span data-ttu-id="c2ff4-129">`[PRM1_NAME]` = El nombre del parámetro de Oracle.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-129">`[PRM1_NAME]` = The name of the Oracle parameter.</span></span> <span data-ttu-id="c2ff4-130">Consulte la columna de descripción de direcciones de parámetros admitidos para cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-130">See the Description column for supported parameter directions for each message.</span></span>  

 <span data-ttu-id="c2ff4-131">`[PACKAGE_NAME]` = El nombre del paquete que contiene el destino del procedimiento o función.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-131">`[PACKAGE_NAME]` = The name of the package that contains the targeted procedure or function.</span></span>  

 <span data-ttu-id="c2ff4-132">La base de datos de Oracle admite la sobrecarga de funciones y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-132">The Oracle database supports overloading for stored procedures and functions.</span></span> <span data-ttu-id="c2ff4-133">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con esta funcionalidad mediante la anexión de una cadena de sobrecarga para el espacio de nombres de destino para cada artefacto sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-133">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports this capability by appending an overload string to the target namespace for each overloaded artifact.</span></span> <span data-ttu-id="c2ff4-134">El valor de esta cadena es "overload1" para la primera sobrecarga, "overload2" para la segunda sobrecarga y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-134">The value of this string is "overload1" for the first overload, "overload2" for the second overload, and so on.</span></span> <span data-ttu-id="c2ff4-135">El ejemplo siguiente muestra la estructura del mensaje para dos procedimientos almacenados sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-135">The following example shows the message structure for two overloaded stored procedures.</span></span>  

```  
Stored Procedure Overload 1:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload1">    
  <[PRM1_NAME]>value1</[PRM1_NAME]>  
  <[PRM2_NAME]>value1</[PRM2_NAME]>  
  …  
</[SP_NAME]>  

Stored Procedure Overload 2:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload2">    
  <[PRM1_NAME]>value1</I_[PRM1_NAME]>  
  <[PRM2_NAME]>value1</I_[PRM2_NAME]>  
  …  
</[SP_NAME]>  
```  

## <a name="message-actions-of-functions-and-procedures"></a><span data-ttu-id="c2ff4-136">Acciones de mensaje de funciones y procedimientos</span><span class="sxs-lookup"><span data-stu-id="c2ff4-136">Message Actions of Functions and Procedures</span></span>  
 <span data-ttu-id="c2ff4-137">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa las siguientes acciones de mensaje para las operaciones de función y procedimiento almacenadas.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-137">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses the following message actions for stored procedure and function operations.</span></span>  


|               <span data-ttu-id="c2ff4-138">de mensaje</span><span class="sxs-lookup"><span data-stu-id="c2ff4-138">Message</span></span>                |                                              <span data-ttu-id="c2ff4-139">Acción</span><span class="sxs-lookup"><span data-stu-id="c2ff4-139">Action</span></span>                                              |                                          <span data-ttu-id="c2ff4-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2ff4-140">Example</span></span>                                           |
|--------------------------------------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|       <span data-ttu-id="c2ff4-141">Solicitud de procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="c2ff4-141">Stored Procedure Request</span></span>       |            `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]`            |          `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT`           |
|      <span data-ttu-id="c2ff4-142">Respuesta de procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="c2ff4-142">Stored Procedure Response</span></span>       |       `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/response`        |      `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/response`      |
|           <span data-ttu-id="c2ff4-143">Solicitud de función</span><span class="sxs-lookup"><span data-stu-id="c2ff4-143">Function Request</span></span>           |            `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function/[FN_NAME]`             |           `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID`            |
|          <span data-ttu-id="c2ff4-144">Respuesta de la función</span><span class="sxs-lookup"><span data-stu-id="c2ff4-144">Function Response</span></span>           |        `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function/[FN_NAME]/response`        |       `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID/response`       |
|  <span data-ttu-id="c2ff4-145">Solicitud de empaquetado de procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="c2ff4-145">Packaged Stored Procedure Request</span></span>   |     `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]`      |       `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT`       |
|  <span data-ttu-id="c2ff4-146">Empaqueta la respuesta del procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="c2ff4-146">Packaged Stored Procedure Response</span></span>  | `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/response` |  `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT/response`   |
|      <span data-ttu-id="c2ff4-147">Solicitud de una función empaquetada</span><span class="sxs-lookup"><span data-stu-id="c2ff4-147">Packaged Function Request</span></span>       |     `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]`      |       `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID`        |
|      <span data-ttu-id="c2ff4-148">Respuesta de la función empaquetada</span><span class="sxs-lookup"><span data-stu-id="c2ff4-148">Packaged Function Response</span></span>      | `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]/response` |   `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID/response`   |
| <span data-ttu-id="c2ff4-149">Solicitud de procedimiento almacenado sobrecargado</span><span class="sxs-lookup"><span data-stu-id="c2ff4-149">Overloaded Stored Procedure Request</span></span>  |      `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]`       |     `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1`      |
| <span data-ttu-id="c2ff4-150">Sobrecargar un procedimiento almacenado respuesta</span><span class="sxs-lookup"><span data-stu-id="c2ff4-150">Overloaded Stored Procedure Response</span></span> |  `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]/response`  | `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1/response` |

 <span data-ttu-id="c2ff4-151">`[SCHEMA]` = La recopilación de artefactos de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-151">`[SCHEMA]` = Collection of Oracle artifacts; for example, SCOTT.</span></span>  

 <span data-ttu-id="c2ff4-152">`[SP_NAME]` = El procedimiento almacenado que se ejecutará; Por ejemplo, SP_INSERT.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-152">`[SP_NAME]` = The stored procedure to be executed; for example, SP_INSERT.</span></span>  

 <span data-ttu-id="c2ff4-153">`[FN_NAME]` = La función que se ejecutará; Por ejemplo, FN_GETID.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-153">`[FN_NAME]` = The function to be executed; for example, FN_GETID.</span></span>  

 <span data-ttu-id="c2ff4-154">`[PACKAGE_NAME]` = El nombre del paquete que contiene el destino del procedimiento o función.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-154">`[PACKAGE_NAME]` = The name of the package that contains the targeted procedure or function.</span></span>  

 <span data-ttu-id="c2ff4-155">`[OVERLOAD]` = El parámetro de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-155">`[OVERLOAD]` = The Overload parameter.</span></span> <span data-ttu-id="c2ff4-156">Los valores posibles son overload1, overload2 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="c2ff4-156">The possible values are overload1, overload2, and so on.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c2ff4-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2ff4-157">See Also</span></span>  
 [<span data-ttu-id="c2ff4-158">Mensajes y esquemas de mensaje para el adaptador de BizTalk para la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="c2ff4-158">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
