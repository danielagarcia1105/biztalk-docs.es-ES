---
title: Propiedades de Descriptor de mensajes TIBCO Enterprise Message Service | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message descriptor properties
ms.assetid: fc164c12-6dc3-4b74-9aa9-024e18faf80a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80c75875c44c4d082089fc9394fef390a0f91571
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-enterprise-message-service-message-descriptor-properties"></a><span data-ttu-id="9c30d-102">Propiedades del descriptor de mensajes de TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="9c30d-102">TIBCO Enterprise Message Service Message Descriptor Properties</span></span>
<span data-ttu-id="9c30d-103">En la tabla siguiente se muestra el conjunto completo de propiedades disponibles del descriptor de mensajes (estructura TibcoEMSMD), así como los valores y tipos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="9c30d-103">The following table shows the complete set of available Message Descriptor (TibcoEMSMD structure) properties and their corresponding types and values.</span></span>  
  
|<span data-ttu-id="9c30d-104">Nombre</span><span class="sxs-lookup"><span data-stu-id="9c30d-104">Name</span></span>|<span data-ttu-id="9c30d-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="9c30d-105">Type</span></span>|<span data-ttu-id="9c30d-106">Value</span><span class="sxs-lookup"><span data-stu-id="9c30d-106">Value</span></span>|<span data-ttu-id="9c30d-107">Notas</span><span class="sxs-lookup"><span data-stu-id="9c30d-107">Notes</span></span>|  
|----------|----------|-----------|-----------|  
|<span data-ttu-id="9c30d-108">TibcoEMS .CorrelationID</span><span class="sxs-lookup"><span data-stu-id="9c30d-108">TibcoEMS .CorrelationID</span></span>|<span data-ttu-id="9c30d-109">string</span><span class="sxs-lookup"><span data-stu-id="9c30d-109">string</span></span>|||  
|<span data-ttu-id="9c30d-110">TibcoEMS .DelieveryMode</span><span class="sxs-lookup"><span data-stu-id="9c30d-110">TibcoEMS .DelieveryMode</span></span>|<span data-ttu-id="9c30d-111">string</span><span class="sxs-lookup"><span data-stu-id="9c30d-111">string</span></span>|<span data-ttu-id="9c30d-112">Uno PERSISTENT o NON-PERSISTENT</span><span class="sxs-lookup"><span data-stu-id="9c30d-112">One of PERSISENT or NON-PERSISTENT</span></span>||  
|<span data-ttu-id="9c30d-113">TibcoEMS .Destination</span><span class="sxs-lookup"><span data-stu-id="9c30d-113">TibcoEMS .Destination</span></span>|<span data-ttu-id="9c30d-114">string</span><span class="sxs-lookup"><span data-stu-id="9c30d-114">string</span></span>||<span data-ttu-id="9c30d-115">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c30d-115">Read-only</span></span>|  
|<span data-ttu-id="9c30d-116">TibcoEMS .Expiration</span><span class="sxs-lookup"><span data-stu-id="9c30d-116">TibcoEMS .Expiration</span></span>|<span data-ttu-id="9c30d-117">long</span><span class="sxs-lookup"><span data-stu-id="9c30d-117">long</span></span>|||  
|<span data-ttu-id="9c30d-118">TibcoEMS .MessageID</span><span class="sxs-lookup"><span data-stu-id="9c30d-118">TibcoEMS .MessageID</span></span>|<span data-ttu-id="9c30d-119">string</span><span class="sxs-lookup"><span data-stu-id="9c30d-119">string</span></span>||<span data-ttu-id="9c30d-120">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c30d-120">Read-only</span></span>|  
|<span data-ttu-id="9c30d-121">TibcoEMS .Priority</span><span class="sxs-lookup"><span data-stu-id="9c30d-121">TibcoEMS .Priority</span></span>|<span data-ttu-id="9c30d-122">integer</span><span class="sxs-lookup"><span data-stu-id="9c30d-122">integer</span></span>|<span data-ttu-id="9c30d-123">De 0 a 9</span><span class="sxs-lookup"><span data-stu-id="9c30d-123">From 0 to 9</span></span>||  
|<span data-ttu-id="9c30d-124">TibcoEMS .Redelivered</span><span class="sxs-lookup"><span data-stu-id="9c30d-124">TibcoEMS .Redelivered</span></span>|<span data-ttu-id="9c30d-125">boolean</span><span class="sxs-lookup"><span data-stu-id="9c30d-125">boolean</span></span>||<span data-ttu-id="9c30d-126">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c30d-126">Read-only</span></span>|  
|<span data-ttu-id="9c30d-127">TibcoEMS .ReplyTo</span><span class="sxs-lookup"><span data-stu-id="9c30d-127">TibcoEMS .ReplyTo</span></span>|<span data-ttu-id="9c30d-128">string</span><span class="sxs-lookup"><span data-stu-id="9c30d-128">string</span></span>|<span data-ttu-id="9c30d-129">Similar al destino</span><span class="sxs-lookup"><span data-stu-id="9c30d-129">Similar to Destination</span></span>||  
|<span data-ttu-id="9c30d-130">TibcoEMS .Timestamp</span><span class="sxs-lookup"><span data-stu-id="9c30d-130">TibcoEMS .Timestamp</span></span>|<span data-ttu-id="9c30d-131">long</span><span class="sxs-lookup"><span data-stu-id="9c30d-131">long</span></span>||<span data-ttu-id="9c30d-132">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c30d-132">Read-only</span></span>|  
  
 <span data-ttu-id="9c30d-133">Las propiedades de solo lectura son aquellas que TIBCO Enterprise Message Service establece cuando el mensaje se entrega al adaptador de Microsoft BizTalk para TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="9c30d-133">The read-only properties are those properties that are set by TIBCO Enterprise Message Service when the message is delivered to Microsoft BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="9c30d-134">Cambiar el valor, aunque es posible en la expresión de la forma de asignación del mensaje, no afecta al mensaje.</span><span class="sxs-lookup"><span data-stu-id="9c30d-134">Changing the value, although it is possible in the expression of the message assignment shape, does not affect the message.</span></span>  
  
 <span data-ttu-id="9c30d-135">Para otras propiedades que se deben mover del mensaje de EMS al mensaje de BizTalk Server, se debe crear un DLL de propiedades y usarlo en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9c30d-135">For other properties that must be moved from the EMS message to the BizTalk Server message, you must create a properties DLL and use it in the project.</span></span>  
  
 <span data-ttu-id="9c30d-136">El siguiente ejemplo de esquema de propiedades permite que la orquestación use la propiedad de mensaje `JMSXDeliveryCount`.</span><span class="sxs-lookup"><span data-stu-id="9c30d-136">The following sample properties schema enables the orchestration to use the `JMSXDeliveryCount` message property.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://schemas.microsoft.com/BizTalk/TibcoEMS-properties" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
        <xs:appinfo>  
            <b:schemaInfo schema_type="property" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" />  
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="JMSXDeliveryCount" type="xs:long">  
        <xs:annotation>  
            <xs:appinfo>  
                <b:fieldInfo propertyGuid="f62f1a4b-a528-45fb-b1f8-bd880e9f46db" />  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
</xs:schema>   
```  
  
 <span data-ttu-id="9c30d-137">Asegúrese de que se usa el espacio de nombres de destino; únicamente la propiedades que usan este espacio de nombres se copian al mensaje de BizTalk Server o de EMS.</span><span class="sxs-lookup"><span data-stu-id="9c30d-137">Make sure that the target namespace is used; only properties that use this namespace are copied to the BizTalk Server message or to the EMS message.</span></span> <span data-ttu-id="9c30d-138">Consulte la documentación de BizTalk Server para obtener más información acerca de las propiedades de contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9c30d-138">See the BizTalk Server documentation for more information about message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c30d-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c30d-139">See Also</span></span>  
 [<span data-ttu-id="9c30d-140">Propiedades de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="9c30d-140">Message Context Properties</span></span>](../core/message-context-properties2.md)