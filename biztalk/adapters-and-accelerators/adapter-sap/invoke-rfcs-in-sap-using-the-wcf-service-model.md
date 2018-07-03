---
title: Invocar RFC de SAP mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- invoking RFCs, using the WCF service model
- WCF service model, invoking RFCs
ms.assetid: 06a373e2-5d16-4480-81ec-611bd0b9749c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991fec074369e774a9eef9ab2ae34f10436c6a4f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973701"
---
# <a name="invoke-rfcs-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="dd46c-102">Invocar RFC de SAP mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="dd46c-102">Invoke RFCs in SAP using the WCF Service Model</span></span>
<span data-ttu-id="dd46c-103">El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] presenta las solicitudes de cambio en el sistema SAP como operaciones que se pueden invocar un programa cliente.</span><span class="sxs-lookup"><span data-stu-id="dd46c-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] surfaces RFCs on the SAP system as operations that can be invoked by a client program.</span></span> <span data-ttu-id="dd46c-104">En el modelo de servicio WCF, estas operaciones se invocan como métodos de una clase de cliente WCF generado.</span><span class="sxs-lookup"><span data-stu-id="dd46c-104">In the WCF service model, these operations are invoked as methods of a generated WCF client class.</span></span> <span data-ttu-id="dd46c-105">Puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF que contiene métodos para cada solicitud de cambio que se desea invocar en el código.</span><span class="sxs-lookup"><span data-stu-id="dd46c-105">You can use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class that contains methods for each RFC that you want to invoke in your code.</span></span> <span data-ttu-id="dd46c-106">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera tipos de .NET para encapsular los tipos de datos y parámetros que se usan con cada solicitud de cambio.</span><span class="sxs-lookup"><span data-stu-id="dd46c-106">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates .NET types to encapsulate the parameters and data types that are used by each RFC.</span></span> <span data-ttu-id="dd46c-107">A continuación, puede crear una instancia de esta clase de cliente WCF y llamar a sus métodos para invocar el destino RFC.</span><span class="sxs-lookup"><span data-stu-id="dd46c-107">You can then create an instance of this WCF client class and call its methods to invoke the target RFCs.</span></span>  
  
 <span data-ttu-id="dd46c-108">Las secciones siguientes muestran cómo invocar RFC en el sistema SAP mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd46c-108">The following sections show you how to invoke RFCs on the SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="dd46c-109">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="dd46c-109">The WCF Client Class</span></span>  
 <span data-ttu-id="dd46c-110">La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone todas las operaciones de RFC en un contrato de servicio único, "Rfc".</span><span class="sxs-lookup"><span data-stu-id="dd46c-110">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces all RFC operations under a single service contract, "Rfc".</span></span> <span data-ttu-id="dd46c-111">Esto significa que una sola clase de cliente WCF, **RfcClient**, se crea para todas las operaciones de RFC que se desean invocar.</span><span class="sxs-lookup"><span data-stu-id="dd46c-111">This means that a single WCF client class, **RfcClient**, is created for all of the RFC operations that you want to invoke.</span></span> <span data-ttu-id="dd46c-112">Cada destino RFC se representa como un método de esta clase.</span><span class="sxs-lookup"><span data-stu-id="dd46c-112">Each target RFC is represented as a method of this class.</span></span> <span data-ttu-id="dd46c-113">En cada método:</span><span class="sxs-lookup"><span data-stu-id="dd46c-113">In each method:</span></span>  
  
- <span data-ttu-id="dd46c-114">Exportación de los parámetros SAP se exponen como **out** parámetros</span><span class="sxs-lookup"><span data-stu-id="dd46c-114">SAP export parameters are surfaced as **out** parameters</span></span>  
  
- <span data-ttu-id="dd46c-115">Los parámetros de cambio de SAP se exponen como **ref** parámetros.</span><span class="sxs-lookup"><span data-stu-id="dd46c-115">SAP changing parameters are surfaced as **ref** parameters.</span></span>  
  
- <span data-ttu-id="dd46c-116">Tipos complejos de SAP como estructuras se exponen como clases .NET con propiedades que corresponden a los campos del tipo SAP.</span><span class="sxs-lookup"><span data-stu-id="dd46c-116">Complex SAP types such as structures are surfaced as .NET classes with properties that correspond to the fields of the SAP type.</span></span> <span data-ttu-id="dd46c-117">Estas clases se definen en el espacio de nombres siguiente: microsoft.lobservices.sap._2007._03.Types.Rfc.</span><span class="sxs-lookup"><span data-stu-id="dd46c-117">These classes are defined in the following namespace: microsoft.lobservices.sap._2007._03.Types.Rfc.</span></span>  
  
  <span data-ttu-id="dd46c-118">El código siguiente muestra parte de la **RfcClient** clase y el método que invoca SD_RFC_CUSTOMER_GET en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="dd46c-118">The following code shows part of the **RfcClient** class and the method that invokes SD_RFC_CUSTOMER_GET on the SAP system.</span></span>  
  
```  
 [System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class RfcClient : System.ServiceModel.ClientBase<Rfc>, Rfc {  
  
    ...  
  
    /// <summary>The metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="KUNNR">Customer number</param>  
    /// <param name="NAME1">Name of the customer</param>  
    /// <param name="CUSTOMER_T">Table of the selected customers</param>  
    /// <returns></returns>  
    public void SD_RFC_CUSTOMER_GET(string KUNNR, string NAME1, ref microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] CUSTOMER_T) {...}  
}  
```  
  
