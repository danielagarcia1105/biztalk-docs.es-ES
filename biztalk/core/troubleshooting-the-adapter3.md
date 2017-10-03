---
title: "Solución de problemas de la Adapter3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters [JD Edwards OneWorld adapters], connecting [Oracle databases]
- JD Edwards OneWorld adapters, troubleshooting
- troubleshooting [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], troubleshooting
- Oracle databases, connecting [JD Edwards OneWorld adapters]
ms.assetid: 2dd6a951-f113-4f43-b43f-057a239d05c4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15197bcdc84e813d31a8d5292f5559aca1f8ae01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-adapter"></a>Solucionar problemas del adaptador
Este tema contiene información que le ayudará a identificar y resolver los problemas que pueden surgir al usar el adaptador de Microsoft BizTalk para JD Edwards OneWorld.  
  
## <a name="cannot-use-wildcards-in-send-and-receive-port-properties"></a>No se pueden utilizar comodines en las propiedades del puerto de envío y recepción  
 El adaptador para JD Edwards One World no admite el uso de comodines en los siguientes campos de propiedades:  
  
|Propiedad de puerto de envío|Propiedad de puerto de recepción|  
|------------------------|---------------------------|  
|Nombre de usuario|Ruta de acceso del archivo del evento|  
|Entorno JDE|Prefijo de nombre de destino del evento|  
|Host||  
|Puerto||  
|Java_Home||  
|Archivos JAR de JDE||  
  
## <a name="connecting-to-oracle-database"></a>Conectando a la base de datos de Oracle  
 Cuando se usa la base de datos de Oracle con JD Edwards debe modificarse el archivo jdeinterop.ini. Mediante el Inicio de sesión único, la sección [JDBj-ORACLE] define la ubicación de tnsnames de Oracle; debe usarse el parámetro de base de datos; y el archivo SQLNET.ORA debe estar presente en el equipo de BizTalk Server (debe incluirse con el cliente Oracle).  
  
 Agregue lo siguiente al archivo jdeinterop.ini:  
  
1.  En [JDBj ORACLE], escriba:  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  En [JDBj-BOOTSTRAP DATA SOURCE], escriba:  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear puertos de envío para JD Edwards OneWorld](../core/how-to-create-send-ports-for-jd-edwards-oneworld.md)   
 [Solución de problemas de JD Edwards OneWorld](../core/troubleshooting-jd-edwards-oneworld.md)