---
title: Mediante la validación de datos dinámicos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic data validation
- validating, dynamic data
ms.assetid: 8dac7f74-92a7-447c-97bf-b1f3ce39b614
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b0ff37ff260ca11e594a208c125f229e2961c01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967165"
---
# <a name="using-dynamic-data-validation"></a>Usa la validación de datos dinámicos
Una parte importante de la validación de datos dinámicos está validando el contenido del mensaje con datos dinámicos, que incluye validar el formato del mensaje y el contenido del mensaje. Un esquema de documento, que implementa MicrosoftBizTalk Server en un archivo XSD, define y valida los formatos de mensaje. Las reglas de negocios definen el contenido del mensaje, que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] valida a través de directivas del motor de reglas de negocios. Validación de contenido puede incluir la confirmación de que los datos en la instancia de mensaje coinciden con los datos que pueden cambiar con frecuencia relativa. Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] implementa este tipo de validación de forma dinámica, para que pueda actualizar estos datos en un entorno de producción sin tener que volver a compilar el código o cerrar los servicios.  
  
## <a name="validate-and-expose-data"></a>Validar y exponer los datos  
 Hay dos pasos para realizar la validación de datos dinámicos (DDV):  
  
- Exponer los datos.  
  
- Aplicar reglas de validación con esos datos.  
  
  DDV proporciona la siguiente compatibilidad para almacenar, exponer y almacenar en caché datos dinámicos:  
  
- El motor de reglas de negocio o la clase de mensaje realiza la validación.  
  
- El motor de reglas de negocio expone los datos a través del vocabulario de columna de tabla de base de datos. El motor de reglas de negocio valida estos datos dinámicos frente a mensajes mediante la implementación de un conjunto de reglas que se ejecuta desde una canalización u orquestación.  
  
- Interfaces existentes de SQL, como SQL Enterprise Manager y analizador de consultas, exponen los datos dinámicos que es pasivos en tiempo de diseño.  
  
- La definición de vocabulario motor de reglas de negocio columna de tabla de base de datos expone los datos dinámicos en tiempo de ejecución.  
  
- El motor de reglas de negocio expone los datos de la instancia de mensaje en tiempo de ejecución.  
  
- Una definición de vocabulario de documento XML de motor de reglas de negocio expone los datos de la instancia de mensaje en tiempo de diseño.  
  
- Puede crear reglas en tiempo de diseño en la interfaz de usuario del compositor de reglas de negocio o directamente en las reglas de lenguaje negocios (BRL) XML en un editor de texto.  
  
  Para obtener más información acerca de las reglas de negocios y el motor de reglas de negocios, vea "Desarrollar con reglas de negocios" en la Ayuda de BizTalk Server.  
  
## <a name="extending-ddv"></a>Extender DDV  
 Si cambia en función de HL7 validación de campos cruzados o validación de tipo de datos, debe tener en cuenta dos cosas:  
  
-   Si modifica una regla existente, no es necesario volver a implementar.  
  
-   Si crea o elimina una nueva regla que afecta un componente de canalización, a continuación, debe volver a compilar.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)