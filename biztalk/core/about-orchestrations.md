---
title: Acerca de las orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations
- Orchestration Designer
- orchestrations, about orchestrations
- Orchestration Designer, about Orchestration Designer
ms.assetid: c0d9a3fb-da87-42cc-9e9e-e2c37232e606
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd3c1abeeb2c42c399a54aea4ba0128cc19bcd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-orchestrations"></a>Acerca de las orquestaciones
Una orquestación es una herramienta flexible y eficaz para la representación de un proceso empresarial ejecutable basado en el lenguaje XLANG/s. XLANG/s se puede ver como un lenguaje de mensajería con algunas de las capacidades de expresión de C#. Puede diseñar flujo, interpretar y generar datos, llamar código personalizado, así como organizar el proceso completo en un dibujo visual intuitivo y, en tiempo de ejecución, el motor de orquestaciones de BizTalk ejecuta los archivos XLANG/s que son los procesos empresariales ejecutables que produce el Diseñador de orquestaciones de BizTalk.  
  
 Los mensajes y las acciones de envío y recepción que se utilizan con ellos, así como los puertos a través de los que se transportan, son elementos fundamentales de una orquestación El mensaje es el medio a través del que las orquestaciones se comunican con el exterior y mediante el que se realizan las actividades de negocio electrónico.  
  
 **Recibir** y **enviar** formas encapsulan la funcionalidad que necesita para recibir mensajes en la orquestación y enviar mensajes desde ella. Debe familiarizarse con las distintas formas que el Diseñador de orquestaciones proporciona para representar el flujo lógico de una orquestación.  
  
 Asimismo, debe comprender los conceptos avanzados relacionados con las orquestaciones, como servicios Web, correlación y transacciones de larga ejecución. Tal vez no necesite utilizar todas estas funciones, pero es útil saber lo que pueden hacer.  
  
 Los servicios Web son programas con interfaces que cumplen los estándares establecidos en el Lenguaje de descripción de servicios Web (WSDL). Al definir de una forma estándar los tipos de mensajes, los puertos, los tipos de puertos y las operaciones, es posible establecer una comunicación eficaz entre sistemas diferentes.  
  
 Una correlación es el mecanismo mediante el cual se asocian los mensajes con determinadas instancias en ejecución de una orquestación, de manera que el proceso empresarial obtiene la información adecuada cuando se ejecutan numerosas instancias y se envían y se reciben numerosos mensajes.  
  
 Las transacciones le permiten mantener de forma adecuada el estado de una orquestación si surgen problemas inesperados. El Diseñador de orquestaciones proporciona varios modos para controlar las excepciones, lo que le permite solucionar los errores de una manera controlada y predecible.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [La superficie de diseño de orquestación](../core/the-orchestration-design-surface.md)  
  
-   [Ficha de orquestaciones de BizTalk, cuadro de herramientas](../core/biztalk-orchestrations-tab-toolbox.md)  
  
-   [Pasos de desarrollo de una orquestación](../core/steps-in-orchestration-development.md)  
  
-   [Consideraciones de seguridad para el desarrollo de orquestaciones](../core/security-considerations-for-developing-orchestrations.md)  
  
-   [Lenguaje XLANG-s.](../core/xlang-s-language.md)  
  
-   [Acerca del motor de orquestación de BizTalk](../core/about-the-biztalk-orchestration-engine.md)