## <a name="how-to-create-an-rfc-client-application"></a><span data-ttu-id="dd46c-119">Cómo crear una aplicación de cliente RFC</span><span class="sxs-lookup"><span data-stu-id="dd46c-119">How to Create an RFC Client Application</span></span>  
 <span data-ttu-id="dd46c-120">Para crear una aplicación de cliente RFC, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="dd46c-120">To create an RFC client application, perform the following steps.</span></span>  
  
#### <a name="to-create-an-rfc-client-application"></a><span data-ttu-id="dd46c-121">Para crear una aplicación de cliente RFC</span><span class="sxs-lookup"><span data-stu-id="dd46c-121">To create an RFC client application</span></span>  
  
1. <span data-ttu-id="dd46c-122">Generar un **RfcClient** clase.</span><span class="sxs-lookup"><span data-stu-id="dd46c-122">Generate an **RfcClient** class.</span></span> <span data-ttu-id="dd46c-123">Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutil.exe) para generar un **RfcClient** clase que tiene como destino las RFC con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="dd46c-123">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate an **RfcClient** class that targets the RFCs with which you want to work.</span></span> <span data-ttu-id="dd46c-124">Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="dd46c-124">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF Service Contract for SAP Solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2. <span data-ttu-id="dd46c-125">Cree una instancia de la **RfcClient** clase generado en el paso 1, y especificar un enlace de cliente.</span><span class="sxs-lookup"><span data-stu-id="dd46c-125">Create an instance of the **RfcClient** class generated in step 1, and specify a client binding.</span></span> <span data-ttu-id="dd46c-126">Especificar un enlace de cliente implica especificar el enlace y el punto de conexión de direcciones que el **RfcClient** va a usar.</span><span class="sxs-lookup"><span data-stu-id="dd46c-126">Specifying a client binding involves specifying the binding and endpoint address that the **RfcClient** will use.</span></span> <span data-ttu-id="dd46c-127">Puede hacerlo imperativamente en código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="dd46c-127">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="dd46c-128">Para obtener más información sobre cómo especificar un enlace de cliente, consulte [configurar un enlace de cliente para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="dd46c-128">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="dd46c-129">El siguiente código inicializa el **RfcClient** de configuración y establece las credenciales para el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="dd46c-129">The following code initializes the **RfcClient** from configuration and sets the credentials for the SAP system.</span></span>  
  
   ```  
   RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
   rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
   rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. <span data-ttu-id="dd46c-130">Abra al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="dd46c-130">Open the WCF client.</span></span>  
  
   ```  
   rfcClient.Open();  
   ```  
  
4. <span data-ttu-id="dd46c-131">Invocar métodos en el **RfcClient** creado en el paso 2 para realizar operaciones en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="dd46c-131">Invoke methods on the **RfcClient** created in step 2 to perform operations on the SAP system.</span></span> <span data-ttu-id="dd46c-132">El código siguiente invoca el **SD_RFC_CUSTOMER_GET** método de la **RfcClient** para invocar la solicitud de cambio en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="dd46c-132">The following code invokes the **SD_RFC_CUSTOMER_GET** method of the **RfcClient** to invoke the RFC on the SAP system.</span></span>  
  
   ```  
   microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
       new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
   rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
   ```  
  
5. <span data-ttu-id="dd46c-133">Cierre al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="dd46c-133">Close the WCF client.</span></span>  
  
   ```  
   rfcClient.Close();   
   ```  
  
### <a name="example"></a><span data-ttu-id="dd46c-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd46c-134">Example</span></span>  
 <span data-ttu-id="dd46c-135">El siguiente es un ejemplo de código completo que se invoca SD_RFC_CUSTOMER_GET para devolver una lista de clientes con nombres que comienzan por "AB" y, a continuación, escribe el nombre e identificador de cada cliente en la consola.</span><span class="sxs-lookup"><span data-stu-id="dd46c-135">The following is a complete code example that invokes SD_RFC_CUSTOMER_GET to return a list of customers with names that begin with "AB" and then writes the name and ID for each customer to the console.</span></span> <span data-ttu-id="dd46c-136">Este ejemplo se crea el **RfcClient** dentro de un **mediante** instrucción.</span><span class="sxs-lookup"><span data-stu-id="dd46c-136">This example creates the **RfcClient** inside a **using** statement.</span></span> <span data-ttu-id="dd46c-137">No es necesario cerrar explícitamente la **RfcClient**; se cerrará cuando la ruta de acceso de ejecución cierra el contexto.</span><span class="sxs-lookup"><span data-stu-id="dd46c-137">There is no need to explicitly close the **RfcClient**; it will be closed when the execution path exits the context.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.SAP;  
  
namespace SapRfcClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                // Create client from configuration  
                using (RfcClient rfcClient = new RfcClient("SAPBinding_Rfc"))  
                {  
  
                    rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
                    rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                    // Open client  
                    rfcClient.Open();  
  
                    microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers = new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
                    // Invoke SD_RFC_CUSTOMER_GET  
                    rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
  
                    // Write the results to the console  
                    foreach (microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST customer in customers)  
                    {  
                        Console.WriteLine("Customer Name = " + customer.NAME1);  
                        Console.WriteLine("         Id   = " + customer.KUNNR);  
                        Console.WriteLine();  
                    }  
                }  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
                if (ex.InnerException != null)  
                    Console.WriteLine("Inner exception is :" + ex.InnerException);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd46c-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd46c-138">See Also</span></span>  
<span data-ttu-id="dd46c-139">[Desarrollar aplicaciones mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="dd46c-139">[Develop applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 [<span data-ttu-id="dd46c-140">Esquemas de mensaje para operaciones de RFC</span><span class="sxs-lookup"><span data-stu-id="dd46c-140">Message Schemas for RFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)