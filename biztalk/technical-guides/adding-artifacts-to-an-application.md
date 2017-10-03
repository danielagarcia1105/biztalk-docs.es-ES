---
title: "Agregar artefactos a una aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9b5e92e-2e55-41d7-9959-f62753bbeb04
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c08fa95dddad06efb2c51d93df56b757ae4caca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adding-artifacts-to-an-application"></a>Agregar artefactos a una aplicación
Puede agregar y configurar artefactos, como el envío y puertos de recepción, ubicaciones de recepción y orquestaciones, con la administración de la consola. También puede generar archivos de enlace y agregarlos a la aplicación si desea aplicar diferentes enlaces a la que desea importar la aplicación en entornos diferentes.  
  
 Puede agregar más (normalmente externos a BizTalk Server) artefactos, como scripts, certificados y archivos Léame, a la aplicación en el nodo de recursos. Para ello, use la consola de administración o BTSTask.  
  
 Para obtener más información acerca de artefactos, vea [cómo crear o agregar un artefacto](http://go.microsoft.com/fwlink/?LinkID=154724) (http://go.Microsoft.com/fwlink/?) LinkID = 154724), [administrar artefactos](http://go.microsoft.com/fwlink/?LinkID=154725) (http://go.Microsoft.com/fwlink/?) LinkID = 154725) y [archivos de enlace e implementación de la aplicación](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.Microsoft.com/fwlink/?) LinkID = 154726).  
  
## <a name="factoring-artifacts-into-multiple-biztalk-applications"></a>Factorizar artefactos en varias aplicaciones de BizTalk  
 Durante el proceso de desarrollo, es posible que se hayan implementado los ensamblados en una única aplicación por comodidad. Puede que, por distintas razones, desee descomponer los artefactos en varias aplicaciones antes de que se implementen en la producción.  
  
 Antes de implementar, debe realizar un análisis detallado de la factorización de un ensamblado. Determinar si es no necesario realizar ninguna factorización, dividir completa o factorización óptimo.  
  
 **No hay factorización**  
  
 Todos los artefactos de BizTalk están en un ensamblado. Esto es más fácil de comprender e implementar, pero proporciona la menor cantidad de flexibilidad.  
  
 **Factorización completa**  
  
 Cada artefacto de BizTalk está en su propio ensamblado. Esto ofrece la máxima flexibilidad, pero es la más compleja para implementar y comprender.  
  
 **Factorización óptimo**  
  
 Factorización óptimo comprendida entre n factorización y factorización completa en función de un análisis exhaustivo de las aplicaciones de BizTalk. Además de las versiones, esto permite que más fácil implementan el diseño de host de BizTalk. Esto se logra mediante la búsqueda de relaciones entre artefactos de BizTalk. Si es posible, coloque los artefactos que están siempre con control de versiones en el mismo ensamblado. Si es necesaria crear versiones independientes de los artefactos, debe colocar en distintos ensamblados. Este es el nivel de factorización de la que se desea lograr.