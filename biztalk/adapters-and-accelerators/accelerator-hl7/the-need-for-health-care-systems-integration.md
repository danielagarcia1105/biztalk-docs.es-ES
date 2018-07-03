---
title: La necesidad de integración de sistemas de atención médica | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- health care organizations
ms.assetid: e747b633-c898-473c-be7d-ba00bfdbdc21
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2527b3174b0497025e070a9228f420a31523f24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972885"
---
# <a name="the-need-for-health-care-systems-integration"></a>La necesidad de integración de sistemas de atención médica
Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] proporciona proveedores de atención médica con soluciones para sus necesidades de automatización de procesos de negocios e integración de aplicaciones. En este tema se describe algunos de los desafíos de negocio que se enfrentan las organizaciones de atención médica y cómo los sistemas que incorpora Microsoft [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] pueden ayudar a las organizaciones a cumplir estos desafíos. También Eche un vistazo a un escenario común que muestra un ejemplo de escenario empresarial con [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)].  
  
## <a name="health-care-business-challenge"></a>Reto empresarial sanitaria

Las organizaciones de atención médica son entidades de negocios compleja con muchas partes distintas pero conectadas. Para un hospital, pueden incluir estos departamentos admisión, laboratorios, estaciones de pacientes, los médicos y facturación. Todos estos departamentos generarán y consumirán datos. Los datos pueden incluir información acerca de los pacientes, facturación, procedimientos y los medicamentos. A menudo, las organizaciones necesitan estos datos a través de muchos de sus departamentos. Un desafío común para la organización sanitaria es cómo tratar eficazmente con el intercambio de datos entre los departamentos de TI.  
  
 En la siguiente ilustración se muestra cuántos de los departamentos de TI pueden comunicarse entre sí, crear un sistema complejo.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-no-btahl7.gif "hl7_no_btahl7")  
  
 Muchos de estos departamentos también tienen procesos de negocio distintos. El personal de un departamento es posible que ha creado, implementan y mantienen sus propios procesos. Estos procesos pueden afectar a otros departamentos, pero el personal es posible que no están diseñadas con los otros departamentos en mente.  
  
 Lograr un mayor control sobre los procesos en el alcance total de la organización es un problema para muchas organizaciones de atención médica.  
  
## <a name="health-care-business-solution"></a>Solución empresarial de atención médica

Tecnología puede ayudar a resolver los desafíos de negocio relacionadas con datos y procesos empresariales. Información de los sistemas de TI pueden ayudar a las organizaciones de atención médica a transformar sus operaciones internas de procesos desconectados, incompatibles, para integrado, aquellas estandarizado.  
  
### <a name="integration"></a>Integración  
 Incluso si los procesos de partes individuales de una organización sanitaria no son compatibles de forma inherente, puede integrarlos. Vincularlas junto con la tecnología que transforma un sistema que se caracterizan por las conexiones de punto a punto (como se muestra en la figura reto empresarial de sanidad (en este tema) a uno basado en una organización de concentrador y radio, tal como se muestra en la ilustración siguiente.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-yes-btahl7.gif "hl7_yes_btahl7")  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] consigue esta integración al conectarse a cada departamento independiente o una entidad y proporcionar los mecanismos que se enlazan los procesos juntos, resolver sus diferencias. También automatiza el intercambio de datos, para que pueden ejecutar los procesos empresariales con una mínima intervención humana.  
  
### <a name="standardization"></a>Estandarización  
 Cuando se han conectado los procesos de negocio, los procesos pueden intercambiar datos. Sin embargo, si los datos mantenidos por departamentos diferentes están en diferentes formatos y sistemas de protocolos de transporte, aunque diferentes datos, el intercambio de datos puede requerir un esfuerzo significativo en el diseño del sistema y la personalización. Puede mejorar considerablemente la eficacia de este proceso si cada uno de los departamentos conectados estandariza el formato y el protocolo utilizado con el intercambio de datos.  
  
 Esto es lo que ha hecho la organización de HL7. Formatos comunes para los datos de atención médica, han creado en el formulario de esquemas de archivo sin formato. Sus esfuerzos han tenido mucho éxito, hasta el punto en que un porcentaje elevado de hospitales grandes ha adoptado sus estándares.  
  
### <a name="solutions-specific-to-the-health-care-industry"></a>Soluciones específicas para el sector sanitario  
 Intercambio estandarizado de datos y sistemas integrados de TI han proporcionado la base para el estado más eficaz los procesos de atención. Una solución de TI realmente eficaz para los sistemas de atención médica es aquella que se centra en los problemas en dicho sector y proporciona la funcionalidad, características y herramientas que abordan las necesidades de organizaciones de atención médica.  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] proporciona esa solución. Instalar [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] en la parte superior de [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]. [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] funciona con los esquemas se crea y mantiene por la organización de HL7. Además, proporciona las características y herramientas diseñadas específicamente para las aplicaciones de atención médica. [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] habilita el procesamiento por lotes, confirmaciones, validación de datos, auditoría y registro se necesitan las organizaciones de atención médica.  
  
## <a name="next"></a>Siguiente
Leer un [ejemplo de escenario empresarial](../../adapters-and-accelerators/accelerator-hl7/sample-business-scenario.md).
