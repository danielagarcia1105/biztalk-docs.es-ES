---
title: Esquemas de mensajes para el compuesto Operation2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0164ea07-a373-430b-b569-3e29df1d081b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1014ea162e9fab33aa6630d0cdb4eb774f91031
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214068"
---
# <a name="message-schemas-for-the-composite-operation"></a><span data-ttu-id="e85e9-102">Esquemas de mensaje para la operación de composición</span><span class="sxs-lookup"><span data-stu-id="e85e9-102">Message Schemas for the Composite Operation</span></span>
<span data-ttu-id="e85e9-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] permite ejecutar operaciones compuestas en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="e85e9-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] enables you to execute composite operations on the Oracle database.</span></span> <span data-ttu-id="e85e9-104">Una operación compuesta puede contener varias operaciones y en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="e85e9-104">A composite operation can contain multiple operations, and in any order.</span></span> <span data-ttu-id="e85e9-105">Para obtener información sobre qué operaciones pueden incluirse en una operación compuesta, consulte [ejecutar operaciones compuestas en base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="e85e9-105">For information about which operations can be included in a composite operation, see [Run Composite Operations in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md).</span></span>  
  
 <span data-ttu-id="e85e9-106">Para obtener información acerca de cómo realizar operaciones compuestas mediante la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [ejecutar operaciones compuestas en la base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="e85e9-106">For information about how to perform composite operations using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Run Composite Operations on Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
## <a name="message-structure-for-the-composite-operation"></a><span data-ttu-id="e85e9-107">Estructura del mensaje para la operación de composición</span><span class="sxs-lookup"><span data-stu-id="e85e9-107">Message Structure for the Composite Operation</span></span>  
 <span data-ttu-id="e85e9-108">Dado que una operación compuesta contiene varias operaciones individuales; la estructura del mensaje de una operación compuesta contiene estructuras de mensajes de las operaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="e85e9-108">Because a composite operation contains multiple individual operations; the message structure of a composite operation contains message structures of the individual operations.</span></span> <span data-ttu-id="e85e9-109">El mensaje de operación compuesta sigue un patrón de intercambio de mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="e85e9-109">The composite operation message follows a request-response message exchange pattern.</span></span>  
  
 <span data-ttu-id="e85e9-110">En la tabla siguiente muestra la estructura de los mensajes de solicitud y respuesta de una operación compuesta que contiene una operación de inserción, un procedimiento almacenado empaquetado que no tome ningún parámetros de entrada y una operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="e85e9-110">The following table shows the structure of the request and response messages of a composite operation that contains an Insert operation, a packaged stored procedure that does not take any input parameters, and a Delete operation.</span></span>  
  
|<span data-ttu-id="e85e9-111">Operación</span><span class="sxs-lookup"><span data-stu-id="e85e9-111">Operation</span></span>|<span data-ttu-id="e85e9-112">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="e85e9-112">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e85e9-113">Solicitud de operación compuesta</span><span class="sxs-lookup"><span data-stu-id="e85e9-113">Composite Operation Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <RECORDSET>       <[TABLE_NAME]RECORDINSERT>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>         …       </[TABLE_NAME]RECORDINSERT>    </RECORDSET>   </Insert>   <[SP_NAME] xmlns="[VERSION]/[SCHEMA]/Procedure" />   <Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <FILTER>[WHERE_clause]</FILTER>   </Delete> </Request>`|  
|<span data-ttu-id="e85e9-114">Respuesta de operación compuesta</span><span class="sxs-lookup"><span data-stu-id="e85e9-114">Composite Operation Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <InsertResult>[value]</InsertResult>    </InsertResponse>   <[SP_NAME]Response xmlns="[VERSION]/[SCHEMA]/Procedure">     <[PRM1_NAME]>value1<[PRM1_NAME]>     <[PRM2_NAME]>value2</[PRM2_NAME]>     …   </[SP_NAME]Response>    <DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 <span data-ttu-id="e85e9-115">[Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.OracleDB/2007/03</span><span class="sxs-lookup"><span data-stu-id="e85e9-115">[VERSION] = The message version string; for example, http://Microsoft.LobServices.OracleDB/2007/03</span></span>  
  
 <span data-ttu-id="e85e9-116">[Nombre_proyecto] = nombre del proyecto de BizTalk que contiene el esquema de operación compuesta.</span><span class="sxs-lookup"><span data-stu-id="e85e9-116">[PROJECT_NAME] = Name of the BizTalk project that contains the composite operation schema.</span></span>  
  
 <span data-ttu-id="e85e9-117">[COMPOSITE_SCHEMA_NAME] = nombre del esquema de operación compuesta proporcionado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e85e9-117">[COMPOSITE_SCHEMA_NAME] = Name of the composite operation schema given by the user.</span></span>  
  
 <span data-ttu-id="e85e9-118">[Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="e85e9-118">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="e85e9-119">[NombreTabla] = nombre de la tabla; Por ejemplo, el empleado.</span><span class="sxs-lookup"><span data-stu-id="e85e9-119">[TABLE_NAME] = Name of the table; for example, EMPLOYEE.</span></span>  
  
 <span data-ttu-id="e85e9-120">[FIELD1_NAME] = nombre de campo de la tabla; Por ejemplo, el nombre.</span><span class="sxs-lookup"><span data-stu-id="e85e9-120">[FIELD1_NAME] = Table field name; for example, NAME.</span></span>  
  
 <span data-ttu-id="e85e9-121">[SP_NAME] = el procedimiento almacenado empaquetado que se ejecutará; Por ejemplo, ADD_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="e85e9-121">[SP_NAME] = The packaged stored procedure to be executed; for example, ADD_EMP_DETAILS.</span></span>  
  
 <span data-ttu-id="e85e9-122">[PRM1_NAME] = el nombre del parámetro de Oracle en el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="e85e9-122">[PRM1_NAME] = The name of the Oracle parameter in the stored procedure.</span></span>  
  
## <a name="message-action-for-the-composite-operation"></a><span data-ttu-id="e85e9-123">Acción de mensaje para la operación de composición</span><span class="sxs-lookup"><span data-stu-id="e85e9-123">Message Action for the Composite Operation</span></span>  
 <span data-ttu-id="e85e9-124">La acción de mensaje para la operación compuesta es "http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation."</span><span class="sxs-lookup"><span data-stu-id="e85e9-124">The message action for the composite operation is “http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e85e9-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e85e9-125">See Also</span></span>  
 [<span data-ttu-id="e85e9-126">Mensajes y esquemas de mensaje para el adaptador de BizTalk para base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="e85e9-126">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)