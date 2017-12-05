---
title: Pruebas unitarias con proyectos de BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2594f29-fc34-4dda-9316-2afd4e0056d7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da7147f4c2500946fb97c47592a2a4a35d3dcf62
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="unit-testing-with-biztalk-server-projects"></a>Pruebas de unidades con proyectos de BizTalk Server
BizTalk Server introdujo un característica que se puede habilitar en de pruebas unitarias la **implementación** página de propiedades de un proyecto de BizTalk. Captura de pantalla siguiente muestra esta configuración del proyecto que se tiene acceso desde el Diseñador de proyectos cuando haga clic en un proyecto y haga clic en el **propiedades**.  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 **Captura de pantalla de la pestaña implementación en el Diseñador de proyectos que expone la propiedad de proyecto habilitar pruebas de unidades.**  
  
 Esta característica permite crear pruebas de unidades para los esquemas, asignaciones y canalizaciones. Los temas de esta sección proporcionan algunos métodos de ejemplo sobre cómo usar la característica de prueba de unidades. Si se habilita esta característica y se vuelve a generar el proyecto, las clases de artefacto se derivan de las siguientes clases base para admitir las pruebas de unidades.  
  
|Tipo de artefacto|Clase base|  
|-------------------|----------------|  
|esquema|**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**|  
|Mapa|**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**|  
|Canalización|**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**|  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Uso de la característica con esquemas y asignaciones de pruebas de unidades](../core/using-the-unit-testing-feature-with-schemas-and-maps.md)  
  
-   [Uso de la característica con canalizaciones de pruebas de unidades](../core/using-the-unit-testing-feature-with-pipelines.md)  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Trabajar con pruebas unitarias (Visual Studio)](http://go.microsoft.com/fwlink/?LinkId=128890)