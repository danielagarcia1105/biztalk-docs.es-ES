---
title: Invocar trfc de SAP mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFCs, invoking by using the WCF service model
- WCF service model, invoking tRFCs
ms.assetid: 456fa869-2f1a-42e0-adbf-86bfe0876846
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d28e3cc47a213f122f30c2599063897e0485816
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002381"
---
# <a name="invoke-trfcs-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="8e1f7-102">Invocar trfc de SAP mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="8e1f7-102">Invoke tRFCs in SAP using the WCF Service Model</span></span>
<span data-ttu-id="8e1f7-103">Transaccional llamadas a funciones remotas (trfc) garantiza una *única* ejecución de una solicitud de cambio en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-103">Transactional Remote Function Calls (tRFCs) guarantee a *one-time* execution of an RFC on an SAP system.</span></span> <span data-ttu-id="8e1f7-104">Puede invocar cualquiera de los documentos RFC obtenidos por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como un tRFC.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-104">You can invoke any of the RFCs surfaced by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as a tRFC.</span></span> <span data-ttu-id="8e1f7-105">Invocar un tRFC en el modelo de servicio WCF es similar a invocar una RFC con las siguientes diferencias:</span><span class="sxs-lookup"><span data-stu-id="8e1f7-105">Invoking a tRFC in the WCF service model is similar to invoking an RFC with the following differences:</span></span>  
  
- <span data-ttu-id="8e1f7-106">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies trfc bajo un nodo diferente (TRFC) que las solicitudes de cambio (RFC).</span><span class="sxs-lookup"><span data-stu-id="8e1f7-106">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces tRFCs under a different node (TRFC) than RFCs (RFC).</span></span>  
  
- <span data-ttu-id="8e1f7-107">las llamadas de cliente tRFC no devuelven valores para la exportación SAP y cambiar los parámetros.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-107">tRFC client calls do not return values for SAP export and changing parameters.</span></span>  
  
- <span data-ttu-id="8e1f7-108">las operaciones de tRFC incluyen un parámetro GUID que se asigna al identificador de transacción de SAP (TID) para el tRFC por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e1f7-108">tRFC operations include a GUID parameter that is mapped to the SAP transaction ID (TID) for the tRFC by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="8e1f7-109">Después de invocar un tRFC, debe invocar la operación RfcConfirmTransID para confirmar la tRFC en el sistema SAP (confirmación).</span><span class="sxs-lookup"><span data-stu-id="8e1f7-109">After you invoke a tRFC, you must invoke the RfcConfirmTransID operation to confirm (commit) the tRFC on the SAP system.</span></span> <span data-ttu-id="8e1f7-110">Esta operación se expone directamente en el nodo TRFC.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-110">This operation is surfaced directly under the TRFC node.</span></span>  
  
  <span data-ttu-id="8e1f7-111">Para obtener más información sobre las operaciones de tRFC y la operación RfcConfirmTransID, consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="8e1f7-111">For more information about tRFC operations and the RfcConfirmTransID operation, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
  <span data-ttu-id="8e1f7-112">Las secciones siguientes muestran cómo invocar trfc en el sistema SAP mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e1f7-112">The following sections show you how to invoke tRFCs on the SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="8e1f7-113">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="8e1f7-113">The WCF Client Class</span></span>  
 <span data-ttu-id="8e1f7-114">La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone todas las operaciones de tRFC bajo un contrato de servicio único, "Trfc".</span><span class="sxs-lookup"><span data-stu-id="8e1f7-114">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces all tRFC operations under a single service contract, "Trfc".</span></span> <span data-ttu-id="8e1f7-115">Esto significa que una sola clase de cliente WCF, **TrfcClient**, se crea para todas las operaciones de tRFC que desea invocar.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-115">This means that a single WCF client class, **TrfcClient**, is created for all of the tRFC operations that you want to invoke.</span></span> <span data-ttu-id="8e1f7-116">Cada tRFC de destino se representa como un método de esta clase.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-116">Each target tRFC is represented as a method of this class.</span></span> <span data-ttu-id="8e1f7-117">Para cada método:</span><span class="sxs-lookup"><span data-stu-id="8e1f7-117">For each method:</span></span>  
  
