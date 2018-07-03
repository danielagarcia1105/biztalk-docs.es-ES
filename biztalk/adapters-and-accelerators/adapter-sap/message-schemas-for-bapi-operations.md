---
title: Los esquemas de mensajes para operaciones de BAPI | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI operations, message schemas for
- BAPI operations, message structure for
- BAPI operations, message actions for
ms.assetid: ef4d88e8-f31a-4b68-a303-6885b6f8c083
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 796e7beb428e6f9a4f0df63eff9cf45e9d5410bb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995221"
---
# <a name="message-schemas-for-bapi-operations"></a><span data-ttu-id="9e0b2-102">Esquemas de mensaje para operaciones de BAPI</span><span class="sxs-lookup"><span data-stu-id="9e0b2-102">Message Schemas for BAPI Operations</span></span>
<span data-ttu-id="9e0b2-103">Las secciones siguientes describen los esquemas de mensaje y las acciones de mensaje utilizadas para invocar BAPI en el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como métodos de objetos de negocios.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-103">The following sections describe the message schemas and message actions used to invoke BAPIs on the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as methods of business objects.</span></span> <span data-ttu-id="9e0b2-104">También puede invocar BAPI como operaciones de RFC en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-104">You can also invoke BAPIs as RFC operations on the adapter.</span></span> <span data-ttu-id="9e0b2-105">Para obtener más información acerca de los mensajes utilizados para invocar RFC, consulte [esquemas de mensaje para operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span><span class="sxs-lookup"><span data-stu-id="9e0b2-105">For more information about the messages used to invoke RFCs, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span> <span data-ttu-id="9e0b2-106">Independientemente de cómo invocar una BAPI en el adaptador, el adaptador siempre invoca la BAPI como una solicitud de cambio en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-106">Regardless of how you invoke a BAPI on the adapter, the adapter always invokes the BAPI as an RFC on the SAP system.</span></span> <span data-ttu-id="9e0b2-107">Para obtener información general de cómo el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite BAPI, vea [operaciones en BAPI de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="9e0b2-107">For an overview of how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports BAPIs, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  

## <a name="message-structure-for-business-object-operations"></a><span data-ttu-id="9e0b2-108">Estructura de mensaje para operaciones de objeto de negocios</span><span class="sxs-lookup"><span data-stu-id="9e0b2-108">Message Structure for Business Object Operations</span></span>  
 <span data-ttu-id="9e0b2-109">La siguiente tabla muestra los esquemas de mensaje utilizados para invocar una BAPI como un método del objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-109">The following table shows the message schemas used to invoke a BAPI as a business object method.</span></span>  

|<span data-ttu-id="9e0b2-110">Operación</span><span class="sxs-lookup"><span data-stu-id="9e0b2-110">Operation</span></span>|<span data-ttu-id="9e0b2-111">Operaciones de recepción de estructuras de mensajes para IDOC</span><span class="sxs-lookup"><span data-stu-id="9e0b2-111">XML Structure</span></span>|<span data-ttu-id="9e0b2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e0b2-112">Description</span></span>|  
|---------------|-------------------|-----------------|  
|<span data-ttu-id="9e0b2-113">[BUSOBJ_METHOD]</span><span class="sxs-lookup"><span data-stu-id="9e0b2-113">[BUSOBJ_METHOD]</span></span>|`<[BUSOBJ_METHOD] xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]>`|<span data-ttu-id="9e0b2-114">Invocar un método del objeto comercial en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-114">Invoke a business object method on an SAP system.</span></span><br /><br /> <span data-ttu-id="9e0b2-115">Se admiten la importación, cambiar y parámetros de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-115">Import, changing, and table parameters are supported.</span></span>|  
|<span data-ttu-id="9e0b2-116">[BUSOBJ_METHOD] Respuesta</span><span class="sxs-lookup"><span data-stu-id="9e0b2-116">[BUSOBJ_METHOD] Response</span></span>|`<[BUSOBJ_METHOD]Response xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]Response>`|<span data-ttu-id="9e0b2-117">Respuesta del método de objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-117">Business object method response.</span></span><br /><br /> <span data-ttu-id="9e0b2-118">Exportar, cambiar, y se admiten parámetros de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-118">Export, changing, and table parameters are supported.</span></span><br /><br /> <span data-ttu-id="9e0b2-119">**Tenga en cuenta** de forma predeterminada, los parámetros de la tabla no se exponen en el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-119">**Note** By default, table parameters are not surfaced in the response message.</span></span> <span data-ttu-id="9e0b2-120">Si se requieren parámetros de la tabla en el mensaje de respuesta, debe pasar los parámetros de la tabla vacía en el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-120">If you require table parameters in response message, you must pass empty table parameters in the request message.</span></span>|  

 <span data-ttu-id="9e0b2-121">[Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-121">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  

 <span data-ttu-id="9e0b2-122">[BUSOBJ_METHOD] = el nombre de un método del objeto comercial; Por ejemplo, CREATEFROMDAT2.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-122">[BUSOBJ_METHOD] = The name of a business object method; for example, CREATEFROMDAT2.</span></span>  

 <span data-ttu-id="9e0b2-123">[IN_PARAM_NAME] = el nombre de un parámetro de importación BAPI.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-123">[IN_PARAM_NAME] =The name of a BAPI import parameter.</span></span>  

 <span data-ttu-id="9e0b2-124">[OUT_PARAM_NAME] = el nombre de un parámetro de exportación BAPI.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-124">[OUT_PARAM_NAME] = The name of a BAPI export parameter.</span></span>  

 <span data-ttu-id="9e0b2-125">[INOUT_PARAM_NAME] = el nombre de un BAPI cambiando el parámetro.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-125">[INOUT_PARAM_NAME] = The name of a BAPI changing parameter.</span></span>  

 <span data-ttu-id="9e0b2-126">[TABLE_PARAM_NAME] = nombre del parámetro de tabla BAPI.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-126">[TABLE_PARAM_NAME] = The name of a BAPI table parameter.</span></span>  

 <span data-ttu-id="9e0b2-127">[STRUCT_PARAM_NAME] = el nombre de un parámetro de estructura BAPI.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-127">[STRUCT_PARAM_NAME] = The name of a BAPI structure parameter.</span></span>  

## <a name="message-actions-for-business-object-operations"></a><span data-ttu-id="9e0b2-128">Acciones de mensaje para operaciones de objeto de negocios</span><span class="sxs-lookup"><span data-stu-id="9e0b2-128">Message Actions for Business Object Operations</span></span>  
 <span data-ttu-id="9e0b2-129">La siguiente tabla muestra las acciones de mensaje que se usan para invocar BAPI como métodos de objetos comerciales.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-129">The following table shows the message actions that are used to invoke BAPIs as business object methods.</span></span>  


|        <span data-ttu-id="9e0b2-130">Operación</span><span class="sxs-lookup"><span data-stu-id="9e0b2-130">Operation</span></span>         |                            <span data-ttu-id="9e0b2-131">Acción de mensaje</span><span class="sxs-lookup"><span data-stu-id="9e0b2-131">Message Action</span></span>                             |                                                   <span data-ttu-id="9e0b2-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e0b2-132">Example</span></span>                                                    |
|--------------------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="9e0b2-133">[BUSOBJ_METHOD]</span><span class="sxs-lookup"><span data-stu-id="9e0b2-133">[BUSOBJ_METHOD]</span></span>      |     <span data-ttu-id="9e0b2-134">/Bapi/ [versión] [BUSOBJ_NAME] / [BUSOBJ_METHOD] / [BAPI_RFC_NAME]</span><span class="sxs-lookup"><span data-stu-id="9e0b2-134">[VERSION]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]</span></span>      |     http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2      |
| <span data-ttu-id="9e0b2-135">[BUSOBJ_METHOD] Respuesta</span><span class="sxs-lookup"><span data-stu-id="9e0b2-135">[BUSOBJ_METHOD] Response</span></span> | <span data-ttu-id="9e0b2-136">/Bapi/ [versión] [BUSOBJ_NAME] / [BUSOBJ_METHOD] / [BAPI_RFC_NAME] / respuesta</span><span class="sxs-lookup"><span data-stu-id="9e0b2-136">[VERSION]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]/response</span></span> | http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2/response |

 <span data-ttu-id="9e0b2-137">[Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-137">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  

 <span data-ttu-id="9e0b2-138">[BUSOBJ_NAME] = el nombre del objeto comercial; Por ejemplo, BUS2032.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-138">[BUSOBJ_NAME] = The name of the business object; for example, BUS2032.</span></span>  

 <span data-ttu-id="9e0b2-139">[BUSOBJ_METHOD] = el método del objeto comercial; Por ejemplo, CREATEFROMDAT2.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-139">[BUSOBJ_METHOD] = The method of the business object; for example, CREATEFROMDAT2.</span></span>  

 <span data-ttu-id="9e0b2-140">[BAPI_RFC_NAME] = nombre de la RFC para la BAPI; Por ejemplo, BAPI_SALESORDER_CREATEFROMDAT2.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-140">[BAPI_RFC_NAME] = The RFC name for the BAPI; for example, BAPI_SALESORDER_CREATEFROMDAT2.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9e0b2-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e0b2-141">See Also</span></span>  
 [<span data-ttu-id="9e0b2-142">Los mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="9e0b2-142">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)