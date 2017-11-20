---
title: Esquemas de mensajes para los conjuntos de solicitud | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bba9677d-ee94-4da5-8611-b1e47f2f3798
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fd81ee75088b41a182c5a2aa675266420f8f32f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-request-sets"></a><span data-ttu-id="9289e-102">Esquemas de mensaje para conjuntos de solicitudes</span><span class="sxs-lookup"><span data-stu-id="9289e-102">Message Schemas for Request Sets</span></span>
<span data-ttu-id="9289e-103">Aparece como una operación en cada solicitud que se establezcan en una aplicación de Oracle en Oracle E-Business Suite [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9289e-103">Each request set in an Oracle application in Oracle E-Business Suite is surfaced as an operation in [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span></span>  
  
## <a name="message-structure-of-request-set-operation"></a><span data-ttu-id="9289e-104">Estructura de mensaje de solicitud de la operación del conjunto</span><span class="sxs-lookup"><span data-stu-id="9289e-104">Message Structure of Request Set Operation</span></span>  
 <span data-ttu-id="9289e-105">Las operaciones que exhibe para conjunto de solicitud siguen un patrón de intercambio de mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="9289e-105">The operations surfaced for request set follow a request-response message exchange pattern.</span></span> <span data-ttu-id="9289e-106">En la tabla siguiente se muestra la estructura de estos mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="9289e-106">The following table shows the structure of these request and response messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9289e-107">Ver una descripción de la entidad después de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9289e-107">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="9289e-108">Operación</span><span class="sxs-lookup"><span data-stu-id="9289e-108">Operation</span></span>|<span data-ttu-id="9289e-109">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="9289e-109">XML Message</span></span>|<span data-ttu-id="9289e-110">Description</span><span class="sxs-lookup"><span data-stu-id="9289e-110">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="9289e-111">[Request_Set_Name] Solicitud</span><span class="sxs-lookup"><span data-stu-id="9289e-111">[Request_Set_Name] Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name] xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]/">   <SetRelClassOptions>     <Application>[value]</Application>     <ClassName>[value]</ClassName>     <CancelOrHold>[value]</CancelOrHold>     <StaleDate>[value]</StaleDate>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRelClassOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <SetNlsOptions>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetNlsOptions>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_NAME1]>[value]</[CONCURRENT_PROGRAM_NAME1]>   <[CONCURRENT_PROGRAM_NAME2]>[value]</[CONCURRENT_PROGRAM_NAME2]>   … </[Request_Set_Name]>`|<span data-ttu-id="9289e-112">-La operación [Request_Set_Name] tiene cinco parámetros estándares: `SetRelClassOptions`, `SetPrintOptions`, `SetRepeatOptions`, `SetNlsOptions`, y `StartTime`.</span><span class="sxs-lookup"><span data-stu-id="9289e-112">- The [Request_Set_Name] operation takes five standard parameters:  `SetRelClassOptions`, `SetPrintOptions`,  `SetRepeatOptions`, `SetNlsOptions`, and `StartTime`.</span></span><br /><br /> <span data-ttu-id="9289e-113">-El `ContinueOnFail` parámetro indica si el envío de conjunto de solicitud debe continuar o se produce una excepción en caso del parámetro parent (`SetRelClassOptions`, `SetPrintOptions`, `SetRepeatOptions` o `SetNlsOptions`) se produce un error.</span><span class="sxs-lookup"><span data-stu-id="9289e-113">- The `ContinueOnFail` parameter indicates whether the request set submission should continue or throw an exception in case the parent parameter (`SetRelClassOptions`, `SetPrintOptions`, `SetRepeatOptions` or `SetNlsOptions`) fails.</span></span> <span data-ttu-id="9289e-114">Puede especificar **True** (continuar) o **False** (producir una excepción).</span><span class="sxs-lookup"><span data-stu-id="9289e-114">You can specify **True** (continue) or **False** (throw an exception).</span></span><br /><br /> <span data-ttu-id="9289e-115">-Para obtener información detallada acerca de cada parámetro, consulte [operaciones con conjuntos de solicitud](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md).</span><span class="sxs-lookup"><span data-stu-id="9289e-115">- For detailed information about each parameter, see [Operations on Request Sets](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md).</span></span>|  
