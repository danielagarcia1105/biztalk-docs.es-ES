---
title: Operaciones en BAPI de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI, operations
- BAPIs, operations on
- Business Application Programming Interface
- BAPIs
- BAPI, transactions
- BAPI transactions, limitations on
ms.assetid: 6be26641-e8d3-4e11-8d82-4fdb13076580
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a319626f23b825187d65e01d687be5a1079df53a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993173"
---
# <a name="operations-on-bapis-in-sap"></a><span data-ttu-id="cde87-102">Operaciones en BAPI de SAP</span><span class="sxs-lookup"><span data-stu-id="cde87-102">Operations on BAPIs in SAP</span></span>
<span data-ttu-id="cde87-103">Una interfaz de programación Business Application (BAPI) es un método de un objeto de negocios SAP que se puede llamar a un proceso externo.</span><span class="sxs-lookup"><span data-stu-id="cde87-103">A Business Application Programming Interface (BAPI) is a method of a SAP business object that can be called by an external process.</span></span> <span data-ttu-id="cde87-104">BAPI es transaccional en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="cde87-104">BAPIs are transactional on the SAP system.</span></span>  
  
 <span data-ttu-id="cde87-105">El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] admite BAPI llama en la dirección de salida.</span><span class="sxs-lookup"><span data-stu-id="cde87-105">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] supports BAPI calls in the outbound direction.</span></span> <span data-ttu-id="cde87-106">Pone de manifiesto BAPI de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="cde87-106">It surfaces BAPIs in two ways:</span></span>  
  
- <span data-ttu-id="cde87-107">**Como una RFC**.</span><span class="sxs-lookup"><span data-stu-id="cde87-107">**As an RFC**.</span></span> <span data-ttu-id="cde87-108">Puede invocar una BAPI invocando la RFC adecuada.</span><span class="sxs-lookup"><span data-stu-id="cde87-108">You can invoke a BAPI directly by invoking the appropriate RFC.</span></span>  
  
- <span data-ttu-id="cde87-109">**Como los métodos de objetos de negocios**.</span><span class="sxs-lookup"><span data-stu-id="cde87-109">**As methods of business objects**.</span></span> <span data-ttu-id="cde87-110">El adaptador presenta BAPI como métodos de objetos de negocios como una comodidad para ayudarle a recuperar los metadatos cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cde87-110">The adapter surfaces BAPIs as methods of business objects as a convenience to help you retrieve metadata when you use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cde87-111">Puede invocar una BAPI en el adaptador como una solicitud de cambio o como un método de un objeto comercial; pero, independientemente de cómo invocar la BAPI en el adaptador, siempre invoca la BAPI de SAP a través de la interfaz RFC.</span><span class="sxs-lookup"><span data-stu-id="cde87-111">You can invoke a BAPI on the adapter as an RFC or as a method of a business object; but regardless of how you invoke the BAPI on the adapter, it always invokes the BAPI on SAP through the RFC interface.</span></span>  
  
 <span data-ttu-id="cde87-112">El adaptador admite transacciones de BAPI.</span><span class="sxs-lookup"><span data-stu-id="cde87-112">The adapter supports BAPI transactions.</span></span> <span data-ttu-id="cde87-113">El modelo de transacciones de BAPI de SAP permite a los usuarios combinar varios BAPI en una unidad lógica de trabajo (LUW).</span><span class="sxs-lookup"><span data-stu-id="cde87-113">The BAPI transaction model on SAP enables users to combine several BAPIs into one logical unit of work (LUW).</span></span> <span data-ttu-id="cde87-114">Un LUW SAP consta de todos los pasos implicados en una transacción incluida la actualización de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cde87-114">An SAP LUW consists of all the steps involved in a transaction including updating the database.</span></span>  
  
 <span data-ttu-id="cde87-115">Los temas de esta sección explican cómo BAPI se expone como objetos de negocios y cómo se admiten las transacciones de BAPI (LUWs) por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="cde87-115">The topics in this section explain how BAPIs are surfaced as business objects and how BAPI transactions (LUWs) are supported by the adapter.</span></span>  
 
  
