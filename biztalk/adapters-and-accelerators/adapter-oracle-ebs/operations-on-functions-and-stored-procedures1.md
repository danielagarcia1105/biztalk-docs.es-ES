---
title: Operaciones en las funciones y almacenado Procedures1 | Documentos de Microsoft
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
ms.openlocfilehash: cfe5f705c8e432c920c8fae41a2b2f050c188047
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216356"
---
# <a name="operations-on-functions-and-stored-procedures"></a>Operaciones en funciones y procedimientos almacenados
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es compatible con los procedimientos y funciones de Oracle.

## <a name="functions-and-procedures"></a>Funciones y procedimientos

El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es compatible con las funciones de Oracle y los procedimientos de la siguiente manera:  
  
-   **Funciones** aparecen como operaciones. El nombre de la operación es el nombre de la función de Oracle. EN fuera y en espera parámetros son compatibles, así como, valores devuelvan.  
  
    > [!IMPORTANT]
    >  Si se pasa un parámetro no válido en una función (es decir, pasar un valor de cadena de un campo numérico), el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] podría producir una excepción según el comportamiento ODP.NET. Esto es porque el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa ODP.NET para comunicarse con Oracle E-Business Suite.  
  
-   **Procedimientos** aparecen como operaciones. El nombre de la operación es el nombre del procedimiento de Oracle. Se admiten parámetros en fuera y en espera.  
  
    > [!IMPORTANT]
    >  Como parte de un procedimiento, si inserta o actualiza un valor decimal (por ejemplo, 15,2) en un campo numérico de una tabla de interfaz o una tabla de base de datos, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se iniciará una excepción. Esto es porque el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] utiliza ODP.NET para comunicarse con Oracle E-Business Suite y ODP.NET no admite aceptando los valores decimales para los campos numéricos.  
  
-   **Tipos de REF CURSOR** son compatibles con IN y OUT parámetros para los procedimientos y funciones, así como para la función de los valores devueltos. Para obtener más información, consulte [operaciones en funciones y procedimientos con parámetros REF CURSOR](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).  
  
-   **Tipos de registro** son compatibles con IN, OUT y en los parámetros de procedimientos y funciones, así como para la función OUT DEVUELVEN valores. Se admiten tipos de registros (anidados) simples y complejos. [Operaciones en funciones y procedimientos con tipos de registro](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
> [!NOTE]
>  También puede establecer el contexto de la aplicación para las funciones y procedimientos almacenados en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener información sobre el contexto de la aplicación y cómo configurarlo, vea [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)