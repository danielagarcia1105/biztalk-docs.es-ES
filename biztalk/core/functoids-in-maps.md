---
title: Functoids en asignaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids
- functoids, about functoids
- functoid types, Record Count
- functoid types, Looping
- Looping functoids
- functoids, categories
- functoid types, Addition
- Record Count functoids
ms.assetid: 10ee8b62-cb20-4d26-9d86-b6564f30c297
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 976af2faed27e6cae8a57d9c7c83308d0519d81d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246044"
---
# <a name="functoids-in-maps"></a>Functoids en asignaciones
El Asignador de BizTalk admite transformaciones estructurales complejas de registros y campos del esquema de origen a registros y campos del esquema de destino. Los functoids realizan cálculos utilizando fórmulas predefinidas y valores específicos, denominados argumentos. Estos cálculos se llevan a cabo según el orden establecido de registros y campos.  
  
 Al seleccionar un functoid en el cuadro de herramientas, arrastrarlo a la página de cuadrícula y vincularlo con nodos de los esquemas de origen y de destino, los datos se pueden agregar juntos, la información de fecha u hora se puede modificar, los datos se pueden concatenar o pueden llevarse a cabo otras operaciones. Por ejemplo, el **suma** functoid agrega valores y la **número de registros** functoid devuelve el número total de un registro de bucle en un mensaje de instancia. Las categorías de functoids que puede encontrar en el cuadro de herramientas son: avanzadas, conversión, acumulativos, base de datos, fecha / hora, lógicos, matemáticos, científica y cadena.  
  
> [!NOTE]
>  Todos los functoids son C# en línea, excepto los de bases de datos.  
  
> [!NOTE]
>  Nodos de esquema de destino solo aceptan una entrada de un functoid con excepción de la **bucle** functoid.  
  
 En los temas de esta sección se describe cómo migrar functoids de versiones anteriores de BizTalk Server, qué functoids hay, qué hacen y cómo utilizarlos.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Categorías de functoids](../core/functoid-categories.md)  
  
-   [Parámetros de entrada de functoid](../core/functoid-input-parameters.md)  
  
-   [Functoids básicos](../core/basic-functoids.md)  
  
-   [Functoids avanzados](../core/advanced-functoids.md)  
  
-   [Functoids en cascada](../core/cascading-functoids.md)  
  
-   [Propiedades de functoid](../core/functoid-properties.md)  
  
-   [Migrar Functoids](../core/migrating-functoids.md)