- <span data-ttu-id="8e1f7-118">Tipos complejos de SAP como estructuras se exponen como clases .NET con propiedades que corresponden a los campos del tipo SAP.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-118">Complex SAP types such as structures are surfaced as .NET classes with properties that correspond to the fields of the SAP type.</span></span> <span data-ttu-id="8e1f7-119">Estas clases se definen en el espacio de nombres siguiente: **microsoft.lobservices.sap._2007._03.Types.Rfc**.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-119">These classes are defined in the following namespace: **microsoft.lobservices.sap._2007._03.Types.Rfc**.</span></span>  
  
  <span data-ttu-id="8e1f7-120">El código siguiente muestra parte de la **TrfcClient** clase y el método que invoca BAPI_SALESORDER_CREATEFROMDAT2 (como un tRFC) en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-120">The following code shows part of the **TrfcClient** class and the method that invokes BAPI_SALESORDER_CREATEFROMDAT2 (as a tRFC) on the SAP system.</span></span> <span data-ttu-id="8e1f7-121">El **TransactionalRfcOperationIdentifier** parámetro contiene el GUID que se asigna al TID de SAP.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-121">The **TransactionalRfcOperationIdentifier** parameter contains the GUID that is mapped to the SAP TID.</span></span> <span data-ttu-id="8e1f7-122">No todos los parámetros al método se muestran.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-122">Not all of the parameters to the method are shown.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class TrfcClient : System.ServiceModel.ClientBase<Trfc>, Trfc {  
  
    ....  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    public void BAPI_SALESORDER_CREATEFROMDAT2(  
                string BEHAVE_WHEN_ERROR,   
                string BINARY_RELATIONSHIPTYPE,   
                string CONVERT,   
                string INT_NUMBER_ASSIGNMENT,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDLS LOGIC_SWITCH,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1 ORDER_HEADER_IN,   
  
                …  
  
               microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIADDR1[] PARTNERADDRESSES,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2[] RETURN,   
                ref System.Guid TransactionalRfcOperationIdentifier) { ...  }  
}  
```  
  
 <span data-ttu-id="8e1f7-123">El código siguiente muestra el método que se genera para la operación RfcConfirmTransID.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-123">The following code shows the method that is generated for the RfcConfirmTransID operation.</span></span> <span data-ttu-id="8e1f7-124">Debe asegurarse de que este método se genera como parte de la **TrfcClient**.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-124">You must ensure that this method is generated as part of the **TrfcClient**.</span></span> <span data-ttu-id="8e1f7-125">La operación RfcConfirmTransID aparece directamente en el nodo TRFC.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-125">The RfcConfirmTransID operation is surfaced directly under the TRFC node.</span></span>  
  
```  
public void RfcConfirmTransID(System.Guid TransactionalRfcOperationIdentifier) {…}  
```  
  
## <a name="how-to-create-a-trfc-client-application"></a><span data-ttu-id="8e1f7-126">Cómo crear una aplicación de cliente tRFC</span><span class="sxs-lookup"><span data-stu-id="8e1f7-126">How to Create a tRFC Client Application</span></span>  
 <span data-ttu-id="8e1f7-127">Los pasos para crear una aplicación que invoca trfc son similares a los pasos que seguir para invocar RFC, con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="8e1f7-127">The steps to create an application that invokes tRFCs are similar to the steps you follow to invoke RFCs, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="8e1f7-128">Debe recuperar las operaciones de destino en el nodo TRFC.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-128">You must retrieve the target operations under the TRFC node.</span></span>  
  
-   <span data-ttu-id="8e1f7-129">Debe recuperar la operación RfcConfirmTransID.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-129">You must retrieve the RfcConfirmTransID operation.</span></span> <span data-ttu-id="8e1f7-130">Esto se expone directamente en el nodo TRFC.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-130">This is surfaced directly under the TRFC node.</span></span>  
  
-   <span data-ttu-id="8e1f7-131">Para confirmar una operación tRFC en el sistema SAP (confirmación), debe invocar la operación RfcConfirmTransID con el GUID que se devolvió para esa operación tRFC.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-131">To confirm (commit) a tRFC operation on the SAP system, you must invoke the RfcConfirmTransID operation with the GUID that was returned for that tRFC operation.</span></span>  
  
#### <a name="to-create-a-trfc-client-application"></a><span data-ttu-id="8e1f7-132">Para crear una aplicación de cliente tRFC</span><span class="sxs-lookup"><span data-stu-id="8e1f7-132">To create a tRFC client application</span></span>  
  
1. <span data-ttu-id="8e1f7-133">Generar un **TrfcClient** clase.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-133">Generate a **TrfcClient** class.</span></span> <span data-ttu-id="8e1f7-134">Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutil.exe) para generar un **TrfcClient** clase que tiene como destino las RFC con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-134">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a **TrfcClient** class that targets the RFCs with which you want to work.</span></span> <span data-ttu-id="8e1f7-135">Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de solución de SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="8e1f7-135">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF Service Contract for SAP solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span> <span data-ttu-id="8e1f7-136">Asegúrese de que la operación RfcConfirmTransID se incluye en el **TrfcClient** clase.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-136">Ensure that the RfcConfirmTransID operation is included in the **TrfcClient** class.</span></span>  
  
2. <span data-ttu-id="8e1f7-137">Cree una instancia de la **TrfcClient** clase generado en el paso 1 y especificar un enlace de cliente.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-137">Create an instance of the **TrfcClient** class generated in step 1 and specify a client binding.</span></span> <span data-ttu-id="8e1f7-138">Especificar un enlace de cliente implica especificar el enlace y el punto de conexión de direcciones que el **TrfcClient** va a usar.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-138">Specifying a client binding involves specifying the binding and endpoint address that the **TrfcClient** will use.</span></span> <span data-ttu-id="8e1f7-139">Puede hacerlo imperativamente en código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-139">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="8e1f7-140">Para obtener más información sobre cómo especificar un enlace de cliente, consulte [configurar un enlace de cliente para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="8e1f7-140">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="8e1f7-141">El siguiente código inicializa el **TrfcClient** de configuración y establece las credenciales para el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-141">The following code initializes the **TrfcClient** from configuration and sets the credentials for the SAP system.</span></span>  
  
   ```  
   TrfcClient trfcClient = new TrfcClient("SAPBinding_Rfc");  
  
   trfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
   trfcClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. <span data-ttu-id="8e1f7-142">Abra el **TrfcClient**.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-142">Open the **TrfcClient**.</span></span>  
  
   ```  
   trfcClient.Open();  
   ```  
  
