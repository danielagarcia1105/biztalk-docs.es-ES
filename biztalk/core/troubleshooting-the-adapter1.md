---
title: "Solución de problemas de la < adaptador 1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, wildcard characters
- adapters [JD Edwards EnterpriseOne adapters], wildcard characters
- wildcard characters, JD Edwards EnterpriseOne adapters
ms.assetid: f5a55e52-039a-4aea-8251-b697fd061ddc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b77b42854a58d7fe8ffafd177e91f327a7f5e7e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-adapter"></a>Solucionar problemas del adaptador
Este tema contiene información para ayudarle a identificar y resolver los problemas que pueda tener mientras usa el adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne.  
  
## <a name="cannot-use-wildcards-in-send-port-properties"></a>No se pueden usar caracteres comodín en las propiedades de puerto de envío  
 El adaptador de BizTalk para JD Edwards EnterpriseOne no admite el uso de caracteres comodín en los siguientes campos de propiedades de puertos de envío:  
  
-   Nombre de usuario  
  
-   Entorno JDE  
  
-   Host  
  
-   Puerto  
  
-   Java_Home  
  
-   Archivos JAR de JDE  
  
-   Nombre del servidor de seguridad  
  
-   Conexión del nombre de servicio  
  
-   Data Source Name  
  
-   Propietario de la base de datos  
  
-   Nombre del servidor de bases de datos  
  
-   Tipo de base de datos  
  
-   Nombre de la base de datos física  
  
## <a name="connecting-to-oracle-database"></a>Conectando a la base de datos de Oracle  
 Cuando se usa la base de datos de Oracle con JD Edwards debe modificarse el archivo jdeinterop.ini. Mediante el Inicio de sesión único, la sección [JDBj-ORACLE] define la ubicación de tnsnames de Oracle; debe usarse el parámetro de base de datos; y el archivo SQLNET.ORA debe estar presente en el equipo de BizTalk Server (debe incluirse con el cliente Oracle).  
  
 Agregue lo siguiente al archivo jdeinterop.ini:  
  
1.  En [JDBj-ORACLE]:  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  En [JDBj-BOOTSTRAP DATA SOURCE]:  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear puertos de envío para JD Edwards EnterpriseOne](../core/how-to-create-send-ports-for-jd-edwards-enterpriseone.md)   
 [Solución de problemas de JD Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md)