## <a name="bapi-operations-as-business-object-methods"></a><span data-ttu-id="cde87-116">Operaciones de BAPI (como métodos de objeto de negocios)</span><span class="sxs-lookup"><span data-stu-id="cde87-116">BAPI Operations (as Business Object Methods)</span></span>  
 <span data-ttu-id="cde87-117">El adaptador presenta BAPI como métodos de objetos de negocio como una comodidad para ayudarle a recuperar los metadatos cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cde87-117">The adapter surfaces BAPIs as business objects methods as a convenience to help you retrieve metadata when you use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="cde87-118">El adaptador invoca siempre BAPI en el sistema SAP mediante la interfaz de RFC.</span><span class="sxs-lookup"><span data-stu-id="cde87-118">The adapter always invokes BAPIs on the SAP system using the RFC interface.</span></span>  
  
 <span data-ttu-id="cde87-119">El adaptador presenta BAPI por su nombre como operaciones en el objeto de negocios adecuados para las operaciones de salida.</span><span class="sxs-lookup"><span data-stu-id="cde87-119">The adapter surfaces BAPIs by name as operations under the appropriate business object for outbound operations.</span></span> <span data-ttu-id="cde87-120">Objetos de negocios se recopilan por grupo funcional en el nodo de categoría BAPI por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="cde87-120">Business objects are collected by functional group under the BAPI category node by the adapter.</span></span> <span data-ttu-id="cde87-121">(Puede examinar o buscar objetos de negocios y BAPI bajo el **BAPI** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="cde87-121">(You can browse or search for business objects and BAPIs under the **BAPI** node when you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)</span></span>  
  
 <span data-ttu-id="cde87-122">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] BAPI admite los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cde87-122">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following on BAPIs:</span></span>  
  
- <span data-ttu-id="cde87-123">IMPORTACIÓN de parámetros</span><span class="sxs-lookup"><span data-stu-id="cde87-123">IMPORT parameters</span></span>  
  
- <span data-ttu-id="cde87-124">Parámetros de exportación</span><span class="sxs-lookup"><span data-stu-id="cde87-124">EXPORT parameters</span></span>  
  
- <span data-ttu-id="cde87-125">Parámetros de variación</span><span class="sxs-lookup"><span data-stu-id="cde87-125">CHANGING parameters</span></span>  
  
- <span data-ttu-id="cde87-126">Parámetros de la tabla</span><span class="sxs-lookup"><span data-stu-id="cde87-126">Table parameters</span></span>  
  
  <span data-ttu-id="cde87-127">Para obtener más información acerca de las estructuras de mensajes y las acciones de SOAP utilizadas para BAPI aparece como métodos de objetos comerciales, vea [esquemas de mensaje para operaciones de BAPI](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md).</span><span class="sxs-lookup"><span data-stu-id="cde87-127">For more information about the message structures and SOAP actions used for BAPIs surfaced as business object methods, see [Message Schemas for BAPI Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md).</span></span>  
  
## <a name="bapi-transactions"></a><span data-ttu-id="cde87-128">Transacciones de BAPI</span><span class="sxs-lookup"><span data-stu-id="cde87-128">BAPI Transactions</span></span>  
 <span data-ttu-id="cde87-129">Cuando se invoca una BAPI, siempre es parte de un LUW en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="cde87-129">When you invoke a BAPI, it is always part of an LUW on the SAP system.</span></span> <span data-ttu-id="cde87-130">Esto es cierto si invocar la BAPI como una solicitud de cambio o como un método de un objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="cde87-130">This is true whether you invoke the BAPI as an RFC or as a method of a business object.</span></span> <span data-ttu-id="cde87-131">El SDK de RFC trata todos los BAPI enviado a través de la misma conexión de SAP como parte de la misma LUW.</span><span class="sxs-lookup"><span data-stu-id="cde87-131">The RFC SDK treats all BAPIs sent over the same SAP connection as part of the same LUW.</span></span> <span data-ttu-id="cde87-132">Después de llamar a confirmar o revertir la transacción en una conexión, el siguiente BAPI enviada a través de la conexión comienza un nuevo LUW.</span><span class="sxs-lookup"><span data-stu-id="cde87-132">After a call to commit or roll back the transaction on a connection, the next BAPI sent over the connection begins a new LUW.</span></span>  
  
 <span data-ttu-id="cde87-133">Se llama a BAPI_TRANSACTION_COMMIT o BAPI_TRANSACTION_ROLLBACK para confirmar o revertir la transacción.</span><span class="sxs-lookup"><span data-stu-id="cde87-133">You call BAPI_TRANSACTION_COMMIT or BAPI_TRANSACTION_ROLLBACK to commit or roll back the transaction.</span></span> <span data-ttu-id="cde87-134">El adaptador presenta estos dos BAPI:</span><span class="sxs-lookup"><span data-stu-id="cde87-134">The adapter surfaces these two BAPIs:</span></span>  
  
