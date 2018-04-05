---
title: Acerca del proveedor de datos para Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, overview
ms.assetid: 461fe4d8-75f2-49d5-9fc2-3baab4ccf13f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81cac425bf1671166b4f40cecae3e1a3aca1c8e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-data-provider-for-siebel"></a>Acerca del proveedor de datos para Siebel
## <a name="overview"></a>Información general
El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] se basa en el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]. Puede usar el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] para:  
  
-   Escribir un cliente ADO.NET para conectarse al sistema Siebel. La [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] expone ciertas clases que permiten interactuar con el proveedor.  
  
-   Ejecute una consulta SELECT en un componente de negocio de Siebel
  
-   Ejecutar una consulta de ejecución en un servicio de negocios de Siebel
  
-   Use la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] con SQL Server Integration Services (SSIS)
  
[Usar el proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md) es un excelente recurso para obtener información sobre:  
  
-   Las interfaces ADO.NET extendidos mediante el[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]  
  
-   La cadena de conexión para conectarse a un sistema Siebel  
  
-   Sintaxis de las instrucciones SELECT y EXEC  
  
-   Con la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] con SSIS  
  
## <a name="limitations"></a>Limitaciones
Los siguientes se conocen las limitaciones de la [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]:  
  
-   El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] alias admite nombres para las tablas en la cláusula SELECT, pero no en la cláusula WHERE.  
  
-   El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] no puede crear una tabla con nombres de columna que contiene el carácter especial, "]". Se puede omitir el carácter especial mediante la inclusión de otro corchete de cierre. Por lo tanto, debe incluir"]]" en lugar de "]".  
  
-   Debido a problemas con el control de tiempo de espera por el cliente de Siebel subyacente API, el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] no es compatible con el tiempo de espera de conexión y comando.  
  
-   El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] no admite el comportamiento del comando asincrónico.  
  
-   Cuando se usa con un proyecto de SQL Server Integration Services (SSIS), el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] se produce un error al recuperar datos para las columnas que contienen valores con más de 8.000 caracteres. Esto es debido a una restricción de SSIS según los cuales:  
  
    -   No se admiten valores superiores a 4.000 caracteres en la variable SSIS.  
  
    -   No se admiten valores superiores a 4.000 caracteres anchos.  
  
    -   No se admiten valores mayores que 8000 caracteres de byte único.  
  
-   La operación de EXEC no será funcional al usar el [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] con SQL Server Integration Services (SSIS). Por lo tanto, por ejemplo, los clientes de adaptador no será capaz de ejecutar un servicio de negocio de Siebel (mediante [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) durante el uso de los proveedores de datos con SSIS. 

## <a name="see-also"></a>Vea también
[Limitaciones del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[Solucionar problemas del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)