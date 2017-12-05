---
title: "Paso 3: Probar la aplicación con el adaptador de Siebel migrar | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 651ee1b2-52da-497a-84a5-67f1436cc3e6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d72799af5221319db2f5f3243e09d984e13399c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-test-the-migrated-application-with-the-siebel-adapter"></a>Paso 3: Probar la aplicación migran con el adaptador de Siebel
![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, probará la aplicación migrada realizando una operación de inserción en el componente de negocio de la cuenta. Para ello, se coloca un mensaje de solicitud que se ajusta al esquema generado con el adaptador de Siebel vPrev.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Configurar la aplicación de BizTalk mediante la asignación de los puertos lógicos de la orquestación de BizTalk a puertos físicos en la consola de administración de BizTalk Server.  
  
-   Configurar la aplicación de BizTalk para utilizar el puerto de envío WCF-Custom para basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
### <a name="to-test-the-migrated-application"></a>Para probar la aplicación migrada  
  
1.  En la carpeta Siebel_BussComp_Migration, copie el mensaje de solicitud de AccountInsert.xml. Este mensaje de solicitud cumple el esquema generado por el adaptador de Siebel vPrev. Mediante la asignación de salida, WCF-Custom enviarla convierte de puerto para que se ajuste al esquema de basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y lo envía al sistema Siebel.  
  
    ```  
    <Insert xmlns="http://schemas.microsoft.com/[Siebel://Business Objects/Account/Account]">  
      <AccountInsertRecordSet>  
        <AccountInsertRecord xmlns="http://schemas.microsoft.com/Business_Objects">  
          <Currency_Code>USD</Currency_Code>  
          <Customer_Account_Group>Sold-To-Party</Customer_Account_Group>  
          <Location>Location_1</Location>  
          <Main_Phone_Number>012345678</Main_Phone_Number>  
          <Name>John_Smith</Name>  
          <Party_Name>Party_Name_1</Party_Name>  
          <Primary_Address_Id></Primary_Address_Id>  
        </AccountInsertRecord>  
      </AccountInsertRecordSet>  
    </Insert>  
    ```  
  
2.  Pegar el mensaje de solicitud a la carpeta que se asigna al archivo de la ubicación de recepción.  
  
3.  La orquestación consume el mensaje de solicitud y lo envía al sistema Siebel. Se recibe la respuesta en el sistema Siebel en el esquema que se ajusta con el esquema de basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Mediante la asignación de entrada, WCF-Custom enviarla puerto convierte el esquema para el adaptador de Siebel vPrev. La respuesta en el sistema Siebel se guarda en la otra ubicación de archivo definida como parte de la orquestación. La respuesta para el mensaje de solicitud anterior es:  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ns0:InsertResponse xmlns:ns0="http://schemas.microsoft.com/[Siebel://Business Objects/Account/Account]" xmlns:exposed="http://schemas.microsoft.com" xmlns:Business_Objects="http://schemas.microsoft.com/Business_Objects">  
      <ns0:RowIDList>  
        <exposed:String>1-8EWWZ</exposed:String>  
      </ns0:RowIDList>  
    </ns0:InsertResponse>  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 2: Migración de proyectos de BizTalk de Siebel](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)