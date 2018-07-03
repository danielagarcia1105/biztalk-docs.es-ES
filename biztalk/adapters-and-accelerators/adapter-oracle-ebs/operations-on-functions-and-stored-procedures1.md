---
title: Operaciones en funciones y almacenado Procedures1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e6bdaa7-ed3c-43bc-bed5-70fe43f9c2d1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3356b41fc7929c55794c65e804245ed231b19b18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007829"
---
# <a name="operations-on-functions-and-stored-procedures"></a>Operaciones en funciones y procedimientos almacenados
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] admite Oracle funciones y procedimientos.

## <a name="functions-and-procedures"></a>Funciones y procedimientos

El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] admite Oracle funciones y procedimientos de la manera siguiente:  
  
- **Funciones** se exponen como operaciones. El nombre de la operación es el nombre de la función de Oracle. IN, OUT y en espera parámetros son compatibles, además, los valores devuelvan.  
  
  > [!IMPORTANT]
  >  Si se pasa un parámetro no válido en una función (es decir, pasar un valor de cadena de un campo numérico), el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] podría producir una excepción según el comportamiento ODP.NET. Esto es porque el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa ODP.NET para comunicarse con Oracle E-Business Suite.  
  
- **Procedimientos** se exponen como operaciones. El nombre de la operación es el nombre del procedimiento de Oracle. Se admiten parámetros IN, OUT y en espera.  
  
  > [!IMPORTANT]
  >  Como parte de un procedimiento, si insertar o actualizar un valor decimal (por ejemplo, 15.2) en un campo numérico de una tabla de interfaz o la tabla de base de datos, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se iniciará una excepción. Esto es porque el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa ODP.NET para comunicarse con Oracle E-Business Suite y ODP.NET no admite aceptando los valores decimales para los campos numéricos.  
  
- **Tipos de REF CURSOR** son compatibles con IN y OUT parámetros para procedimientos y funciones, así como para la función de los valores devueltos. Para obtener más información, consulte [operaciones en funciones y procedimientos con parámetros REF CURSOR](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).  
  
- **Tipos de registro** son compatibles con IN, OUT y en los parámetros de procedimientos y funciones, así como para la función OUT devolver valores. Se admiten tipos de registros (anidados) simples y complejos. [Operaciones en funciones y procedimientos con tipos RECORD](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
> [!NOTE]
>  También puede establecer el contexto de la aplicación para las funciones y procedimientos almacenados en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener información sobre el contexto de la aplicación y cómo configurarlo, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)