---
title: Compatibilidad con HIPAA en BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1ad8c64-6375-4364-80ce-440db943c222
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7817e3b69edd0a34c13b92128f7ddba0f28a5586
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014765"
---
# <a name="hipaa-support-in-biztalk-server"></a>Compatibilidad con HIPAA en BizTalk Server
En este tema se proporciona una breve introducción a HIPAA y a cómo [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] es compatible con HIPAA.  
  
## <a name="introduction-to-hipaa"></a>Introducción a HIPAA  
 La Ley de transferencia y responsabilidad de seguros de salud de 1996 (HIPAA) requiere que las entidades cubiertas usen los estándares impuestos cuando realizan transacciones electrónicas como notificaciones, envíos, elegibilidad, solicitudes y respuestas de estado de notificaciones, etc. Las entidades cubiertas bajo HIPAA son planes de salud, centros de enrutamiento y la mayoría de los proveedores de atención médica.  
  
## <a name="hipaa-support-in-biztalk-server"></a>Compatibilidad HIPAA en BizTalk Server  
 Microsoft se compromete a ayudar a las organizaciones sanitarias y relacionadas a mejorar el modo en que sus servicios médicos se proporcionan y financian. Microsoft intenta reducir la cantidad de tiempo y dinero que las organizaciones deben gastar para cumplir las regulaciones de HIPAA.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda a las organizaciones a cumplir sus objetivos de crear procesos empresariales automatizados que se conecten e interoperen entre varios sistemas sanitarios. Las organizaciones afectadas por la HIPAA pueden aprovechar las capacidades de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el desarrollo, la implementación y la integración de soluciones compatibles con la transacción que también cumplan la ley federal.  
  
[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] incluye funcionalidad nativa que proporciona compatibilidad con HIPAA. No se trata de un complemento del producto, como pueden ser los adaptadores o aceleradores, Se encuentra integrado en el producto. [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] incluye el EDI componentes y capacidades que son necesarias para cumplan los mandatos de la HIPAA y también para adoptar la HIPAA como un proceso empresarial medido y bien administrado.  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] es compatible con las versiones 5010 y 4010 de la HIPAA.  
  
## <a name="hipaa-documentation-in-biztalk-server"></a>Documentación de HIPAA en BizTalk Server  
 Los estándares EDI más importantes son X12 (estandarizado por ANSI y usado principalmente en Norteamérica) y EDIFACT (estandarizado por las Naciones Unidas y usado principalmente fuera de los Estados Unidos). HIPAA es un estándar derivado de X12. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona compatibilidad con HIPAA, como parte de la funcionalidad nativa de EDI X12. Por lo tanto, siempre que vea referencias a la compatibilidad con X12 en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], esta compatibilidad también se aplica al procesamiento HIPAA, a menos que se indique lo contrario.  
  
 Las siguientes secciones [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contienen información específica acerca de HIPAA.  
  
 **Introducción**  
  
- [Conjuntos de transacciones de HIPAA](../core/hipaa-transaction-sets.md)  
  
  **Planificación y arquitectura**  
  
- [Versión de esquema del documento HIPAA 5010](../core/hipaa-document-schema-version-5010.md)  
  
- [Anotaciones del campo desencadenador del esquema HIPAA](../core/hipaa-schema-trigger-field-annotations.md)  
  
- [División de subdocumentos HIPAA](../core/splitting-hipaa-subdocuments.md)  
  
  **Desarrollo**  
  
- [Modificación de esquemas EDI](../core/modifying-edi-schemas.md) 

- [Personalización de enumeraciones en el esquema de sobres](../core/customizing-enumerations-in-the-envelope-schema.md)

- [Configuración de la validación de campos cruzados](../core/configuring-cross-field-validation.md)

  
 **Solucionar problemas**  
  
-   [Problemas conocidos del procesamiento de recepción de EDI](../core/known-issues-with-edi-receive-processing.md)  
  
-   [Problemas conocidos con las herramientas XML usadas con soluciones de EDI](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)  
  
## <a name="more-information-about-hipaa"></a>Para obtener más información acerca de HIPAA  
  
-   Para obtener información sobre el American National Standards Institute, Accredited Standards Committee para el intercambio de datos, vaya a [ASC X12 doméstica](http://www.x12.org/).  
  
-   Para obtener información sobre el Subcomité de seguros del X12 y su implementación guías adoptadas bajo HIPAA, vaya a [guías de EDI para HIPAA Washington Publishing Company](http://www.wpc-edi.com/).
  
-   Para obtener información sobre el grupo de trabajo para el intercambio de datos, vaya a [grupo de trabajo de la página principal de intercambio de datos electrónicos](http://www.wedi.org/).