4. <span data-ttu-id="8e1f7-143">Invocar el método adecuado en el **TrfcClient** creado en el paso 2 para invocar la tRFC de destino en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-143">Invoke the appropriate method on the **TrfcClient** created in step 2 to invoke the target tRFC on the SAP system.</span></span> <span data-ttu-id="8e1f7-144">Puede pasar una variable que contiene un GUID o que contiene un GUID vacío para el **TransactionalRrcOperationIdentifier** parámetro.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-144">You can pass a variable that contains a GUID or that contains an empty GUID for the **TransactionalRrcOperationIdentifier** parameter.</span></span> <span data-ttu-id="8e1f7-145">Si se pasa un GUID vacío, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] genera uno automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-145">If you pass an empty GUID, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] generates one for you.</span></span> <span data-ttu-id="8e1f7-146">El código siguiente invoca BAPI_SALESORDER_CREATEFROMDAT2 como un tRFC en el sistema SAP (no todos los parámetros del método se muestran).</span><span class="sxs-lookup"><span data-stu-id="8e1f7-146">The following code invokes BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC on the SAP system (not all parameters to the method are shown).</span></span> <span data-ttu-id="8e1f7-147">Se especificó un GUID.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-147">A GUID is specified.</span></span>  
  
   ```  
   transactionalRfcOperationIdentifier = Guid.NewGuid();  
  
   //invoke RFC_CUSTOMER_GET as a tRFC  
   trfcClient.BAPI_SALESORDER_CREATEFROMDAT2(  
                                   request.BEHAVE_WHEN_ERROR,  
                                   request.BINARY_RELATIONSHIPTYPE,  
                                   request.CONVERT,  
  
                                   ...  
  
                                   ref transactionalRfcOperationIdentifier);  
   ```  
  