|<span data-ttu-id="9289e-116">[Request_Set_Name] Respuesta</span><span class="sxs-lookup"><span data-stu-id="9289e-116">[Request_Set_Name] Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name]Response xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]">   <[Request_Set_Name]Result>[value]</[Request_Set_Name]Result> </[Request_Set_Name]Response>`|<span data-ttu-id="9289e-117">La respuesta de Oracle E-Business Suite contiene un identificador de solicitudes simultáneas.</span><span class="sxs-lookup"><span data-stu-id="9289e-117">The response from Oracle E-Business Suite contains a concurrent request ID.</span></span>|  
  
 <span data-ttu-id="9289e-118">Descripciones de entidad:</span><span class="sxs-lookup"><span data-stu-id="9289e-118">Entity descriptions:</span></span>  
  
 <span data-ttu-id="9289e-119">[Versión] = http://schemas.microsoft.com/OracleEBS/2008/05</span><span class="sxs-lookup"><span data-stu-id="9289e-119">[VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05</span></span>  
  
 <span data-ttu-id="9289e-120">.</span><span class="sxs-lookup"><span data-stu-id="9289e-120">.</span></span>  
  
 <span data-ttu-id="9289e-121">[CONCURRENT_PROGRAM_NAME] = simultánea programa incluido en el conjunto de solicitud.</span><span class="sxs-lookup"><span data-stu-id="9289e-121">[CONCURRENT_PROGRAM_NAME] = Concurrent program included in the request set.</span></span>  
  
## <a name="message-actions-for-request-sets"></a><span data-ttu-id="9289e-122">Acciones de mensaje para conjuntos de solicitudes</span><span class="sxs-lookup"><span data-stu-id="9289e-122">Message Actions for Request Sets</span></span>  
 <span data-ttu-id="9289e-123">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa las siguientes acciones de mensaje para conjuntos de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="9289e-123">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses the following message actions for request sets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9289e-124">Ver una descripción de la entidad después de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9289e-124">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="9289e-125">de mensaje</span><span class="sxs-lookup"><span data-stu-id="9289e-125">Message</span></span>|<span data-ttu-id="9289e-126">Acción</span><span class="sxs-lookup"><span data-stu-id="9289e-126">Action</span></span>|<span data-ttu-id="9289e-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9289e-127">Example</span></span>|  
|-------------|------------|-------------|  
|<span data-ttu-id="9289e-128">Solicitud de conjunto de solicitud</span><span class="sxs-lookup"><span data-stu-id="9289e-128">Request Set request</span></span>|<span data-ttu-id="9289e-129">RequestSets / [APP_SHORT_NAME] / [REQUESTSET_SHORT_NAME]</span><span class="sxs-lookup"><span data-stu-id="9289e-129">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]</span></span>|<span data-ttu-id="9289e-130">RequestSets/SQLGL/FNDRSSUB965</span><span class="sxs-lookup"><span data-stu-id="9289e-130">RequestSets/SQLGL/FNDRSSUB965</span></span>|  
|<span data-ttu-id="9289e-131">Conjunto de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="9289e-131">Request Set response</span></span>|<span data-ttu-id="9289e-132">RequestSets / [APP_SHORT_NAME] / [REQUESTSET_SHORT_NAME]] / respuesta</span><span class="sxs-lookup"><span data-stu-id="9289e-132">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]]/response</span></span>|<span data-ttu-id="9289e-133">RequestSets/SQLGL/FNDRSSUB965/respuesta</span><span class="sxs-lookup"><span data-stu-id="9289e-133">RequestSets/SQLGL/FNDRSSUB965/response</span></span>|  
  
 <span data-ttu-id="9289e-134">Descripciones de entidad:</span><span class="sxs-lookup"><span data-stu-id="9289e-134">Entity descriptions:</span></span>  
  
 <span data-ttu-id="9289e-135">[APP_SHORT_NAME] = nombre corto de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9289e-135">[APP_SHORT_NAME] = Application short name.</span></span>  
  
 <span data-ttu-id="9289e-136">[REQUESTSET_SHORT_NAME] = solicitud establecer nombre corto.</span><span class="sxs-lookup"><span data-stu-id="9289e-136">[REQUESTSET_SHORT_NAME] = Request Set short name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9289e-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="9289e-137">See Also</span></span>  
 [<span data-ttu-id="9289e-138">Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="9289e-138">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)