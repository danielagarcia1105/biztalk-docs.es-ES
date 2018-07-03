---
title: 'Paso 3: Probar la aplicación migrada al adaptador de base de datos de Oracle | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495efc4f-9d9e-450f-a03a-628bb54e658f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cdd41227b8c51eae6a1f1d2e11f3b3b792482f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970381"
---
# <a name="step-3-test-the-migrated-application-to-oracle-database-adapter"></a>Paso 3: Probar la aplicación migrada al adaptador de base de datos de Oracle
![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, probará la aplicación migrada mediante la realización de una operación de inserción en el SCOTT. Tabla CUSTOMER. Para ello, coloque un mensaje de solicitud que se ajusta al esquema generado con el adaptador de base de datos de Oracle vPrev.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
- Configurar la aplicación de BizTalk mediante la asignación de los puertos lógicos de la orquestación de BizTalk a puertos físicos en la consola de administración de BizTalk Server.  
  
- Configurar la aplicación de BizTalk para utilizar el puerto de envío WCF-Custom basado en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
### <a name="to-test-the-migrated-application"></a>Para probar la aplicación migrada  
  
1. En la carpeta Oracle_Migration, copie el mensaje de solicitud OracleInsert.xml. Este mensaje de solicitud cumple el esquema generado por el adaptador de base de datos de Oracle vPrev. Mediante la asignación de salida, el WCF-Custom enviar puerto convierte esto para ajustarse al esquema basado en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] y lo envía a la base de datos de Oracle.  
  
   ```  
   <ns0:Insert xmlns:ns0="http://schemas.microsoft.com/[OracleDb://ADAPTER/SCOTT/Tables/CUSTOMER]">  
     <ns0:Rows>  
       <ns0:InsertRecord>  
         <ns0:NAME>Customer_1</ns0:NAME>  
         <ns0:STREET>Street_1</ns0:STREET>  
         <ns0:CITY>City_1</ns0:CITY>  
       </ns0:InsertRecord>  
       <ns0:InsertRecord>  
         <ns0:NAME>Customer_2</ns0:NAME>  
         <ns0:STREET>Street_2</ns0:STREET>  
         <ns0:CITY>City_2</ns0:CITY>  
       </ns0:InsertRecord>  
     </ns0:Rows>  
   </ns0:Insert>  
   ```  
  
2. Pegar el mensaje de solicitud a la carpeta que se asigna al archivo de la ubicación de recepción.  
  
3. La orquestación consume el mensaje de solicitud y lo envía a la base de datos de Oracle. Se recibe la respuesta de la base de datos de Oracle en el esquema que se ajusta con el esquema de basada en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Mediante la asignación de entrada, el WCF-Custom enviar puerto convierte esto al esquema para el adaptador de base de datos de Oracle vPrev. La respuesta de la base de datos de Oracle se guarda en la otra ubicación de archivo definida como parte de la orquestación. La respuesta para el mensaje de solicitud anterior es:  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:InsertResponse xmlns:ns0="http://schemas.microsoft.com/[OracleDb://ADAPTER/SCOTT/Tables/CUSTOMER]"></ns0:InsertResponse>  
   ```  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Migración de proyectos de BizTalk](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)