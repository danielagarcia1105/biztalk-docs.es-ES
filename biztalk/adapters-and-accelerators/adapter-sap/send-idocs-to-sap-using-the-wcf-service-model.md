---
title: Enviar los IDOC a SAP mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, sending IDOCs to SAP
- IDOCs, sending to SAP by using the WCF service model
ms.assetid: 84077234-b82b-4e88-b858-ce2cb1383fb4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7efff52b335acb9ab1835bdecf38caf8d0e67e71
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988229"
---
# <a name="send-idocs-to-sap-using-the-wcf-service-model"></a><span data-ttu-id="564ef-102">Enviar los IDOC a SAP mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="564ef-102">Send IDOCs to SAP using the WCF Service Model</span></span>
<span data-ttu-id="564ef-103">Internamente, el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] envía el IDOC al sistema SAP mediante la invocación de una de las dos siguientes RFC:</span><span class="sxs-lookup"><span data-stu-id="564ef-103">Internally, the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] sends IDOCs to the SAP system by invoking one of the two following RFCs:</span></span>  
  
- <span data-ttu-id="564ef-104">IDOC_INBOUND_ASYNCHRONOUS para IDOC versión 3.</span><span class="sxs-lookup"><span data-stu-id="564ef-104">IDOC_INBOUND_ASYNCHRONOUS for version 3 IDOCs.</span></span>  
  
- <span data-ttu-id="564ef-105">INBOUND_IDOC_PROCESS para IDOC versión 2.</span><span class="sxs-lookup"><span data-stu-id="564ef-105">INBOUND_IDOC_PROCESS for version 2 IDOCs.</span></span>  
  
  <span data-ttu-id="564ef-106">Puede enviar un IDOC al adaptador mediante la invocación de la RFC adecuado (o tRFC); Sin embargo, también puede usar las dos operaciones siguientes para enviar los IDOC para el adaptador:</span><span class="sxs-lookup"><span data-stu-id="564ef-106">You can send an IDOC to the adapter by invoking the appropriate RFC (or tRFC); however, you can also use the two following operations to send IDOCs to the adapter:</span></span>  
  
- <span data-ttu-id="564ef-107">**SendIdoc** aparece directamente en el nodo raíz IDOC.</span><span class="sxs-lookup"><span data-stu-id="564ef-107">**SendIdoc** is surfaced directly under the IDOC root node.</span></span> <span data-ttu-id="564ef-108">La operación SendIdoc envía el IDOC como datos de cadena (débilmente tipada) a la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="564ef-108">The SendIdoc operation sends the IDOC as string (weakly-typed) data to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="564ef-109">**Enviar** aparece individualmente para cada IDOC.</span><span class="sxs-lookup"><span data-stu-id="564ef-109">**Send** is surfaced individually for each IDOC.</span></span> <span data-ttu-id="564ef-110">La operación de envío envía el IDOC como datos fuertemente tipados a la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="564ef-110">The Send operation sends the IDOC as strongly-typed data to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
  <span data-ttu-id="564ef-111">Estas operaciones determinan cómo se envían los datos IDOC al adaptador, no cómo se envía al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="564ef-111">These operations determine how the IDOC data is sent to the adapter, not how it is sent to the SAP system.</span></span> <span data-ttu-id="564ef-112">El adaptador siempre envía el IDOC al sistema SAP mediante la tRFC adecuado.</span><span class="sxs-lookup"><span data-stu-id="564ef-112">The adapter always sends the IDOC to the SAP system by using the appropriate tRFC.</span></span>  
  
  <span data-ttu-id="564ef-113">Dado que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] envía el IDOC como un tRFC, las operaciones de envío y SendIdoc exponen un parámetro GUID que usa para confirmar el IDOC (confirmación).</span><span class="sxs-lookup"><span data-stu-id="564ef-113">Because the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] sends the IDOC as a tRFC, both the Send and SendIdoc operations expose a GUID parameter that you use to confirm (commit) the IDOC.</span></span> <span data-ttu-id="564ef-114">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] internamente se asigna este GUID con la transacción TID (Id.) que está asociado el tRFC SAP.</span><span class="sxs-lookup"><span data-stu-id="564ef-114">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] internally maps this GUID with the SAP transaction ID (TID) that is associated with the tRFC.</span></span> <span data-ttu-id="564ef-115">Puede confirmar el IDOC en uno de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="564ef-115">You can confirm the IDOC in one of two ways:</span></span>  
  
