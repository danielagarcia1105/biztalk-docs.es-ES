---
title: La necesidad de integración de sistemas de atención médica | Documentos de Microsoft
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
ms.openlocfilehash: b7674cff1c9c1e787c0ab9638e0abad407adafea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207236"
---
# <a name="the-need-for-health-care-systems-integration"></a>La necesidad de integración de sistemas de atención médica
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] proporciona proveedores de atención médica con soluciones para sus necesidades de automatización de procesos de negocios e integración de aplicaciones. En este tema se describe algunos de los desafíos de negocios que se enfrentan las organizaciones sanitaria y cómo sistemas que incorporan [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] puede ayudar a las organizaciones a cumplir los desafíos. También Eche un vistazo a un escenario común que muestra un escenario empresarial de ejemplo con [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)].  
  
## <a name="health-care-business-challenge"></a>Desafío para el negocio sanitaria

Las organizaciones de atención sanitaria son entidades empresariales son complejas con muchas partes distintas pero conectadas. Para un hospital pueden incluir estos departamentos admisión, laboratorios, estaciones de reposo, médicos y facturación. Todos estos departamentos generarán y consumen datos. Los datos pueden incluir información acerca de los pacientes, la facturación, procedimientos y medicamentos. A menudo, las organizaciones necesitan estos datos a través de muchas de sus departamentos. Un desafío común para la organización sanitaria es cómo tratar eficazmente con el intercambio de datos entre departamentos.  
  
 La siguiente ilustración muestra cuántos departamentos pueden comunicarse entre sí, crear un sistema complejo.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-no-btahl7.gif "hl7_no_btahl7")  
  
 Muchos de estos departamentos también tienen procesos empresariales distintos. El personal de un departamento puede ha creado, implementan y mantienen sus propios procesos. Estos procesos pueden afectar a otros departamentos, pero el personal puede no se han diseñado con los otros departamentos en cuenta.  
  
 Lograr un mayor control sobre los procesos en el alcance total de la organización es un problema para muchas organizaciones de atención médica.  
  
## <a name="health-care-business-solution"></a>Solución empresarial de atención médica

Tecnología puede ayudar a resolver los desafíos de negocios relacionadas con datos y procesos empresariales. Información de sistemas de tecnología (TI) pueden ayudar a las organizaciones sanitarios transformar sus operaciones internas de procesos desconectados, incompatibles, para integrado, estandarizado llaves.  
  
### <a name="integration"></a>Integración  
 Incluso si los procesos de partes individuales de una organización de atención sanitaria no son compatibles de forma inherente, puede integrarlos. Se puede asociar junto con la tecnología que transforma un sistema que se caracteriza por conexiones de punto a punto (como se muestra en la ilustración de desafío para el negocio sanitaria (en este tema) a una basada en una organización de concentrador y radio, tal como se muestra en la ilustración siguiente.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-yes-btahl7.gif "hl7_yes_btahl7")  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]consigue esta integración mediante la conexión a cada departamento independiente o una entidad y proporcionar los mecanismos que enlazar los procesos y resolver sus diferencias. También automatiza el intercambio de datos, para que pueden ejecutar procesos empresariales con un mínimo de intervención humana.  
  
### <a name="standardization"></a>Estandarización  
 Una vez que se han conectado los procesos empresariales, los procesos pueden intercambiar datos. Sin embargo, si los datos mantenidos por departamentos diferentes en diferentes formatos y sistemas de protocolos de transporte, aunque diferentes datos, el intercambio de datos puede requerir un esfuerzo significativo para el diseño del sistema y la personalización. Puede mejorar considerablemente la eficacia de este proceso si cada uno de los departamentos conectados normaliza el formato y el protocolo que se utiliza con su intercambio de datos.  
  
 Esto es lo que ha hecho la organización HL7. Formatos comunes para los datos de atención sanitaria, han creado en el formulario de esquemas de archivo sin formato. Sus esfuerzos han tenido mucho éxito, hasta el punto que un porcentaje alto de hospitales grandes ha adoptado los estándares.  
  
### <a name="solutions-specific-to-the-health-care-industry"></a>Soluciones específicas para el sector sanitario  
 Sistemas de TI integrados e intercambio de datos normalizado han proporcionado la base para el estado más eficaz procesos de atención. Una solución de TI verdaderamente efectiva para los sistemas de atención sanitaria es aquella que se centra en los problemas en dicho sector y proporciona la funcionalidad, características y herramientas que tratar las necesidades de las organizaciones de atención médica.  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]proporciona esa solución. Instalar [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] sobre [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]. [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]funciona con los esquemas creadas y mantenidas por la organización de HL7. Además, proporciona características y herramientas diseñadas específicamente para las aplicaciones de atención médica. [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]habilita el procesamiento por lotes, confirmaciones, validación de datos, auditoría y registro necesitan por las organizaciones de atención médica.  
  
## <a name="next"></a>Siguiente
Leer un [escenario empresarial de ejemplo](../../adapters-and-accelerators/accelerator-hl7/sample-business-scenario.md).
