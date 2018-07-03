---
title: Recibir llamadas de tRFC de entrada de SAP mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFC calls, receiving inbound using the WCF service model
- WCF service model, receiving inbound tRFC calls
ms.assetid: 02dc282b-b659-466a-8bd1-f400a05f71ec
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd54bdfd3a772912b4d2687ab1ce9e715e7fbab9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013333"
---
# <a name="receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="1041a-102">Recibir llamadas de tRFC de entrada de SAP mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="1041a-102">Receive Inbound tRFC Calls in SAP using the WCF Service Model</span></span>
<span data-ttu-id="1041a-103">Puede usar el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como un servidor RFC (tRFC) transaccional para recibir llamadas de tRFC de entrada de SAP.</span><span class="sxs-lookup"><span data-stu-id="1041a-103">You can use the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as a transactional RFC (tRFC) server to receive inbound tRFC calls from SAP.</span></span> <span data-ttu-id="1041a-104">Para trfc de entrada, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite varios trfc en la misma unidad lógica de SAP de trabajo (LUW).</span><span class="sxs-lookup"><span data-stu-id="1041a-104">For inbound tRFCs, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports multiple tRFCs in the same SAP logical unit of work (LUW).</span></span>  
  
 <span data-ttu-id="1041a-105">Las secciones de este tema proporcionan información sobre cómo usar el adaptador como un servidor tRFC en el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="1041a-105">The sections in this topic provide information about how to use the adapter as a tRFC server in the WCF service model.</span></span>  
  
 <span data-ttu-id="1041a-106">Puede encontrar más información acerca de cómo utilizar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como un servidor tRFC en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1041a-106">You can find more information about using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as a tRFC server in the following topics:</span></span>  
  
- <span data-ttu-id="1041a-107">Para obtener información general de la compatibilidad con trfc en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="1041a-107">For an overview of support for tRFCs on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span> <span data-ttu-id="1041a-108">Debe leer este tema antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="1041a-108">You should read this topic before continuing.</span></span>  
  
- <span data-ttu-id="1041a-109">Para obtener más información acerca de los esquemas de mensaje para operaciones de tRFC del servidor, consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="1041a-109">For more information about the message schemas for tRFC server operations, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
## <a name="the-wcf-service-contract-for-a-trfc"></a><span data-ttu-id="1041a-110">El contrato de servicio WCF para un tRFC</span><span class="sxs-lookup"><span data-stu-id="1041a-110">The WCF Service Contract for a tRFC</span></span>  
 <span data-ttu-id="1041a-111">Usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutil.exe) para generar un contrato de servicio WCF para las trfc que desea recibir desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="1041a-111">You use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF service contract for the tRFCs that you want to receive from the SAP system.</span></span> <span data-ttu-id="1041a-112">El contrato generado para un tRFC de entrada es similar a la que se genera para una solicitud de cambio entrante, salvo que:</span><span class="sxs-lookup"><span data-stu-id="1041a-112">The contract generated for an inbound tRFC is similar to that generated for an inbound RFC except that:</span></span>  
  
- <span data-ttu-id="1041a-113">las operaciones de tRFC aparecen bajo el nodo TRFC.</span><span class="sxs-lookup"><span data-stu-id="1041a-113">tRFC operations are surfaced under the TRFC node.</span></span>  
  
- <span data-ttu-id="1041a-114">El contrato de servicio WCF (interfaz) generado para trfc entrante se denomina "Trfc".</span><span class="sxs-lookup"><span data-stu-id="1041a-114">The WCF service contract (interface) generated for incoming tRFCs is named "Trfc".</span></span> <span data-ttu-id="1041a-115">Debe especificar esta interfaz cuando se agrega el extremo de servicio al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="1041a-115">You must specify this interface when you add the service endpoint to the service host.</span></span> <span data-ttu-id="1041a-116">También es la interfaz que debe implementar su servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="1041a-116">This is also the interface that your WCF service must implement.</span></span>  
  
  ```  
  public interface Trfc {  
  
      // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Trfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
      [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD/response")]  
      Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
  }  
  ```  
  
