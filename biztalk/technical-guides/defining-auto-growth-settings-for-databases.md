---
title: "Definir los valores de crecimiento automático de las bases de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dd86dd49-6505-4673-b413-d3af729dfca9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e39de58751615e0465ce543368f47c1acd42ebc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="defining-auto-growth-settings-for-databases"></a>Definir los valores de crecimiento automático de las bases de datos
Debe establecer el crecimiento automático de base de datos en un número fijo de megabytes, en lugar de a un porcentaje, especialmente para las bases de datos de cuadro de mensaje y seguimiento de BizTalk. Dependiendo de la aplicación de BizTalk y el rendimiento, el cuadro de mensajes y las bases de datos de seguimiento pueden ser bastante grandes. Si el crecimiento automático se establece en un porcentaje, a continuación, el crecimiento automático puede ser sustancial así.  
  
## <a name="how-instant-file-initialization-works"></a>Cómo instantánea funciona de inicialización de archivos  
 Cuando SQL Server aumenta el tamaño de un archivo, debe inicializar el nuevo espacio antes de poder utilizarlo. Se trata de una operación de bloqueo que implica ocupar todo el espacio nuevo con páginas vacías. SQL Server en Windows admite "inicialización instantánea de archivos". Esto puede reducir considerablemente el impacto en el rendimiento de una operación de crecimiento de archivos. Para obtener más información, vea [Inicialización de archivos de base de datos](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization). En este tema se describe los pasos que se deben realizar para habilitar la inicialización instantánea de archivos.  
  
## <a name="enabling-instant-file-initialization"></a>Habilitar la inicialización instantánea de archivos  
 Para pasos sobre la habilitación de instantánea de inicialización de archivos, consulte [la inicialización de archivos de base de datos](https://docs.microsoft.com/en-us/sql/relational-databases/databases/database-instant-file-initialization). Para crear grupos de archivos y mover las tablas de base de datos de BizTalk Server, los índices y los archivos de registro en los grupos de archivos adecuada, siga las recomendaciones de "Apéndice B – recomienda base de datos de configuración de BizTalk Server" en el ["BizTalk Server Optimización de la base de datos"notas del producto](http://go.microsoft.com/fwlink/?LinkID=101578). Lo ideal es que el tamaño de los archivos de compatibilidad con los grupos de archivos se debe asignar previamente y si es posible, se establece en un tamaño estático.  
  
 Si el sistema es nuevo y los tamaños estáticos no se han establecido definitivamente, a continuación, configure los archivos con la **Habilitar crecimiento automático** opción y especifique el crecimiento del archivo **en Megabytes**. El incremento de crecimiento por lo general debe ser no superior a 100 MB (para archivos de gran tamaño), 10 MB (para archivos de tamaño medio) o 1 MB (para archivos pequeños).