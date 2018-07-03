---
title: Acerca del proveedor de datos para Siebel | Microsoft Docs
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
ms.openlocfilehash: 97d7366ba227c16a5910a8000e57e92f992d3e1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989581"
---
# <a name="about-the-data-provider-for-siebel"></a>Acerca del proveedor de datos para Siebel
## <a name="overview"></a>Información general
El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] se basa en la parte superior de la [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]. Puede usar el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] para:  
  
- Escribir un cliente de ADO.NET para conectarse al sistema Siebel. La [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] expone algunas clases que permiten interactuar con el proveedor.  
  
- Ejecute una consulta SELECT en un componente empresarial de Siebel
  
- Ejecutar una consulta de ejecución en un servicio de negocio de Siebel
  
- Use la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] con SQL Server Integration Services (SSIS)
  
[Usar el proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md) es un excelente recurso para obtener información sobre:  
  
- Extiende las interfaces de ADO.NET mediante el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]  
  
- La cadena de conexión para conectarse a un sistema de Siebel  
  
- Sintaxis de las instrucciones SELECT y EXEC  
  
- Mediante el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] con SSIS  
  
## <a name="limitations"></a>Limitaciones
Lo siguiente es limitaciones conocida de la [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]:  
  
- El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] alias admite nombres de tablas en la cláusula SELECT, pero no en la cláusula WHERE.  
  
- El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] no puede crear una tabla con los nombres de columna que contiene el carácter especial, "]". Puede anular el carácter especial mediante la inclusión de otro corchete de cierre. Por lo tanto, se debe incluir"]]" en lugar de "]".  
  
- Debido a problemas con el control de tiempo de espera por el cliente de Siebel subyacente API, el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] no es compatible con el tiempo de espera de conexión y comando.  
  
- El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] no admite el comportamiento del comando asincrónico.  
  
- Cuando se usa con un proyecto de SQL Server Integration Services (SSIS), el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] se produce un error al recuperar datos para las columnas que contienen valores con más de 8.000 caracteres. Esto es debido a una restricción de SSIS, según el cual:  
  
  -   No se admiten los valores mayores que 4000 caracteres en la variable SSIS.  
  
  -   No se admiten los valores mayores que 4000 caracteres anchos.  
  
  -   No se admiten los valores mayores de 8000 caracteres de byte único.  
  
- La operación EXEC no será funcional al usar el [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] con SQL Server Integration Services (SSIS). Por lo tanto, por ejemplo, los clientes del adaptador no será capaz de ejecutar un servicio de negocio de Siebel (mediante [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) al usar los proveedores de datos con SSIS. 

## <a name="see-also"></a>Vea también
[Limitaciones del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[Solucionar problemas del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)