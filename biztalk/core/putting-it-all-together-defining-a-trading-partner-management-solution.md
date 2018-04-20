---
title: 'Perspectiva general: definir una solución de administración de socios comerciales | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4219312a-c4b5-45f3-b77b-d5cc4f1a1ca4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea32fba8e9e57d7a0549a680b06e08d5bf8e087f
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="putting-it-all-together-defining-a-trading-partner-management-solution"></a>Perspectiva general: definir una solución de administración de socios comerciales
Ahora que hemos comprendido los diferentes tipos de componentes en la generación de una solución TPM, vamos a describir el flujo de una solución TPM típica y cómo funcionan juntos los diferentes componentes fundamentales. En esta sección también se enumeran algunas de las prácticas recomendadas para modelar una solución TPM.  
  
 Un flujo típico para crear una solución TPM incluiría lo siguiente:  
  
1.  Cree socios que representen a todas las organizaciones implicadas en un intercambio comercial. Por ejemplo, si hay dos organizaciones empresariales implicadas en un intercambio comercial, deberá crear un socio comercial para cada una de ellas. Para obtener instrucciones sobre cómo crear socios comerciales, vea [configurar propiedades de entidad General](../core/configuring-general-party-properties.md) o [configurar propiedades de entidad General (AS2)](../core/configuring-general-party-properties-as2.md)  
  
2.  Para cada división de negocio de una organización, cree un perfil en el socio que represente la división de negocio. Por ejemplo, si una organización tiene las divisiones de negocio “Compra” y “Suministros”, cada una de estas divisiones deberá estar representada como perfil de negocio en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Además, debe crear los perfiles de negocio no solo para el socio que representa su organización, sino también para el socio con el que comercia. Para obtener instrucciones sobre cómo crear perfiles de negocio, consulte [configurar propiedades de perfil de negocio](../core/configuring-business-profile-properties.md).  
  
3.  Para cada perfil de negocio, defina la configuración del protocolo B2B que incluya la configuración de codificación del mensaje y la configuración del protocolo de mensaje. Esta configuración define cómo se codifican y transportan los mensajes B2B entre dos perfiles de negocio.  
  
    > [!NOTE]
    >  Especificar la configuración del protocolo es opcional en esta etapa. Puede agregar directamente la configuración del protocolo como parte del acuerdo de socio comercial.  
  
4.  Cree acuerdos de socios comerciales (TPA) entre los perfiles de negocio que definen los protocolos de codificación y/o mensajes que acuerdan usar los dos perfiles de negocio al intercambiar mensajes. Para obtener instrucciones sobre cómo crear acuerdos, vea [configurar propiedades del acuerdo específicas de X12](../core/configuring-x12-specific-agreement-properties.md), [configurar propiedades del acuerdo específicas de EDIFACT](../core/configuring-edifact-specific-agreement-properties.md), o [configuración de AS2 Propiedades del acuerdo de](../core/configuring-as2-agreement-properties.md).  
  
 Al realizar el anterior conjunto de tareas, debe haber creado la solución TPM para intercambiar mensajes B2B con su socio comercial.  
  
## <a name="where-do-i-start"></a>¿Dónde debo empezar?  
 Puede iniciar, vaya a través de las siguientes secciones:  
  
-   Tutorial de X12 específica en [Tutorial 2: EDI Interface Developer Tutorial](../core/tutorial-2-edi-interface-developer-tutorial.md).  
  
-   Tutorial de específicos de AS2 en [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md).  
  
-   X12-y EDIFACT-tutoriales específicos en [desarrollar y configurar soluciones de EDI de BizTalk Server](../core/developing-and-configuring-biztalk-server-edi-solutions.md).  
  
-   Tutoriales específicos de AS2 en [desarrollar y configurar soluciones de AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md).  
  
-   Crear entidades, perfiles y acuerdos para X12 y EDIFACT mensajería siguiendo las instrucciones en [configurar propiedades de EDI](../core/configuring-edi-properties.md).  
  
-   Crear entidades, perfiles y acuerdos de AS2 Mensajería siguiendo las instrucciones en [configurar propiedades de AS2](../core/configuring-as2-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Bloques de creación de una solución de administración de socios comerciales](../core/building-blocks-of-a-trading-partner-management-solution.md)