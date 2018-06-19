---
title: Mediante la validación de datos dinámicos | Documentos de Microsoft
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
ms.openlocfilehash: 3387117648329828c9276545eafddca6872c4aa2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009045"
---
# <a name="using-dynamic-data-validation"></a>Mediante la validación de datos dinámicos
Una parte importante de la validación de datos dinámicos se está validando contenido del mensaje con datos dinámicos, que incluye validar el formato del mensaje y el contenido del mensaje. Un esquema de documento, que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server se implementa en un archivo XSD, define y valida los formatos de mensaje. Las reglas de negocios definen el contenido del mensaje, que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] valida a través de directivas de motor de reglas de negocios. Validación de contenido puede incluir la confirmación de que los datos en la instancia de mensaje coincide con los datos que pueden cambiar con relativa frecuencia. [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]implementa este tipo de validación de forma dinámica, para que pueda actualizar estos datos en un entorno de producción, sin tener que compilar el código o cerrar los servicios.  
  
## <a name="validate-and-expose-data"></a>Validar y exponer los datos  
 Existen dos pasos para realizar la validación de datos dinámicos (DDV):  
  
-   Exponer los datos.  
  
-   Aplicar reglas de validación utilizando esos datos.  
  
 DDV proporciona la siguiente compatibilidad para almacenar, exponer y almacenar en caché datos dinámicos:  
  
-   El motor de reglas de negocios o la clase de mensaje realiza la validación.  
  
-   El motor de reglas de negocios expone los datos a través del vocabulario de columna de tabla de base de datos. El motor de reglas de negocios valida estos datos dinámicos frente a mensajes mediante la implementación de un conjunto de reglas que se ejecuta desde una canalización u orquestación.  
  
-   Interfaces de SQL existente, como el Administrador corporativo de SQL y el analizador de consultas, exponer datos dinámicos que es pasivos en tiempo de diseño.  
  
-   La definición de vocabulario de motor de reglas de negocios base de datos tabla columna expone datos dinámicos en tiempo de ejecución.  
  
-   El motor de reglas de negocios expone los datos de la instancia de mensaje en tiempo de ejecución.  
  
-   Una definición de vocabulario de documento XML de motor de reglas de negocios expone los datos de la instancia de mensaje en tiempo de diseño.  
  
-   Puede crear reglas en tiempo de diseño en la interfaz de usuario del compositor de reglas de negocio o directamente en las reglas de lenguaje negocios (BRL) XML en un editor de texto.  
  
 Para obtener más información acerca de las reglas de negocios y el motor de reglas de negocios, vea "Desarrollar con reglas de negocios" en la Ayuda de BizTalk Server.  
  
## <a name="extending-ddv"></a>Extender DDV  
 Si cambia la validación de campos cruzados basada en HL7 o validación de tipo de datos, se deben tener en cuenta dos cosas:  
  
-   Si modifica una regla existente, no es necesario volver a implementar.  
  
-   Si crea o eliminar una nueva regla que afecta un componente de canalización, a continuación, debe volver a compilar.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)