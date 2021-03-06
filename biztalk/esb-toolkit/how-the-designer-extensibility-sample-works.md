---
title: Cómo funciona el ejemplo de extensibilidad del diseñador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f4dc622-28b8-498d-961f-df969cff9dcb
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f78e5ab2c8a274b53b3cc580b37842772924af94
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975881"
---
# <a name="how-the-designer-extensibility-sample-works"></a>Cómo funciona el ejemplo de extensibilidad del diseñador
Cada proyecto en el ejemplo de extensibilidad del diseñador contiene dos clases: una **Extender** clase y un **proveedor de extensiones** clase. Estas clases están diseñadas para ampliar las capacidades y definir las propiedades de la **ItineraryDsl** elementos del modelo.  
  
 El **proveedor de extensiones** clases se derivan de la **ExtensionProviderBase** clase y tener la **ExtensionProviderAttribute** aplicado a ellos con propiedades que identificar la extensión y su finalidad. Estos valores se mostrará al usuario en el diseñador cuando el usuario establezca la **Extender** propiedad en un elemento del modelo. Cuando el **proveedor de extensiones** inicialización de clases, que llaman al constructor de la **ExtensionProviderBase** y pasándole el tipo de la clase extender.  
  
 El **Extender** las clases tienen una **ObjectExtender** atributo aplicado a ellos; en el **ObjectExtender** atributo, pasa el tipo del objeto en el  **ItineraryDsl** que extienden. La clase base para estas clases varía, dependiendo del tipo de dispositivo extender. Para extender de resolución, la clase base es **ObjectExtender\<resolución\>**. Para extender el servicio de itinerario, la clase base es **ItineraryServiceExtenderBase**. En el **Extender** clases, los atributos siguientes se aplican a las propiedades: atributos necesarios para una visualización adecuada en una cuadrícula de propiedades, atributos que se incluyen en la biblioteca de empresa de Microsoft con fines de validación, atributos necesarios para la serialización sea correcta, o atributos que determinan cómo se guardan las propiedades.  
  
 Cuando estos ensamblados se compila y se coloca en la carpeta "lib", se cargan y almacenan en caché por el diseñador en tiempo de ejecución. Cuando extensores son necesarias, el **ItineraryDsl** utiliza la reflexión para cargar los ensamblados aplicables de la memoria caché mediante el examen de los tipos que se exportan y los atributos de esos tipos.