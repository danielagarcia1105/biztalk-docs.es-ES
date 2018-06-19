---
title: Crear y usar las reglas de negocios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Editor
- Business Rules Editor
ms.assetid: a15fd09b-ff4e-4c26-8cb6-5ffd258a2182
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76a6b51c72f04d5c7918da637f4266567f92e8bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238244"
---
# <a name="creating-and-using-business-rules"></a>Crear y usar reglas de negocios
Las reglas de negocios (o las directivas empresariales) definen y controlan la estructura, el funcionamiento y la estrategia de una organización. Las reglas de negocios pueden estar formalmente definidas en manuales de procedimiento, contratos o acuerdos, o bien pueden existir como conocimiento o experiencia que tienen los empleados. Las reglas de negocios son dinámicas, están sujetas a cambios en el tiempo y pueden encontrarse en todo tipo de aplicaciones. Finanzas y seguros, negocio electrónico, transporte, telecomunicaciones, servicios basados en Web y personalización son solo algunos de los muchos ámbitos de negocio que controlan las reglas de negocios. Todos estos ámbitos de negocio comparten la necesidad de transmitir estrategias, directivas y regulaciones empresariales al personal de tecnologías de la información (TI) para su inclusión en aplicaciones de software.  
  
 Los lenguajes de programación orientada a objetos o de procedimiento tradicional, como C, C++ y Microsoft Visual Basic, están orientados a los programadores. Incluso los lenguajes avanzados de programación orientada a objetos, como Java y C#, siguen siendo principalmente lenguajes de programadores. El ciclo de desarrollo tradicional de software basado en diseño, desarrollo, compilación y comprobación requiere mucho tiempo y coordinación, y no permite a quienes no son programadores participar en el mantenimiento de directivas empresariales automatizadas. El marco de trabajo de reglas de negocios corrige este problema, facilitando un entorno de desarrollo que permite la rápida creación de aplicaciones sin el extenso ciclo de programación tradicional de aplicaciones. Por ejemplo, las directivas empresariales que se construyen en este marco de trabajo pueden actualizarse sin necesidad de volver a compilar o implementar las orquestaciones asociadas.  
  
 El marco de trabajo de reglas de negocios está directamente integrado en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y los programadores pueden usar las siguientes características para generar y administrar reglas de negocios:  
  
-   Un motor de reglas de alto rendimiento que implementa un mecanismo de inferencia para evaluar las reglas de negocios.  
  
-   Un amplio conjunto de interfaces de programación de aplicaciones (API) para desarrollar aplicaciones basadas en reglas.  
  
-   Una interfaz de usuario gráfica, el Compositor de reglas de negocio, que los programadores, los analistas de negocios y los administradores pueden usar de varias maneras para desarrollar y aplicar eficazmente las reglas y directivas.  
  
-   Una perfecta integración con las orquestaciones de BizTalk, lo que permite invocar una directiva empresarial o un conjunto de reglas de negocios desde una orquestación de BizTalk.  
  
-   El Asistente para implementar el motor de reglas, que permite importar o exportar rápidamente reglas de negocios o los vocabularios que utilizan las reglas, así como implementar o anular la implementación de esas reglas.  
  
 Las reglas de negocios (o las directivas empresariales) creadas en el marco de trabajo de reglas de negocios se pueden usar en un proceso empresarial de orquestaciones, como se muestra en la siguiente ilustración.  
  
 ![Diagrama que muestra una directiva empresarial en proceso. ] (../core/media/ebiz-dev-busprcsi.gif "ebiz_dev_busprcsi")  
Directiva empresarial  
  
 Esta sección proporciona información conceptual acerca de cómo puede aprovechar el marco de trabajo de reglas de negocios y utilizar las herramientas que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona para desarrollar reglas de negocio.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Crear reglas de negocios](../core/creating-business-rules-using-the-business-rule-composer.md)  
  
-   [Seguridad de marco de trabajo de reglas de negocios](../core/business-rules-framework-security.md)  
  
-   [Programar con marco de trabajo de reglas de negocios](../core/programming-with-business-rules-framework.md)  
  
-   [Configuración del motor de reglas y parámetros de ajuste](../core/rule-engine-configuration-and-tuning-parameters.md)