---
title: Esquemas de mensajes para el compuesto Operation1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 768473ef-da8d-4e58-86cb-597c28ded49c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b22861d36693ab3ef487e5e3d0b86544f048e95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215180"
---
# <a name="message-schemas-for-the-composite-operation"></a><span data-ttu-id="726bc-102">Esquemas de mensaje para la operación de composición</span><span class="sxs-lookup"><span data-stu-id="726bc-102">Message Schemas for the Composite Operation</span></span>
<span data-ttu-id="726bc-103">El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] permite ejecutar operaciones compuestas en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="726bc-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] enables you to execute composite operations in Oracle E-Business Suite.</span></span> <span data-ttu-id="726bc-104">Una operación compuesta puede contener varias operaciones y en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="726bc-104">A composite operation can contain multiple operations, and in any order.</span></span> <span data-ttu-id="726bc-105">Para obtener información sobre qué operaciones pueden incluirse en una operación compuesta, consulte [compatibilidad para operaciones compuestas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).</span><span class="sxs-lookup"><span data-stu-id="726bc-105">For information about which operations can be included in a composite operation, see [Support for Composite Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).</span></span>  
  
 <span data-ttu-id="726bc-106">Para obtener información acerca de cómo realizar operaciones compuestas mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [ejecutar operaciones compuestas en la base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="726bc-106">For information about how to perform composite operations using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [Run Composite Operations on Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
## <a name="message-structure-for-the-composite-operation"></a><span data-ttu-id="726bc-107">Estructura del mensaje para la operación de composición</span><span class="sxs-lookup"><span data-stu-id="726bc-107">Message Structure for the Composite Operation</span></span>  
 <span data-ttu-id="726bc-108">Puesto que una operación compuesta contiene varias operaciones individuales; la estructura del mensaje de una operación compuesta contiene estructuras de mensajes de las operaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="726bc-108">Since a composite operation contains multiple individual operations; the message structure of a composite operation contains message structures of the individual operations.</span></span> <span data-ttu-id="726bc-109">El mensaje de operación compuesta sigue un patrón de intercambio de mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="726bc-109">The composite operation message follows a request-response message exchange pattern.</span></span>  
  
 <span data-ttu-id="726bc-110">En la tabla siguiente muestra la estructura de los mensajes de solicitud y respuesta de una operación compuesta que contiene una operación de inserción, un procedimiento almacenado empaquetado que no tome ningún parámetros de entrada y una operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="726bc-110">The following table shows the structure of the request and response messages of a composite operation that contains an Insert operation, a packaged stored procedure that does not take any input parameters, and a Delete operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="726bc-111">Ver una descripción de la entidad después de la tabla.</span><span class="sxs-lookup"><span data-stu-id="726bc-111">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="726bc-112">Operación</span><span class="sxs-lookup"><span data-stu-id="726bc-112">Operation</span></span>|<span data-ttu-id="726bc-113">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="726bc-113">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="726bc-114">Solicitud de operación compuesta</span><span class="sxs-lookup"><span data-stu-id="726bc-114">Composite Operation Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <Recordset>       <InsertRecord>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>           <InLineValue>[value]</InlineValue>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>           <InLineValue>[value]</InlineValue>         …       <InsertRecord>    </RECORDSET>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/[SCHEMA]/[APP_NAME]" />   <Delete xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <FILTER>[WHERE_clause]</FILTER>   </Delete> </Request>`|  
|<span data-ttu-id="726bc-115">Respuesta de operación compuesta</span><span class="sxs-lookup"><span data-stu-id="726bc-115">Composite Operation Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <InsertResult>[value]</InsertResult>    </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Procedures/[SCHEMA]">     <[PRM1_NAME]>value1<[PRM1_NAME]>     <[PRM2_NAME]>value2</[PRM2_NAME]>     …   </[SP_NAME]Response>    <DeleteResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 <span data-ttu-id="726bc-116">Descripciones de entidad:</span><span class="sxs-lookup"><span data-stu-id="726bc-116">Entity descriptions:</span></span>  
  
 <span data-ttu-id="726bc-117">[Nombre_proyecto] = nombre del proyecto de BizTalk que contiene el esquema de operación compuesta.</span><span class="sxs-lookup"><span data-stu-id="726bc-117">[PROJECT_NAME] = Name of the BizTalk project that contains the composite operation schema.</span></span>  
  
 <span data-ttu-id="726bc-118">[COMPOSITE_SCHEMA_NAME] = nombre del esquema de operación compuesta proporcionado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="726bc-118">[COMPOSITE_SCHEMA_NAME] = Name of the composite operation schema given by the user.</span></span>  
  
 <span data-ttu-id="726bc-119">[Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="726bc-119">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="726bc-120">[NombreTabla] = nombre de la tabla; Por ejemplo, el empleado.</span><span class="sxs-lookup"><span data-stu-id="726bc-120">[TABLE_NAME] = Name of the table; for example, EMPLOYEE.</span></span>  
  
 <span data-ttu-id="726bc-121">[FIELD1_NAME] = nombre de campo de la tabla; Por ejemplo, el nombre.</span><span class="sxs-lookup"><span data-stu-id="726bc-121">[FIELD1_NAME] = Table field name; for example, NAME.</span></span>  
  
 <span data-ttu-id="726bc-122">[SP_NAME] = el procedimiento almacenado empaquetado que se ejecutará; Por ejemplo, ADD_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="726bc-122">[SP_NAME] = The packaged stored procedure to be executed; for example, ADD_EMP_DETAILS.</span></span>  
  
 <span data-ttu-id="726bc-123">[APP_NAME] = nombre de la aplicación de Oracle que contiene el procedimiento almacenado empaquetado.</span><span class="sxs-lookup"><span data-stu-id="726bc-123">[APP_NAME] = Name of the Oracle Application that contains the packaged stored procedure.</span></span>  
  
 <span data-ttu-id="726bc-124">[PRM1_NAME] = el nombre del parámetro de Oracle en el procedimiento almacenado empaquetado.</span><span class="sxs-lookup"><span data-stu-id="726bc-124">[PRM1_NAME] = The name of the Oracle parameter in the packaged stored procedure.</span></span>  
  
## <a name="message-action-for-the-composite-operation"></a><span data-ttu-id="726bc-125">Acción de mensaje para la operación de composición</span><span class="sxs-lookup"><span data-stu-id="726bc-125">Message Action for the Composite Operation</span></span>  
 <span data-ttu-id="726bc-126">La acción de mensaje para la operación compuesta es "CompositeOperation."</span><span class="sxs-lookup"><span data-stu-id="726bc-126">The message action for the composite operation is “CompositeOperation.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726bc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="726bc-127">See Also</span></span>  
 [<span data-ttu-id="726bc-128">Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="726bc-128">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)