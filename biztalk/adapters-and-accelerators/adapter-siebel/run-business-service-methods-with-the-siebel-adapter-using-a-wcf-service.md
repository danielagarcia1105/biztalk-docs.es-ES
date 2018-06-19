---
title: Invocar métodos de servicio empresarial con el adaptador de Siebel mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, invoking business service methods
- business service methods, invoking by using the WCF service model
ms.assetid: b41cf944-efdc-453f-824b-70581e7143e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27eafcbfadc353e8aed9430e2d1bed3ef9e16017
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222180"
---
# <a name="invoke-business-service-methods-with-the-siebel-adapter-using-the-wcf-service-model"></a>Invocar métodos de servicio empresarial con el adaptador de Siebel mediante el modelo de servicio de WCF
Puede crear a un cliente WCF que métodos de destinos de servicios empresariales de Siebel. A continuación, puede usar al cliente de WCF para invocar estos métodos en el sistema Siebel. Servicios empresariales de Siebel aparecen bajo el nodo de servicios para la empresa en el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Los métodos expuestos por cada servicio de negocio aparecen bajo el nodo correspondiente a ese servicio. Puede seguir los pasos descritos en [información general sobre el modelo de servicio de WCF con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md) para generar un cliente WCF para un servicio empresarial y usarlo para invocar métodos del servicio.  
  
 El código siguiente usa un cliente de WCF para invocar la **Execute** método del servicio de negocio de marca de tiempo. La marca de tiempo, que se devuelve en la hora local del servidor de Siebel, a continuación, se escribe en la consola. El cliente de WCF en este ejemplo se inicia desde un archivo de configuración generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener un ejemplo de un archivo de configuración generado, consulte [configurar un cliente de WCF para un sistema Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md).  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using microsoft.lobservices.siebel._2007._03.BusinessServices.TimeStamp;  
  
namespace Business_Service  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BusinessServices_TimeStamp_OperationClient client = null;  
  
            try  
            {  
                client =  
                     new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
                client.ClientCredentials.UserName.UserName = "YourUserName";  
                client.ClientCredentials.UserName.Password = "YourPassword";  
                client.Open();  
  
                ExecuteResponseRecord er = client.Execute();  
                Console.WriteLine(er.Time);  
  
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
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Siebel mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)