5. <span data-ttu-id="8e1f7-148">Para confirmar el TID asociado con el tRFC en el sistema SAP, invocar el **RfcConfirmTransID** método en el **TrfcClient**.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-148">To confirm the TID associated with the tRFC on the SAP system, invoke the **RfcConfirmTransID** method on the **TrfcClient**.</span></span> <span data-ttu-id="8e1f7-149">Especifique el GUID devuelto en el paso 4 para el **TransactionRfcOperationIdentifier**parámetro.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-149">Specify the GUID returned in step 4 for the **TransactionRfcOperationIdentifier**parameter.</span></span>  
  
   ```  
   trfcClient.RfcConfirmTransID(transactionalRfcOperationIdentifier);  
   ```  
  
6. <span data-ttu-id="8e1f7-150">Cerrar la **TrfcClient** cuando haya terminado con él (cuando haya terminado de invocar trfc todas).</span><span class="sxs-lookup"><span data-stu-id="8e1f7-150">Close the **TrfcClient** when you are done using it (after you have finished invoking all tRFCs).</span></span>  
  
   ```  
   trfcClient.Close();   
   ```  
  
### <a name="example"></a><span data-ttu-id="8e1f7-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e1f7-151">Example</span></span>  
 <span data-ttu-id="8e1f7-152">El ejemplo siguiente muestra cómo invocar BAPI_SALESORDER_CREATE como un tRFC.</span><span class="sxs-lookup"><span data-stu-id="8e1f7-152">The following example shows how to invoke BAPI_SALESORDER_CREATE as a tRFC.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, the WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for WCF LOB Adapter SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using microsoft.lobservices.sap._2007._03.Types.Rfc;  
  
