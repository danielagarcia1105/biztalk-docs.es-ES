---
title: Operaciones en API PL-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d47b894d-1047-48ed-8f8c-865c343a12db
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5719d74517331b30de986424bc14e7d01d128cf3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999349"
---
# <a name="operations-on-plsql-apis"></a>Operaciones en las API de PL/SQL
Oracle E-Business Suite proporciona un conjunto de API de PL/SQL en forma de procedimientos almacenados y funciones empaquetadas. Estas funciones de empaquetado y los procedimientos se exponen como operaciones en [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]. 

## <a name="plsql-apis-are-grouped-by-schema-names"></a>Las API de PL/SQL se agrupan por nombres de esquema 
Las API de PL/SQL se agrupan por nombres de esquema en el **vista basada en el artefacto** y **vista basada en esquema** nodos al conectarse a Oracle E-Business Suite utilizando [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener información acerca de cómo explorar las API de PL/SQL en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [examinar, buscar y obtener metadatos para operaciones de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] muestra las API de PL/SQL asociados con la base de datos de Oracle, así como las aplicaciones de Oracle E-Business Suite en el **vista basada en el artefacto** y **vista basada en esquema** nodos.  
  
## <a name="important-info"></a>Información importante
  -   Para poder realizar operaciones en las API de PL/SQL asociadas a las aplicaciones de Oracle E-Business Suite, debe establecer el contexto de las aplicaciones. Esto es porque el contexto de las aplicaciones de configuración facilita transacciones seguras en Oracle E-Business Suite estableciendo las preferencias del usuario (por ejemplo, la configuración de idioma, la organización y la responsabilidad) y el control de acceso de un artefacto. Sin embargo, es opcional establecer el contexto de las aplicaciones para las API de PL/SQL asociado con la base de datos de Oracle. Consulte [establecer el contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  

- El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no se puede determinar si se asigna un valor predeterminado para un parámetro en una API de PL/SQL de Oracle.  Además, el adaptador también no se puede determinar si un parámetro se define como obligatorio u opcional en una API de PL/SQL de Oracle. El adaptador trata todos los parámetros como un parámetro opcional, y si se especifica ningún valor para un parámetro que:  

  -   Tiene un valor predeterminado por el valor especificado en Oracle, a continuación, se usa el valor predeterminado.  
  -   Se define como un parámetro obligatorio en Oracle, a continuación, una excepción se produce.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)