- <span data-ttu-id="564ef-116">Mediante el uso de la **AutoConfirmSentIdocs** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="564ef-116">By using the **AutoConfirmSentIdocs** binding property.</span></span> <span data-ttu-id="564ef-117">Si se establece esta propiedad de enlace en **true**, el adaptador confirma automáticamente la tRFC utilizado para enviar el IDOC.</span><span class="sxs-lookup"><span data-stu-id="564ef-117">If this binding property is set to **true**, the adapter automatically confirms the tRFC used to send the IDOC.</span></span>  
  
- <span data-ttu-id="564ef-118">Invocando RfcConfirmTransID.</span><span class="sxs-lookup"><span data-stu-id="564ef-118">By invoking RfcConfirmTransID.</span></span> <span data-ttu-id="564ef-119">Invocar esta operación con el GUID asociado con el IDOC.</span><span class="sxs-lookup"><span data-stu-id="564ef-119">You invoke this operation with the GUID associated with the IDOC.</span></span>  
  
  <span data-ttu-id="564ef-120">Las secciones siguientes muestran cómo enviar los IDOC a un sistema SAP mediante el uso de las operaciones de SendIdoc y envío.</span><span class="sxs-lookup"><span data-stu-id="564ef-120">The following sections show you how to send IDOCs to an SAP system by using the SendIdoc and Send operations.</span></span> <span data-ttu-id="564ef-121">Para que obtener más información para ayudarle a enviar un IDOC como un tRFC, consulte [invocar trfc de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="564ef-121">For more information to help you send an IDOC as a tRFC, see [Invoke tRFCs in SAP by using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="564ef-122">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="564ef-122">The WCF Client Class</span></span>  
  
### <a name="the-sendidoc-operation"></a><span data-ttu-id="564ef-123">La operación SendIdoc</span><span class="sxs-lookup"><span data-stu-id="564ef-123">The SendIdoc Operation</span></span>  
 <span data-ttu-id="564ef-124">La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone una única operación (y el contrato de servicio) para enviar un IDOC en formato de cadena.</span><span class="sxs-lookup"><span data-stu-id="564ef-124">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces a single operation (and service contract) to send an IDOC in string format.</span></span> <span data-ttu-id="564ef-125">El nombre del contrato de servicio es "Idoc" y la clase de cliente WCF es **IdocClient**.</span><span class="sxs-lookup"><span data-stu-id="564ef-125">The name of the service contract is "Idoc" and the WCF client class is **IdocClient**.</span></span>  
  
 <span data-ttu-id="564ef-126">Puede enviar los IDOC a SAP mediante el uso de este cliente.</span><span class="sxs-lookup"><span data-stu-id="564ef-126">You can send any IDOC to SAP by using this client.</span></span> <span data-ttu-id="564ef-127">Contiene un método único, **SendIdoc**, que toma dos parámetros:</span><span class="sxs-lookup"><span data-stu-id="564ef-127">It contains a single method, **SendIdoc**, that takes two parameters:</span></span>  
  
- <span data-ttu-id="564ef-128">**idocData** es una cadena que contiene los datos IDOC</span><span class="sxs-lookup"><span data-stu-id="564ef-128">**idocData** is a string that contains the IDOC data</span></span>  
  
- <span data-ttu-id="564ef-129">**GUID** es el GUID que se asigna al TID de SAP.</span><span class="sxs-lookup"><span data-stu-id="564ef-129">**guid** is the GUID that is mapped to the SAP TID.</span></span>  
  
  <span data-ttu-id="564ef-130">El código siguiente muestra al cliente de WCF que se genera para la operación SendIdoc.</span><span class="sxs-lookup"><span data-stu-id="564ef-130">The following code shows the WCF client that is generated for the SendIdoc operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class IdocClient : System.ServiceModel.ClientBase<Idoc>, Idoc {  
  
    public void SendIdoc(string idocData, ref System.Nullable\<System.Guid\> guid) {…}  
}  
```  
  
### <a name="the-send-operation"></a><span data-ttu-id="564ef-131">La operación de envío</span><span class="sxs-lookup"><span data-stu-id="564ef-131">The Send Operation</span></span>  
 <span data-ttu-id="564ef-132">Dado que la operación de envío usa datos fuertemente tipados, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone un contrato de servicio único para cada IDOC.</span><span class="sxs-lookup"><span data-stu-id="564ef-132">Because the Send operation uses strongly-typed data, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces a unique service contract for each IDOC.</span></span> <span data-ttu-id="564ef-133">El nombre de la interfaz (y la clase de cliente WCF) generado para este contrato se basa en el tipo de IDOC, versión, el número de versión y tipo CIM (si procede).</span><span class="sxs-lookup"><span data-stu-id="564ef-133">The name of the interface (and the WCF client class) generated for this contract is based on the IDOC type, version, release number, and CIM type (if relevant).</span></span> <span data-ttu-id="564ef-134">Por ejemplo, para el IDOC ORDERS03.v3.620, la interfaz se denomina "IdocORDERS03V3R620" y la clase de cliente WCF es **IdocORDERS03V3R620Client**.</span><span class="sxs-lookup"><span data-stu-id="564ef-134">For example for the ORDERS03.v3.620 IDOC, the interface is named "IdocORDERS03V3R620" and the WCF client class is **IdocORDERS03V3R620Client**.</span></span>  
  
 <span data-ttu-id="564ef-135">Debe generar a un cliente único para cada tipo de IDOC diferente.</span><span class="sxs-lookup"><span data-stu-id="564ef-135">You must generate a unique client for each different type of IDOC.</span></span> <span data-ttu-id="564ef-136">Este cliente contiene un único método, **enviar**, que toma dos parámetros:</span><span class="sxs-lookup"><span data-stu-id="564ef-136">This client contains a single method, **Send**, that takes two parameters:</span></span>  
  
- <span data-ttu-id="564ef-137">**idocData** es una clase que representa los datos IDOC fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="564ef-137">**idocData** is a class that represents the strongly-typed IDOC data.</span></span>  
  
- <span data-ttu-id="564ef-138">**GUID** es una representación de cadena del GUID que se asigna al TID de SAP.</span><span class="sxs-lookup"><span data-stu-id="564ef-138">**guid** is a string representation of the GUID that is mapped to the SAP TID.</span></span>  
  
  <span data-ttu-id="564ef-139">El código siguiente muestra al cliente de WCF que se genera para la operación de envío que se exponen para el IDOC ORDERS03.v3.620.</span><span class="sxs-lookup"><span data-stu-id="564ef-139">The following code shows the WCF client that is generated for the Send operation surfaced for the ORDERS03.v3.620 IDOC.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class IdocORDERS03V3R620Client : System.ServiceModel.ClientBase<IdocORDERS03V3R620>, IdocORDERS03V3R620 {  
  
    ...  
  
    public void Send(ORDERS03 idocData, ref string guid) { ... }  
}  
```  
  
## <a name="how-to-create-an-application-to-send-idocs"></a><span data-ttu-id="564ef-140">Cómo crear una aplicación para enviar los IDOC</span><span class="sxs-lookup"><span data-stu-id="564ef-140">How to Create an Application to Send IDOCs</span></span>  
 <span data-ttu-id="564ef-141">Para enviar un IDOC a un sistema SAP, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="564ef-141">To send an IDOC to an SAP system, perform the following steps.</span></span>  
  
#### <a name="to-send-an-idoc-to-an-sap-system"></a><span data-ttu-id="564ef-142">Para enviar un IDOC a un sistema SAP</span><span class="sxs-lookup"><span data-stu-id="564ef-142">To send an IDOC to an SAP system</span></span>  
  
1. <span data-ttu-id="564ef-143">Generar una clase de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="564ef-143">Generate a WCF client class.</span></span> <span data-ttu-id="564ef-144">Use el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutil.exe) para generar la clase de cliente WCF que tiene como destino el IDOC con la que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="564ef-144">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate the WCF client class that targets the IDOCs with which you want to work.</span></span> <span data-ttu-id="564ef-145">Para obtener más información sobre cómo generar un cliente de WCF, vea [generando un contrato de servicio de WCF o un cliente de WCF para artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="564ef-145">For more information about how to generate a WCF client, see [Generating a WCF Client or a WCF Service Contract for SAP Solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span> <span data-ttu-id="564ef-146">Si desea confirmar explícitamente los IDOC, asegúrese de que genera al cliente de WCF para la operación RfcConfirmTransID.</span><span class="sxs-lookup"><span data-stu-id="564ef-146">If you want to explicitly confirm IDOCs, make sure that you generate the WCF client for the RfcConfirmTransID operation.</span></span> <span data-ttu-id="564ef-147">Las operaciones pueden encontrarse en los nodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="564ef-147">Operations can be found under the following nodes:</span></span>  
  
   -   <span data-ttu-id="564ef-148">Operación SendIdoc.</span><span class="sxs-lookup"><span data-stu-id="564ef-148">SendIdoc operation.</span></span> <span data-ttu-id="564ef-149">Directamente en el nodo IDOC.</span><span class="sxs-lookup"><span data-stu-id="564ef-149">Directly under the IDOC node.</span></span>  
  
   -   <span data-ttu-id="564ef-150">Operación de envío.</span><span class="sxs-lookup"><span data-stu-id="564ef-150">Send operation.</span></span> <span data-ttu-id="564ef-151">En el nodo correspondiente al número de tipo, versión y lanzamiento del destino IDOC.</span><span class="sxs-lookup"><span data-stu-id="564ef-151">Under the node corresponding to the type, version and release number of the target IDOC.</span></span>  
  
   -   <span data-ttu-id="564ef-152">Operación RfcConfirmTransID.</span><span class="sxs-lookup"><span data-stu-id="564ef-152">RfcConfirmTransID operation.</span></span> <span data-ttu-id="564ef-153">Directamente en el nodo TRFC.</span><span class="sxs-lookup"><span data-stu-id="564ef-153">Directly under the TRFC node.</span></span>  
  
2. <span data-ttu-id="564ef-154">Cree una instancia de la clase de cliente WCF generada en el paso 1, y especificar un enlace de cliente.</span><span class="sxs-lookup"><span data-stu-id="564ef-154">Create an instance of the WCF client class generated in step 1, and specify a client binding.</span></span> <span data-ttu-id="564ef-155">Especificar un enlace de cliente implica especificar el enlace y dirección de punto de conexión que va a usar el cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="564ef-155">Specifying a client binding involves specifying the binding and endpoint address that the WCF client will use.</span></span> <span data-ttu-id="564ef-156">Puede hacerlo imperativamente en código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="564ef-156">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="564ef-157">Para obtener más información sobre cómo especificar un enlace de cliente, consulte [configurar un enlace de cliente para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="564ef-157">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="564ef-158">El código siguiente inicializa un IdocClient (para la operación de envío) de configuración y establece las credenciales para el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="564ef-158">The following code initializes an IdocClient (for the Send operation) from configuration and sets the credentials for the SAP system.</span></span>  
  
   ```  
   SAPBinding binding = new SAPBinding();  
  
   // Set endpoint address  
   EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
   // Create client and set credentials  
   idocClient = new IdocClient(binding, endpointAddress);  
   idocClient.ClientCredentials.UserName.UserName = "YourUserName";  
   idocClient.ClientCredentials.UserName.Password = "YourPassword";;  
   ```  
  
3. <span data-ttu-id="564ef-159">Si desea que el adaptador para confirmar la tRFC en el sistema SAP después de envía el IDOC, establezca el **AutoConfirmSentIdocs** enlazar la propiedad a **true**.</span><span class="sxs-lookup"><span data-stu-id="564ef-159">If you want the adapter to confirm the tRFC on the SAP system after it sends the IDOC, set the **AutoConfirmSentIdocs** binding property to **true**.</span></span> <span data-ttu-id="564ef-160">Debe hacerlo antes de abrir al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="564ef-160">You must do this before you open the WCF client.</span></span>  
  
   ```  
   // Set AutoConfirmSentIdocs property to true  
   binding.AutoConfirmSentIdocs = true;  
   ```  
  
4. <span data-ttu-id="564ef-161">Abra al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="564ef-161">Open the WCF client.</span></span>  
  
   ```  
   idocClient.Open();  
   ```  
  
5. <span data-ttu-id="564ef-162">Invocar el método adecuado en el cliente WCF que creó en el paso 2 para enviar el IDOC al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="564ef-162">Invoke the appropriate method on the WCF client created in step 2 to send the IDOC to the SAP system.</span></span> <span data-ttu-id="564ef-163">Puede pasar una variable que contiene un GUID o que se establece en **null** para el **guid** parámetro.</span><span class="sxs-lookup"><span data-stu-id="564ef-163">You can pass a variable that contains a GUID or that is set to **null** for the **guid** parameter.</span></span> <span data-ttu-id="564ef-164">Si no especifica un GUID, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] genera uno para la operación (**guid** es un **ref** parámetro).</span><span class="sxs-lookup"><span data-stu-id="564ef-164">If you do not specify a GUID, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] generates one for the operation (**guid** is a **ref** parameter).</span></span> <span data-ttu-id="564ef-165">El código siguiente lee un IDOC (en formato de cadena) de un archivo y lo envía al sistema SAP mediante la operación SendIdoc.</span><span class="sxs-lookup"><span data-stu-id="564ef-165">The following code reads an IDOC (in string format) from a file and sends it to the SAP system by using the SendIdoc operation.</span></span>  
  
   ```  
   // Read IDOC into string variable  
   using (StreamReader reader = new StreamReader("ORDERS03.txt"))  
   {  
   idocData = reader.ReadToEnd();  
   }  
  
   //Get a new GUID to pass to SendIdoc. You can also assign a null  
   //value to have the adapter generate a GUID.  
   adapterTxGuid = Guid.NewGuid();  
  
   //Invoke SendIdoc on the client to send the IDOC to the SAP system  
   idocClient.SendIdoc(idocData, ref adapterTxGuid);  
   ```  
  
6. <span data-ttu-id="564ef-166">Si no estableció la **AutoConfirmSentIdocs** enlazar la propiedad a **true** (en el paso 3), a continuación, debe confirmar el tRFC en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="564ef-166">If you did not set the **AutoConfirmSentIdocs** binding property to **true** (in step 3), then you must confirm the tRFC on the SAP system.</span></span> <span data-ttu-id="564ef-167">Para ello se debe invocar el **RfcConfirmTransID** método en un **TrfcClient** (no se muestra la creación).</span><span class="sxs-lookup"><span data-stu-id="564ef-167">To do this you must invoke the **RfcConfirmTransID** method on a **TrfcClient** (creation not shown).</span></span> <span data-ttu-id="564ef-168">Especifique el GUID devuelto en el paso 4 para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="564ef-168">Specify the GUID returned in step 4 for the parameter.</span></span>  
  
   ```  
   trfcClient.RfcConfirmTransID(adapterTxGuid);  
   ```  
  
7. <span data-ttu-id="564ef-169">Cierre el cliente WCF (y **TrfcClient**, si se usa) cuando haya terminado con él (cuando haya terminado de enviar los idoc).</span><span class="sxs-lookup"><span data-stu-id="564ef-169">Close the WCF client (and **TrfcClient**, if used) when you are done using it (after you have finished sending IDOCs).</span></span>  
  
   ```  
   idocClient.Close();   
   ```  
  
### <a name="example"></a><span data-ttu-id="564ef-170">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="564ef-170">Example</span></span>  
 <span data-ttu-id="564ef-171">El ejemplo siguiente envía un IDOC a un sistema SAP mediante el método SendIdoc.</span><span class="sxs-lookup"><span data-stu-id="564ef-171">The following example sends an IDOC to an SAP system by using the SendIdoc method.</span></span> <span data-ttu-id="564ef-172">El IDOC se lee desde un archivo, ORDERS03.txt.</span><span class="sxs-lookup"><span data-stu-id="564ef-172">The IDOC is read from a file, ORDERS03.txt.</span></span> <span data-ttu-id="564ef-173">Este archivo contiene un ORDERS03. IDOC V3.620 y se incluye con los ejemplos; Sin embargo, la operación de SendIdoc puede utilizarse para enviar todos los IDOC.</span><span class="sxs-lookup"><span data-stu-id="564ef-173">This file contains an ORDERS03.V3.620 IDOC and is included with the samples; however, the SendIdoc operation can be used to send any IDOC.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.IO;  
  
// Add WCF, WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for WCF LOB Adapter SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// This example sends a flat IDOC to the SAP system by using the SendIdoc operation.  
namespace SapIdocStringClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // variable for the IDOC client  
            IdocClient idocClient = null;  
  
            Console.WriteLine("IDOC string client sample started");  
            try  
            {  
                // Variable for the GUID  
                System.Nullable<System.Guid> adapterTxGuid;  
                // string to hold the Idoc data  
                string idocData;  
                // string to hold the SAP transaction ID (TID)  
                string sapTxId;  
  
                // The client can be configured from app.config, but it is   
                // explicitly configured here for demonstration.  
                // set AutoConfirmSentIdocs property to true  
                SAPBinding binding = new SAPBinding();  
                binding.AutoConfirmSentIdocs = true;  
  
                // Set endpoint address  
                EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPServer/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
                // Create client and set credentials  
                idocClient = new IdocClient(binding, endpointAddress);  
                idocClient.ClientCredentials.UserName.UserName = "YourUserName";  
                idocClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                // Open the client and send the Idoc  
                idocClient.Open();  
  
                // Read IDOC into string variable  
                using (StreamReader reader = new StreamReader("ORDERS03.txt"))  
                {  
                    idocData = reader.ReadToEnd();  
                }  
  
                //Get a new GUID to pass to SendIdoc. You can also assign a null.  
                //value to have the adapter generate a GUID.  
                adapterTxGuid = Guid.NewGuid();  
  
                //Invoke SendIdoc on the client to send the IDOC to the SAP system.  
                idocClient.SendIdoc(idocData, ref adapterTxGuid);  
  
                // The AutoConfirmSentIdocs binding property is set to true, so there is no need to  
                // confirm the IDOC. If this property is not set to true, you must call the   
                // RfcConfirmTransID method of a TrfcClient with adapterTxGuid to   
                // confirm the transaction on the SAP system.   
  
                // Get SAP tx id from GUID  
                sapTxId = SAPAdapterUtilities.ConvertGuidToTid((Guid) adapterTxGuid);  
  
                Console.WriteLine("IDOC sent");  
                Console.WriteLine("The SAP Transaction Id is : " + sapTxId);  
  
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
                // Close the IDOC client  
                if (idocClient != null)  
                {  
                    if (idocClient.State == CommunicationState.Opened)  
                        idocClient.Close();  
                    else  
                        idocClient.Abort();  
                }  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="564ef-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="564ef-174">See Also</span></span>  
[<span data-ttu-id="564ef-175">Desarrollar aplicaciones con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="564ef-175">Develop applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)