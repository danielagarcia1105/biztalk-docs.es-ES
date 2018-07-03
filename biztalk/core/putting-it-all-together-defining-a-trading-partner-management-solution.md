---
title: 'Perspectiva general: definición de una solución de administración de socios comerciales | Microsoft Docs'
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
ms.openlocfilehash: 4846df26680fa547a81c9136dfc2fd92fb95ee96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001229"
---
# <a name="putting-it-all-together-defining-a-trading-partner-management-solution"></a>Perspectiva general: definición de una solución de administración de socios comerciales
Ahora que hemos comprendido los diferentes tipos de componentes en la generación de una solución TPM, vamos a describir el flujo de una solución TPM típica y cómo funcionan juntos los diferentes componentes fundamentales. En esta sección también se enumeran algunas de las prácticas recomendadas para modelar una solución TPM.  
  
 Un flujo típico para crear una solución TPM incluiría lo siguiente:  
  
1. Cree socios que representen a todas las organizaciones implicadas en un intercambio comercial. Por ejemplo, si hay dos organizaciones empresariales implicadas en un intercambio comercial, deberá crear un socio comercial para cada una de ellas. Para obtener instrucciones sobre cómo crear socios comerciales, vea [configurar propiedades de entidad General](../core/configuring-general-party-properties.md) o [configurar propiedades de entidad General (AS2)](../core/configuring-general-party-properties-as2.md)  
  
2. Para cada división de negocio de una organización, cree un perfil en el socio que represente la división de negocio. Por ejemplo, si una organización tiene las divisiones de negocio “Compra” y “Suministros”, cada una de estas divisiones deberá estar representada como perfil de negocio en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Además, debe crear los perfiles de negocio no solo para el socio que representa su organización, sino también para el socio con el que comercia. Para obtener instrucciones sobre cómo crear perfiles de negocio, consulte [configurar propiedades de perfil de negocio](../core/configuring-business-profile-properties.md).  
  
3. Para cada perfil de negocio, defina la configuración del protocolo B2B que incluya la configuración de codificación del mensaje y la configuración del protocolo de mensaje. Esta configuración define cómo se codifican y transportan los mensajes B2B entre dos perfiles de negocio.  
  
   > [!NOTE]
   >  Especificar la configuración del protocolo es opcional en esta etapa. Puede agregar directamente la configuración del protocolo como parte del acuerdo de socio comercial.  
  
4. Cree acuerdos de socios comerciales (TPA) entre los perfiles de negocio que definen los protocolos de codificación y/o mensajes que acuerdan usar los dos perfiles de negocio al intercambiar mensajes. Para obtener instrucciones sobre cómo crear acuerdos, vea [configurar propiedades de acuerdo específicas de X12](../core/configuring-x12-specific-agreement-properties.md), [configurar propiedades del acuerdo de EDIFACT específicos](../core/configuring-edifact-specific-agreement-properties.md), o [configuración AS2 Las propiedades del acuerdo](../core/configuring-as2-agreement-properties.md).  
  
   Al realizar el anterior conjunto de tareas, debe haber creado la solución TPM para intercambiar mensajes B2B con su socio comercial.  
  
## <a name="where-do-i-start"></a>¿Por dónde comenzar?  
 Puede iniciar a través de las siguientes secciones:  
  
-   Tutorial de X12 específicos en [Tutorial 2: EDI Interface Developer Tutorial](../core/tutorial-2-edi-interface-developer-tutorial.md).  
  
-   Tutorial de específicos de AS2 en [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md).  
  
-   X12-y EDIFACT-tutoriales específicos en [desarrollar y configurar soluciones de EDI de BizTalk Server](../core/developing-and-configuring-biztalk-server-edi-solutions.md).  
  
-   Tutoriales específicos de AS2 en [desarrollar y configurar soluciones de AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md).  
  
-   Crear entidades, perfiles y contratos para X12 y EDIFACT siguiendo las instrucciones en la mensajería [configurar propiedades de EDI](../core/configuring-edi-properties.md).  
  
-   Crear entidades, perfiles y mensajería siguiendo las instrucciones en los acuerdos de AS2 [configurar propiedades de AS2](../core/configuring-as2-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Bloques de creación de una solución de administración de socios comerciales](../core/building-blocks-of-a-trading-partner-management-solution.md)