---
title: ¿Qué es una definición de BAM? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definitions [BAM], observation models
- definitions [BAM], about BAM definitions
- definitions [BAM]
ms.assetid: 1ba1f45e-85fe-492f-8a2e-98bf3570c633
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cbc600f66be7167aabb4cf0273cb1c0bda78973
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289684"
---
# <a name="what-is-a-bam-definition"></a>¿Qué es una definición de BAM?
Una definición de BAM es una representación XML de un modelo de observación de BAM, que es una definición de alto nivel de un proceso empresarial que desea supervisar. Las partes principales del modelo de observación, y por lo tanto, la definición de BAM, son los hitos y eventos de datos que se van a recopilar (la actividad de BAM), una descripción de cualquier agregación de datos y la presentación de la información a los usuarios (la vista de BAM).  
  
> [!NOTE]
>  Asimismo, puede crear un archivo XML que siga el esquema de BAM aunque no se recomienda para crear la definición de BAM ya que no proporciona una definición que se haya validado.  
  
 Las definiciones de BAM contienen los siguientes elementos:  
  
-   Actividades empresariales – Una definición de BAM válida debe contener una actividad empresarial (a la que también se denomina actividad de BAM). Todos los demás elementos de la definición son opcionales. Para obtener información acerca de cómo agregar una actividad económica a una definición, vea [cómo definir una actividad económica](../core/how-to-define-a-business-activity.md).  
  
-   Vistas – Las vistas definen el conjunto de usuarios que pueden obtener acceso a los datos que definió la actividad económica. Las vistas se componen de datos filtrados, agregaciones de los datos filtrados y formas de presentar los datos filtrados, como un informe de tabla dinámica. BAM admite la definición de una o más vistas por actividad.  
  
     En una vista puede definir los siguientes procesos empresariales:  
  
    -   Datos económicos con alias – Los alias le permiten aplicar nombres descriptivos a los elementos de datos. Por ejemplo, un programador puede definir un elemento de datos que se llame “LName”. Puede crear un alias de manera que “LName” se muestre como “Apellido” cuando se vean los datos activos de BAM.  Para obtener más información acerca de los alias, vea [cómo cambiar el nombre de elementos de vista](../core/how-to-rename-view-items.md).  
  
    -   Duración – El período de tiempo durante el que se supervisa una actividad.  
  
    -   Grupos de hitos – Conjuntos de hitos económicos. Puede utilizar un grupo como hito económico, tanto de inicio de una duración como de fin.  
  
    -   Agregaciones - resultan agregaciones en tiempo real (ATR) o agregaciones programadas (contempladas también como procesamiento analítico en línea (OLAP)) y constan de los siguientes elementos:  
  
-   Medidas – Un conjunto de valores numéricos en un cubo de Analysis Services (OLAP) basado en una columna de la taba de hechos del cubo.  
  
-   Dimensión de progreso – Representa la creación de agregaciones en relación con el progreso de actividades que todavía están en ejecución.  
  
-   Dimensión de datos – Se utiliza para clasificar una agregación. Las dimensiones de datos están basadas en el valor de los elementos de datos con formato de cadena de la actividad de BAM.  
  
-   Dimensión de tiempo – Se utiliza para crear agregaciones en segmentos de tiempo definidos.  
  
-   Dimensión de intervalo numérico – Se utiliza para clasificar las agregaciones basadas en nombres descriptivos de intervalos numéricos determinados.  
  
 Las definiciones de BAM pueden contener definiciones de alertas que se han definido en las vistas. Las definiciones de BAM también pueden contener diseños de tablas dinámicas. Una vez implementada la definición de BAM, el informe de tabla dinámica contiene los datos económicos activos que se pueden ver mediante el libro de datos activos de Excel o mediante el portal de BAM.  
  
> [!NOTE]
>  Definiciones de BAM creadas con el complemento de BAM para Excel no pueden contener alertas.  
  
## <a name="see-also"></a>Vea también  
 [Definir actividades económicas y vistas en Excel](../core/defining-business-activities-and-views-in-excel.md)   
 [Portal de BAM](../core/bam-portal.md)   
 [Infraestructura dinámica de BAM](../core/bam-dynamic-infrastructure.md)