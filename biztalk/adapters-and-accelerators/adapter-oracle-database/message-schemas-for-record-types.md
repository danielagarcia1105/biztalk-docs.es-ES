---
title: Los esquemas de mensajes para tipos de registros | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD types, message schemas for
- RECORD types, support for
ms.assetid: 637c42f2-eed0-4941-a6cd-7e03d01088b8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aae82fad713fd9a2789e165845958421e1213402
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996925"
---
# <a name="message-schemas-for-record-types"></a><span data-ttu-id="1727d-102">Esquemas de mensaje para tipos de registro</span><span class="sxs-lookup"><span data-stu-id="1727d-102">Message Schemas for RECORD Types</span></span>
<span data-ttu-id="1727d-103">Tipos de registros de Oracle son tipos de datos estructurados de PL/SQL que se componen de uno o más los tipos de base de datos estructurados o simple.</span><span class="sxs-lookup"><span data-stu-id="1727d-103">Oracle RECORD types are structured PL/SQL data types that consist of one or more simple or structured database types.</span></span> <span data-ttu-id="1727d-104">Tipos de registros se utilizan principalmente en las funciones y procedimientos almacenados de PL/SQL para enviar y recibir datos jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="1727d-104">RECORD types are primarily used in PL/SQL stored procedures and functions to send and receive hierarchical data.</span></span>  
  
 <span data-ttu-id="1727d-105">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es compatible con tipos de registros de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1727d-105">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports RECORD types in the following manner:</span></span>  
  
- <span data-ttu-id="1727d-106">Tipos de registro se exponen como tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="1727d-106">RECORD types are surfaced as complex types.</span></span>  
  
- <span data-ttu-id="1727d-107">Tipos de registro pueden ser (registro anidado en un registro).</span><span class="sxs-lookup"><span data-stu-id="1727d-107">RECORD types can be nested (record in a record).</span></span>  
  
- <span data-ttu-id="1727d-108">Tipos de registros se pueden declarar como parámetros de tipo de fila de tabla % en procedimientos almacenados y funciones.</span><span class="sxs-lookup"><span data-stu-id="1727d-108">RECORD types can be declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
- <span data-ttu-id="1727d-109">Tipos de registros se pueden declarar como parámetros de tipo de registro en los paquetes de PL/SQL; Por ejemplo, `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`.</span><span class="sxs-lookup"><span data-stu-id="1727d-109">RECORD types can be declared as TYPE of RECORD parameters in PL/SQL packages; for example, `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="1727d-110">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tipos BFILE como miembros de registro.</span><span class="sxs-lookup"><span data-stu-id="1727d-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
  <span data-ttu-id="1727d-111">Cuando se utiliza un parámetro de tipo de registro en un procedimiento almacenado o una función, está calificado con el espacio de nombres de esa operación.</span><span class="sxs-lookup"><span data-stu-id="1727d-111">When a RECORD type parameter is used in a stored procedure or a function, it is qualified with the namespace of that operation.</span></span> <span data-ttu-id="1727d-112">El siguiente XML muestra la estructura de un tipo de registro en un mensaje:</span><span class="sxs-lookup"><span data-stu-id="1727d-112">The following XML shows the structure of a RECORD type in a message:</span></span>  
  
```  
<[REC_PARAM_NAME]>  
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
 <span data-ttu-id="1727d-113">[REC_PARAM_NAME] es el nombre del parámetro de registro.</span><span class="sxs-lookup"><span data-stu-id="1727d-113">[REC_PARAM_NAME] is the name of the RECORD parameter.</span></span>  
  
 <span data-ttu-id="1727d-114">[Nombre_de_campo] es el nombre de un campo en el tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="1727d-114">[FIELD_NAME] is the name of a field in the RECORD type.</span></span>  
  
 <span data-ttu-id="1727d-115">[OPERATION_NAMESPACE] es el espacio de nombres del procedimiento almacenado o función en el que se usa el parámetro de registro.</span><span class="sxs-lookup"><span data-stu-id="1727d-115">[OPERATION_NAMESPACE] is the namespace of the stored procedure or function in which the RECORD parameter is being used.</span></span>  
  
 <span data-ttu-id="1727d-116">El siguiente XML muestra la estructura de un parámetro de tipo de registro con un campo de tipo de registro anidado:</span><span class="sxs-lookup"><span data-stu-id="1727d-116">The following XML shows the structure of a RECORD type parameter with a nested RECORD type field:</span></span>  
  
```  
<[REC_PARAM_NAME]>    
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  <[REC_PARAM_NAME2]>  
    <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
    <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME2]>  
    …  
  </[REC_PARAM_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1727d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1727d-117">See Also</span></span>  
 [<span data-ttu-id="1727d-118">Mensajes y esquemas de mensaje para el adaptador de BizTalk para la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="1727d-118">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)