---
title: "Cómo desarrollar vocabularios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- vocabularies, creating
ms.assetid: 5c16eb98-2257-44f2-8a29-899e02f7e556
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2644cc938cbe5e42f4e124453d863741755d965d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-develop-vocabularies"></a>Cómo desarrollar vocabularios
Las condiciones y acciones de reglas se basan en orígenes que pueden tener información de enlace detallada y de difícil lectura y que cuentan al usuario poco o nada acerca de aquello a lo que se refieren. El marco de trabajo de reglas de negocios permite crear vocabularios para simplificar el desarrollo de reglas mediante terminología intuitiva para el usuario y específica del dominio, y que los usuarios pueden asociar con condiciones y acciones de reglas.  
  
 Puede identificar orígenes de datos para utilizar y crear un nuevo vocabulario y agregarle a éste definiciones.  Puede guardar una versión del vocabulario en el almacén de reglas y, cuando esté completa, publicarla para proporcionar a los usuarios un conjunto de términos bien definidos e inmutables enlazados con referencias de datos.  
  
 Si necesita realizar cambios en el vocabulario más adelante, puede crear sencillamente una nueva versión del vocabulario que refleje los cambios.  
  
> [!CAUTION]
>  Cuando se crea una nueva versión de un vocabulario, las reglas generadas a partir de una versión anterior seguirán apuntando hacia la versión anterior.   
  
### <a name="to-create-a-vocabulary"></a>Para crear un vocabulario.  
  
1.  En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha.  
  
2.  Haga clic en el **vocabularios** carpeta y, a continuación, haga clic en **Agregar nuevo vocabulario**.  
  
     Un nuevo **vocabulario** carpeta aparece debajo de la **vocabularios** carpeta.  
  
3.  Haga clic en el nuevo **vocabulario** carpeta y, a continuación, edite el nombre en la ventana Propiedades.  
  
    > [!NOTE]
    >  Debe guardarlo todo (todas las versiones de las definiciones) antes de poder cambiar el nombre a un vocabulario o a una directiva.