---
title: Esquemas de mensajes para operaciones de BAPI | Documentos de Microsoft
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
ms.openlocfilehash: 999e60a7e2cac827031ea2a19f9482d9da0baaa6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217452"
---
# <a name="message-schemas-for-bapi-operations"></a><span data-ttu-id="2bf02-102">Esquemas de mensaje para las operaciones de BAPI</span><span class="sxs-lookup"><span data-stu-id="2bf02-102">Message Schemas for BAPI Operations</span></span>
<span data-ttu-id="2bf02-103">Las secciones siguientes describen los esquemas de mensaje y acciones de mensaje que se usan para invocar BAPI en el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como métodos de objetos comerciales.</span><span class="sxs-lookup"><span data-stu-id="2bf02-103">The following sections describe the message schemas and message actions used to invoke BAPIs on the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as methods of business objects.</span></span> <span data-ttu-id="2bf02-104">También puede invocar BAPI como operaciones de RFC en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="2bf02-104">You can also invoke BAPIs as RFC operations on the adapter.</span></span> <span data-ttu-id="2bf02-105">Para obtener más información acerca de los mensajes que se utiliza para invocar las solicitudes de cambio, consulte [esquemas de mensaje para las operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span><span class="sxs-lookup"><span data-stu-id="2bf02-105">For more information about the messages used to invoke RFCs, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span> <span data-ttu-id="2bf02-106">Independientemente de cómo invocar una BAPI en el adaptador, el adaptador, siempre invoca la BAPI como una solicitud de cambio en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2bf02-106">Regardless of how you invoke a BAPI on the adapter, the adapter always invokes the BAPI as an RFC on the SAP system.</span></span> <span data-ttu-id="2bf02-107">Para obtener información general del uso del [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite BAPI, consulte [operaciones de BAPI en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="2bf02-107">For an overview of how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports BAPIs, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  
  
## <a name="message-structure-for-business-object-operations"></a><span data-ttu-id="2bf02-108">Estructura de los mensajes para las operaciones de objeto de negocios</span><span class="sxs-lookup"><span data-stu-id="2bf02-108">Message Structure for Business Object Operations</span></span>  
 <span data-ttu-id="2bf02-109">La siguiente tabla muestra los esquemas de mensaje utilizados para invocar una BAPI como un método del objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="2bf02-109">The following table shows the message schemas used to invoke a BAPI as a business object method.</span></span>  
  
|<span data-ttu-id="2bf02-110">Operación</span><span class="sxs-lookup"><span data-stu-id="2bf02-110">Operation</span></span>|<span data-ttu-id="2bf02-111">Estructura XML</span><span class="sxs-lookup"><span data-stu-id="2bf02-111">XML Structure</span></span>|<span data-ttu-id="2bf02-112">Description</span><span class="sxs-lookup"><span data-stu-id="2bf02-112">Description</span></span>|  
|---------------|-------------------|-----------------|  
|<span data-ttu-id="2bf02-113">[BUSOBJ_METHOD]</span><span class="sxs-lookup"><span data-stu-id="2bf02-113">[BUSOBJ_METHOD]</span></span>|`<[BUSOBJ_METHOD] xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]>`|<span data-ttu-id="2bf02-114">Invocar un método de objeto de negocio en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2bf02-114">Invoke a business object method on an SAP system.</span></span><br /><br /> <span data-ttu-id="2bf02-115">Se admiten la importación, cambiar y parámetros de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2bf02-115">Import, changing, and table parameters are supported.</span></span>|  
|<span data-ttu-id="2bf02-116">[BUSOBJ_METHOD] Respuesta</span><span class="sxs-lookup"><span data-stu-id="2bf02-116">[BUSOBJ_METHOD] Response</span></span>|`<[BUSOBJ_METHOD]Response xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]Response>`|<span data-ttu-id="2bf02-117">Respuesta de método del objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="2bf02-117">Business object method response.</span></span><br /><br /> <span data-ttu-id="2bf02-118">Exportar, cambiar, y se admiten los parámetros de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2bf02-118">Export, changing, and table parameters are supported.</span></span><br /><br /> <span data-ttu-id="2bf02-119">**Tenga en cuenta** de forma predeterminada, los parámetros de tabla no aparecen en el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="2bf02-119">**Note** By default, table parameters are not surfaced in the response message.</span></span> <span data-ttu-id="2bf02-120">Si se requieren parámetros de la tabla en el mensaje de respuesta, debe pasar parámetros de una tabla vacía en el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="2bf02-120">If you require table parameters in response message, you must pass empty table parameters in the request message.</span></span>|  
  
 <span data-ttu-id="2bf02-121">[Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.</span><span class="sxs-lookup"><span data-stu-id="2bf02-121">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  
  
 <span data-ttu-id="2bf02-122">[BUSOBJ_METHOD] = el nombre de un método de objeto comercial; Por ejemplo, CREATEFROMDAT2.</span><span class="sxs-lookup"><span data-stu-id="2bf02-122">[BUSOBJ_METHOD] = The name of a business object method; for example, CREATEFROMDAT2.</span></span>  
  
 <span data-ttu-id="2bf02-123">[IN_PARAM_NAME] = el nombre de un parámetro de importación BAPI.</span><span class="sxs-lookup"><span data-stu-id="2bf02-123">[IN_PARAM_NAME] =The name of a BAPI import parameter.</span></span>  
  
 <span data-ttu-id="2bf02-124">[OUT_PARAM_NAME] = el nombre de un parámetro de exportación BAPI.</span><span class="sxs-lookup"><span data-stu-id="2bf02-124">[OUT_PARAM_NAME] = The name of a BAPI export parameter.</span></span>  
  
 <span data-ttu-id="2bf02-125">[INOUT_PARAM_NAME] = el nombre de un BAPI cambiar el parámetro.</span><span class="sxs-lookup"><span data-stu-id="2bf02-125">[INOUT_PARAM_NAME] = The name of a BAPI changing parameter.</span></span>  
  
 <span data-ttu-id="2bf02-126">[TABLE_PARAM_NAME] = el nombre de un parámetro de la tabla BAPI.</span><span class="sxs-lookup"><span data-stu-id="2bf02-126">[TABLE_PARAM_NAME] = The name of a BAPI table parameter.</span></span>  
  
 <span data-ttu-id="2bf02-127">[STRUCT_PARAM_NAME] = el nombre de un parámetro de estructura BAPI.</span><span class="sxs-lookup"><span data-stu-id="2bf02-127">[STRUCT_PARAM_NAME] = The name of a BAPI structure parameter.</span></span>  
  
## <a name="message-actions-for-business-object-operations"></a><span data-ttu-id="2bf02-128">Acciones de mensaje para las operaciones de objeto de negocios</span><span class="sxs-lookup"><span data-stu-id="2bf02-128">Message Actions for Business Object Operations</span></span>  
 <span data-ttu-id="2bf02-129">La siguiente tabla muestra las acciones de mensaje que se usan para invocar BAPI como métodos de objetos comerciales.</span><span class="sxs-lookup"><span data-stu-id="2bf02-129">The following table shows the message actions that are used to invoke BAPIs as business object methods.</span></span>  
  
|<span data-ttu-id="2bf02-130">Operación</span><span class="sxs-lookup"><span data-stu-id="2bf02-130">Operation</span></span>|<span data-ttu-id="2bf02-131">Acción de mensaje</span><span class="sxs-lookup"><span data-stu-id="2bf02-131">Message Action</span></span>|<span data-ttu-id="2bf02-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2bf02-132">Example</span></span>|  
|---------------|--------------------|-------------|  
|<span data-ttu-id="2bf02-133">[BUSOBJ_METHOD]</span><span class="sxs-lookup"><span data-stu-id="2bf02-133">[BUSOBJ_METHOD]</span></span>|<span data-ttu-id="2bf02-134">/Bapi/ [versión] [BUSOBJ_NAME] / [BUSOBJ_METHOD] / [BAPI_RFC_NAME]</span><span class="sxs-lookup"><span data-stu-id="2bf02-134">[VERSION]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]</span></span>|<span data-ttu-id="2bf02-135">http://Microsoft.LobServices.SAP/2007/03/BAPI/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2</span><span class="sxs-lookup"><span data-stu-id="2bf02-135">http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2</span></span>|  
|<span data-ttu-id="2bf02-136">[BUSOBJ_METHOD] Respuesta</span><span class="sxs-lookup"><span data-stu-id="2bf02-136">[BUSOBJ_METHOD] Response</span></span>|<span data-ttu-id="2bf02-137">/Bapi/ [versión] [BUSOBJ_NAME] / [BUSOBJ_METHOD] / [BAPI_RFC_NAME] / respuesta</span><span class="sxs-lookup"><span data-stu-id="2bf02-137">[VERSION]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]/response</span></span>|<span data-ttu-id="2bf02-138">http://Microsoft.LobServices.SAP/2007/03/BAPI/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2/Response</span><span class="sxs-lookup"><span data-stu-id="2bf02-138">http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2/response</span></span>|  
  
 <span data-ttu-id="2bf02-139">[Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.</span><span class="sxs-lookup"><span data-stu-id="2bf02-139">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  
  
 <span data-ttu-id="2bf02-140">[BUSOBJ_NAME] = el nombre del objeto de negocios; Por ejemplo, BUS2032.</span><span class="sxs-lookup"><span data-stu-id="2bf02-140">[BUSOBJ_NAME] = The name of the business object; for example, BUS2032.</span></span>  
  
 <span data-ttu-id="2bf02-141">[BUSOBJ_METHOD] = el método del objeto comercial; Por ejemplo, CREATEFROMDAT2.</span><span class="sxs-lookup"><span data-stu-id="2bf02-141">[BUSOBJ_METHOD] = The method of the business object; for example, CREATEFROMDAT2.</span></span>  
  
 <span data-ttu-id="2bf02-142">[BAPI_RFC_NAME] = nombre de la RFC de BAPI; Por ejemplo, BAPI_SALESORDER_CREATEFROMDAT2.</span><span class="sxs-lookup"><span data-stu-id="2bf02-142">[BAPI_RFC_NAME] = The RFC name for the BAPI; for example, BAPI_SALESORDER_CREATEFROMDAT2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf02-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bf02-143">See Also</span></span>  
 [<span data-ttu-id="2bf02-144">Mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="2bf02-144">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)