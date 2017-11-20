---
title: Invocar RFC en SAP mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- invoking RFCs, using the WCF service model
- WCF service model, invoking RFCs
ms.assetid: 06a373e2-5d16-4480-81ec-611bd0b9749c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8a18e9ae4990ecd5e85c57fc86919f239d51cbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-rfcs-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="9781e-102">Invocar RFC en SAP mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="9781e-102">Invoke RFCs in SAP using the WCF Service Model</span></span>
<span data-ttu-id="9781e-103">El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] presenta las solicitudes de cambio en el sistema SAP como operaciones que se pueden invocar mediante un programa cliente.</span><span class="sxs-lookup"><span data-stu-id="9781e-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] surfaces RFCs on the SAP system as operations that can be invoked by a client program.</span></span> <span data-ttu-id="9781e-104">En el modelo de servicio WCF, estas operaciones se invocan como métodos de una clase de cliente WCF generada.</span><span class="sxs-lookup"><span data-stu-id="9781e-104">In the WCF service model, these operations are invoked as methods of a generated WCF client class.</span></span> <span data-ttu-id="9781e-105">Puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF que contiene métodos para cada solicitud de cambio que desea invocar en el código.</span><span class="sxs-lookup"><span data-stu-id="9781e-105">You can use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class that contains methods for each RFC that you want to invoke in your code.</span></span> <span data-ttu-id="9781e-106">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera tipos de .NET para encapsular los parámetros y tipos de datos que se utilizan con cada solicitud de cambio.</span><span class="sxs-lookup"><span data-stu-id="9781e-106">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates .NET types to encapsulate the parameters and data types that are used by each RFC.</span></span> <span data-ttu-id="9781e-107">A continuación, puede crear una instancia de esta clase de cliente WCF y llamar a sus métodos para invocar el destino RFC.</span><span class="sxs-lookup"><span data-stu-id="9781e-107">You can then create an instance of this WCF client class and call its methods to invoke the target RFCs.</span></span>  
  
 <span data-ttu-id="9781e-108">Las secciones siguientes muestran cómo invocar las solicitudes de cambio en el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9781e-108">The following sections show you how to invoke RFCs on the SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="9781e-109">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="9781e-109">The WCF Client Class</span></span>  
 <span data-ttu-id="9781e-110">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies todas las operaciones de RFC bajo un contrato de servicio único, "Rfc".</span><span class="sxs-lookup"><span data-stu-id="9781e-110">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces all RFC operations under a single service contract, "Rfc".</span></span> <span data-ttu-id="9781e-111">Esto significa que una sola clase de cliente WCF, **RfcClient**, se crea para todas las operaciones de RFC que se desea invocar.</span><span class="sxs-lookup"><span data-stu-id="9781e-111">This means that a single WCF client class, **RfcClient**, is created for all of the RFC operations that you want to invoke.</span></span> <span data-ttu-id="9781e-112">Cada destino RFC se representa como un método de esta clase.</span><span class="sxs-lookup"><span data-stu-id="9781e-112">Each target RFC is represented as a method of this class.</span></span> <span data-ttu-id="9781e-113">En cada método:</span><span class="sxs-lookup"><span data-stu-id="9781e-113">In each method:</span></span>  
  
-   <span data-ttu-id="9781e-114">Los parámetros de exportación SAP aparecen como **out** parámetros</span><span class="sxs-lookup"><span data-stu-id="9781e-114">SAP export parameters are surfaced as **out** parameters</span></span>  
  
-   <span data-ttu-id="9781e-115">SAP cambiantes parámetros aparecen como **ref** parámetros.</span><span class="sxs-lookup"><span data-stu-id="9781e-115">SAP changing parameters are surfaced as **ref** parameters.</span></span>  
  
-   <span data-ttu-id="9781e-116">Tipos complejos de SAP como estructuras aparecen como clases de .NET con propiedades que corresponden a los campos del tipo SAP.</span><span class="sxs-lookup"><span data-stu-id="9781e-116">Complex SAP types such as structures are surfaced as .NET classes with properties that correspond to the fields of the SAP type.</span></span> <span data-ttu-id="9781e-117">Estas clases se definen en el espacio de nombres siguiente: microsoft.lobservices.sap._2007._03.Types.Rfc.</span><span class="sxs-lookup"><span data-stu-id="9781e-117">These classes are defined in the following namespace: microsoft.lobservices.sap._2007._03.Types.Rfc.</span></span>  
  
 <span data-ttu-id="9781e-118">El código siguiente muestra parte de la **RfcClient** clase y el método que invoca SD_RFC_CUSTOMER_GET en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="9781e-118">The following code shows part of the **RfcClient** class and the method that invokes SD_RFC_CUSTOMER_GET on the SAP system.</span></span>  
  
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
  
