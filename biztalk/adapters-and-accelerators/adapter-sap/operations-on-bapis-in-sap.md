---
title: Operaciones de BAPI en SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAPI, operations
- BAPIs, operations on
- Business Application Programming Interface
- BAPIs
- BAPI, transactions
- BAPI transactions, limitations on
ms.assetid: 6be26641-e8d3-4e11-8d82-4fdb13076580
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8504dd05c671307085d621c474969a70026d2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-bapis-in-sap"></a><span data-ttu-id="c35ad-102">Operaciones de BAPI en SAP</span><span class="sxs-lookup"><span data-stu-id="c35ad-102">Operations on BAPIs in SAP</span></span>
<span data-ttu-id="c35ad-103">Una interfaz de programación de aplicación de empresariales (BAPI) es un método de un objeto de negocios SAP que puede llamarse mediante un proceso externo.</span><span class="sxs-lookup"><span data-stu-id="c35ad-103">A Business Application Programming Interface (BAPI) is a method of a SAP business object that can be called by an external process.</span></span> <span data-ttu-id="c35ad-104">BAPI es transaccional en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="c35ad-104">BAPIs are transactional on the SAP system.</span></span>  
  
 <span data-ttu-id="c35ad-105">El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] admite BAPI llama en la dirección de salida.</span><span class="sxs-lookup"><span data-stu-id="c35ad-105">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] supports BAPI calls in the outbound direction.</span></span> <span data-ttu-id="c35ad-106">Pone de manifiesto BAPI de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="c35ad-106">It surfaces BAPIs in two ways:</span></span>  
  
-   <span data-ttu-id="c35ad-107">**Como una RFC**.</span><span class="sxs-lookup"><span data-stu-id="c35ad-107">**As an RFC**.</span></span> <span data-ttu-id="c35ad-108">Puede invocar una BAPI invocando la RFC adecuada.</span><span class="sxs-lookup"><span data-stu-id="c35ad-108">You can invoke a BAPI directly by invoking the appropriate RFC.</span></span>  
  
-   <span data-ttu-id="c35ad-109">**Como métodos de objetos comerciales**.</span><span class="sxs-lookup"><span data-stu-id="c35ad-109">**As methods of business objects**.</span></span> <span data-ttu-id="c35ad-110">El adaptador Emerge BAPI como métodos de objetos comerciales como una comodidad para ayudarle a recuperar los metadatos cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c35ad-110">The adapter surfaces BAPIs as methods of business objects as a convenience to help you retrieve metadata when you use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c35ad-111">Puede invocar una BAPI en el adaptador como una solicitud de cambio o como un método de un objeto de negocios; pero independientemente de cómo invocar la BAPI en el adaptador, invoca siempre la BAPI en SAP a través de la interfaz RFC.</span><span class="sxs-lookup"><span data-stu-id="c35ad-111">You can invoke a BAPI on the adapter as an RFC or as a method of a business object; but regardless of how you invoke the BAPI on the adapter, it always invokes the BAPI on SAP through the RFC interface.</span></span>  
  
 <span data-ttu-id="c35ad-112">El adaptador admite transacciones de BAPI.</span><span class="sxs-lookup"><span data-stu-id="c35ad-112">The adapter supports BAPI transactions.</span></span> <span data-ttu-id="c35ad-113">El modelo de transacción BAPI en SAP permite a los usuarios combinar varias BAPI en una unidad lógica de trabajo (LUW).</span><span class="sxs-lookup"><span data-stu-id="c35ad-113">The BAPI transaction model on SAP enables users to combine several BAPIs into one logical unit of work (LUW).</span></span> <span data-ttu-id="c35ad-114">Un LUW de SAP está formada por todos los pasos implicados en una transacción incluida la actualización de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c35ad-114">An SAP LUW consists of all the steps involved in a transaction including updating the database.</span></span>  
  
 <span data-ttu-id="c35ad-115">Los temas de esta sección explican cómo BAPI aparecen como objetos de negocios y cómo se admiten las transacciones de BAPI (LUWs) por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="c35ad-115">The topics in this section explain how BAPIs are surfaced as business objects and how BAPI transactions (LUWs) are supported by the adapter.</span></span>  
 
  
