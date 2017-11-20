---
title: Ejecute las operaciones en los componentes empresariales con el adaptador de Siebel mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations on business components
- how to, perform operations using the proxy
- business components, performing operations by using the WCF service model
- performing operations, using the proxy
ms.assetid: 7a5fdc95-6159-4f43-aac5-4e2f84e9138b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99ac40efda9ed8c27fb5ac5fedfbe782b9a4f645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-business-components-with-the-siebel-adapter-using-the-wcf-service-model"></a><span data-ttu-id="7c1ee-102">Ejecute las operaciones en los componentes empresariales con el adaptador de Siebel mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="7c1ee-102">Run Operations on Business Components with the Siebel adapter using the WCF Service Model</span></span>
<span data-ttu-id="7c1ee-103">Puede crear a un cliente WCF que tiene como destino un componente de negocio de Siebel.</span><span class="sxs-lookup"><span data-stu-id="7c1ee-103">You can create a WCF client that targets a Siebel business component.</span></span> <span data-ttu-id="7c1ee-104">A continuación, puede usar al cliente de WCF para realizar la inserción, actualización, consulta, Delete, asociar, desasócielo y operaciones de consulta de registros secundarios en el componente empresarial en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="7c1ee-104">You can then use the WCF client to perform Insert, Update, Query, Delete, Associate, Dissociate, and child record query operations on the business component on the Siebel system.</span></span> <span data-ttu-id="7c1ee-105">Objetos de negocios de Siebel aparecen bajo el nodo objetos de negocios en el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c1ee-105">Siebel business objects are surfaced under the Business Objects node in the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="7c1ee-106">Los componentes empresariales que componen cada objeto de negocios aparecen bajo el nodo correspondiente a ese objeto.</span><span class="sxs-lookup"><span data-stu-id="7c1ee-106">The business components that compose each business object are surfaced under the node corresponding to that object.</span></span> <span data-ttu-id="7c1ee-107">Puede seguir los pasos descritos en [información general sobre el modelo de servicio de WCF con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md) para generar un cliente WCF para un componente empresarial que tiene como destino las operaciones específicas y usar el cliente para invocar estas operaciones en la empresa componente.</span><span class="sxs-lookup"><span data-stu-id="7c1ee-107">You can follow the steps in [Overview of the WCF Service Model with the Siebel Adapter](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md) to generate a WCF client for a business component that targets specific operations and use the client to invoke these operations on the business component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c1ee-108">Este tema proporciona información acerca de cómo realizar operaciones básicas (Insert, Update, consulta, Delete) en los componentes empresariales.</span><span class="sxs-lookup"><span data-stu-id="7c1ee-108">This topic provides information about performing basic operations (Insert, Update, Query, Delete) on business components.</span></span> <span data-ttu-id="7c1ee-109">Para obtener más información acerca de cómo realizar la asociación, desasócielo y operaciones de consulta de registros secundarios, vea [ejecutar operaciones en los componentes empresariales con campos de MVG mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)</span><span class="sxs-lookup"><span data-stu-id="7c1ee-109">For more information about performing Associate, Dissociate, and child record query operations, see [Run Operations on Business Components with MVG Fields by Using the WCF Service Model](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)</span></span>  
  
 <span data-ttu-id="7c1ee-110">El código siguiente utiliza a un cliente WCF para realizar operaciones Insert, Update y Delete en un registro del componente empresarial de cuenta del objeto de negocios de cuenta.</span><span class="sxs-lookup"><span data-stu-id="7c1ee-110">The following code uses a WCF client to perform Insert, Update, and Delete operations on a record in the Account business component of the Account business object.</span></span> <span data-ttu-id="7c1ee-111">Pregunte en cada operación, se realiza una operación de consulta para comprobar los resultados.</span><span class="sxs-lookup"><span data-stu-id="7c1ee-111">Between each operation, a Query operation is performed to verify the results.</span></span> <span data-ttu-id="7c1ee-112">El cliente de WCF en este ejemplo se inicia desde un archivo de configuración generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c1ee-112">The WCF client in this example is initialized from a configuration file that is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="7c1ee-113">Para obtener un ejemplo de un archivo de configuración generado, consulte [configurar un cliente de WCF para un sistema Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md).</span><span class="sxs-lookup"><span data-stu-id="7c1ee-113">For an example of a generated configuration file, see [Configure a WCF Client for a Siebel System](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md).</span></span>  
  