- <span data-ttu-id="1041a-117">El contrato de mensaje de solicitud para las operaciones de TRFC tiene un parámetro GUID.</span><span class="sxs-lookup"><span data-stu-id="1041a-117">The request message contract for TRFC operations has a GUID parameter.</span></span> <span data-ttu-id="1041a-118">Este es el GUID que se asigna a la TID SAP el tRFC.</span><span class="sxs-lookup"><span data-stu-id="1041a-118">This is the GUID that maps to the SAP TID for the tRFC.</span></span> <span data-ttu-id="1041a-119">En las operaciones del servidor tRFC, el adaptador administra todas las llamadas a confirmar, deshacer y confirmar el TID por el sistema SAP, por lo que no hay ninguna razón para usar explícitamente este GUID.</span><span class="sxs-lookup"><span data-stu-id="1041a-119">In tRFC server operations, the adapter manages all calls to commit, rollback, and confirm the TID by the SAP system so there is no reason for you to explicitly use this GUID.</span></span> <span data-ttu-id="1041a-120">Sin embargo, puede usar para recuperar el TID de SAP desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante una llamada a **SapAdapterUtilities.ConvertGuidToTid**.</span><span class="sxs-lookup"><span data-stu-id="1041a-120">However, you can use it to retrieve the SAP TID from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by calling **SapAdapterUtilities.ConvertGuidToTid**.</span></span> <span data-ttu-id="1041a-121">Esto puede ser útil para ayudar a solucionar problemas en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="1041a-121">This can be useful to help you troubleshoot issues on the SAP system.</span></span>  
  
  ```  
  [System.Diagnostics.DebuggerStepThroughAttribute()]  
  [System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
  [System.ServiceModel.MessageContractAttribute(WrapperName="Z_RFC_MKD_ADD", WrapperNamespace="http://Microsoft.LobServices.Sap/2007/03/Trfc/", IsWrapped=true)]  
  public partial class Z_RFC_MKD_ADDRequest {  
  
      ...  
  
      public Z_RFC_MKD_ADDRequest(string DEST, System.Nullable<int> X, System.Nullable<int> Y, System.Guid TransactionalRfcOperationIdentifier) {  
          this.DEST = DEST;  
          this.X = X;  
          this.Y = Y;  
          this.TransactionalRfcOperationIdentifier = TransactionalRfcOperationIdentifier;  
      }  
  }  
  
  ```  
  
## <a name="how-do-i-enable-the-adapter-to-act-as-a-trfc-server"></a><span data-ttu-id="1041a-122">¿Cómo se habilita el adaptador de actuar como un servidor tRFC?</span><span class="sxs-lookup"><span data-stu-id="1041a-122">How do I Enable the Adapter to Act as a tRFC Server?</span></span>  
 <span data-ttu-id="1041a-123">Para habilitar el adaptador para que actúe como un servidor tRFC, debe establecer el **TidDatabaseConnectionString** enlazar propiedad con la cadena de conexión para la base de datos TID.</span><span class="sxs-lookup"><span data-stu-id="1041a-123">To enable the adapter to act as a tRFC server, you must set the **TidDatabaseConnectionString** binding property to the connection string for the TID database.</span></span> <span data-ttu-id="1041a-124">Debe hacerlo antes de abrir el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="1041a-124">You should do this before you open the service host.</span></span> <span data-ttu-id="1041a-125">Se trata de la base de datos en el que el adaptador almacena las transacciones de SAP TID (Id.) para cada tRFC.</span><span class="sxs-lookup"><span data-stu-id="1041a-125">This is the database in which the adapter stores the SAP transaction ID (TID) for each tRFC.</span></span> <span data-ttu-id="1041a-126">Para obtener más información acerca de esta propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1041a-126">For more information about this binding property, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
## <a name="how-do-i-enlist-in-the-transaction-for-inbound-trfcs"></a><span data-ttu-id="1041a-127">¿Cómo inscribirse en la transacción para trfc de entrada?</span><span class="sxs-lookup"><span data-stu-id="1041a-127">How do I Enlist in the Transaction for Inbound tRFCs?</span></span>  
 <span data-ttu-id="1041a-128">Un SAP lógico unidad de trabajo (LUW) puede contener varios trfc.</span><span class="sxs-lookup"><span data-stu-id="1041a-128">An SAP Logical Unit of Work (LUW) can contain multiple tRFCs.</span></span> <span data-ttu-id="1041a-129">En el sistema SAP un LUW se identifica por un Id. de transacción único (TID).</span><span class="sxs-lookup"><span data-stu-id="1041a-129">On the SAP system a LUW is identified by a unique Transaction ID (TID).</span></span> <span data-ttu-id="1041a-130">El adaptador crea una transacción confirmable para cada uno de los TID que usa el sistema SAP al invocar las llamadas de tRFC en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="1041a-130">The adapter creates a committable transaction for each of the TIDs that the SAP system uses when it invokes tRFC calls on the adapter.</span></span> <span data-ttu-id="1041a-131">Cuando el sistema SAP invoca un tRFC del adaptador; el adaptador pasa la transacción asociada con el TID SAP a su servicio.</span><span class="sxs-lookup"><span data-stu-id="1041a-131">When the SAP system invokes a tRFC on the adapter; the adapter flows the transaction associated with the SAP TID to your service.</span></span> <span data-ttu-id="1041a-132">Puede tener acceso a esta transacción como la transacción ambiente dentro del método de operación.</span><span class="sxs-lookup"><span data-stu-id="1041a-132">You can access this transaction as the ambient transaction from inside your operation method.</span></span> <span data-ttu-id="1041a-133">Dando de alta en esta transacción de ambiente, las acciones realizadas durante la operación pueden participar en el LUW en SAP.</span><span class="sxs-lookup"><span data-stu-id="1041a-133">By enlisting in this ambient transaction, the actions performed in the operation can participate in the SAP LUW.</span></span>  
  
 <span data-ttu-id="1041a-134">Para dar de alta la transacción de ambiente de un método de operación, debe:</span><span class="sxs-lookup"><span data-stu-id="1041a-134">To enlist in the ambient transaction in an operation method, you must:</span></span>  
  