## <a name="how-to-create-an-rfc-client-application"></a><span data-ttu-id="9781e-119">Cómo crear una aplicación de cliente RFC</span><span class="sxs-lookup"><span data-stu-id="9781e-119">How to Create an RFC Client Application</span></span>  
 <span data-ttu-id="9781e-120">Para crear una aplicación de cliente RFC, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="9781e-120">To create an RFC client application, perform the following steps.</span></span>  
  
#### <a name="to-create-an-rfc-client-application"></a><span data-ttu-id="9781e-121">Para crear una aplicación de cliente RFC</span><span class="sxs-lookup"><span data-stu-id="9781e-121">To create an RFC client application</span></span>  
  
1.  <span data-ttu-id="9781e-122">Generar un **RfcClient** clase.</span><span class="sxs-lookup"><span data-stu-id="9781e-122">Generate an **RfcClient** class.</span></span> <span data-ttu-id="9781e-123">Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos de herramienta de utilidad ServiceModel (svcutil.exe) para generar un **RfcClient** clase que tenga como destino las RFC con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="9781e-123">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate an **RfcClient** class that targets the RFCs with which you want to work.</span></span> <span data-ttu-id="9781e-124">Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio de WCF para los artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="9781e-124">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF Service Contract for SAP Solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="9781e-125">Cree una instancia de la **RfcClient** clase generado en el paso 1, y especificar un enlace del cliente.</span><span class="sxs-lookup"><span data-stu-id="9781e-125">Create an instance of the **RfcClient** class generated in step 1, and specify a client binding.</span></span> <span data-ttu-id="9781e-126">Especificación de un enlace de cliente implica especificar el enlace y el punto de conexión de dirección que el **RfcClient** va a usar.</span><span class="sxs-lookup"><span data-stu-id="9781e-126">Specifying a client binding involves specifying the binding and endpoint address that the **RfcClient** will use.</span></span> <span data-ttu-id="9781e-127">Puede hacerlo imperativamente en código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="9781e-127">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="9781e-128">Para obtener más información sobre cómo especificar un enlace del cliente, consulte [configurar un enlace de cliente para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="9781e-128">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="9781e-129">El siguiente código inicializa el **RfcClient** de configuración y establece las credenciales para el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="9781e-129">The following code initializes the **RfcClient** from configuration and sets the credentials for the SAP system.</span></span>  
  
    ```  
    RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
    rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
    rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  <span data-ttu-id="9781e-130">Abra al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="9781e-130">Open the WCF client.</span></span>  
  
    ```  
    rfcClient.Open();  
    ```  
  
4.  <span data-ttu-id="9781e-131">Invocar métodos en el **RfcClient** creado en el paso 2 para realizar operaciones en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="9781e-131">Invoke methods on the **RfcClient** created in step 2 to perform operations on the SAP system.</span></span> <span data-ttu-id="9781e-132">El código siguiente, se invoca el **SD_RFC_CUSTOMER_GET** método de la **RfcClient** para invocar la solicitud de cambio en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="9781e-132">The following code invokes the **SD_RFC_CUSTOMER_GET** method of the **RfcClient** to invoke the RFC on the SAP system.</span></span>  
  
    ```  
    microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
        new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
    rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
    ```  
  
5.  <span data-ttu-id="9781e-133">Cierre al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="9781e-133">Close the WCF client.</span></span>  
  
    ```  
    rfcClient.Close();   
    ```  
  
### <a name="example"></a><span data-ttu-id="9781e-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9781e-134">Example</span></span>  
 <span data-ttu-id="9781e-135">El siguiente es un ejemplo de código completo que invoca SD_RFC_CUSTOMER_GET para devolver una lista de los clientes que tengan nombres que comienzan por "AB" y, a continuación, escribe el nombre y el identificador de cada cliente en la consola.</span><span class="sxs-lookup"><span data-stu-id="9781e-135">The following is a complete code example that invokes SD_RFC_CUSTOMER_GET to return a list of customers with names that begin with "AB" and then writes the name and ID for each customer to the console.</span></span> <span data-ttu-id="9781e-136">Este ejemplo se crea el **RfcClient** dentro de un **con** instrucción.</span><span class="sxs-lookup"><span data-stu-id="9781e-136">This example creates the **RfcClient** inside a **using** statement.</span></span> <span data-ttu-id="9781e-137">No es necesario cerrar explícitamente el **RfcClient**; se cerrarán cuando salga de la ruta de acceso de ejecución del contexto.</span><span class="sxs-lookup"><span data-stu-id="9781e-137">There is no need to explicitly close the **RfcClient**; it will be closed when the execution path exits the context.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9781e-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="9781e-138">See Also</span></span>  
<span data-ttu-id="9781e-139">[Desarrollar aplicaciones mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="9781e-139">[Develop applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 [<span data-ttu-id="9781e-140">Esquemas de mensaje para las operaciones de RFC</span><span class="sxs-lookup"><span data-stu-id="9781e-140">Message Schemas for RFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)