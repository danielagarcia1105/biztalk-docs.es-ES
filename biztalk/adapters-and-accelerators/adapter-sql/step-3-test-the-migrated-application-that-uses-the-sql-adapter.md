---
title: 'Paso 3: Probar la aplicación migrados que utiliza el adaptador de SQL | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 929ce2f3-94ed-4e12-b629-e229769f825a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c2487c6bdf05ae926b8bb962ed9dae6c770298e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973293"
---
# <a name="step-3-test-the-migrated-application-that-uses-the-sql-adapter"></a>Paso 3: Probar la aplicación migrados que utiliza el adaptador de SQL
![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, probará la aplicación migrada mediante la realización de una operación de inserción en la tabla Customer. Para ello, se quita un mensaje de solicitud que se ajusta al esquema generado con el vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
  
- Configurar la aplicación de BizTalk mediante la asignación de los puertos lógicos de la orquestación de BizTalk a puertos físicos en la consola de administración de BizTalk Server.  
  
- Configurar la aplicación de BizTalk para utilizar el puerto de envío WCF-Custom basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
### <a name="to-test-the-migrated-application"></a>Para probar la aplicación migrada  
  
1. Crear una solicitud de XML que cumple el esquema generado por el vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Mediante la asignación de salida, el WCF-Custom enviar puerto convierte esto para ajustarse al esquema basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y lo envía a la base de datos de SQL Server.  
  
   ```  
   <Insert xmlns="http://SQLInsert">  
     <sync>  
       <after>  
         <CustomerTable Name="John" />  
       </after>  
     </sync>  
   </Insert>  
   ```  
  
2. Pegar el mensaje de solicitud a la carpeta que se asigna al archivo de la ubicación de recepción.  
  
3. La orquestación consume el mensaje de solicitud y lo envía a la base de datos de SQL Server. Se recibe la respuesta de la base de datos de SQL Server en el esquema que se ajusta al esquema de basada en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Mediante la asignación de entrada, el WCF-Custom enviar puerto convierte esto al esquema para el vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. La respuesta de la base de datos de SQL Server se guarda en la otra ubicación de archivo definida como parte de la orquestación. La respuesta para el mensaje de solicitud anterior es:  
  
   ```  
   <?xml version="1.0" encoding="utf-8" ?>   
   <InsertResponse xmlns="http://SQLInsert">  
     <Success>  
       <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">101</long>   
     </Success>  
   </InsertResponse>  
   ```  
  
    En la respuesta anterior, "101" es el valor de la columna de identidad insertado en la tabla Customer.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Migrar proyectos de BizTalk para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)