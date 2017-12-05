---
title: "Paso 3: Probar la aplicación migrada al adaptador de la base de datos de Oracle | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 495efc4f-9d9e-450f-a03a-628bb54e658f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30b5871aee85316b9885bd1ec22f4118c83743d1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-test-the-migrated-application-to-oracle-database-adapter"></a>Paso 3: Probar la aplicación migrada al adaptador de la base de datos de Oracle
![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, probará la aplicación migrada realizando una operación de inserción en el SCOTT. Tabla de clientes. Para ello, se coloca un mensaje de solicitud que se ajusta al esquema generado con el adaptador de la base de datos de Oracle vPrev.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Configurar la aplicación de BizTalk mediante la asignación de los puertos lógicos de la orquestación de BizTalk a puertos físicos en la consola de administración de BizTalk Server.  
  
-   Configurar la aplicación de BizTalk para utilizar el puerto de envío WCF-Custom para basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
### <a name="to-test-the-migrated-application"></a>Para probar la aplicación migrada  
  
1.  En la carpeta Oracle_Migration, copie el mensaje de solicitud de OracleInsert.xml. Este mensaje de solicitud cumple el esquema generado por el adaptador de la base de datos de Oracle vPrev. Mediante la asignación de salida, WCF-Custom enviarla convierte de puerto para que se ajuste al esquema de basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] y lo envía a la base de datos de Oracle.  
  
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
  
2.  Pegar el mensaje de solicitud a la carpeta que se asigna al archivo de la ubicación de recepción.  
  
3.  La orquestación consume el mensaje de solicitud y lo envía a la base de datos de Oracle. Se recibe la respuesta de la base de datos de Oracle en el esquema que se ajusta con el esquema de basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Mediante la asignación de entrada, WCF-Custom enviarla puerto convierte el esquema para el adaptador de la base de datos de Oracle vPrev. La respuesta de la base de datos de Oracle se guarda en la otra ubicación de archivo definida como parte de la orquestación. La respuesta para el mensaje de solicitud anterior es:  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ns0:InsertResponse xmlns:ns0="http://schemas.microsoft.com/[OracleDb://ADAPTER/SCOTT/Tables/CUSTOMER]"></ns0:InsertResponse>  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Migrar proyectos de BizTalk](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)