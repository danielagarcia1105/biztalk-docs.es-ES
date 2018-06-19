---
title: Esquemas de mensajes para tipos de registro | Documentos de Microsoft
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
ms.openlocfilehash: c9022274041e06ad8ccc3f5243715d44d2b64282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214140"
---
# <a name="message-schemas-for-record-types"></a><span data-ttu-id="94ffc-102">Esquemas de mensaje para tipos de registro</span><span class="sxs-lookup"><span data-stu-id="94ffc-102">Message Schemas for RECORD Types</span></span>
<span data-ttu-id="94ffc-103">Tipos de registros de Oracle son tipos de datos estructurados de PL/SQL que se componen de uno o más los tipos de base de datos estructurados o simple.</span><span class="sxs-lookup"><span data-stu-id="94ffc-103">Oracle RECORD types are structured PL/SQL data types that consist of one or more simple or structured database types.</span></span> <span data-ttu-id="94ffc-104">Tipos de registro se utilizan principalmente en las funciones y procedimientos almacenados de PL/SQL para enviar y recibir datos jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="94ffc-104">RECORD types are primarily used in PL/SQL stored procedures and functions to send and receive hierarchical data.</span></span>  
  
 <span data-ttu-id="94ffc-105">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es compatible con tipos de registros de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="94ffc-105">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports RECORD types in the following manner:</span></span>  
  
-   <span data-ttu-id="94ffc-106">Tipos de registro se exponen como tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="94ffc-106">RECORD types are surfaced as complex types.</span></span>  
  
-   <span data-ttu-id="94ffc-107">Tipos de registro pueden ser (registro anidado en un registro).</span><span class="sxs-lookup"><span data-stu-id="94ffc-107">RECORD types can be nested (record in a record).</span></span>  
  
-   <span data-ttu-id="94ffc-108">Tipos de registro se pueden declarar como parámetros de tabla % ROWTYPE en procedimientos almacenados y funciones.</span><span class="sxs-lookup"><span data-stu-id="94ffc-108">RECORD types can be declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
-   <span data-ttu-id="94ffc-109">Tipos de registros se pueden declarar como parámetros de tipo de registro de paquetes de PL/SQL; Por ejemplo, `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`.</span><span class="sxs-lookup"><span data-stu-id="94ffc-109">RECORD types can be declared as TYPE of RECORD parameters in PL/SQL packages; for example, `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="94ffc-110">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tipos BFILE como miembros de registro.</span><span class="sxs-lookup"><span data-stu-id="94ffc-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
 <span data-ttu-id="94ffc-111">Cuando se utiliza un parámetro de tipo de registro en un procedimiento almacenado o una función, se califican con el espacio de nombres de esa operación.</span><span class="sxs-lookup"><span data-stu-id="94ffc-111">When a RECORD type parameter is used in a stored procedure or a function, it is qualified with the namespace of that operation.</span></span> <span data-ttu-id="94ffc-112">El siguiente XML muestra la estructura de un tipo de registro en un mensaje:</span><span class="sxs-lookup"><span data-stu-id="94ffc-112">The following XML shows the structure of a RECORD type in a message:</span></span>  
  
```  
<[REC_PARAM_NAME]>  
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
 <span data-ttu-id="94ffc-113">[REC_PARAM_NAME] es el nombre del parámetro de registro.</span><span class="sxs-lookup"><span data-stu-id="94ffc-113">[REC_PARAM_NAME] is the name of the RECORD parameter.</span></span>  
  
 <span data-ttu-id="94ffc-114">[Nombre_de_campo] es el nombre de un campo en el tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="94ffc-114">[FIELD_NAME] is the name of a field in the RECORD type.</span></span>  
  
 <span data-ttu-id="94ffc-115">[OPERATION_NAMESPACE] es el espacio de nombres del procedimiento almacenado o la función en la que se está utilizando el parámetro de registro.</span><span class="sxs-lookup"><span data-stu-id="94ffc-115">[OPERATION_NAMESPACE] is the namespace of the stored procedure or function in which the RECORD parameter is being used.</span></span>  
  
 <span data-ttu-id="94ffc-116">El siguiente XML muestra la estructura de un parámetro de tipo de registro con un campo de tipo de registro anidado:</span><span class="sxs-lookup"><span data-stu-id="94ffc-116">The following XML shows the structure of a RECORD type parameter with a nested RECORD type field:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="94ffc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="94ffc-117">See Also</span></span>  
 [<span data-ttu-id="94ffc-118">Mensajes y esquemas de mensaje para el adaptador de BizTalk para base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="94ffc-118">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)