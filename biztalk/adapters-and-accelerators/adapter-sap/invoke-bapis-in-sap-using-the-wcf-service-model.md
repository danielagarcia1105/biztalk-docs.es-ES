---
title: Invocar BAPI de SAP mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPIs, invoking by using the WCF service model
- WCF service model, invoking BAPIs
ms.assetid: be3c48d6-2213-4ae5-97f4-634fbc423022
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6f5cab88b0f672f9f09bdeb7795c0a58213f92f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002445"
---
# <a name="invoke-bapis-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="ba458-102">Invocar BAPI de SAP mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="ba458-102">Invoke BAPIs in SAP using the WCF Service Model</span></span>
<span data-ttu-id="ba458-103">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies BAPI como:</span><span class="sxs-lookup"><span data-stu-id="ba458-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces BAPIs as:</span></span>  
  
- <span data-ttu-id="ba458-104">**Las operaciones de RFC**.</span><span class="sxs-lookup"><span data-stu-id="ba458-104">**RFC operations**.</span></span> <span data-ttu-id="ba458-105">BAPI como cualquier otro RFC aparecen bajo el nodo RFC en la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba458-105">BAPIs like any other RFC are surfaced under the RFC node in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
- <span data-ttu-id="ba458-106">**Métodos de objetos SAP business**.</span><span class="sxs-lookup"><span data-stu-id="ba458-106">**Methods of SAP business objects**.</span></span> <span data-ttu-id="ba458-107">Como los métodos de objetos de negocios, BAPI aparecen por objeto de negocios en el nodo BAPI el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba458-107">As methods of business objects, BAPIs are surfaced by business object under the BAPI node in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
  <span data-ttu-id="ba458-108">Si se invoca una BAPI como una operación de RFC o como un método del objeto comercial, cada BAPI siempre forma parte de un LUW en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ba458-108">Whether you invoke a BAPI as an RFC operation or as a business object method, each BAPI is always part of an LUW on the SAP system.</span></span>  
  
  <span data-ttu-id="ba458-109">Para obtener información general de cómo el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite BAPI, vea [operaciones en BAPI de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="ba458-109">For an overview of how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports BAPIs, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  
  
  <span data-ttu-id="ba458-110">Cuando usa el modelo de servicio WCF para invocar BAPI como métodos de objetos comerciales, cada objeto de negocio SAP se representa mediante una clase de cliente WCF y las BAPI de ese objeto de negocios se representan como métodos en el cliente.</span><span class="sxs-lookup"><span data-stu-id="ba458-110">When you use the WCF service model to invoke BAPIs as business object methods, each SAP business object is represented by a WCF client class and the BAPIs of that business object are represented as methods on the client.</span></span> <span data-ttu-id="ba458-111">Puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF para objetos de negocio específico que contiene métodos para cada BAPI que desea invocar en el código.</span><span class="sxs-lookup"><span data-stu-id="ba458-111">You can use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class for specific business objects that contains methods for each BAPI that you want to invoke in your code.</span></span> <span data-ttu-id="ba458-112">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera tipos de .NET para encapsular los tipos de datos y los parámetros utilizados por cada BAPI.</span><span class="sxs-lookup"><span data-stu-id="ba458-112">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates .NET types to encapsulate the parameters and data types that are used by each BAPI.</span></span> <span data-ttu-id="ba458-113">A continuación, puede crear una instancia de esta clase de cliente WCF y llamar a sus métodos para invocar el destino BAPI.</span><span class="sxs-lookup"><span data-stu-id="ba458-113">You can then create an instance of this WCF client class and call its methods to invoke the target BAPIs.</span></span>  
  
  <span data-ttu-id="ba458-114">Las secciones siguientes muestran cómo invocar BAPI como métodos de objetos de negocios y explicar cómo se admiten las transacciones de BAPI en el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ba458-114">The following sections show you how to invoke BAPIs as methods of business objects and discuss how BAPI transactions are supported in the WCF service model.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="ba458-115">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="ba458-115">The WCF Client Class</span></span>  
 <span data-ttu-id="ba458-116">La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone un contrato de servicio diferente para cada objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="ba458-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces a different service contract, for each business object.</span></span> <span data-ttu-id="ba458-117">Esto significa que para cada objeto de negocios WCF único se crea la clase de cliente.</span><span class="sxs-lookup"><span data-stu-id="ba458-117">This means that for each business object a unique WCF client class is created.</span></span> <span data-ttu-id="ba458-118">El nombre de esta clase se basa en el tipo de objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="ba458-118">The name of this class is based on the business object type.</span></span> <span data-ttu-id="ba458-119">Por ejemplo para el objeto de negocios de pedido de ventas (tipo de objeto de negocios BUS2032), la clase de cliente WCF es **BapiBUS2032Client**.</span><span class="sxs-lookup"><span data-stu-id="ba458-119">For example for the Sales Order business object (business object type BUS2032), the WCF client class is **BapiBUS2032Client**.</span></span> <span data-ttu-id="ba458-120">Cada destino BAPI en el objeto de negocios se representa como un método en la clase de cliente WCF generado.</span><span class="sxs-lookup"><span data-stu-id="ba458-120">Each target BAPI in the business object is represented as a method in the generated WCF client class.</span></span> <span data-ttu-id="ba458-121">En cada método:</span><span class="sxs-lookup"><span data-stu-id="ba458-121">In each method:</span></span>  
  
- <span data-ttu-id="ba458-122">Exportación de los parámetros SAP se exponen como **out** parámetros</span><span class="sxs-lookup"><span data-stu-id="ba458-122">SAP export parameters are surfaced as **out** parameters</span></span>  
  
- <span data-ttu-id="ba458-123">Parámetros de llamada de SAP se exponen como **ref** parámetros.</span><span class="sxs-lookup"><span data-stu-id="ba458-123">SAP calling parameters are surfaced as **ref** parameters.</span></span>  
  
- <span data-ttu-id="ba458-124">Tipos complejos de SAP como estructuras se exponen como clases .NET con propiedades que corresponden a los campos del tipo SAP.</span><span class="sxs-lookup"><span data-stu-id="ba458-124">Complex SAP types such as structures are surfaced as .NET classes with properties that correspond to the fields of the SAP type.</span></span> <span data-ttu-id="ba458-125">Estas clases se definen en el espacio de nombres siguiente: microsoft.lobservices.sap._2007._03.Types.Rfc.</span><span class="sxs-lookup"><span data-stu-id="ba458-125">These classes are defined in the following namespace: microsoft.lobservices.sap._2007._03.Types.Rfc.</span></span>  
  
  <span data-ttu-id="ba458-126">BAPI_TRANSACTION_COMMIT BAPI_TRANSACTION_ROLLBACK aparecen para cada objeto de negocios y siempre debe incluir en el cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ba458-126">BAPI_TRANSACTION_COMMIT and BAPI_TRANSACTION_ROLLBACK are surfaced for each business object and you should always include these in your WCF client.</span></span>  
  
  <span data-ttu-id="ba458-127">El código siguiente muestra parte de una clase de cliente WCF generada para el objeto de negocios de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="ba458-127">The following code shows part of a WCF client class generated for the Sales Order business object.</span></span> <span data-ttu-id="ba458-128">Este cliente contiene métodos para invocar CREATEFROMDAT2, BAPI_TRANSACTION_COMMIT y BAPI_TRANSACTION_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="ba458-128">This client contains methods to invoke CREATEFROMDAT2, BAPI_TRANSACTION_COMMIT and BAPI_TRANSACTION_ROLLBACK.</span></span> <span data-ttu-id="ba458-129">Para mayor claridad los constructores y otro código se ha omitido.</span><span class="sxs-lookup"><span data-stu-id="ba458-129">For clarity the constructors and other code has been omitted.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class BapiBUS2032Client : System.ServiceModel.ClientBase<BapiBUS2032>, BapiBUS2032 {  
  
    // Code has been removed for clarity  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="SALESDOCUMENT">Number of Generated Document</param>  
    /// <param name="BEHAVE_WHEN_ERROR">Error Handling</param>  
    /// …  
    /// <param name="ORDER_TEXT">Texts</param>  
    /// <param name="PARTNERADDRESSES">BAPI Reference Structure for Addresses (Org./Company)</param>  
    /// <param name="RETURN">Return Messages</param>  
    /// <returns></returns>  
    public string CREATEFROMDAT2(  
                string BEHAVE_WHEN_ERROR,   
                string BINARY_RELATIONSHIPTYPE,   
                string CONVERT,   
                string INT_NUMBER_ASSIGNMENT,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDLS LOGIC_SWITCH,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1 ORDER_HEADER_IN,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1X ORDER_HEADER_INX,   
                string SALESDOCUMENTIN,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPI_SENDER SENDER,   
                string TESTRUN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPAREX[] EXTENSIONIN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICCARD[] ORDER_CCARD,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUBLB[] ORDER_CFGS_BLOB,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUINS[] ORDER_CFGS_INST,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUPRT[] ORDER_CFGS_PART_OF,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUCFG[] ORDER_CFGS_REF,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUREF[] ORDER_CFGS_REFINST,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUVAL[] ORDER_CFGS_VALUE,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUVK[] ORDER_CFGS_VK,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICOND[] ORDER_CONDITIONS_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICONDX[] ORDER_CONDITIONS_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDITM[] ORDER_ITEMS_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDITMX[] ORDER_ITEMS_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDKEY[] ORDER_KEYS,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPARNR[] ORDER_PARTNERS,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISCHDL[] ORDER_SCHEDULES_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISCHDLX[] ORDER_SCHEDULES_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDTEXT[] ORDER_TEXT,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIADDR1[] PARTNERADDRESSES,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2[] RETURN) { ...}  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="RETURN">Confirmations</param>  
    /// <param name="WAIT">Using the command `COMMIT AND WAIT`</param>  
    /// <returns></returns>  
    public microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2 BAPI_TRANSACTION_COMMIT(string WAIT) { ... }  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="RETURN">Confirmations</param>  
    /// <returns></returns>  
    public microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2 BAPI_TRANSACTION_ROLLBACK() { ... }  
}  
```  
  
## <a name="bapi-transactions-in-the-wcf-service-model"></a><span data-ttu-id="ba458-130">Transacciones de BAPI en el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="ba458-130">BAPI Transactions in the WCF Service Model</span></span>  
 <span data-ttu-id="ba458-131">Cada BAPI, si se invoca como una solicitud de cambio o como un método de objeto comercial, forma parte de una transacción (LUW) sobre el sistema SAP. y cada BAPI recibido a través de la misma conexión de SAP es parte de la misma transacción BAPI en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ba458-131">Every BAPI, whether it is invoked as an RFC or as a business object method, is part of a transaction (LUW) on the SAP system; and every BAPI received over the same SAP connection is part of the same BAPI transaction on the SAP system.</span></span> <span data-ttu-id="ba458-132">SAP se confirma o revierte la transacción BAPI cuando recibe un BAPI_TRANSACTION_COMMIT o un BAPI_TRANSACTION_ROLLBACK en la conexión.</span><span class="sxs-lookup"><span data-stu-id="ba458-132">SAP commits or rolls back the BAPI transaction when it receives a BAPI_TRANSACTION_COMMIT or a BAPI_TRANSACTION_ROLLBACK on the connection.</span></span> <span data-ttu-id="ba458-133">Después de haber realizado commit o rollback, el siguiente BAPI recibida a través de la conexión inicia una transacción nueva.</span><span class="sxs-lookup"><span data-stu-id="ba458-133">After a commit or rollback has been performed, the next BAPI received over the connection begins a new transaction.</span></span>  
  
 <span data-ttu-id="ba458-134">Para el adaptador de cada canal WCF tiene una conexión dedicada de SAP.</span><span class="sxs-lookup"><span data-stu-id="ba458-134">For the adapter each WCF channel has a dedicated SAP connection.</span></span> <span data-ttu-id="ba458-135">En el modelo de servicio WCF, cada cliente WCF tiene un canal interno que es usado enviar mensajes al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ba458-135">In the WCF service model, each WCF client has an inner channel that is used send messages to the SAP system.</span></span> <span data-ttu-id="ba458-136">Esto significa que las BAPI que se invocan mediante un cliente WCF específico forman parte de una única transacción BAPI en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ba458-136">This means that the BAPIs that are invoked using a specific WCF client are part of a unique BAPI transaction on the SAP system.</span></span> <span data-ttu-id="ba458-137">Esto impone una limitación importante cuando se usa el modelo de servicio WCF para invocar BAPI como métodos de objetos comerciales.</span><span class="sxs-lookup"><span data-stu-id="ba458-137">This imposes a significant limitation when you use the WCF service model to invoke BAPIs as business object methods.</span></span> <span data-ttu-id="ba458-138">Dado que cada objeto de negocio SAP se representa mediante una clase de cliente WCF dedicada, no se puede invocar BAPI de dos objetos empresariales diferentes como parte de la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="ba458-138">Because each SAP business object is represented by a dedicated WCF client class, you cannot invoke BAPIs from two different business objects as part of the same transaction.</span></span> <span data-ttu-id="ba458-139">La manera de solucionar este problema es invocar el BAPI como operaciones de RFC.</span><span class="sxs-lookup"><span data-stu-id="ba458-139">The way around this is to invoke the BAPIs as RFC operations.</span></span> <span data-ttu-id="ba458-140">Esto es porque el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera un único cliente WCF para las operaciones de RFC, y, por lo tanto, todas las operaciones invocadas mediante ese cliente se envían a través del mismo canal WCF.</span><span class="sxs-lookup"><span data-stu-id="ba458-140">This is because the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates a single WCF client for RFC operations, and, therefore, all operations invoked using that client are sent over the same WCF channel.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ba458-141">Si desea incluir BAPI de diferentes objetos de negocio SAP en la misma transacción BAPI, se debe invocar como operaciones de RFC (con el mismo cliente WCF).</span><span class="sxs-lookup"><span data-stu-id="ba458-141">If you want to include BAPIs from different SAP business objects in the same BAPI transaction, you must invoke them as RFC operations (using the same WCF client).</span></span> <span data-ttu-id="ba458-142">No se puede invocar a ellos como métodos de objetos comerciales.</span><span class="sxs-lookup"><span data-stu-id="ba458-142">You cannot invoke them as business object methods.</span></span>  
  
 <span data-ttu-id="ba458-143">Se llama a BAPI_TRANSACTION_COMMIT o BAPI_TRANSACTION_ROLLBACK para confirmar o revertir la transacción BAPI en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ba458-143">You call BAPI_TRANSACTION_COMMIT or BAPI_TRANSACTION_ROLLBACK to commit or roll back the BAPI transaction on the SAP system.</span></span> <span data-ttu-id="ba458-144">El adaptador presenta estos dos BAPI:</span><span class="sxs-lookup"><span data-stu-id="ba458-144">The adapter surfaces these two BAPIs:</span></span>  
  
- <span data-ttu-id="ba458-145">En el nodo base como las operaciones de RFC.</span><span class="sxs-lookup"><span data-stu-id="ba458-145">Under the Basis node as RFC operations.</span></span>  
  
- <span data-ttu-id="ba458-146">En cada objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="ba458-146">Under each business object.</span></span>  
  
  <span data-ttu-id="ba458-147">Para obtener más información acerca de cómo el adaptador admite transacciones de BAPI de SAP, consulte [operaciones en BAPI de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="ba458-147">For more information about how the adapter supports BAPI transactions on SAP, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  
  
## <a name="how-to-create-an-application-that-invokes-bapis-as-methods-of-business-objects"></a><span data-ttu-id="ba458-148">Cómo crear una aplicación que invoca BAPI como métodos de objetos de negocios</span><span class="sxs-lookup"><span data-stu-id="ba458-148">How to Create an Application that Invokes BAPIs as Methods of Business Objects</span></span>  
 <span data-ttu-id="ba458-149">En esta sección se proporciona información sobre cómo invocar BAPI como métodos de objetos de negocios.</span><span class="sxs-lookup"><span data-stu-id="ba458-149">This section provides information about how to invoke BAPIs as methods of business objects.</span></span> <span data-ttu-id="ba458-150">Debe seguir el mismo procedimiento básico para invocar BAPI como operaciones de RFC, excepto en que crear a un cliente WCF que tiene como destino las BAPI como operaciones de RFC y usarlo para invocar cada BAPI.</span><span class="sxs-lookup"><span data-stu-id="ba458-150">The same basic procedure should be followed to invoke BAPIs as RFC operations, except that you create a WCF client that targets the BAPIs as RFC operations and use it to invoke each BAPI.</span></span>  
  
 <span data-ttu-id="ba458-151">Para crear una aplicación de cliente BAPI, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="ba458-151">To create a BAPI client application, perform the following steps.</span></span>  
  
#### <a name="to-create-an-bapi-client-application"></a><span data-ttu-id="ba458-152">Para crear una aplicación de cliente BAPI</span><span class="sxs-lookup"><span data-stu-id="ba458-152">To create an BAPI client application</span></span>  
  
1. <span data-ttu-id="ba458-153">Generar una clase de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ba458-153">Generate a WCF client class.</span></span> <span data-ttu-id="ba458-154">Use el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o ServiceModel Metadata Utility Tool (svcutil.exe) para generar una clase de cliente WCF (o clases) que tenga como destino los objetos de negocio y BAPI con la que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="ba458-154">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class (or classes) that targets the business objects and BAPIs with which you want to work.</span></span> <span data-ttu-id="ba458-155">No olvide incluir el BAPI_TRANSACTION_COMMIT y los métodos BAPI_TRANSACTION_ROLLBACK (BAPI) expuestos para cada objeto de negocios de destino.</span><span class="sxs-lookup"><span data-stu-id="ba458-155">Be sure to include the BAPI_TRANSACTION_COMMIT and the BAPI_TRANSACTION_ROLLBACK methods (BAPIs) exposed for each target business object.</span></span> <span data-ttu-id="ba458-156">Para obtener más información sobre cómo generar un cliente de WCF, vea [generando un contrato de servicio de WCF o un cliente de WCF para artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="ba458-156">For more information about how to generate a WCF client, see [Generating a WCF Client or a WCF Service Contract for SAP Solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2. <span data-ttu-id="ba458-157">Cree una instancia de la clase de cliente WCF generada en el paso 1 y crear y configurar a un cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="ba458-157">Create an instance of the WCF client class generated in step 1, and create and configure a WCF client.</span></span> <span data-ttu-id="ba458-158">Configurar al cliente de WCF implica especificar el enlace y dirección de punto de conexión que usará el cliente.</span><span class="sxs-lookup"><span data-stu-id="ba458-158">Configuring the WCF client involves specifying the binding and endpoint address that the client will use.</span></span> <span data-ttu-id="ba458-159">Puede hacerlo imperativamente en código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="ba458-159">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="ba458-160">Para obtener más información sobre cómo especificar un enlace de cliente, consulte [configurar un enlace de cliente para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="ba458-160">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="ba458-161">El siguiente código inicializa al cliente WCF para el objeto de negocios de pedido de ventas (BUS2032) SAP de configuración y establece las credenciales para el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ba458-161">The following code initializes the WCF client for the Sales Order (BUS2032) SAP business object from configuration and sets the credentials for the SAP system.</span></span>  
  
   ```  
   BapiBUS2032Client bapiClient = new BapiBUS2032Client("SAPBinding_BapiBUS2032");  
  
   bapiClient.ClientCredentials.UserName.UserName = "YourUserName";  
   bapiClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. <span data-ttu-id="ba458-162">Abra al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="ba458-162">Open the WCF client.</span></span>  
  
   ```  
   bapiClient.Open();  
   ```  
  
4. <span data-ttu-id="ba458-163">Invocar métodos en el cliente de WCF que creó en el paso 2 para invocar las BAPI adecuadas en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ba458-163">Invoke methods on the WCF client created in step 2 to invoke the appropriate BAPIs on the SAP system.</span></span> <span data-ttu-id="ba458-164">Puede invocar BAPI varios en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ba458-164">You can invoke multiple BAPIs on the SAP system.</span></span>  
  
5. <span data-ttu-id="ba458-165">Finalizar la transacción por:</span><span class="sxs-lookup"><span data-stu-id="ba458-165">End the transaction by:</span></span>  
  
   1.  <span data-ttu-id="ba458-166">Invocar el método BAPI_TRANSACTION_COMMIT para confirmar la transacción.</span><span class="sxs-lookup"><span data-stu-id="ba458-166">Invoking the BAPI_TRANSACTION_COMMIT method to commit the transaction.</span></span>  
  
       ```  
       bapiClient.BAPI_TRANSACTION_COMMIT("X");  
       ```  
  
   2.  <span data-ttu-id="ba458-167">Invocar el método BAPI_TRANSACTION_ROLLBACK para revertir la transacción.</span><span class="sxs-lookup"><span data-stu-id="ba458-167">Invoking the BAPI_TRANSACTION_ROLLBACK method to roll back the transaction.</span></span>  
  
       ```  
       bapiClient.BAPI_TRANSACTION_ROLLBACK();  
       ```  
  
6. <span data-ttu-id="ba458-168">Cierre al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ba458-168">Close the WCF client.</span></span>  
  
   ```  
   bapiClient.Close();   
   ```  
  
### <a name="example"></a><span data-ttu-id="ba458-169">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba458-169">Example</span></span>  
 <span data-ttu-id="ba458-170">El ejemplo siguiente invoca el BAPI CREATEFROMDAT2 en el objeto de negocios de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="ba458-170">The following example invokes the CREATEFROMDAT2 BAPI on the Sales Order business object.</span></span> <span data-ttu-id="ba458-171">Invoca el BAPI varias veces y, a continuación, invoca BAPI_TRANSACTION_COMMIT para confirmar la transacción.</span><span class="sxs-lookup"><span data-stu-id="ba458-171">It invokes the BAPI several times and then invokes BAPI_TRANSACTION_COMMIT to commit the transaction.</span></span> <span data-ttu-id="ba458-172">Si se produce un error al invocar el BAPI, BAPI_TRANSACTION_ROLLBACK se invoca en el controlador de excepción para revertir la transacción.</span><span class="sxs-lookup"><span data-stu-id="ba458-172">If an error occurs when invoking the BAPI, BAPI_TRANSACTION_ROLLBACK is invoked in the exception handler to roll back the transaction.</span></span>  
  
 <span data-ttu-id="ba458-173">El método CREATEFROMDAT2 toma varios parámetros; se omiten en el ejemplo por brevedad.</span><span class="sxs-lookup"><span data-stu-id="ba458-173">The CREATEFROMDAT2 method takes many parameters; these are omitted in the example for the sake of brevity.</span></span> <span data-ttu-id="ba458-174">Puede encontrar un ejemplo que muestra las transacciones de BAPI en los ejemplos se incluye con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba458-174">You can find a sample that demonstrates BAPI transactions in the samples shipped with the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="ba458-175">Para obtener más información, consulte [ejemplos para el adaptador SAP ](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="ba458-175">For more information, see [Samples for the SAP Adapter ](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, Adapter LOB SDK, and SAP Adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for Adapter LOB SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using microsoft.lobservices.sap._2007._03.Types.Rfc;  
  
// This Example demonstrates BAPI transactions. Two sales orders are  
// created using the CREATEFROMDAT2 method of a SAP Business Object.   
// After the orders are created, the BAPI transaction is committed.   
// If an exception occurs when sending the BAPIs, the BAPI transaction is   
// rolled back.  
//   
  
namespace SapBapiTxClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create the BAPI client from the generated endpoint configuration.  
  
            BapiBUS2032Client bapiClient = null;  
  
            Console.WriteLine("BAPI transaction sample started");  
            Console.WriteLine("\nCreating business object client");  
  
            try  
            {  
                bapiClient = new BapiBUS2032Client("SAPBinding_BapiBUS2032");  
  
                bapiClient.ClientCredentials.UserName.UserName = "YourUserName";  
                bapiClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                // Open the BAPI Client  
                bapiClient.Open();  
  
                ...  
  
                // send first BAPI  
                try  
                {  
                    string salesDocNumber1 = bapiClient.CREATEFROMDAT2(  
                        ...  
                        // parameters ommitted  
                        ...                          
                        );  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
                // send second BAPI  
                try  
                {  
                    string salesDocNumber1 = bapiClient.CREATEFROMDAT2(  
                        ...  
                        // parameters omitted  
                        ...                          
                        );  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
                // Commit BAPI Transaction  
                try  
                {  
                    bapiClient.BAPI_TRANSACTION.Commit();  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
            }  
            catch (ConnectionException cex)  
            {  
                // Get here if problem connecting to the SAP system   
  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                // Get here if the SAP system returns an exception  
  
                Console.WriteLine("Exception occurred on the SAP System");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
            // Close the client when finished  
                if (bapiClient != null)  
                {  
                    if (bapiClient.State == CommunicationState.Opened)  
                        bapiClient.Close();  
                    else  
                        bapiClient.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba458-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba458-176">See Also</span></span>  
[<span data-ttu-id="ba458-177">Desarrollar aplicaciones con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="ba458-177">Develop applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)  
 [<span data-ttu-id="ba458-178">Operaciones en BAPI de SAP</span><span class="sxs-lookup"><span data-stu-id="ba458-178">Operations on BAPIs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)