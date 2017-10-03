---
title: "Ejecutar una operación de ejecución en los servicios de negocios con Siebel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, execute business services using ADO.NET Provider
- performing operations, executing business services using ADO.NET Provider
ms.assetid: c8f7888f-72c6-4f20-b592-f233721fbddd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 644d915998e6c6e6f386d30021629f78dc109864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-an-execute-operation-on-business-services-with-siebel"></a>Ejecutar una operación de ejecución en los servicios de negocios con Siebel
Esta sección muestra cómo ejecutar una operación en un servicio de negocios de Siebel mediante el [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)].  
  
## <a name="executing-a-siebel-business-service"></a>Ejecutar un servicio de negocios de Siebel  
 Esta sección muestra cómo ejecutar operaciones en un servicio empresarial en el repositorio de Siebel.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Data.Common;  
using System.Data;  
using Microsoft.Adapters.SiebelDbProvider;  
  
namespace SiebelADOBS  
{  
 class Program  
  {  
   static void Main(string[] args)  
    {  
      try  
       {  
        SiebelProviderFactory factory = SiebelProviderFactory.Instance;  
        DbConnection connection = factory.CreateConnection();  
        connection.ConnectionString = "Username=SADMIN;Password=SADMIN;ServiceUri=172.23.115.223:2321;SiebelObjectManager=SSEObjMgr;SiebelEnterpriseServer=ent771;Language=enu;SiebelRepository=Siebel Repository";  
  
        connection.Open();  
        DbCommand command = connection.CreateCommand();  
        command.CommandText = "EXEC ExtractDataService.Echo @In, @InOut, @Out OUTPUT";  
  
        //Add @In  
        DbParameter param1 = command.CreateParameter();  
        param1.ParameterName = "@In";  
        param1.Direction = ParameterDirection.Input;  
        param1.Value = "SomethingElse";  
        command.Parameters.Add(param1);  
  
        //Add @InOut  
        DbParameter param2 = command.CreateParameter();  
        param2.ParameterName = "@InOut";  
        param2.Direction = ParameterDirection.InputOutput;  
        command.Parameters.Add(param2);  
  
        //Add @Out  
        DbParameter outParam = command.CreateParameter();  
        outParam.ParameterName = "@Out";  
        outParam.Direction = ParameterDirection.Output;  
        command.Parameters.Add(outParam);  
  
        DbDataReader dbReader = command.ExecuteReader();  
  
        Console.WriteLine("Param2: " + param2.Value);  
        Console.WriteLine("OutParam: " + outParam.Value);  
  
        Console.WriteLine("Press any key...");  
        Console.ReadLine();  
      }  
     catch (Exception exp) { Console.WriteLine(exp.Message); }  
      }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)   
 [Ejecute una consulta SELECT en componentes empresariales con Siebel](../../adapters-and-accelerators/adapter-siebel/run-a-select-query-on-business-components-with-siebel.md)