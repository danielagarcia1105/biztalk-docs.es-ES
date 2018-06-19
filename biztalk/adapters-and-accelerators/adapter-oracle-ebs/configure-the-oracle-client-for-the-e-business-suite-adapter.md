---
title: Configurar el cliente de Oracle para el adaptador de E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 842b6ecc-5334-4cc0-af10-baa7f692ad23
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ada64bf6f54c95f3d6e1c8f968a506476dbbc6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214772"
---
# <a name="configure-the-oracle-client-for-the-e-business-suite-adapter"></a>Configurar al cliente de Oracle para el adaptador de E-Business Suite
> [!IMPORTANT]
>  En este tema solo es pertinente si utilizas tnsnames.ora para conectarse a la base de datos de Oracle.  
  
 Para establecer una conexión con el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)], el adaptador se conecta a la base de datos de Oracle subyacente a través del cliente de Oracle instalado en el equipo. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pasa el nombre de servicio de red que especifique en el URI de conexión para el cliente de Oracle para establecer una conexión a Oracle E-Business Suite. El nombre de servicio de red es un alias que utiliza el cliente de Oracle para adquirir la información de conexión para el destino de servicio de base de datos de Oracle.  
  
 El cliente de Oracle resuelve el servicio de net nombre según el método de asignación de nombres que está configurado para usar. Utilice Oracle Net Configuration Assistant para configurar los métodos de asignación de nombres que va a usar el cliente de Oracle. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con el método de nomenclatura Local para conectarse a Oracle E-Business Suite. Este método usa un archivo local, tnsnames.ora, para resolver el nombre de servicio de red.  
  
 El archivo tnsnames.ora asocia nombres de servicio de red con conexión descriptores que contienen la información que necesita el cliente de Oracle para establecer una conexión a un servicio específico de base de datos de Oracle (instancia). El siguiente es un ejemplo de entrada de tnsnames.ora.  
  
```  
ADAPTER =  
  (DESCRIPTION =  
    (ADDRESS_LIST =  
      (ADDRESS = (PROTOCOL = TCP)(HOST = yourOracleServer)(PORT = 1521))  
    )  
    (CONNECT_DATA =  
      (SERVICE_NAME = yourOracleDatabaseServiceName)  
    )  
  )  
```  
  
 En esta entrada de ejemplo, el adaptador es el nombre de servicio de red. El descriptor de conexión especifica información de dirección y el nombre de servicio del servicio de base de datos de Oracle asociado con el adaptador. Puede usar Oracle Net Configuration Assistant para crear y configurar los nombres de servicio de red en tnsnames.ora. Después de haber configurado el nombre de servicio de red, puede especificar en un URI de conexión como en el ejemplo siguiente.  
  
```  
oracleebs://ADAPTER  
```  
  
 Para obtener más información sobre el uso de Oracle Net Configuration Assistant y tnsnames.ora, consulte el Oracle base de datos neto servicios Guía del administrador. Consulte al administrador de base de datos acerca de los detalles de configuración para su instalación específica.  
  
## <a name="see-also"></a>Vea también  
 [Crear una conexión a Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)