// This example demonstrates sending BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC. The client has   
// methods to:  
//      send the BAPI (BAPI_SALESORDER_CREATEFROMDAT2)and to  
//      Confirm the transaction (RfcConfirmTransID)  
// An instance of BAPI_SALESORDER_CREATEFROMDAT2Request (generated)   
// is used to format the BAPI before invoking BAPI_SALESORDER_CREATEFROMDAT2. This   
// is not necessary, but is done to make it easier to read the code.  
// tRFC invocations always includes a ref parameter that contains a GUID. You can optionally   
// set this parameter when you invoke the method; however, you must use the value returned by  
// the adapter when you call RfcConfirmTransID to confirm the transaction on the SAP system.   
// You can call the utility method, SAPAdapterUtilities.ConvertGuidToTid, to get the value  
// of the SAP transaction Id from the GUID that the adapter returns.  
namespace SapTrfcClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            TrfcClient sapTrfcClient = null;  
  
            try  
            {  
                Console.WriteLine("SAP TRFC client sample started");  
                Console.WriteLine("Creating the TRFC client");  
                // Create the SAP Trfc Client from configuration  
                sapTrfcClient = new TrfcClient("SAPBinding_Trfc");  
                sapTrfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
                sapTrfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                Console.WriteLine("Opening the TRFC client");  
                // Open the Trfc Client  
                sapTrfcClient.Open();  
  
                // Create a GUID -- note: this is optional. If you do not pass a GUID,  
                // for the TransactionalRfcOperationIdentifier parameter, the SAP adapter will   
                // generate one, associate it with the SAP TID, and set the   
                // TransactionalRfcOperationIdentifier parameter.  
                Guid tidGuid = Guid.NewGuid();  
  
                BAPI_SALESORDER_CREATEFROMDAT2Request request = new BAPI_SALESORDER_CREATEFROMDAT2Request();  
  
                request.ORDER_HEADER_IN = new BAPISDHD1();  
                request.ORDER_HEADER_IN.DOC_TYPE = "TA";  
                request.ORDER_HEADER_IN.SALES_ORG = "1000";  
                request.ORDER_HEADER_IN.DISTR_CHAN = "10";  
                request.ORDER_HEADER_IN.DIVISION = "00";  
                request.ORDER_HEADER_IN.SALES_OFF = "1000";  
                request.ORDER_HEADER_IN.REQ_DATE_H = DateTime.Now;  
                request.ORDER_HEADER_IN.PURCH_DATE = DateTime.Now;  
                request.ORDER_HEADER_IN.PURCH_NO_C = "Cust PO";  
                request.ORDER_HEADER_IN.CURRENCY = "EUR";  
  
                BAPISDITM[] orderItems = new BAPISDITM[1];  
                orderItems[0] = new BAPISDITM();  
                orderItems[0].MATERIAL = "P-109";  
                orderItems[0].PLANT = "1000";  
                orderItems[0].TARGET_QU = "ST";  
                request.ORDER_ITEMS_IN = orderItems;  
  
                BAPIPARNR[] orderPartners = new BAPIPARNR[1];  
                orderPartners[0] = new microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPARNR();  
                orderPartners[0].PARTN_ROLE = "AG";  
                orderPartners[0].PARTN_NUMB = "0000001390";  
                request.ORDER_PARTNERS = orderPartners;  
  
                // Create a GUID -- note: this is optional. If you do not pass a GUID,  
                // for the TransactionalRfcOperationIdentifier parameter, the SAP adapter will   
                // generate one, associate it with the SAP TID, and set the   
                // TransactionalRfcOperationIdentifier parameter.  
                request.TransactionalRfcOperationIdentifier = Guid.NewGuid();  
  
                Console.WriteLine("Invoking BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC");  
  
                //invoke RFC_CUSTOMER_GET as a tRFC  
                sapTrfcClient.BAPI_SALESORDER_CREATEFROMDAT2(request.BEHAVE_WHEN_ERROR,  
                                                                request.BINARY_RELATIONSHIPTYPE,  
                                                                request.CONVERT,  
                                                                request.INT_NUMBER_ASSIGNMENT,  
                                                                request.LOGIC_SWITCH,  
                                                                request.ORDER_HEADER_IN,  
                                                                request.ORDER_HEADER_INX,  
                                                                request.SALESDOCUMENTIN,  
                                                                request.SENDER,  
                                                                request.TESTRUN,  
                                                                request.EXTENSIONIN,  
                                                                request.ORDER_CCARD,  
                                                                request.ORDER_CFGS_BLOB,  
                                                                request.ORDER_CFGS_INST,  
                                                                request.ORDER_CFGS_PART_OF,  
                                                                request.ORDER_CFGS_REF,  
                                                                request.ORDER_CFGS_REFINST,  
                                                                request.ORDER_CFGS_VALUE,  
                                                                request.ORDER_CFGS_VK,  
                                                                request.ORDER_CONDITIONS_IN,  
                                                                request.ORDER_CONDITIONS_INX,  
                                                                request.ORDER_ITEMS_IN,  
                                                                request.ORDER_ITEMS_INX,  
                                                                request.ORDER_KEYS,  
                                                                request.ORDER_PARTNERS,  
                                                                request.ORDER_SCHEDULES_IN,  
                                                                request.ORDER_SCHEDULES_INX,  
                                                                request.ORDER_TEXT,  
                                                                request.PARTNERADDRESSES,  
                                                                request.RETURN,  
                                                                ref request.TransactionalRfcOperationIdentifier);  
  
                string sapTxId = null;  
                sapTxId = SAPAdapterUtilities.ConvertGuidToTid(request.TransactionalRfcOperationIdentifier);  
  
                Console.WriteLine("BAPI_SALESORDER_CREATEFROMDAT2 Sent");  
                Console.WriteLine("The SAP Transaction Id is " + sapTxId);  
  
                // Invoke the RfcConfirmTransID method to confirm (commit) the transaction on  
                // the SAP system. This step is required to complete the transaction. The SAP  
                // adapter will always return a TranactionalRfcOperationIdentifier, whether   
                // one was supplied in the call or not.  
                sapTrfcClient.RfcConfirmTransID(request.TransactionalRfcOperationIdentifier);  
  
                Console.WriteLine("SAP Transaction {0} has been committed", sapTxId);  
  
                Console.WriteLine("\nHit <RETURN> to end");  
                Console.ReadLine();  
  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
                throw;  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw;  
            }  
            finally  
            {  
                // Close the client  
                if (sapTrfcClient != null)  
                {  
                    if (sapTrfcClient.State == CommunicationState.Opened)  
                        sapTrfcClient.Close();  
                    else  
                        sapTrfcClient.Abort();  
                }  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e1f7-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e1f7-153">See Also</span></span>  
<span data-ttu-id="8e1f7-154">[Desarrollar aplicaciones mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="8e1f7-154">[Develop applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 [<span data-ttu-id="8e1f7-155">Operaciones en trfc de SAP</span><span class="sxs-lookup"><span data-stu-id="8e1f7-155">Operations on tRFCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)