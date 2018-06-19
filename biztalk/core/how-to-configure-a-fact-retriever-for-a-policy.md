---
title: Cómo configurar un administrador de almacenes de una directiva | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, policies
- Business Rule Composer, facts
- policies, facts
ms.assetid: a7bcf3e5-3f28-4f0e-b112-8c97dee072a1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18572af1323de817b3c934866af917d2601332f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247100"
---
# <a name="how-to-configure-a-fact-retriever-for-a-policy"></a>Cómo configurar un administrador de almacenes de una directiva
Puede almacenar hechos que no cambien con frecuencia y, posteriormente, antes del primer ciclo de ejecución de la aplicación de host, puede recuperar esos hechos desde donde se encuentren almacenados, presentarlos una vez al motor de reglas para su almacenamiento en caché y volver a utilizarlos en múltiples ciclos de ejecución.  
  
 Existen dos modos para asociar un administrador de almacenes de datos con una directiva. Puede hacerlo mediante el Compositor de reglas de negocio o mediante programación utilizando la **RuleSetExecutionConfiguration** objeto.  
  
> [!NOTE]
>  Sólo se puede asociar una implementación de administrador de almacenes de datos con una versión de directiva.  
  
### <a name="to-associate-a-fact-retriever-with-a-policy-in-the-business-rule-composer"></a>Para asociar un administrador de almacenes de datos con una directiva en el Compositor de reglas de negocio  
  
1.  En la ventana Explorador de directivas, haga clic en la versión de directiva con la que desee asociar el administrador de almacenes de datos.  
  
2.  En la ventana Propiedades, haga clic en el **puntos suspensivos** botón (…) en el **FactRetriever** propiedad que se va a buscar en la caché global de ensamblados para un objeto de almacenes de datos de hechos.  
  
    > [!IMPORTANT]
    >  El **puntos suspensivos** botón (...) no aparece hasta que haga clic en el **FactRetriever** fila en la ventana Propiedades.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear un administrador de almacenes](../core/how-to-create-a-fact-retriever.md)