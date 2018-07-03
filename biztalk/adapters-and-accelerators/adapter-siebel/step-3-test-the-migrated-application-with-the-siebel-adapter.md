---
title: 'Paso 3: Probar la aplicación migrado con el adaptador de Siebel | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 651ee1b2-52da-497a-84a5-67f1436cc3e6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1669ed459dffbd8746936ffa1ba8c23677173e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989589"
---
# <a name="step-3-test-the-migrated-application-with-the-siebel-adapter"></a>Paso 3: Probar la aplicación migrado con el adaptador de Siebel
![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, probará la aplicación migrada mediante la realización de una operación de inserción en el componente de negocio de la cuenta. Para ello, coloque un mensaje de solicitud que se ajusta al esquema generado con el adaptador de Siebel vPrev.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
- Configurar la aplicación de BizTalk mediante la asignación de los puertos lógicos de la orquestación de BizTalk a puertos físicos en la consola de administración de BizTalk Server.  
  
- Configurar la aplicación de BizTalk para utilizar el puerto de envío WCF-Custom basado en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
### <a name="to-test-the-migrated-application"></a>Para probar la aplicación migrada  
  
1. En la carpeta Siebel_BussComp_Migration, copie el mensaje de solicitud AccountInsert.xml. Este mensaje de solicitud cumple el esquema generado por el adaptador de Siebel vPrev. Mediante la asignación de salida, el WCF-Custom enviar puerto convierte esto para ajustarse al esquema basado en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y lo envía al sistema Siebel.  
  
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
  
2. Pegar el mensaje de solicitud a la carpeta que se asigna al archivo de la ubicación de recepción.  
  
3. La orquestación consume el mensaje de solicitud y lo envía al sistema Siebel. Se recibe la respuesta en el sistema Siebel en el esquema que se ajusta con el esquema de basada en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Mediante la asignación de entrada, el WCF-Custom enviar puerto convierte esto al esquema para el adaptador de Siebel vPrev. La respuesta en el sistema Siebel se guarda en la otra ubicación de archivo definida como parte de la orquestación. La respuesta para el mensaje de solicitud anterior es:  
  
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