```  
  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using microsoft.lobservices.siebel._2007._03.BusinessObjects;  
using microsoft.lobservices.siebel._2007._03;  
  
namespace Business_Component_Operations  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BusinessObjects_Account_Account_OperationClient client = null;  
  
            try  
            {  
  
                client = new BusinessObjects_Account_Account_OperationClient("SiebelBinding_BusinessObjects_Account_Account_Operation");  
                client.ClientCredentials.UserName.UserName = "YourUserName";  
                client.ClientCredentials.UserName.Password = "YourPassword";  
  
                Console.WriteLine("Opening connection to " + client.Endpoint.Address.Uri.Host);  
                client.Open();  
                AccountInsertRecord[] air = new AccountInsertRecord[1];  
                air[0] = new AccountInsertRecord();  
                Random r = new Random();  
                int count = r.Next();  
  
                air[0].Name = "Anil" + count.ToString();  
                Console.WriteLine("Inserting " + air[0].Name + " ...");  
                client.Insert(air);  
  
                //Query for the record.  
                Console.WriteLine("Querying to check inserted record ...");  
                AccountQueryInputRecord aqir = new AccountQueryInputRecord();  
                short viewmode = new short(); viewmode = 3;  
                string[] fields = new string[2];  
                fields[0] = "Name";  
                fields[1] = "Id";  
                aqir.QueryFields = fields;  
                aqir.SearchExpr = "[Name] LIKE \"Anil*\"";  
                AccountQueryRecord[] aqr = client.Query(viewmode, aqir);  
                Console.WriteLine(aqr.Length + " records returned");  
                string[] ids = new string[1];  
                AccountUpdateRecord[] aur = new AccountUpdateRecord[1];  
                aur[0] = new AccountUpdateRecord();  
                foreach (AccountQueryRecord rec in aqr)  
                {  
                    Console.WriteLine("Name: " + rec.Name);  
                    Console.WriteLine("Id: " + rec.Id);  
                    Console.WriteLine("");  
                    ids[0] = rec.Id;  
                    aur[0].Name = rec.Name;  
                    aur[0].Id = rec.Id;  
                }  
  
                //Update it.  
  
                aur[0].Name = "Anil" + count.ToString() + "modified";  
                Console.WriteLine("Update the record to " + aur[0].Name + " ...");  
                client.Update(viewmode, aur);  
                //query again  
                aqr = client.Query(viewmode, aqir);  
                Console.WriteLine(aqr.Length + " records returned");  
                foreach (AccountQueryRecord rec in aqr)  
                {  
                    Console.WriteLine("Name: " + rec.Name);  
                    Console.WriteLine("Id: " + rec.Id);  
                    Console.WriteLine("");  
                }  
  
                //Delete it.  
                Console.WriteLine("Deleting record ...");  
                client.Delete(viewmode, ids, "");  
  
                //Check again.  
                Console.WriteLine("Check that " + aur[0].Name + " is not present");  
                aqr = client.Query(viewmode, aqir);  
  
                Console.WriteLine(aqr.Length + " records returned");  
                foreach (AccountQueryRecord rec in aqr)  
                {  
                    Console.WriteLine(rec.Name);  
                    Console.WriteLine(rec.Id);  
  
                }  
  
                // Wait for <RETURN> to end sample.  
                Console.WriteLine("\nHit <RETURN> to finish");  
                Console.ReadLine();  
  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine(e.Message);  
            }  
            finally  
            {  
                // Close the client.  
                if (client != null)  
                {  
                    if (client.State == CommunicationState.Opened)  
                        client.Close();  
                    else  
                        client.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c1ee-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c1ee-114">See Also</span></span>  
 [<span data-ttu-id="7c1ee-115">Desarrollar aplicaciones de Siebel mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="7c1ee-115">Develop Siebel Applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)