## <a name="bapi-operations-as-business-object-methods"></a><span data-ttu-id="c35ad-116">Operaciones de BAPI (como métodos de objetos comerciales)</span><span class="sxs-lookup"><span data-stu-id="c35ad-116">BAPI Operations (as Business Object Methods)</span></span>  
 <span data-ttu-id="c35ad-117">El adaptador de superficies BAPI como métodos de objetos de negocio como una comodidad para ayudarle a recuperar los metadatos cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c35ad-117">The adapter surfaces BAPIs as business objects methods as a convenience to help you retrieve metadata when you use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="c35ad-118">El adaptador siempre invoca en el sistema SAP mediante la interfaz de RFC BAPI.</span><span class="sxs-lookup"><span data-stu-id="c35ad-118">The adapter always invokes BAPIs on the SAP system using the RFC interface.</span></span>  
  
 <span data-ttu-id="c35ad-119">El adaptador de superficies BAPI por su nombre como operaciones bajo el objeto de negocios adecuada para las operaciones de salida.</span><span class="sxs-lookup"><span data-stu-id="c35ad-119">The adapter surfaces BAPIs by name as operations under the appropriate business object for outbound operations.</span></span> <span data-ttu-id="c35ad-120">Objetos de negocios se recopilan por grupo funcional en el nodo de categoría BAPI por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="c35ad-120">Business objects are collected by functional group under the BAPI category node by the adapter.</span></span> <span data-ttu-id="c35ad-121">(Se puede examinar o buscar BAPI en y objetos de negocios de la **BAPI** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="c35ad-121">(You can browse or search for business objects and BAPIs under the **BAPI** node when you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)</span></span>  
  
 <span data-ttu-id="c35ad-122">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite las siguientes en BAPI:</span><span class="sxs-lookup"><span data-stu-id="c35ad-122">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following on BAPIs:</span></span>  
  
-   <span data-ttu-id="c35ad-123">IMPORTACIÓN de parámetros</span><span class="sxs-lookup"><span data-stu-id="c35ad-123">IMPORT parameters</span></span>  
  
-   <span data-ttu-id="c35ad-124">Parámetros de exportación</span><span class="sxs-lookup"><span data-stu-id="c35ad-124">EXPORT parameters</span></span>  
  
-   <span data-ttu-id="c35ad-125">VARIABLES parámetros</span><span class="sxs-lookup"><span data-stu-id="c35ad-125">CHANGING parameters</span></span>  
  
-   <span data-ttu-id="c35ad-126">Parámetros de la tabla</span><span class="sxs-lookup"><span data-stu-id="c35ad-126">Table parameters</span></span>  
  
 <span data-ttu-id="c35ad-127">Para obtener más información sobre las estructuras de mensajes y acciones de SOAP que se usan para BAPI aparecen como métodos de objetos comerciales, vea [esquemas de mensaje para las operaciones de BAPI](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c35ad-127">For more information about the message structures and SOAP actions used for BAPIs surfaced as business object methods, see [Message Schemas for BAPI Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md).</span></span>  
  
## <a name="bapi-transactions"></a><span data-ttu-id="c35ad-128">Transacciones de BAPI</span><span class="sxs-lookup"><span data-stu-id="c35ad-128">BAPI Transactions</span></span>  
 <span data-ttu-id="c35ad-129">Cuando se invoca una BAPI, siempre es parte de un LUW en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="c35ad-129">When you invoke a BAPI, it is always part of an LUW on the SAP system.</span></span> <span data-ttu-id="c35ad-130">Esto es cierto si se invoca la BAPI como una solicitud de cambio o como un método de un objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="c35ad-130">This is true whether you invoke the BAPI as an RFC or as a method of a business object.</span></span> <span data-ttu-id="c35ad-131">RFC SDK trata todos los BAPI enviado a través de la misma conexión de SAP como parte de la misma LUW.</span><span class="sxs-lookup"><span data-stu-id="c35ad-131">The RFC SDK treats all BAPIs sent over the same SAP connection as part of the same LUW.</span></span> <span data-ttu-id="c35ad-132">Después de llamar a confirmar o revertir la transacción en una conexión, el siguiente BAPI enviada a través de la conexión comienza un nuevo LUW.</span><span class="sxs-lookup"><span data-stu-id="c35ad-132">After a call to commit or roll back the transaction on a connection, the next BAPI sent over the connection begins a new LUW.</span></span>  
  
 <span data-ttu-id="c35ad-133">Se llama a BAPI_TRANSACTION_COMMIT o BAPI_TRANSACTION_ROLLBACK para confirmar o revertir la transacción.</span><span class="sxs-lookup"><span data-stu-id="c35ad-133">You call BAPI_TRANSACTION_COMMIT or BAPI_TRANSACTION_ROLLBACK to commit or roll back the transaction.</span></span> <span data-ttu-id="c35ad-134">El adaptador de superficies de estos dos BAPI:</span><span class="sxs-lookup"><span data-stu-id="c35ad-134">The adapter surfaces these two BAPIs:</span></span>  
  
-   <span data-ttu-id="c35ad-135">En el nodo de base como operaciones de RFC.</span><span class="sxs-lookup"><span data-stu-id="c35ad-135">Under the Basis node as RFC operations.</span></span>  
  
-   <span data-ttu-id="c35ad-136">En cada objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="c35ad-136">Under each business object.</span></span>  
  
 <span data-ttu-id="c35ad-137">Controlar la BAPI en una transacción asegurándose de que todas las envíen a través de la misma conexión de SAP (incluida la llamada para confirmar o revertir la transacción).</span><span class="sxs-lookup"><span data-stu-id="c35ad-137">You control the BAPIs in a transaction by ensuring that they are all sent over the same SAP connection (including the call to commit or roll back the transaction).</span></span> <span data-ttu-id="c35ad-138">Para hacer esto:</span><span class="sxs-lookup"><span data-stu-id="c35ad-138">You can do this in:</span></span>  
  
-   <span data-ttu-id="c35ad-139">Soluciones de BizTalk mediante el uso de la **ConnectionState** message (propiedad) contexto para asegurarse de que la BAPI en una transacción se envía con la misma conexión.</span><span class="sxs-lookup"><span data-stu-id="c35ad-139">BizTalk Solutions by using the **ConnectionState** message context property to ensure that the BAPIs in a transaction are sent using the same connection.</span></span> <span data-ttu-id="c35ad-140">Esta propiedad es obtenida por el adaptador y proporciona un control explícito sobre la conexión usada para enviar un mensaje en una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c35ad-140">This property is surfaced by the adapter and provides you with explicit control over the connection used to send a message in a BizTalk orchestration.</span></span>  
  
     <span data-ttu-id="c35ad-141">Para realizar transacciones de BAPI mediante BizTalk Server, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite las siguientes propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c35ad-141">For performing BAPI transactions using BizTalk Server, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following message context properties.</span></span>  
  
    |<span data-ttu-id="c35ad-142">Campo</span><span class="sxs-lookup"><span data-stu-id="c35ad-142">Field</span></span>|<span data-ttu-id="c35ad-143">Description</span><span class="sxs-lookup"><span data-stu-id="c35ad-143">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="c35ad-144">OPEN</span><span class="sxs-lookup"><span data-stu-id="c35ad-144">OPEN</span></span>|<span data-ttu-id="c35ad-145">Abre un canal nuevo para la transacción.</span><span class="sxs-lookup"><span data-stu-id="c35ad-145">Opens a new channel for the transaction.</span></span>|  
    |<span data-ttu-id="c35ad-146">VOLVER A USAR</span><span class="sxs-lookup"><span data-stu-id="c35ad-146">REUSE</span></span>|<span data-ttu-id="c35ad-147">Reutilizar un canal existente para la transacción.</span><span class="sxs-lookup"><span data-stu-id="c35ad-147">Reuse existing channel for the transaction.</span></span>|  
    |<span data-ttu-id="c35ad-148">CLOSE</span><span class="sxs-lookup"><span data-stu-id="c35ad-148">CLOSE</span></span>|<span data-ttu-id="c35ad-149">Confirmar la transacción y cierre el canal existente.</span><span class="sxs-lookup"><span data-stu-id="c35ad-149">Commit the transaction and close the existing channel.</span></span>|  
    |<span data-ttu-id="c35ad-150">ANULACIÓN</span><span class="sxs-lookup"><span data-stu-id="c35ad-150">ABORT</span></span>|<span data-ttu-id="c35ad-151">Anular la transacción y cierre el canal existente.</span><span class="sxs-lookup"><span data-stu-id="c35ad-151">Abort the transaction and close the existing channel.</span></span>|  
  
     <span data-ttu-id="c35ad-152">Para obtener más información, consulte [ejecutar BAPI transacciones en SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="c35ad-152">For more information, see [Run BAPI Transactions in SAP using BizTalk Server](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c35ad-153">Asegúrese de establecer el **EnableBizTalkCompatibilityMode**propiedad de enlace al realizar las transacciones que usan el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c35ad-153">Make sure you set the **EnableBizTalkCompatibilityMode**binding property when performing transactions using BizTalk Server.</span></span>  
  
-   <span data-ttu-id="c35ad-154">Soluciones de modelo de servicio WCF asegurándose de que la BAPI en una transacción se envía con el mismo cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="c35ad-154">WCF service model solutions by ensuring that the BAPIs in a transaction are sent using the same WCF client.</span></span> <span data-ttu-id="c35ad-155">Para obtener más información, consulte [invocar BAPI en SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="c35ad-155">For more information, see [Invoke BAPIs in SAP using WCF Service Model](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="c35ad-156">WCF canal soluciones de modelos asegurándose de que la BAPI en una transacción se envía a través del mismo canal WCF.</span><span class="sxs-lookup"><span data-stu-id="c35ad-156">WCF channel model solutions by ensuring that the BAPIs in a transaction are sent over the same WCF channel.</span></span> <span data-ttu-id="c35ad-157">Para obtener más información, consulte [desarrollar aplicaciones mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="c35ad-157">For more information, see [Develop applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).</span></span>  
  
### <a name="limitations-on-bapi-transactions"></a><span data-ttu-id="c35ad-158">Limitaciones de las transacciones de BAPI</span><span class="sxs-lookup"><span data-stu-id="c35ad-158">Limitations on BAPI Transactions</span></span>  
 <span data-ttu-id="c35ad-159">Se aplican las siguientes restricciones en las transacciones de BAPI:</span><span class="sxs-lookup"><span data-stu-id="c35ad-159">The following restrictions apply on BAPI transactions:</span></span>  
  
-   <span data-ttu-id="c35ad-160">No es posible crear dos accesos de escritura en la misma instancia dentro de un LUW.</span><span class="sxs-lookup"><span data-stu-id="c35ad-160">It is not possible to make two write accesses on the same instance within one LUW.</span></span> <span data-ttu-id="c35ad-161">Por ejemplo, no puede crear un pedido y actualizarlo en la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="c35ad-161">For example, you cannot create an order and update it in the same transaction.</span></span>  
  
-   <span data-ttu-id="c35ad-162">Al realizar una transacción mediante BAPI [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], todos los mensajes se deben enviar a través de una instancia de host del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="c35ad-162">When performing BAPI a transaction using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], all the messages must be sent over a single host instance of the send port.</span></span>  
  
-   <span data-ttu-id="c35ad-163">Si una instancia se crea, actualiza o elimina mediante el uso de una operación de escritura BAPI, una lectura BAPI no podrá ver los datos más recientes, hasta que se confirma la operación de escritura BAPI.</span><span class="sxs-lookup"><span data-stu-id="c35ad-163">If an instance is created, updated, or deleted by using a write BAPI, a read BAPI cannot view the most recent data until the write BAPI is committed.</span></span>  
  
-   <span data-ttu-id="c35ad-164">Un cliente externo que invoca un LUW debería llamar a todos lo BAPI que contiene el LUW en la misma conexión de SAP.</span><span class="sxs-lookup"><span data-stu-id="c35ad-164">An external client that invokes an LUW should call all the BAPIs that the LUW contains on the same SAP connection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c35ad-165">BAPI que pertenecen a la versión 3.1, llame a COMMIT WORK como parte de su implementación.</span><span class="sxs-lookup"><span data-stu-id="c35ad-165">BAPIs that belong to Release 3.1 call COMMIT WORK as part of their implementation.</span></span> <span data-ttu-id="c35ad-166">Esto significa que estos BAPI no puede incluirse con otra BAPI en un LUW (debido a confirmación la transacción).</span><span class="sxs-lookup"><span data-stu-id="c35ad-166">This means that these BAPIs cannot be included with other BAPIs in an LUW (because they will commit the transaction).</span></span> <span data-ttu-id="c35ad-167">Para obtener más información, consulte la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="c35ad-167">For more information, see the SAP documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c35ad-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="c35ad-168">See Also</span></span>  
 <span data-ttu-id="c35ad-169">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="c35ad-169">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>