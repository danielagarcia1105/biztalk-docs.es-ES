---
title: HIPAA versión 5010 del esquema de documento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62e50964-66e1-4ed9-a1a1-68556b13b024
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6566110e3388e6b955dbd3c0cd9fe8781d853796
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989333"
---
# <a name="hipaa-document-schema-version-5010"></a>Versión de esquema del documento HIPAA 5010
El valor predeterminado para inglés Departamento de salud y servicios humanos (HHS) ha anunciado una regla final el 16 de enero de 2009 que reemplaza a la actual versión 4010A1 HIPAA versión 5010. La versión 5010 de las normas HIPAA incluye mejoras en preliminares estructural, de técnicas y el contenido de datos. Estas mejoras reducirán y eliminarán ambigüedades de datos mientras se atiende la algunas necesidades empresariales anteriormente no satisfechas. BizTalk Server proporciona compatibilidad con HIPAA versión 5010.  

> [!NOTE]
>  BizTalk Server sigue admitiendo HIPAA versión 4010A1.  

## <a name="hipaa-5010-version-support"></a>Compatibilidad de versiones de HIPAA 5010  
 Se han introducido los siguientes cambios como parte de la compatibilidad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con HIPAA 5010:  

- **Nuevos esquemas de sustitución**: versión HIPAA 5010 presenta los siguientes nuevos esquemas de reemplazo a través de la anterior versión 4010A1. Esquemas EDI están comprimidos y se proporcionan en el archivo ejecutable, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe. Cuando se ejecuta, MicrosoftEdiXSDTemplates.exe deposita esquemas HIPAA 5010 en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]carpeta XSD_Schema\EDI\HIPAA\5010.  


  |  GS08/ST03   | Id. de conjunto (ST01) |                       Descripción                       |
  |--------------|----------------|---------------------------------------------------------|
  |  005010X279  |      270       |   Elegibilidad, cobertura o consulta de beneficio - solicitud    |
  |  005010X279  |      271       | Elegibilidad, cobertura o información de beneficio - respuesta |
  |  005010X212  |      276       |           Estado de reclamación de atención médica - solicitud            |
  |  005010X212  |      277       |           Estado de Reclamación de atención médica - respuesta           |
  |  005010X217  |      278       |   Revisión de servicios de asistencia sanitaria: solicitud y respuesta    |
  |  005010X218  |      820       |                    Deducción en nómina                    |
  |  005010X220  |      834       |    Inscripción y mantenimiento de beneficio(s) de atención médica    |
  |  005010X221  |      835       |              Pago(s) de reclamaciones de atención médica               |
  |  005010X222  |      837       |           Reclamaciones de atención médica - profesional           |
  | 005010X223A1 |      837       |          Reclamaciones de atención médica - institucional           |
  | 005010X224A1 |      837       |              Reclamaciones de atención médica - dental              |


- **Soporte técnico para el campo ST03**: versión 5010 impone la presencia de ST03 en toda la transacción establece distinto 835 (Payment(s)) de Reclamación de atención médica. ST03 se usa para identificar la versión del conjunto de transacciones. ST03 permite diferentes versiones de conjuntos de transacciones dentro de un único grupo. ST03 tiene prioridad sobre GS08 a la hora de identificar la versión del conjunto de transacciones. Puede escribir y promocionar ST03 debajo del espacio de nombres del esquema de propiedades EDI como propiedad de contexto y enrutar los mensajes basándose en ST03.  

- **Compatibilidad con conjuntos de transacciones similares dentro de un grupo**: X12 los estándares proporcionan una asignación entre conjuntos de transacciones y grupos, conocida como la asignación ST01-GS01. Esta asignación se usa para validar conjuntos de transacciones similares que se pueden combinar en un único grupo (GS-GE). Para HIPAA, esto supone que puede tener lugar una reclamación Profesional, Institucional y Dental 837 en un único grupo.  

- **Compatibilidad con ICD-10**: conjuntos de transacciones electrónicas de código se utilizan para la transmisión de datos sanitarios. La versión 5010 permite el uso de los conjuntos de códigos de la Clasificación Internacional de Enfermedades (ICD-10), que no se admitían en la versión anterior 4010A1. ICD-10 se usa para identificar diversos diagnósticos y procedimientos en la reclamación de facturas relacionados con transacciones e informes clínicos. Las ventajas del uso de ICD-10 son la mayor exactitud en los datos de los servicios al paciente, del diagnóstico y de la información del tratamiento, y unos informes más exhaustivos de datos de calidad.  

- **Nuevos campos en 5010 997**: 997 la confirmación funcional esquema proporcionado-de-fábrica por BizTalk Server introduce tres nuevos campos opcionales concretamente AK103, AK203 y AK41.3. El motor de EDI es capaz de procesamiento de una entrada 5010 mensaje 997 que contiene estos campos, pero no generará una confirmación 997 de salida basándose en el nuevo esquema.  

  Había un problema conocido con los esquemas HIPAA 4010A1 en los cuales los elementos del tipo de datos X12_R no se comprobaban contra sus longitudes mínima y máxima. En BizTalk Server se ha corregido este problema y los esquemas HIPAA 5010 validan los elementos del tipo de datos X12_R para las longitudes mínima y máxima.  

## <a name="see-also"></a>Vea también  
 [Compatibilidad con HIPAA en BizTalk Server](../core/hipaa-support-in-biztalk-server.md)   
 [División de subdocumentos HIPAA](../core/splitting-hipaa-subdocuments.md)