- <span data-ttu-id="cde87-135">En el nodo base como las operaciones de RFC.</span><span class="sxs-lookup"><span data-stu-id="cde87-135">Under the Basis node as RFC operations.</span></span>  
  
- <span data-ttu-id="cde87-136">En cada objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="cde87-136">Under each business object.</span></span>  
  
  <span data-ttu-id="cde87-137">Controlar las BAPI en una transacción asegurándose de que todos enviarse a través de la misma conexión de SAP (incluida la llamada al confirmar o revertir la transacción).</span><span class="sxs-lookup"><span data-stu-id="cde87-137">You control the BAPIs in a transaction by ensuring that they are all sent over the same SAP connection (including the call to commit or roll back the transaction).</span></span> <span data-ttu-id="cde87-138">Puede hacerlo en:</span><span class="sxs-lookup"><span data-stu-id="cde87-138">You can do this in:</span></span>  
  
- <span data-ttu-id="cde87-139">Soluciones de BizTalk mediante el uso de la **ConnectionState** propiedad de contexto para garantizar que las BAPI en una transacción se envían con la misma conexión de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cde87-139">BizTalk Solutions by using the **ConnectionState** message context property to ensure that the BAPIs in a transaction are sent using the same connection.</span></span> <span data-ttu-id="cde87-140">Esta propiedad es obtenida por el adaptador y le proporciona un control explícito sobre la conexión usada para enviar un mensaje en una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cde87-140">This property is surfaced by the adapter and provides you with explicit control over the connection used to send a message in a BizTalk orchestration.</span></span>  
  
   <span data-ttu-id="cde87-141">Para realizar transacciones de BAPI mediante BizTalk Server, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite las siguientes propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="cde87-141">For performing BAPI transactions using BizTalk Server, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following message context properties.</span></span>  
  
  |<span data-ttu-id="cde87-142">Campo</span><span class="sxs-lookup"><span data-stu-id="cde87-142">Field</span></span>|<span data-ttu-id="cde87-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="cde87-143">Description</span></span>|  
  |-----------|-----------------|  
  |<span data-ttu-id="cde87-144">OPEN</span><span class="sxs-lookup"><span data-stu-id="cde87-144">OPEN</span></span>|<span data-ttu-id="cde87-145">Se abre un nuevo canal para la transacción.</span><span class="sxs-lookup"><span data-stu-id="cde87-145">Opens a new channel for the transaction.</span></span>|  
  |<span data-ttu-id="cde87-146">VOLVER A USAR</span><span class="sxs-lookup"><span data-stu-id="cde87-146">REUSE</span></span>|<span data-ttu-id="cde87-147">Reutilizar un canal existente para la transacción.</span><span class="sxs-lookup"><span data-stu-id="cde87-147">Reuse existing channel for the transaction.</span></span>|  
  |<span data-ttu-id="cde87-148">CLOSE</span><span class="sxs-lookup"><span data-stu-id="cde87-148">CLOSE</span></span>|<span data-ttu-id="cde87-149">Confirmar la transacción y cierra el canal existente.</span><span class="sxs-lookup"><span data-stu-id="cde87-149">Commit the transaction and close the existing channel.</span></span>|  
  |<span data-ttu-id="cde87-150">ABORT</span><span class="sxs-lookup"><span data-stu-id="cde87-150">ABORT</span></span>|<span data-ttu-id="cde87-151">Anular la transacción y cierra el canal existente.</span><span class="sxs-lookup"><span data-stu-id="cde87-151">Abort the transaction and close the existing channel.</span></span>|  
  
   <span data-ttu-id="cde87-152">Para obtener más información, consulte [ejecutar transacciones de BAPI de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="cde87-152">For more information, see [Run BAPI Transactions in SAP using BizTalk Server](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="cde87-153">Asegúrese de establecer el **EnableBizTalkCompatibilityMode**enlaza la propiedad cuando se realizan transacciones con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="cde87-153">Make sure you set the **EnableBizTalkCompatibilityMode**binding property when performing transactions using BizTalk Server.</span></span>  
  
- <span data-ttu-id="cde87-154">Soluciones de modelos de servicio WCF asegurándose de que las BAPI en una transacción se envían con el mismo cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="cde87-154">WCF service model solutions by ensuring that the BAPIs in a transaction are sent using the same WCF client.</span></span> <span data-ttu-id="cde87-155">Para obtener más información, consulte [invocar BAPI de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="cde87-155">For more information, see [Invoke BAPIs in SAP using WCF Service Model](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md).</span></span>  
  
- <span data-ttu-id="cde87-156">WCF canal soluciones de modelos al garantizar que las BAPI en una transacción se envían a través del mismo canal WCF.</span><span class="sxs-lookup"><span data-stu-id="cde87-156">WCF channel model solutions by ensuring that the BAPIs in a transaction are sent over the same WCF channel.</span></span> <span data-ttu-id="cde87-157">Para obtener más información, consulte [desarrollar aplicaciones mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="cde87-157">For more information, see [Develop applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).</span></span>  
  
### <a name="limitations-on-bapi-transactions"></a><span data-ttu-id="cde87-158">Limitaciones de las transacciones de BAPI</span><span class="sxs-lookup"><span data-stu-id="cde87-158">Limitations on BAPI Transactions</span></span>  
 <span data-ttu-id="cde87-159">Las siguientes restricciones se aplican en transacciones de BAPI:</span><span class="sxs-lookup"><span data-stu-id="cde87-159">The following restrictions apply on BAPI transactions:</span></span>  
  
- <span data-ttu-id="cde87-160">No es posible crear dos accesos de escritura en la misma instancia dentro de un LUW.</span><span class="sxs-lookup"><span data-stu-id="cde87-160">It is not possible to make two write accesses on the same instance within one LUW.</span></span> <span data-ttu-id="cde87-161">Por ejemplo, no se puede crear un pedido y actualiza en la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="cde87-161">For example, you cannot create an order and update it in the same transaction.</span></span>  
  
- <span data-ttu-id="cde87-162">Al realizar una transacción utilizando el BAPI [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], todos los mensajes deben enviarse a través de una instancia de host del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="cde87-162">When performing BAPI a transaction using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], all the messages must be sent over a single host instance of the send port.</span></span>  
  
- <span data-ttu-id="cde87-163">Si una instancia se crea, actualiza o elimina mediante el uso de una escritura BAPI, una lectura BAPI no podrá ver los datos más reciente hasta que se confirma la escritura BAPI.</span><span class="sxs-lookup"><span data-stu-id="cde87-163">If an instance is created, updated, or deleted by using a write BAPI, a read BAPI cannot view the most recent data until the write BAPI is committed.</span></span>  
  
- <span data-ttu-id="cde87-164">Un cliente externo que invoca un LUW debe llamar a todas las BAPI que contiene el LUW en la misma conexión de SAP.</span><span class="sxs-lookup"><span data-stu-id="cde87-164">An external client that invokes an LUW should call all the BAPIs that the LUW contains on the same SAP connection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cde87-165">BAPI que pertenecen a la versión 3.1 llamar a COMMIT WORK como parte de su implementación.</span><span class="sxs-lookup"><span data-stu-id="cde87-165">BAPIs that belong to Release 3.1 call COMMIT WORK as part of their implementation.</span></span> <span data-ttu-id="cde87-166">Esto significa que estos BAPI no puede incluirse con otra BAPI en un LUW (porque confirmará la transacción).</span><span class="sxs-lookup"><span data-stu-id="cde87-166">This means that these BAPIs cannot be included with other BAPIs in an LUW (because they will commit the transaction).</span></span> <span data-ttu-id="cde87-167">Para obtener más información, consulte la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="cde87-167">For more information, see the SAP documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cde87-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="cde87-168">See Also</span></span>  
 <span data-ttu-id="cde87-169">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="cde87-169">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>