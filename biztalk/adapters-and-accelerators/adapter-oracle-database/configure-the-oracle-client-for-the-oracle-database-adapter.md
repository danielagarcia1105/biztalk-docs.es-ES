---
title: Configurar el cliente de Oracle para el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- net service name
- tnsnames.ora
- configuring, the Oracle client
- connect descriptor
- Oracle client, configuring
- Oracle Net Configuration Assistant
- Oracle Net Configuration Assistant, using the
ms.assetid: 2d4c0f20-b3a6-453f-a9b3-65fd5a38c020
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 209d5603a9f8ff8c09185093efb976afb6432d65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-oracle-client-for-the-oracle-database-adapter"></a>Configurar al cliente de Oracle para el adaptador de la base de datos de Oracle
> [!IMPORTANT]
>  En este tema solo es pertinente si utilizas tnsnames.ora para conectarse a la base de datos de Oracle.  
  
 El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] se conecta a la base de datos de Oracle a través del cliente de Oracle instalado en el equipo. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] pasa el nombre de servicio de red que especifique en el URI de conexión para el cliente de Oracle para establecer una conexión a la base de datos de Oracle. El nombre de servicio de red es un alias que utiliza el cliente de Oracle para adquirir la información de conexión para el destino de servicio de base de datos de Oracle.  
  
 El cliente de Oracle resuelve el servicio de net nombre según el método de asignación de nombres que está configurado para usar. Utilice Oracle Net Configuration Assistant para configurar los métodos de asignación de nombres que va a usar el cliente de Oracle. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con el método de nomenclatura Local para conectarse a la base de datos de Oracle. Este método usa un archivo local, tnsnames.ora, para resolver el nombre de servicio de red.  
  
 La asociación de archivo tnsnames.ora nombres de servicio de red con conexión descriptores que contienen la información que necesita el cliente de Oracle para establecer una conexión a un servicio específico de base de datos de Oracle (instancia). El siguiente es un ejemplo de entrada de tnsnames.ora.  
  
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
oracledb://ADAPTER  
```  
  
 Para obtener más información sobre el uso de Oracle Net Configuration Assistant y tnsnames.ora, consulte el Oracle base de datos neto servicios Guía del administrador. Consulte al administrador de base de datos acerca de los detalles de configuración para su instalación específica.  
  
## <a name="see-also"></a>Vea también  
[Crear una conexión a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)