1. <span data-ttu-id="1041a-135">Anotar el método de operación con el **TransactionScopeRequired** propiedad de la **OperationBehavior** atributo.</span><span class="sxs-lookup"><span data-stu-id="1041a-135">Annotate the operation method with the **TransactionScopeRequired** property of the **OperationBehavior** attribute.</span></span> <span data-ttu-id="1041a-136">Esto indica a WCF que desea tener acceso a la transacción ambiente desde dentro de la operación.</span><span class="sxs-lookup"><span data-stu-id="1041a-136">This tells WCF that you want access to the ambient transaction from inside the operation.</span></span>  
  
2. <span data-ttu-id="1041a-137">Crear un ámbito de transacción por anotar el método de operación con el **TransactionAutoComplete** propiedad de la **OperationBehavior** atributo o explícitamente con un  **TransactionScope** dentro del método de operación.</span><span class="sxs-lookup"><span data-stu-id="1041a-137">Create a transaction scope either by annotating the operation method with the **TransactionAutoComplete** property of the **OperationBehavior** attribute or by explicitly using a **TransactionScope** inside the operation method.</span></span>  
  
   <span data-ttu-id="1041a-138">El ejemplo siguiente muestra un servicio que implementa dos operaciones.</span><span class="sxs-lookup"><span data-stu-id="1041a-138">The following example shows a service that implements two operations.</span></span> <span data-ttu-id="1041a-139">Ambos métodos de operación se anotan con el **TransactionScopeRequired** propiedad para tener acceso a la transacción de ambiente.</span><span class="sxs-lookup"><span data-stu-id="1041a-139">Both operation methods are annotated with the **TransactionScopeRequired** property to access the ambient transaction.</span></span>  
  
-   <span data-ttu-id="1041a-140">**Z_TRFC_EXAMPLE1** da de alta explícitamente en la transacción mediante el uso de un **TransactionScope** objeto.</span><span class="sxs-lookup"><span data-stu-id="1041a-140">**Z_TRFC_EXAMPLE1** explicitly enlists in the transaction by using a **TransactionScope** object.</span></span>  
  
-   <span data-ttu-id="1041a-141">**Z_TRFC_EXAMPLE2** se anota con el **TransactionAutoComplete** propiedad que se va a dar de alta la transacción</span><span class="sxs-lookup"><span data-stu-id="1041a-141">**Z_TRFC_EXAMPLE2** is annotated with the **TransactionAutoComplete** property to enlist in the transaction</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, UseSynchronizationContext = false)]  
class Z_Example_ServiceContractClass : Trfc  
{  
  
    // This operation method explicitly creates a TransactionScope to enlist in the ambient transaction  
    // You must explictly call ts.Complete to complete the transaction before you return from the operation  
    // Otherwise the transaction is aborted.  
    // You can throw an exception or return without calling ts.complete to abort the transacation  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public Z_TRFC_EXAMPLE1Response Z_TRFC_EXAMPLE1(Z_TRFC_EXAMPLE1Request request)  
    {  
        using (TransactionScope ts = new TransactionScope(TransactionScopeOption.Required))  
        {  
            // Process tRFC  
  
            ...  
  
            Z_TRFC_EXAMPLE1Response response = new Z_TRFC_EXAMPLE1Response();  
            response.TransactionalRfcOperationIdentifier = request.TransactionalRfcOperationIdentifier;  
            return response;  
            //since there is no ts.Complete(), this is equivalent to a rollback.  
        }  
    }  
  
    // This operation method sets the TransactionAutoComplete property of the OperationBehavior attribute  
    // to enlist in the transaction. There is no need to explictly create a TransactionScope in the code.  
    // If the method returns with no unhandled exceptions, the transaction completes; otherwise it aborts  
    // You can throw an exception to abort the transaction.  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public Z_TRFC_EXAMPLE2Response Z_TRFC_EXAMPLE2(Z_TRFC_EXAMPLE2Request request)  
    {  
        // Process tRFC  
  
        ...  
  
        Z_TRFC_EXAMPLE2Response response = new Z_TRFC_EXAMPLE2Response();  
        response.TransactionalRfcOperationIdentifier = request.TransactionalRfcOperationIdentifier;  
        return response;  
        //if there is no unhandled exception, the transaction completes when the operation returns.  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1041a-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="1041a-142">See Also</span></span>  
[<span data-ttu-id="1041a-143">Desarrollar aplicaciones con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="1041a-143">Develop applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)