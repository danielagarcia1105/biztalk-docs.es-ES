---
title: "Paso 3: Probar la aplicación migrados que utiliza el adaptador de SQL | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929ce2f3-94ed-4e12-b629-e229769f825a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2eaf57c08157ffb9785f591016793c4c416704bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-migrated-application-that-uses-the-sql-adapter"></a>Paso 3: Probar la aplicación migrados que utiliza el adaptador de SQL
![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, probará la aplicación migrada realizando una operación de inserción en la tabla Customer. Para ello, se coloca un mensaje de solicitud que se ajusta al esquema generado mediante la vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Configurar la aplicación de BizTalk mediante la asignación de los puertos lógicos de la orquestación de BizTalk a puertos físicos en la consola de administración de BizTalk Server.  
  
-   Configurar la aplicación de BizTalk para utilizar el puerto de envío WCF-Custom para basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
### <a name="to-test-the-migrated-application"></a>Para probar la aplicación migrada  
  
1.  Crear una solicitud de XML que se ajusta al esquema generado por el vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Mediante la asignación de salida, WCF-Custom enviarla convierte de puerto para que se ajuste al esquema de basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y lo envía a la base de datos de SQL Server.  
  
    ```  
    <Insert xmlns="http://SQLInsert">  
      <sync>  
        <after>  
          <CustomerTable Name="John" />  
        </after>  
      </sync>  
    </Insert>  
    ```  
  
2.  Pegar el mensaje de solicitud a la carpeta que se asigna al archivo de la ubicación de recepción.  
  
3.  La orquestación consume el mensaje de solicitud y lo envía a la base de datos de SQL Server. Se recibe la respuesta de la base de datos de SQL Server en el esquema que se ajusta al esquema de basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Mediante la asignación de entrada, WCF-Custom enviarla puerto convierte el esquema para el vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. La respuesta de la base de datos de SQL Server se guarda en la otra ubicación de archivo definida como parte de la orquestación. La respuesta para el mensaje de solicitud anterior es:  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <InsertResponse xmlns="http://SQLInsert">  
      <Success>  
        <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">101</long>   
      </Success>  
    </InsertResponse>  
    ```  
  
     En la respuesta anterior, "101" es el valor de la columna de identidad insertado en la tabla Customer.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Migrar proyectos de BizTalk para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)